---
title: 다 대 다 관계 지침
description: 다 대 다 모델 관계를 개발하기 위한 지침입니다.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 11/25/2019
ms.author: v-pemyer
ms.openlocfilehash: 6ce82516413fe43cfbc1336e2f6f51003277fb4a
ms.sourcegitcommit: 3d6b27e3936e451339d8c11e9af1a72c725a5668
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2020
ms.locfileid: "76161297"
---
# <a name="many-to-many-relationship-guidance"></a>다 대 다 관계 지침

이 문서는 Power BI Desktop을 개발하는 데이터 모델러를 대상으로 합니다. 세 가지 다 대 다 모델링 시나리오를 설명합니다. 또한 모델에서 시나리오에 맞게 디자인하는 방법에 대한 지침을 제공합니다.

> [!NOTE]
> 이 문서에서 모델 관계를 소개하지는 않습니다. 관계, 해당 속성 또는 관계를 구성하는 방법을 잘 모르겠으면 먼저 [Power BI Desktop의 모델 관계](../desktop-relationships-understand.md) 문서를 읽어보시는 것이 좋습니다.
>
> 별모양 스키마 디자인을 살펴보는 것도 중요합니다. 자세한 내용은 [별모양 스키마 및 Power BI에서의 중요도 이해](star-schema.md)를 참조하세요.

사실상 세 가지 다 대 다 시나리오가 있습니다. 세 가지 시나리오는 다음 작업을 수행해야 하는 경우에 발생할 수 있습니다.

- [두 차원 유형 테이블 연결](#relate-many-to-many-dimensions)
- [두 팩트 유형 테이블 연결](#relate-many-to-many-facts)
- 팩트 유형 테이블이 차원 유형 테이블 행보다 높은 세분성으로 행을 저장하는 경우 [상위 세분성 팩트 유형 테이블 연결](#relate-higher-grain-facts)

## <a name="relate-many-to-many-dimensions"></a>다대다 차원 연결

예제를 사용하여 첫 번째 다 대 다 시나리오 유형을 살펴봅시다. 이 클래식 시나리오에서는 은행 고객과 은행 계좌라는 2개의 엔터티를 연결합니다. 고객이 여러 계정을 가질 수 있고, 계정에 여러 고객이 있을 수 있습니다. 계정에 여러 고객이 있는 경우 일반적으로 ‘공동 계정 소유자’라고 합니다. 

이러한 엔터티의 모델링은 간단합니다. 하나의 차원 유형 테이블에는 계정이 저장되고, 다른 차원 유형 테이블에는 고객이 저장됩니다. 차원 유형 테이블의 특성에 따라 각 테이블에는 ID 열이 있습니다. 두 테이블 간의 관계를 모델링하기 위해 세 번째 테이블이 필요합니다. 이 테이블을 일반적으로 ‘브리징 테이블’이라고 합니다.  이 예제에서는 고객-계정 연결마다 하나의 행을 저장하는 것이 목적입니다. 이 테이블에 ID 열만 포함되어 있을 경우 [‘팩트 없는 팩트 테이블’](star-schema.md#factless-fact-tables)이라고 합니다. 

다음은 테이블 3개로 이루어진 간단한 모델 다이어그램입니다.

![모델 다이어그램에는 테이블 3개가 포함되어 있습니다. 디자인은 다음 단락에서 설명합니다.](media/relationships-many-to-many/bank-account-customer-model-example.png)

첫 번째 테이블의 이름은 **Account**이고 **AccountID**와 **Account**라는 2개의 열이 있습니다. 두 번째 테이블의 이름은 **AccountCustomer**이고 **AccountID**와 **CustomerID**라는 2개의 열이 있습니다. 세 번째 테이블의 이름은 **Customer**이고 **CustomerID**와 **Customer**라는 2개의 열이 있습니다. 테이블 간에는 관계가 없습니다.

테이블을 연결하기 위해 일 대 다 관계 2개를 추가합니다. 다음은 업데이트된 관련 테이블 모델 다이어그램입니다. **Transaction**이라는 팩트 유형 테이블이 추가되었습니다. 이 테이블에는 계정 트랜잭션이 기록됩니다. 브리징 테이블과 모든 ID 열은 숨겨져 있습니다.

![이제 모델 다이어그램에 테이블 4개가 포함되어 있습니다. 모든 테이블을 연결하기 위해 일 대 다 관계를 추가했습니다.](media/relationships-many-to-many/bank-account-customer-model-related-tables-1.png)

관계 필터 전달의 작동 방식을 설명하는 데 도움이 되도록 모델 다이어그램이 테이블 행을 표시하도록 수정되었습니다.

> [!NOTE]
> Power BI Desktop 모델 다이어그램에는 테이블 행을 표시할 수 없습니다. 이 문서에서는 명확한 예제로 설명을 지원하기 위해 표시한 것입니다.

![이제 모델 다이어그램에 테이블 행이 표시됩니다. 행 세부 정보는 다음 단락에서 설명합니다.](media/relationships-many-to-many/bank-account-customer-model-related-tables-2.png)

네 테이블의 행 세부 정보는 다음 글머리 기호 목록에 설명되어 있습니다.

- **Account** 테이블에는 다음 2개의 행이 있습니다.
  - **AccountID** 1은 Account-01을 나타냅니다.
  - **AccountID** 2는 Account-02를 나타냅니다.
- **Customer** 테이블에는 다음 2개의 행이 있습니다.
  - **CustomerID** 91은 Customer-91을 나타냅니다.
  - **CustomerID** 92는 Customer-92를 나타냅니다.
- **AccountCustomer** 테이블에는 다음 3개의 행이 있습니다.
  - **AccountID** 1은 **CustomerID** 91에 연결되어 있습니다.
  - **AccountID** 1은 **CustomerID** 92에 연결되어 있습니다.
  - **AccountID** 3은 **CustomerID** 92에 연결되어 있습니다.
- **Transaction** 테이블에는 다음 3개의 행이 있습니다.
  - **Date** January 1 2019, **AccountID** 1, **Amount** 100
  - **Date** February 2 2019, **AccountID** 2, **Amount** 200
  - **Date** March 3 2019, **AccountID** 1, **Amount** -25

모델을 쿼리하면 어떻게 되는지 살펴봅시다.

다음은 **Transaction** 테이블의 **Amount** 열을 요약하는 두 개의 시각적 개체입니다. 첫 번째 시각적 개체는 계정을 기준으로 그룹화되므로, **Amount** 열의 합계는 ‘계정 잔액’을 나타냅니다.  두 번째 시각적 개체는 고객을 기준으로 그룹화되므로, **Amount** 열의 합계는 ‘고객 잔액’을 나타냅니다. 

![두 개의 보고서 시각적 개체가 나란히 표시됩니다. 시각적 개체는 다음 단락에서 설명합니다.](media/relationships-many-to-many/bank-account-customer-model-queried-1.png)

첫 번째 시각적 개체의 제목은 **Account Balance**이고 **Account**와 **Amount**라는 2개의 열이 있습니다. 다음 결과를 표시합니다.

- Account-01 잔액 금액은 75입니다.
- Account-02 잔액 금액은 200입니다.
- 합계는 275입니다.

두 번째 시각적 개체의 제목은 **Customer Balance**이고 **Customer**와 **Amount**라는 2개의 열이 있습니다. 다음 결과를 표시합니다.

- Customer-91 잔액 금액은 275입니다.
- Customer-92 잔액 금액은 275입니다.
- 합계는 275입니다.

테이블 행과 **Account Balance** 시각적 개체를 살펴보면 각 계정과 총 금액의 결과가 올바른 것을 확인할 수 있습니다. 각 계정 그룹화의 결과로 필터가 해당 계정의 **Transaction** 테이블로 전달되기 때문입니다.

그러나 **Customer Balance** 시각적 개체에는 결과가 올바르게 표시되지 않습니다. **Customer Balance** 시각적 개체에서 각 고객의 잔액이 총 잔액과 같습니다. 이 결과는 각 고객이 모든 계정의 공동 계정 소유자인 경우에만 올바른 결과일 수 있습니다. 이 예제는 해당 경우가 아닙니다. 문제는 필터 전달과 관련이 있습니다. 필터가 **Transaction** 테이블까지 전달되지 않습니다.

**Customer** 테이블에서 **Transaction** 테이블로 관계 필터 방향을 따릅니다. **Account** 및 **AccountCustomer** 테이블 간의 관계가 잘못된 방향으로 전달되고 있는 것이 분명합니다. 이 관계의 필터 방향을 **모두**로 설정해야 합니다.

![모델 다이어그램이 업데이트되었습니다. Account 및 AccountCustomer 테이블 간의 관계에 하나의 변경 내용이 적용되었습니다. 이제 양방향으로 모두 필터링됩니다.](media/relationships-many-to-many/bank-account-customer-model-related-tables-3.png)

![동일한 두 개의 보고서 시각적 개체가 나란히 표시됩니다. 첫 번째 시각적 개체는 변경되지 않았습니다. 두 번째 시각적 개체는 다른 결과를 표시하며 다음 단락에서 설명합니다.](media/relationships-many-to-many/bank-account-customer-model-queried-2.png)

예상대로 **Account Balance** 시각적 개체는 변경되지 않았습니다.

그러나 **Customer Balance** 시각적 개체는 이제 다음과 같은 결과를 표시합니다.

- Customer-91 잔액 금액은 75입니다.
- Customer-92 잔액 금액은 275입니다.
- 합계는 275입니다.

이제 **Customer Balance** 시각적 개체가 올바른 결과를 표시합니다. 직접 필터 방향을 따라가면서 고객 잔액이 계산된 방식을 확인합니다. 또한 보이는 값 합계가 ‘모든 고객’을 의미한다는 것을 이해합니다. 

모델 관계를 잘 모르는 사용자는 결과가 잘못된 것으로 결론을 내리고 다음과 같이 질문할 수 있습니다. ‘**Customer-91**과 **Customer-92**의 총 잔액이 350 (75 + 275)과 왜 다른가요?’ 

이 질문의 답변은 다 대 다 관계의 이해에 있습니다. 각 고객 잔액은 여러 계정 잔액의 더하기를 나타낼 수 있으므로 고객 잔액은 ‘비가산적’입니다. 

### <a name="relate-many-to-many-dimensions-guidance"></a>다대다 차원 연결 지침

차원 유형 테이블 간에 다 대 다 관계가 있는 경우 다음 지침을 제공합니다.

- 각 다 대 다 관련 엔터티를 모델 테이블로 추가하여 고유 식별자(ID) 열이 있도록 합니다.
- 연결된 엔터티를 저장할 브리징 테이블을 추가합니다.
- 세 테이블 간에 일 대 다 관계를 만듭니다.
- 양방향 관계 **1개**를 구성하여 필터 전달이 팩트 유형 테이블까지 계속 진행되도록 합니다.
- ID 값이 누락되는 것이 적절하지 않은 경우 ID 열의 **Null 허용 여부** 속성을 FALSE로 설정합니다. 누락된 값이 제공되면 데이터 새로 고침이 실패합니다.
- 브리징 테이블을 숨깁니다(보고에 필요한 추가 열 또는 측정값이 포함된 경우 제외).
- 보고에 적합하지 않은 ID 열을 숨깁니다(예: ID가 서로게이트 키인 경우).
- ID 열을 표시하는 것이 적합한 경우 관계의 “일” 쪽에 있도록 하고 “다” 쪽 열은 항상 숨깁니다. 이렇게 하면 최상의 필터 성능을 얻을 수 있습니다.
- 혼동이나 오해를 방지하기 위해 보고서 사용자에게 설명을 전달합니다. 텍스트 상자나 [시각적 개체 머리글 도구 설명](report-page-tooltips.md)을 사용하여 설명을 추가할 수 있습니다.

다대다 차원 유형 테이블은 직접 연결하지 않는 것이 좋습니다. 이 디자인 방법은 다 대 다 카디널리티를 사용해서 관계를 구성해야 합니다. 개념적으로 가능하긴 하지만, 관련 열에 중복 값이 포함됩니다. 하지만 차원 유형 테이블에 ID 열을 포함하는 것은 널리 허용되는 디자인 방법입니다. 차원 유형 테이블은 항상 ID 열을 관계의 “일” 쪽으로 사용해야 합니다.

## <a name="relate-many-to-many-facts"></a>다 대 다 팩트 연결

두 번째 다 대 다 시나리오 유형에서는 2개의 팩트 유형 테이블을 연결해야 합니다. 2개의 팩트 유형 테이블을 직접 연결할 수 있습니다. 이 디자인 방법은 빠르고 간단한 데이터 탐색에 유용할 수 있습니다. 그러나 분명히 이 디자인 방법은 일반적으로 권장되지 않습니다. 이유는 이 섹션의 뒷부분에서 설명합니다.

2개의 팩트 유형 테이블 **Order**와 **Fulfillment**가 포함된 예제를 살펴봅시다. **Order** 테이블에는 주문 라인당 하나의 행이 있고, **Fulfillment** 테이블에는 주문 라인당 0개 이상의 행이 포함될 수 있습니다. **Order** 테이블의 행은 판매 주문을 나타냅니다. **Fulfillment** 테이블의 행은 배송된 주문 항목을 나타냅니다. 다 대 다 관계는 2개의 **OrderID** 열을 연결하고 **Order** 테이블에서만 필터를 전달합니다(**Order**가 **Fulfillment**를 필터링함).

![모델 다이어그램에는 Order와 Fulfillment라는 2개의 테이블이 포함되어 있습니다. 다 대 다 관계는 두 OrderID 열을 연결하고 Order에서 Fulfillment로 필터링합니다.](media/relationships-many-to-many/order-fulfillment-model-example.png)

관계 카디널리티는 다 대 다로 설정되어 두 테이블에 중복된 **OrderID** 값을 저장할 수 있도록 지원합니다. 한 주문에 여러 라인이 있을 수 있으므로 **Order** 테이블에는 중복된 **OrderID** 값이 있을 수 있습니다. 한 주문에 여러 라인이 있을 수 있고 주문 라인이 여러 배송을 통해 처리될 수 있으므로 **Fulfillment** 테이블에도 중복된 **OrderID** 값이 있을 수 있습니다.

이제 테이블 행을 살펴봅시다. **Fulfillment** 테이블에서 주문 라인이 여러 배송을 통해 처리될 수 있음을 확인합니다. 주문 라인이 없으면 주문이 아직 처리되지 않은 것입니다.

![이제 모델 다이어그램에 테이블 행이 표시됩니다. 행 세부 정보는 다음 단락에서 설명합니다.](media/relationships-many-to-many/order-fulfillment-model-related-tables.png)

두 테이블의 행 세부 정보는 다음 글머리 기호 목록에 설명되어 있습니다.

- **Order** 테이블에는 다음 5개의 행이 있습니다.
  - **OrderDate** January 1 2019, **OrderID** 1, **OrderLine** 1, **ProductID** Prod-A, **OrderQuantity** 5, **Sales** 50
  - **OrderDate** January 1 2019, **OrderID** 1, **OrderLine** 2, **ProductID** Prod-B, **OrderQuantity** 10, **Sales** 80
  - **OrderDate** February 2 2019, **OrderID** 2, **OrderLine** 1, **ProductID** Prod-B, **OrderQuantity** 5, **Sales** 40
  - **OrderDate** February 2 2019, **OrderID** 2, **OrderLine** 2, **ProductID** Prod-C, **OrderQuantity** 1, **Sales** 20
  - **OrderDate** March 3 2019, **OrderID** 3, **OrderLine** 1, **ProductID** Prod-C, **OrderQuantity** 5, **Sales** 100
- **Fulfillment** 테이블에는 다음 4개의 행이 있습니다.
  - **FulfillmentDate** January 1 2019, **FulfillmentID** 50, **OrderID** 1, **OrderLine** 1, **FulfillmentQuantity** 2
  - **FulfillmentDate** February 2 2019, **FulfillmentID** 51, **OrderID** 2, **OrderLine** 1, **FulfillmentQuantity** 5
  - **FulfillmentDate** February 2 2019, **FulfillmentID** 52, **OrderID** 1, **OrderLine** 1, **FulfillmentQuantity** 3
  - **FulfillmentDate** January 1 2019, **FulfillmentID** 53, **OrderID** 1, **OrderLine** 2, **FulfillmentQuantity** 10

모델을 쿼리하면 어떻게 되는지 살펴봅시다. 다음은 **Order** 테이블의 **OrderID** 열을 기준으로 주문 및 처리 수량을 비교하는 테이블 시각적 개체입니다.

![테이블 시각적 개체에 OrderID, OrderQuantity, FulfillmentQuantity라는 3개의 열이 있습니다. 주문마다 하나씩, 3개의 행이 있습니다. OrderID 2와 3은 완전히 처리되지 않았습니다.](media/relationships-many-to-many/order-fulfillment-model-queried.png)

시각적 개체는 정확한 결과를 표시합니다. 그러나 모델의 유용성이 제한적입니다. 즉, **Order** 테이블의 **OrderID** 열로만 필터링하거나 그룹화할 수 있습니다.

### <a name="relate-many-to-many-facts-guidance"></a>다 대 다 팩트 연결 지침

일반적으로 다 대 다 카디널리티를 사용하여 두 팩트 유형 테이블을 직접 연결하지 않는 것이 좋습니다. 주요 이유는 이 모델을 사용할 경우 시각적 개체 필터 또는 그룹을 다양한 방식으로 보고할 수 없기 때문입니다. 이 예제에서는 시각적 개체가 **Order** 테이블의 **OrderID** 열로만 필터링하거나 그룹화할 수 있습니다. 추가 이유는 데이터 품질과 관련이 있습니다. 데이터에 무결성 문제가 있을 경우 ‘약한 관계’의 특성으로 인해 쿼리 중에 일부 행이 생략될 수 있습니다.  자세한 내용은 [관계 평가](../desktop-relationships-understand.md#relationship-evaluation)를 참조하세요.

팩트 유형 테이블을 직접 연결하는 대신, [별모양 스키마](star-schema.md) 디자인 원칙을 채택하는 것이 좋습니다. 차원 유형 테이블을 추가하면 됩니다. 그러면 차원 유형 테이블이 일 대 다 관계를 사용하여 팩트 유형 테이블에 연결됩니다. 이 디자인 방법은 유연성 있는 보고 옵션을 제공하므로 강력합니다. 이 방법을 사용하면 차원 유형 열 중 하나로 필터링하거나 그룹화하고 관련 팩트 유형 테이블을 요약할 수 있습니다.

더 나은 솔루션을 살펴봅시다.

![모델 다이어그램에는 OrderLine, OrderDate, Order, Fulfillment, Product, FulfillmentDate라는 6개의 테이블이 포함되어 있습니다. 모든 테이블이 연결되어 있습니다. 디자인은 다음 단락에서 설명합니다.](media/relationships-many-to-many/order-fulfillment-model-improved.png)

디자인이 다음과 같이 변경된 것을 확인합니다.

- 이제 모델에 **OrderLine**, **OrderDate**, **Product**, **FulfillmentDate**라는 4개의 추가 테이블이 있습니다.
- 4개의 추가 테이블은 모두 차원 유형 테이블이며, 일 대 다 관계를 통해 테이블이 팩트 유형 테이블에 연결되어 있습니다.
- **OrderLine** 테이블에는 **OrderLineID** 열이 있습니다. 이 열은 **OrderID** 값에 100을 곱하고 **OrderLine** 값을 더한 값인 각 주문 라인의 고유 식별자를 나타냅니다.
- 이제 **Order** 및 **Fulfillment** 테이블에 **OrderLineID** 열이 있으며, 더 이상 **OrderID** 및 **OrderLine** 열이 포함되지 않습니다.
- 이제 **Fulfillment** 테이블에 **OrderDate** 및 **ProductID** 열이 있습니다.
- **FulfillmentDate** 테이블은 **Fulfillment** 테이블에만 연결됩니다.
- 모든 고유 식별자 열은 숨겨집니다.

별모양 스키마 디자인 원칙을 적용하면 다음과 같은 혜택이 있습니다.

- 보고서 시각적 개체가 차원 유형 테이블의 보이는 열을 기준으로 ‘필터링하거나 그룹화’할 수 있습니다. 
- 보고서 시각적 개체가 팩트 유형 테이블의 보이는 열을 ‘요약’할 수 있습니다. 
- **OrderLine**, **OrderDate** 또는 **Product** 테이블에 적용된 필터가 두 팩트 유형 테이블에 모두 전달됩니다.
- 모든 관계는 일 대 다이고, 각 관계는 ‘강력한 관계’입니다.  데이터 무결성 문제가 마스킹 되지 않습니다. 자세한 내용은 [관계 평가](../desktop-relationships-understand.md#relationship-evaluation)를 참조하세요.

## <a name="relate-higher-grain-facts"></a>상위 세분성 팩트 연결

이 다 대 다 시나리오는 이 문서에서 이미 설명한 다른 두 시나리오와 전혀 다릅니다.

다음 4개의 테이블이 포함된 예제를 살펴봅시다. **Date**, **Sales**, **Product**, **Target**. **Date** 및 **Product**는 차원 유형 테이블이며, 일 대 다 관계를 통해 각각 **Sales** 팩트 유형 테이블에 연결되어 있습니다. 지금까지는 양호한 별모양 스키마 디자인입니다. 그러나 **Target** 테이블은 다른 테이블에 아직 연결되어 있지 않습니다.

![모델 다이어그램에는 Date, Sales, Product, Target이라는 4개의 테이블이 포함되어 있습니다. Target 테이블은 다른 테이블에 연결되어 있지 않습니다. 디자인은 다음 단락에서 설명합니다.](media/relationships-many-to-many/sales-targets-model-example.png)

**Target** 테이블에는 **Category**, **TargetQuantity**, **TargetYear**라는 3개의 열이 있습니다. 테이블 행에는 연도 및 제품 범주 세분성이 표시됩니다. 즉, 판매 성과를 측정하는 데 사용되는 목표는 각 제품 범주에 대해 매년 설정됩니다.

![Target 테이블에는 TargetYear, Category, TargetQuantity라는 3개의 열이 있습니다. 6개 행은 각각 세 가지 범주의 2019년 및 2020년 목표를 기록합니다.](media/relationships-many-to-many/sales-targets-model-target-rows.png)

**Target** 테이블에는 차원 유형 테이블보다 상위 수준의 데이터가 저장되므로 일 대 다 관계를 만들 수 없습니다. 관계 중 하나에만 적용됩니다. **Target** 테이블을 차원 유형 테이블에 연결할 수 있는 방법을 살펴봅시다.

### <a name="relate-higher-grain-time-periods"></a>상위 세분성 기간 연결

**Date** 및 **Target** 테이블 간의 관계는 일 대 다 관계여야 합니다. **TargetYear** 열 값이 날짜이기 때문입니다. 이 예제에서 각 **TargetYear** 열 값은 대상 연도의 첫 번째 날짜입니다.

> [!TIP]
> 일보다 높은 시간 세분성으로 팩트를 저장할 때는 열 데이터 형식을 **날짜**(또는 날짜 키를 사용하는 경우 **정수**)로 설정합니다. 열에 기간의 첫 번째 날을 나타내는 값을 저장합니다. 예를 들어 연도 기간은 해당 연도의 1월 1일로 기록되고, 월 기간은 해당 월의 첫 번째 날로 기록됩니다.

그러나 월 또는 날짜 수준 필터가 의미 있는 결과를 생성하도록 주의해야 합니다. 특별한 계산 논리가 없을 경우, 보고서 시각적 개체는 대상 날짜를 문자 그대로 각 연도의 첫 번째 날로 보고할 수 있습니다. 다른 모든 날과 1월을 제외한 모든 월은 목표 수량을 BLANK로 요약합니다.

다음 행렬 시각적 개체는 보고서 사용자가 연도에서 월로 드릴하는 경우 어떻게 되는지를 보여 줍니다. 시각적 개체가 **TargetQuantity** 열을 요약합니다. 행렬 행에 [데이터가 없는 항목 표시](../desktop-show-items-no-data.md) 옵션이 사용하도록 설정되었습니다.

![행렬 시각적 개체는 2020년 목표 수량을 270으로 표시합니다. 2020년 월을 표시하도록 확장하면 1월은 270이고 다른 모든 월 수준 목표 수량은 BLANK입니다.](media/relationships-many-to-many/sales-targets-model-matrix-blank-months-bad.png)

이 동작을 방지하려면 측정값을 사용하여 팩트 데이터의 요약을 제어하는 것이 좋습니다. 요약을 제어하는 한 가지 방법은 하위 수준 기간을 쿼리할 때 BLANK를 반환하는 것입니다. 일부 정교한 DAX로 정의하는 또 다른 방법은 하위 수준 기간에 값을 배분하는 것입니다.

[ISFILTERED](/dax/isfiltered-function-dax) DAX 함수를 사용하는 다음 측정값 정의를 살펴보세요. **Date** 또는 **Month** 열이 필터링 되지 않은 경우에만 값을 반환합니다.

```dax
Target Quantity =
IF(
    NOT ISFILTERED('Date'[Date])
        && NOT ISFILTERED('Date'[Month]),
    SUM(Target[TargetQuantity])
)
```

이제 다음 행렬 시각적 개체가 **Target Quantity** 측정값을 사용합니다. 모든 월별 목표 수량이 BLANK임을 보여 줍니다.

![행렬 시각적 개체는 2020년 목표 수량을 270으로 표시합니다. 2020년 월을 표시하도록 확장하면 모든 월 수준 목표 수량이 BLANK입니다.](media/relationships-many-to-many/sales-targets-model-matrix-blank-months-good.png)

### <a name="relate-higher-grain-non-date"></a>상위 세분성 연결(날짜 아님)

차원 유형 테이블의 날짜가 아닌 열을 팩트 유형 테이블에 연결하는 경우 다른 디자인 방법이 필요하며, 차원 유형 테이블보다 높은 세분성을 사용합니다.

**Product** 및 **Target** 테이블의 **Category** 열에는 중복 값이 포함되어 있습니다. 따라서 일 대 다 관계의 “일”이 없습니다. 이 경우 다 대 다 관계를 만들어야 합니다. 관계는 차원 유형 테이블에서 팩트 유형 테이블로 필터를 단방향으로 전달해야 합니다.

![모델 다이어그램의 조각은 Target 및 Product 테이블을 보여 줍니다. 다 대 다 관계를 통해 두 테이블을 연결합니다. 필터 방향은 Product에서 Target으로 진행됩니다.](media/relationships-many-to-many/sales-targets-model-relate-non-date.png)

이제 테이블 행을 살펴봅시다.

![모델 다이어그램에는 Target과 Product라는 2개의 테이블이 포함되어 있습니다. 다 대 다 관계를 통해 두 Category 열을 연결합니다. 행 세부 정보는 다음 단락에서 설명합니다.](media/relationships-many-to-many/sales-targets-model-relate-non-date-tables.png)

**Target** 테이블에는 각 대상 연도(2019년, 2020년)를 나타내는 행 2개와 범주 2개(Clothing, Accessories)가 있습니다. **Product** 테이블에는 세 가지 제품이 있습니다. 두 제품은 clothing 범주에 속하고, 한 제품은 accessories 범주에 속합니다. clothing 색 중 하나는 녹색이고 나머지 두 제품은 파란색입니다.

**Product** 테이블의 **Category** 열을 기준으로 그룹화된 테이블 시각적 개체는 다음과 같은 결과를 생성합니다.

![테이블 시각적 개체에는 Category와 TargetQuantity라는 2개의 열이 있습니다. Accessories는 60, Clothing은 40, 합계는 100입니다.](media/relationships-many-to-many/sales-targets-model-visual-category-targets.png)

이 시각적 개체는 올바른 결과를 생성합니다. 이제 **Product** 테이블의 **Color** 열을 사용하여 목표 수량을 그룹화하면 어떻게 되는지를 살펴봅시다.

![테이블 시각적 개체에는 Color와 TargetQuantity라는 2개의 열이 있습니다. Blue는 100, Green은 40, 합계는 100입니다.](media/relationships-many-to-many/sales-targets-model-visual-color-targets-bad.png)

이 시각적 개체는 잘못된 데이터 표현을 생성합니다. 어떤 문제가 발생한 것일까요?

**Product** 테이블의 **Color** 열 필터가 2개의 행을 반환합니다. 행 중 하나는 Clothing 범주에 속하고, 다른 행은 Accessories 범주에 속합니다. 두 범주 값이 **Target** 테이블에 필터로 전달됩니다. 즉, 파란색이 두 범주의 제품에 사용되었기 때문에 ‘해당 범주’가 대상을 필터링하는 데 사용됩니다. 

이 동작을 방지하려면, 앞에서 설명한 대로 측정값을 사용하여 팩트 데이터의 요약을 제어하는 것이 좋습니다.

다음 측정값 정의를 살펴보세요. 범주 수준 아래에 있는 모든 **Product** 테이블 열이 필터에 대해 테스트 됩니다.

```dax
Target Quantity =
IF(
    NOT ISFILTERED('Product'[ProductID])
        && NOT ISFILTERED('Product'[Product])
        && NOT ISFILTERED('Product'[Color]),
    SUM(Target[TargetQuantity])
)
```

이제 다음 테이블 시각적 개체가 **Target Quantity** 측정값을 사용합니다. 모든 색 목표 수량이 BLANK임을 보여 줍니다.

![테이블 시각적 개체에는 Color와 TargetQuantity라는 2개의 열이 있습니다. Blue는 BLANK, Green은 BLANK, 합계는 100입니다.](media/relationships-many-to-many/sales-targets-model-visual-color-targets-good.png)

최종 모델 디자인은 다음과 같이 표시됩니다.

![모델 다이어그램은 일 대 다 관계를 통해 Date 및 Target 테이블이 연결되었음을 보여 줍니다. Product 및 Target 테이블은 다 대 다 관계를 통해 연결되었으며 Product에서 Target으로 필터링됩니다.](media/relationships-many-to-many/sales-targets-model-example-final.png)

### <a name="relate-higher-grain-facts-guidance"></a>상위 세분성 팩트 연결 지침

차원 유형 테이블을 팩트 유형 테이블에 연결해야 하고, 팩트 유형 테이블이 차원 유형 테이블 행보다 높은 세분성으로 행을 저장하는 경우 다음 지침을 제공합니다.

- 상위 세분성 팩트 날짜의 경우:
  - 팩트 유형 테이블에 기간의 첫 번째 날짜를 저장합니다.
  - 날짜 테이블과 팩트 유형 테이블 간에 일 대 다 관계를 만듭니다.
- 다른 상위 세분성 팩트의 경우:
  - 차원 유형 테이블과 팩트 유형 테이블 간에 다 대 다 관계를 만듭니다.
- 두 유형 모두:
  - 측정값 논리를 사용하여 요약을 제어합니다. 하위 수준 차원 유형 열을 사용하여 필터링 또는 그룹화하는 경우 BLANK를 반환합니다.
  - 요약 가능한 팩트 유형 테이블 열을 숨깁니다. 이 경우 측정값만 팩트 유형 테이블을 요약하는 데 사용할 수 있습니다.

## <a name="next-steps"></a>다음 단계

이 문서와 관련된 보다 자세한 내용을 알아보려면 다음 리소스를 참조하세요.

- [Power BI Desktop의 모델 관계](../desktop-relationships-understand.md)
- [별모양 스키마 및 Power BI에서의 중요성 이해](star-schema.md)
- 질문이 있으십니까? [Power BI 커뮤니티에 질문하세요.](https://community.powerbi.com/)
