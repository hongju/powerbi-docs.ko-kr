---
title: Power BI에 대한 자격 증명을 프로그래밍 방식으로 구성
description: 자동화를 위해 Power BI에 대한 자격 증명을 프로그래밍 방식으로 구성하는 방법
author: rkarlin
ms.author: rkarlin
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 02/25/2019
ms.openlocfilehash: f93119a621330d673fd2cf6035e0416646bd5e6a
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "61380184"
---
# <a name="configure-credentials-programmatically-for-power-bi"></a>Power BI에 대한 자격 증명을 프로그래밍 방식으로 구성

Power BI에 대한 자격 증명을 프로그래밍 방식으로 구성하려면 다음 단계를 따릅니다.

## <a name="configure-a-credential-flow-for-data-sources"></a>데이터 원본에 대한 자격 증명 흐름 구성

1. [데이터 원본 가져오기](https://docs.microsoft.com/rest/api/power-bi/datasets/getdatasourcesingroup)를 호출하여 데이터 세트의 데이터 원본을 검색합니다. 각 데이터 원본의 응답 본문에는 형식, 연결 세부 정보, 게이트웨이 및 데이터 원본 ID가 있습니다.

    ```csharp
    var datasources = pbiClient.Datasets.GetDatasources(datasetId).Value;
    var datasource = datasources.First(); // select a datasource
    ```

2. 자격 증명 형식과 [데이터 원본 업데이트 예제](https://docs.microsoft.com/rest/api/power-bi/gateways/updatedatasource)에 따라 자격 증명 문자열을 빌드합니다.

    ```csharp
    var credentials = "{\"credentialData\":[{\"name\":\"username\", \"value\":\"john\"},{\"name\":\"password\", \"value\":\"*****\"}]}";
    ```

3. 자격 증명 세부 정보를 빌드합니다.

    ```csharp
    var credentialDetails = new CredentialDetails(
                    credentials,
                    CredentialTypeEnum.Basic,
                    EncryptedConnectionEnum.Encrypted,
                    EncryptionAlgorithmEnum.None,
                    PrivacyLevelEnum.Private);
    ```

4. 1단계의 게이트웨이와 데이터 원본 ID를 사용하고 4단계의 자격 증명 세부 정보를 사용하여 자격 증명을 설정하려면 [데이터 원본 업데이트](https://docs.microsoft.com/rest/api/power-bi/gateways/updatedatasource)를 호출합니다.

    ```csharp
    pbiClient.Gateways.UpdateDatasource(gatewayId, datasourceId, credentialDetails);
    ```

### <a name="expired-on-premises-data-source-credentials-flow"></a>만료된 온-프레미스 데이터 원본 자격 증명 흐름

1. [이전 시나리오에서 1단계와 2단계를 수행합니다](#configure-a-credential-flow-for-data-sources).

2. [게이트웨이 가져오기](https://docs.microsoft.com/rest/api/power-bi/gateways/getgateways)를 호출하여 게이트웨이 공용 키를 검색합니다.

    ```csharp
    var gateway = pbiClient.Gateways.GetGatewayById(datasource.GatewayId);
    ```

3. RSA 암호화 알고리즘을 사용하여 게이트웨이 공용 키로 자격 증명 문자열을 암호화합니다.

    암호화를 위해 다음 도우미 클래스를 사용합니다.

    ```csharp
        public static class AsymmetricKeyEncryptionHelper
        {
            private const int SegmentLength = 85;
            private const int EncryptedLength = 128;

            /// <summary>

            /// Encrypts credentials using the RSA algorithm

            /// </summary>

            public static string EncodeCredentials(string credentialData, string publicKeyExponent, string publicKeyModulus)
            {
                using (RSACryptoServiceProvider rsa = new RSACryptoServiceProvider(EncryptedLength * 8))
                {
                    var parameters = rsa.ExportParameters(false);

                    parameters.Exponent = Convert.FromBase64String(publicKeyExponent);

                    parameters.Modulus = Convert.FromBase64String(publicKeyModulus);

                    rsa.ImportParameters(parameters);

                    return Encrypt(credentialData, rsa);
                }
            }

             private static string Encrypt(string plainText, RSACryptoServiceProvider rsa)
            {

                byte[] plainTextArray = Encoding.UTF8.GetBytes(plainText);

                // Split the message into different segments, each segment's length is 85. So, the result may be 85,85,85,20. 

                bool hasIncompleteSegment = plainTextArray.Length % SegmentLength != 0; 

                int segmentNumber = (!hasIncompleteSegment) ? (plainTextArray.Length / SegmentLength) : ((plainTextArray.Length SegmentLength) + 1);

                byte[] encryptedData = new byte[segmentNumber * EncryptedLength];

                int encryptedDataPosition = 0;

                for (var i = 0; i < segmentNumber; i++)
                {
                    int lengthToCopy;

                    if (i == segmentNumber - 1 && hasIncompleteSegment)

                        lengthToCopy = plainTextArray.Length % SegmentLength;

                    else

                        lengthToCopy = SegmentLength;

                    var segment = new byte[lengthToCopy];

                    Array.Copy(plainTextArray, i * SegmentLength, segment, 0, lengthToCopy);

                    var segmentEncryptedResult = rsa.Encrypt(segment, true);

                    Array.Copy(segmentEncryptedResult, 0, encryptedData, encryptedDataPosition, segmentEncryptedResult.Length);

                    encryptedDataPosition += segmentEncryptedResult.Length;

                }

                return Convert.ToBase64String(encryptedData);

            }

        }

        var encryptedCredentials = AsymmetricKeyEncryptionHelper.EncodeCredentials(credentials);
    ```

4. 암호화된 자격 증명을 사용하여 자격 증명 세부 정보를 빌드합니다.

    ```csharp
    var credentialDetails = new CredentialDetails(
                    encryptedCredentials,
                    CredentialTypeEnum.Basic,
                    EncryptedConnectionEnum.Encrypted,
                    EncryptionAlgorithmEnum.RSA-OAEP,
                    PrivacyLevelEnum.Private);
    ```

5. [데이터 원본 업데이트](https://docs.microsoft.com/rest/api/power-bi/gateways/updatedatasource)를 호출하여 자격 증명을 설정합니다.

    ```csharp
    pbiClient.Gateways.UpdateDatasource(gatewayId, datasourceId, credentialDetails);
    ```

## <a name="configure-a-new-data-source-for-a-data-gateway"></a>데이터 게이트웨이에 대한 새 데이터 원본 구성

1. 머신에 [온-프레미스 데이터 게이트웨이](https://powerbi.microsoft.com/gateway/)를 설치합니다.

2. [게이트웨이 가져오기](https://docs.microsoft.com/rest/api/power-bi/gateways/getgateways)를 호출하여 게이트웨이 ID 및 공용 키를 검색합니다.

    ```csharp
    var gateways = pbiClient.Gateways.GetGateways().Value;
    var gateway = gateways.First(); // select a gateway
    ```

3. [만료된 온-프레미스 데이터 원본 자격 증명 흐름](#expired-on-premises-data source-credentials-flow-on-premises-data-gateway) 단계에서 검색된 게이트웨이 공용 키를 사용하여 이전 시나리오와 같은 자격 증명 세부 정보를 빌드합니다.

4. 요청 본문 빌드

    ```csharp
    var request = new PublishDatasourceToGatewayRequest(
    dataSourceType: "SQL",
    connectionDetails: "{\"server\":\"myServer\",\"database\":\"myDatabase\"}",
    credentialDetails: credentialDetails,
    dataSourceName: "my sql datasource");
    ```

5. [데이터 원본 만들기](https://docs.microsoft.com/rest/api/power-bi/gateways/createdatasource) API를 호출합니다.

    ```csharp
    pbiClient.Gateways.CreateDatasource(gateway.Id, request);
    ```

## <a name="troubleshooting"></a>문제 해결

### <a name="no-gateway-and-data-source-id-found-when-calling-get-data-sources"></a>데이터 원본 가져오기를 호출할 때 게이트웨이 및 데이터 원본 ID를 찾을 수 없음

이 문제는 데이터 세트가 게이트웨이에 바인딩되지 않았음을 의미합니다. 새 데이터 세트를 만들 때 각 클라우드 연결에 대해 자격 증명이 없는 데이터 원본이 사용자의 클라우드 게이트웨이에 자동으로 생성됩니다. 이 게이트웨이는 클라우드 연결에 대한 자격 증명을 저장하는 데 사용됩니다.

데이터 세트를 만든 후에는 데이터 세트와 적절한 게이트웨이 간에 자동 바인딩이 수행됩니다. 이 게이트웨이에는 모든 연결에 대해 일치하는 데이터 원본이 포함되어 있습니다. 이러한 게이트웨이나 여러 개의 적합한 게이트웨이가 없으면 자동 바인딩이 실패합니다.

누락된 온-프레미스 데이터 원본이 있는 경우 이를 생성하고 [Bind To Gateway](https://docs.microsoft.com/rest/api/power-bi/datasets/bindtogateway)를 사용하여 데이터 세트를 수동으로 게이트웨이에 바인딩합니다.

바인딩될 수 있는 게이트웨이를 검색하려면 [게이트웨이 검색](https://docs.microsoft.com/rest/api/power-bi/datasets/discovergateways)을 사용합니다.
