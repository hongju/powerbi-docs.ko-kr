---
title: 행을 추가할 데이터 세트 가져오기
description: 데이터 푸시 연습 - Power BI 테이블에 행을 추가할 데이터 세트 가져오기
author: rkarlin
ms.author: rkarlin
manager: kfile
ms.reviewer: madia
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 02/05/2019
ms.openlocfilehash: c0a70339e8336f3e7b93b40ad8a99dcb87715812
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "65710241"
---
# <a name="step-4-get-a-dataset-to-add-rows-into-a-power-bi-table"></a>4단계: Power BI 테이블에 행을 추가할 데이터 세트 가져오기

이 문서는 [데이터 세트에 데이터를 푸시](walkthrough-push-data.md)하는 단계별 연습의 일부입니다.

데이터 세트에 데이터 푸시의 **3단계**[Power BI에서 데이터 세트 만들기](walkthrough-push-data-create-dataset.md)에서는 [데이터 세트 만들기](https://docs.microsoft.com/rest/api/power-bi/datasets) 작업을 호출하여 Power BI에서 데이터 세트를 만들었습니다. 이 단계에서는 [데이터 세트 가져오기](https://docs.microsoft.com/rest/api/power-bi/datasets/getdatasets) 작업과 Newtonsoft.Json을 사용하여 데이터 세트 ID를 가져옵니다. 4단계의 데이터 세트 ID를 사용하여 데이터 세트에 행을 추가합니다. 

데이터를 Power BI 데이터 세트로 푸시하려면 데이터 세트의 테이블을 참조해야 합니다. 데이터 세트의 테이블을 참조하려면 먼저 **데이터 세트 ID**를 가져와야 합니다. **데이터 세트 ID**는 [ID별 데이터 세트 가져오기](https://docs.microsoft.com/rest/api/power-bi/datasets/getdatasetbyid) 작업을 사용하여 가져옵니다. **ID별 데이터 세트 가져오기** 작업은 Power BI에 있는 모든 데이터 세트의 목록이 포함된 JSON 문자열을 반환합니다. JSON 문자열을 역직렬화하는 데 권장되는 방법은 [Newtonsoft.Json](http://www.newtonsoft.com/json)을 사용하는 것입니다.

데이터 세트를 가져오는 방법은 다음과 같습니다.

## <a name="get-a-power-bi-dataset"></a>Power BI 데이터 세트 가져오기

> **참고**: 시작하기 전에 [데이터 세트에 데이터 푸시](walkthrough-push-data.md)의 이전 단계를 수행해야 합니다.

1. 2단계: 데이터 푸시 연습, [인증 액세스 토큰 가져오기](walkthrough-push-data-get-token.md)에서 만든 콘솔 애플리케이션 프로젝트에서 Newtonsoft.Json NuGet 패키지를 설치합니다. 패키지를 설치하는 방법은 다음과 같습니다.

     a. Visual Studio 2015에서 **도구** > **NuGet 패키지 관리자** > **패키지 관리자 콘솔**을 선택합니다.

     b. **패키지 관리자 콘솔**에서 Install-Package Newtonsoft.Json을 입력합니다.
2. 패키지가 설치되면 **using Newtonsoft.Json;** 을 Program.cs에 추가합니다.
3. Program.cs에 **데이터 세트 ID**를 가져오는 아래 코드를 추가합니다.
4. 콘솔 앱을 실행하고 Power BI 계정에 로그인합니다. 콘솔 창에 **데이터 세트 ID:** 다음에 ID가 표시됩니다.

**데이터 세트 가져오기 샘플**

Program.cs에 이 코드를 추가합니다.

* static void Main(string[] args)에서:
  
  ```csharp
  static void Main(string[] args)
  {
  
    //Get an authentication access token
    token = GetToken();
  
    //Create a dataset in Power BI
    CreateDataset();
  
    //Get a dataset to add rows into a Power BI table
    string datasetId = GetDataset();
  }
  ```
* GetDatset() 메서드 추가:
  
  ```csharp
    #region Get a dataset to add rows into a Power BI table
    private static string GetDataset()
    {
        string powerBIDatasetsApiUrl = "https://api.powerbi.com/v1.0/myorg/datasets";
        //POST web request to create a dataset.
        //To create a Dataset in a group, use the Groups uri: https://api.PowerBI.com/v1.0/myorg/groups/{group_id}/datasets
        HttpWebRequest request = System.Net.WebRequest.Create(powerBIDatasetsApiUrl) as System.Net.HttpWebRequest;
        request.KeepAlive = true;
        request.Method = "GET";
        request.ContentLength = 0;
        request.ContentType = "application/json";
  
        //Add token to the request header
        request.Headers.Add("Authorization", String.Format("Bearer {0}", token));
  
        string datasetId = string.Empty;
        //Get HttpWebResponse from GET request
        using (HttpWebResponse httpResponse = request.GetResponse() as System.Net.HttpWebResponse)
        {
            //Get StreamReader that holds the response stream
            using (StreamReader reader = new System.IO.StreamReader(httpResponse.GetResponseStream()))
            {
                string responseContent = reader.ReadToEnd();
  
                //TODO: Install NuGet Newtonsoft.Json package: Install-Package Newtonsoft.Json
                //and add using Newtonsoft.Json
                var results = JsonConvert.DeserializeObject<dynamic>(responseContent);
  
                //Get the first id
                datasetId = results["value"][0]["id"];
  
                Console.WriteLine(String.Format("Dataset ID: {0}", datasetId));
                Console.ReadLine();
  
                return datasetId;
            }
        }
    }
    #endregion
  ```

다음 단계에서는 [Power BI 테이블에 행을 추가](walkthrough-push-data-add-rows.md)하는 방법을 보여 줍니다.

다음은 [전체 코드 목록](#code)입니다.

<a name="code"/>

## <a name="complete-code-listing"></a>전체 코드 목록

```csharp
using System;
using Microsoft.IdentityModel.Clients.ActiveDirectory;
using System.Net;
using System.IO;
using Newtonsoft.Json;

namespace walkthrough_push_data
{
    class Program
    {
        private static string token = string.Empty;

        static void Main(string[] args)
        {

            //Get an authentication access token
            token = GetToken();

            //Create a dataset in Power BI
            CreateDataset();

            //Get a dataset to add rows into a Power BI table
            string datasetId = GetDataset();

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

        #region Create a dataset in Power BI
        private static void CreateDataset()
        {
            //TODO: Add using System.Net and using System.IO

            string powerBIDatasetsApiUrl = "https://api.powerbi.com/v1.0/myorg/datasets";
            //POST web request to create a dataset.
            //To create a Dataset in a group, use the Groups uri: https://api.PowerBI.com/v1.0/myorg/groups/{group_id}/datasets
            HttpWebRequest request = System.Net.WebRequest.Create(powerBIDatasetsApiUrl) as System.Net.HttpWebRequest;
            request.KeepAlive = true;
            request.Method = "POST";
            request.ContentLength = 0;
            request.ContentType = "application/json";

            //Add token to the request header
            request.Headers.Add("Authorization", String.Format("Bearer {0}", token));

            //Create dataset JSON for POST request
            string datasetJson = "{\"name\": \"SalesMarketing\", \"tables\": " +
                "[{\"name\": \"Product\", \"columns\": " +
                "[{ \"name\": \"ProductID\", \"dataType\": \"Int64\"}, " +
                "{ \"name\": \"Name\", \"dataType\": \"string\"}, " +
                "{ \"name\": \"Category\", \"dataType\": \"string\"}," +
                "{ \"name\": \"IsCompete\", \"dataType\": \"bool\"}," +
                "{ \"name\": \"ManufacturedOn\", \"dataType\": \"DateTime\"}" +
                "]}]}";

            //POST web request
            byte[] byteArray = System.Text.Encoding.UTF8.GetBytes(datasetJson);
            request.ContentLength = byteArray.Length;

            //Write JSON byte[] into a Stream
            using (Stream writer = request.GetRequestStream())
            {
                writer.Write(byteArray, 0, byteArray.Length);

                var response = (HttpWebResponse)request.GetResponse();

                Console.WriteLine(string.Format("Dataset {0}", response.StatusCode.ToString()));

                Console.ReadLine();
            }
        }
        #endregion

        #region Get a dataset to add rows into a Power BI table
        private static string GetDataset()
        {
            string powerBIDatasetsApiUrl = "https://api.powerbi.com/v1.0/myorg/datasets";
            //POST web request to create a dataset.
            //To create a Dataset in a group, use the Groups uri: https://api.PowerBI.com/v1.0/myorg/groups/{group_id}/datasets
            HttpWebRequest request = System.Net.WebRequest.Create(powerBIDatasetsApiUrl) as System.Net.HttpWebRequest;
            request.KeepAlive = true;
            request.Method = "GET";
            request.ContentLength = 0;
            request.ContentType = "application/json";

            //Add token to the request header
            request.Headers.Add("Authorization", String.Format("Bearer {0}", token));

            string datasetId = string.Empty;
            //Get HttpWebResponse from GET request
            using (HttpWebResponse httpResponse = request.GetResponse() as System.Net.HttpWebResponse)
            {
                //Get StreamReader that holds the response stream
                using (StreamReader reader = new System.IO.StreamReader(httpResponse.GetResponseStream()))
                {
                    string responseContent = reader.ReadToEnd();

                    //TODO: Install NuGet Newtonsoft.Json package: Install-Package Newtonsoft.Json
                    //and add using Newtonsoft.Json
                    var results = JsonConvert.DeserializeObject<dynamic>(responseContent);

                    //Get the first id
                    datasetId = results["value"][0]["id"];

                    Console.WriteLine(String.Format("Dataset ID: {0}", datasetId));
                    Console.ReadLine();

                    return datasetId;
                }
            }
        }
        #endregion
    }
}
```

[다음 단계 >](walkthrough-push-data-add-rows.md)

## <a name="next-steps"></a>다음 단계

[Power BI 테이블에 행 추가](walkthrough-push-data-add-rows.md)  
[Newtonsoft.Json](http://www.newtonsoft.com/json)  
[데이터 세트 가져오기](https://docs.microsoft.com/rest/api/power-bi/datasets/getdatasets)  
[Power BI로 데이터 푸시](walkthrough-push-data.md)  
[Power BI REST API 개요](overview-of-power-bi-rest-api.md)  
[Power BI REST API 참조](https://docs.microsoft.com/rest/api/power-bi/)  

궁금한 점이 더 있나요? [Power BI 커뮤니티를 이용하세요.](http://community.powerbi.com/)