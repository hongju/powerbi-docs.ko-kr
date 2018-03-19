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
ms.date: 03/05/2018
ms.author: v-thepet
LocalizationGroup: Visualizations
ms.openlocfilehash: cfa4c0f17c67a036b7d01744da1b5247345c493a
ms.sourcegitcommit: 4217430c3419046c3a90819c34f133ec7905b6e7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2018
---
# <a name="slicers-in-power-bi-tutorial"></a>Power BI의 슬라이서(자습서)
영업 담당 부사장은 사업부 전체 또는 각 개별 지역 관리자에 대한 몇 가지 메트릭을 보려고 할 수도 있습니다. 각 관리자별로 별도의 보고서를 만들거나 슬라이서를 사용할 수 있습니다. 슬라이서는 보고서에서 다른 시각화에 표시된 데이터 집합의 부분을 좁힙니다. 슬라이서는 필터링의 다른 방법입니다.

이 자습서에서는 무료 [소매점 분석 샘플](sample-retail-analysis.md)을 사용하여 슬라이서를 만들고 서식을 지정하고 이를 사용하여 보고서를 필터링하는 방법을 안내합니다. 슬라이서의 서식을 지정하고 사용하는 방법을 재미있게 알아보세요. 

![슬라이서](media/power-bi-visualization-slicers/slicer2.gif)

## <a name="when-to-use-a-slicer"></a>슬라이서를 사용하는 경우
다음과 같은 경우 슬라이서를 사용하는 것이 좋습니다.

* 보고서 캔버스에서 자주 사용되거나 중요한 필터를 표시하여 더 쉽게 액세스할 수 있게 하려는 경우
* 드롭다운 목록을 열지 않고도 현재 필터링된 상태를 더 쉽게 보려는 경우 
* 데이터 테이블에서 불필요하고 숨겨진 열을 필터링하는 경우
* 중요한 시각적 개체 옆에 슬라이서를 배치하여 더 집중된 보고서를 만드는 경우

Power BI 슬라이서에는 다음과 같은 제한 사항이 있습니다.

- 슬라이서는 입력 필드를 지원하지 않습니다.
- 슬라이서는 대시보드에 고정할 수 없습니다.
- 슬라이서 드릴다운은 지원하지 않습니다.
- 슬라이서는 시각적 개체 수준 필터를 지원하지 않습니다.

## <a name="create-a-slicer"></a>슬라이서 만들기

이 자습서에서는 목록 슬라이서를 사용합니다. 숫자 및 날짜/시간 데이터 형식에는 범위 슬라이서를 사용할 수 있습니다. 범위 슬라이서를 만들고 사용하는 방법에 대한 자세한 내용은 [Power BI Desktop에서 숫자 범위 슬라이서 사용](desktop-slicer-numeric-range.md) 또는 다음 비디오를 참조하세요.
<iframe width="560" height="315" src="https://www.youtube.com/embed/zIZPA0UrJyA" frameborder="0" allowfullscreen></iframe>

1. Power BI Desktop 또는 Power BI 서비스에서는 [편집용 보기](service-interact-with-a-report-in-editing-view.md)에서 [소매점 분석 샘플](sample-retail-analysis.md)을 열고 [새 보고서 페이지를 추가](power-bi-report-add-page.md)합니다.
2. 필드 창의 구역에서 **구역 관리자**를 선택하여 새 시각화를 만듭니다.
    
    ![새 차트](media/power-bi-visualization-slicers/1-new-vis.png)
    
3. 시각화 창에서 **슬라이서** 아이콘 ![슬라이서 아이콘](media/power-bi-visualization-slicers/slicer-icon.png)을 선택하여 새 시각화를 슬라이서로 변환합니다. 
    
    ![슬라이서로 변환](media/power-bi-visualization-slicers/2-slicer.png)

또한 슬라이서 아이콘을 선택하여 새 슬라이서를 만든 다음, 데이터 필드를 선택하거나 필드 상자로 끌어서 채울 수 있습니다.

>[!TIP]
>슬라이서 항목 목록을 데이터 값별로 정렬할 수 있습니다. 슬라이서 항목을 알파벳 역순으로 정렬하려면 슬라이서의 오른쪽 위 모서리에 있는 줄임표(...)를 선택하고 **구역 관리자별로 정렬**을 선택합니다. 설정은 기본적으로 알파벳순으로 오름차순이지만 오름차순과 내림차순 간에 전환됩니다. 

## <a name="format-the-slicer"></a>슬라이서의 서식을 지정합니다.
구역 관리자 슬라이서에 시각적 개체 서식을 적용합니다.
1. 슬라이서가 선택되면 시각화 창에서 서식 아이콘 ![](media/power-bi-visualization-slicers/power-bi-paintroller.png)을 선택하여 서식 지정 컨트롤을 표시합니다. 
    
    ![서식 지정](media/power-bi-visualization-slicers/3-format.png)
    
2. 옵션을 표시하고 편집하려면 각 범주 옆에 있는 드롭다운 화살표를 클릭합니다. 

### <a name="general-options"></a>일반 옵션
1. **윤곽선 색**에서 빨간색을 선택하고 **윤곽선 두께**를 "2"로 변경합니다. 이 옵션을 사용하면 머리글 및 항목 윤곽선 또는 밑줄의 색과 두께를 설정할 수 있습니다. 
2. 방향에서 기본값은 세로이며, 이 값은 항목 앞에 선택 상자가 있는 세로 목록 슬라이서를 만듭니다. 가로로 배열된 항목이 있는 슬라이서를 생성하려면 **가로**를 선택하세요. 가로 방향은 슬라이서 크기와 모양 및 항목 서식에 따라 텍스트, 단추 또는 타일의 다양한 배치를 만들 수 있습니다. 
    
    ![가로](media/power-bi-visualization-slicers/4-horizontal.png)
    
3. **반응형** 레이아웃을 켜면 슬라이서 크기와 모양에 맞게 수평 슬라이서 항목의 크기와 배열이 변경됩니다. 매우 작은 크기에서 슬라이서는 필터 아이콘이 됩니다. 
    
    ![반응형](media/power-bi-visualization-slicers/5-responsive.png)
    
    >[!NOTE]
    >반응형 레이아웃의 변경 내용은 사용자가 설정한 특정 제목 및 항목 서식을 재정의할 수 있습니다. 
    
4. **X 위치**, **Y 위치**, **너비** 및 **높이**에서 슬라이서 위치와 크기를 숫자 정밀도로 설정하거나, 슬라이서를 캔버스에서 직접 이동하고 크기를 조정하여 가로 단추 행과 같은 다양한 항목 크기 및 배열을 생성합니다.  

    ![가로 단추](media/power-bi-visualization-slicers/6-buttons.png)

가로 방향 및 응답성이 뛰어난 서식에 대한 자세한 내용은 [Power BI에서 크기를 조정할 수 있는 응답 슬라이서 만들기](power-bi-slicer-filter-responsive.md)를 참조하세요.

### <a name="selection-controls-options"></a>선택 컨트롤 옵션
1. 모두 선택 표시는 기본적으로 꺼져 있습니다. 모든 항목을 선택하거나 선택 취소하는 모두 선택 항목을 슬라이서에 추가하려면 **켜기**로 전환하세요. 모든 항목이 선택되어 있을 때 한 항목을 클릭하면 선택이 취소되고 "is-not" 형식의 필터가 허용됩니다. 
    
    ![모두 선택](media/power-bi-visualization-slicers/7-select-all.png)
    
2. 단일 선택은 기본적으로 켜져 있습니다. 각 항목을 클릭하면 항목이 선택되고 Ctrl 키를 누른 채로 클릭하면 여러 항목이 선택됩니다. Ctrl 키를 누르지 않고 여러 항목을 선택할 수 있게 하려면 단일 선택을 **끄기**로 전환하세요. 각 항목을 다시 클릭하면 선택이 취소됩니다. 

### <a name="header-options"></a>헤더 옵션
헤더는 기본적으로 켜져 있으므로 슬라이서 위쪽에 데이터 필드 이름이 표시됩니다. 
1. 헤더 텍스트의 서식을 지정하여 **글꼴 색**을 빨강으로, **텍스트 크기**를 14pt로, **글꼴 패밀리**를 Arial Black으로 설정합니다. 
2. 윤곽 아래에서 일반 옵션에서 설정한 크기와 색상으로 밑줄을 표시하려면 **아래쪽만**을 선택하세요. 

### <a name="item-options"></a>항목 옵션
1. 항목 텍스트와 배경의 서식을 지정하여 **글꼴 색**을 검정으로, **배경**을 연한 빨강으로, **텍스트 크기**를 10pt로, **글꼴 패밀리**를 Arial로 설정합니다. 
2. 윤곽에서 **프레임**을 선택하여 일반 옵션에서 설정한 크기와 색상으로 각 항목 둘레에 테두리를 그립니다. 
    
    ![서식 지정](media/power-bi-visualization-slicers/8-formatted.png)
    
    >[!TIP]
    >- 가로 방향을 사용하면 선택 취소된 항목이 선택된 텍스트와 배경색으로 표시되고, 선택된 항목은 시스템 기본값(일반적으로 흰색 텍스트의 검은 배경)으로 표시됩니다. 
    >- 세로 방향을 사용하면 항목이 항상 설정된 색상으로 표시되고 선택 상자는 선택 시 항상 검은색으로 표시됩니다. 

### <a name="other-formatting-options"></a>다른 서식 지정 옵션
다른 서식 지정 옵션은 기본적으로 꺼져 있습니다. **켜기**로 전환할 경우: 
- **제목:** 슬라이서의 맨 위에 (헤더와 별개이고 독립적인) 제목을 추가하고 서식을 지정합니다. 
- **배경:** 전체 슬라이서에 배경색을 추가하고 투명도를 설정합니다.
- **가로 세로 비율 잠금:** 슬라이서의 크기가 조정된 경우 슬라이서의 모양을 유지합니다.
- **테두리:** 슬라이서 둘레에 1픽셀 테두리를 추가하고 색을 설정합니다. (이 슬라이서 테두리는 일반 윤곽 설정과 별개이며 영향을 받지 않습니다.) 

## <a name="sync-and-use-the-slicer-on-other-pages"></a>다른 페이지에서 슬라이서 동기화 및 사용
2018년 2월 Power BI 업데이트부터 보고서의 일부 또는 모든 페이지에서 슬라이서를 동기화하여 사용할 수 있습니다. 
1. 구역 관리자 슬라이서를 선택한 후 보기 메뉴에서 Power BI Desktop의 **슬라이서 동기화**를 선택하거나, Power BI 서비스의 **슬라이서 동기화 창**을 켭니다. 슬라이서 동기화 창이 나타납니다. 
    
    ![슬라이서 동기화](media/power-bi-visualization-slicers/9-sync-slicers.png)
    
2. 첫 번째 열에서 **개요** 및 슬라이서를 동기화할 다른 페이지를 선택하거나 **모든 항목에 추가**를 클릭하여 슬라이서를 모든 보고서 페이지에 동기화합니다.  
3. 다음 열에서 **개요** 및 슬라이서를 표시할 다른 페이지를 선택하세요. 
4. **개요** 페이지로 전환하고 슬라이서와 다른 페이지의 시각적 개체에 미치는 영향을 확인합니다. 
    - 다른 항목을 선택하고 제거한 다음, 페이지의 다른 시각적 개체가 그에 따라 어떻게 변하는지 확인합니다.  모든 페이지의 항목 선택은 모든 동기화된 페이지에 반영됩니다.
    - 개요 페이지에서 슬라이서의 크기, 모양, 위치 및/또는 서식을 변경하세요. 다른 동기화된 페이지의 슬라이서 서식은 변경되지 않습니다. 

### <a name="control-which-page-visuals-are-affected-by-the-slicer"></a>슬라이서의 영향을 받는 페이지 시각적 개체 제어
기본적으로 보고서 페이지의 슬라이서는 해당 페이지의 다른 모든 시각화에 영향을 줍니다. **시각적 상호 작용**을 사용하여 일부 페이지 시각화가 영향을 받지 않도록 하세요.

1. **개요** 페이지에서 슬라이서를 선택합니다.
    - Power BI Desktop에서 시각적 개체 도구 아래의 서식 메뉴를 클릭하고 **상호 작용 편집**을 선택합니다.
    - Power BI 서비스에서 메뉴 모음의 **시각적 상호 작용**을 드롭다운하고 **상호 작용 편집**을 켭니다. 
    
    필터 컨트롤은 페이지의 다른 모든 시각적 개체 위에 표시됩니다. ![필터 컨트롤](media/power-bi-visualization-slicers/filter-controls.png)
    
2. 시각적 개체 위의 **없음** 아이콘을 선택하면 슬라이서가 필터링을 중지합니다. 슬라이서가 시각적 개체 필터링을 다시 시작하게 하려면 **필터** 아이콘을 선택하세요. 

상호 작용 편집에 대한 자세한 내용은 [Power BI 보고서의 시각적 상호 작용](service-reports-visual-interactions.md)을 참조하세요.

## <a name="next-steps"></a>다음 단계
[사용해 보세요. 무료입니다!](https://powerbi.com/)

Power BI 개선 방법에 대한 아이디어가 있습니까? [아이디어 제출](https://ideas.powerbi.com/forums/265200-power-bi-ideas)

궁금한 점이 더 있나요? [Power BI 커뮤니티를 이용하세요.](http://community.powerbi.com/)

[시각화를 보고서에 추가](power-bi-report-add-visualizations-i.md)

[Power BI의 시각화 유형](power-bi-visualization-types-for-reports-and-q-and-a.md)

[Power BI - 기본 개념](service-basic-concepts.md)

