---
title: 'DAX: 공백을 값으로 변환하지 마세요.'
description: 공백을 값으로 변환하기 위한 가이드입니다.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 11/24/2019
ms.author: v-pemyer
ms.openlocfilehash: 2f70b98ed540a2e5b87e5a949e30b0c1c02069d1
ms.sourcegitcommit: 8e3d53cf971853c32eff4531d2d3cdb725a199af
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "74700389"
---
# <a name="dax-avoid-converting-blanks-to-values"></a>DAX: 공백을 값으로 변환하지 마세요.

데이터 모델러가 측정값 식을 작성할 때 의미 있는 값을 반환할 수 없는 경우가 있을 수 있습니다. 이 경우 그 대신 특정 값(예: 0)을 반환하고 싶을 수 있습니다. 하지만 이러한 방식이 효율적이고 실용적인지 따져 봐야 합니다.

비어 있는 결과를 명시적으로 0으로 변환하는 다음 측정값 정의를 살펴보겠습니다.

```dax
Sales (No Blank) =
IF(
    ISBLANK([Sales]),
    0,
    [Sales]
)
```

비어 있는 결과를 0으로 변환하는 또 다른 측정값 정의를 살펴보겠습니다.

```dax
Profit Margin =
DIVIDE([Profit], [Sales], 0)
```

[DIVIDE](/dax/divide-function-dax) 함수는 **Profit** 측정값을 **Sales** 측정값으로 나눕니다. 결과가 0 또는 비어 있는 경우, 세 번째 인수(선택 사항인 대체 결과)가 반환됩니다. 이 예제에서, 0이 대체 결과로 전달되므로 측정값을 어떤 경우에도 항상 값을 반환합니다.

이러한 측정값 설계는 비효율적이며 좋지 않은 보고서 디자인으로 이어집니다.

이러한 측정값 설계를 보고서 시각적 개체에 추가할 경우, Power BI는 필터 컨텍스트 내의 모든 그룹화를 가져오려고 시도합니다. 다량의 쿼리 결과를 계산하고 가져오려면 보고서 렌더링이 느려지게 됩니다. 위의 두 예제는 희소 계산을 고밀도 계산으로 바꾸어서 Power BI가 필요한 것보다 많은 메모리를 사용하도록 만듭니다.

게다가 그룹화가 너무 많으면 보고서 사용자가 소화하기 어려울 수 있습니다.

테이블 시각적 개체에 고객으로 그룹화된 **Profit Margin** 측정값을 추가하면 어떻게 되는지 살펴보겠습니다.

![테이블 시각적 개체에 Customer(고객), Sales(판매량), Profit Margin(이익)이라는 3개의 열이 있습니다. 테이블에는 약 10개의 데이터 행이 있으며, 세로 스크롤 막대가 있는 것으로 보아 표시된 것보다 더 많은 행이 있다는 것을 알 수 있습니다. Sales(판매량) 열에는 아무런 값도 표시되어 있지 않습니다. Profit Margin(이익) 열에는 0만 표시되어 있습니다.](media/dax-avoid-converting-blank/table-visual-poor.png)

테이블 시각적 개체에 매우 많은 개수의 행이 표시되어 있습니다. (실제로 이 모델에는 18,484명의 고객이 포함되어 있으므로 테이블에 해당 데이터가 모두 표시될 것입니다.) 표시된 고객의 경우 판매량이 없는 것을 알 수 있습니다. 그러나 **Profit Margin**(이익)이 어떤 경우에도 항상 값을 반환하므로 모두 표시되고 있습니다.

> [!NOTE]
> 시각적 개체에 표시해야 할 데이터 요소가 너무 많은 경우, Power BI는 데이터 감소 전략을 사용하여 다량의 쿼리 결과를 제거하거나 요약할 수 있습니다. 자세한 내용은 [시각적 개체 유형별 데이터 요소 제한 및 전략](../visuals/power-bi-data-points.md)을 참조하세요.

**Profit Margin**(이익) 측정값 정의를 개선하면 어떻게 되는지 살펴보겠습니다. 이제는 **Sales**(판매량) 측정값이 공백(또는 0)이 아닌 경우에만 값을 반환합니다.

```dax
Profit Margin =
DIVIDE([Profit], [Sales])
```

테이블 시각적 개체는 이제 현재 필터 컨텍스트 내에서 판매량이 있는 고객만 표시합니다. 향상된 측정값은 보고서 사용자에게 보다 효율적이고 실용적인 경험을 제공합니다.

![아까와 동일한 테이블 시각적 개체가 4개와 데이터 행만 표시하는 것을 볼 수 있습니다. 각 행에는 판매량 값이 있고 Profit Margin(이익) 값이 0이 아닌 고객이 표시되어 있습니다.](media/dax-avoid-converting-blank/table-visual-good.png)

> [!TIP]
> 필요한 경우 [데이터가 없는 항목 표시](../desktop-show-items-no-data.md) 옵션을 사용하도록 설정하여 시각적 개체가 필터 컨텍스트 내에서 모든 그룹화(값을 반환하는 것과 비어 있음을 반환하는 것 모두)를 표시하도록 구성할 수 있습니다.

## <a name="recommendation"></a>권장 사항

의미 있는 값이 반환되지 않는 경우에는 측정값이 공백을 반환하도록 하는 것이 권장됩니다.

이 접근 방식은 효율적일 뿐 아니라 Power BI가 보고서를 더 빠르게 렌더링하게 됩니다. 게다가 요약이 비어 있는 경우 보고서의 시각적 개체가 기본적으로 그룹화를 제거하기 때문에 비어 있음을 반환하는 것이 더 좋습니다.

## <a name="next-steps"></a>다음 단계

이 문서에 대한 자세한 내용은 다음 리소스를 참조하세요.

- [DAX(Data Analysis Expressions) 참조](/dax/)
- 궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](https://community.powerbi.com/)
