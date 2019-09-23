---
ms.openlocfilehash: cd6ea6fd52f929e2cd254214cf0e8c96e858f6c2
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "61273637"
---
Power BI를 통해 완전히 다른 데이터 원본에서 제공하는 테이블을 비롯하여 여러 테이블 간에 관계를 만들 수 있습니다. Power BI Desktop의 **관계** 보기에서 모든 데이터 모델에 대한 이러한 관계를 볼 수 있습니다.

![](media/7-5-table-relationships-and-dax/dax-relationships_1.png)

## <a name="dax-relational-functions"></a>DAX 관계형 함수
DAX에는 설정된 관계가 있는 테이블과 상호 작용할 수 있도록 해주는 **관계형 함수**가 있습니다.

DAX 함수를 사용하여 열의 값을 반환하거나 관계의 모든 행을 반환할 수 있습니다.

예를 들어 **RELATED** 함수는 관계를 따르고 열 값을 반환하는 반면, **RELATEDTABLE**은 관계를 따르고 관계된 행만을 포함하도록 필터링된 모든 테이블을 반환합니다.

![](media/7-5-table-relationships-and-dax/dax-relationships_2.png)

**RELATED** 함수는 *다대일* 관계에서 작동하는 반면, **RELATEDTABLE**은 *일대일* 관계에서 작동합니다.

관계형 함수를 사용하여 여러 테이블의 값을 포함하는 식을 작성할 수 있습니다. DAX는 관계의 체인 길이에 상관없이 이러한 함수를 사용하여 결과를 반환합니다.

> [Alberto Ferrari, SQLBI](http://www.sqlbi.com/learning-dax)의 비디오 콘텐츠 출처
> 
> 

