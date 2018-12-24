---
title: Power BI Desktop의 데이터 소스
description: Power BI Desktop의 데이터 소스
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 11/13/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: a49b433af32e6c0f03d43333a424864c5463ddd3
ms.sourcegitcommit: 6a6f552810a596e1000a02c8d144731ede59c0c8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/14/2018
ms.locfileid: "51619819"
---
# <a name="data-sources-in-power-bi-desktop"></a>Power BI Desktop의 데이터 소스
Power BI Desktop을 사용하면 다양한 원본의 데이터에 연결할 수 있습니다. 이 페이지의 맨 아래에는 사용 가능한 데이터 소스의 전체 목록이 있습니다.

데이터에 연결하려면 **홈** 리본 메뉴에서 **데이터 가져오기** 를 선택합니다. 아래쪽 화살표 또는 단추의 **데이터 가져오기** 텍스트를 선택하면 다음 이미지의 **가장 일반적** 데이터 형식 메뉴가 표시됩니다.

![Power BI Desktop에서 데이터 가져오기](media/desktop-data-sources/data-sources_01.png)

**자세히…** 선택 **가장 일반적** 메뉴에서 자세히...를 선택하면**데이터 가져오기** 창이 표시됩니다. **데이터 가져오기** **아이콘 단추**를 직접 선택하여 **데이터 가져오기** 창을 표시할 수도 있습니다(**가장 일반적** 메뉴 무시).

![데이터 단추 가져오기](media/desktop-data-sources/data-sources_02.png)

> [!NOTE]
> Power BI 팀은 **Power BI Desktop** 및 **Power BI 서비스**에 사용할 수 있는 데이터 원본을 지속적으로 확장합니다. 따라서 *베타* 또는 *미리 보기*로 표시된 작업 진행 데이터 원본의 초기 버전을 자주 볼 수 있습니다. *베타* 또는 *미리 보기*로 표시된 모든 데이터 원본은 제한된 지원 및 기능을 가지며 프로덕션 환경에서는 사용할 수 없습니다.

## <a name="data-sources"></a>데이터 소스
데이터 형식은 다음 범주로 구성됩니다.

* 모두
* 파일
* 데이터베이스
* Power BI
* Azure
* 온라인 서비스
* 기타

**모두** 범주에는 모든 범주의 모든 데이터 연결 형식이 포함됩니다.

**파일** 범주는 다음과 같은 데이터 연결을 제공합니다.

* Excel
* 텍스트/CSV
* XML
* JSON
* 폴더
* PDF(베타)
* SharePoint 폴더

다음 그림은 **파일** 에 대한 **데이터 가져오기**창을 보여 줍니다.

![데이터 가져오기 > 파일](media/desktop-data-sources/data-sources_03.png)

**데이터베이스** 범주는 다음과 같은 데이터 연결을 제공합니다.

* SQL Server 데이터베이스
* Access 데이터베이스
* SQL Server Analysis Services 데이터베이스
* Oracle 데이터베이스
* IBM DB2 데이터베이스
* IBM Informix 데이터베이스(베타)
* IBM Netezza
* MySQL 데이터베이스
* PostgreSQL 데이터베이스
* Sybase 데이터베이스
* Teradata 데이터베이스
* SAP HANA 데이터베이스
* SAP Business Warehouse 응용 프로그램 서버
* SAP Business Warehouse 메시지 서버
* Amazon Redshift
* Impala
* Google BigQuery
* Snowflake
* BI 커넥터
* Exasol
* Dremio(베타)
* Jethro(베타)
* Kyligence 엔터프라이즈(베타)

> [!NOTE]
> 일부 데이터베이스 커넥터는 **파일 > 옵션 및 설정 > 옵션**을 선택한 다음 **미리 보기 기능**을 선택하고 커넥터를 사용하도록 설정하여 사용해야 합니다. 위에서 언급한 커넥터 중 일부를 표시하지 않고 사용하지 않으려는 경우 **미리 보기 기능** 설정을 확인합니다. *베타* 또는 *미리 보기*로 표시된 모든 데이터 원본은 제한된 지원 및 기능을 가지며 프로덕션 환경에서는 사용할 수 없습니다.

다음 그림은 **데이터베이스** 에 대한 **데이터 가져오기**창을 보여 줍니다.

![데이터 가져오기 > 데이터베이스](media/desktop-data-sources/data-sources_04.png)

**Power BI** 범주는 다음과 같은 데이터 연결을 제공합니다.

* Power BI 데이터 집합
* Power BI 데이터 흐름(베타)

다음 이미지는 **Power BI**에 대한 **데이터 가져오기** 창을 보여줍니다.

![데이터 가져오기 > Power BI](media/desktop-data-sources/data-sources_05.png)

**Azure** 범주는 다음과 같은 데이터 연결을 제공합니다.

* Azure SQL Database
* Azure SQL Data Warehouse
* Azure Analysis Services 데이터베이스
* Azure Blob Storage
* Azure Table Storage
* Azure Cosmos DB(베타)
* Azure Data Lake Storage
* Azure HDInsight(HDFS)
* Azure HDInsight Spark
* HDInsight 대화형 쿼리
* Azure Data Explorer(베타)

다음 그림은 **Azure** 에 대한 **데이터 가져오기**창을 보여 줍니다.

![데이터 가져오기 > Azure](media/desktop-data-sources/data-sources_06.png)

**온라인 서비스** 범주는 다음과 같은 데이터 연결을 제공합니다.

* SharePoint Online 목록
* Microsoft Exchange Online
* Dynamics 365(온라인)
* Dynamics NAV
* Dynamics 365 Business Central
* Dynamics 365 Business Central(온-프레미스)
* 앱용 Common Data Service(베타)
* Microsoft Azure Consumption Insights(베타)
* Azure DevOps(베타)
* Azure DevOps Server(베타)
* Salesforce 개체
* Salesforce 보고서
* Google 분석
* Adobe Analytics
* appFigures(베타)
* comScore Digital Analytix(베타)
* Dynamics 365 for Customer Insights(베타)
* Data.World - 데이터 집합 가져오기(베타)
* Facebook
* GitHub(베타)
* MailChimp(베타)
* Marketo(베타)
* Mixpanel(베타)
* Planview Enterprise One - PRM(베타)
* Planview Projectplace(베타)
* QuickBooks Online(베타)
* Smartsheet
* SparkPost(베타)
* Stripe(베타)
* SweetIQ(베타)
* Planview Enterprise One - CMT(베타)
* Twilio(베타)
* tyGraph(베타)
* Webtrends(베타)
* Zendesk(베타)
* TeamDesk(베타)

다음 그림은 **온라인 서비스**에 대한 **데이터 가져오기** 창을 보여 줍니다.

![데이터 가져오기 > 온라인 서비스](media/desktop-data-sources/data-sources_07.png)

**기타** 범주는 다음과 같은 데이터 연결을 제공합니다.

* Vertica
* 웹
* SharePoint 목록
* OData 피드
* Active Directory
* Microsoft Exchange
* HDFS(Hadoop 파일)
* Spark
* R 스크립트
* Python 스크립트
* ODBC
* OLE DB
* Denado
* Paxata(베타)
* 빈 쿼리

다음 그림은 **기타** 에 대한 **데이터 가져오기**창을 보여 줍니다.

![데이터 가져오기 > 기타](media/desktop-data-sources/data-sources_08.png)

> [!NOTE]
> 지금은 Azure Active Directory를 사용하여 보호되는 사용자 지정 데이터 소스에 연결할 수 없습니다.

## <a name="connecting-to-a-data-source"></a>데이터 소스에 연결
데이터 소스에 연결하려면 **데이터 가져오기** 창에서 데이터 소스를 선택한 다음 **연결**을 선택합니다. 다음 그림에서는 **기타** 데이터 연결 범주에서 **웹** 이 선택됩니다.

![웹에 연결](media/desktop-data-sources/data-sources_08a.png)

데이터 연결 형식과 관련된 연결 창이 표시됩니다. 자격 증명이 필요한 경우 제공하라는 메시지가 표시됩니다. 다음 그림은 웹 데이터 소스에 연결하기 위해 입력되는 URL을 보여 줍니다.

![입력 웹 URL](media/desktop-data-sources/datasources_fromwebbox.png)

URL 또는 리소스 연결 정보를 입력한 경우 **확인**을 선택합니다. Power BI Desktop이 데이터 소스에 연결하고 **탐색기**에 사용 가능한 데이터 소스를 제공합니다.

![탐색기 화면](media/desktop-data-sources/datasources_fromnavigatordialog.png)

**탐색기** 창의 맨 아래에 있는 **로드** 단추를 선택하여 데이터를 로드하거나 **편집** 단추를 선택하여 데이터를 로드하기 전에 쿼리를 편집할 수 있습니다.

Power BI Desktop에서 데이터 소스에 연결하는 데 필요한 작업을 마쳤습니다. 데이터 원본의 성장 목록에서 데이터에 연결을 시도하고 자주 확인하세요. 항상 이 목록에 계속해서 추가합니다.

## <a name="next-steps"></a>다음 단계
Power BI Desktop에서 모든 종류의 작업을 수행할 수 있습니다. 해당 기능에 대한 자세한 내용은 다음 리소스를 확인하세요.

* [Power BI Desktop이란?](desktop-what-is-desktop.md)
* [Power BI Desktop을 사용한 쿼리 개요](desktop-query-overview.md)
* [Power BI Desktop의 데이터 형식](desktop-data-types.md)
* [Power BI Desktop에서 데이터 셰이핑 및 결합](desktop-shape-and-combine-data.md)
* [Power BI Desktop의 일반적인 쿼리 작업](desktop-common-query-tasks.md)    
