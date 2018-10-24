---
title: Power BI Desktop의 복합 모델 사용(미리 보기)
description: Power BI Desktop에서 여러 데이터 연결 및 다 대 다 관계를 사용하여 데이터 모델 만들기
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 10/02/2018
ms.author: davidi
LocalizationGroup: Transform and shape data
ms.openlocfilehash: 49540dd491d02c6a6b474ff80690a75eecfd27db
ms.sourcegitcommit: b8461c1876bfe47bf71c87c7820266993f82c0d3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2018
ms.locfileid: "49336993"
---
# <a name="composite-models-in-power-bi-desktop-preview"></a>Power BI Desktop의 복합 모델(미리 보기)

보고서에서 DirectQuery를 사용했을 때 이전에 **Power BI Desktop**에서는 DirectQuery 또는 가져오기인지 여부와 관계없이 해당 보고서에 대한 다른 데이터 연결이 허용되지 않습니다. **복합 모델**을 사용하면 해당 제한 사항이 제거되고, 보고서에 둘 이상의 DirectQuery 또는 가져오기 데이터 연결의 데이터 연결을 선택한 조합으로 원활하게 포함할 수 있습니다.

![Power BI Desktop의 복합 모델](media/desktop-composite-models/composite-models_01.png)

**Power BI Desktop**의 **복합 모델** 기능은 다음 세 가지 관련 기능으로 구성됩니다.

* **복합 모델** - 보고서에 DirectQuery 연결 또는 가져오기를 비롯한 여러 데이터 연결을 다양한 조합으로 포함할 수 있습니다.
* **다 대 다 관계** - **복합 모델**을 사용하면 테이블 간에 **다 대 다 관계**를 설정할 수 있어 테이블의 고유한 값에 대한 요구 사항이 제거되고 관계 설정만을 위한 새 테이블 도입과 같은 이전 해결 방법을 사용할 필요가 없습니다. 
* **저장소 모드** - 이제 백 엔드 데이터 원본에 대한 쿼리가 필요한 시각적 개체를 지정할 수 있고, 쿼리가 필요하지 않은 시각적 개체는 DirectQuery를 기반으로 하는 경우에도 가져오게 되어 성능을 향상하고 백 엔드 로그를 줄일 수 있습니다. 이전에는 슬라이서와 같은 간단한 시각적 개체도 백 엔드 원본으로 전송되는 쿼리를 시작했습니다. 

**복합 모델**에 대한 세 가지 관련 기능 모음은 다음 별도의 문서에서 설명합니다.

* **복합 모델**은 이 문서에서 자세히 설명합니다.
* **다 대 다 관계**는 관련 문서 [Power BI Desktop의 다 대 다 관계(미리 보기)](desktop-many-to-many-relationships.md)에서 설명합니다.
* **저장소 모드**는 자체 문서인 [Power BI Desktop의 저장소 모드(미리 보기)](desktop-storage-mode.md)에서 설명합니다.

## <a name="enabling-the-composite-models-preview-feature"></a>복합 모델 미리 보기 기능 사용

**복합 모델** 기능은 미리 보기 상태이며 **Power BI Desktop**에서 사용하도록 설정해야 합니다. **복합 모델**을 사용하려면 **파일 > 옵션 및 설정 > 옵션 > 미리 보기 기능**을 선택한 후 **복합 모델** 확인란을 선택합니다. 

![미리 보기 기능 사용](media/desktop-composite-models/composite-models_02.png)

기능을 사용하려면 **Power BI Desktop**을 다시 시작해야 합니다.

![변경 내용을 적용하려면 다시 시작 필요](media/desktop-composite-models/composite-models_03.png)


## <a name="using-composite-models"></a>복합 모델 사용

**복합 모델**을 사용하면 **Power BI Desktop** 또는 **Power BI 서비스**를 사용하는 경우 모든 종류의 다양한 데이터 원본에 연결할 수 있으며 이러한 데이터를 여러 가지 방법으로 연결할 수 있습니다. 데이터를 가져오는 가장 일반적인 방법인 Power BI로 데이터를 가져오거나 DirectQuery를 사용하여 원래의 원본 리포지토리에 있는 데이터에 직접 연결할 수 있습니다. [Power BI의 DirectQuery 사용](desktop-directquery-about.md) 문서에서 DirectQuery 를 자세히 알아볼 수 있습니다.

DirectQuery를 사용하는 경우 **복합 모델**에서는 다음을 수행하는 Power BI 모델(예: 단일 .pbix Power BI Desktop 파일)을 만들 수 있습니다.

* 하나 이상 DirectQuery 원본의 데이터 결합 및/또는
* DirectQuery 원본의 데이터와 가져오기 데이터 결합

예를 들어 **복합 모델**을 사용하면 스프레드시트에서 가져온 데이터와 함께, 엔터프라이즈 데이터 웨어하우스의 데이터를 부서별 SQL Server 데이터베이스에 있는 판매 대상 데이터와 결합하는 모델을 빌드할 수 있습니다. 둘 이상 DirectQuery 원본의 데이터를 결합하거나 DirectQuery를 가져온 데이터와 결합하는 모델을 ‘복합 모델’이라고 합니다.

> [!NOTE]
> **Power BI Desktop**의 2018년 10월 릴리스부터 Power BI 서비스에 대한 복합 모델을 Power BI 서비스에 게시’할 수 있습니다’. 예약된 새로 고침 및 대시보드 타일 새로 고침의 경우 Power BI 서비스의 복합 모델은 모델 가져오기와 동일한 방식으로 동작합니다. 

테이블이 다양한 원본에서 오는 경우에도 일반적인 경우처럼 해당 테이블 간에 관계를 만들 수 있으며 다음 제한 사항이 적용됩니다. 교차 원본인 관계는 실제 카디널리티와 관계없이 **다 대 다** 카디널리티를 포함하는 것으로 정의해야 합니다. [Power BI Desktop의 다 대 다 관계(미리 보기)](desktop-many-to-many-relationships.md)에 설명된 대로 해당 관계의 동작은 **다 대 다** 관계의 정상 동작과 동일합니다. 복합 모델의 컨텍스트 내에서 모든 가져온 테이블은 실제로 가져온 실제 기본 데이터 원본과 관계없이 실질적으로 단일 원본입니다.   

## <a name="example-of-using-composite-models"></a>복합 모델 사용 예제

**복합 모델**의 예로 DirectQuery를 사용하여 SQL Server에서 회사 데이터 웨어하우스에 연결한 보고서를 살펴보겠습니다. 여기서 데이터 웨어하우스에는 다음 이미지와 같이 ‘국가, 분기 및 자전거(제품)별 판매액’의 데이터가 포함됩니다.

![복합 모델에 대한 관계 보기](media/desktop-composite-models/composite-models_04.png)

이 시점에 이 원본의 필드를 사용하여 단순 시각적 개체를 빌드할 수 있습니다. 예를 들어 다음 시각적 개체는 선택된 분기에 대한 *ProductName*별 총 판매액을 표시합니다. 

![데이터 기반 시각적 개체](media/desktop-composite-models/composite-models_05.png)

그러나 마케팅 우선 순위, 해당 데이터가 Excel 스프레드시트에서 유지 관리되는 위치와 함께 각 제품에 할당된 제품 관리자에 대한 일부 정보가 있다면 어떻게 될까요? ‘제품 관리자’별 ‘판매액’을 확인하려고 하지만 이 로컬 데이터를 회사 데이터 웨어하우스에 추가하는 것은 불가능하거나 아무리 잘해도 몇 달이 걸릴 수 있습니다. DirectQuery를 사용하는 대신 데이터 웨어하우스에서 해당 판매액 데이터를 가져올 수 있고 이때 스프레드시트에서 가져온 데이터와 결합할 수 있지만, 데이터의 순수한 규모, 최신 데이터를 확인해야 할 필요성 및 기본 원본에 적용된 보안 규칙의 일부 조합과 같이 처음부터 DirectQuery를 사용해야 하는 이유가 있으면 이 접근 방식이 적절하지 않습니다. 

그래서 **복합 모델**이 도입되었습니다. 복합 모델은 DirectQuery를 사용하여 데이터 웨어하우스에 연결한 후 추가 원본에 GetData를 사용하는 옵션을 제공합니다. 이 경우 회사 데이터 웨어하우스에 대한 DirectQuery 연결을 설정한 후 GetData를 사용하고 Excel을 선택하여 로컬 데이터를 포함하는 스프레드시트로 이동하면 *ProductNames*, 할당된 *SalesManager* 및 *Priority*가 포함된 시트를 가져올 수 있습니다.  

![탐색기 창](media/desktop-composite-models/composite-models_06.png)

이제 **필드** 목록에 원래 *Bike* 테이블(SQL Server에서 가져옴) 및 새 *Product Managers* 테이블(Excel에서 가져온 데이터 포함)이 표시됩니다. 

![테이블의 필드 보기](media/desktop-composite-models/composite-models_07.png)

마찬가지로 **Power BI Desktop**의 **관계 보기**를 살펴보면 *Product Managers*라는 추가 테이블이 확인됩니다. 

![테이블의 관계 보기](media/desktop-composite-models/composite-models_08.png)

이제 항상 하던 것처럼 *Bike* 테이블(SQL Server에 있음)과 *Product Managers* 테이블(가져옴) 간에(예: *Bike[ProductName]* 과 *ProductManagers[ProductName]* 간에) 관계를 만들어 이러한 테이블을 모델의 다른 테이블과 연결해야 합니다. 이 문서의 앞부분에서 설명한 대로 원본을 거쳐 가는 모든 관계에는 **다 대 다** 카디널리티가 있어야 하고 이는 일반적으로 선택되는 기본 카디널리티입니다. 

![관계 만들기 대화 상자](media/desktop-composite-models/composite-models_09.png)

이 관계가 만들어지면 관계가 예상대로 **Power BI Desktop**의 **관계 보기**에 표시됩니다.

![새 관계 보기](media/desktop-composite-models/composite-models_10.png)

이러한 테이블 관계를 설정하면 이제 **필드** 목록의 필드를 사용하여 시각적 개체를 만들어 여러 원본의 데이터를 원활하게 혼합할 수 있습니다. 예를 들어 아래 시각적 개체는 각 ‘제품 관리자’의 총 ‘판매액’을 표시합니다. 

![필드 창이 표시된 시각적 개체](media/desktop-composite-models/composite-models_11.png)

이 예제에서는 다른 곳에서 가져온 일부 추가 데이터로 확장되는 ‘차원’ 테이블(예: *Product* 또는 *Customer*)의 일반적인 사례를 보여주며 테이블에서 다른 원본에 대한 DirectQuery 연결을 사용할 수도 있습니다. 이제 예제를 확장하기 위해 *Country* 및 *Period*별 *SalesTargets*이 별도의 부서별 데이터베이스에 저장된다고 가정합니다. 다음 이미지와 같이 **GetData**를 사용하여 일반적인 방법으로 해당 데이터에 연결할 수 있습니다. 

![탐색기 대화 상자](media/desktop-composite-models/composite-models_12.png)

그런 다음, 이 예제에서 이전에 수행한 작업처럼 새 테이블과 모델의 다른 테이블 간에 관계를 만들고 해당 데이터를 결합하는 시각적 개체를 만들 수 있습니다. 확장된 예제 시나리오에서 새 관계를 설정한 **관계 보기**를 다시 살펴보겠습니다.

![여러 테이블이 있는 관계 보기](media/desktop-composite-models/composite-models_13.png)

방금 만든 새 데이터 및 관계를 기반으로 하는 다음 이미지와 같이 왼쪽 아래 모서리에 있는 시각적 개체는 차이를 보여주는 차이 계산과 함께 총 ‘판매액’ 및 ‘대상’을 표시합니다. 여기서 ‘판매액’ 및 ‘대상’은 두 개의 다른 SQL Server 데이터베이스에서 가져옵니다. 

![더 많은 데이터를 표시하는 시각적 개체](media/desktop-composite-models/composite-models_14.png)

## <a name="setting-storage-mode"></a>저장소 모드 설정

**복합 모델**의 각 테이블에는 테이블이 DirectQuery 또는 가져오기를 기반으로 하는지 여부를 나타내는 **저장소 모드**가 있습니다. **저장소 모드**는 **속성** 창에서 보고 수정할 수 있습니다. 이 창으로 이동하려면 **필드** 목록의 마우스 오른쪽 클릭 상황에 맞는 메뉴에서 **속성**을 선택합니다. 다음 이미지는 **저장소 모드**를 보여줍니다(창 너비 때문에 이미지에는 **저장소 ...** 로 축약됨).

![저장소 모드 설정](media/desktop-composite-models/composite-models_15.png)

각 테이블의 도구 설명에서도 **저장소 모드**를 확인할 수 있습니다.

![저장소 모드가 있는 도구 설명](media/desktop-composite-models/composite-models_16.png)

DirectQuery 및 일부 가져오기 테이블의 일부 테이블을 포함하는 **Power BI Desktop** 파일(.pbix 파일)의 경우 상태 표시줄에는 **혼합**의 **저장소 모드**가 표시됩니다. 상태 표시줄에서 해당 용어를 클릭하여 모든 테이블을 가져오기로 쉽게 전환할 수 있습니다.

**저장소 모드**는 [Power BI Desktop(미리 보기)의 저장소 모드](desktop-storage-mode.md) 문서에서 자세히 설명합니다.  

## <a name="calculated-tables"></a>계산된 테이블

DirectQuery를 사용하는 모델에 계산된 테이블을 추가할 수 있으며, 계산된 테이블을 정의하는 DAX는 가져온 테이블이나 DirectQuery 테이블 또는 두 가지의 조합을 참조할 수 있습니다. 

계산된 테이블은 항상 가져오며 테이블을 새로 고칠 때 해당 테이블의 데이터가 새로 고쳐집니다. 따라서 계산된 테이블이 DirectQuery 테이블을 참조하는 경우 DirectQuery 테이블을 참조하는 시각적 개체는 항상 기본 원본의 최신 값을 표시하지만, 계산된 테이블을 참조하는 시각적 개체는 계산된 테이블을 마지막으로 새로 고친 시간의 값을 표시합니다.

## <a name="security-implications"></a>보안 의미 

복합 모델에는 일부 보안 의미가 있습니다. 한 데이터 원본에 전송된 쿼리는 또 다른 원본에서 검색된 데이터 값을 포함할 수 있습니다. 이 문서의 앞부분에서 설명한 예제의 경우 ‘제품 관리자’별 ‘판매액’을 표시하는 시각적 개체는 **Sales** 관계형 데이터베이스로 전송되는 SQL 쿼리를 생성하고, 여기서 SQL 쿼리에는 ‘제품 관리자’의 이름과 연결된 ‘제품’이 포함될 수 있습니다. 

![보안 의미를 표시하는 스크립트](media/desktop-composite-models/composite-models_17.png)

이로 인해 스프레드시트에 저장된 정보가 이제 관계형 데이터베이스에 전송되는 쿼리에 포함됩니다. 이 정보가 기밀 정보인 경우에는 이 정보의 보안 의미를 고려해야 합니다. 특히 다음 의미를 고려해야 합니다.

* 추적 또는 감사 로그를 볼 수 있는 데이터베이스의 모든 관리자는 원래 원본의 데이터에 대한 권한(이 경우 Excel 파일에 대한 권한)이 없는 경우에도 이 정보를 볼 수 있습니다.

* 정보가 암호화된 연결을 사용하는 한 원본에서 검색된 후 암호화되지 않은 연결을 사용하는 또 다른 원본으로 전송되는 쿼리에 실수로 포함되지 않게 하려면 각 원본에 대한 암호화 설정을 고려해야 합니다. 

복합 모델을 만드는 작업을 수행하면 보안 의미가 고려되었는지 확인할 수 있는 경고 메시지가 **Power BI Desktop**에서 표시됩니다.  

비슷한 이유로 신뢰할 수 없는 원본에서 전송된 **Power BI Desktop** 파일을 열 때 주의해야 합니다. 해당 파일에 복합 모델이 포함된 경우 이는 파일을 여는 사용자의 자격 증명 사용하는 한 원본에서 검색된 정보가, Power BI Desktop 파일의 악의적인 작성자가 확인할 수 있는 쿼리에 포함된 또 다른 데이터 원본으로 전송됨을 의미합니다. 따라서 Power BI Desktop 파일을 처음 열 때 여러 원본이 포함된 경우에는 경고가 표시됩니다. 이 경고는 네이티브 SQL 쿼리를 포함하는 파일을 열 때 표시되는 경고와 비슷합니다.  

## <a name="performance-implications"></a>성능 의미  

DirectQuery를 사용하는 경우 주로 사용자에게 좋은 환경을 제공할 충분한 리소스가 백 엔드 원본에 있는지 확인하기 위해 성능을 항상 고려해야 합니다. 좋은 환경에서는 시각적 개체가 5초 이내에 새로 고쳐집니다. 또한 [Power BI의 DirectQuery 사용](desktop-directquery-about.md) 문서에서 성능 관련 정보를 준수해야 합니다. 단일 시각적 개체의 결과로 쿼리가 여러 원본으로 전송될 수 있어 종종 한 쿼리의 결과가 두 번째 원본으로 전달되므로 복합 모델을 사용할 경우 추가적인 성능 관련 정보를 고려해야 합니다. 이 상황에서는 다음과 같은 가능한 실행 형식이 나타날 수 있습니다.

* **많은 리터럴 값을 포함하는 SQL 쿼리** - 예를 들어 스프레드시트에서 가져온 관련 테이블의 선택된 ‘프로젝트 관리자’ 집합에 대한 SQL 데이터베이스의 총 ‘판매액’을 요청하는 시각적 개체는 먼저 해당 프로젝트 관리자가 관리한 ‘제품’을 찾은 후 *WHERE* 절에 모든 제품 ID가 포함된 SQL 쿼리를 보내야 합니다.

* **나중에 로컬로 집계되는 데이터를 사용하여 대략적인 수준에서 쿼리하는 SQL 쿼리** - 목록의 이전 말머리 기호 항목과 동일한 예제를 사용하면 ‘제품 관리자’에 대한 필터를 충족하는 ‘제품’ 수가 매우 커지므로 특정 시점에 모든 제품을 *WHERE* 절에 포함하기에 부족하거나 포함할 수 없게 됩니다. 대신 ‘제품’의 하위 수준에서 관계형 원본을 쿼리한 후 로컬로 결과를 집계해야 합니다. *Products*의 카디널리티가 1백만 개 제한을 초과하면 쿼리가 실패합니다.

* **여러 SQL 쿼리, 값별로 그룹당 하나** - 다른 원본의 일부 열별로 그룹화된 **DistinctCount**를 집계에서 사용할 때 외부 원본이 그룹을 정의하는 많은 리터럴 값을 효율적으로 전달할 수 없는 경우에는 값별로 그룹당 하나의 SQL 쿼리를 보내야 합니다. 예를 들어 스프레드시트에서 가져온 관련 테이블의 ‘제품 관리자’가 SQL Server 테이블의 개별 *CustomerAccountNumber* 개수를 요청하는 시각적 개체는 SQL Server로 전송되는 쿼리에서 *Product Managers* 테이블의 세부 정보를 전달해야 합니다. Redshift와 같은 다른 원본을 사용하면 이를 실행할 수 없고 ‘영업 관리자’당 하나의 SQL 쿼리가 전송됩니다(쿼리가 실패하는 실제적인 제한까지). 

이러한 각 사례에는 성능에 대한 고유한 의미가 있고 각 데이터 원본에 대한 정확한 세부 정보는 달라집니다. 두 원본을 조인하는 관계에 사용되는 열의 카디널리티가 낮게(몇천 개) 유지되지만 성능에는 큰 영향을 미치지 않아야 하는 것이 경험에 의한 좋은 방법입니다. 이 카디널리티가 증가하면 결과 성능에 미치는 영향에 더 많은 것을 고려해야 합니다. 

또한 **다 대 다** 관계의 사용은 세부 값을 로컬로 집계하는 것보다 각 합계/소계 수준에 대한 기본 원본에 개별 쿼리를 보내야 함을 의미합니다. 따라서 합계가 있는 간단한 테이블 시각적 개체는 하나가 아닌 두 개의 SQL 쿼리를 보냅니다. 

## <a name="limitations-and-considerations"></a>제한 사항 및 고려 사항

**복합 모델**의 이 릴리스에는 몇 가지 제한 사항이 있습니다.

다음 Live Connect(다차원) 원본은 **복합 모델**과 함께 사용할 수 없습니다.

* SAP HANA
* SAP Business Warehouse
* SQL Server Analysis Services
* Power BI 데이터 집합
* Azure Analysis Services

DirectQuery를 사용하여 이러한 다차원 원본에 연결할 경우 다른 DirectQuery 원본에 연결할 수 없고 가져온 데이터와 결합할 수도 없습니다.

DirectQuery 사용에 대한 기존 제한 사항은 **복합 모델**을 사용할 경우에도 적용됩니다. 이러한 제한 사항 중 대부분은 테이블의 **저장소 모드**에 따라 테이블별로 적용됩니다. 예를 들어 가져온 테이블의 계산 열은 다른 테이블을 참조할 수 있지만, DirectQuery 테이블에서 계산 열은 동일한 테이블의 열만 참조하도록 제한됩니다. 다른 제한 사항은 모델 내의 테이블이 DirectQuery인 경우 모델에 전체적으로 적용됩니다. 예를 들어 **QuickInsights** 및 **Q&A** 기능은 모델 내의 테이블에 DirectQuery의 **저장소 모드**가 있는 경우 해당 모델에서 사용할 수 없습니다. 

## <a name="next-steps"></a>다음 단계

다음 문서에서는 복합 모델을 자세히 설명하고 DirectQuery도 자세히 설명합니다.

* [Power BI Desktop의 다 대 다 관계(미리 보기)](desktop-many-to-many-relationships.md)
* [Power BI Desktop의 저장소 모드(미리 보기)](desktop-storage-mode.md)

DirectQuery 문서:

* [Power BI의 DirectQuery 사용](desktop-directquery-about.md)
* [Power BI의 DirectQuery에서 지원하는 데이터 원본](desktop-directquery-data-sources.md)

