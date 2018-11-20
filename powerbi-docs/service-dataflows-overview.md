---
title: Power BI의 데이터 흐름에 대해 알아보기
description: Power BI에서 데이터 흐름이 작동하는 방식 알아보기
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 11/06/2018
ms.author: davidi
LocalizationGroup: Data from files
ms.openlocfilehash: 360ffdd61525244bd75e57c8c9c9aad25131a13d
ms.sourcegitcommit: b23fdcc0ceff5acd2e4d52b15b310068236cf8c7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2018
ms.locfileid: "51267992"
---
# <a name="self-service-data-prep-in-power-bi-preview"></a>Power BI의 셀프 서비스 데이터 준비(미리 보기)

데이터 볼륨이 증가함에 따라 잘 구성된 실행 가능 정보로 데이터를 랭글링하는 문제도 증가하고 있습니다. 우리는 시각적 개체, 보고서 및 대시보드를 채워 빠르게 데이터 볼륨을 실행 가능한 인사이트로 전환할 수 있는 분석 준비가 된 데이터가 필요합니다. Power BI의 빅 데이터용 **셀프 서비스 데이터 준비**를 사용하면 몇 번의 클릭만으로 데이터를 Power BI 인사이트로 전환할 수 있습니다.

![Power BI에서 데이터 흐름 사용](media/service-dataflows-overview/powerbi-dataflows_01.png)

Power BI는 조직이 여러 원본의 데이터를 통합하고 모델링을 위해 준비하는 데 도움이 되도록 **데이터 흐름**을 도입했습니다. 분석가는 익숙한 셀프 서비스 도구를 사용하여 쉽게 데이터 흐름을 만들 수 있습니다. 데이터 흐름은 데이터 원본 연결, ETL 논리, 새로 고침 일정 등을 정의하여 빅 데이터를 수집, 변환, 통합 및 강화하는 데 사용됩니다. 또한 데이터 흐름의 일부인 새 모델 기반 계산 엔진은 데이터 분석가와 보고서 작성자 모두에게 데이터 준비 프로세스가 더 관리하기 쉽고 결정적이며 덜 번거롭게 해줍니다. 스프레드시트가 영향받는 모든 수식의 재계산을 처리하는 방법과 마찬가지로, 데이터 흐름도 사용자 대신 엔터티 또는 데이터 요소에 대한 변경을 관리하고, 업데이트를 자동화하며, 기본적인 데이터 새로 고침을 위한 논리 검사가 덜 지루하고 시간을 절약할 수 있도록 지원합니다. 데이터 흐름을 사용하면 전에는 데이터 과학자가 감독해야 했으며 완료하는 데 여러 시간 또는 여러 날이 필요했던 작업을 분석가 및 보고서 작성자가 몇 번의 클릭으로 처리할 수 있습니다. 

데이터는 Azure Data Lake Storage Gen2의 [**공통 데이터 모델**](https://docs.microsoft.com/powerapps/common-data-model/overview)에 엔터티로 저장됩니다. 데이터 흐름은 Power BI 서비스를 사용하여 앱 작업 영역에서 만들고 관리합니다.  

> [!NOTE]
> 데이터 흐름 기능은 미리 보기로 제공되며 일반 공급 전에 변경되고 업데이트될 수 있습니다.

 
**데이터 흐름**은 데이터를 쉽게 빌드, 사용 및 분석할 수 있도록 설계되었으며 Microsoft에서 게시한 표준화된 모듈식 확장 가능 데이터 스키마 컬렉션인 **공통 데이터 모델**을 사용하도록 설계되었습니다. 이 모델을 사용하면 마찰이 거의 없이 데이터 원본에서 Power BI 대시보드로 이동할 수 있습니다.

데이터 흐름을 사용하여 Dynamics 365, Salesforce, Azure SQL Database, Excel, SharePoint 등 지원되는 여러 온-프레미스 및 클라우드 기반 데이터 원본에서 데이터를 수집할 수 있습니다. 이 원본 수는 점점 증가합니다.

그런 다음, 공통 데이터 모델의 표준 엔터티에 데이터를 매핑하고 기존 엔터티를 수정 및 확장하고 사용자 지정 엔터티를 만들 수 있습니다. 고급 사용자는 수많은 Power BI Desktop 및 Excel 사용자가 이미 알고 있는 파워 쿼리 환경과 유사한 셀프 서비스, 로우 코드/노 코드, 기본 제공 파워 쿼리 제작 환경을 사용하여 완전히 사용자 지정된 데이터 흐름을 만들 수 있습니다.  

데이터 흐름을 만들면 Power BI Desktop 및 Power BI 서비스를 사용하여 공통 데이터 모델의 기능을 활용한 데이터 세트, 보고서, 대시보드 및 앱을 만들어 비즈니스 활동에 대한 깊이 있는 인사이트를 얻을 수 있습니다. 

데이터 흐름 새로 고침 예약은 데이터 세트와 마찬가지로 데이터 흐름을 만든 작업 영역에서 직접 관리합니다. 

## <a name="how-dataflows-work"></a>데이터 흐름 작동 방식

다음은 데이터 흐름이 작동하는 방식에 대한 몇 가지 예입니다.

* 조직은 공통 데이터 모델의 표준 엔터티에 데이터를 매핑하거나 고유한 사용자 지정 엔터티를 만들 수 있습니다. 그런 다음, 이러한 엔터티를 구성 요소로 사용하여 바로 사용할 수 있는 보고서, 대시보드 및 앱을 만들어 조직 전체의 사용자에게 배포할 수 있습니다. 

* 조직은 광범위한 Microsoft 데이터 커넥터 컬렉션을 사용하여 고유한 데이터 원본을 데이터 흐름에 연결할 수 있으며 파워 쿼리를 사용하여 해당 원본의 데이터를 매핑하고 Power BI로 가져올 수 있습니다. 데이터 흐름을 통해 해당 데이터를 가져오면(지정된 빈도로 새로 고침) Power BI Desktop 애플리케이션에서 해당 데이터 흐름 엔터티를 사용하여 매력적인 보고서와 대시보드를 만들 수 있습니다. 

## <a name="how-to-use-dataflows"></a>데이터 흐름 사용 방법

이전 섹션에서는 데이터 흐름을 사용하여 빠르게 Power BI에서 강력한 분석을 만들 수 있는 몇 가지 방법을 설명했습니다. 이 섹션에서는 조직에서 데이터 흐름을 사용하여 빠르게 인사이트를 만들 수 있는 방법을 살펴보고 BI Pro가 고유한 데이터 흐름을 만들고 고유한 조직에 대해 인사이트를 사용자 지정할 수 있는 방법을 간략하게 알아봅니다.

### <a name="extend-the-common-data-model-for-your-business-needs"></a>비즈니스 요구 사항에 맞게 공통 데이터 모델 확장
CDM(공통 데이터 모델)을 확장하려는 조직의 경우 데이터 흐름을 사용하면 비즈니스 인텔리전스 전문가가 표준 엔터티를 사용자 지정하거나 새 엔터티를 만들 수 있습니다. 데이터 모델을 사용자 지정하는 이러한 셀프 서비스 접근 방식을 데이터 흐름과 함께 사용하여 조직에 맞는 앱과 Power BI 대시보드를 빌드할 수 있습니다.

### <a name="define-dataflows-programmatically"></a>프로그래밍 방식으로 데이터 흐름 정의
고유한 프로그래밍 솔루션을 개발하여 데이터 흐름을 만들고자 할 수도 있습니다. 사용자 지정 데이터 흐름 정의 파일(model.json)을 프로그래밍 방식으로 만들 수 있는 기능과 공용 API를 사용하여 조직의 고유 데이터 및 분석 요구 사항에 맞는 사용자 지정 솔루션을 만듭니다. 

개발자는 공용 API를 통해 간단하고 쉬운 방법으로 Power BI와 데이터 흐름을 조작할 수 있습니다.

### <a name="extend-your-capabilities-with-azure"></a>Azure를 통해 기능 확장
모든 유료 Power BI 구독(사용자당 10GB, P1 노드당 100TB)에는 Azure Data Lake Storage Gen2가 포함되어 있습니다. 따라서 쉽게 Azure Data Lake에서 셀프 서비스 데이터 준비를 시작할 수 있습니다. 

조직의 Azure Data Lake Storage Gen2 계정에 데이터 흐름 데이터를 저장하도록 Power BI를 구성할 수 있습니다. Power BI가 Azure 구독에 연결되면 데이터 개발자 및 데이터 과학자가 Azure Machine Learning, Azure Databricks, Azure Data Factory 등과 같은 강력한 Azure 제품을 활용할 수 있습니다.

Power BI는 조직의 Azure Data Lake Storage 계정에 저장된 공통 데이터 모델 형식의 스키마화된 데이터가 있는 폴더에 연결할 수도 있습니다. 이러한 폴더는 Azure Data Services와 같은 서비스를 통해 만들 수 있습니다. 이러한 폴더에 연결하면 분석가가 Power BI의 데이터로 원활하게 작업할 수 있습니다. 


## <a name="dataflow-capabilities-on-power-bi-premium"></a>Power BI Premium의 데이터 흐름 기능

데이터 흐름 기능 및 워크로드가 Power BI Premium 구독에서 작동하려면 해당 프리미엄 용량의 데이터 흐름 워크로드가 켜져 있어야 합니다. [Power BI Premium이란](service-premium.md) 문서에서 Power BI Premium에 대해 자세히 알아볼 수 있습니다. 

다음 표에는 Power BI Pro 계정을 사용하는 경우의 데이터 흐름 기능 및 해당 용량이 Power BI Premium을 사용하는 경우와 비교하여 설명되어 있습니다.


|데이터 흐름 기능 | Power BI Pro |   Power BI Premium |
|---------|---------|---------|
|예약된 새로 고침| 8/일|  48|
|총 스토리지| 10GB/사용자  |100TB/노드|
|파워 쿼리 온라인으로 데이터 흐름 제작|    +   |+|
|Power BI 내 데이터 흐름 관리|   +|  +|
|Power BI Desktop의 데이터 흐름 데이터 커넥터|  +|  +|
|Azure와의 통합|    +|  +|
|계산된 엔터티(M을 통한 스토리지 내 변환) | |   +|
|새 커넥터|    +|  +|
|데이터 흐름 증분 새로 고침|  |   +|
|Power BI Premium 용량에서 실행/변환 병렬 실행|   |   +|
|데이터 흐름 연결된 엔터티| |        +|
|표준화된 스키마/공통 데이터 모델에 대한 기본 제공 지원|  +|  +|



## <a name="summary-of-self-service-data-prep-for-big-data-in-power-bi"></a>Power BI의 빅 데이터용 셀프 서비스 데이터 준비에 대한 요약
이 문서의 앞에 설명된 것처럼 **데이터 흐름**을 사용하여 비즈니스 데이터를 더 효율적으로 제어하고 더 빠르게 인사이트를 얻을 수 있는 여러 시나리오와 예제가 있습니다. 공통 데이터 모델에 의해 정의된 표준 데이터 모델(스키마)을 사용하면 데이터 흐름이 중요한 비즈니스 데이터를 가져와 매우 짧은 기간 동안 BI 인사이트를 모델링하고 만들기를 위한 데이터를 준비할 수 있습니다. 이전에는 이러한 인사이트 만들기에 몇 달 또는 그 이상의 시간이 걸렸습니다. 

**공통 데이터 모델**의 표준화된 형식으로 비즈니스 데이터를 저장하면 BI Pro(또는 개발자)가 시각적 개체와 보고서를 빠르고 쉽게 자동으로 생성하는 앱을 만들 수 있습니다. 이 작업에는 다음과 같은 작업이 포함되며 이로 제한되지 않습니다.


* 데이터를 공통 데이터 모델의 표준 엔터티에 매핑하여 데이터를 통합하고 알려진 스키마를 활용하여 바로 사용할 수 있는 인사이트를 얻습니다.
* 고유한 사용자 지정 엔터티를 만들어 조직 전체에서 데이터를 통합합니다. 
* 데이터 흐름의 일부로 **외부 데이터**를 사용하고 새로 고치며 해당 데이터 가져오기를 사용하도록 설정하여 인사이트를 얻습니다.
* 개발자를 위한 데이터 흐름을 시작합니다.





## <a name="next-steps"></a>다음 단계

이 문서에는 Power BI의 빅 데이터용 셀프 서비스 데이터 준비에 대한 개요와 이 기능을 사용할 수 있는 여러 방법이 제공되어 있습니다. 다음 문서에서는 데이터 흐름의 공통 사용 시나리오에 대해 자세히 설명합니다. 

* [Power BI에서 데이터 흐름 만들기 및 사용](service-dataflows-create-use.md)
* [Power BI Premium의 계산된 엔터티 사용(미리 보기)](service-dataflows-computed-entities-premium.md)
* [온-프레미스 데이터 원본으로 만든 데이터 흐름 사용(미리 보기)](service-dataflows-on-premises-gateways.md)
* [Power BI 데이터 흐름에 사용할 수 있는 개발자 리소스(미리 보기)](service-dataflows-developer-resources.md)

파워 쿼리 및 예약된 새로 고침에 대한 자세한 내용은 다음 문서를 참조하세요.
* [Power BI Desktop을 사용한 쿼리 개요](desktop-query-overview.md)
* [예약된 새로 고침 구성](refresh-scheduled-refresh.md)

공통 데이터 모델에 대한 자세한 내용은 해당 개요 문서를 참조할 수 있습니다.
* [공통 데이터 모델 - 개요 ](https://docs.microsoft.com/powerapps/common-data-model/overview)

