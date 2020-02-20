---
title: Power BI Desktop에서 관계 만들기 및 관리
description: Power BI Desktop에서 관계 만들기 및 관리
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/09/2020
ms.author: davidi
LocalizationGroup: Model your data
ms.openlocfilehash: 6f71cf9b8325441fe3827a259daf3bcbe15765a5
ms.sourcegitcommit: a1409030a1616027b138128695b80f6843258168
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76709916"
---
# <a name="create-and-manage-relationships-in-power-bi-desktop"></a>Power BI Desktop에서 관계 만들기 및 관리
여러 테이블을 가져올 때 이러한 모든 테이블의 데이터를 사용하여 분석을 수행하려는 경우가 있습니다. 결과를 정확하게 계산하고 보고서에 올바른 정보를 표시하려면 테이블 간의 관계가 필요합니다. Power BI Desktop에서는 이러한 관계를 쉽게 만들 수 있습니다. 실제로 아무 작업도 수행할 필요가 없는 경우가 대부분입니다. 자동 검색 기능이 자동으로 작업을 수행합니다. 그러나 관계를 직접 만들거나 관계를 변경해야 하는 경우도 있습니다. 어떤 경우든지 Power BI Desktop에서의 관계 및 관계를 만들고 편집하는 방법을 이해하는 것이 중요합니다. 

## <a name="autodetect-during-load"></a>로드하는 동안 자동 검색 
둘 이상의 테이블을 동시에 쿼리하는 경우 데이터가 로드될 때 Power BI Desktop에서 자동으로 관계를 찾고 만들려고 합니다. 관계 옵션 **카디널리티**, **교차 필터 방향** 및 **이 관계를 활성으로 만들기**가 자동으로 설정됩니다. Power BI Desktop은 쿼리하는 테이블의 열 이름을 보고 잠재적 관계가 있는지를 확인합니다. 관계가 있는 경우 자동으로 생성됩니다. Power BI Desktop이 높은 수준의 신뢰도로 일치하는 항목을 확인할 수 없을 경우 관계를 만들지 않습니다. 그러나 여전히 **관계 관리** 대화 상자를 사용하여 직접 관계를 만들거나 편집할 수 있습니다.

## <a name="create-a-relationship-with-autodetect"></a>자동 검색으로 관계 만들기
**홈** 탭에서 **관계 관리** \> **자동 검색**을 선택합니다.

![자동 검색으로 관계 만들기](media/desktop-create-and-manage-relationships/automaticrelationship.gif)

## <a name="create-a-relationship-manually"></a>수동으로 관계 만들기
1. **홈** 탭에서 **관계 관리** \> **새로 만들기**를 선택합니다.

2. **관계 만들기** 대화 상자의 첫 번째 테이블 드롭다운 목록에서 테이블을 선택합니다. 관계에서 사용할 열을 선택합니다.

3. 두 번째 테이블 드롭다운 목록에서 관계에 사용할 다른 테이블을 선택합니다. 사용할 다른 열을 선택한 다음 **확인**을 선택합니다.

   ![수동으로 관계 만들기](media/desktop-create-and-manage-relationships/manualrelationship2.gif)

기본적으로 Power BI Desktop이 새 관계에 대한 **카디널리티**(방향), **교차 필터 방향** 및 **이 관계를 활성으로 만들기** 옵션을 자동으로 구성합니다. 그러나 필요한 경우 해당 설정을 변경할 수 있습니다. 자세한 내용은 [추가 옵션 이해](#understanding-additional-options)를 확인하세요.

관계를 위해 선택한 테이블 중 고유한 값이 없는 경우 다음과 같은 오류가 표시됩니다. *열 중 하나는 고유한 값이 있어야 합니다*. 관계에 있는 테이블 중 적어도 하나에는 모든 관계형 데이터베이스 기술에 대한 공통 요구 사항인 고유한 키 값 목록이 있어야 *합니다*. 

해당 오류가 발생하면 이를 해결할 수 있는 몇 가지 방법이 있습니다.

* **중복 제거**를 사용하여 고유한 값을 가진 열을 만듭니다. 이 방법의 단점은 중복 행이 제거될 때 정보도 손실될 수 있다는 것이며, 이 때문에 키(행)가 복제되기도 합니다.
* 별개의 키 값 목록으로 만들어진 중간 테이블을 모델에 추가하면 관계의 원래 두 열 모두에 연결됩니다.

자세한 내용은 이 [블로그 게시물](https://blogs.technet.microsoft.com/cansql/2016/12/19/relationships-in-power-bi-fixing-one-of-the-columns-must-have-unique-values-error-message/)을 참조하세요.


## <a name="edit-a-relationship"></a>관계 편집
1. **홈** 탭에서 **관계 관리**를 선택합니다.

2. **관계 관리** 대화 상자에서 관계를 선택하고 **편집**을 선택합니다.

## <a name="configure-additional-options"></a>추가 구성 옵션
관계를 만들거나 편집할 때 추가 옵션을 구성할 수 있습니다. 기본적으로 Power BI Desktop은 가장 적합한 추측을 기반으로 자동으로 추가 옵션을 구성합니다. 이러한 옵션은 열의 데이터를 기반으로 하는 각 관계마다 다를 수 있습니다.

### <a name="cardinality"></a>카디널리티
**카디널리티** 옵션은 다음 설정 중 하나를 사용할 수 있습니다.

**다 대 일(\*:1)**: 다 대 일 관계는 관계의 가장 일반적인 기본 형식입니다. 이는 한 테이블의 열은 둘 이상의 값 인스턴스를 가질 수 있고, 다른 관련 테이블(조회 테이블이라고도 함)은 하나의 값 인스턴스만 가질 수 있음을 의미합니다.

**일 대 일(1:1)**: 일 대 일 관계에서는 한 테이블의 열과 다른 관련 테이블이 하나의 특정 값 인스턴스만 가질 수 있음을 의미합니다.

**일 대 다(1:*)**: 일 대 다 관계에서 한 테이블의 열은 특정 값의 인스턴스를 하나만 가질 수 있고, 다른 관련 테이블은 값의 인스턴스를 하나 이상 가질 수 있음을 의미합니다.

**다 대 다(\**\*:)**: 복합 모델을 사용하여 테이블 간에 다 대 다 관계를 설정할 수 있습니다. 그러면 테이블의 고유한 값에 대한 요구 사항이 제거됩니다. 또한 관계 설정 목적으로만 새 테이블을 도입하는 것과 같은 이전 해결 방법을 제거합니다. 자세한 내용은 [다 대 다 카디널리티와의 관계](https://docs.microsoft.com/power-bi/desktop-many-to-many-relationships)를 참조하세요. 

카디널리티를 변경하는 시점에 대한 자세한 내용은 [추가 옵션 이해](#understanding-additional-options)를 참조하세요.

### <a name="cross-filter-direction"></a>교차 필터 방향
**교차 필터 방향** 옵션은 다음 설정 중 하나를 가질 수 있습니다.


## <a name="cross-filter-direction"></a>교차 필터 방향
**모두** - 필터링 용도로 두 테이블이 모두 단일 테이블인 것처럼 처리됨을 의미합니다. **모두**는 주위에 조회 테이블이 많은 단일 테이블에서 잘 작동합니다. 부서에 대한 조회 테이블이 있는 판매 실적 테이블을 예로 들 수 있습니다. 이를 종종 별 모양 스키마 구성(여러 조회 테이블이 있는 중앙 테이블)이라고 합니다. 그러나 조회 테이블이 있는(일부 공통) 테이블이 여럿인 경우 모두 설정을 사용하지 않는 게 나을 것입니다. 앞의 예에서 각 부서에 대한 목표 예산을 기록하는 판매 예산 테이블도 있다고 가정해 보겠습니다. 또한 부서 테이블은 판매와 예산에 모두 연결되어 있습니다. 이러한 유형의 구성에서는 모두 설정을 사용하지 않습니다.


**단일** 가장 일반적인 기본 방향으로, 값이 집계되는 테이블에 연결된 테이블의 필터링 선택 항목이 적용됨을 의미합니다. Excel 2013 이전 버전의 데이터 모델에서 파워 피벗을 가져오는 경우 모든 관계가 단일 방향을 갖습니다. 

교차 필터 방향 변경 시점에 대한 자세한 내용은 [추가 옵션 이해](#understanding-additional-options)를 참조하세요.

### <a name="make-this-relationship-active"></a>이 관계를 활성으로 만들기
이 옵션을 선택하면 관계가 활성 기본 관계로 사용됩니다. 두 테이블 간에 두 개 이상의 관계가 있는 경우 활성 관계를 통해 Power BI Desktop이 두 테이블을 포함하는 시각화 요소를 자동으로 만들 수 있습니다.

특정 관계 활성화 시점에 대한 자세한 내용은 [추가 옵션 이해](#understanding-additional-options)를 참조하세요.

## <a name="understanding-relationships"></a>관계 이해
관계를 사용하여 두 테이블을 연결한 후에는 관계 세부 정보에 대해 걱정하거나 가져오기 전에 단일 테이블로 평면화할 필요 없이 단일 테이블인 것처럼 두 테이블의 데이터로 작업할 수 있습니다. 대부분의 경우 Power BI Desktop은 자동으로 관계를 만들 수 있습니다. 그러나 Power BI Desktop은 두 테이블 간의 관계가 존재해야 하는 상황에서 불확실성이 높아 관계를 결정하지 못할 경우 자동으로 관계를 만듭니다. 이 경우에는 그렇게 해야 합니다. 

Power BI Desktop에서 관계가 작동하는 방식을 이해하는 데 도움이 되도록 간단한 자습서를 살펴보겠습니다.

>[!TIP]
>이 단원은 직접 완료할 수 있습니다. 
>
> 1. 다음 **ProjectHours** 테이블을 Excel 워크시트(제목 제외)에 복사하고 모든 셀을 선택한 다음 **삽입** \> **테이블**을 선택합니다. 
> 2. **테이블 만들기** 대화 상자에서 **확인**을 선택합니다. 
> 3. 테이블 셀을 선택하고 **테이블 디자인** \> **테이블 이름**을 선택한 다음 *ProjectHours*를 입력합니다. 
> 4. **CompanyProject** 테이블에 대해 동일한 작업을 수행합니다. 
> 5. 그런 다음 Power BI Desktop에서 **데이터 가져오기**를 사용하여 데이터를 가져옵니다. 두 테이블을 데이터 원본으로 선택한 다음 **로드**를 선택합니다.

첫 번째 테이블인 **ProjectHours**는 개인이 특정 프로젝트에서 작업한 시간 수를 기록하는 작업 티켓 레코드입니다. 

**ProjectHours**

| **Ticket** | **SubmittedBy** | **Hours** | **Project** | **DateSubmit** |
| ---:|:--- | ---:|:--- | ---:|
| 1001 |Brewer, Alan |22 |파랑 |1/1/2013 |
| 1002 |Brewer, Alan |26 |빨강 |2/1/2013 |
| 1003 |Ito, Shu |34 |노랑 |12/4/2012 |
| 1004 |Brewer, Alan |13 |주황 |1/2/2012 |
| 1005 |Bowen, Eli |29 |Purple |2013/10/1 |
| 1006 |Bento, Nuno |35 |녹색 |2/1/2013 |
| 1007 |Hamilton, David |10 |노랑 |2013/10/1 |
| 1008 |Han, Mu |28 |Orange |1/2/2012 |
| 1009 |Ito, Shu |22 |보라 |2/1/2013 |
| 1010 |Bowen, Eli |28 |녹색 |10/1/2013 |
| 1011 |Bowen, Eli |9 |파랑 |10/15/2013 |

두 번째 테이블인 **CompanyProject**는 우선 순위가 할당된 프로젝트 목록입니다. A, B 또는 C입니다. 

**CompanyProject**

| **ProjName** | **Priority** |
| --- | --- |
| 파랑 |A |
| Red |B |
| 녹색 |C |
| Yellow |C |
| 보라 |B |
| 주황 |C |

각 테이블에는 프로젝트 열이 있습니다. 각각의 이름은 약간씩 다르게 지정되나 값은 동일하게 보입니다. 이는 중요한 것으로, 잠시 후 다시 살펴보겠습니다.

이제 두 테이블을 모델로 가져왔으므로 보고서를 만들어 보겠습니다. 먼저 프로젝트 우선 순위별로 제출된 시간 수를 확인하려고 하므로 **필드** 창에서 **우선 순위** 및 **시간**을 선택합니다.

![필드 창에서 우선 순위 및 시간 선택](media/desktop-create-and-manage-relationships/candmrel_reportfiltersnorel.png)

보고서 캔버스에서 테이블을 보면 각 프로젝트에 대한 시간이 총 256시간으로 표시되는 것을 알 수 있습니다. 분명히 이 숫자는 잘못되었습니다. 이유가 무엇일까요? 이는 두 테이블 간의 관계가 없으면 다른 테이블의 값(**CompanyProject** 테이블의 **Priority**)으로 분리된 한 테이블의 값(**Project** 테이블의 **Hours**)에 대한 합계를 계산할 수 없기 때문입니다.

따라서 이러한 두 테이블 간에 관계를 만들겠습니다.

열에서 두 테이블에 모두 프로젝트 이름이 있지만 값은 비슷해 보였습니다. 이러한 두 열을 사용하여 테이블 간의 관계를 만들겠습니다.

이러한 열을 사용하는 이유는 무엇일까요? **ProjectHours** 테이블의 **Project** 열을 보면 Blue, Red, Yellow, Orange 등의 값이 표시됩니다. 실제로 동일한 값을 가진 여러 행이 표시됩니다. **프로젝트**에 대한 많은 색상 값이 있습니다.

**CompanyProject** 테이블의 **ProjName** 열에는 프로젝트 이름의 각 색상 값이 하나밖에 없습니다. 이 테이블의 각 색상 값은 고유하며, 이러한 두 테이블 간에 관계를 만들 수 있기 때문에 이는 중요합니다. 이 경우 다대일 관계입니다. 다대일 관계에서는 테이블 중 하나에 고유한 값을 가진 열이 하나 이상 있어야 합니다. 일부 관계에 대한 몇 가지 추가 옵션이 있습니다. 이에 대해서는 나중에 살펴보겠습니다. 지금은 두 테이블 각각의 프로젝트 열 사이에 관계를 만들어보겠습니다.

### <a name="to-create-the-new-relationship"></a>새 관계를 만들려면
1. **홈** 탭에서 **관계 관리**를 선택합니다.
2. **관계 관리**에서 **새로 만들기**를 선택하여 관계에 사용하려는 테이블, 열 및 추가 설정을 선택할 수 있는 **관계 만들기** 대화 상자를 엽니다.
3. 첫 번째 드롭다운 목록에서 첫 번째 테이블로 **ProjectHours**를 선택한 다음 **프로젝트** 열을 선택합니다. 이 측면은 관계의 *다* 측면입니다.
4. 두 번째 드롭다운 목록에서 **CompanyProject**가 두 번째 테이블로 미리 선택됩니다. **ProjName** 열을 선택합니다. 이 측면은 관계의 *일* 측면입니다. 
5. 관계 옵션의 기본값을 그대로 승인한 다음 **확인**을 선택합니다.

   ![관계 만들기 대화 상자](media/desktop-create-and-manage-relationships/candmrel_create_compproj.png)

6. **관계 관리** 대화 상자에서 **닫기**를 선택합니다.

자세한 설명을 위해 지금은 이 관계를 어려운 방법으로 만들었습니다. **관계 관리** 대화 상자에서 **자동 검색**을 선택하기만 해도 됐을 것입니다. 사실 두 열의 이름이 같은 경우 데이터를 로드할 때 자동 검색은 자동으로 관계를 만들었습니다. 하지만 무엇이 문제일까요?

이제 보고서 캔버스에서 다시 테이블을 살펴보겠습니다.

![우선 순위 및 시간을 사용하여 만든 관계](media/desktop-create-and-manage-relationships/candmrel_reportfilterswithrel.png)

이제 훨씬 좋아 보이지 않나요?

**Priority**를 기준으로 시간 합계를 계산하는 경우, Power BI Desktop은 **CompanyProject** 조회 테이블에서 고유한 색상 값의 모든 인스턴스를 찾고 **ProjectHours** 테이블에서 각 값의 모든 인스턴스를 찾은 다음 각 고유한 값의 합계를 계산합니다.

이 과정은 쉽습니다. 사실 자동 검색을 사용하면 이러한 작업조차 불필요할 수 있습니다.

## <a name="understanding-additional-options"></a>추가 옵션 이해
자동 검색을 통해 관계가 생성되거나 수동으로 관계를 만들면 Power BI Desktop이 테이블의 데이터를 기반으로 하여 추가 옵션을 자동으로 구성합니다. 해당 추가 관계 옵션은 **관계 만들기** 및 **관계 편집** 대화 상자의 아래쪽 부분에 있습니다.

 ![관계 옵션](media/desktop-create-and-manage-relationships/candmrel_advancedoptions2.png)

일반적으로 Power BI에서는 관계 옵션이 자동으로 설정되므로 사용자가 이 옵션을 조정할 필요가 없습니다. 하지만 몇몇 경우에는 관계 옵션을 직접 구성하는 것이 좋습니다.

## <a name="automatic-relationship-updates"></a>자동 관계 업데이트

Power BI에서 보고서와 모델의 관계를 처리하고 자동으로 조정하는 방법을 관리할 수 있습니다. Power BI에서 관계 옵션을 처리하는 방법을 지정하려면 Power BI Desktop에서 **파일** > **옵션 및 설정** > **옵션**을 선택한 다음 왼쪽 창에서 **데이터 로드**를 선택합니다. **관계**에 대한 옵션이 표시됩니다.

   ![관계 옵션](media/desktop-create-and-manage-relationships/relationships-options-01.png)

세 가지 옵션을 선택하고 사용할 수 있습니다. 

- **처음 로드 시 데이터 원본에서 관계 가져오기** 이 옵션은 기본적으로 선택되어 있습니다. 이를 선택하면 Power BI에서 데이터 웨어하우스의 외래 키/기본 키 관계와 같이 데이터 원본에 정의된 관계를 확인합니다. 이러한 관계가 있는 경우 처음에 데이터를 로드할 때 Power BI 데이터 모델로 미러됩니다. 이 옵션을 사용하면 사용자가 직접 관계를 찾거나 정의하지 않아도 모델 작업을 신속하게 시작할 수 있습니다.

- **데이터를 새로 고칠 때 관계 업데이트 또는 삭제**: 이 옵션은 기본적으로 선택되어 있지 않습니다. 이 옵션을 선택하면 Power BI가 데이터 세트를 새로 고칠 때 데이터 원본 관계의 변경 내용을 확인합니다. 이러한 관계가 변경되거나 제거되는 경우 Power BI는 자체 데이터 모델에서 변경 내용을 미러링하거나, 해당 변경 내용을 업데이트 또는 삭제하여 일치시킵니다.

   > [!WARNING]
   > 정의된 관계에 의존하는 행 수준 보안을 사용하는 경우 이 옵션을 선택하지 않는 것이 좋습니다. RLS 설정이 의존하는 관계를 제거하면 모델의 보안이 저하될 수 있습니다. 

- **데이터가 로드된 후 새 관계 자동 검색합니다.** 이 옵션은 [로드하는 동안 자동 검색](#autodetect-during-load)에 설명되어 있습니다. 


## <a name="future-updates-to-the-data-require-a-different-cardinality"></a>이후에 데이터를 업데이트하려면 다른 카디널리티가 필요합니다.
일반적으로 Power BI Desktop은 관계에 대한 최상의 카디널리티를 자동으로 결정할 수 있습니다. 데이터가 나중에 변경될 것을 알고 있으므로 자동 설정을 재정의해야 하는 경우 **카디널리티** 컨트롤에서 변경할 수 있습니다. 다른 카디널리티를 선택해야 하는 예를 살펴보겠습니다.

**CompanyProjectPriority** 테이블은 모든 회사 프로젝트 목록과 해당 우선 순위입니다. **ProjectBudget** 테이블은 예산이 승인된 프로젝트 집합입니다.

**CompanyProjectPriority**

| **ProjName** | **Priority** |
| --- | --- |
| 파랑 |A |
| Red |B |
| 녹색 |C |
| Yellow |C |
| 보라 |B |
| 주황 |C |

**ProjectBudget**

| **Approved Projects** | **BudgetAllocation** | **AllocationDate** |
|:--- | ---:| ---:|
| 파랑 |40,000 |12/1/2012 |
| 빨강 |100,000 |12/1/2012 |
| Green |50,000 |12/1/2012 |


카디널리티는 자동으로 일대일(1:1)로 설정되고 교차 필터링은 모두로 설정됩니다(표시 참조). 이는 Power BI Desktop에서 두 테이블의 최적 조합은 실제로 다음과 같이 표시되기 때문입니다.


 ![테이블 열 간의 관계 만들기](media/desktop-create-and-manage-relationships/candmrel_create_compproj_appproj2.png)

Power BI가 해당 설정을 만드는 이유는 Power BI Desktop에서 두 테이블의 최적 조합이 다음과 같기 때문입니다.

| **ProjName** | **Priority** | **BudgetAllocation** | **AllocationDate** |
|:--- | --- | ---:| ---:|
| Blue |A |40,000 |12/1/2012 |
| 빨강 |B |100,000 |12/1/2012 |
| 녹색 |C |50,000 |12/1/2012 |
| 노랑 |C |<br /> |<br /> |
| 보라 |B |<br /> |<br /> |
| 주황 |C |<br /> |<br /> |

결합된 테이블의 **ProjName** 열에 반복 값이 없기 때문에 두 테이블 간에 일대일 관계가 있습니다. **ProjName** 열은 각 값이 한 번씩만 나타나므로 고유하며, 따라서 두 테이블의 행을 중복 없이 직접 결합할 수 있습니다.

그러나 다음에 새로 고칠 때 데이터가 변경되는 것을 알고 있다고 가정해 보세요. 이제 새로 고친 버전의 **ProjectBudget** 테이블에 Blue와 Red 프로젝트에 대한 추가 행이 있습니다.

**ProjectBudget**

| **Approved Projects** | **BudgetAllocation** | **AllocationDate** |
| --- | ---:| ---:|
| 파랑 |40,000 |12/1/2012 |
| 빨강 |100,000 |12/1/2012 |
| Green |50,000 |12/1/2012 |
| 파랑 |80,000 |6/1/2013 |
| 빨강 |90,000 |6/1/2013 |

 이러한 추가 행은 두 테이블의 최적 조합이 이제 다음과 같이 표시됨을 의미합니다. 

| **ProjName** | **Priority** | **BudgetAllocation** | **AllocationDate** |
| --- | --- | ---:| ---:|
| Blue |A |40,000 |12/1/2012 |
| 빨강 |B |100,000 |12/1/2012 |
| 녹색 |C |50,000 |12/1/2012 |
| 노랑 |C |<br /> |<br /> |
| 보라 |B |<br /> |<br /> |
| 주황 |C |<br /> |<br /> |
| 파랑 |A |80000 |6/1/2013 |
| 빨강 |B |90000 |6/1/2013 |

새로 결합된 테이블의 **ProjName** 열에는 반복 값이 있습니다. 테이블을 새로 고치고 나면 원래의 두 테이블 간에 일대일 관계가 없습니다. 이 경우 이후의 업데이트로 인해 **ProjName** 열에 중복 항목이 포함될 것을 알고 있으므로 **ProjectBudget** 쪽을 *다*로 지정하고 **CompanyProjectPriority** 쪽을 *일*로 지정하여 **카디널리티**를 **다대일(\*:1)** 로 설정하려고 합니다.

## <a name="adjusting-cross-filter-direction-for-a-complex-set-of-tables-and-relationships"></a>복잡한 테이블 및 관계 집합에 대해 교차 필터 방향 조정

대부분의 관계에 대해 교차 필터 방향은 '모두'로 설정됩니다. 그러나 드물긴 하지만 모든 관계가 단일 방향으로 설정되는 이전 버전의 파워 피벗에서 모델을 가져오는 경우처럼 기본값과 다른 값으로 설정해야 하는 경우가 있습니다. 

모두 설정을 사용하면 Power BI Desktop이 연결된 테이블의 모든 측면을 단일 테이블처럼 처리할 수 있습니다. 그러나 Power BI Desktop이 관계의 교차 필터 방향을 '모두'로 설정할 수 없고 보고 용도로 명확한 기본값 집합도 사용 가능하도록 유지해야 하는 경우가 있습니다. 관계 교차 필터 방향을 모두로 설정하지 않는 경우는 보통 모호해지기 때문입니다. 기본 교차 필터 설정이 적합하지 않은 경우 특정 테이블 방향이나 모두로 설정할 수 있습니다.


단일 방향 교차 필터링은 대부분의 상황에서 작동합니다. 실제로 Excel 2013 또는 그 이전 버전의 파워 피벗에서 모델을 가져온 경우 모든 관계가 단일 방향으로 설정됩니다. 단일 방향은 집계 작업이 발생하는 테이블에 연결된 테이블의 필터링 선택 항목이 적용됨을 의미합니다. 때로는 교차 필터링 이해가 약간 어려울 수 있으므로 예를 살펴보겠습니다.

단일 방향 교차 필터링을 사용하여 프로젝트 시간을 요약하는 보고서를 만드는 경우 **CompanyProject** 테이블과 해당 **우선 순위** 열 또는 **CompanyEmployee** 테이블과 해당 **City** 열을 요약(또는 필터링)하도록 선택할 수 있습니다. 그러나 (덜 일반적인 질문이기는 하지만) 프로젝트당 직원 수를 계산하려는 경우에는 작동하지 않습니다. 모두 동일한 값을 가진 열이 생성됩니다. 다음 예제에서는 관계 교차 필터링 방향이 둘 다 단일 방향(**ProjectHours** 테이블 방향)으로 설정됩니다. **값** 웰에서 **프로젝트** 필드는 **개수**로 설정됩니다.

 ![교차 필터링 방향](media/desktop-create-and-manage-relationships/candmrel_repcrossfiltersingle.png)

필터 지정은 **CompanyProject**에서 **CompanyEmployee**로 진행되지만(다음 그림 참조) **CompanyEmployee**까지 진행되지는 않습니다. 

 ![교차 필터링 예제](media/desktop-create-and-manage-relationships/candmrel_singledircrossfiltering.png)


필터 지정은 CompanyProject에서 CompanyEmployee로 진행되지만(아래 그림 참조) CompanyEmployee까지 진행되지는 않습니다. 그러나 교차 필터링 방향을 모두로 설정하면 작동합니다. 모두로 설정하면 필터 지정이 Employee까지 진행될 수 있습니다.


그러나 교차 필터링 방향을 **양쪽**으로 설정하면 작동합니다. **양쪽**으로 설정하면 필터 지정이 **CompanyEmployee**까지 진행될 수 있습니다.

 ![필터 사양 흐름](media/desktop-create-and-manage-relationships/candmrel_bidircrossfiltering.png)

교차 필터링 방향을 **양쪽**으로 설정하면 이제 보고서가 올바르게 표시됩니다.

 ![교차 필터링 방향을 양쪽으로 설정](media/desktop-create-and-manage-relationships/candmrel_repcrossfilterbi.png)

양방향 교차 필터링은 위 패턴과 같은 테이블 관계 패턴에 적합합니다. 이 스키마는 일반적으로 다음과 같이 별모양 스키마라고 합니다.

 ![별모양 스키마의 양방향 교차 필터링](media/desktop-create-and-manage-relationships/candmrel_crossfilterstarschema.png)

교차 필터링 방향은 다음 다이어그램과 같이 데이터베이스에서 자주 발견되는 보다 일반적인 패턴에서는 제대로 작동하지 않습니다.

 ![데이터베이스 패턴의 양방향 교차 필터링](media/desktop-create-and-manage-relationships/candmrel_crossfilterwithloops.png)

루프와 함께 이러한 테이블 패턴이 있는 경우 교차 필터링에서 모호한 관계 집합을 만들 수 있습니다. 예를 들어 테이블 X에서 필드 합계를 계산한 다음 테이블 Y의 필드를 기준으로 필터링하도록 선택하는 경우 필터가 상단 테이블을 통해 진행되어야 하는지 또는 하단 테이블을 통해 진행되어야 하는지 명확하지 않습니다. 이러한 패턴의 일반적인 예로 판매 실적 데이터가 있는 판매 테이블인 테이블 X와 예산 데이터가 될 테이블 Y를 들 수 있습니다. 그러면 가운데 테이블이 부서, 지역 등 두 테이블이 사용할 조회 테이블이 됩니다. 

활성/비활성 관계와 마찬가지로 Power BI Desktop은 보고서에 모호성을 유발하는 경우 관계를 **양쪽**으로 설정할 수 없습니다. 이 상황을 처리할 수 있는 몇 가지 방법이 있습니다. 가장 일반적인 두 가지는 다음과 같습니다.


* 모호성을 줄이기 위해 관계를 삭제하거나 비활성으로 표시합니다. 그런 다음 관계 교차 필터링을 모두로 설정할 수 있습니다.
* 테이블을 두 번 가져와(두 번째는 다른 이름으로) 루프를 제거합니다. 이렇게 하면 관계 패턴이 별모양 스키마와 비슷해집니다. 별모양 스키마를 사용할 경우 모든 관계를 모두로 설정할 수 있습니다.


## <a name="wrong-active-relationship"></a>잘못된 활성 관계
Power BI Desktop이 자동으로 관계를 만들 때 두 테이블 간에 둘 이상의 관계를 발견하는 경우도 있습니다. 해당 상황이 발생하는 경우 관계 중 하나만 활성으로 설정됩니다. 활성 관계는 서로 다른 두 테이블에서 필드를 선택할 때 Power BI Desktop이 자동으로 시각화를 만들 수 있도록 기본 관계 역할을 합니다. 그러나 자동으로 선택된 관계가 잘못된 경우도 있습니다. **관계 관리** 대화 상자를 사용하여 관계를 활성 또는 비활성으로 설정하거나, **관계 편집** 대화 상자에서 활성 관계를 설정합니다. 

기본 관계가 있도록 하기 위해 Power BI Desktop은 지정된 시간에 두 테이블 간에 하나의 활성 관계만 허용합니다. 따라서 먼저 현재 관계를 비활성으로 설정한 다음 활성화할 관계를 설정해야 합니다.

예를 살펴보겠습니다. 이 첫 번째 테이블은 **ProjectTickets**이고 두 번째 테이블은 **EmployeeRole**입니다.

**ProjectTickets**

| **Ticket** | **OpenedBy** | **SubmittedBy** | **Hours** | **Project** | **DateSubmit** |
| ---:|:--- |:--- | ---:|:--- | ---:|
| 1001 |Perham, Tom |Brewer, Alan |22 |파랑 |1/1/2013 |
| 1002 |Roman, Daniel |Brewer, Alan |26 |빨강 |2/1/2013 |
| 1003 |Roth, Daniel |Ito, Shu |34 |노랑 |12/4/2012 |
| 1004 |Perham, Tom |Brewer, Alan |13 |주황 |1/2/2012 |
| 1005 |Roman, Daniel |Bowen, Eli |29 |Purple |2013/10/1 |
| 1006 |Roth, Daniel |Bento, Nuno |35 |녹색 |2/1/2013 |
| 1007 |Roth, Daniel |Hamilton, David |10 |노랑 |2013/10/1 |
| 1008 |Perham, Tom |Han, Mu |28 |Orange |1/2/2012 |
| 1009 |Roman, Daniel |Ito, Shu |22 |보라 |2/1/2013 |
| 1010 |Roth, Daniel |Bowen, Eli |28 |녹색 |10/1/2013 |
| 1011 |Perham, Tom |Bowen, Eli |9 |파랑 |10/15/2013 |

**EmployeeRole**

| **Employee** | **Role** |
| --- | --- |
| Bento, Nuno |Project Manager |
| Bowen, Eli |Project Lead |
| Brewer, Alan |Project Manager |
| Hamilton, David |Project Lead |
| Han, Mu |Project Lead |
| Ito, Shu |Project Lead |
| Perham, Tom |Project Sponsor |
| Roman, Daniel |Project Sponsor |
| Roth, Daniel |Project Sponsor |

실제로 여기에는 두 개의 관계가 있습니다.
- **EmployeeRole** 테이블의 **Employee**과 **ProjectTickets** 테이블의 **SubmittedBy** 사이입니다.
- **ProjectTickets** 테이블의 **OpenedBy**와 **EmployeeRole** 테이블의 **Employee** 사이입니다.

 ![두 관계 예제](media/desktop-create-and-manage-relationships/candmrel_activerelview.png)

두 관계를 모두 모델에 추가하면(먼저 **OpenedBy** 추가) **관계 관리** 대화 상자에 **OpenedBy**가 활성 상태로 표시됩니다.

 ![관계 관리 대화 상자에서 OpenedBy 활성화](media/desktop-create-and-manage-relationships/candmrel_managerelactive.png)

이제 보고서 캔버스의 테이블 시각화에 **EmployeeRole**의 **Role** 및 **Employee** 필드와 **ProjectTickets**의 **Hours** 필드를 사용하는 보고서를 만들면 프로젝트 스폰서만 표시되는 데 이것은 이들만이 프로젝트 티켓을 열었기 때문입니다.

 ![직원, 역할 및 시간 필드 선택](media/desktop-create-and-manage-relationships/candmrel_repcrossfilteractive.png)

활성 관계를 변경하여 **OpenedBy** 대신 **SubmittedBy**를 가져올 수 있습니다. **관계 관리**에서 **ProjectTickets(OpenedBy)** 와 **EmployeeRole(Employee)** 간의 관계를 선택 취소한 다음 **EmployeeRole(Employee)** 과 **Project Tickets(SubmittedBy)** 간의 관계를 선택합니다.

![관계 관리 대화 상자에서 활성 관계 변경](media/desktop-create-and-manage-relationships/candmrel_managerelactivesubmittedby.png)

## <a name="see-all-of-your-relationships-in-relationship-view"></a>관계 보기의 모든 관계 참조
경우에 따라 모델에 여러 테이블이 있고 테이블 간의 관계가 복잡할 수 있습니다. Power BI Desktop의 **관계** 보기는 모델의 모든 관계, 방향 및 카디널리티를 이해하기 쉽고 사용자 지정할 수 있는 다이어그램으로 보여 줍니다. 

자세한 내용은 [Power BI Desktop의 관계 보기와 작업](desktop-relationship-view.md)을 참조하세요.

