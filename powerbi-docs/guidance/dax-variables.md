---
title: 'DAX: 변수를 사용하여 수식 향상'
description: DAX 식에서 변수를 사용하기 위한 가이드입니다.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 11/23/2019
ms.author: v-pemyer
ms.openlocfilehash: f352cbbd7c42aa54ae876e73c0ed821eccda59c8
ms.sourcegitcommit: f77b24a8a588605f005c9bb1fdad864955885718
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2019
ms.locfileid: "74700711"
---
# <a name="dax-use-variables-to-improve-your-formulas"></a>DAX: 변수를 사용하여 수식 향상

데이터 모델러는 작성하고 디버깅하기 까다로운 DAX 계산에 맞닥뜨리는 경우가 있습니다. 복잡한 계산의 경우에는 복잡한 식이나 복합 식이 필요한 경우가 많습니다. 복합 식에는 여러 개의 중첩 함수가 사용될 수 있고, 식 논리가 재사용되기도 합니다.

DAX 수식에서 변수를 사용하면 복잡하고 효율적인 계산을 작성할 수 있습니다. 변수를 사용하면 다음과 같은 이점이 제공됩니다.

- [성능 향상](#improve-performance)
- [가독성 향상](#improve-readability)
- [디버깅 간소화](#simplify-debugging)
- [복잡성 감소](#reduce-complexity)

이 문서에서는 측정값의 전년 대비(YoY) 판매량 성장률을 통해 처음 3가지 이점을 살펴보겠습니다. (YoY 판매량 성장률 수식은 전년도 동기 판매량을 금년도 동기 판매량으로 _나눈_ 것입니다.)

다음과 같은 측정값 정의로 시작하겠습니다.

```dax
Sales YoY Growth % =
DIVIDE(
    ([Sales] - CALCULATE([Sales], PARALLELPERIOD('Date'[Date], -12, MONTH))),
    CALCULATE([Sales], PARALLELPERIOD('Date'[Date], -12, MONTH))
)
```

측정값은 올바른 결과를 생성합니다. 이번에는 이것을 어떻게 개선할 수 있을지 살펴보겠습니다.

## <a name="improve-performance"></a>성능 향상

수식에서 “전년도 동기”를 계산하는 식이 반복되는 것을 볼 수 있습니다. 이 수식은 Power BI가 동일한 식을 두 번 계산하도록 만들기 때문에 비효율적입니다. 변수를 사용하면 측정값 정의를 더 효율적으로 만들 수 있습니다.

다음은 개선된 측정값 정의입니다. **SalesPriorYear**라는 변수에 “전년도 동기”라는 결과를 할당하는 식을 사용합니다. 이 변수는 RETURN 식에서 두 번 사용됩니다.

```dax
Sales YoY Growth % =
VAR SalesPriorYear =
    CALCULATE([Sales], PARALLELPERIOD('Date'[Date], -12, MONTH))
RETURN
    DIVIDE(([Sales] - SalesPriorYear), SalesPriorYear)
```

측정값이 계속해서 올바른 결과를 생성하며, 쿼리 시간의 약 절반 가량 올바른 값을 생성합니다.

## <a name="improve-readability"></a>가독성 향상

앞에 나온 측정값 정의에서는 변수 이름 덕분에 RETURN 식을 보다 쉽게 이해할 수 있었습니다. 이 식은 짧으면서도 그 자체로 내용을 설명해 줍니다.

## <a name="simplify-debugging"></a>디버깅 간소화

변수는 수식을 디버깅할 때도 도움이 됩니다. 변수에 할당된 식을 테스트하려면 RETURN 식이 변수를 출력하도록 임시로 다시 작성해 볼 수 있습니다.

다음 측정값 정의는 **SalesPriorYear** 변수만 반환합니다. 원래의 RETURN 식은 주석 처리된 것을 볼 수 있습니다. 이와 같은 방법을 사용하면 디버깅을 마친 후에 손쉽게 다시 원래로 되돌릴 수 있습니다.

```dax
Sales YoY Growth % =
VAR SalesPriorYear =
    CALCULATE([Sales], PARALLELPERIOD('Date'[Date], -12, MONTH))
RETURN
    --DIVIDE(([Sales] - SalesPriorYear), SalesPriorYear)
    SalesPriorYear
```

## <a name="reduce-complexity"></a>복잡성 감소

이전 버전의 DAX에서는 변수가 지원되지 않았습니다. 새로운 필터 컨텍스트가 도입되는 복잡한 식의 경우 [EARLIER](/dax/earlier-function-dax) 또는 [EARLIEST](/dax/earliest-function-dax) DAX 함수를 사용하여 외부 필터 컨텍스트를 참조해야 했습니다. 데이터 모델러들은 이러한 함수를 이해하고 사용하는 데 많은 어려움을 겪었습니다.

변수는 항상 RETURN 식이 적용되는 필터 밖에서 계산됩니다. 따라서 수정된 필터 컨텍스트 내에서 변수를 사용할 경우 EARLIEST 함수와 동일한 결과가 나옵니다. 그러므로 EARLIER 또는 EARLIEST 함수를 사용하지 않을 수 있습니다. 즉, 이제 덜 복잡하고 이해하기 쉬운 수식을 작성할 수 있습니다.

아래에서 **Subcategory** 테이블에 추가된 계산 열 정의를 살펴보겠습니다. 계산 열은 **Subcategory Sales** 열 값을 기준으로 각 제품 하위 범주의 순위를 계산합니다.

```dax
Subcategory Sales Rank =
COUNTROWS(
    FILTER(
        Subcategory,
        EARLIER(Subcategory[Subcategory Sales]) < Subcategory[Subcategory Sales]
    )
) + 1
```

_현재 행 컨텍스트_에서 **Subcategory Sales** 열 값을 참조하기 위해 EARLIER 함수가 사용되었습니다.

EARLIER 함수 대신 변수를 사용하면 계산 열 정의를 개선할 수 있습니다. **CurrentSubcategorySales** 변수는 _현재 행 컨텍스트_에서 **Subcategory Sales** 열 값을 저장하고, RETURN 식은 수정된 필터 컨텍스트 내에서 이 값을 사용합니다.

```dax
Subcategory Sales Rank =
VAR CurrentSubcategorySales = Subcategory[Subcategory Sales]
RETURN
    COUNTROWS(
        FILTER(
            Subcategory,
            CurrentSubcategorySales < Subcategory[Subcategory Sales]
        )
    ) + 1
```

## <a name="next-steps"></a>다음 단계

이 문서에 대한 자세한 내용은 다음 리소스를 참조하세요.

- [VAR](/dax/var-dax) DAX 문서
- 궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](https://community.powerbi.com/)
