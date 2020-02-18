---
title: 보고서의 색 서식을 위한 팁과 힌트
description: Power BI 보고서의 색 서식을 위한 팁과 힌트
author: mihart
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/29/2020
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 0b633f2482c5b9f1624f39e4f2c0e07afc55353f
ms.sourcegitcommit: 8e3d53cf971853c32eff4531d2d3cdb725a199af
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "76895021"
---
# <a name="tips-and-tricks-for-color-formatting-in-power-bi"></a>Power BI의 색 서식을 위한 팁과 힌트
Power BI는 대시보드 및 보고서를 사용자 지정할 수 있는 다양한 방법을 제공합니다. 이 아티클에서는 사용자의 요구에 맞게 Power BI를 보다 매력적이고 흥미롭게 시각화하고 사용자 지정할 수 있는 팁 모음에 대해 자세히 다룹니다.

다음 팁을 제공합니다. 다른 유용한 팁이 있나요? 좋습니다! 팁을 보내주시면 이 목록에 추가하는 것을 고려해 보겠습니다.

* 전체 보고서에 테마 적용
* 단일 데이터 요소 색 변경
* 조건부 서식 지정
* 숫자 값 기준 차트 색
* 필드 값 기준 데이터 요소 색
* 색 눈금에 사용되는 색 사용자 지정
* 색 눈금 분기 사용
* 테이블 행에 색 추가
* Power BI에서 실행 취소 방법

보고서를 변경하려면 보고서 편집 권한이 있어야 합니다. Power BI Desktop의 **보고서** 보기에서 보고서를 엽니다. Power BI 서비스에서 다음 그림에 표시된 것처럼 보고서를 열고 메뉴 모음에서 **편집**을 선택합니다.

![편집 메뉴를 찾을 수 있는 위치](media/service-tips-and-tricks-for-color-formatting/power-bi-edit-report.png)

보고서 캔버스 오른쪽에 **필터** 및 **시각화** 창이 나타나면 사용자 지정을 시작할 준비가 된 것입니다. 창이 표시되지 않으면 오른쪽 위 모서리의 화살표를 선택하여 창을 엽니다.

![편집용 보기에서 캔버스 보고](media/service-tips-and-tricks-for-color-formatting/power-bi-edit.png)

## <a name="apply-a-theme"></a>테마 적용
보고서 테마를 사용하여 전체 보고서에 디자인 변경 내용을 적용할 수 있습니다. 예를 들어, 회사 색을 사용하거나 아이콘 세트를 변경하거나 새로운 기본 시각적 서식을 적용할 수 있습니다. 보고서 테마를 적용하면 보고서의 모든 시각적 개체는 선택한 테마의 색과 서식을 사용합니다. 자세히 알아보려면 [보고서 테마 사용](../desktop-report-themes.md)을 참조하세요.

![메뉴 모음에서 테마 아이콘 전환](media/service-tips-and-tricks-for-color-formatting/power-bi-theme.png)

여기에서 판매 및 마케팅 보고서에 **혁신** 테마를 적용했습니다.

![혁신 테마 적용됨](media/service-tips-and-tricks-for-color-formatting/power-bi-theme-innovate.png)

## <a name="change-the-color-of-a-single-data-point"></a>단일 데이터 요소 색 변경
하나의 특정 데이터 요소를 강조 표시하려는 경우가 있습니다. 아마도 신제품 출시에 대한 판매 수치 또는 새 프로그램을 시작한 후 품질 점수 증가 등을 강조 표시하려는 경우입니다. Power BI에서는 색을 변경하여 특정 데이터 요소를 강조 표시할 수 있습니다.

다음 시각화는 제품 세그먼트별로 판매된 단위의 순위를 보여 줍니다. 

![데이터 색을 회색으로 변경](media/service-tips-and-tricks-for-color-formatting/power-bi-data.png)

이제 색을 사용하여 이 브랜드의 새 세그먼트가 얼마나 잘 운영되는지 보여 주기 위해 **Convenience** 세그먼트를 살펴보겠습니다. 수행하는 단계는 다음과 같습니다.

**데이터 색** 카드를 확장하고 **모두 표시**의 슬라이더를 켜기로 전환합니다. 그러면 시각화에서 각 데이터 요소에 대한 색이 표시됩니다. 이제 데이터 요소를 수정할 수 있습니다.

![](media/service-tips-and-tricks-for-color-formatting/power-bi-show.png)

**Convenience**를 주황색으로 설정합니다. 

![](media/service-tips-and-tricks-for-color-formatting/power-bi-one-color.png)

선택된 **Convenience** 데이터 요소는 멋지게 음영 표시되고 확실히 돋보입니다.

시각화 유형을 변경한 후 돌아오더라도 Power BI에서 선택 항목을 기억하고 **Convenience**를 주황색으로 유지합니다.

하나, 여러 개 또는 모든 데이터 요소(element)의 데이터 요소(point) 색을 변경할 수 있습니다. 노랑, 녹색 및 파랑의 회사 색상처럼 보이는 시각적 개체가 필요할 수 있습니다. 

![녹색, 노란색, 파란색 막대를 사용하는 가로 막대형 차트](media/service-tips-and-tricks-for-color-formatting/power-bi-corporate.png)

색으로 모든 종류의 작업을 수행할 수 있습니다. 다음 섹션에서는 조건부 서식 지정에 대해 살펴봅니다.

## <a name="conditional-formatting-for-visualizations"></a>시각 효과의 조건부 서식 지정
시각 효과에서는 필드의 숫자 값을 기준으로 동적으로 색을 설정하는 기능을 종종 활용합니다. 이렇게 하면 막대 크기에 사용한 것과 다른 값을 표시하고 단일 그래프에 두 값을 표시할 수 있습니다. 또는 이 기능을 사용하여 특정 값을 초과(또는 미만)하는 데이터 요소를 강조 표시할 수 있으며 예를 들면 수익성이 낮은 영역을 강조 표시할 수 있습니다.

다음 섹션에서는 숫자 값을 기준으로 색을 지정하는 다양한 방법을 보여줍니다.

### <a name="base-the-color-of-data-points-on-a-value"></a>값 기준 데이터 요소 색
값을 기준으로 색을 변경하려면 시각화를 선택하여 활성 상태로 만듭니다. 페인트 롤러 아이콘을 선택하여 서식 창을 연 다음 **데이터 색** 카드를 확장합니다. 카드를 마우스로 가리킨 후 표시되는 세로 점 세 개를 선택하고 **조건부 서식**을 선택합니다.  

![세 개의 세로 점을 클릭하여 조건부 서식 지정 옵션 선택](media/service-tips-and-tricks-for-color-formatting/power-bi-conditional-formatting.gif)

**기본 색** 창에서 드롭다운을 사용하여 조건부 서식 지정에 사용할 필드를 식별합니다. 이 제에서는 **Sales 팩트** > **총 단위** 필드를 선택하고 **최솟값**에 대해 밝은 파란색과 **최댓값**에 대해 진한 파란색을 선택합니다. 

![데이터 색상별 조건부 서식 지정 설정](media/service-tips-and-tricks-for-color-formatting/power-bi-conditional-formatting2-new.png)

![기본 색이 적용된 세로 막대형 차트](media/service-tips-and-tricks-for-color-formatting/power-bi-default-colors.png)

시각적 개체의 일부가 아닌 필드를 사용하여 시각적 개체의 색을 서식 지정할 수도 있습니다. 다음 이미지에서는 **%Market Share SPLY YTD**가 사용되고 있습니다. 

![](media/service-tips-and-tricks-for-color-formatting/power-bi-conditional-colors.png)


보시는 것처럼 **Productivity** 및 **Extreme**에서 둘 다 더 많은 단위를 판매했지만(해당 열이 더 높음), **Moderation**의 **%Market Share SPLY YTD**가 더 큽니다(해당 열의 색 채도가 더 큼).

### <a name="customize-the-colors-used-in-the-color-scale"></a>색 눈금에 사용되는 색 사용자 지정
또한 값이 이러한 색에 매핑되는 방식을 변경할 수도 있습니다. 다음 이미지에서는 **최소** 및 **최대** 에 대한 색이 각각 주황색 및 녹색으로 설정됩니다.

첫 번째 이미지에서 차트의 막대가 막대에 표시된 그라데이션을 어떻게 반영하는지 확인합니다. 가장 높은 값은 녹색이고 가장 낮은 값은 주황색이며 그 사이의 각 막대는 녹색과 주황색 사이의 스펙트럼 음영으로 색이 지정됩니다.

![](media/service-tips-and-tricks-for-color-formatting/power-bi-conditional4.png)

이제 **최소** 및 **최대** 값 상자에 숫자 값을 제공하면 어떻게 되는지 살펴보겠습니다. **최소** 및 **최대**의 드롭 상자에서 **사용자 지정**을 선택하고 **최소**를 3,500으로 설정한 다음 **최대**를 6,000으로 설정합니다.

![숫자로 조건부 서식 지정](media/service-tips-and-tricks-for-color-formatting/power-bi-conditional-formatting-numbers.png)

이러한 값을 설정하면 차트에서 **최소** 미만이거나 **최대**를 초과하는 값에 더 이상 그라데이션이 적용되지 않습니다. **최대** 값을 초과하는 값의 막대는 녹색으로 표시되고 **최소** 미만인 값의 막대는 빨간색으로 표시됩니다.

![숫자로 지정한 조건부 서식의 결과](media/service-tips-and-tricks-for-color-formatting/power-bi-conditional3.png)

### <a name="use-diverging-color-scales"></a>색 눈금 분기 사용
경우에 따라 데이터에 자연스럽게 분기하는 눈금이 있을 수 있습니다. 예를 들어 온도 범위에는 어는 점이 자연스런 중심이고 수익성 점수에는 자연스런 중간 지점(0)이 있습니다.

색 눈금 분기를 사용하려면 **분기** 확인란을 선택합니다. **분기**가 켜지면 다음 이미지처럼 **가운데**라는 추가 색 선택기가 나타납니다.

![색 눈금이 선택된 기본 색 대화 상자](media/service-tips-and-tricks-for-color-formatting/power-bi-diverging-colors.png)

**분기** 슬라이더가 켜지면 **최소**, **최대** 및 **가운데** 에 대한 색을 개별적으로 설정할 수 있습니다. 다음 이미지에서는 **% Market Share SPLY YTD**의 경우 **가운데**가 .2로 설정되므로 .2를 초과하는 값의 막대는 녹색 음영으로 그라데이션 표시되고 1 미만인 막대는 빨간색 음영으로 표시됩니다.

![빨간색 및 녹색 막대가 있는 세로 막대형 차트](media/service-tips-and-tricks-for-color-formatting/power-bi-diverging.png)

## <a name="add-color-to-table-rows"></a>테이블 행에 색 추가
테이블 및 행렬은 색 서식 지정을 위한 다양한 옵션을 제공합니다. 

![기본 테이블](media/service-tips-and-tricks-for-color-formatting/power-bi-table.png)

테이블 또는 행렬에 색을 적용하는 가장 빠른 방법 중 하나는 서식 탭을 열고 **스타일**을 선택하는 것입니다.  아래 이미지에서는 **굵은 헤더 현란한 행**을 선택했습니다.

![기본 테이블](media/service-tips-and-tricks-for-color-formatting/power-bi-table-style.png)

다른 색 서식 옵션을 사용하여 실험해 보세요. 이 이미지에서는 **열 머리글**의 배경색을 변경하고 **값**(행)의 **배경색**과 **다른 배경색**을 모두 변경했습니다.

![기본 테이블](media/service-tips-and-tricks-for-color-formatting/power-bi-table-rows.png)

## <a name="how-to-undo-in-power-bi"></a>Power BI에서 실행 취소 방법
다른 여러 Microsoft 서비스 및 소프트웨어와 마찬가지로 Power BI는 마지막 명령을 손쉽게 실행 취소하는 방법을 제공합니다. 예를 들어, 한 개의 데이터 요소 또는 복수의 데이터 요소 색을 변경했으나 시각화에 그 색을 표시했을 때 마음에 들지 않는다고 가정해 보세요. 이전에 어떤 색이었는지 정확히 기억나지는 않지만 색을 되돌리고 싶을 수 있습니다.

마지막 작업 또는 마지막 몇 가지 작업을 **실행 취소**하려면 CTRL+Z를 입력하면 됩니다.

서식 카드에서 변경한 내용을 모두 취소하려면 **기본값으로 되돌리기**를 선택합니다.

![맨 아래에 기본값으로 되돌리기가 표시된 서식 카드](media/service-tips-and-tricks-for-color-formatting/power-bi-revert.png)

## <a name="feedback"></a>피드백
공유하고 싶은 팁이 있나요? 팁을 보내주시면 여기에 포함하는 것을 고려해 보겠습니다.

## <a name="next-steps"></a>다음 단계
[색 서식 지정 및 축 속성 시작](service-getting-started-with-color-formatting-and-axis-properties.md)

