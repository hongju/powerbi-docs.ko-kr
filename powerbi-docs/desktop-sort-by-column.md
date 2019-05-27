---
title: Power BI Desktop의 열 기준 정렬
description: Power BI Desktop의 열 기준 정렬
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 53fc561e2f8dcb4869eff6e6fd172c8a3663840d
ms.sourcegitcommit: 10a87c016f497dbeba32f94ed1f3688a70816fea
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/09/2019
ms.locfileid: "65513979"
---
# <a name="sort-by-column-in-power-bi-desktop"></a>Power BI Desktop의 열 기준 정렬
**Power BI Desktop**과 **Power BI 서비스**에서는 다양한 데이터 필드로 정렬하여 시각적 개체의 모양을 변경할 수 있습니다. 시각적 개체의 정렬 방법을 변경하여 전달하려는 정보를 강조 표시하고 해당 추세(또는 강조점)에 시각적 효과를 반영했는지 확인할 수 있습니다.

숫자 데이터(예: 판매 수치) 또는 텍스트 데이터(예: 주 이름) 중 어떤 데이터를 사용하든지 시각화를 원하는 대로 정렬하고 모양으로 만들 수 있습니다.  **Power BI**는 여러 다양한 정렬 방법과 사용 가능한 간편한 메뉴를 제공합니다. 다음 이미지에서처럼 시각적 개체에서 줄임표(...)를 선택한 다음, 정렬하려는 순서대로 필드를 선택합니다.

![추가 옵션 메뉴](media/desktop-sort-by-column/sortbycolumn_2.png)

## <a name="more-depth-and-an-example"></a>더 구체적인 예제
더 구체적인 예제와, **Power BI Desktop**에서 어떻게 작동하는지 살펴보겠습니다.

다음과 같은 시각화는 제조업체 이름별로 비용, 수량 및 금액을 보여줍니다. 추가로 정렬하기 전에 시각화 모양은 다음과 같습니다.

![초기 시각화](media/desktop-sort-by-column/sortbycolumn_1.png)

이 시각적 개체는 현재 **SalesQuantity**를 기준으로 정렬되어 있습니다. 범례에 대해 오름차순으로 표시된 막대의 색을 찾아 알 수 있지만 현재 정렬 열을 확인하는 더 나은 방법으로 시각적 개체의 오른쪽 위 모서리에 있는 줄임표 메뉴(...)를 사용하는 것입니다. 줄임표를 선택하면 다음이 표시됩니다.

![추가 옵션 메뉴](media/desktop-sort-by-column/sortbycolumn_2.png)

* 현재 정렬 필드는 **SalesQuantity**이며 **정렬 기준 SalesQuantity**가 굵게 표시되고 노란색 막대가 있다는 팩트로 나타냅니다. 

* 작은 아이콘 **A/Z**(Z 위에 A) 및 아래쪽 화살표으로 표시된 대로 현재 정렬 방향은 오름차순입니다.

다음 두 섹션에서 독립적으로 정렬 필드 및 방향을 살펴보겠습니다.

## <a name="selecting-which-column-to-use-for-sorting"></a>정렬에 사용할 열 선택
**추가 옵션** 메뉴에서 **정렬 기준 SalesQuantity** 옆의 노란색 막대는 시각적 개체가 **SalesQuantity** 열로 정렬되었음을 나타냅니다. 다른 열을 기준으로 정렬하는 방법도 간단합니다. 줄임표를 선택하여 줄임표 메뉴를 표시한 다음, 다른 열을 선택합니다.

다음 이미지에서는 정렬하려는 기준 열로 *DiscountAmount*를 선택했습니다. 이 열은 시각적 개체에서 막대가 아닌 한 개의 줄로 나타납니다. **정렬 기준 DiscountAmount**를 선택한 후의 모양은 다음과 같습니다.

![정렬 기준 DiscoutAmount](media/desktop-sort-by-column/sortbycolumn_3.png)

시각적 개체가 어떻게 변경되었는지 확인합니다. 이제 값은 가장 높은 DiscountAmount 값(이 시각적 개체의 경우, Fabrikam Inc.)에서 가장 작은 값인 Northwind Traders까지 정렬됩니다. 

그러나 내림차순 대신 오름차순으로 정렬하려고 한다면 어떨까요? 다음 섹션에서는 이 작업이 얼마나 쉬운지 보여 줍니다.

## <a name="selecting-the-sort-order---smallest-to-largest-largest-to-smallest"></a>정렬 순서(작은 값-큰 값, 큰 값-작은 값)를 선택합니다.
이전 이미지의 **옵션** 메뉴를 자세히 살펴보면 **정렬 기준 DiscountAmount** 옆의 아이콘에 **Z/A**(A 위에 Z)가 표시된 것을 알 수 있습니다. 직접 살펴보겠습니다.

![내림차순 정렬](media/desktop-sort-by-column/sortbycolumn_4.png)

**Z/A**가 표시되면 시각적 개체가 선택한 열을 기준으로 가장 큰 값에서 가장 작은 값으로 정렬되는 것을 의미합니다. 이러한 동작을 변경하려는 경우 문제가 되지 않습니다. **Z/A** 아이콘을 탭하거나 클릭하면 정렬 순서가 **A/Z**로 변경되고 시각적 개체가 선택한 열을 기준으로 작은 값에서 큰 값으로 정렬됩니다.

다음은 동일한 시각적 개체의 순서를 변경하기 위해 **정렬 기준 DiscountAmount** 메뉴 항목에서 **Z/A** 아이콘을 탭한 후의 모양입니다. 이제 Northwind Traders가 나열된 첫 번째 제조업체이고 Fabrikam Inc.가 앞과 반대로 마지막입니다.

![오름차순 정렬](media/desktop-sort-by-column/sortbycolumn_5.png)

정렬 기준으로 시각적 개체에 포함된 어떤 열이든 사용할 수 있습니다. 정렬할 기준 열로 SalesQuantity를 간편하게 선택하여 **정렬 기준 SalesQuantity**에서 가장 판매량이 높은 제조업체를 표시해도 시각적 개체에 있는 다른 열은 그대로 유지됩니다. 그러나 해당 제조업체에는 적용됩니다. 이러한 설정을 통해 시각적 개체를 살펴보겠습니다.

![정렬 기준 SalesQuantity](media/desktop-sort-by-column/sortbycolumn_6.png)

## <a name="sort-using-the-sort-by-column-button"></a>열 기준 정렬 단추를 사용하여 정렬
데이터를 정렬하는 다른 방법이 있습니다. 바로 **모델링** 리본에 있는 **열 기준 정렬** 단추를 사용하는 것입니다.

![열 기준 정렬 단추](media/desktop-sort-by-column/sortbycolumn_8.png)

이 정렬 방식은 **필드** 창에서 열을 선택한 다음, **열 기준 정렬** 단추를 선택하여 시각적 개체를 정렬할 방식(기준으로 사용할 열)을 선택합니다. **열 기준 정렬** 단추를 활성화하려면 **필드** 창에서 정렬하려는 열(필드)을 선택해야 합니다. 그렇지 않으면 단추는 비활성화 상태입니다.

일반적인 예제를 살펴보겠습니다. 연도의 월별 데이터가 있고 시간 순서대로 정렬하고자 합니다. 다음 단계는 방법을 알아봅니다.

1. 먼저 시각적 개체는 선택되어 있으나 **필드** 창에서 선택된 열이 없습니다. **열 기준 정렬** 단추가 비활성화(회색으로 표시)되어 있습니다.
   
   ![비활성 열 기준 정렬 단추](media/desktop-sort-by-column/sortbycolumn_9.png)

2. **필드** 창에서 정렬하려는 열을 선택하면 **열 기준 정렬** 단추가 활성화됩니다.
   
   ![활성 열 기준 정렬 단추](media/desktop-sort-by-column/sortbycolumn_10.png)
3. 이제 선택한 시각적 개체로 기본값(*MonthName*) 대신 *MonthOfYear*를 선택할 수 있습니다. 이제 시각적 개체가 원하는 순서인 연도의 월별로 정렬됩니다.
   
   ![열 기준 정렬 메뉴](media/desktop-sort-by-column/sortbycolumn_11.png)

이것으로 끝입니다! **필드** 창에서 열을 선택하여 **열 기준 정렬** 단추를 활성화해야 하는 것을 기억하세요.

## <a name="getting-back-to-default-column-for-sorting"></a>기본 열 정렬로 되돌리기
원하는 열을 기준으로 정렬할 수 있지만 시각적 개체를 기본 정렬 열로 되돌리고 싶을 때도 있습니다. 그러나 문제가 되지 않습니다. 정렬 열을 선택한 시각적 개체에 대해(이전에 배운 것처럼 선택한 정렬 열에는 줄임표 메뉴 옆에 노란색 막대가 표시됨) **추가 옵션** 메뉴를 열고 해당 열을 다시 선택하면 시각화가 기본 정렬 열로 되돌려집니다.

예를 들어 다음은 이전 차트입니다.

![초기 시각화](media/desktop-sort-by-column/sortbycolumn_6.png)

해당 메뉴로 돌아가 **SalesQuantity**를 다시 선택하면 다음 이미지처럼 시각적 개체가 **Manufacturer**를 기준으로 사전순으로 정렬되는 기본 상태가 됩니다.

![기본 정렬 순서](media/desktop-sort-by-column/sortbycolumn_7.png)

시각적 개체를 정렬하는 다양한 옵션을 통해 손쉽게 차트 또는 이미지를 만들 수 있습니다.

