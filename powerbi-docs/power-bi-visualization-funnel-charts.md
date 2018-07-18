---
title: 깔대기형 차트
description: Power BI의 깔때기형 차트
author: mihart
manager: kfile
ms.reviewer: ''
featuredvideoid: maTzOJSRB3g
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 01/29/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: bae4effe719fa74dfa5deb3545e81bfc2aac655f
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34292090"
---
# <a name="funnel-charts"></a>깔대기형 차트
깔때기형 차트는 순차적으로 연결된 단계가 있는 선형 프로세스를 시각화하는 데 도움이 됩니다. 예를 들어 잠재 고객 \> 적격 잠재 고객 \> 가망 고객 \> 계약 \> 완료 단계를 통해 고객을 추적하는 영업 깔때기가 있습니다.  깔때기의 모양은 추적 중인 프로세스의 상태를 한눈에 보여줍니다.

각 깔때기 단계는 합계의 백분율을 나타냅니다. 따라서 대부분의 경우 깔때기형 차트는 깔때기 모양으로, 첫 단계가 가장 크고 뒤로 갈수록 점점 작아집니다.  서양배 모양의 깔때기도 유용합니다. 프로세스의 문제를 식별할 수 있기 때문입니다.  하지만 일반적으로 첫 번째 단계인 "유입" 단계가 가장 큽니다.

![](media/power-bi-visualization-funnel-charts/funnelplain.png)

## <a name="when-to-use-a-funnel-chart"></a>깔때기형 차트를 사용하는 경우
다음과 같은 경우 깔때기형 차트를 사용하는 것이 좋습니다.

* 데이터가 순차적이고 4단계 이상을 통과하는 경우
* 첫 번째 단계의 "항목" 수가 최종 단계의 숫자보다 클 것으로 예상되는 경우
* 단계별 잠재적 수익/판매액/거래 등을 계산하려는 경우
* 변환 및 보존 비율을 계산하고 추적하려는 경우
* 선형 프로세스의 병목 상태를 표시하려는 경우
* 장바구니 워크플로를 추적하려는 경우
* 클릭 광고/마케팅 캠페인의 진행률 및 성공 여부를 추적하려는 경우

## <a name="working-with-funnel-charts"></a>깔때기형 차트 작업
깔대기형 차트:

* 보고서와 질문 및 답변에서 고정할 수 있습니다.
* 정렬할 수 있습니다.
* 여러 개의 차트를 지원합니다.
* 동일한 보고서 페이지에서 강조 표시하고 다른 시각화로 교차 필터링할 수 있습니다.
* 동일한 보고서 페이지에서 강조 표시하고 다른 시각화로 교차 필터링하는 데 사용할 수 있습니다.

## <a name="create-a-basic-funnel-chart"></a>기본 깔때기형 차트 만들기
이 비디오를 통해 판매 및 샘플 마케팅을 사용하여 깔때기형 차트를 만듭니다.

<iframe width="560" height="315" src="https://www.youtube.com/embed/qKRZPBnaUXM" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>


이제 영업 단계 각각에 있는 기회의 수를 보여 주는 고유한 깔때기형 차트를 만듭니다.

이러한 지침에서는 영업 기회 분석 샘플을 사용합니다. 이를 수행하려면 Power BI 서비스(app.powerbi.com) 또는 Power BI Desktop에 대한 [샘플을 다운로드](sample-datasets.md)합니다.   

1. [빈 보고서 페이지](power-bi-report-add-page.md)에서 시작하고 **SalesStage** \> **영업 단계** 필드를 선택합니다. Power BI 서비스를 사용하는 경우 [편집용 보기](service-interact-with-a-report-in-editing-view.md)에서 보고서를 엽니다.
   
    ![](media/power-bi-visualization-funnel-charts/funnelselectfield_new.png)
2. [차트를 깔때기로 변환](power-bi-report-change-visualization-type.md)합니다. **Sales Stage** 가 **그룹** 에 있습니다. 
3. **필드** 창에서 **팩트** \> **기회 수**를 선택합니다.
   
    ![](media/power-bi-visualization-funnel-charts/power-bi-funnel.png)
4. 막대를 마우스로 가리키면 다양한 정보가 표시됩니다.
   
   * 단계의 이름
   * 현재 이 단계에 있는 기회의 수
   * 전반적인 변환율(잠재 고객의 %) 
   * 이전 단계(이 경우에는 제안 단계/해결 단계)의 %인 단계-단계(즉, 중단율)
     
     ![](media/power-bi-visualization-funnel-charts/funnelhover_new.png)
5. [깔때기를 대시보드 타일로 추가합니다](service-dashboard-tiles.md). 
6. [보고서를 저장합니다](service-report-save.md).

## <a name="highlighting-and-cross-filtering"></a>강조 표시 및 교차 필터링
필터 창 사용 방법에 대한 자세한 내용은 [보고서에 필터 추가](power-bi-report-add-filter.md)를 참조하세요.

보고서 페이지에서 다른 시각화 요소를 교차 필터링하는 등치 지역도에서 막대를 강조 표시하고 그 반대의 경우도 마찬가지입니다. 계속 수행하려면 깔때기형 차트를 포함하는 보고서 페이지에 몇 가지 시각적 개체를 추가합니다.

1. 깔때기에서 **제안** 막대를 선택합니다. 이는 페이지의 다른 시각화 요소를 상호 간에 강조 표시합니다. Ctrl 키를 사용하면 여러 개를 선택할 수 있습니다.
   
   ![](media/power-bi-visualization-funnel-charts/funnelchartnoowl.gif)
2. 시각적 개체를 상호 간에 강조 표시하고 필터링하는 방법에 대한 기본 설정을 설정하려면 [Power BI에서 시각적 상호 작용](service-reports-visual-interactions.md)을 참조하세요.

## <a name="create-a-funnel-chart-in-qa"></a>질문 및 대답에서 깔때기형 차트 만들기
기회 분석 샘플 대시보드나 기회 분석 샘플 데이터 집합에서 고정된 하나 이상의 시각화가 있는 다른 대시보드를 엽니다.  질문 및 답변에서 질문을 입력하면 Power BI가 선택된 대시보드(타일이 고정된)와 관련된 모든 데이터 집합에서 답변을 검색합니다. 자세한 내용은 [Power BI - 기본 개념](service-basic-concepts.md)을 참조하세요.

1. 기회 분석 샘플 대시보드에서 질문 및 답변의 질문 상자에 질문을 입력하세요.
   
   ![](media/power-bi-visualization-funnel-charts/funnelfromqna_new.png)
   
2. Power BI에서 여러분이 선호하는 시각화 유형을 알 수 있도록 "깔때기형"으로 추가해야 합니다.

## <a name="next-steps"></a>다음 단계
[Power BI의 시각화 유형](power-bi-visualization-types-for-reports-and-q-and-a.md)

[시각화를 대시보드에 고정](service-dashboard-pin-tile-from-report.md)

[Power BI - 기본 개념](service-basic-concepts.md)

궁금한 점이 더 있나요? [Power BI 커뮤니티를 이용하세요.](http://community.powerbi.com/)

