---
title: Power BI Desktop의 계산된 테이블 사용
description: Power BI Desktop의 계산된 테이블
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/07/2019
ms.author: davidi
LocalizationGroup: Model your data
ms.openlocfilehash: 7c7d3b04b8c954ae220fb8b157b183f615abd39c
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "65239478"
---
# <a name="using-calculated-tables-in-power-bi-desktop"></a>Power BI Desktop의 계산된 테이블 사용
계산된 테이블을 사용하면 새 테이블을 모델에 추가할 수 있습니다. 그러나 값을 쿼리하고 데이터 소스에서 새 테이블의 열로 로드하는 대신 테이블 값을 정의하는 DAX(Data Analysis Expressions) 수식을 만듭니다. Power BI Desktop에서 보고서 뷰나 데이터 뷰의 새 테이블 기능을 사용하여 계산된 열이 생성됩니다.

대부분의 경우 외부 데이터 원본에서 모델로 데이터를 가져옵니다. 그러나 계산된 테이블에는 특정한 이점이 있습니다. 계산된 테이블은 보통, 즉석 또는 쿼리의 일부로 계산된 것이 아닌 모델의 일부로 저장하려는 데이터와 중간 계산에 가장 적합합니다.

쿼리의 일부로 만든 테이블과 달리, 보고서 뷰나 데이터 뷰에서 만든 계산된 테이블은 이미 모델에 로드한 데이터를 기반으로 합니다. 예를 들어, 두 테이블을 연결하거나 크로스 조인하려 할 수 있습니다.

일반 테이블처럼 계산된 테이블에는 다른 테이블과의 관계가 있을 수 있습니다. 계산된 테이블의 열에는 데이터 형식, 서식이 있으며 데이터 범주에 속할 수 있습니다. 열에 원하는 대로 이름을 지정하고 다른 필드처럼 보고서 시각화에 추가할 수 있습니다. 데이터를 가져오는 테이블이 새로 고쳐지거나 어떤 식으로든 업데이트되면 계산된 테이블이 다시 계산됩니다.

계산된 테이블은 Power BI Desktop에서와 같이 관계형 데이터 작업에 사용되는 수식 언어인 DAX([Data Analysis Expressions](https://msdn.microsoft.com/library/gg413422.aspx))를 사용하여 결과를 계산합니다. DAX에는 200개가 넘는 함수, 연산자 및 구문 라이브러리가 포함되어 데이터 분석 결과를 계산하는 수식을 만들 때 엄청난 유연성을 제공합니다.

## <a name="lets-look-at-an-example"></a>예를 살펴보겠습니다.
Contoso의 프로젝트 관리자인 Jeff에게는 북서부 직원이 담긴 테이블과 남서부 직원이 담긴 다른 테이블이 있습니다. 제프는 두 테이블을 단일 테이블에 배치하려 합니다.

**NorthwestEmployees**

 ![](media/desktop-calculated-tables/calctables_nwempl.png)

**SouthwestEmployees**

 ![](media/desktop-calculated-tables/calctables_swempl.png)

계산된 테이블을 사용하면 두 테이블을 간편하게 하나로 합칠 수 있습니다. 제프는 계산된 테이블을 보고서 뷰나 데이터 뷰로 볼 수 있지만, 새 계산된 테이블을 즉시 볼 수 있는 데이터 뷰가 약간 더 편리합니다.

**데이터 뷰**의 **모델링** 탭에서 **새 테이블**을 클릭합니다. 수식 입력줄이 표시됩니다.

 ![](media/desktop-calculated-tables/calctables_formulabarempty.png)

제프가 다음 수식을 입력합니다.

 ![](media/desktop-calculated-tables/calctables_formulabarformula.png)

이름이 서부 지역 직원인 새 테이블이 만들어집니다.

 ![](media/desktop-calculated-tables/calctables_westregionempl.png)

제프의 새 서부 지역 직원 테이블은 필드 목록의 다른 테이블과 똑같이 표시됩니다. 다른 테이블에서처럼 다른 테이블과의 관계를 만들고, 계산된 열과 측정치를 추가하고, 필드를 보고서에 추가할 수 있습니다.

 ![](media/desktop-calculated-tables/calctables_fieldlist.png)

## <a name="functions-for-calculated-tables"></a>계산된 테이블에 대한 함수
계산된 테이블은 다른 테이블에 대한 간단한 참조를 포함하여 테이블을 반환하는 DAX 식으로 정의할 수 있습니다. 예:

 ![](media/desktop-calculated-tables/calctables_formulabarsimpleformula.png)

많은 분석 문제를 해결하기 위해 DAX가 있는 계산된 테이블을 사용할 수 있습니다. 여기서는 계산된 테이블에 대한 간략한 소개만 제공했습니다. 계산된 테이블 작업을 시작할 때는 다음과 같은 여러 공통 DAX 테이블 함수가 유용할 수 있습니다.

* DISTINCT
* Values
* CROSSJOIN
* UNION
* NATURALINNERJOIN
* NATURALLEFTOUTERJOIN
* INTERSECT
* CALENDAR
* CALENDARAUTO

이 함수 및 기타 테이블 반환 DAX 함수는 [DAX 함수 참조](https://msdn.microsoft.com/ee634396.aspx)에서확인하세요.

