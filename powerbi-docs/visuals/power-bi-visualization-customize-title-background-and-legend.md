---
title: Power BI 시각화 서식 지정 시작
description: 시각화 제목, 배경 및 범례 사용자 지정
author: mihart
ms.reviewer: ''
featuredvideoid: IkJda4O7oGs
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 12/04/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 1e2465273368c6b76e602e5ffbdf4ec3a1d121a3
ms.sourcegitcommit: 8e3d53cf971853c32eff4531d2d3cdb725a199af
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "75757834"
---
# <a name="customize-visualization-titles-backgrounds-and-legends"></a>시각화 제목, 배경 및 범례 사용자 지정

이 자습서에서는 시각화를 사용자 지정하는 몇 가지 방법을 알아봅니다. 시각화를 사용자 지정하는 많은 옵션이 있습니다. 모든 옵션에 대해 자세히 알아볼 가장 좋은 방법은 **서식** 창을 탐색하는 것입니다(페인트 롤러 아이콘 선택). 시작하기 위해 이 문서는 시각화 제목, 범례, 배경을 사용자 지정하고 테마를 추가하는 방법을 보여 줍니다.

시각화 중 일부는 사용자 지정할 수 없습니다. 자세한 내용은 시각화 [전체 목록](#visualization-types-that-you-can-customize)을 참조하세요.


## <a name="prerequisites"></a>필수 조건

- Power BI 서비스 또는 Power BI Desktop

- 소매점 분석 샘플 보고서

## <a name="customize-visualization-titles-in-reports"></a>보고서의 시각화 제목 사용자 지정

이를 수행하려면 Power BI Desktop에 로그인하고 [소매점 분석 샘플](../sample-datasets.md) 보고서를 엽니다.

> [!NOTE]
> 시각화를 대시보드에 고정하면 대시보드 타일이 됩니다. 타일 자체를 [새 제목 및 부제, 하이퍼링크로 사용자 지정하고 크기를 조정](../service-dashboard-edit-tile.md)할 수도 있습니다.

1. **소매점 분석 샘플** 보고서의 **새 상점** 페이지로 이동합니다.

1. **개업 월별 및 체인별 오픈 매장 수** 묶은 세로 막대형 차트를 선택합니다.

1. **시각화** 창에서 페인트 롤러 아이콘을 선택하여 서식 옵션을 표시합니다.

1. **제목**을 선택하여 해당 섹션을 확장합니다.

   ![페인트 롤러 아이콘이 호출되고 제목 드롭다운을 가리키는 화살표가 있는, 서식 창의 스크린샷](media/power-bi-visualization-customize-title-background-and-legend/power-bi-format-menu.png)

1. **제목** 슬라이더를 **켜기**로 이동합니다.

1. 제목을 변경하려면 **제목 텍스트** 필드에 ‘월별 개업 매장 수’를 입력합니다. 

    ![제목 텍스트가 입력된 서식 창의 스크린샷](media/power-bi-visualization-customize-title-background-and-legend/power-bi-title.png)

1. **글꼴 색**을 흰색으로 변경하고 **배경색**을 파란색으로 변경합니다.    

    a. 드롭다운을 선택하고 **테마 색**, **최근에 사용한 색**또는 **사용자 지정 색**에서 색을 선택합니다.

        ![Screenshot of the Font color and Background color options.](media/power-bi-visualization-customize-title-background-and-legend/power-bi-color.png)

    b. 색 창을 닫으려면 드롭다운을 선택합니다.


1. 텍스트 크기를 **16pt**로 늘립니다.

1. 차트 제목에 대한 마지막으로 사용자 지정 작업은 시각화의 가운데에 정렬하는 것입니다.

    ![가운데 옵션이 선택된 맞춤 컨트롤의 스크린샷](media/power-bi-visualization-customize-title-background-and-legend/power-bi-align.png)

    자습서의 이 시점에서 묶은 세로 막대형 차트 제목은 다음과 같습니다.

    ![새로 구성된 묶은 세로 막대형 차트의 스크린샷](media/power-bi-visualization-customize-title-background-and-legend/power-bi-table.png)

변경 내용을 저장하고 다음 섹션으로 이동합니다.

모든 변경 내용을 되돌려야 하는 경우 **제목** 사용자 지정 창 맨 아래에 있는 **기본값으로 되돌리기**를 선택합니다.

![기본으로 되돌리기 옵션의 스크린샷](media/power-bi-visualization-customize-title-background-and-legend/power-bi-revert.png)

## <a name="customize-visualization-backgrounds"></a>시각화 배경 사용자 지정

동일한 묶은 세로 막대형 차트를 선택한 상태로 **배경** 옵션을 확장합니다.

1. **배경** 슬라이더를 **켜기**로 이동합니다.

1. 드롭다운을 선택하고 회색을 선택합니다.

1. **투명도**를 **74%** 로 변경합니다.

자습서의 이 시점에서 묶은 세로 막대형 차트 배경은 다음과 같습니다.

![배경색이 업데이트된 묶은 세로 막대형 차트의 스크린샷](media/power-bi-visualization-customize-title-background-and-legend/power-bi-background.png)

변경 내용을 저장하고 다음 섹션으로 이동합니다.

모든 변경 내용을 되돌려야 하는 경우 **배경** 사용자 지정 창 맨 아래에 있는 **기본값으로 되돌리기**를 선택합니다.

## <a name="customize-visualization-legends"></a>시각화 범례 사용자 지정

1. **Overview** 보고서 페이지를 열고 **회계 월 및 구역 관리자별 총판매액 차이** 차트를 선택합니다.

1. **시각화** 탭에서 페인트 롤러 아이콘을 선택하여 서식 창을 엽니다.

1. **범례** 옵션을 확장합니다.

    ![범례 카드의 스크린샷](media/power-bi-visualization-customize-title-background-and-legend/power-bi-legends.png)

1. **범례** 슬라이더를 **켜기**로 이동합니다.

1. 범례를 시각화의 왼쪽으로 이동합니다.

1. **제목**을 **켜기**로 전환하여 범례 제목을 추가합니다.

1. **범례 이름** 필드에 *관리자*를 입력합니다.

1. **색**을 검은색으로 변경합니다.

변경 내용을 저장하고 다음 섹션으로 이동합니다.

모든 변경 내용을 되돌려야 하는 경우 **범례** 사용자 지정 창 맨 아래에 있는 **기본값으로 되돌리기**를 선택합니다.

## <a name="customize-colors-using-a-theme"></a>테마를 사용하여 색 사용자 지정

보고서 테마를 사용하여 전체 보고서에 디자인 변경 내용을 적용할 수 있습니다. 예를 들어, 회사 색을 사용하거나 아이콘 세트를 변경하거나 새로운 기본 시각적 서식을 적용할 수 있습니다. 보고서 테마를 적용하면 보고서의 모든 시각적 개체는 선택한 테마의 색과 서식을 사용합니다.

보고서에 테마를 적용하려면 메뉴 모음에서 **테마 전환**을 선택합니다. 테마를 선택합니다.  아래 보고서는 **태양** 테마를 사용합니다.

 
![노란색, 주황색, 빨간색으로 된 태양 테마를 사용하는 보고서](media/power-bi-visualization-customize-title-background-and-legend/power-bi-theme.png)

## <a name="visualization-types-that-you-can-customize"></a>사용자 지정할 수 있는 시각화 유형

다음은 각 항목에 사용할 수 있는 시각화 및 사용자 지정 옵션의 목록입니다.

| 시각화 | 제목 | 배경 | 범례 |
|:--- |:--- |:--- |:--- |
| 영역 | 예 | 예 |예 |
| 막대형 | 예 | 예 |예 |
| 카드 | 예 | 예 |해당 없음 |
| 여러 행 카드 | 예 | 예 | 해당 없음 |
| 열 | 예 | 예 | 예 |
| 콤보 | 예 | 예 | 예 |
| 도넛 | 예 | 예 | 예 |
| 등치 지역도 | 예 | 예 | 예 |
| 깔때기형 | 예 | 예 | 해당 없음 |
| 계기 | 예 | 예 | 해당 없음 |
| 주요 영향 요인 | 예 | 예 | 해당 없음 |
| KPI | 예 | 예 | 해당 없음 |
| 선 | 예 | 예 | 예 |
| 맵 | 예 | 예 | 예 |
| Matrix | 예 | 예 | 해당 없음 |
| 원형 | 예 | 예 | 예 |
| 질문 및 답변 | 예 | 예 | 해당 없음 |
| 분산형 | 예 | 예 | 예 |
| 셰이프 | 예 | 예 | 예 |
| 슬라이서 | 예 | 예 | 해당 없음 |
| 테이블 | 예 | 예 | 해당 없음 |
| 텍스트 상자 | 아니요 | 예 | 해당 없음 |
| 트리맵 | 예 | 예 | 예 |
| 폭포 | 예 | 예 | 예 |

## <a name="next-steps"></a>다음 단계

- [X축 및 Y축 속성 사용자 지정](power-bi-visualization-customize-x-axis-and-y-axis.md)

- [색 서식 지정 및 축 속성 시작](service-getting-started-with-color-formatting-and-axis-properties.md)

궁금한 점이 더 있나요? [Power BI 커뮤니티를 이용하세요.](https://community.powerbi.com/)
