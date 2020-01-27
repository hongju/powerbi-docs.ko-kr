---
title: 'DAX: FILTER를 필터 인수로 사용하지 마세요.'
description: FILTER 함수를 필터 인수로 사용하는 방법에 대한 지침입니다.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 12/30/2019
ms.author: v-pemyer
ms.openlocfilehash: 935b453dabeaa731a218175526ddddeb980a2b92
ms.sourcegitcommit: b09de56e971b8844a3771413d1f56d49b31baaaf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75692462"
---
# <a name="dax-avoid-using-filter-as-a-filter-argument"></a>DAX: FILTER를 필터 인수로 사용하지 마세요.

데이터 모델러는 일반적으로 수정된 필터 컨텍스트에서 평가되어야 하는 DAX 식을 작성합니다. 예를 들어 “이익이 높은 제품”의 판매를 계산하는 측정값 정의를 작성할 수 있습니다. 이 계산은 이 문서의 뒷부분에서 설명합니다.

> [!NOTE]
> 이 문서는 특히 가져오기 테이블에 필터를 적용하는 모델 계산과 관련이 있습니다.

[CALCULATE](/dax/calculate-function-dax) 및 [CALCULATETABLE](/dax/calculatetable-function-dax) DAX 함수는 중요하고 유용한 함수입니다. 이러한 함수를 사용하면 필터를 제거 또는 추가하거나 관계 경로를 수정하는 계산을 작성할 수 있습니다. 이 작업은 부울 식, 테이블 식 또는 특수 필터 함수인 필터 인수를 전달하여 수행합니다. 이 문서에서는 부울 식 및 테이블 식에 대해서만 설명합니다.

테이블 식을 사용하여 빨간색 제품 판매를 계산하는 다음과 같은 측정값 정의를 고려해 보세요. 이 정의는 **Product** 테이블에 적용될 수 있는 모든 필터를 바꿉니다.

```dax
Red Sales =
CALCULATE(
    [Sales],
    FILTER('Product', 'Product'[Color] = "Red")
)
```

CALCULATE 함수에서는 **Product** 테이블의 각 행에 대해 해당 필터 식을 평가하는, [FILTER](/dax/filter-function-dax) DAX 함수에서 반환된 테이블 식이 허용됩니다. 따라서 정확하게 빨간색 제품 판매 결과를 구할 수 있습니다. 하지만 부울 식을 사용하면 훨씬 더 효율적으로 결과를 구할 수 있습니다.

테이블 식 대신 부울 식을 사용하는 더 효율적인 측정값 정의는 다음과 같습니다.

```dax
Red Sales =
CALCULATE(
    [Sales],
    'Product'[Color] = "Red"
)
```

가능한 한 필터 인수는 부울 식으로 전달하는 것이 좋습니다. 가져오기 모델 테이블은 메모리 내 열 저장소이기 때문입니다. 이러한 방식으로 열을 효율적으로 필터링하도록 명시적으로 최적화됩니다.

하지만 부울 식이 필터 인수로 사용되는 경우 부울 식에 적용되는 제한이 있습니다. 제한은 다음과 같습니다.

- 열을 다른 열과 비교할 수 없습니다.
- 측정값을 참조할 수 없습니다.
- 중첩된 CALCULATE 함수를 사용할 수 없습니다.
- 테이블을 검사하거나 반환하는 함수를 사용할 수 없습니다.

즉, 더 복잡한 필터 요구 사항을 충족하도록 테이블 식을 사용해야 합니다.

이제 다른 측정값 정의를 살펴보겠습니다.

```dax
High Margin Product Sales =
CALCULATE(
    [Sales],
    FILTER(
        'Product',
        'Product'[ListPrice] > 'Product'[StandardCost] * 2
    )
)
```

_이익이 높은 제품_의 정의는 정가가 해당 표준 비용의 2배가 넘는 제품입니다. 이 예제에서는 FILTER 함수를 사용해야 합니다. 부울 식에는 필터 식이 너무 복잡하기 때문입니다.

아래에는 또 다른 예제가 있습니다. 이번 요구 사항은 수익을 달성한 월에 대해서만 판매를 계산하는 것입니다.

```dax
Sales for Profitable Months =
CALCULATE(
    [Sales],
    FILTER(
        VALUES('Date'[Month]),
        [Profit] > 0)
    )
)
```

이 예제에서는 FILTER 함수도 사용해야 합니다. **수익** 측정값을 평가하여 수익을 달성하지 못한 월을 제거해야 하기 때문입니다. 필터 인수로 사용되는 경우에는 부울 식에서 측정값을 사용할 수 없습니다.

## <a name="recommendations"></a>권장 사항

최상의 성능을 얻으려면 가능한 한 부울 식을 필터 인수로 사용하는 것이 좋습니다.

따라서 FILTER 함수는 필요한 경우에만 사용해야 합니다. 필터 복합 열 비교를 수행하는 데 사용할 수 있습니다. 이러한 열 비교에는 다음이 포함될 수 있습니다.

- 측정값
- 기타 열
- [OR](/dax/or-function-dax) DAX 함수 또는 OR 논리 연산자(||) 사용

## <a name="next-steps"></a>다음 단계

이 문서에 대한 자세한 내용은 다음 리소스를 참조하세요.

- [DAX(Data Analysis Expressions) 참조](/dax/)
- [필터 함수(DAX)](/dax/filter-function-dax)
- 궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](https://community.powerbi.com/)
