---
title: 'DAX: COUNT 대신 COUNTROWS 사용'
description: COUNTROWS 함수를 사용할 경우에 대한 지침입니다.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 11/23/2019
ms.author: v-pemyer
ms.openlocfilehash: fd3b50e9016298db8b692d6a2f3549b770f143e8
ms.sourcegitcommit: 8e3d53cf971853c32eff4531d2d3cdb725a199af
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "74700665"
---
# <a name="dax-use-countrows-instead-of-count"></a>DAX: COUNT 대신 COUNTROWS 사용

데이터 모델러는 경우에 따라 테이블 행을 계산하는 DAX 식을 작성해야 할 수도 있습니다. 테이블은 모델 테이블이거나 테이블을 반환하는 식일 수 있습니다.

요구 사항은 두 가지 방법으로 충족할 수 있습니다. [COUNT](/dax/count-function-dax) 함수를 사용하여 열 값을 계산하거나 [COUNTROWS](/dax/countrows-function-dax) 함수를 사용하여 테이블 행 수를 계산할 수 있습니다. 두 함수는 모두 계산된 열에 공백이 없음을 가정하여 동일한 결과를 얻을 수 있습니다.

다음 측정값 정의는 예제입니다. **OrderDate** 열 값의 수를 계산합니다.

```dax
Sales Orders =
COUNT(Sales[OrderDate])
```

**Sales** 테이블의 세분성이 판매 주문당 한 행이고 **OrderDate** 열에 공백이 없는 경우 측정값이 올바른 결과를 반환합니다.

그러나 다음 측정값 정의가 더 효율적인 솔루션입니다.

```dax
Sales Orders =
COUNTROWS(Sales)
```

두 번째 측정값 정의가 더 좋은 이유는 세 가지입니다.

- 효율성이 높으므로 더 효율적으로 수행됩니다.
- 테이블의 열에 공백이 있다고 고려하지 않습니다.
- 수식의 목적이 자체 설명될 수 있을 만큼 더 분명합니다.

## <a name="recommendation"></a>권장 사항

테이블 행을 계산하려는 경우 항상 COUNTROWS 함수를 사용하는 것이 좋습니다.

## <a name="next-steps"></a>다음 단계

이 문서에 대한 자세한 내용은 다음 리소스를 참조하세요.

- [DAX(Data Analysis Expressions) 참조](/dax/)
- 궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](https://community.powerbi.com/)
