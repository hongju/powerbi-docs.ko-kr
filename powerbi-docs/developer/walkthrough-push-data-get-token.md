---
title: "인증 액세스 토큰 가져오기"
description: "데이터 푸시 연습 - 인증 액세스 토큰 가져오기"
services: powerbi
documentationcenter: 
author: guyinacube
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: get-started-article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 08/10/2017
ms.author: asaxton
ms.openlocfilehash: 068baa78315bfc7e4f7078ed47596a480dbe3765
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2017
---
# <a name="step-2-get-an-authentication-access-token"></a>2단계: 인증 액세스 토큰 가져오기
이 문서는 [데이터 집합에 데이터를 푸시](walkthrough-push-data.md)하는 단계별 연습의 일부입니다.

데이터 집합에 데이터 푸시의 **1단계**인 [Azure AD에 앱 등록](walkthrough-push-data-register-app-with-azure-ad.md)에서는 Azure AD에 클라이언트 앱을 등록했습니다. 이 단계에서는 인증 액세스 토큰을 가져옵니다. Power BI 앱이 **Azure AD** 와 통합되어 보안 로그인 및 앱에 대한 권한 부여를 제공합니다. 토큰을 사용하여 **Azure AD** 에 인증하고 Power BI 리소스에 액세스할 수 있습니다.

인증 액세스 토큰을 가져오는 방법은 다음과 같습니다.

## <a name="get-an-authentication-access-token"></a>인증 액세스 토큰 가져오기
> **참고**: 시작하기 전에 [데이터 집합에 데이터 푸시](walkthrough-push-data.md)의 이전 단계를 수행해야 합니다.
> 
> 

1. Visual Studio 2015에서 **콘솔 응용 프로그램** 프로젝트를 만듭니다.
2. [.NET NuGet 패키지용 Azure AD 인증 라이브러리](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)를 설치합니다. .NET 앱에서 인증 보안 토큰을 가져오려면 이 패키지를 사용합니다. 패키지를 설치하는 방법은 다음과 같습니다.
   
     a. Visual Studio 2015에서 **도구** > **NuGet 패키지 관리자** > **패키지 관리자 콘솔**을 선택합니다.
   
     b. **패키지 관리자 콘솔**에서 Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory -Version 2.21.301221612를 입력합니다.
3. 아래 코드를 class Program {...}에 추가합니다.
4. "{ClientID}"는 앱을 등록할 때 가져온 **클라이언트 ID** 로 바꿉니다. [Azure AD에 앱 등록](walkthrough-push-data-register-app-with-azure-ad.md)을 참조하세요.
5. Microsoft.IdentityModel.Clients.ActiveDirectory 패키지를 설치한 후 **using Microsoft.IdentityModel.Clients.ActiveDirectory;** 를 Program.cs에 추가합니다.
6. 콘솔 앱을 실행하고 Power BI 계정에 로그인합니다. 토큰 문자열이 콘솔 창에 표시됩니다.

**인증 보안 토큰을 가져오는 샘플 코드**

Program {...}에 이 코드를 추가합니다.

* 작업을 호출하는 토큰 변수:
  
  ```
  private static string token = string.Empty;
  
  static void Main(string[] args)
  {
  }
  ```
* static void Main(string[] args)에서:
  
  ```
  static void Main(string[] args)
  {
    //Get an authentication access token
    token = GetToken();
  }
  ```
* GetToken() 메서드 추가:

```
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
           string authorityUri = "https://login.windows.net/common/oauth2/authorize";

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

인증 토큰을 가져온 후에는 원하는 Power BI 작업을 호출할 수 있습니다. 다음 단계에서는 [데이터 집합 만들기](https://msdn.microsoft.com/library/mt203562.aspx) 작업을 호출하여 대시보드에 데이터를 푸시할 데이터 집합을 만드는 방법을 보여 줍니다.

다음 단계에서는 [Power BI에서 데이터 집합을 만드는](walkthrough-push-data-create-dataset.md) 방법을 보여 줍니다.

다음은 [전체 코드 목록](#code)입니다.

<a name="code"/>

## <a name="complete-code-listing"></a>전체 코드 목록
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
                string authorityUri = "https://login.windows.net/common/oauth2/authorize";

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


[다음 단계 >](walkthrough-push-data-create-dataset.md)

## <a name="next-steps"></a>다음 단계
[Power BI에서 데이터 집합 만들기](walkthrough-push-data-create-dataset.md)  
[Azure AD에 앱 등록](walkthrough-push-data-register-app-with-azure-ad.md)  
[.NET NuGet 패키지용 Azure AD 인증 라이브러리](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)  
[Power BI 데이터 집합에 데이터 푸시](walkthrough-push-data.md)  
[Power BI REST API 개요](overview-of-power-bi-rest-api.md)  
[Power BI REST API 참조](https://msdn.microsoft.com/library/mt147898.aspx)  
궁금한 점이 더 있나요? [Power BI 커뮤니티를 이용하세요.](http://community.powerbi.com/)

