---
title: Power BI Desktop의 계산된 테이블 사용
description: Power BI Desktop의 계산된 테이블
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/02/2020
ms.author: davidi
LocalizationGroup: Model your data
ms.openlocfilehash: c72387d40ddf4b193481a37dbcb40695668eab66
ms.sourcegitcommit: 4b926ab5f09592680627dca1f0ba016b07a86ec0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2020
ms.locfileid: "75837334"
---
# <a name="create-calculated-tables-in-power-bi-desktop"></a>Power BI Desktop에서 계산된 테이블 만들기
대부분의 경우, 테이블은 외부 데이터 원본에서 모델로 데이터를 가져와서 만듭니다. 반면에 *계산된 테이블*을 사용하면 모델로 이미 로드한 데이터를 기반으로 새 테이블을 추가할 수 있습니다. 값을 쿼리하고 데이터 원본에서 새 테이블의 열로 로드하는 대신 [DAX(Data Analysis Expressions)](/dax/index) 수식을 만들어서 테이블 값을 정의합니다.

DAX는 Power BI Desktop에서처럼 관계형 데이터로 작업할 때 사용하는 수식 언어입니다. DAX에는 200개가 넘는 함수, 연산자 및 구문 라이브러리가 포함되어 데이터 분석 결과를 계산하는 수식을 만들 때 엄청난 유연성을 제공합니다. 계산된 테이블은 즉석에서 또는 쿼리 결과로 계산된 것이 아닌 모델의 일부로 저장하려는 데이터와 중간 계산에 가장 적합합니다. 예를 들어, 두 개의 기존 테이블을 *연결*하거나 *크로스 조인*해야 하는 경우가 있습니다.

계산된 테이블은 여타 Power BI Desktop 테이블과 마찬가지로 다른 테이블과 관계를 가질 수 있습니다. 계산된 테이블 열은 데이터 형식과 서식을 가질 수 있으며 데이터 범주에 속할 수 있습니다. 열에는 원하는 대로 이름을 지정할 수 있고, 다른 필드처럼 보고서 시각화에 열을 추가할 수 있습니다. 계산된 테이블은 데이터를 가져오는 테이블 중 하나라도 새로 고쳐지거나 업데이트되면 다시 계산됩니다.

## <a name="create-a-calculated-table"></a>계산된 테이블 만들기

계산된 테이블은 Power BI Desktop의 보고서 뷰 또는 데이터 뷰에서 **새 테이블** 기능을 사용하여 만듭니다.

예를 들어, 여러분이 **Northwest Employees** 테이블과 **Southwest Employees** 테이블을 관리하는 인력 관리자라고 가정해 보겠습니다. 이 두 개의 테이블을 **Western Region Employees**이라는 하나의 테이블로 결합하려고 합니다.

**Northwest Employees**

 ![](media/desktop-calculated-tables/calctables_nwempl.png)

**Southwest Employees**

 ![](media/desktop-calculated-tables/calctables_swempl.png)

Power BI Desktop의 보고서 뷰 또는 데이터 뷰에서, **Modeling** 탭의 **계산** 그룹에서 **새 테이블**을 선택합니다. 데이터 뷰에서는 새로 만든 계산된 테이블을 곧바로 볼 수 있으므로 데이터 뷰에서 작업하는 것이 좀 더 편리합니다.

 ![데이터 뷰의 새 테이블](media/desktop-calculated-tables/calctables_formulabarempty.png)

수식 입력줄에 다음 수식을 입력합니다.

```dax
Western Region Employees = UNION('Northwest Employees', 'Southwest Employees')
```

**Western Region Employees**라는 새 테이블이 생성되고, **필드**  창에 다른 테이블과 동일하게 표시됩니다. 여타 테이블로 작업할 때와 마찬가지로 다른 테이블과의 관계를 만들고, 측정값과 계산된 열을 추가하고, 필드를 보고서에 추가할 수 있습니다.

 ![새 계산된 테이블](media/desktop-calculated-tables/calctables_westregionempl.png)

 ![필드 창의 새 테이블](media/desktop-calculated-tables/calctables_fieldlist.png)

## <a name="functions-for-calculated-tables"></a>계산된 테이블에 대한 함수

계산된 테이블은 다른 테이블에 대한 간단한 참조를 포함하여 테이블을 반환하는 임의의 DAX 식을 사용하여 정의할 수 있습니다. 예:

```dax
New Western Region Employees = 'Western Region Employees'
```

이 문서에서는 계산된 테이블에 대한 간략한 소개만 제공합니다. 많은 분석 문제를 해결하기 위해 DAX가 있는 계산된 테이블을 사용할 수 있습니다. 다음은 자주 사용되는 DAX 테이블 함수입니다.

* DISTINCT
* Values
* CROSSJOIN
* UNION
* NATURALINNERJOIN
* NATURALLEFTOUTERJOIN
* INTERSECT
* CALENDAR
* CALENDARAUTO

위 함수와 테이블을 반환하는 기타 DAX 함수는 [DAX 함수 참조](/dax/dax-function-reference)에서 확인하세요.

