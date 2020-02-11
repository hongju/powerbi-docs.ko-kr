---
title: 'DAX: 열 및 측정값 참조'
description: DAX 식의 측정값에서 열을 참조하는 방법에 대한 지침입니다.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 12/18/2019
ms.author: v-pemyer
ms.openlocfilehash: 3ca49008639f7e3e084c8d045bc911aff57b7b21
ms.sourcegitcommit: 0da17de80c9651f9f4474d1abb1bdaaade8808fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/27/2019
ms.locfileid: "75498740"
---
# <a name="dax-column-and-measure-references"></a>DAX: 열 및 측정값 참조

데이터 모델러는 DAX 식에서 모델 열과 측정값을 참조합니다. 열과 측정값은 항상 모델 테이블과 연결되지만 이러한 연결은 다릅니다. 따라서 식에서 열과 측정값을 참조하는 방법의 권장 사항도 다릅니다.

## <a name="columns"></a>열

열은 테이블 수준 개체이므로, 열 이름이 테이블 내에서 고유해야 합니다. 따라서 서로 다른 테이블에 속해 있는 경우, 동일한 열 이름이 모델에서 여러 번 사용될 수 있습니다. 한 가지 규칙이 더 있습니다. 열 이름은 동일한 테이블에 있는 측정값 이름 또는 계층 구조 이름과 같을 수 없습니다.

일반적으로 DAX는 _정규화된_ 열 참조를 사용하도록 강제 적용하지 않습니다. 정규화된 참조는 열 이름 앞에 테이블 이름을 사용하는 것입니다.

다음은 열 이름 참조만 사용한 계산 열 정의의 예입니다. **판매량** 및 **비용** 열은 모두 **주문** 테이블에 속해 있습니다.

```dax
Profit = [Sales] - [Cost]
```

정규화된 열 참조를 사용하여 동일한 정의를 다시 작성할 수 있습니다.

```dax
Profit = Orders[Sales] - Orders[Cost]
```

그러나 Power BI에서 모호성을 탐지할 경우 정규화된 열 참조를 사용해야 하는 경우도 있습니다. 수식을 입력할 때 빨간색 물결선과 오류 메시지가 표시되어 경고합니다. 또한 [LOOKUPVALUE](/dax/lookupvalue-function-dax) DAX 함수와 같은 일부 DAX 함수는 정규화된 열을 사용해야 합니다.

항상 열 참조를 정규화하는 것이 좋습니다. 이유는 [권장 사항](#recommendations) 섹션에 나와 있습니다.

## <a name="measures"></a>측정값

측정값은 모델 수준 개체입니다. 이런 이유로 측정값 이름은 모델 내에서 고유해야 합니다. 그러나 **필드** 창에서 보고서 작성자는 각 측정값이 단일 모델 테이블과 연결되어 있는 것을 확인할 수 있습니다. 이 연결은 외관상의 이유로 설정된 것이며, 측정값의 **홈 테이블** 속성을 설정하여 구성할 수 있습니다. 자세한 내용은 [Power BI Desktop의 측정값(측정값 구성)](../desktop-measures.md#organizing-your-measures)을 참조하세요.

식에 정규화된 측정값을 사용할 수 있습니다. DAX intellisense에서 제안도 제공합니다. 그러나 이 방법은 필요하지 않으며 권장되지 않습니다. 측정값의 홈 테이블을 변경하면 정규화된 측정값 참조를 사용하는 모든 식이 중단됩니다. 중단된 수식을 각각 편집하여 측정값 참조를 제거(또는 업데이트)해야 합니다.

측정값 참조를 정규화하지 않는 것이 좋습니다. 이유는 [권장 사항](#recommendations) 섹션에 나와 있습니다.

## <a name="recommendations"></a>권장 사항

권장 사항은 간단하고 쉽게 기억할 수 있습니다.

- 항상 정규화된 열 참조 사용
- 정규화된 측정값 참조 사용 안 함

그 이유는 다음과 같습니다.

- **수식 입력**: 확인할 모호한 참조가 없으므로 식이 허용됩니다. 또한 정규화된 열 참조가 필요한 DAX 함수의 요구 사항을 충족합니다.
- **견고성**: 측정값 홈 테이블 속성을 변경해도 식이 계속 작동합니다.
- **가독성**: 쉽고 빠르게 식을 파악할 수 있습니다. 정규화되었는지 여부에 따라 열 또는 측정값인지를 빠르게 확인할 수 있습니다.

## <a name="next-steps"></a>다음 단계

이 문서에 대한 자세한 내용은 다음 리소스를 참조하세요.

- [DAX(Data Analysis Expressions) 참조](/dax/)
- 궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](https://community.powerbi.com/)
