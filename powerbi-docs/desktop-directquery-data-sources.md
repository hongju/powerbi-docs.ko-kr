---
title: Power BI의 DirectQuery에서 지원하는 데이터 원본
description: DirectQuery를 사용할 수 있는 데이터 원본 목록을 가져옵니다.
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 11/01/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 098447f4d0c0b1dc9534c91e84827c4cefb8850c
ms.sourcegitcommit: fdb54145f9bc93b312409c15c603749f3a4a876e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "52452548"
---
# <a name="data-sources-supported-by-directquery-in-power-bi"></a>Power BI의 DirectQuery에서 지원하는 데이터 원본
**Power BI Desktop** 및 **Power BI 서비스**에는 데이터에 연결하고 액세스할 수 있는 많은 데이터 원본이 포함되어 있습니다. 이 문서에서는 **DirectQuery**라는 연결 방법을 지원하는 Power BI의 데이터 원본에 대해 설명합니다. DirectQuery에 대한 자세한 내용은 [**Power BI의 DirectQuery**](desktop-directquery-about.md)를 참조하세요.

다음 데이터 원본은 Power BI에서 DirectQuery를 지원합니다.

* Amazon Redshift
* Azure HDInsight Spark(베타)
* Azure SQL Database
* Azure SQL Data Warehouse
* Google BigQuery(베타)
* IBM DB2 데이터베이스
* IBM Netezza(베타)
* Impala(버전 2.x)
* Oracle 데이터베이스(버전 12 이상)
* SAP Business Warehouse 애플리케이션 서버
* SAP Business Warehouse 메시지 서버(베타)
* SAP HANA
* Snowflake
* Spark(베타)(버전 0.9 이상)
* SQL Server
* Teradata 데이터베이스
* Vertica(베타)

이름 뒤에 **(베타)** 또는 **(미리 보기)** 가 있는 데이터 원본의 이름은 변경될 수 있으며 프로덕션 용도로 지원되지 않습니다. 또한 **Power BI 서비스**에 보고서를 게시한 후에도 게시된 보고서를 열거나 데이터 집합을 탐색할 때 오류가 발생할 수 있으므로 지원되지 않을 수 있습니다.

**(베타)** 및 **(미리 보기)** 데이터 원본 간의 유일한 차이점은 **(미리 보기)** 원본은 사용 가능해질 때까지 미리 보기 기능으로만 사용할 수 있어야 합니다. **(미리 보기)** 데이터 커넥터를 사용하도록 설정하려면 **Power BI Desktop**에서 **파일 > 옵션 및 설정 > 옵션**으로 이동한 다음, **미리 보기 기능**을 선택합니다.

> [!NOTE]
> 현재 SQL Server에 대한 DirectQuery 쿼리는 인증에서 액세스 권한을 설정하기 위해 Windows 인증 자격 증명 또는 데이터베이스 자격 증명을 사용하도록 요구합니다. 대체 자격 증명이 지원되지 않습니다.
>

## <a name="on-premises-gateway-requirements"></a>온-프레미스 게이트웨이 요구 사항
다음 표에서는 보고서를 **Power BI 서비스**에 게시한 후 지정된 데이터 원본에 연결하는 데 **온-프레미스 데이터 게이트웨이**가 필요한지를 명시합니다.

| 소스 | 게이트웨이 필요 여부 |
| --- | --- |
| SQL Server |예 |
| Azure SQL Database |아니요 |
| Azure SQL Data Warehouse |아니요 |
| SAP HANA |예 |
| Oracle 데이터베이스 |예 |
| Teradata 데이터베이스 |예 |
| Amazon Redshift |아니요 |
| Impala(버전 2.x) |예 |
| Snowflake |예 |
| Spark(베타), 버전 0.9 이상 |예 |
| Azure HDInsight Spark(베타) |아니요 |
| IBM Netezza |예 |
| SAP Business Warehouse 애플리케이션 서버 |예 |
| SAP Business Warehouse 메시지 서버 |**Power BI 서비스**에서는 아직 지원되지 않음 |
| Google BigQuery |아니요 |


## <a name="next-steps"></a>다음 단계
DirectQuery에 대한 자세한 내용은 다음 리소스를 참조하세요.

* [Power BI의 DirectQuery](desktop-directquery-about.md)
* [DirectQuery 및 SAP HANA](desktop-directquery-sap-hana.md)
* [DirectQuery 및 SAP BW](desktop-directquery-sap-bw.md)
* [온-프레미스 데이터 게이트웨이](service-gateway-onprem.md)

