---
title: PowerShell을 사용하여 데이터 원본 연결 문자열 변경
description: PowerShell의 API를 사용하여 데이터 원본 연결 문자열 변경 - Power BI Report Server
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 10/24/2019
ms.author: maggies
ms.openlocfilehash: 5cdf29c71ef3e5f8dc02799945cf76ccc518dabe
ms.sourcegitcommit: df8bcc65f0df69bf1fc1d47eb06575742eac1622
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2020
ms.locfileid: "75953745"
---
# <a name="change-data-source-connection-strings-in-power-bi-reports-with-powershell---power-bi-report-server"></a>PowerShell을 사용하여 Power BI 보고서에서 데이터 원본 연결 문자열 변경 - Power BI Report Server


PowerShell의 API를 사용하여 Power BI Report Server의 Power BI 보고서에서 데이터 원본 연결 문자열을 변경할 수 있습니다. 

> [!NOTE]
> 현재 이 기능은 DirectQuery에서만 작동합니다. 가져오기 및 데이터 새로 고침 지원이 예정되어 있습니다.

1. Power BI Report Server PowerShell commandlet을 설치합니다. [https://github.com/Microsoft/ReportingServicesTools](https://github.com/Microsoft/ReportingServicesTools)에서 commandlet 및 설치 지침을 찾습니다. 

2. PowerShell commandlet을 통해 Power BI 파일의 기존 데이터 원본 정보를 가져옵니다.

    ```powershell
    Get-RsRestItemDataSource -RsItem '/MyPbixReport'
    ```

    Power BI 보고서에 포함된 첫 번째 데이터 원본의 정보를 보려면 다음을 수행합니다. 

    ```powershell
    $dataSources[0]
    ```

3. 필요에 따라 연결 및 자격 증명 정보를 업데이트합니다. 연결 문자열을 업데이트하고 데이터 원본이 저장된 자격 증명을 사용하는 경우, 계정 암호를 입력해야 합니다. 

    데이터 원본 연결 문자열을 업데이트하는 코드는 다음과 같습니다.

    ```powershell
    $dataSources[0].ConnectionString = 'data source=myCatalogServer;initial catalog=ReportServer;persist security info=False' 
    ```

    데이터 원본 자격 증명 유형을 변경하는 코드는 다음과 같습니다.

    ```powershell
    $dataSources[0].DataModelDataSource.AuthType = 'Integrated'
    ```

    데이터 원본 사용자 이름/암호를 변경하는 코드는 다음과 같습니다.

    ```powershell
    $dataSources[0].DataModelDataSource.Username = 'domain\user
    ```
    ```powershell
    $dataSources[0].DataModelDataSource.Secret = 'password'
    ```

4. 업데이트된 자격 증명을 서버에 다시 저장합니다.

    ```powershell
    Set-RsRestItemDataSource -RsItem '/MyPbixReport' -RsItemType 'PowerBIReport' -DataSources $dataSources
    ```

## <a name="next-steps"></a>다음 단계

[Power BI Report Server의 페이지를 매긴 보고서 데이터 원본](connect-data-sources.md) 

추가 질문이 있으신가요? [Power BI 커뮤니티에 질문합니다.](https://community.powerbi.com/)
