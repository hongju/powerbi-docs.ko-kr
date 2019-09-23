---
ms.openlocfilehash: f4043a5a8deac0596b58519183988f6ae574458e
ms.sourcegitcommit: 226b47f64e6749061cd54bf8d4436f7deaed7691
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/09/2019
ms.locfileid: "70847711"
---
DAX를 사용하여 만들 수 있는 두 가지 기본 계산이 있습니다.

* **계산 열**
* **계산 측정값**

그 중 하나를 만드는 방법을 살펴보기 전에 **계산 된 열** 또는 **계산 된 측정값** 중 하나를 만들 때 사용하는 테이블 및 열에 대한 DAX 구문을 파악하는 것이 좋습니다.

## <a name="dax-table-and-column-name-syntax"></a>DAX 테이블 및 열 이름 구문
새 열 또는 측정값을 만드는 경우 DAX에서 테이블 이름의 일반 형식을 알아야 합니다.

    'Table Name'[ColumnName]

(위와 같이)테이블 이름에 공백이 있는 경우 작은따옴표로 테이블 이름을 묶어야 합니다. 테이블 이름에 공백이 없으면 작은따옴표를 생략할 수 있기에 구문을 다음과 같이 표시합니다.

    TableName[ColumnName]

다음 이미지에서는 Power BI에서 생성된 DAX 수식을 보여 줍니다.

![](media/7-2-dax-calculation-types/dax-calc-types_1.png)

테이블 이름을 완전히 생략하거나 열 이름만 사용할 수 있지만 이는 지우기 기능을 작성하는 데 적절한 방법이 아닙니다(따라서 DAX 코드 지우기의 경우에도 해당). 열 이름은 항상 대괄호를 포함해야 합니다.

*항상* 다음을 수행하는 모범 사례입니다.

* 테이블 이름에 공백 없음
* 수식에서 테이블 이름 항상 포함(DAX를 사용하는 경우에도 생략하지 않음)

## <a name="creating-calculated-columns"></a>계산 열 만들기
값을 조각화하거나 필터링하려는 경우 또는 테이블의 모든 행을 계산하려는 경우 **계산 열**이 유용합니다.

**모델링** 탭에서 **새 열**을 선택하여 Power BI Desktop에서 계산 열을 만들 수 있습니다. 만든 새 열을 볼 수 있고 **수식 입력줄**이 채워지며 DAX 수식에 대해 준비가 완료되었기 때문에 **데이터** 보기가 좋습니다(**보고서** 또는 **관계** 보기 대신).

![](media/7-2-dax-calculation-types/dax-calc-types_2a.png)

**새 열** 단추를 선택하면 **수식 입력줄**은 기본 열 이름으로 채워지고(물론 수식에 맞게 변경) **=** 연산자 및 새 열이 다음 이미지에 보이는 대로 데이터 표에 나타납니다.

![](media/7-2-dax-calculation-types/dax-calc-types_3.png)

계산 열에 대한 필수 요소는 다음과 같습니다.

* 새 열 이름
* 하나 이상의 함수 또는 식

계산 열 수식에서 테이블 또는 열을 참조하는 경우 테이블에서 행을 지정하지 않아도 됩니다. Power BI에서 각 계산에 대한 현재 행의 열을 계산합니다.

## <a name="creating-calculated-measures"></a>계산 측정값 만들기
백분율 또는 비율을 계산하거나 복잡한 집계가 필요할 때 **계산 측정값**을 사용합니다. DAX 수식을 사용하여 측정값을 만들려면 **모델링** 탭에서 **새 측정값** 단추를 선택합니다. **수식 입력줄**을 보여 주고 쉽게 DAX 수식을 작성할 수 있기 때문에 Power BI Desktop에서 **데이터** 보기가 좋습니다.

![](media/7-2-dax-calculation-types/dax-calc-types_4.png)

**측정값**을 사용하면 새 측정값 아이콘이 측정값의 이름을 가진 **필드** 창에 표시됩니다. **수식 입력줄**은 DAX 수식의 이름으로 다시 채워집니다(이 경우 측정값으로 채워짐).

![](media/7-2-dax-calculation-types/dax-calc-types_5.png)

계산 측정값에 대한 필수 요소는 계산 열의 경우와 동일합니다.

* 새 측정값 이름
* 하나 이상의 함수 또는 식

> [Alberto Ferrari, SQLBI](http://www.sqlbi.com/learning-dax)의 비디오 콘텐츠 출처
> 
> 

