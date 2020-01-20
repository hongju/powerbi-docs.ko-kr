---
title: Power BI에 대한 자격 증명을 프로그래밍 방식으로 구성
description: 자동화를 위해 Power BI에 대한 자격 증명을 프로그래밍 방식으로 구성하는 방법
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 01/08/2020
ms.openlocfilehash: 222edd901409fa71d98308f27407838d54564834
ms.sourcegitcommit: 4b926ab5f09592680627dca1f0ba016b07a86ec0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2020
ms.locfileid: "75836585"
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

3. 게이트웨이 공개 키로 자격 증명 문자열을 암호화합니다. 게이트웨이 버전에 따라 공개 키 크기가 서로 다를 수 있습니다.
    
    PowerBI-CSharp GitHub 리포지토리([PowerBI-CSharp/sdk/PowerBI.Api/Extensions/V2/](https://github.com/microsoft/PowerBI-CSharp/tree/master/sdk/PowerBI.Api/Extensions/V2))에 있는 SDK 코드의 예제를 참조하세요.
    * [AsymmetricKeyEncryptor.cs](https://github.com/microsoft/PowerBI-CSharp/blob/master/sdk/PowerBI.Api/Extensions/V2/AsymmetricKeyEncryptor.cs)
    * [Asymmetric1024KeyEncryptionHelper.cs](https://github.com/microsoft/PowerBI-CSharp/blob/master/sdk/PowerBI.Api/Extensions/V2/Asymmetric1024KeyEncryptionHelper.cs)
    * [AsymmetricHigherKeyEncryptionHelper.cs](https://github.com/microsoft/PowerBI-CSharp/blob/master/sdk/PowerBI.Api/Extensions/V2/AsymmetricHigherKeyEncryptionHelper.cs)
    * [AuthenticatedEncryption.cs](https://github.com/microsoft/PowerBI-CSharp/blob/master/sdk/PowerBI.Api/Extensions/V2/AuthenticatedEncryption.cs)

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