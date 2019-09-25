---
title: Power BI의 방사형 계기 차트
description: Power BI의 방사형 계기 차트
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: xmja6Epqa
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 06/24/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 8b0db9aebe72d54aa464ec012e614ae0ec5bc723
ms.sourcegitcommit: 1c96b65a03ec0a0612e851dd58c363f4d56bca38
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2019
ms.locfileid: "67390412"
---
# <a name="radial-gauge-charts-in-power-bi"></a>Power BI의 방사형 계기 차트

방사형 계기 차트는 원호 형태로 목표에 대한 진행률 또는 KPI(핵심 성과 지표)를 측정하는 단일 값을 표시합니다. 선(또는 ‘바늘’)은 목표 또는 대상 값을 나타냅니다.  음영은 목표에 대한 진행률을 나타냅니다. 호 내부의 값은 진행률 값을 나타냅니다. Power BI에서 모든 가능한 값을 최소(맨 왼쪽 값)에서 최대(맨 오른쪽 값)까지 호를 따라 균등하게 분배합니다.

![방사형 계기의 스크린샷](media/power-bi-visualization-radial-gauge-charts/gauge_m.png)

이 예에서는 월별 판매 팀의 평균 판매량을 추적하는 자동차 소매업체입니다. 바늘은 140대 판매 목표를 나타냅니다. 가능한 최소 평균 판매량은 0이고 최대는 200입니다.  파란색 음영은 팀이 이번 달에 평균 약 120대를 판매한 상태임을 나타냅니다. 다행히 목표에 도달할 수 있는 또 다른 한 주가 아직 남아있습니다.

Will이 단일 메트릭 시각적 개체: 계기, 카드 및 KPI를 만드는 방법을 보여 주는 과정을 봅니다.

<iframe width="560" height="315" src="https://www.youtube.com/embed/xmja6EpqaO0?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

## <a name="when-to-use-a-radial-gauge"></a>방사형 계기를 사용하는 경우

방사형 계기는 다음에 매우 적합합니다.

* 목표 진행률을 표시합니다.

* KPI와 같은 백분위수 측정값을 표시합니다.

* 단일 측정값의 상태를 표시합니다.

* 빠르게 훑어보고 이해할 수 있는 정보를 표시합니다.

## <a name="prerequisites"></a>필수 조건

* Power BI 서비스 또는 Power BI Desktop

* 재무 샘플 Excel 통합 문서: [샘플을 직접 다운로드합니다](http://go.microsoft.com/fwlink/?LinkID=521962).

## <a name="create-a-basic-radial-gauge"></a>기본 방사형 계기 만들기

이러한 지침에서는 Power BI 서비스를 사용합니다. 지침을 따르려면 Power BI에 로그인하고 Excel 재무 샘플 파일을 엽니다.

### <a name="step-1-open-the-financial-sample-excel-file"></a>1단계: 재무 샘플 Excel 파일 열기

1. 아직 다운로드하지 않았으면 [재무 샘플 Excel 파일](../sample-financial-download.md)을 다운로드합니다. 파일을 어디에 저장했는지 기억해야 합니다.

1. Power BI 서비스에서 **데이터 가져오기** > **파일**을 선택합니다.

1. **로컬 파일**을 선택하고 샘플 파일의 위치를 찾습니다.

1. **가져오기**를 선택합니다. Power BI에서 작업 영역 탐색 창에 재무 샘플을 데이터 세트로 추가합니다.

1. **데이터 세트** 콘텐츠 목록에서 **재무 샘플**에 대한 **보고서 만들기** 아이콘을 선택합니다.

    ![재무 샘플에 대한 보고서 생성 아이콘을 가리키는 화살표가 있는 데이터 세트 목록의 스크린샷](media/power-bi-visualization-radial-gauge-charts/power-bi-dataset.png)

### <a name="step-2-create-a-gauge-to-track-gross-sales"></a>2단계: 총 매출을 추적하는 계기 만들기

마지막 섹션에서 **보고서 만들기** 아이콘을 선택하여 Power BI에서 편집용 보기에 빈 보고서를 만들었습니다.

1. **필드** 창에서 **총매출액**을 선택합니다.

   ![](media/power-bi-visualization-radial-gauge-charts/grosssalesvalue_new.png)

1. 집계를 **평균**으로 변경합니다.

   ![총매출액 및 평균 집계가 호출된 필드 창의 스크린샷](media/power-bi-visualization-radial-gauge-charts/changetoaverage_new.png)

1. 계기 아이콘 ![계기 아이콘의 스크린샷](media/power-bi-visualization-radial-gauge-charts/gaugeicon_new.png) 을 선택하여 세로 막대형 차트를 계기 차트로 변환합니다.

    ![계기 차트의 스크린샷](media/power-bi-visualization-radial-gauge-charts/gauge_no_target.png)

    **재무 샘플** 파일을 다운로드하는 시점에 따라 이러한 수치와 일치하지 않는 숫자가 표시될 수 있습니다.

    > [!TIP]
    > 기본적으로 Power BI는 현재 값(이 경우, **평균 총매출액**)이 계기에 중간 지점으로 간주되는 계기 차트를 만듭니다. **평균 총매출액** 값이 $182.76K이므로 시작 값(최소)은 0으로 설정하고 끝 값(최대)은 현재 값의 두 배로 설정됩니다.

### <a name="step-3-set-a-target-value"></a>3단계: 대상 값 설정

1. **필드** 창에서 **대상 값**으로 **COGS**를 끕니다.

1. 집계를 **평균**으로 변경합니다.

   Power BI가 바늘을 추가하여 대상 값이 **$145.48K**임을 나타냅니다.

   ![COGS의 평균이 추가된 계기 차트의 스크린샷](media/power-bi-visualization-radial-gauge-charts/gaugeinprogress_new.png)

    목표를 초과 했음을 알 수 있습니다.

   > [!NOTE]
   > 대상 값을 수동으로 입력할 수도 있습니다. [수동 서식 옵션을 사용하여 최솟값, 최댓값 및 대상 값 설정](#use-manual-format-options-to-set-minimum-maximum-and-target-values) 섹션을 참조하세요.

### <a name="step-4-set-a-maximum-value"></a>4단계: 최대값 설정

2단계에서 Power BI는 **값** 필드를 사용하여 최솟값과 최댓값을 자동으로 설정했습니다. 사용자가 스스로 최댓값을 설정하려는 경우 어떻게 해야 할까요? 가능한 최댓값으로 현재 값을 두 배로 사용하는 대신, 데이터 세트에서 가장 높은 총매출액 수로 설정하는 것을 가정해 보겠습니다.

1. **필드** 창에서 **최대값**으로 **총매출액**을 끕니다.

1. 집계를 **최대값**으로 변경합니다.

   ![총매출액 및 최대 집계가 호출된 필드 창의 스크린샷](media/power-bi-visualization-radial-gauge-charts/setmaximum_new.png)

   계기는 총 판매량이 새 끝 값인 121만으로 다시 그려집니다.

   ![완료된 계기 차트의 스크린샷](media/power-bi-visualization-radial-gauge-charts/power-bi-final-gauge.png)

### <a name="step-5-save-your-report"></a>5단계: 보고서 저장

1. [보고서를 저장합니다](../service-report-save.md).

1. [대시보드 타일로 계기 차트를 추가합니다](../service-dashboard-pin-tile-from-report.md). 

## <a name="use-manual-format-options-to-set-minimum-maximum-and-target-values"></a>수동 서식 옵션을 사용하여 최솟값, 최댓값 및 대상 값 설정

1. **최대값**에서 **최대 총 판매량**을 제거합니다.

1. 페인트 롤러 아이콘을 선택하여 **서식** 창을 엽니다.

   ![계기 차트 및 페인트 롤러 아이콘이 호출된 서식 창의 스크린샷](media/power-bi-visualization-radial-gauge-charts/power-bi-roller.png)

1. **게이지 축**을 확장하고 **최소값** 및 **최대값**에 값을 입력합니다.

    ![게이지 축 옵션의 스크린샷](media/power-bi-visualization-radial-gauge-charts/power-bi-gauge-axis.png)

1. **필드** 창에서 **COGS** 옵션을 선택 취소하여 대상 값을 제거합니다.

    ![선택 취소한 COGS 옵션의 스크린샷](media/power-bi-visualization-radial-gauge-charts/pbi_remove_target.png)

1. **대상** 필드가 **게이지 축**아래에 나타나는 경우 값을 입력합니다.

     ![대상이 호출된 게이지 축 옵션의 스크린샷](media/power-bi-visualization-radial-gauge-charts/power-bi-gauge-target.png)

1. 필요에 따라 계기 차트 서식 지정을 계속합니다.

이러한 단계를 완료하면 다음과 같은 모양의 계기 차트가 나옵니다.

![최종 계기 차트의 스크린샷](media/power-bi-visualization-radial-gauge-charts/power-bi-final.png)

## <a name="next-step"></a>다음 단계

* [KPI(핵심 성과 지표) 시각적 개체](power-bi-visualization-kpi.md)

* [Power BI의 시각화 유형](power-bi-visualization-types-for-reports-and-q-and-a.md)

궁금한 점이 더 있나요? [Power BI 커뮤니티를 이용하세요.](http://community.powerbi.com/)
