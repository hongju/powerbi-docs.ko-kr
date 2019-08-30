---
title: 'DAX: 나누기 함수 및 나누기 연산자(/)'
description: DAX 나누기 함수를 사용할 경우에 대한 지침입니다.
author: guyinacube
manager: asaxton
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 08/05/2019
ms.author: v-pemyer
ms.openlocfilehash: d22491ee314ebcebd4479c4e57dbfdf7a6a1ffdb
ms.sourcegitcommit: c2197c3ad1d747b4ad490ab75771a0d32d0ae208
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/23/2019
ms.locfileid: "70010440"
---
# <a name="dax-divide-function-vs-divide-operator-"></a>DAX: 나누기 함수 및 나누기 연산자(/)

이 문서는 DAX 식을 정의하는 데이터 모델러를 대상으로 합니다.

## <a name="background"></a>배경

분자를 분모로 나누는 DAX 식을 작성할 때 [나누기](/dax/divide-function-dax) 함수 또는 나누기 연산자(/ - 슬래시)를 사용하도록 선택할 수 있습니다.

나누기 함수를 사용하는 경우 분자 및 분모 식으로 전달해야 합니다. 선택적으로 대체 결과를 나타내는 값으로 전달할 수 있습니다.

```dax

DIVIDE(<numerator>, <denominator> [,<alternateresult>])

```

나누기 함수는 0으로 나누기 사례를 자동으로 처리하도록 설계되었습니다. 대체 결과가 전달되지 않고 분모가 0이거나 비어 있는 경우 함수는 BLANK를 반환합니다. 대체 결과가 전달된 경우 공백 대신 반환됩니다.

나누기 함수는 식으로 분모 값을 먼저 테스트할 필요가 없기 때문에 편리합니다. 함수는 [IF](/dax/if-function-dax) 함수보다 분모 값을 테스트하는 데에도 더욱 최적화되어 있습니다. 나누기를 사용하면 더욱 간결하고 세련된 식이 생성됩니다.

## <a name="example"></a>예제

다음 측정값 식은 안전한 나눗셈을 만들지만 세 개의 DAX 함수를 사용합니다.

```dax

=IF(ISBLANK([Sales]) || [Sales] = 0, BLANK(), [Profit] / [Sales])

```

이 측정값 식은 동일한 결과를 더 효율적이고 세련되게 달성합니다.

```dax

=DIVIDE([Profit], [Sales])

```

## <a name="recommendations"></a>권장 사항

분모가 0을 반환하거나 비어 있을 _가능성이 있는_ 식일 때는 항상 나누기 함수를 사용하는 것이 좋습니다.

분모가 상수 값인 경우 나누기 연산자를 사용하는 것이 좋습니다. 이 경우 나누기의 성공이 보장되며, 불필요한 테스트를 피할 수 있으므로 식이 더 효과적으로 수행됩니다.

나누기 함수에서 대체 값을 반환할지를 신중하게 고려해야 합니다. 측정값의 경우 일반적으로 비어 있음이 반환되도록 설계하는 것이 더 좋습니다. 이는 요약이 비어 있는 경우 보고서의 시각적 개체가 기본적으로 그룹화를 제거하기 때문입니다. 이를 통해 시각적 개체는 데이터가 존재하는 그룹에 집중될 수 있습니다. 필요한 경우 ‘데이터가 없는 항목 표시’ 옵션을 사용하도록 설정하여 시각적 개체가 필터 컨텍스트 내에서 모든 그룹(값이나 비어 있음을 반환)을 표시하도록 구성할 수 있습니다.
