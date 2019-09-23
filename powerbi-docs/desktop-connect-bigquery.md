---
title: Power BI Desktop에서 Google BigQuery 데이터베이스에 연결
description: Power BI Desktop에서 쉽게 Google BigQuery에 연결 및 사용
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: e47dd26c6a8433777f0c4d3ef15cce41225cf03a
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "65514662"
---
# <a name="connect-to-a-google-bigquery-database-in-power-bi-desktop"></a>Power BI Desktop에서 Google BigQuery 데이터베이스에 연결
Power BI Desktop에서 Google **BigQuery** 데이터베이스에 연결하고 Power BI Desktop의 다른 데이터 원본처럼 기본 데이터를 사용할 수 있습니다.

## <a name="connect-to-google-bigquery"></a>Google BigQuery에 연결
Google **BigQuery** 데이터베이스에 연결하려면 Power BI Desktop의 **홈** 리본에서 **데이터 가져오기**를 선택합니다. 왼쪽에 있는 범주에서 **데이터베이스**를 선택하면 **Google BigQuery**가 표시됩니다.

![Google BigQuery에 대한 데이터 가져오기 대화 상자](media/desktop-connect-bigquery/connect_bigquery_01.png)

표시되는 **Google BigQuery** 창에서 Google BigQuery 계정에 로그인하고 **연결**을 선택합니다.

![Google BigQuery에 로그인](media/desktop-connect-bigquery/connect_bigquery_02.png)

로그인하면 인증되었음을 나타내는 다음 창이 표시됩니다. 

![Google에 로그인됨](media/desktop-connect-bigquery/connect_bigquery_02b.png)

성공적으로 연결되면 **탐색기** 창이 나타나고 서버에 사용 가능한 데이터를 표시합니다. 여기서 하나 이상의 요소를 선택하여 **Power BI Desktop**에 가져오고 사용할 수 있습니다.

![Google BigQuery의 데이터](media/desktop-connect-bigquery/connect_bigquery_03.png)

## <a name="considerations-and-limitations"></a>고려 사항 및 제한 사항
Google **BigQuery** 커넥터에서 유의해야 하는 몇 가지 제한 및 고려 사항이 있습니다.

* Google BigQuery 커넥터는 Power BI Desktop 및 Power BI 서비스에서 사용할 수 있습니다. Power BI 서비스에서는 Power BI에서 Google BigQuery로의 클라우드 간 연결을 사용하여 커넥터에 액세스할 수 있습니다.

Google BigQuery **청구 프로젝트**에 Power BI를 사용할 수 있습니다. 기본적으로 Power BI는 사용자에 대해 반환된 목록의 첫 번째 프로젝트를 사용합니다. Power BI에서 사용할 때 청구 프로젝트의 동작을 사용자 지정하려면 다음 단계를 수행합니다.

 * 원본 단계의 기본 M에서 다음 옵션을 지정합니다. Power BI Desktop의 **파워 쿼리 편집기**를 통해 사용자 지정할 수 있습니다.

    ```Source = GoogleBigQuery.Database([BillingProject="Include-Billing-Project-Id-Here"])```

## <a name="next-steps"></a>다음 단계
Power BI Desktop을 사용하여 연결할 수 있는 모든 종류의 데이터가 있습니다. 데이터 원본에 대한 자세한 내용은 다음 리소스를 확인하세요.

* [Power BI Desktop이란?](desktop-what-is-desktop.md)
* [Power BI Desktop의 데이터 원본](desktop-data-sources.md)
* [Power BI Desktop에서 데이터 셰이핑 및 결합](desktop-shape-and-combine-data.md)
* [Power BI Desktop에서 Excel 통합 문서에 연결](desktop-connect-excel.md)   
* [Power BI Desktop에 데이터 직접 연결](desktop-enter-data-directly-into-desktop.md)   

