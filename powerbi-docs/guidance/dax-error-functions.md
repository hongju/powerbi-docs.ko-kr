---
title: 'DAX: 오류 함수를 적절하게 사용'
description: DAX 오류 함수를 사용할 경우에 대한 지침입니다.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 09/26/2019
ms.author: v-pemyer
ms.openlocfilehash: ae4e9081930b0f6934a557ba45afd99dd8dfc05d
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2019
ms.locfileid: "73875627"
---
# <a name="dax-appropriate-use-of-error-functions"></a>DAX: 오류 함수를 적절하게 사용

이 문서는 DAX 식을 정의하는 데이터 모델러를 대상으로 합니다.

## <a name="background"></a>배경

평가 시간 오류를 발생시킬 수 있는 DAX 식을 작성할 때 두 가지 유용한 DAX 함수를 사용할 것을 고려할 수 있습니다.

- [ISERROR](/dax/iserror-function-dax) 함수 - 단일 식을 사용하고 해당 식에서 오류가 발생하는 경우 TRUE를 반환힙니다.
- [IFERROR](/dax/iferror-function-dax) 함수 - 두 개의 식을 사용합니다. 첫 번째 식에서 오류가 발생할 경우 두 번째 식의 값이 반환됩니다. 실제로는 [IF](/dax/if-function-dax) 함수 안에 ISERROR 함수를 중첩하는 보다 최적화된 구현입니다.

그러나 이러한 함수는 유용하고 이해하기 쉬운 식을 작성하는 데 기여할 수 있지만 계산 성능도 크게 저하될 수 있습니다. 이러한 함수는 필요한 스토리지 엔진 검색 수를 증가시키기 때문입니다.

대부분의 평가 시간 오류는 예기치 않은 공백이나 0 값 또는 잘못된 데이터 형식 변환으로 인해 발생합니다.

## <a name="recommendations"></a>권장 사항

ISERROR 및 IFERROR 함수를 사용하지 않는 것이 좋습니다. 대신 모델을 개발하고 식을 작성할 때 방어 전략을 적용합니다. 여기에는 다음이 포함될 수 있습니다.

- **모델에 고품질 데이터가 로드되는지 확인:** 파워 쿼리 변환을 사용하여 잘못되었거나 누락된 값을 제거 또는 대체하고 올바른 데이터 형식을 설정합니다. 잘못된 데이터 변환과 같은 오류가 발생하는 경우에도 파워 쿼리 변환을 사용하여 행을 필터링할 수 있습니다.

    모델 열 **Is Nullable** 속성을 Off로 설정하여 데이터 품질을 제어할 수도 있습니다. 그러면 데이터 새로 고침이 실패하는 경우 오류가 발생합니다. 이 오류가 발생하는 경우 성공적으로 새로 고친 결과로 로드된 데이터는 테이블에 유지됩니다.
- **IF 함수 사용:** IF 함수 논리 테스트 식은 오류 결과가 발생하는지 여부를 확인하는 데 사용할 수 있습니다. 참고로, ISERROR 및 IFERROR 함수와 마찬가지로 이 함수는 추가 스토리지 엔진 검색을 수행할 수 있지만 오류가 발생하지 않을 경우 더 나은 성능을 얻을 수 있습니다.
- **오류 허용 함수 사용:** 일부 DAX 함수는 오류 조건을 테스트하고 보정합니다. 이러한 함수를 사용하면 대신 반환되는 대체 결과를 입력할 수 있습니다. [DIVIDE](/dax/divide-function-dax) 함수가 이러한 예 중 하나입니다. 이 함수에 대한 추가 지침은 [DAX: DIVIDE 함수 및 나누기 연산자(/)](dax-divide-function-operator.md) 문서를 참조하세요.

## <a name="example"></a>예제

다음 측정값 식은 오류가 발생하는지 여부를 테스트합니다. 이 인스턴스에서는 BLANK를 반환합니다(IF 함수에 value-if-false 식을 제공하지 않는 경우에 해당).
```dax
= IF(ISERROR([Profit] / [Sales]))
```
이 다음 버전의 측정값 식은 IF 및 ISERROR 함수 대신 IFERROR 함수를 사용하여 개선된 것입니다.
```dax
= IFERROR([Profit] / [Sales], BLANK())
```
그러나 이 최종 버전의 측정값 식은 동일한 결과를 더 효율적이고 세련되게 달성합니다.
```dax
= DIVIDE([Profit], [Sales])
```