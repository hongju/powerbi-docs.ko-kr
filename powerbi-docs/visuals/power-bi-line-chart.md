---
title: Power BI의 꺾은선형 차트
description: Power BI의 꺾은선형 차트
author: mihart
manager: kvivek
ms.reviewer: amac
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 06/26/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 4b2c7c237393fd0a8e76b7ca27987c479b5c411d
ms.sourcegitcommit: 58c649ec5fd2447a0f9ca4c4d45a0e9fff2f1b6a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2019
ms.locfileid: "67408608"
---
# <a name="line-charts-in-power-bi"></a>Power BI의 꺾은선형 차트
꺾은선형 차트는 점으로 표시되고 직선으로 연결되는 일련의 데이터 요소입니다. 꺾은선형 차트에는 하나 이상의 선이 있을 수 있습니다. 꺾은선형 차트에는 X축과 Y축이 있습니다. 

![간단한 꺾은선형 차트](media/power-bi-line-charts/power-bi-line.png)

## <a name="create-a-line-chart"></a>꺾은선형 차트 만들기
이러한 지침에서는 영업 및 마케팅 샘플 앱을 사용하여 올해의 판매액을 범주별로 표시하는 꺾은선형 차트를 만듭니다. 이를 따르려면 appsource.com에서 샘플 앱을 받으세요.

1. 빈 보고서 페이지에서 시작합니다. Power BI 서비스를 사용하는 경우 [편집용 보기](../service-interact-with-a-report-in-editing-view.md)에서 보고서를 엽니다.

2. 필드 창에서 **SalesFact** \> **전체 단위**를 선택하고 **날짜** > **월**을 선택합니다.  Power BI는 보고서 캔버스에 세로 막대형 차트를 만듭니다.

    ![필드 창에서 선택](media/power-bi-line-charts/power-bi-step1.png)

4. 시각화 창에서 꺾은선형 차트 템플릿을 선택하여 꺾은선형 차트로 변환합니다. 

    ![꺾은선형 차트로 변환](media/power-bi-line-charts/power-bi-convert-to-line.png)
   

4. 꺾은선형 차트를 필터링하여 연도 2012-2014에 대한 데이터를 표시합니다. 필터 창이 축소된 경우 지금 확장합니다. 필드 창에서 **날짜** \> **연도**를 선택하고 필터 창으로 끌어 **이 시각적 개체의 필터** 머리글 아래에 놓습니다. 
     
    ![필드 창 옆의 선](media/power-bi-line-charts/power-bi-year-filter.png)

    **고급 필터**를 **기본 필터**로 변경하고 **2012**, **2013** 및 **2014**를 선택합니다.

    ![연도 필터](media/power-bi-line-charts/power-bi-filter-year.png)

6. 필요에 따라 [차트 텍스트의 크기와 색을 조정](power-bi-visualization-customize-title-background-and-legend.md)합니다. 

    ![글꼴 크기 늘리기 및 Y축 글꼴 변경](media/power-bi-line-charts/power-bi-line-3years.png)

## <a name="add-additional-lines-to-the-chart"></a>차트에 선 추가
꺾은선형 차트에는 다수의 선이 있을 수 있습니다. 또한 일부 경우에는 선의 값이 매우 다양하고 함께 잘 표시되지 않을 수도 있습니다. 현재 차트에 선을 더 추가한 후 살펴보면서 선이 표시하는 값이 매우 다를 때 차트의 서식을 지정하는 방법을 알아보세요. 

### <a name="add-additional-lines"></a>선 추가
모든 지역의 전체 단위를 차트상의 단일 선으로 살펴보는 대신 전체 단위를 지역별로 분할해 보겠습니다. **지역** > **지역**을 범례 웰로 끌어 선을 추가합니다.

   ![각 지역에 대해 선 하나](media/power-bi-line-charts/power-bi-line-regions.png)


### <a name="use-two-y-axes"></a>두 개의 Y축 사용
총판매액 및 총 단위를 동일한 차트에서 보려는 경우 어떻게 해야 할까요? 판매 수치는 단위 수보다 훨씬 더 높으므로, 꺾은선형 차트를 사용할 수 없게 됩니다. 실제로 전체 단위에 해당하는 빨간 선은 0으로 표시됩니다.

   ![고도로 분산된 값](media/power-bi-line-charts/power-bi-diverging.png)

고도로 분산된 값을 하나의 차트에 표시하려면 콤보 차트를 사용합니다. [Power BI의 콤보 차트](power-bi-visualization-combo-chart.md)를 읽어 보면 콤보 차트에 대해 모두 알아볼 수 있습니다. 아래 예에서 두 번째 Y축을 추가하여 하나의 차트에 판매량 및 전체 단위를 함께 표시할 수 있습니다. 

   ![고도로 분산된 값](media/power-bi-line-charts/power-bi-dual-axes.png)

## <a name="highlighting-and-cross-filtering"></a>강조 표시 및 교차 필터링
필터 창 사용 방법에 대한 자세한 내용은 [보고서에 필터 추가](../power-bi-report-add-filter.md)를 참조하세요.

꺾은선형 차트에서 데이터 요소를 선택하면 보고서 페이지의 다른 시각화 요소가 교차 강조 표시 및 교차 필터링되며 그 반대의 경우도 마찬가지입니다. 과정을 따르려면 **시장 점유율** 탭을 엽니다.  

꺾은선형 차트에서 단일 데이터 요소는 X축과 Y축의 지점 간의 교차점입니다. 데이터 요소를 선택하면 Power BI는 보고서 페이지의 다른 시각적 개체의 교차 강조 표시 및 교차 필터링에 대한 소스인 단일 지점(단일 선) 또는 여러 지점(선이 두 개 이상 있는 경우)을 나타내는 표식을 추가합니다. 시각적 개체가 밀도가 높은 경우 Power BI는 시각적 개체를 클릭하는 위치와 가장 가까운 지점을 선택합니다.

이 예에서는 다음을 포함하는 데이터 요소를 선택했습니다. 2014년 7월, % 단위의 시장 점유율 R12 = 33.16, % 단위의 시장 점유율= 34.74.

![꺾은선형 차트에서 단일 데이터 요소 선택](media/power-bi-line-charts/power-bi-single-select.png)

세로 막대형 차트가 교차 강조 표시되고 계기가 교차 필터링되는 방식을 확인합니다.

차트를 상호 간에 강조 표시하고 필터링하는 방법을 관리하려면 [Power BI 보고서의 시각화 상호 작용](../service-reports-visual-interactions.md)을 참조하세요.

## <a name="considerations-and-troubleshooting"></a>고려 사항 및 문제 해결
* 하나의 꺾은선형 차트에 이중 Y축이 있을 수 없습니다.  대신 콤보 차트를 사용해야 합니다.
* 위의 예에서 차트는 글꼴 크기를 늘리고, 글꼴 색을 변경하고, 축 제목을 추가하고, 차트 제목 및 범례를 가운데로 배치하고, 두 축을 모두 0에서 시작하도록 서식 지정되었습니다. 서식 지정 창(페인트 롤러 아이콘)에는 차트를 원하는 방식으로 만드는 옵션 세트가 매우 많습니다. 알아볼 수 있는 가장 좋은 방법은 서식 지정 창을 열고 탐색하는 것입니다.

## <a name="next-steps"></a>다음 단계

[Power BI의 시각화 유형](power-bi-visualization-types-for-reports-and-q-and-a.md)


