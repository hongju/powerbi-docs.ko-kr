---
ms.openlocfilehash: 8af5b1cf243d599ab68e9c2db1a3c6003f82c29f
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "61273640"
---
**DAX**를 소개하기 위해 설계된 Power BI **단계별 학습** 섹션을 시작합니다.

**DAX**는 **데이터 분석 식**의 약자로 Power BI 전체에서 사용되는 수식 언어입니다(Power BI 숨은 기능에서도 사용함). 또한 DAX는 Powerpivot과 SSAS 테이블 형식과 같은 Microsoft의 다른 제품에도 있지만 단계별 학습의 이 컬렉션은 DAX를 사용하는 방법 및 Power BI에서 사용자가 사용할 수 있는 방법에 중점을 둡니다.

## <a name="dax-and-this-guided-learning-video-series"></a>DAX 및 단계별 학습 비디오 시리즈
이 **단계별 학습** 섹션의 목표는 유명한 DAX 전문가인 [Alberto Ferrari](http://www.sqlbi.com/learning-dax)가 설명한(그리고 경험으로 학습한) DAX에 대해 인지하는 방법, 작동 방법 및 가장 유용한 기능과 같은 DAX 기본 사항 및 기본 항목을 알려주는 것입니다.

![Alberto Ferrari의 초상화](media/7-1-intro-to-dax/intro_dax_6_alberto_ferrari.png)

**DAX**에 대한 이 **단계별 학습** 섹션의 비디오는 DAX 수식 언어의 작동 원리의 관점에서 DAX 기본 사항을 설명합니다. DAX 수식을 처음부터 만들 경우에 유용하지만 **쿼리 편집기**에서 쿼리를 만드는 것처럼 Power BI에서 DAX 수식을 생성하는 방법을 이해하는 데에도 매우 유용합니다.

## <a name="in-this-video---introduction-to-dax"></a>이 비디오에서 - DAX 소개
DAX 개념은 쉽고 간단하지만 DAX는 강력합니다. DAX는 완벽하게 사용하고 이해하기 어려울 수 있는 몇 가지 고유한 프로그래밍 개념 및 패턴을 사용합니다. 언어를 배우는 전통적인 방법은 DAX에 대한 가장 좋은 방법이 아닐 수 있으므로 이 비디오의 목표는 나중에 Power BI 작업에서 도움을 줄 개념과 이론을 알려 주는 것입니다.

DAX는 기능 언어입니다. 즉, 실행되는 전체 코드가 함수 내에 포함됩니다. 

DAX에서 함수는 다른 중첩된 함수, 조건문 및 값 참조를 포함할 수 있습니다. DAX의 실행은 가장 안쪽 함수 또는 매개 변수부터 시작해서 바깥쪽으로 작동합니다. Power BI에서 DAX 수식은 한 줄에 기록되므로 함수를 올바르게 서식 지정하는 것이 가독성을 위해 중요합니다.

DAX는 두 개의 기본 데이터 형식에 테이블을 함께 사용 하도록 설계 되었습니다. **숫자** 하 고 **다른**합니다. **숫자**는 정수, 10진수 및 통화를 포함할 수 있습니다.    **기타**는 *문자열* 및 이진 개체를 포함할 수 있습니다.  즉 DAX 함수를 한 가지 형식의 숫자에서 작동하도록 작성하는 경우 다른 숫자 데이터에서 작동한다는 것을 확신할 수 있습니다.

DAX는 연산자 오버로드를 사용합니다. 즉 계산에서 데이터 형식을 섞을 수 있으며 결과는 입력에 사용되는 데이터의 형식에 따라 변경됩니다. 변환이 자동으로 발생합니다. 즉, Power BI에서 사용되는 열의 데이터 형식을 알 필요가 없지만 경우에 따라 변환이 예기치 못한 방식으로 발생할 수 있음을 의미하기도 합니다. 연산자가 예상한 대로 동작하는지 확인하기 위해 사용 중인 데이터를 이해하는 것이 좋습니다.

하나의 데이터 형식은 특히 있습니다에서는 함께 작업할 가능성이 훨씬 Power BI에 있는: **DateTime**합니다. **날짜/시간**은 정수와 소수 부분을 모두 사용하여 부동 소수점 값으로 저장됩니다. 날짜/시간을 1900년 3월 1일 이후의 모든 시간 간격을 계산하기 위해 정확하게 사용할 수 있습니다.

> [Alberto Ferrari, SQLBI](http://www.sqlbi.com/learning-dax/?utm_source=powerbi&utm_medium=marketing&utm_campaign=after-summit)의 비디오 콘텐츠 출처
> 
> 

