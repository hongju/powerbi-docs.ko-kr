---
title: "Power BI에서 템플릿 콘텐츠 팩 작성"
description: "템플릿 콘텐츠 팩 작성"
services: powerbi
documentationcenter: 
author: markingmyname
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/09/2017
ms.author: maghan
ms.openlocfilehash: 9b8de53534c94ad995e2d953cfc6994b93915bd8
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/30/2018
---
# <a name="author-template-content-packs-in-power-bi"></a>Power BI에서 템플릿 콘텐츠 팩 작성
템플릿 콘텐츠 팩 작성 시에는 Power BI Desktop 및 PowerBI.com을 사용합니다. 콘텐츠 팩에는 네 가지 구성 요소가 있습니다.

* 쿼리를 사용하면 데이터를 [연결](../desktop-connect-to-data.md) 및 [변환](../desktop-query-overview.md)할 수 있으며 [매개 변수](https://powerbi.microsoft.com/blog/deep-dive-into-query-parameters-and-power-bi-templates/)도 정의할 수 있습니다.  
* 데이터 모델로 [관계](../desktop-create-and-manage-relationships.md), [측정값](../desktop-measures.md) 및 Q&A 개선을 만들 수 있습니다.  
* 보고서 [페이지](../desktop-report-view.md)는 데이터에 대한 정보를 제공하는 시각적 개체 및 필터가 포함됩니다.  
* [대시보드](../service-dashboards.md) 및 [타일](../service-dashboard-create.md)은 포함된 Insights에 대한 개요를 제공합니다.  

기존 Power BI 기능으로 각 구성 요소에 익숙할 수 있습니다. 콘텐츠 팩을 빌드할 때는 각 측면에 대해 추가 고려 사항이 있습니다. 자세한 내용은 아래 각 섹션을 참조하세요.

<a name="queries"></a>

## <a name="queries"></a>쿼리
템플릿 콘텐츠 팩의 경우 Power BI Desktop에서 개발된 쿼리를 사용하여 데이터 원본에 연결하고 데이터를 가져옵니다. 이러한 쿼리는 일관된 스키마를 반환하는 데 필요하며 예약된 데이터 새로 고침에 대해 지원됩니다(직접 쿼리는 지원되지 않음).

템플릿 콘텐츠 팩은 콘텐츠 팩당 하나의 데이터 원본만 지원하므로 쿼리를 신중하게 정의합니다. 단일 데이터 원본은 동일한 인증을 요구하는 원본으로 정의됩니다. 모든 호출이 동일한 API 끝점을 향하며 동일한 인증을 사용하는 경우 다른 쿼리에서 여러 API 호출을 만들 수 있습니다. Power BI 콘텐츠 팩은 서로 다른 인증을 요구하는 여러 원본을 지원하지 않습니다.

### <a name="connect-to-your-api"></a>API에 연결
시작하려면 Power BI Desktop에서 API에 연결하여 쿼리 작성을 시작해야 합니다.

API에 연결하려면 Power BI Desktop에서 바로 사용할 수 있는 데이터 커넥터를 사용할 수 있습니다. 웹 데이터 커넥터(데이터 가져오기 -> 웹)를 사용하여 OData 피드에 연결하도록 Rest API 또는 OData 커넥터(데이터 가져오기 -> OData 피드)에 연결할 수 있습니다. API가 기본 인증을 지원하는 경우에만 이러한 커넥터는 즉시 작동합니다.

> [!NOTE]
> API가 OAuth 2.0 또는 웹 API 키와 같은 다른 인증 유형을 사용하는 경우 Power BI Desktop이 성공적으로 API에 연결하고 인증하도록 사용자 고유의 데이터 커넥터를 개발해야 합니다. 콘텐츠 팩에 대한 고유한 데이터 커넥터를 개발하는 방법에 대한 내용은 [여기](https://aka.ms/DataConnectors)에서 데이터 커넥터 설명서를 참조하세요. 
> 
> 

### <a name="consider-the-source"></a>소스 고려
쿼리는 데이터 모델에 포함될 데이터를 정의합니다. 시스템의 크기에 따라 이러한 쿼리는 고객이 비즈니스 시나리오에 따라 관리하기 쉬운 크기를 처리하도록 해주는 필터도 포함합니다.

Power BI 콘텐츠 팩에서는 여러 쿼리를 병렬로, 여러 사용자에 대해 동시에 실행할 수 있습니다.  제한 및 동시성 전략을 미리 계획하고 콘텐츠 팩을 내결함성 있게 만드는 방법을 문의하세요.

### <a name="schema-enforcement"></a>스키마 적용
쿼리는 시스템 변경에 대해 복원력이 있어야 하며 새로 고침 시 스키마 변경으로 모델이 손상될 수 있습니다. 소스에서 일부 쿼리에 대해 Null/누락된 스키마 결과를 반환할 수 있는 경우 빈 테이블을 반환하는 것을 고려하거나 사용자에게 의미 있는 사용자 지정 오류 메시지를 throw합니다.

### <a name="parameters"></a>매개 변수
Power BI Desktop에서 [매개 변수](https://powerbi.microsoft.com/blog/deep-dive-into-query-parameters-and-power-bi-templates/)를 통해 사용자는 사용자가 검색한 데이터를 사용자 지정하는 입력 값을 제공할 수 있습니다. 자세한 쿼리 또는 보고서를 작성하는 데 시간을 투자한 후 재작업을 방지하도록 매개 변수를 미리 생각합니다.

> [!NOTE]
> 템플릿 콘텐츠 팩에서는 현재 텍스트 매개 변수만 지원합니다. 개발 중에 다른 매개 변수 형식을 사용할 수 있지만 [테스트](template-content-pack-testing.md#templates) 부분 중에는 사용자가 제공한 모든 값이 리터럴입니다.
> 
> 

### <a name="additional-query-tips"></a>추가 쿼리 팁
* 모든 열은 적절하게 형식화되어야 합니다.  
* 열에는 정보를 전달하는 이름을 사용합니다(Q&A 참조).  
* 공유 논리의 경우 함수 또는 쿼리를 사용하는 것이 좋습니다.  
* 개인 정보 수준은 현재 서비스에서 지원되지 않습니다. 개인 정보 수준에 대한 프롬프트를 받으면 상대 경로를 사용하도록 쿼리를 다시 작성해야 할 수 있습니다.  

## <a name="data-model"></a>데이터 모델
잘 정의된 데이터 모델을 통해 고객은 콘텐츠 팩과 쉽고 직관적으로 상호 작용할 수 있습니다. Power BI Desktop에서 데이터 모델을 생성합니다.

> [!NOTE]
> 대부분의 기본 모델링(형식 지정, 열 이름)은 [쿼리](#queries)에서 수행됩니다.
> 
> 

### <a name="qa"></a>Q&A
모델링은 또한 Q&A에서 고객에게 얼마나 잘 결과를 제공할 수 있는지에도 영향을 줍니다. 자주 사용되는 열에 동의어를 추가하고 해당 열이 [쿼리](#queries)에서 적절하게 이름 지정되도록 해야 합니다.

### <a name="additional-data-model-tips"></a>추가 데이터 모델 팁
* 모든 값 열에 형식이 적용됩니다.
    >[!NOTE]
    >형식은 쿼리에 적용되어야 합니다.  
* 모든 측정값에 형식이 적용됩니다.  
* 기본 요약이 설정됩니다. 특히 해당하는 경우 "요약 안 함"(예를 들어 고유 값인 경우).  
* 데이터 범주가 설정되었습니다(해당하는 경우).  
* 필요에 따라 관계가 설정됩니다.  

## <a name="reports"></a>보고서
보고서 페이지는 콘텐츠 팩에 포함된 데이터에 대한 추가 정보를 제공합니다. 보고서의 페이지를 사용하여 콘텐츠 팩에서 해결 시도 중인 주요 비즈니스 질문에 대답할 수 있습니다. Power BI Desktop을 사용하여 보고서를 만듭니다.

> [!NOTE]
> 하나의 보고서만 콘텐츠 팩에 포함될 수 있으며 다양한 페이지를 활용하여 시나리오의 특정 섹션을 호출합니다.
> 
> 

### <a name="additional-report-tips"></a>추가 보고서 팁
* 교차 필터링을 위해 페이지당 두 개 이상의 시각적 개체를 사용합니다.  
* 시각적 개체를 신중하게 맞춥니다(겹치지 않게).  
* 페이지 레이아웃을 "4:3" 또는 "16:9" 모드로 설정합니다.  
* 제시된 모든 집계는 숫자로 인식됩니다(평균, 고유 값).  
* 조각화를 통해 관계형 결과가 생성됩니다.  
* 로고는 최상위 보고서 이상에 있습니다.  
* 요소는 색 구성표에 가능한 범위 내에 있습니다.  

<a name="dashboard"></a>

## <a name="dashboard"></a>대시보드
대시보드는 고객에 대해 콘텐츠 팩과 상호 작용하는 주요 지점입니다. 포함된 콘텐츠에 대한 개요를 포함하며 특히 비즈니스 시나리오에 대한 중요한 메트릭이 포함됩니다.

템플릿 콘텐츠 팩에 대한 대시보드를 만들려면 데이터 가져오기 > 파일을 통해 PBIX를 업로드하거나 Power BI Desktop에서 직접 게시합니다.

> [!NOTE]
> 템플릿 콘텐츠 팩에는 현재 콘텐츠 팩당 단일 보고서 및 데이터 집합이 필요합니다. 여러 보고서/데이터 집합의 콘텐츠를 콘텐츠 팩에 사용되는 대시보드에 고정하지 마세요.
> 
> 

### <a name="additional-dashboard-tips"></a>추가 대시보드 팁
* 고정할 때는 동일한 테마를 유지하여 대시보드의 타일이 일관되게 합니다.  
* 로고를 테마에 고정하여 소비자가 팩의 출처를 알 수 있도록 합니다.  
* 대부분의 화면 해상도에 작동하는 추천 레이아웃은 너비가 5-6개의 작은 타일입니다.  
* 모든 대시보드 타일에는 적절한 제목/부제가 있어야 합니다.  
* 가로 또는 세로로 다양한 시나리오에 맞는 대시보드 그룹화를 사용하는 것이 좋습니다.  

<a name="restrictions"></a>

## <a name="summary-of-restrictions"></a>제한 사항 요약
위의 섹션에 나열된 것처럼 현재 템플릿 콘텐츠 팩에는 일련의 제한 사항이 있습니다.  

| 지원됨 | *지원되지 않음* |
| --- | --- |
| PBI Desktop에 기본 제공되는 데이터 집합 |*다른 콘텐츠 팩 또는 Excel 파일 등의 입력의 데이터 집합* |
| 클라우드 예약된 데이터 새로 고침에 대해 지원되는 데이터 원본 |*직접 쿼리 또는 온-프레미스 연결은 지원되지 않음* |
| 해당 위치에서 일관된 스키마 또는 오류를 반환하는 쿼리 |*동적 또는 사용자 지정 스키마* |
| 데이터 집합당 한 개의 데이터 원본 |*여러 데이터 원본으로 감지되는 매시업 또는 URL 등의 여러 데이터 원본* |
| 텍스트 형식의 매개 변수 |*기타 매개 변수 형식(예: 날짜) 또는 "허용되는 값 목록"* |
| 한 개 대시보드, 보고서 및 데이터 집합 |*여러 개의 대시보드, 보고서 또는 데이터 집합* |

## <a name="next-step"></a>다음 단계
[콘텐츠 팩 테스트 및 제출](template-content-pack-testing.md)

