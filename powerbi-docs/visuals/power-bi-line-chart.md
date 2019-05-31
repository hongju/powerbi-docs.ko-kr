---
title: Power BI에서 꺾은선형 차트
description: Power BI에서 꺾은선형 차트
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/07/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 0654dccf55b1e13f26d8ecaabee0349f0e56afc6
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "65535793"
---
# <a name="line-charts-in-power-bi"></a>Power BI에서 꺾은선형 차트
꺾은선형 차트는 일련의 점으로 표시 되 고 직선으로 연결 하는 데이터 요소입니다. 꺾은선형 차트를 하나 또는 여러 줄에 있을 수 있습니다. 꺾은선형 차트에는 X 및 Y 축에 있습니다. 

![간단한 꺾은선형 차트](media/power-bi-line-charts/power-bi-line.png)

## <a name="create-a-line-chart"></a>꺾은선형 차트를 만듭니다
이러한 명령 사용 하 여 판매 및 마케팅 샘플 앱 올해의 판매액을 범주별으로 표시 하는 꺾은선형 차트를 만듭니다. 자습서에 따라 appsource.com에서 샘플 앱을 가져옵니다.

1. 빈 보고서 페이지에서 시작합니다. Power BI 서비스를 사용하는 경우 [편집용 보기](../service-interact-with-a-report-in-editing-view.md)에서 보고서를 엽니다.

2. 필드 창에서 선택 **SalesFact** \> **총 단위**를 선택 하 고 **날짜** > **월**합니다.  Power BI 보고서 캔버스에 세로 막대형 차트를 만듭니다.

    ![필드 창에서 선택](media/power-bi-line-charts/power-bi-step1.png)

4. 시각화 창에서 선 차트 서식 파일을 선택 하 여 꺾은선형 차트로 변환 합니다. 

    ![꺾은선형 차트로 변환](media/power-bi-line-charts/power-bi-convert-to-line.png)
   

4. 2012-2014 년에 대 한 데이터를 표시 하도록 꺾은선형 차트를 필터링 합니다. 필터 창에 축소 되어 있으면 확장 이제 합니다. 필드 창에서 선택 **날짜** \> **연도** 필터 창으로 끌어 옵니다. 제목 아래에 놓습니다 **이 시각적 개체에 대 한 필터**합니다. 
     
    ![필드 창 옆에 있는 줄](media/power-bi-line-charts/power-bi-year-filter.png)

    변경 **고급 필터** 하 **기본 필터** 선택한 **2012**, **2013** 하 고 **2014**합니다.

    ![연도 대 한 필터](media/power-bi-line-charts/power-bi-filter-year.png)

6. 필요에 따라 [차트 텍스트의 크기와 색을 조정](power-bi-visualization-customize-title-background-and-legend.md)합니다. 

    ![글꼴 크기를 늘리고 Y axisfont 변경](media/power-bi-line-charts/power-bi-line-3years.png)

## <a name="add-additional-lines-to-the-chart"></a>차트에 추가 줄을 추가 합니다.
꺾은선형 차트를 다른 줄 수 있습니다. 및 일부 경우에는 줄에서 값을 함께 표시 안 함 분기 될 수 있습니다. 이 현재 줄 추가 차트 및 선으로 표시 값이 매우 다른 경우 차트 서식을 지정 하는 방법을 알아봅니다 추가에 대해 살펴보겠습니다. 

### <a name="add-additional-lines"></a>줄을 추가
대신 차트에서 한 줄으로 모든 지역에 대 한 월별 총 단위를 살펴보면, 지역별 총 단위 분할 해 보겠습니다. 드래그 하 여 줄을 추가 **지리적** > **지역** 범례 웰에 있습니다.

   ![각 지역에 대해 한 줄](media/power-bi-line-charts/power-bi-line-regions.png)


### <a name="use-two-y-axes"></a>두 개의 Y 축 사용 합니다.
총 판매액 및 총 단위 동일한 차트에 어떻게 해야 할까요? 판매량 단위 번호, 꺾은선형 차트를 사용할 수 없게 비해 훨씬 높습니다. 사실, 0 총 단위에 대 한 빨간색 선이 나타납니다.

   ![항상 수렴 하는 값](media/power-bi-line-charts/power-bi-diverging.png)

에 하나의 차트에서 항상 분기 값을 표시 하려면 콤보 차트를 사용 합니다. 참조 하 여 콤보 차트에 대 한 모든 알아보십시오 [Power BI의 콤보 차트](power-bi-visualization-combo-chart.md)합니다. 아래 예에서에서는 표시할 수 있습니다 판매 및 총 단위 함께 하는 하나의 차트에 보조 Y 축을 추가 하 여. 

   ![항상 수렴 하는 값](media/power-bi-line-charts/power-bi-dual-axes.png)

## <a name="considerations-and-troubleshooting"></a>고려 사항 및 문제 해결
* 꺾은선형 차트를 하나의 이중 Y 축에 사용할 수 없습니다.  콤보 차트를 대신 사용 해야 합니다.
* 위의 예제에서 차트는 글꼴 크기 크게, 글꼴 색을 변경, 축 제목을 추가, 차트 제목 및 범례 center, 양쪽 축 0 등에 시작 형식이 지정 되었습니다. 서식 창 (페인트 롤러 아이콘) 끊임 집합이 차트 생김 하기를 원하는 방식으로 만들기 위한 옵션입니다. 가장 좋은 방법은 서식 창을 열고 탐색 하는 경우

## <a name="next-steps"></a>다음 단계

[Power BI의 시각화 유형](power-bi-visualization-types-for-reports-and-q-and-a.md)


