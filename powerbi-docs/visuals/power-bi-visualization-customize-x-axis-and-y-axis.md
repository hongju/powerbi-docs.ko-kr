---
title: X축 및 Y축 속성 사용자 지정
description: X축 및 Y축 속성 사용자 지정
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: 9DeAKM4SNJM
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 06/24/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 3bfe84acdf73fcb5ace791c9a84943262d0f73ab
ms.sourcegitcommit: 1c96b65a03ec0a0612e851dd58c363f4d56bca38
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2019
ms.locfileid: "67390126"
---
# <a name="customize-x-axis-and-y-axis-properties"></a>X축 및 Y축 속성 사용자 지정

이 자습서에서는 시각적 개체의 X축 및 Y축을 사용자 지정하는 다양한 방법을 배웁니다. 일부 시각적 개체에는 축이 없습니다. 예를 들어, 원형 차트는 축이 없습니다. 또한 사용자 지정 옵션은 시각적 개체에 따라 다릅니다. 이 문서 하나에서 다루기에는 옵션이 너무 많습니다. 따라서 가장 많이 사용되는 축 사용자 지정을 몇 개만 살펴보고, Power BI 보고서 캔버스에서 시각적 **서식** 창을 사용하는 방법을 익히도록 하겠습니다.  

> [!NOTE]
> 이 페이지는 Power BI 서비스 및 Power BI Desktop 모두에 적용됩니다. **서식**(페인트 롤러 ![페인트 롤러 아이콘 스크린샷](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-paintroller.png)) 아이콘을 선택하면 사용할 수 있는 이러한 사용자 지정 항목을 Power BI Desktop에서도 사용할 수 있습니다.

Amanda가 X축과 Y축을 사용자 지정하는 방법을 보세요. 드릴다운 및 드릴업을 사용할 때 연결을 제어하는 다양한 방법을 시연합니다.

<iframe width="560" height="315" src="https://www.youtube.com/embed/9DeAKM4SNJM" frameborder="0" allowfullscreen></iframe>

## <a name="prerequisites"></a>필수 조건

- Power BI 서비스

- 소매점 분석 샘플 보고서

## <a name="customize-visualization-x--and-y-axes-in-reports"></a>보고서의 시각화 X축 및 Y축 사용자 지정

과정을 따르려면 [Power BI 서비스](https://app.powerbi.com)에 로그인하고 [보고서 편집](../service-interact-with-a-report-in-editing-view.md)에서 [소매점 분석 샘플](../sample-datasets.md) 보고서를 엽니다.

### <a name="create-a-stacked-column-chart-visualization"></a>누적 세로 막대형 차트 시각화 만들기

시각화를 사용자 지정하려면 먼저 빌드해야 합니다.

1. Power BI 서비스에서 **내 작업 영역**을 확장합니다.

1. 아래로 스크롤하여 **데이터 세트** 목록에서 **소매점 분석 샘플**을 선택합니다.

1. **시각화** 창에서 누적 세로 막대형 차트 아이콘을 선택합니다.

    ![시각화 창 및 빈 누적 세로 막대형 차트의 스크린샷](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-stacked-column-chart.png)

1. X축 값을 설정하려면 **필드** 창에서 **시간** > **FiscalMonth**를 선택합니다.

1. Y축 값을 설정하려면 **필드** 창에서 **판매량** > **작년 판매액** 및 **판매량** > **올해 판매액** > **값**을 선택합니다.

    ![채워진 누적 세로 막대형 차트의 스크린샷](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-create-chart.png)

### <a name="customize-the-x-axis"></a>X축 사용자 지정

이제 X축을 사용자 지정할 수 있습니다.

1. **시각화** 창에서 **서식**(페인트 롤러 아이콘 ![페인트 롤러 아이콘 스크린샷](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-paintroller.png))을 선택하여 사용자 지정 옵션을 표시합니다.

1. X축 옵션을 확장합니다.

   ![X축 옵션의 스크린샷](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-x-axis.png)

1. **X축** 슬라이더를 **켜기**로 이동합니다.

    ![켜기 슬라이더의 스크린샷](media/power-bi-visualization-customize-x-axis-and-y-axis/onoffslider.png)

    추가 데이터의 공간을 절약하기 위해 X축 옵션을 해제하는 것이 좋습니다.

1. 텍스트 색, 크기 및 글꼴의 서식을 지정합니다.

    - **색**: 검정 선택

    - **텍스트 크기**: *14* 입력

    - **글꼴 제품군**: **Arial Black** 선택

1. **제목** 옵션을 **켜기**로 밀어 X축 이름을 표시합니다. 이 경우에는 **FiscalMonth**입니다.

1. 제목 텍스트 색, 크기 및 글꼴의 서식을 지정합니다.

    - **제목 색**: 주황색 선택

    - **축 제목**: ‘회계 월’ 입력 

    - **제목 텍스트 크기**: *21* 입력

사용자 지정을 완료한 후 누적 세로 막대형 차트는 다음과 같습니다.

![사용자 지정된 누적 세로 막대형 차트의 스크린샷](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-customize-axis.png)

변경 내용을 저장하고 다음 섹션으로 이동합니다.

모든 변경 내용을 되돌려야 하는 경우 **X축** 사용자 지정 창 맨 아래에 있는 **기본값으로 되돌리기**를 선택합니다.

### <a name="customize-the-y-axis"></a>Y축 사용자 지정

다음으로, Y축을 사용자 지정합니다.

1. Y축 옵션을 확장합니다.

   ![Y축 옵션의 스크린샷](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-y-axis.png)

1. **Y축** 슬라이더를 **켜기**로 이동합니다.  

    ![켜기 슬라이더의 스크린샷](media/power-bi-visualization-customize-x-axis-and-y-axis/onoffslider.png)

    추가 데이터의 공간을 절약하기 위해 Y축 옵션을 해제하는 것이 좋습니다.

1. Y축 **위치**를 **오른쪽**으로 설정합니다.

1. 텍스트 색, 크기 및 글꼴의 서식을 지정합니다.

    - **색**: 검정 선택

    - **텍스트 크기**: *14* 입력

    - **글꼴 제품군**: **Arial Black** 선택

1. **표시 단위**를 **백만**으로 설정하고 **값 소수 자릿수**를 *0*으로 설정합니다.

1. 이 시각화의 경우 Y축 제목이 있더라도 시각적 개체가 달라지지 않으므로 **제목**을 **해제**한 채로 둡니다.  

1. 색을 변경하고 스트로크를 증가시켜 눈금선을 강조하겠습니다.

    - **색**: 진한 회색 선택

    - **스트로크**: *2* 입력

이러한 사용자 지정 후 세로 막대형 차트는 이렇게 보여야 합니다.

![사용자 지정된 Y축이 있는 차트의 스크린샷](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-y-axis-complete.png)

## <a name="customizing-visualizations-with-dual-y-axes"></a>이중 Y축으로 시각화 요소 사용자 지정

먼저 상점 수가 판매액에 미치는 영향을 보여 주는 콤보 차트를 만들어 보겠습니다. 이는 [콤보 차트 자습서](power-bi-visualization-combo-chart.md)에서 만든 것과 동일한 차트입니다. 그런 다음, 이중 Y축에 서식을 지정합니다.

### <a name="create-a-chart-with-two-y-axes"></a>Y축 두 개로 차트 만들기

1. **시간 > FiscalMonth** 기준 **영업 > 작년의 총 수익률(%)** 을 추적하는 새로운 꺾은선형 차트를 만듭니다.

    ![새 꺾은선형 차트의 스크린샷](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-line-chart.png)

    > [!NOTE]
    > 월별로 정렬하기 위한 도움말은 [다른 조건을 사용하여 정렬](../consumer/end-user-change-sort.md#other)을 참조하세요.

    매상 총이익 백분율이 1월에 35%이고 4월에 45%로 최고이며 7월에 떨어졌다가 8월에 다시 최고가 되었습니다. 작년과 금년의 매출 패턴이 유사할까요?

1. **This Year Sales > Value** 및 **Last Year Sales**를 꺾은선형 차트에 추가합니다.

    ![새 데이터가 추가된 꺾은선형 차트의 스크린샷](media/power-bi-visualization-customize-x-axis-and-y-axis/flatline_new.png)

    **작년의 매상 총이익(%)** 의 눈금(**0M%** 눈금선과 함께 있는 파란색 선)은 **판매량** 눈금보다 훨씬 더 작기 때문에 비교하기가 어렵습니다. 또한 Y축 레이블 백분율도 그렇습니다.

1. 보다 쉽게 읽고 해석 가능한 시각적 개체를 만들려면 꺾은선형 차트를 꺾은선형 및 누적 세로 막대형 차트로 변환합니다.

   ![꺾은선형 차트 및 누적 세로 막대형 차트 아이콘이 호출된 시각화 창의 스크린샷](media/power-bi-visualization-customize-x-axis-and-y-axis/converttocombo_new.png)

1. **Gross Margin Last Year(%)** 을 **세로 막대 값**에서 **꺾은선형 값**으로 끌어다 놓습니다.

    ![세 값이 모두 명확하게 표현된 꺾은선형 차트 및 누적 세로 막대형 차트의 스크린샷](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-dual-axes.png)

    이제 첫 번째 섹션에서 작성한 누적 세로 막대형 차트 위에 꺾은선형 차트가 중첩됩니다. 필요한 경우 위에서 배운 내용을 사용하여 축 글꼴 색 및 크기를 지정합니다.

   ![사용자 지정된 꺾은선형 차트 및 누적 세로 막대형 차트의 스크린샷](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-dual-axes-new.png)

   Power BI에서는 데이터 세트를 서로 다르게 확장할 수 있는 두 개의 Y축을 만듭니다. 왼쪽 축은 달러를, 오른쪽 축은 백분율을 측정합니다.

### <a name="format-the-secondary-y-axis"></a>보조 Y축 서식 지정

1. **시각화** 창에서 페인트 롤러 아이콘을 선택하여 서식 옵션을 표시합니다.

1. Y축 옵션을 확장합니다.

1. **보조 표시** 옵션을 찾을 때까지 아래로 스크롤합니다. **켜기**로 설정되어 있는지 확인합니다.

   ![보조 표시 옵션의 스크린샷](media/power-bi-visualization-customize-x-axis-and-y-axis/combo3.png)

1. (선택 사항) 두 축을 사용자 지정합니다. 열 축 또는 행 축에 대한 **위치**를 전환하면 두 축은 서로의 위치를 전환합니다.

### <a name="add-titles-to-both-axes"></a>두 축에 제목 추가

이렇게 복잡한 시각화에서는 축 제목을 추가하는 것이 좋습니다.  제목은 동료들이 시각화가 전달하는 스토리를 파악하는 데 도움이 됩니다.

1. **제목**을 **Y축 (열)** 과 **Y축 (선)** 에 대해 **켜기**를 설정합니다.

1. 두 축 모두에 대해 **스타일**을 **제목만 표시**로 설정합니다.

   ![제목 및 스타일 옵션의 스크린샷](media/power-bi-visualization-customize-x-axis-and-y-axis/yaxissettings.png)

1. 이제 콤보 차트에 제목과 함께 이중 축이 표시됩니다.

   ![사용자 지정된 이중 Y축 차트의 스크린샷](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-combo-chart.png)

자세한 내용은 [Power BI의 색 서식을 위한 팁과 힌트](service-tips-and-tricks-for-color-formatting.md)를 참조하세요.

## <a name="considerations-and-troubleshooting"></a>고려 사항 및 문제 해결

보고서 소유자가 X축을 날짜 형식으로 분류하는 경우 **형식** 옵션이 표시되며 연속 또는 범주 간에 선택할 수 있습니다.

## <a name="next-steps"></a>다음 단계

- [Power BI 보고서의 시각화](power-bi-report-visualizations.md)

- [시각화 제목, 범례 및 배경 사용자 지정](power-bi-visualization-customize-title-background-and-legend.md)

- [색 서식 지정 및 축 속성 시작](service-getting-started-with-color-formatting-and-axis-properties.md)

- [Power BI 서비스 소비자를 위한 기본 개념](../consumer/end-user-basic-concepts.md)

궁금한 점이 더 있나요? [Power BI 커뮤니티를 이용하세요.](http://community.powerbi.com/)
