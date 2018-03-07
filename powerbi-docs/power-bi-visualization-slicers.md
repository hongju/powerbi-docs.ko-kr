---
title: "Power BI의 슬라이서(자습서)"
description: "자습서: Power BI의 슬라이서"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: zIZPA0UrJyA
qualityfocus: monitoring
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 05/30/2017
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 619f694e6e3ed167a14262994c1c978d5b4ea2e0
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/24/2018
---
# <a name="slicers-in-power-bi-service-tutorial"></a>Power BI 서비스의 슬라이서(자습서)
영업 담당 부사장은 사업부 전체 또는 지역관리자 개별에 대한 수많은 지표를 자세히 보려고 할 수도 있습니다. 이때 관리자별로 별도의 보고서 페이지를 만들거나 슬라이서를 사용할 수 있습니다. 슬라이서는 페이지에서 다른 시각화에 표시된 데이터 집합의 부분을 좁힙니다.  슬라이서는 필터링의 다른 방법입니다.

![](media/power-bi-visualization-slicers/slicer2.gif)

## <a name="when-to-use-a-slicer"></a>슬라이서를 사용하는 경우
슬라이서는 다음과 같은 상황에서 탁월한 선택입니다.

* 쉬운 액세스를 위해 보고서 캔버스에 일반적으로 사용하거나 중요한 필터를 표시하는 경우
* 드롭다운 목록을 열어 필터링 세부 정보를 검토하지 않고도 현재 필터링된 상태를 쉽게 보려는 경우
* 필요하지 않지만 필터링하는 데 사용할 수 있는 열을 숨기는 경우 - 슬라이서는 더 좁고 깔끔한 테이블을 만듭니다.
* 자세한 보고서를 만드는 경우 - 슬라이서는 중점을 두려는 보고서의 흥미로운 부분 옆에 배치할 수 있는 유동 개체이기 때문입니다.

## <a name="create-a-slicer"></a>슬라이서 만들기
<iframe width="560" height="315" src="https://www.youtube.com/embed/zIZPA0UrJyA" frameborder="0" allowfullscreen></iframe>


1. [편집용 보기](service-interact-with-a-report-in-editing-view.md)에서 [소매점 분석 샘플](sample-retail-analysis.md)을 열고[새 보고서 페이지를 추가](power-bi-report-add-page.md)합니다.
2. 필드 창에서 **구역 > 구역 관리자**를 선택합니다.
   
    ![](media/power-bi-visualization-slicers/pbi_slicer_chartfirst.png)
3. 시각화를 슬라이서로 변환합니다. 시각화 창에서 슬라이서 아이콘을 선택합니다.
   
    ![](media/power-bi-visualization-slicers/pbi_slicer_select.png)

## <a name="format-the-slicer"></a>슬라이서의 서식을 지정합니다.
1. 슬라이서가 선택되면 시각화 창에서 페인트 롤러 아이콘 ![](media/power-bi-visualization-slicers/power-bi-paintroller.png)을 선택하여 서식 지정 옵션을 표시합니다.
2. **일반 > 윤곽 색**을 선택하고 진한 파란색을 선택하며 **가중치**를 **6**으로 변경합니다.
   
    ![](media/power-bi-visualization-slicers/pbi_slicer_outline2.png)
3. **선택 컨트롤**에서 기본적으로 **모두 선택** 은 **해제** 이고 **단일 선택** 은 **사용**입니다. 즉 한 번에 둘 이상의 이름을 선택하려면 CTRL 키를 사용해야 합니다. **모두 선택** 을 **사용** 하고 **단일 선택** 을 **해제**합니다.
   
    ![](media/power-bi-visualization-slicers/pbi_slicer_selectioncontrols2.png)
   
   * 슬라이서에는 목록 맨 위에 **모두 선택** 옵션이 있습니다. **모두 선택** 을 설정/해제하여 모든 이름을 선택하거나 선택하지 않습니다.
   * CTRL 키를 사용하지 않고 둘 이상의 이름을 선택할 수 있습니다.
4. **항목**아래에서 텍스트 크기를 14pt로 늘립니다.  동료들이 슬라이서를 알 수 있도록 하려고 합니다.
5. 마지막으로 **글꼴 색** 을 진한 빨간색으로 설정합니다.  슬라이서의 선택되지 않은 이름에서 선택한 이름을 구분합니다.
   
    ![](media/power-bi-visualization-slicers/pbi_slicer_font2.png)
6. 슬라이서에 대해 사용 가능한 다른 옵션을 탐색합니다.

## <a name="use-the-slicer-in-a-report"></a>보고서에 슬라이서를 사용합니다.
1. 보고서 페이지에 몇 가지 추가적인 시각화를 추가하거나 [소매점 분석 샘플 보고서](sample-retail-analysis.md)를 열고 **구역 월간 판매량** 탭을 선택합니다.
   
    ![](media/power-bi-visualization-slicers/power-bi-retail-sample.png)
2. Carlos를 위해 보고서 페이지를 나눕니다. 다른 시각화 요소가 이러한 선택 항목을 반영하도록 업데이트하는 방법을 확인합니다.
   
    ![](media/power-bi-visualization-slicers/slicer2.gif)
3. 슬라이서를 구역 관리자 성을 기준으로 사전순으로 정렬합니다.  슬라이서의 오른쪽 위 모서리에 있는 줄임표(...)를 선택하고 **구역 관리자**를 선택합니다.
   
    ![](media/power-bi-visualization-slicers/pbi_slicer_sort2.png)
   
    ![](media/power-bi-visualization-slicers/pbi_slicer_sorted.png)

## <a name="control-what-effect-the-slicer-has-on-other-visuals-on-the-page"></a>페이지의 다른 시각적 개체에 대한 슬라이서의 효과를 제어합니다.
슬라이서로 보고서 페이지의 시각적 개체 중 일부를 필터링하시겠습니까?  **시각적 상호 작용** 제어를 사용하여 이를 설정합니다.

**참고**: **시각적 개체 상호 작용**이 표시되지 않는 경우 ![](media/power-bi-visualization-slicers/power-bi-slicer-visual-interactions.png) 대신 해당 아이콘을 찾아보세요. 해당 아이콘도 표시되지 않는 경우 보고서 [편집용 보기](service-reading-view-and-editing-view.md)에 있는지 확인합니다.

1. 슬라이서를 선택하여 활성 상태로 만들고 메뉴 바에서 **시각적 개체 상호 작용**을 선택합니다.
   
    ![](media/power-bi-visualization-slicers/pbi-slicer-interactions.png)
2. 필터 제어가 페이지의 다른 시각적 개체 위에 표시됩니다. 슬라이서가 시각적 개체를 필터링해야 하는 경우 **필터** 아이콘을 선택합니다.  슬라이서가 시각적 개체에 영향을 미치지 않는 경우 **없음** 아이콘을 선택합니다.
   
    ![](media/power-bi-visualization-slicers/filter-controls.png)

자세한 내용은 [Power BI 보고서의 시각적 상호 작용](service-reports-visual-interactions.md)을 참조하세요.

## <a name="considerations-and-troubleshooting-slicers-in-power-bi"></a>Power BI의 슬라이서 고려 사항 및 문제 해결
Power BI에서 슬라이서를 사용하는 경우 다음과 같이 몇 가지 제한이 있습니다.

1. 슬라이서는 입력 필드를 지원하지 않습니다.
2. 단일 슬라이서는 전체 보고서에서 사용할 수 없습니다. 단일 슬라이서는 현재 페이지에만 영향을 줍니다.
3. 슬라이서는 대시보드에 고정할 수 없습니다.
4. 슬라이서 드릴다운은 지원하지 않습니다.    
5. 슬라이서는 시각적 수준 필터를 지원하지 않습니다.

Power BI 개선 방법에 대한 아이디어가 있습니까? [아이디어 제출](https://ideas.powerbi.com/forums/265200-power-bi-ideas)

## <a name="next-steps"></a>다음 단계
 [시각화를 보고서에 추가](power-bi-report-add-visualizations-i.md)

 [Power BI의 시각화 유형](power-bi-visualization-types-for-reports-and-q-and-a.md)

 [Power BI - 기본 개념](service-basic-concepts.md)

[사용해 보세요. 무료입니다!](https://powerbi.com/)

궁금한 점이 더 있나요? [Power BI 커뮤니티를 이용하세요.](http://community.powerbi.com/)

