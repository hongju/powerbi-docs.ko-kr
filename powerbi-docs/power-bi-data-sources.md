---
title: Power BI 데이터 원본
description: 이 문서에는 DirectQuery 및 온-프레미스 데이터 게이트웨이에 대한 정보를 포함하여 Power BI에서 지원하는 데이터 원본이 나열되어 있습니다.
author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 01/08/2020
ms.author: kfollis
ms.openlocfilehash: 2578f8621140a64b85e6765d80d860c1489a5900
ms.sourcegitcommit: 8e3d53cf971853c32eff4531d2d3cdb725a199af
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "75762557"
---
# <a name="power-bi-data-sources"></a>Power BI 데이터 원본

다음 표에서는 DirectQuery 및 온-프레미스 데이터 게이트웨이에 대한 정보를 포함하여 Power BI가 데이터 집합으로 지원하는 데이터 원본을 보여 줍니다. 데이터 흐름에 대한 자세한 내용은 [Power BI 데이터 흐름용 데이터 원본에 연결](service-dataflows-data-sources.md)을 참조하세요.

| 데이터 원본 | 데스크톱에서 연결 | 서비스에서 연결 및 새로 고침 | DirectQuery/라이브 연결 | 게이트웨이(지원됨) | 게이트웨이(필수) |

|---|---|---|---|---|---|---|---|
| Access 데이터베이스 | 예 | 예 | 아니요 | 예 <sup>1</sup> | 예 |
| ActiveDirectory | 예 | 예 | 아니요 | 예 | 예 |
| Adobe Analytics | 예 | 예 | 아니요 | 아니요 | 아니요 |
| Amazon Redshift | 예 | 예 | 예 | 예 | 아니요 |
| appFigures | 예 | 예 | 아니요 | 아니요 | 아니요 |
| AtScale 큐브 | 예 | 예 | 예 | 예 | 아니요 |
| Azure Analysis Services | 예 | 예 | 예 | 예 <sup>2</sup> | 아니요 |
| Azure Blob Storage | 예 | 예 | 아니요 | 예 | 아니요 |
| Azure Cosmos DB | 예 | 예 | 아니요 | 아니요 | 아니요 |
| Azure Cost Management | 예 | 예 | 아니요 | 아니요 | 아니요 |
| Azure Data Explorer(kusto) | 예 | 예 | 예 | 아니요 | 아니요 |
| Azure Data Lake Storage Gen1 | 예 | 예 | 아니요 | 아니요 | 아니요 |
| Azure Data Lake Storage Gen2 | 예 | 예 | 아니요 | 예 | 아니요 |
| Azure DevOps | 예 | 예 | 아니요 | 아니요 | 아니요 |
| Azure DevOps Server | 예 | 예 | 아니요 | 예 | 예 |
| Azure HDInsight(HDFS) | 예 | 예 | 아니요 | 아니요 | 아니요 |
| Azure HDInsight Spark | 예 | 예 | 예 | 아니요 | 아니요 |
| Azure SQL Database | 예 | 예 | 예 | 예 <sup>2</sup> | 아니요 |
| Azure SQL Data Warehouse | 예 | 예 | 예 | 아니요 | 아니요 |
| Azure Table Storage | 예 | 예 | 아니요 | 예 | 아니요 |
| BI 커넥터 | 예 | 예 | 예 | 예 | 예 |
| BI360 - 예산 및 재무 보고 | 예 | 예 | 아니요 | 아니요 | 아니요 |
| Common Data Service | 예 | 예 | 아니요 | 아니요 | 아니요 |
| Data.World - 데이터 세트 가져오기 | 예 | 예 | 아니요 | 아니요 | 아니요 |
| Denodo | 예 | 예 | 예 | 예 | 예 |
| Dremio | 예 | 예 | 예 | 예 | 예 |
| Dynamics 365(온라인) | 예 | 예 | 아니요 | 아니요 | 아니요 |
| Dynamics 365 Business Central | 예 | 예 | 아니요 | 아니요 | 아니요 |
| Dynamics 365 Business Central(온-프레미스) | 예 | 예 | 아니요 | 아니요 | 아니요 |
| Dynamics 365 Customer Insights | 예 | 예 | 아니요 | 아니요 | 아니요 |
| Dynamics NAV | 예 | 예 | 아니요 | 아니요 | 아니요 |
| Emigo 데이터 원본 | 예 | 예 | 아니요 | 아니요 | 아니요 |
| Entersoft Business Suite | 예 | 예 | 아니요 | 아니요 | 아니요 |
| Essbase | 예 | 예 | 예 | 예 | 예 |
| Exasol | 예 | 예 | 예 | 예 | 예 |
| Excel | 예 <sup>3</sup> | 예 <sup>3</sup> | 아니요 | 예 <sup>3</sup> | 아니요 <sup>4</sup> |
| Facebook | 예 | 예 | 아니요 | 아니요 | 아니요 |
| 파일 | 예 | 예 | 아니요 | 예 | 예 |
| 폴더 | 예 | 예 | 아니요 | 예 | 예 |
| GitHub | 예 | 예 | 아니요 | 아니요 | 아니요 |
| Google 애널리틱스 | 예 | 예 | 아니요 | 아니요 | 아니요 |
| Google BigQuery | 예 | 예 | 아니요 | 아니요 | 아니요 |
| HDFS(Hadoop 파일) | 예 | 아니요 | 아니요 | 아니요 | 아니요 |
| HDInsight 대화형 쿼리 | 예 | 예 | 예 | 아니요 | 아니요 |
| IBM DB2 | 예 | 예 | 예 | 예 | 아니요 |
| IBM Informix 데이터베이스 | 예 | 예 | 아니요 | 예 | 아니요 |
| IBM Netezza | 예 | 예 | 예 | 예 | 예 |
| Impala | 예 | 예 | 예 | 예 | 예 |
| Indexima | 예 | 예 | 예 | 예 | 예 |
| 산업 앱 스토어 | 예 | 예 | 아니요 | 아니요 | 아니요 |
| 정보 표 | 예 | 예 | 아니요 | 아니요 | 아니요 |
| Intersystems IRIS | 예 | 예 | 예 | 예 | 예 |
| Intune 데이터 웨어하우스 | 예 | 예 | 아니요 | 아니요 | 아니요 |
| Jethro ODBC | 예 | 예 | 예 | 예 | 예 |
| JSON | 예 | 예 | 아니요 | 예** | 아니요 <sup>4</sup> |
| Kyligence Enterprise | 예 | 예 | 예 | 예 | 예 |
| MailChimp | 예 | 예 | 아니요 | 아니요 | 아니요 |
| Marketo | 예 | 예 | 아니요 | 아니요 | 아니요 |
| MarkLogic ODBC | 예 | 예 | 예 | 예 | 예 |
| Microsoft Azure Consumption Insights | 예 | 예 | 아니요 | 아니요 | 아니요 |
| Microsoft Exchange | 예 | 예 | 아니요 | 예 | 아니요 |
| Microsoft Exchange Online | 예 | 예 | 아니요 | 아니요 | 아니요 |
| Microsoft Graph 보안 | 예 | 예 | 아니요 | 예 | 아니요 |
| Mixpanel | 예 | 예 | 아니요 | 아니요 | 아니요 |
| MySQL | 예 | 예 | 아니요 | 예 | 예 |
| OData | 예 | 예 | 아니요 | 예 | 아니요 |
| ODBC | 예 | 예 | 아니요 | 예 | 예 |
| OleDb | 예 | 예 | 아니요 | 예 | 예 |
| Oracle | 예 | 예 | 예 | 예 | 예 |
| Paxata | 예 | 예 | 아니요 | 예 | 아니요 |
| PDF | 예 | 예 | 아니요 | 예 | 아니요 <sup>4</sup> |
| Planview Enterprise One - CTM | 예 | 예 | 아니요 | 아니요 | 아니요 |
| Planview Enterprise One - PRM | 예 | 예 | 아니요 | 아니요 | 아니요 |
| Planview Projectplace | 예 | 예 | 아니요 | 아니요 | 아니요 |
| PostgreSQL | 예 | 예 | 예 | 예 | 아니요 |
| Power BI 데이터 흐름 | 예 | 예 | 아니요 | 아니요 | 아니요 |
| Power BI 데이터 세트 | 예 | 예 | 예 | 아니요 | 아니요 |
| Power Platform 데이터 흐름 | 예 | 예 | 아니요 | 아니요 | 아니요 |
| Python 스크립트 | 예 | 예 <sup>5</sup> | 아니요 | 예 <sup>5</sup> | 예 |
| QubolePresto | 예 | 예 | 예 | 예 | 예 |
| 빠른 자료 | 예 | 예 | 아니요 | 예 | 예 |
| QuickBooks Online | 예 | 예 | 아니요 | 아니요 | 아니요 |
| R 스크립트 | 예 | 예 <sup>5</sup> | 아니요 | 예 <sup>5</sup> | 아니요 |
| Roamler | 예 | 예 | 아니요 | 예 | 아니요 |
| Salesforce 개체 | 예 | 예 | 아니요 | 아니요 | 아니요 |
| Salesforce 보고서 | 예 | 예 | 아니요 | 아니요 | 아니요 |
| SAP Business Warehouse 메시지 서버 | 예 | 예 | 예 | 예 | 예 |
| SAP Business Warehouse 서버 | 예 | 예 | 예 | 예 | 예 |
| SAP HANA | 예 | 예 | 예 | 예 | 예 |
| SharePoint 폴더 | 예 | 예 | 아니요 | 예 | 아니요 <sup>4</sup> |
| SharePoint 목록 | 예 | 예 | 아니요 | 예 | 아니요 <sup>4</sup> |
| SharePoint Online 목록 | 예 | 예 | 아니요 | 예 <sup>2</sup> | 아니요 |
| Smartsheet | 예 | 예 | 아니요 | 아니요 | 아니요 |
| Snowflake | 예 | 예 | 예 | 예 | 아니요 |
| Spark | 예 | 예 | 예 | 예 | 아니요 |
| SparkPost | 예 | 예 | 아니요 | 아니요 | 아니요 |
| SQL Server | 예 | 예 | 예 | 예 | 예 |
| SQL Server Analysis Services | 예 | 예 | 예 | 예 | 예 |
| Stripe | 예 | 예 | 아니요 | 아니요 | 아니요 |
| SurveyMonkey | 예 | 예 | 아니요 | 예 | 아니요 |
| SweetIQ | 예 | 예 | 아니요 | 아니요 | 아니요 |
| Sybase | 예 | 예 | 아니요 | 예 | 예 |
| TeamDesk | 예 | 예 | 아니요 | 예 | 아니요 |
| Tenforce | 예 | 예 | 아니요 | 아니요 | 아니요 |
| Teradata | 예 | 예 | 예 | 예 | 예 |
| 텍스트/CSV | 예 | 예 | 아니요 | 예 | 아니요 <sup>4</sup> |
| Twilio | 예 | 예 | 아니요 | 아니요 | 아니요 |
| tyGraph | 예 | 예 | 아니요 | 아니요 | 아니요 |
| Vertica | 예 | 예 | 예 | 예 | 예 |
| 웹 | 예 | 예 | 아니요 | 예 | 예 |
| Webtrends | 예 | 예 | 아니요 | 아니요 | 아니요 |
| Workforce Dimensions | 예 | 예 | 아니요 | 예 | 아니요 |
| XML | 예 | 예 | 아니요 | 예 | 아니요 <sup>4</sup> |
| Zendesk | 예 | 예 | 아니요 | 아니요 | 아니요 |
| | | | | | | | |

<sup>1</sup> 게이트웨이와 동일한 머신에 설치된 [ACE OLEDB 공급자](https://www.microsoft.com/download/details.aspx?id=54920)에서 지원됩니다.

<sup>2</sup> 온-프레미스 버전과 동일한 M 함수에서 지원됩니다.

<sup>3</sup> Excel 1997~2003 파일(.xls)에 [ACE OLEDB 공급자](https://www.microsoft.com/download/details.aspx?id=54920)가 필요합니다.

<sup>4</sup> 온-프레미스 버전의 기술에 필요합니다.

<sup>5</sup>[개인 게이트웨이](service-gateway-personal-mode.md)에서만 지원됩니다.

## <a name="single-sign-on-sso-for-directquery-sources"></a>DirectQuery 원본의 SSO(Single Sign-On)

SSO 옵션이 활성화되어 있고 사용자가 데이터 원본을 기반으로 작성된 보고서에 액세스하면 Power BI는 쿼리에 인증된 Azure AD 자격 증명을 기본 데이터 원본으로 보냅니다. 그러면 Power BI가 데이터 원본 수준에서 구성된 보안 설정을 준수할 수 있습니다.
SSO 옵션은 이 데이터 원본을 사용하는 모든 데이터 세트에 적용됩니다. 가져오기 시나리오에 사용되는 인증 방법에는 영향을 주지 않습니다. 다음 데이터 원본은 DirectQuery를 통한 연결에 대해 SSO를 지원합니다.

- Azure SQL Database
- Azure SQL Data Warehouse
- Impala
- SAP HANA
- SAP BW
- SAP BW 메시지 서버
- Spark
- SQL Server
- Teradata

> [!Note]
> Azure MFA(Multi-Factor Authentication)는 지원되지 않습니다. DirectQuery와 함께 SSO를 사용하려는 사용자는 MFA에서 제외해야 합니다.

## <a name="next-steps"></a>다음 단계

[Power BI Desktop에서 데이터에 연결](desktop-quickstart-connect-to-data.md)  
[Power BI의 DirectQuery 사용](desktop-directquery-about.md)  
[Power BI의 SQL Server Analysis Services 라이브 데이터](sql-server-analysis-services-tabular-data.md)  
[온-프레미스 데이터 게이트웨이란?](service-gateway-onprem.md)  
