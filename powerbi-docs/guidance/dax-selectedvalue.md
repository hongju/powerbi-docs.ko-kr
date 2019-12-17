---
title: 'DAX: 값 대신 SELECTEDVALUE 사용'
description: 어떤 경우에 SELECTEDVALUE 함수를 사용해야 하는지 설명합니다.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 11/20/2019
ms.author: v-pemyer
ms.openlocfilehash: 6aef2c06cc62668ea7dea9fe404e294d1a5faa93
ms.sourcegitcommit: f77b24a8a588605f005c9bb1fdad864955885718
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2019
ms.locfileid: "74700481"
---
# <a name="dax-use-selectedvalue-instead-of-values"></a>DAX: 값 대신 SELECTEDVALUE 사용

데이터 모델러는 열이 특정 값에 의해 필터링되는지 테스트하는 DAX 식을 작성해야 하는 경우가 있습니다.

이전 버전의 DAX에서는 3가지 DAX 함수가 사용되는 패턴을 사용하여 이 목적을 안전하게 달성할 수 있었습니다. 3가지 함수는 [IF](/dax/if-function-dax), [HASONEVALUE](/dax/hasonevalue-function-dax), [VALUES](/dax/values-function-dax)입니다. 다음 측정값 정의는 예제입니다. 여기서는 호주 고객에게 판매된 건수에 대해서만 판매세 금액을 계산합니다.

```dax
Australian Sales Tax =
IF(
    HASONEVALUE(Customer[Country-Region]),
    IF(
        VALUES(Customer[Country-Region]) = "Australia",
        [Sales] * 0.10
    )
)
```

위 예에서 HASONEVALUE 함수는 1개의 값이 **Country-Region** 열을 필터링하는 경우에만 TRUE를 반환합니다. TRUE가 반환되면 VALUES 함수가 리터럴 텍스트 “Australia”와 비교됩니다. VALUES 함수가 TRUE를 반환하면 **Sales** 측정값에 0.10(즉, 10%)이 곱해집니다. 둘 이상의 값이 열을 필터링하기 때문에 HASONEVALUE 함수가 FALSE를 반환하는 경우, 첫 번째 IF 함수가 비어 있음을 반환합니다.

HASONEVALUE의 용법은 방어적인 기법입니다. 방어적인 기법은 **Country-Region** 열을 여러 개의 값이 필터링할 수 있기 때문에 필요합니다. 이 경우에는 VALUES 함수가 여러 행으로 이루어진 테이블을 반환합니다. 여러 행으로 이루어진 테이블을 스칼라 값과 비교하면 오류가 반환됩니다.

## <a name="recommendation"></a>권장 사항

[SELECTEDVALUE](/dax/selectedvalue-function) 함수를 사용할 것을 권장합니다. SELECTEDVALUE는 이 문서에서 설명하는 패턴과 동일한 결과를 제공하면서도 그보다 더 효율적이고 간단합니다.

SELECTEDVALUE 함수를 사용하여 측정값 정의를 다시 작성하면 다음과 같습니다.

```dax
Australian Sales Tax =
IF(
    SELECTEDVALUE(Customer[Country-Region]) = "Australia",
    [Sales] * 0.10
)
```

> [!TIP]
> SELECTEDVALUE 함수로 _대체 결과_ 값을 전달하는 것이 가능합니다. 대체 결과 값은 열에 적용된 필터가 없거나 여러 개의 필터가 적용된 경우에 반환됩니다.

## <a name="next-steps"></a>다음 단계

이 문서에 대한 자세한 내용은 다음 리소스를 참조하세요.

- [DAX(Data Analysis Expressions) 참조](/dax/)
- 궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](https://community.powerbi.com/)
