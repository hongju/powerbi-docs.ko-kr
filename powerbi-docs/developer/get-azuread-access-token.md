---
title: 사용자를 인증하고 응용 프로그램에 대한 Azure AD 액세스 토큰 가져오기
description: Power BI 콘텐츠 포함에 사용하기 위해 Azure Active Directory 내에서 응용 프로그램을 등록하는 방법에 대해 알아봅니다.
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 08/11/2017
ms.author: maghan
ms.openlocfilehash: 339390bba2e35101bdd42f7f51ab059473231575
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/17/2018
---
# <a name="authenticate-users-and-get-an-azure-ad-access-token-for-your-power-bi-app"></a>사용자를 인증하고 Power BI 앱에 대한 Azure AD 액세스 토큰 가져오기
Power BI 응용 프로그램 내에서 사용자를 인증하고 REST API와 함께 사용할 액세스 토큰을 검색할 수 있는 방법을 알아봅니다.

Power BI REST API를 호출할 수 있으려면, Azure Active Directory(Azure AD) **인증 액세스 토큰**(액세스 토큰)이 있어야 합니다. **액세스 토큰**은 앱이 **Power BI** 대시보드, 타일 및 보고서에 액세스하도록 허용하는 데 사용됩니다. Azure Active Directory **액세스 토큰** 흐름에 대해 자세히 알아보려면, [Azure AD 인증 코드 부여 흐름](https://msdn.microsoft.com/library/azure/dn645542.aspx)을 참조하세요.

콘텐츠를 포함하는 방법에 따라 액세스 토큰은 다르게 검색됩니다. 이 문서에서는 두 가지 방법이 사용됩니다.

## <a name="access-token-for-power-bi-users-user-owns-data"></a>Power BI 사용자(사용자 소유 데이터)에 대한 액세스 토큰
이 예제는 사용자가 조직 로그인을 사용하여 Azure AD에 수동으로 로그인할 때에 대한 것입니다. Power BI 서비스 내에서 액세스 권한이 있는 콘텐츠에 액세스하는 Power BI 사용자를 위한 콘텐츠를 포함할 때 사용됩니다.

### <a name="get-an-authorization-code-from-azure-ad"></a>Azure AD에서 인증 코드 가져오기
**액세스 토큰**을 가져오는 첫 번째 단계는 **Azure AD**에서 인증 코드를 가져오는 것입니다. 이렇게 하려면, 다음 속성을 포함하는 쿼리 문자열을 생성하고 **Azure AD**에 리디렉션합니다.

**인증 코드 쿼리 문자열**

```
var @params = new NameValueCollection
{
    //Azure AD will return an authorization code. 
    //See the Redirect class to see how "code" is used to AcquireTokenByAuthorizationCode
    {"response_type", "code"},

    //Client ID is used by the application to identify themselves to the users that they are requesting permissions from. 
    //You get the client id when you register your Azure app.
    {"client_id", Properties.Settings.Default.ClientID},

    //Resource uri to the Power BI resource to be authorized
    // https://analysis.windows.net/powerbi/api
    {"resource", Properties.Settings.Default.PowerBiAPI},

    //After user authenticates, Azure AD will redirect back to the web app
    {"redirect_uri", "http://localhost:13526/Redirect"}
};
```

쿼리 문자열을 생성한 후에 **Azure AD**를 리디렉션하여 **인증 코드**를 가져옵니다.  다음은 **인증 코드** 쿼리 문자열을 생성하고 **Azure AD**에 리디렉션하는 전체 C# 메서드입니다. 인증 코드를 가져온 후 **인증 코드**를 사용하여 **액세스 토큰**을 가져옵니다.

그런 다음 Redirect.aspx.cs 내의 [AuthenticationContext.AcquireTokenByAuthorizationCode](https://msdn.microsoft.com/library/azure/dn479531.aspx)이 토큰을 생성하기 위해 호출됩니다.

**인증 코드 가져오기**

```
protected void signInButton_Click(object sender, EventArgs e)
{
    //Create a query string
    //Create a sign-in NameValueCollection for query string
    var @params = new NameValueCollection
    {
        //Azure AD will return an authorization code. 
        //See the Redirect class to see how "code" is used to AcquireTokenByAuthorizationCode
        {"response_type", "code"},

        //Client ID is used by the application to identify themselves to the users that they are requesting permissions from. 
        //You get the client id when you register your Azure app.
        {"client_id", Properties.Settings.Default.ClientID},

        //Resource uri to the Power BI resource to be authorized
        // https://analysis.windows.net/powerbi/api
        {"resource", Properties.Settings.Default.PowerBiAPI},

        //After user authenticates, Azure AD will redirect back to the web app
        {"redirect_uri", "http://localhost:13526/Redirect"}
    };

    //Create sign-in query string
    var queryString = HttpUtility.ParseQueryString(string.Empty);
    queryString.Add(@params);

    //Redirect authority
    //Authority Uri is an Azure resource that takes a client id to get an Access token
    // AADAuthorityUri = https://login.windows.net/common/oauth2/authorize/
    string authorityUri = Properties.Settings.Default.AADAuthorityUri;
    var authUri = String.Format("{0}?{1}", authorityUri, queryString);
    Response.Redirect(authUri);
}
```

### <a name="get-an-access-token-from-authorization-code"></a>인증 코드에서 액세스 토큰 가져오기
이제 Azure AD에서 인증 코드를 가져와야 합니다. **Azure AD**가 **인증 코드**를 사용하여 웹앱에 다시 리디렉션되면, **인증 코드**를 사용하여 액세스 토큰을 가져옵니다. 다음은 default.aspx 페이지에 대한 리디렉션 페이지나 Page_Load 이벤트에 사용할 수 있는 C# 샘플입니다.

**Microsoft.IdentityModel.Clients.ActiveDirectory** 네임스페이스는 [Active Directory 인증 라이브러리](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/) NuGet 패키지에서 검색할 수 있습니다.

```
Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory
```

**Redirect.aspx.cs**

```
using Microsoft.IdentityModel.Clients.ActiveDirectory;

protected void Page_Load(object sender, EventArgs e)
{
    //Redirect uri must match the redirect_uri used when requesting Authorization code.
    string redirectUri = String.Format("{0}Redirect", Properties.Settings.Default.RedirectUrl);
    string authorityUri = Properties.Settings.Default.AADAuthorityUri;

    // Get the auth code
    string code = Request.Params.GetValues(0)[0];

    // Get auth token from auth code
    TokenCache TC = new TokenCache();

    AuthenticationContext AC = new AuthenticationContext(authorityUri, TC);
    ClientCredential cc = new ClientCredential
        (Properties.Settings.Default.ClientID,
        Properties.Settings.Default.ClientSecret);

    AuthenticationResult AR = AC.AcquireTokenByAuthorizationCode(code, new Uri(redirectUri), cc);

    //Set Session "authResult" index string to the AuthenticationResult
    Session[_Default.authResultString] = AR;

    //Redirect back to Default.aspx
    Response.Redirect("/Default.aspx");
}
```

**Default.aspx**

```
using Microsoft.IdentityModel.Clients.ActiveDirectory;

protected void Page_Load(object sender, EventArgs e)
{

    //Test for AuthenticationResult
    if (Session[authResultString] != null)
    {
        //Get the authentication result from the session
        authResult = (AuthenticationResult)Session[authResultString];

        //Show Power BI Panel
        signInStatus.Visible = true;
        signInButton.Visible = false;

        //Set user and token from authentication result
        userLabel.Text = authResult.UserInfo.DisplayableId;
        accessTokenTextbox.Text = authResult.AccessToken;
    }
}
```

## <a name="access-token-for-non-power-bi-users-app-owns-data"></a>비Power BI 사용자(앱 소유 데이터) 포함에 대한 액세스 토큰
이 방법은 앱이 데이터에 대한 액세스를 소유한 ISV 유형 응용 프로그램에 일반적으로 사용됩니다. 사용자가 Power BI 사용자일 필요는 없으며 응용 프로그램이 인증 및 최종 사용자의 액세스를 컨트롤합니다.

이 방법은 단일 *마스터* 계정인 Power BI Pro 사용자를 사용합니다. 이 계정에 대한 자격 증명은 응용 프로그램과 함께 저장됩니다. 응용 프로그램은 이러한 저장된 자격 증명으로 Azure AD에 대해 인증합니다. 아래와 같은 예제 코드는 [앱 소유 데이터 샘플](https://github.com/guyinacube/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data)에서 가져옵니다.

**HomeController.cs**

```
using Microsoft.IdentityModel.Clients.ActiveDirectory;

// Create a user password cradentials.
var credential = new UserPasswordCredential(Username, Password);

// Authenticate using created credentials
var authenticationContext = new AuthenticationContext(AuthorityUrl);
var authenticationResult = await authenticationContext.AcquireTokenAsync(ResourceUrl, ClientId, credential);

if (authenticationResult == null)
{
    return View(new EmbedConfig()
    {
        ErrorMessage = "Authentication Failed."
    });
}

var tokenCredentials = new TokenCredentials(authenticationResult.AccessToken, "Bearer");
```

**Await** 사용에 대한 자세한 내용은 [await (C# 참조)](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/await)를 참조하세요.

## <a name="next-steps"></a>다음 단계
이제 액세스 토큰을 가졌으므로, 콘텐츠를 포함하기 위해 Power BI REST API를 호출할 수 있습니다. 콘텐츠를 포함하는 방법에 대한 정보는 [Power BI 대시보드, 보고서 및 타일을 포함하는 방법](embedding-content.md#step-2-embed-your-content)을 참조하세요.

궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](http://community.powerbi.com/)

