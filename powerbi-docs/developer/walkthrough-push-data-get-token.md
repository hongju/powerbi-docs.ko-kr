---
title: 인증 액세스 토큰 가져오기
description: 데이터 푸시 연습 - 인증 액세스 토큰 가져오기
author: rkarlin
ms.author: rkarlin
ms.reviewer: madia
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 05/29/2019
ms.openlocfilehash: f6e0bbec2275407e963d5b97e6d780089fedc0ae
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2019
ms.locfileid: "73875692"
---
# <a name="step-2-get-an-authentication-access-token"></a>2단계: 인증 액세스 토큰 가져오기

이 문서는 시리즈 [Power BI 데이터 세트에 데이터 푸시](walkthrough-push-data.md)의 두 번째 단계입니다.

1단계에서 [Azure AD에 클라이언트 앱을 등록했습니다](walkthrough-push-data-register-app-with-azure-ad.md). 이 단계에서는 인증 액세스 토큰을 가져옵니다. Power BI 앱이 Azure Active Directory와 통합되어 앱에 보안 로그인 및 앱에 권한 부여를 제공합니다. 앱은 토큰을 사용하여 Azure AD에 인증하고 Power BI 리소스에 액세스합니다.

## <a name="get-an-authentication-access-token"></a>인증 액세스 토큰 가져오기

시작하기 전에 [Power BI 데이터 세트에 데이터 푸시](walkthrough-push-data.md) 시리즈에서 [이전 단계](walkthrough-push-data-register-app-with-azure-ad.md)를 완료했는지 확인합니다. 

이 프로시저를 수행하려면 Visual Studio 2015 이상이 필요합니다.

1. Visual Studio에서 새 C# **콘솔 애플리케이션** 프로젝트를 만듭니다.

2. [.NET NuGet 패키지용 Azure AD 인증 라이브러리](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/2.22.302111727)를 설치합니다. .Net 앱에서 인증 보안 토큰을 가져오려면 이 패키지가 필요합니다. 

     a. **도구** > **NuGet 패키지 관리자** > **패키지 관리자 콘솔**을 선택합니다.

     b. **Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory -Version 2.21.301221612**를 입력합니다.

     c. Program.cs에 `using Microsoft.IdentityModel.Clients.ActiveDirectory;`를 추가합니다.

3. 이 단계 다음에 나열된 샘플 코드를 Program.cs에 추가합니다.

4. 앱을 등록할 때 [이전 시리즈 문서](walkthrough-push-data-register-app-with-azure-ad.md)에서 가져온 **클라이언트 ID**가 있는 "{ClientID}"로 바꿉니다.

5. 콘솔 앱을 실행하고 Power BI 계정에 로그인합니다. 

   토큰 문자열이 콘솔 창에 나타나야 합니다.

**인증 보안 토큰을 가져오는 샘플 코드**

Program {...}에 이 코드를 추가합니다.

* 작업을 호출하는 토큰 변수: 
  
  ```csharp
  private static string token = string.Empty;
  
  static void Main(string[] args)
  {
  }
  ```
* static void Main(string[] args)에서:
  
  ```csharp
  static void Main(string[] args)
  {
    //Get an authentication access token
    token = GetToken();
  }
  ```
* GetToken() 메서드 추가:

```csharp
       #region Get an authentication access token
       private static string GetToken()
       {
           // TODO: Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory -Version 2.21.301221612
           // and add using Microsoft.IdentityModel.Clients.ActiveDirectory

           //The client id that Azure AD created when you registered your client app.
           string clientID = "{Client_ID}";

           //RedirectUri you used when you register your app.
           //For a client app, a redirect uri gives Azure AD more details on the application that it will authenticate.
           // You can use this redirect uri for your client app
           string redirectUri = "https://login.live.com/oauth20_desktop.srf";

           //Resource Uri for Power BI API
           string resourceUri = "https://analysis.windows.net/powerbi/api";

           //OAuth2 authority Uri
           string authorityUri = "https://login.microsoftonline.net/common/";

           //Get access token:
           // To call a Power BI REST operation, create an instance of AuthenticationContext and call AcquireToken
           // AuthenticationContext is part of the Active Directory Authentication Library NuGet package
           // To install the Active Directory Authentication Library NuGet package in Visual Studio,
           //  run "Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory" from the nuget Package Manager Console.

           // AcquireToken will acquire an Azure access token
           // Call AcquireToken to get an Azure token from Azure Active Directory token issuance endpoint
           AuthenticationContext authContext = new AuthenticationContext(authorityUri);
           string token = authContext.AcquireToken(resourceUri, clientID, new Uri(redirectUri)).AccessToken;

           Console.WriteLine(token);
           Console.ReadLine();

           return token;
       }

       #endregion
```

인증 토큰을 가져온 후에는 원하는 Power BI 작업을 호출할 수 있습니다.

이 시리즈의 다음 문서에서는 [Power BI에서 데이터 세트를 만드는](walkthrough-push-data-create-dataset.md) 방법을 보여 줍니다.


## <a name="complete-code-listing"></a>전체 코드 목록

```csharp
using System;
using Microsoft.IdentityModel.Clients.ActiveDirectory;

namespace walkthrough_push_data
{
    class Program
    {
        private static string token = string.Empty;

        static void Main(string[] args)
        {

            //Get an authentication access token
            token = GetToken();

        }

        #region Get an authentication access token
        private static string GetToken()
        {
            // TODO: Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory -Version 2.21.301221612
            // and add using Microsoft.IdentityModel.Clients.ActiveDirectory

            //The client id that Azure AD created when you registered your client app.
            string clientID = "{Client_ID}";

            //RedirectUri you used when you register your app.
            //For a client app, a redirect uri gives Azure AD more details on the application that it will authenticate.
            // You can use this redirect uri for your client app
            string redirectUri = "https://login.live.com/oauth20_desktop.srf";

            //Resource Uri for Power BI API
            string resourceUri = "https://analysis.windows.net/powerbi/api";

            //OAuth2 authority Uri
            string authorityUri = "https://login.microsoftonline.com/common/";

            //Get access token:
            // To call a Power BI REST operation, create an instance of AuthenticationContext and call AcquireToken
            // AuthenticationContext is part of the Active Directory Authentication Library NuGet package
            // To install the Active Directory Authentication Library NuGet package in Visual Studio,
            //  run "Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory" from the nuget Package Manager Console.

            // AcquireToken will acquire an Azure access token
            // Call AcquireToken to get an Azure token from Azure Active Directory token issuance endpoint
            AuthenticationContext authContext = new AuthenticationContext(authorityUri);
            string token = authContext.AcquireToken(resourceUri, clientID, new Uri(redirectUri)).AccessToken;

            Console.WriteLine(token);
            Console.ReadLine();

            return token;
        }

        #endregion

    }
}
```



## <a name="next-steps"></a>다음 단계

[이 시리즈의 다음 문서 > Power BI에서 데이터 세트 만들기](walkthrough-push-data-create-dataset.md)

[Power BI REST API 개요](overview-of-power-bi-rest-api.md)  
[Power BI REST API](https://docs.microsoft.com/rest/api/power-bi/)  

궁금한 점이 더 있나요? [Power BI 커뮤니티를 이용하세요.](https://community.powerbi.com/)