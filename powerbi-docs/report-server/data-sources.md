---
title: Power BI Report Server에서 Power BI 보고서 데이터 원본
description: Power BI 보고서는 여러 데이터 원본에 연결할 수 있습니다. 데이터 사용 방법에 따라 다른 데이터 원본을 사용할 수 있습니다.
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 01/21/2020
ms.author: maggies
ms.openlocfilehash: 343c7d7e81d8e8ec53383feab6dc4dcfb17129d6
ms.sourcegitcommit: 02342150eeab52b13a37b7725900eaf84de912bc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2020
ms.locfileid: "76540593"
---
# <a name="power-bi-report-data-sources-in-power-bi-report-server"></a>Power BI Report Server에서 Power BI 보고서 데이터 원본
Power BI 보고서는 여러 데이터 원본에 연결할 수 있습니다. 데이터 사용 방법에 따라 다른 데이터 원본을 사용할 수 있습니다. DirectQuery 또는 SQL Server Analysis Services에 대한 라이브 연결을 사용하여 데이터를 가져오거나 데이터를 직접 쿼리할 수 있습니다.

이러한 데이터 원본은 Power BI Report Server 내에서 사용되는 Power BI 보고서에 적용됩니다. 페이지가 매겨진 보고서(.rdl)로 지원되는 데이터 원본에 대한 자세한 내용은 [Reporting Services에서 지원되는 데이터 원본](https://docs.microsoft.com/sql/reporting-services/report-data/data-sources-supported-by-reporting-services-ssrs)을 참조하세요.

> [!IMPORTANT]
> Power BI Desktop 보고서의 모든 데이터 원본은 예약된 새로 고침 구성을 지원해야 합니다.
>  

## <a name="list-of-supported-data-sources"></a>지원되는 데이터 원본 목록

다른 데이터 원본은 지원되는 목록에 없더라도 작동할 수 있습니다.

| **데이터 원본** | **캐시된 데이터** | **예약된 새로 고침** | **라이브/DirectQuery** |
| --- | --- | --- | --- |
| SQL Server 데이터베이스 |예 |예 |예 |
| SQL Server Analysis Services |예 |예 |예 |
| Azure SQL Database |예 |예 |예 |
| Azure SQL Data Warehouse |예 |예 |예 |
| Excel |예 |예 |아니요 |
| Access 데이터베이스 |예 |예 |아니요 |
| Active Directory |예 |예 |아니요 |
| Amazon Redshift |예 |아니요 |아니요 |
| Azure Blob Storage |예 |예 |아니요 |
| Azure Data Lake Store |예 |아니요 |아니요 |
| Azure HDInsight(HDFS) |예 |아니요 |아니요 |
| Azure HDInsight(Spark) |예 |예 |아니요 |
| Azure Table Storage |예 |예 |아니요 |
| Dynamics 365(온라인) |예 |아니요 |아니요 |
| Facebook |예 |아니요 |아니요 |
| 폴더 |예 |예 |아니요 |
| Google 애널리틱스 |예 |아니요 |아니요 |
| HDFS(Hadoop 파일) |예 |아니요 |아니요 |
| IBM DB2 데이터베이스 |예 |예 |아니요 |
| Impala |예 |아니요 |아니요 |
| JSON |예 |예 |아니요 |
| Microsoft Exchange |예 |아니요 |아니요 |
| Microsoft Exchange Online |예 |아니요 |아니요 |
| MySQL 데이터베이스 |예 |예 |아니요 |
| OData 피드 |예 |예 |아니요 |
| ODBC |예 |예 |아니요 |
| OLE DB |예 |예 |아니요 |
| Oracle 데이터베이스 |예 |예 |예 |
| PostgreSQL 데이터베이스 |예 |예 |아니요 |
| Power BI 서비스 |아니요 |아니요 |아니요 |
| R 스크립트 |예 |아니요 |아니요 |
| Salesforce 개체 |예 |아니요 |아니요 |
| Salesforce 보고서 |예 |아니요 |아니요 |
| SAP Business Warehouse 서버 |예 |예 |예 |
| SAP HANA 데이터베이스 |예 |예 |예 |
| SharePoint 폴더(온-프레미스) |예 |예 |아니요 |
| SharePoint 목록(온-프레미스) |예 |예 |아니요 |
| SharePoint Online 목록 |예 |아니요 |아니요 |
| Snowflake |예 |아니요 |아니요 |
| Sybase 데이터베이스 |예 |예 |아니요 |
| Teradata |예 |예 |예 |
| 텍스트/CSV |예 |예 |아니요 |
| 웹 |예 |예 |아니요 |
| XML |예 |예 |아니요 |
| appFigures(베타) |예 |아니요 |아니요 |
| Azure Analysis Services 데이터베이스 |예 |아니요 |예 |
| Azure Cosmos DB(베타) |예 |아니요 |아니요 |
| Azure HDInsight Spark(베타) |예 |아니요 |아니요 |
| Common Data Service(베타) |예 |아니요 |아니요 |
| comScore Digital Analytix(베타) |예 |아니요 |아니요 |
| Dynamics 365 for Customer Insights(베타) |예 |아니요 |아니요 |
| Dynamics 365 Financial(베타) |예 |아니요 |아니요 |
| GitHub(베타) |예 |아니요 |아니요 |
| Google BigQuery(베타) |예 |아니요 |아니요 |
| IBM Informix 데이터베이스(베타) |예 |아니요 |아니요 |
| IBM Netezza(베타) |예 |아니요 |아니요 |
| Kusto(베타) |예 |아니요 |아니요 |
| MailChimp(베타) |예 |아니요 |아니요 |
| Microsoft Azure Consumption Insights(베타) |예 |아니요 |아니요 |
| Mixpanel(베타) |예 |아니요 |아니요 |
| Planview Enterprise(베타) |예 |아니요 |아니요 |
| Projectplace(베타) |예 |아니요 |아니요 |
| QuickBooks Online(베타) |예 |아니요 |아니요 |
| Smartsheet |예 |아니요 |아니요 |
| Spark(베타) |예 |아니요 |아니요 |
| SparkPost(베타) |예 |아니요 |아니요 |
| SQL Sentry(베타) |예 |아니요 |아니요 |
| Stripe(베타) |예 |아니요 |아니요 |
| SweetIQ(베타) |예 |아니요 |아니요 |
| Troux(베타) |예 |아니요 |아니요 |
| Twilio(베타) |예 |아니요 |아니요 |
| tyGraph(베타) |예 |아니요 |아니요 |
| Vertica(베타) |예 |아니요 |아니요 |
| Visual Studio Team Services(베타) |예 |아니요 |아니요 |
| Webtrends(베타) |예 |아니요 |아니요 |
| Zendesk(베타) |예 |아니요 |아니요 |

> [!IMPORTANT]
> 데이터 원본에서 구성된 행 수준 보안은 특정 DirectQuery(SQL Server, Azure SQL Database, Oracle 및 Teradata)에 대해 작동되어야 하며 Kerberos를 가정하는 라이브 연결은 환경에서 적절히 구성됩니다.
> 
> 

## <a name="list-of-supported-authentication-methods-for-model-refresh"></a>모델 새로 고침을 위해 지원되는 인증 방법 목록

Power BI Report Server는 모델 새로 고침을 위한 OAuth 기반 인증을 지원하지 않습니다. Excel 또는 Access 데이터베이스와 같은 일부 데이터 원본은 파일 또는 웹과 같은 별도의 단계를 거쳐 데이터에 연결합니다.

| **데이터 원본** | **익명 인증** | **키 인증** | **사용자 이름 및 암호** | **Windows 인증** |
| --- | --- | --- | --- | --- |
| SQL Server 데이터베이스 |아니요 |아니요 |예 |예 |
| SQL Server Analysis Services |아니요 |아니요 |예 |예 |
| 웹 |예 |아니요 |예 |예 |
| Azure SQL Database |아니요 |아니요 |예 |아니요 |
| Azure SQL Data Warehouse |아니요 |아니요 |예 |아니요 |
| Active Directory |아니요 |아니요 |예 |예 |
| Amazon Redshift |아니요 |아니요 |아니요 |아니요 |
| Azure Blob Storage |예 |예 |아니요 |아니요 |
| Azure Data Lake Store |아니요 |아니요 |아니요 |아니요 |
| Azure HDInsight(HDFS) |아니요 |아니요 |아니요 |아니요 |
| Azure HDInsight(Spark) |예 |예 |아니요 |아니요 |
| Azure Table Storage |아니요 |예 |아니요 |아니요 |
| Dynamics 365(온라인) |아니요 |아니요 |아니요 |아니요 |
| Facebook |아니요 |아니요 |아니요 |아니요 |
| 폴더 |아니요 |아니요 |아니요 |예 |
| Google 애널리틱스 |아니요 |아니요 |아니요 |아니요 |
| HDFS(Hadoop 파일) |아니요 |아니요 |아니요 |아니요 |
| IBM DB2 데이터베이스 |아니요 |아니요 |예 |예 |
| Impala |아니요 |아니요 |아니요 |아니요 |
| Microsoft Exchange |아니요 |아니요 |아니요 |아니요 |
| Microsoft Exchange Online |아니요 |아니요 |아니요 |아니요 |
| MySQL 데이터베이스 |아니요 |아니요 |예 |예 |
| OData 피드 |예 |예 |예 |예 |
| ODBC |예 |아니요 |예 |예 |
| OLE DB |예 |아니요 |예 |예 |
| Oracle 데이터베이스 |아니요 |아니요 |예 |예 |
| PostgreSQL 데이터베이스 |아니요 |아니요 |예 |아니요 |
| Power BI 서비스 |아니요 |아니요 |아니요 |아니요 |
| R 스크립트 |아니요 |아니요 |아니요 |아니요 |
| Salesforce 개체 |아니요 |아니요 |아니요 |아니요 |
| Salesforce 보고서 |아니요 |아니요 |아니요 |아니요 |
| SAP Business Warehouse 서버 |아니요 |아니요 |예 |아니요 |
| SAP HANA 데이터베이스 |아니요 |아니요 |예 |예 |
| SharePoint 폴더(온-프레미스) |예 |아니요 |아니요 |예 |
| SharePoint 목록(온-프레미스) |예 |아니요 |아니요 |예 |
| SharePoint Online 목록 |아니요 |아니요 |아니요 |아니요 |
| Snowflake |아니요 |아니요 |아니요 |아니요 |
| Sybase 데이터베이스 |아니요 |아니요 |예 |예 |
| Teradata |아니요 |아니요 |예 |예 |
| appFigures(베타) |아니요 |아니요 |아니요 |아니요 |
| Azure Analysis Services 데이터베이스(베타) |아니요 |아니요 |아니요 |아니요 |
| Azure Cosmos DB(베타) |아니요 |아니요 |아니요 |아니요 |
| Azure HDInsight Spark(베타) |아니요 |아니요 |아니요 |아니요 |
| Common Data Service(베타) |아니요 |아니요 |아니요 |아니요 |
| comScore Digital Analytix(베타) |아니요 |아니요 |아니요 |아니요 |
| Dynamics 365 for Customer Insights(베타) |아니요 |아니요 |아니요 |아니요 |
| Dynamics 365 Financial(베타) |아니요 |아니요 |아니요 |아니요 |
| GitHub(베타) |아니요 |아니요 |아니요 |아니요 |
| Google BigQuery(베타) |아니요 |아니요 |아니요 |아니요 |
| IBM Informix 데이터베이스(베타) |아니요 |아니요 |아니요 |아니요 |
| IBM Netezza(베타) |아니요 |아니요 |아니요 |아니요 |
| Kusto(베타) |아니요 |아니요 |아니요 |아니요 |
| MailChimp(베타) |아니요 |아니요 |아니요 |아니요 |
| Microsoft Azure Consumption Insights(베타) |아니요 |아니요 |아니요 |아니요 |
| Mixpanel(베타) |아니요 |아니요 |아니요 |아니요 |
| Planview Enterprise(베타) |아니요 |아니요 |아니요 |아니요 |
| Projectplace(베타) |아니요 |아니요 |아니요 |아니요 |
| QuickBooks Online(베타) |아니요 |아니요 |아니요 |아니요 |
| Smartsheet |아니요 |아니요 |아니요 |아니요 |
| Spark(베타) |아니요 |아니요 |아니요 |아니요 |
| SparkPost(베타) |아니요 |아니요 |아니요 |아니요 |
| SQL Sentry(베타) |아니요 |아니요 |아니요 |아니요 |
| Stripe(베타) |아니요 |아니요 |아니요 |아니요 |
| SweetIQ(베타) |아니요 |아니요 |아니요 |아니요 |
| Troux(베타) |아니요 |아니요 |아니요 |아니요 |
| Twilio(베타) |아니요 |아니요 |아니요 |아니요 |
| tyGraph(베타) |아니요 |아니요 |아니요 |아니요 |
| Vertica(베타) |아니요 |아니요 |아니요 |아니요 |
| Visual Studio Team Services(베타) |아니요 |아니요 |아니요 |아니요 |
| Webtrends(베타) |아니요 |아니요 |아니요 |아니요 |
| Zendesk(베타) |아니요 |아니요 |아니요 |아니요 |

## <a name="list-of-supported-authentication-methods-for-directquery"></a>DirectQuery를 위해 지원되는 인증 방법 목록

Power BI Report Server는 DirectQuery를 위한 OAuth 기반 인증을 지원하지 않습니다.

| **데이터 원본** | **익명 인증** | **키 인증** | **사용자 이름 및 암호** | **Windows 인증** | **통합 Windows 인증** |
| --- | --- | --- | --- | --- | --- |
| SQL Server 데이터베이스 |아니요 |아니요 |예 |예 |예 |
| SQL Server Analysis Services |아니요 |아니요 |예 |예 |예 |
| Azure SQL Database |아니요 |아니요 |예 |아니요 |아니요 |
| Azure SQL Data Warehouse |아니요 |아니요 |예 |아니요 |아니요 |
| Oracle 데이터베이스 |아니요 |아니요 |예 |예 |예 |
| SAP Business Warehouse 서버 |아니요 |아니요 |예 |아니요 |아니요 |
| SAP HANA 데이터베이스 |아니요 |아니요 |예 |예 |예** |
| Teradata |아니요 |아니요 |예 |예 |예 |

**SAP HANA는 게시된 Power BI Desktop 파일(.pbix)에서 관계형 데이터베이스로 사용하는 경우에만 Windows 통합 인증을 사용하여 DirectQuery를 지원합니다.

## <a name="next-steps"></a>다음 단계
데이터 원본에 연결했으므로 데이터 원본의 데이터를 사용하여 [Power BI 보고서를 만듭니다](quickstart-create-powerbi-report.md).

궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](https://community.powerbi.com/)
