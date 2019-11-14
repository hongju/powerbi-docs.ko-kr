---
ms.openlocfilehash: c3b1b7288d0d277fc866ea47887335d10279c6cc
ms.sourcegitcommit: a5853ef44ed52e80eabee3757bb6887fa400b75b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73799996"
---
DAX를 사용하면 데이터의 모양을 지정하고 형성하거나 그렇지 않으면 분석하는 데 사용할 수 있는 많은 함수가 있습니다. 이러한 함수는 소수의 범주로 그룹화할 수 있습니다.

* **집계** 함수
* **계산** 함수
* **논리** 함수
* **정보** 함수
* **텍스트** 함수
* **날짜** 함수

Excel과 유사하게 Power BI Desktop **수식 입력줄**에 수식을 입력하기 시작할 때 사용할 수 있는 함수 중 어떤 것을 선택할지 결정할 수 있도록 사용 가능한 함수의 목록을 표시합니다. 키보드의 **위** 및 **아래** 화살표 키를 사용하여 사용 가능한 함수를 강조 표시할 수 있고 간략한 설명이 표시됩니다.

Power BI에서는 지금까지 입력한 문자와 일치하는 함수를 표시하므로 S를 입력하면 S로 시작하는 함수만 목록에 나타납니다.   Su를 입력하는 경우 해당 이름에 문자 시퀀스 Su를 포함하는 함수만이 목록에 표시됩니다(Su로 시작하지 않아도 해당 문자 시퀀스를 포함하기만 하면 됨).    

![](media/7-3-dax-functions/dax-functions_1.png)

이러한 방식으로 쉽게 DAX를 실험하고 Power BI에서 사용할 수 있는 다양한 DAX 함수 각각을 찾을 수 있습니다. 입력하기 시작하면 Power BI에서 함께 도움을 줍니다.

시작된 DAX 수식을 가져오는 방법을 알았으므로 이러한 각 함수 범주를 차례로 살펴보겠습니다.

## <a name="aggregation-functions"></a>집계 함수
DAX에는 일반적으로 사용되는 다음 함수를 비롯한 다양한 **집계** 함수가 있습니다.

* 합계
* 평균값
* 최소값
* 최대값
* SUMX(및 기타 *X* 함수)

이러한 함수는 숫자 열에서만 작동하며 일반적으로 한 번에 하나의 열만 집계할 수 합니다.

그러나 **SUMX**처럼 **X**로 끝나는 특별한 집계 함수는 여러 열에서 작동할 수 있습니다. 이러한 함수는 테이블에서 반복되며 각 행에 대해 식을 평가합니다.

## <a name="counting-functions"></a>계산 함수
DAX에서 자주 사용하는 **계산** 함수는 다음을 포함합니다.

* COUNT
* COUNTA
* COUNTBLANK
* COUNTROWS
* DISTINCTCOUNT

이러한 함수는 고유 값, 비어 있지 않은 값, 테이블 행 등 여러 요소의 개수를 계산합니다.

## <a name="logical-functions"></a>논리 함수
DAX에서 **논리** 함수의 컬렉션은 다음을 포함합니다.

* AND
* 또는
* NOT
* IF
* IFERROR

이러한 특수 함수는 연산자를 사용하여 표현될 수도 있습니다.  예를 들어 **AND**은 DAX 수식에서 **&&** (로 바뀜)로 입력될 수 있습니다.

DAX 코드의 가독성을 위해 수식에 둘 이상의 조건이 필요하지만 그렇지 않으면 함수 이름 자체를 사용하는 모범 사례인 연산자(예: **&&** )를 사용할 수 있습니다(예: **AND**).

## <a name="information-functions"></a>정보 함수
DAX에서 **정보** 함수는 다음을 포함합니다.

* ISBLANK
* ISNUMBER
* ISTEXT
* ISNONTEXT
* ISERROR

이러한 함수는 상황에 맞게 유용할 수 있는 반면 데이터 형식을 제공하는 이러한 함수에 의존하지 않고 시간에 앞서 열의 데이터 형식을 알 수 있는 값이 있습니다.

DAX에서는 **MAX** 및 **MIN** 함수를 사용하여 값을 집계하고 비교합니다.  

## <a name="text-functions"></a>텍스트 함수
DAX에서 **텍스트** 함수는 다음을 포함합니다.

* CONCATENTATE
* REPLACE
* SEARCH
* UPPER
* FIXED

이러한 **텍스트**는 동일한 이름을 갖는 Excel 함수와 매우 유사하게 작동하므로 따라서 Excel이 텍스트 기능을 처리하는 방법에 대해 잘 알고 있다면 이미 한 발 앞서 있는 것입니다. 그렇지 않으면 항상 Power BI에서 이러한 함수를 실험하고 어떻게 동작하는지에 대해 자세히 알아볼 수 있습니다.

## <a name="date-functions"></a>날짜 함수
DAX는 다음과 같은 **날짜** 함수를 포함합니다.

* DATE
* HOUR
* NOW
* EOMONTH
* WEEKDAY

이러한 함수는 *날짜* 값에서 정보를 추출하고 계산하는 데 유용하지만 날짜 테이블을 사용하는 시간 인텔리전스에 적용되지 않습니다.

> [Alberto Ferrari, SQLBI](https://www.sqlbi.com/learning-dax)의 비디오 콘텐츠 출처
> 
> 

