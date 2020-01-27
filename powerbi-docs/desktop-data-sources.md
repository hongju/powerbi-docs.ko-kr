---
title: Power BI Desktop의 데이터 원본
description: Power BI Desktop의 데이터 원본
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/08/2020
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: fd25e4ca6357dbfa5954eeabe0bf97fb6ccb8a1c
ms.sourcegitcommit: 97597ff7d9ac2c08c364ecf0c729eab5d59850ce
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2020
ms.locfileid: "75761367"
---
# <a name="data-sources-in-power-bi-desktop"></a>Power BI Desktop의 데이터 원본

Power BI Desktop을 사용하면 다양한 원본의 데이터에 연결할 수 있습니다. 사용 가능한 데이터 원본에 대한 전체 목록은 [Power BI 데이터 원본](power-bi-data-sources.md)을 참조하세요.

데이터에 연결하려면 리본 메뉴의 **홈**  탭에서 **데이터 가져오기** 를 선택합니다. 아래쪽 화살표 또는 단추의 **데이터 가져오기** 텍스트를 선택하면 다음 이미지의 **가장 일반적** 데이터 형식 메뉴가 표시됩니다.

![Power BI Desktop에서 데이터 가져오기](media/desktop-data-sources/data-sources-01.png)

**자세히…** 선택 **가장 일반적** 메뉴에서 **추가...**를 선택하면**데이터 가져오기** 창이 표시됩니다. **데이터 가져오기** **아이콘 단추**를 직접 선택하여 **데이터 가져오기** 창을 표시할 수도 있습니다(**가장 일반적** 메뉴 무시).

![데이터 단추 가져오기](media/desktop-data-sources/data-sources-02.png)

> [!NOTE]
> Power BI 팀은 **Power BI Desktop** 및 **Power BI 서비스**에 사용할 수 있는 데이터 원본을 지속적으로 확장합니다. 따라서 *베타* 또는 *미리 보기*로 표시된 작업 진행 데이터 원본의 초기 버전을 자주 볼 수 있습니다. *베타* 또는 *미리 보기*로 표시된 모든 데이터 원본은 제한된 지원 및 기능을 가지며 프로덕션 환경에서는 사용할 수 없습니다. 또한 **Power BI Desktop**에서 ‘베타’ 또는 ‘미리 보기’로 표시된 데이터 원본은 데이터 원본이 GA(일반 공급) 상태가 될 때까지 **Power BI 서비스** 또는 기타 Microsoft 서비스에서 사용하지 못할 수 있습니다.  

> [!NOTE]
> 인증에 Internet Explorer 10 이상이 필요한 Power BI Desktop용 데이터 커넥터가 많습니다. 


## <a name="data-sources"></a>데이터 원본
데이터 유형은 다음 범주로 구성됩니다.

* 모두
* 파일
* 데이터베이스
* Power BI
* Azure
* 온라인 서비스
* 기타

**모두** 범주에는 모든 범주의 모든 데이터 연결 유형이 포함됩니다.

**파일** 범주는 다음과 같은 데이터 연결을 제공합니다.

* Excel
* 텍스트/CSV
* XML
* JSON
* 폴더
* PDF
* SharePoint 폴더

다음 그림은 **파일**에 대한 **데이터 가져오기** 창을 보여 줍니다.

![데이터 가져오기 > 파일](media/desktop-data-sources/data-sources-03.png)

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
* Teradata
* SAP HANA 데이터베이스
* SAP Business Warehouse 애플리케이션 서버
* SAP Business Warehouse 메시지 서버
* Amazon Redshift
* Impala
* Google BigQuery
* Vertica
* Snowflake
* Essbase
* AtScale 큐브
* BI 커넥터
* Dremio
* Exasol
* Indexima(베타)
* InterSystems IRIS(베타)
* Jethro(베타)
* Kyligence 엔터프라이즈(베타)
* MarkLogic(베타)

> [!NOTE]
> 일부 데이터베이스 커넥터는 **파일 > 옵션 및 설정 > 옵션**을 선택한 다음 **미리 보기 기능**을 선택하고 커넥터를 사용하도록 설정하여 사용해야 합니다. 위에서 언급한 커넥터 중 일부를 표시하지 않고 사용하지 않으려는 경우 **미리 보기 기능** 설정을 확인합니다. *베타* 또는 *미리 보기*로 표시된 모든 데이터 원본은 제한된 지원 및 기능을 가지며 프로덕션 환경에서는 사용할 수 없습니다.

다음 그림은 **데이터베이스**에 대한 **데이터 가져오기** 창을 보여 줍니다.

![데이터 가져오기 > 데이터베이스](media/desktop-data-sources/data-sources-04.png)

**Power Platform** 범주는 다음과 같은 데이터 연결을 제공합니다.

* Power BI 데이터 세트
* Power BI 데이터 흐름
* Common Data Service
* Power Platform 데이터 흐름

다음 그림은 **Power Platform**에 대한 **데이터 가져오기** 창을 보여 줍니다.

![데이터 가져오기 > Power BI](media/desktop-data-sources/data-sources-05.png)

**Azure** 범주는 다음과 같은 데이터 연결을 제공합니다.

* Azure SQL Database
* Azure SQL Data Warehouse
* Azure Analysis Services 데이터베이스
* Azure Blob Storage
* Azure Table Storage
* Azure Cosmos DB
* Azure Data Lake Storage Gen2
* Azure Data Lake Storage Gen1
* Azure HDInsight(HDFS)
* Azure HDInsight Spark
* HDInsight 대화형 쿼리
* Azure Data Explorer(Kusto)
* Azure Cost Management
* Azure Time Series Insights(베타)

다음 그림은 **Azure** 에 대한 **데이터 가져오기** 창을 보여 줍니다.

![데이터 가져오기 > Azure](media/desktop-data-sources/data-sources-06.png)

**온라인 서비스** 범주는 다음과 같은 데이터 연결을 제공합니다.

* SharePoint Online 목록
* Microsoft Exchange Online
* Dynamics 365(온라인)
* Dynamics NAV
* Dynamics 365 Business Central
* Dynamics 365 Business Central(온-프레미스)
* Microsoft Azure Consumption Insights(베타)
* Azure DevOps(베타)
* Azure DevOps Server(베타)
* Salesforce 개체
* Salesforce 보고서
* Google 애널리틱스
* Adobe Analytics
* appFigures(베타)
* Data.World - 데이터 세트 가져오기(베타)
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
* Dynamics 365 Customer Insights(베타)
* Emigo 데이터 원본(베타)
* Entersoft Business Suite(베타)
* 산업 앱 스토어
* Intune Data Warehouse(베타)
* Microsoft Graph 보안(베타)
* 빠른 자료
* TeamDesk(베타)


다음 그림은 **온라인 서비스**에 대한 **데이터 가져오기** 창을 보여 줍니다.

![데이터 가져오기 > 온라인 서비스](media/desktop-data-sources/data-sources-07.png)

**기타** 범주는 다음과 같은 데이터 연결을 제공합니다.

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
* BI360 - 예산 및 재무 보고(베타)
* Denodo
* 정보 표(베타)
* Paxata 
* QubolePresto(베타)
* Roamler(베타)
* SurveyMonkey(베타)
* Tenforce(스마트) 목록(베타)
* 직원 차원(베타)
* 빈 쿼리

다음 그림은 **기타**에 대한 **데이터 가져오기** 창을 보여 줍니다.

![데이터 가져오기 > 기타](media/desktop-data-sources/data-sources-08.png)

> [!NOTE]
> 지금은 Azure Active Directory를 사용하여 보호되는 사용자 지정 데이터 원본에 연결할 수 없습니다.

## <a name="connecting-to-a-data-source"></a>데이터 원본에 연결
데이터 원본에 연결하려면 **데이터 가져오기** 창에서 데이터 원본을 선택한 다음 **연결**을 선택합니다. 다음 그림에서는 **기타** 데이터 연결 범주에서 **웹**이 선택됩니다.

![웹에 연결](media/desktop-data-sources/data-sources-08.png)

데이터 연결 형식과 관련된 연결 창이 표시됩니다. 자격 증명이 필요한 경우 제공하라는 메시지가 표시됩니다. 다음 그림은 웹 데이터 소스에 연결하기 위해 입력되는 URL을 보여 줍니다.

![입력 웹 URL](media/desktop-data-sources/datasources-fromwebbox.png)

URL 또는 리소스 연결 정보를 입력한 경우 **확인**을 선택합니다. Power BI Desktop이 데이터 소스에 연결하고 **탐색기**에 사용 가능한 데이터 소스를 제공합니다.

![탐색기 화면](media/desktop-data-sources/datasources-fromnavigatordialog.png)

**탐색기** 창의 맨 아래에 있는 **로드** 단추를 선택하여 데이터를 로드하거나 **편집** 단추를 선택하여 데이터를 로드하기 전에 쿼리를 편집할 수 있습니다.

Power BI Desktop에서 데이터 소스에 연결하는 데 필요한 작업을 마쳤습니다. 데이터 원본의 성장 목록에서 데이터에 연결을 시도하고 자주 확인하세요. 항상 이 목록에 계속해서 추가합니다.

## <a name="using-pbids-files-to-get-data"></a>PBIDS 파일을 사용하여 데이터 가져오기

PBIDS 파일은 특정 구조가 있는 Power BI Desktop 파일이며, Power BI 데이터 원본 파일임을 식별하기 위한 .PBIDS 확장명이 있습니다.

조직의 보고서 작성자를 위한 **데이터 가져오기** 환경을 간소화하기 위해 .PBIDS 파일을 만들 수 있습니다. 새 보고서 작성자를 위해 PBIDS 파일의 사용이 용이하도록, 관리자는 일반적으로 사용되는 연결용으로 이러한 파일을 만드는 것이 좋습니다. 

작성자가 .PBIDS 파일을 열 때, Power BI Desktop이 열리고 사용자에게 인증을 위해 자격 증명을 입력하라는 메시지를 표시하고 파일에 지정되어 있는 데이터 원본에 연결합니다. 탐색 대화 상자가 나타나면, 사용자가 해당 데이터 원본에서 테이블을 선택하여 모델에 로드해야 합니다. .PBIDS 파일에서 지정되지 않은 경우 사용자가 데이터베이스를 선택해야 할 수도 있습니다. 

선택한 후에는 사용자가 시각화를 빌드하거나 ‘최근 원본’을 다시 방문하여 새 테이블 집합을 모델에 로드할 수 있습니다.  

현재 .PBIDS 파일은 한 파일에서 단일 데이터 원본만 지원합니다. 둘 이상의 데이터 원본을 지정하면 오류가 발생합니다. 

.PBIDS 파일을 생성하려면 관리자가 단일 연결에 필요한 입력을 지정해야 하며, **DirectQuery** 또는 **가져오기**로 연결 모드를 지정할 수 있습니다. 파일에 **모드**가 없거나 파일이 null인 경우, Power BI Desktop에서 파일을 여는 사용자에게 DirectQuery 또는 가져오기를 선택하라는 메시지가 표시됩니다. 

### <a name="pbids-file-examples"></a>PBIDS 파일 예제

이 섹션에서는 일반적으로 사용되는 데이터 원본의 몇 가지 예를 제공합니다. .PBIDS 파일 형식은 Power BI Desktop에서도 지원되는 데이터 연결만 지원합니다. 단, Live Connect 및 빈 쿼리의 경우는 예외입니다. 

.PBIDS 파일은 인증 정보와 테이블 및 스키마 정보를 포함하지 *않습니다*.  

다음은 .PBIDS 파일에 대한 몇 가지 일반적인 예이며, 완전하거나 포괄적이지는 않습니다. 다른 데이터 원본에 대해서는 [프로토콜 및 주소 정보를 위한 DSR(데이터 원본 참조) 서식](https://docs.microsoft.com/azure/data-catalog/data-catalog-dsr#data-source-reference-specification)을 참조할 수 있습니다.

이러한 예는 편의를 위한 것으로, 포괄적이지 않으며 지원되는 모든 커넥터를 DSR 서식에 포함하지는 않습니다. 관리자 또는 조직은 이러한 예를 자체의 고유한 데이터 원본 파일을 만들고 지원할 수 있는 가이드로 사용하여 자체의 고유한 데이터 원본을 만들 수 있습니다. 


**Azure AS**
```
{ 
    "version": "0.1", 
    "connections": [ 
    { 
        "details": { 
        "protocol": "analysis-services", 
        "address": { 
            "server": "server-here" 
        }, 
        } 
    } 
    ] 
}
```


 

**폴더**
```
{ 
  "version": "0.1", 
  "connections": [ 
    { 
      "details": { 
        "protocol": "folder", 
        "address": { 
            "path": "folder-path-here" 
        } 
      } 
    } 
  ] 
} 
```

**OData**
```
{ 
  "version": "0.1", 
  "connections": [ 
    { 
      "details": { 
        "protocol": "odata", 
        "address": { 
            "url": "URL-here" 
        } 
      } 
    } 
  ] 
} 
```
 
**SAP BW**
```
{ 
  "version": "0.1", 
  "connections": [ 
    { 
      "details": { 
        "protocol": "sap-bw-olap", 
        "address": { 
          "server": "server-name-here", 
          "systemNumber": "system-number-here", 
          "clientId": "client-id-here" 
        }, 
      } 
    } 
  ] 
} 
```
 
**SAP Hana**
```
{ 
  "version": "0.1", 
  "connections": [ 
    { 
      "details": { 
        "protocol": "sap-hana-sql", 
        "address": { 
          "server": "server-name-here:port-here" 
        }, 
      } 
    } 
  ] 
} 
```

**SharePoint 목록**

URL은 사이트 내의 목록이 아니라 SharePoint 사이트 자체를 가리켜야 합니다. 사용자는 해당 사이트에서 목록을 하나 이상 선택할 수 있는 탐색기를 가져옵니다(이러한 목록은 각각 모델에서 테이블이 됩니다). 
```
{ 
  "version": "0.1", 
  "connections": [ 
    { 
      "details": { 
        "protocol": "sharepoint-list", 
        "address": { 
          "url": "URL-here" 
        }, 
       } 
    } 
  ] 
} 
```
 
 
**SQL Server**
```
{ 
  "version": "0.1", 
  "connections": [ 
    { 
      "details": { 
        "protocol": "tds", 
        "address": { 
          "server": "server-name-here", 
          "database": "db-name-here (optional) "
        } 
      }, 
      "options": {}, 
      "mode": "DirectQuery" 
    } 
  ] 
} 
```
 

**텍스트 파일**
```
{ 
  "version": "0.1", 
  "connections": [ 
    { 
      "details": { 
        "protocol": "file", 
        "address": { 
            "path": "path-here" 
        } 
      } 
    } 
  ] 
} 
```
 

**웹**
```
{ 
  "version": "0.1", 
  "connections": [ 
    { 
      "details": { 
        "protocol": "http", 
        "address": { 
            "url": "URL-here" 
        } 
      } 
    } 
  ] 
} 
```
 

**데이터 흐름**
```
{
  "version": "0.1",
  "connections": [
    {
      "details": {
        "protocol": "powerbi-dataflows",
        "address": {
          "workspace":"workspace id (Guid)",
          "dataflow":"optional dataflow id (Guid)",
          "entity":"optional entity name"
        }
       }
    }
  ]
}
```


## <a name="next-steps"></a>다음 단계
Power BI Desktop에서 모든 종류의 작업을 수행할 수 있습니다. 해당 기능에 대한 자세한 내용은 다음 리소스를 확인하세요.

* [Power BI Desktop이란?](desktop-what-is-desktop.md)
* [Power BI Desktop을 사용한 쿼리 개요](desktop-query-overview.md)
* [Power BI Desktop의 데이터 형식](desktop-data-types.md)
* [Power BI Desktop에서 데이터 셰이핑 및 결합](desktop-shape-and-combine-data.md)
* [Power BI Desktop의 일반적인 쿼리 작업](desktop-common-query-tasks.md)    
