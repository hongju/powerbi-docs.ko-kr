---
title: Power BI Desktop에서 집계 사용 및 관리
description: 집계를 사용하여 Power BI Desktop에서 빅 데이터에 대한 대화형 분석을 수행합니다.
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/16/2020
ms.author: davidi
LocalizationGroup: Transform and shape data
ms.openlocfilehash: d8db626300902125cf3536f03ed111ef3e052324
ms.sourcegitcommit: 8e3d53cf971853c32eff4531d2d3cdb725a199af
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "76538746"
---
# <a name="use-aggregations-in-power-bi-desktop"></a>Power BI Desktop에서 집계 사용

Power BI의 *집계*를 사용하면 테이블 크기를 줄여 중요한 데이터에 집중하고 쿼리 성능을 향상할 수 있습니다. 집계를 사용하면 다른 방법으로는 불가능한 방식으로 빅 데이터에 대한 대화형 분석을 수행할 수 있으며, 의사 결정을 위해 빅 데이터 세트를 잠금 해제하는 비용을 크게 줄일 수 있습니다.

집계를 사용하면 다음과 같은 이점이 있습니다.

- **빅 데이터에 대한 쿼리 성능 향상**. Power BI 시각적 개체와의 모든 상호 작용은 DAX 쿼리를 데이터 세트에 제출합니다. 캐시된 집계 데이터는 세부 데이터에 필요한 리소스의 일부를 사용하므로, 다른 방법으로는 액세스할 수 없는 빅 데이터의 잠금을 해제할 수 있습니다.
- **최적화된 데이터 새로 고침**. 캐시 크기가 작을수록 새로 고침 시간이 줄어들고 데이터가 사용자에게 빠르게 전달됩니다.
- **균형 잡힌 아키텍처**. Power BI의 메모리 내 캐시는 집계된 쿼리를 처리할 수 있으며 DirectQuery 모드에서 전송된 쿼리를 제한하여 동시성 제한을 충족하는 데 도움이 됩니다. 나머지 세부 수준 쿼리는 데이터 웨어하우스 및 빅 데이터 시스템에서 일반적으로 잘 처리하는 트랜잭션 수준 쿼리로 필터링되는 경향이 있습니다.

![Microsoft Power BI Desktop의 집계](media/desktop-aggregations/aggregations_07.jpg)

데이터 웨어하우스와 데이터 마트 같은 차원 데이터 원본은 [관계 기반 집계](#aggregation-based-on-relationships)를 사용할 수 있습니다. Hadoop 기반 빅 데이터 원본은 종종 [GroupBy 열에 대한 기본 집계](#aggregation-based-on-groupby-columns)를 수행하기도 합니다. 이 문서에서는 각 유형의 데이터 원본에 대한 일반적인 Power BI 모델링 차이점에 대해 설명합니다.

## <a name="create-an-aggregated-table"></a>집계 테이블 만들기

집계 테이블을 만들려면 다음을 수행해야 합니다.
1. 데이터 원본 및 모델에 따라 원하는 필드를 사용하여 새 테이블을 설정합니다. 
1. **집계 관리** 대화 상자를 사용하여 집계를 정의합니다.
1. 해당하는 경우 집계된 테이블에 대한 [스토리지 모드](#storage-modes)를 변경합니다. 

### <a name="manage-aggregations"></a>집계 관리

원하는 필드를 포함하는 새 테이블을 만든 후 Power BI Desktop 보기의 **필드** 창에서 테이블을 마우스 오른쪽 단추로 클릭하고 **집계 관리**를 선택합니다.

![집계 관리 선택](media/desktop-aggregations/aggregations-06.png)

**집계 관리** 대화 상자에는 테이블의 각 열에 대한 행이 표시되며, 여기서 집계 동작을 지정할 수 있습니다. 다음 예에서는 **판매** 세부 정보 테이블에 대한 쿼리가 내부적으로 **판매 집계** 집계 테이블로 리디렉션됩니다. 

**집계 관리** 대화 상자의 **요약** 드롭다운은 다음 값을 제공합니다.
- 개수
- GroupBy
- Max
- 최소
- 합계
- 테이블 행 개수

![집계 관리 대화 상자](media/desktop-aggregations/aggregations_07.jpg)

이 관계 기반 집계 예제에서 GroupBy 항목은 선택 사항입니다. DISTINCTCOUNT를 제외하고는 집계 동작에 영향을 주지 않으며 주로 가독성을 높이기 위한 것입니다. GroupBy 항목이 없는 경우에도 집계는 관계를 기반으로 하여 계속 적중합니다. 해당 내용은 이 문서 뒷부분에 있는 GroupBy 항목이 필요한 [빅 데이터 예제](#aggregation-based-on-groupby-columns)와 다릅니다.

원하는 집계를 정의한 후 **모두 적용**을 선택합니다. 

### <a name="validations"></a>유효성 검사

**집계 관리** 대화 상자는 다음과 같은 주목할 만한 유효성 검사를 시행합니다.

- **세부 정보 열**에는 Count 및 Count 테이블 행 **요약 함수**를 제외하고는 **집계 열**과 동일한 데이터 형식이 있어야 합니다. Count 및 테이블 행 수 계산은 정수 집계 열에 대해서만 사용할 수 있으며, 일치하는 데이터 형식은 필요하지 않습니다.
- 셋 이상의 테이블이 포함된 연결 집계는 허용되지 않습니다. 예를 들어 **테이블 A**에 대한 집계는 **테이블 C**를 참조하는 집계가 있는 **테이블 B**를 참조할 수 없습니다.
- 두 항목에서 동일한 **요약** 함수를 사용하고 동일한 **세부 정보 테이블** 및 **세부 정보 열**을 참조하는 중복 집계는 허용되지 않습니다.
- **정보 테이블**은 가져오기가 아닌 DirectQuery 스토리지 모드를 사용해야 합니다.
- 비활성 관계에서 사용되는 외래 키 열로 그룹화하고 집계 적중에 USERELATIONSHIP 함수를 사용하는 기능은 지원되지 않습니다.

대부분의 이러한 유효성 검사는 다음 이미지와 같이 드롭다운 값을 사용하지 않도록 설정하고 도구 설명에 설명 텍스트를 표시함으로써 적용됩니다.

![도구 설명에서 보여 주는 유효성 검사](media/desktop-aggregations/aggregations_08.jpg)

### <a name="aggregation-tables-are-hidden"></a>집계 테이블 숨김

데이터 세트에 대한 읽기 전용 액세스 권한이 있는 사용자는 집계 테이블을 쿼리할 수 없습니다. 따라서 *RLS(행 수준 보안)* 와 함께 사용하는 경우 보안 문제가 방지됩니다. 소비자 및 쿼리는 집계 테이블이 아닌 세부 정보 테이블을 참조하며, 집계 테이블에 대해 알 필요가 없습니다.

이러한 이유로 집계 테이블은 **보고서** 보기에서 숨겨집니다. 테이블이 아직 숨겨져 있지 않은 경우 **모두 적용**을 선택하면 **집계 관리** 대화 상자에서 이를 숨김으로 설정합니다.

### <a name="storage-modes"></a>스토리지 모드
집계 기능은 테이블 수준 스토리지 모드와 상호 작용합니다. Power BI 테이블은 *DirectQuery*, *가져오기* 또는 *이중* 스토리지 모드를 사용할 수 있습니다. DirectQuery는 백엔드를 직접 쿼리하지만 가져오기는 메모리에 데이터를 캐시하고 캐시된 데이터로 쿼리를 보냅니다. 모든 Power BI 가져오기 및 다차원이 아닌 DirectQuery 데이터 원본은 집계와 함께 작동할 수 있습니다. 

집계된 테이블의 스토리지 모드를 가져오기로 설정하여 쿼리 속도를 높이려면 **모델** 보기에서 Power BI Desktop의 집계 테이블을 선택합니다. **속성** 창에서 **고급**을 확장하고 **스토리지 모드**에서 선택을 드롭다운한 다음 **가져오기**를 선택합니다. 이 작업은 되돌릴 수 없습니다. 

![스토리지 모드 설정](media/desktop-aggregations/aggregations-04.png)

테이블 스토리지 모드에 대한 자세한 내용은 [Power BI Desktop의 스토리지 모드 관리](desktop-storage-mode.md)를 참조하세요.

### <a name="rls-for-aggregations"></a>집계에 대한 RLS

RLS(행 수준 보안) 식이 집계에 대해 올바르게 작동하려면 집계 테이블과 세부 정보 테이블을 둘 다 필터링해야 합니다. 

예제를 계속 살펴보면, Geography가 **판매** 테이블 및 **판매 집계** 테이블에 모두에 대한 관계의 필터링 쪽에 있으므로 **Geography** 테이블의 RLS 식은 집계에 사용됩니다. 집계 테이블에 도달하는 쿼리와 도달하지 않는 쿼리 모두에서 RLS가 성공적으로 적용됩니다.

![집계를 위한 성공적인 RLS](media/desktop-aggregations/manage-roles.png)

**제품** 테이블의 RLS 식은 집계된 **판매 집계** 테이블이 아니라 세부 **판매** 테이블만 필터링합니다. 집계 테이블은 세부 정보 테이블에 있는 동일한 데이터의 다른 표현이기 때문에 RLS 필터를 적용할 수 없다면 집계 테이블의 쿼리에 응답하는 것은 안전하지 않습니다. 이 역할의 사용자 쿼리는 집계 적중의 이점을 활용하지 않으므로 세부 정보 테이블만 필터링하지 않는 것이 좋습니다. 

**판매 집계** 집계 테이블만 필터링하고 **판매** 세부 정보 테이블은 필터링하지 않는 RLS 식은 허용되지 않습니다.

![집계 테이블에서만 RLS를 사용할 수 없습니다.](media/desktop-aggregations/filter-agg-error.jpg)

[GroupBy 열을 기반으로 하는 집계](#aggregation-based-on-groupby-columns)의 경우, 집계 테이블의 모든 GroupBy 열이 세부 정보 테이블에서 처리되므로 세부 정보 테이블에 적용된 RLS 식을 사용하여 집계 테이블을 필터링할 수 있습니다. 반면에 집계 테이블의 RLS 필터는 세부 정보 테이블에 적용할 수 없으므로, 허용되지 않습니다.

## <a name="aggregation-based-on-relationships"></a>관계 기반 집계

차원 모델은 일반적으로 *관계에 따른 집계*를 사용합니다. 데이터 웨어하우스 및 데이터 마트의 Power BI 데이터 세트는 차원 테이블과 팩트 테이블 간의 관계가 있는 별모양 스키마 및 눈송이 스키마와 비슷합니다.

단일 데이터 원본의 다음 모델에서 테이블은 DirectQuery 스토리지 모드를 사용합니다. **Sales**(판매) 팩트 테이블에는 수십억 개의 행이 있습니다. 캐싱을 위해 **판매**의 스토리지 모드를 가져오기로 설정하면 상당한 메모리 및 관리 오버헤드가 사용됩니다.

![모델의 세부 정보 테이블](media/desktop-aggregations/aggregations_02.jpg)

대신 **판매 집계** 집계 테이블을 만듭니다. **판매 집계** 테이블에서 행 수는 **CustomerKey**, **DateKey**및 **ProductSubcategoryKey**별로 그룹화된 **SalesAmount Amount**의 합계와 같습니다. **판매 집계** 테이블은 **판매**보다 높은 세분성을 가지므로 수십억 대신 수백만 행이 포함되어 관리하기가 훨씬 쉽습니다.

다음 차원 테이블이 비즈니스 가치가 높은 쿼리에 가장 일반적으로 사용되는 경우에는 *일 대 다* 또는 *다 대 일* 관계를 사용하여 **판매 집계**를 필터링할 수 있습니다.

- 지리
- 고객
- 날짜
- 제품 하위 범주
- Product Category(제품 범주)

다음 이미지에서는 이 모델을 보여 줍니다.

![모델의 집계 테이블](media/desktop-aggregations/aggregations_03.jpg)

다음 표에는 **판매 집계** 테이블에 대한 집계가 나와 있습니다.

![판매 집계 테이블의 집계](media/desktop-aggregations/aggregations-table_01.jpg)

> [!NOTE]
> **판매 집계** 테이블은 다른 테이블과 마찬가지로 다양한 방식으로 유연하게 로드할 수 있습니다. 집계는 ETL/ELT 프로세스를 사용하거나 테이블에 대한 [M 식](/powerquery-m/power-query-m-function-reference)을 통해 원본 데이터베이스에서 수행할 수 있습니다. 집계 테이블은 [Power BI Premium에서 증분 새로 고침](service-premium-incremental-refresh.md)을 사용하는지 여부와 관계없이 가져오기 스토리지 모드를 사용하거나, DirectQuery를 사용할 수 있고 [columnstore 인덱스](/sql/relational-databases/indexes/columnstore-indexes-overview)를 사용하여 빠르게 쿼리하도록 최적화될 수 있습니다. 이러한 유연성 덕분에 쿼리 로드를 분산시키는 분산된 아키텍처를 가능하게 하여 병목 현상을 방지할 수 있습니다.

집계된 **판매 집계** 테이블의 스토리지 모드를 **가져오기**로 변경하면 관련 차원 테이블을 스토리지 모드 *이중*으로 설정할 수 있는 대화 상자가 열립니다. 

![스토리지 모드 대화 상자](media/desktop-aggregations/aggregations_05.jpg)

관련 차원 테이블을 이중으로 설정하면 하위 쿼리에 따라 [가져오기] 또는 DirectQuery로 작동할 수 있습니다. 예제:

- 가져오기 모드의 **판매 집계** 테이블에서 메트릭을 집계하고 관련 이중 테이블의 특성별로 그룹화하는 쿼리는 메모리 내 캐시에서 반환될 수 있습니다.
- DirectQuery의 **판매** 테이블에서 집계 메트릭을 쿼리하고 관련 이중 테이블의 특성별로 그룹화하는 쿼리는 DirectQuery 모드에서 반환할 수 있습니다. 그룹화 작업이 포함된 쿼리 논리는 원본 데이터베이스로 전달됩니다.

이중 스토리지 모드에 대한 자세한 내용은 [Power BI Desktop의 스토리지 모드 관리](desktop-storage-mode.md)를 참조하세요.

### <a name="strong-vs-weak-relationships"></a>강력 관계 대 약한 관계

관계를 기반으로 하는 집계 적중은 강력한 관계가 필요합니다.

강력한 관계에는 두 테이블이 모두 단일 원본에 있는 다음과 같은 스토리지 모드 조합이 포함됩니다.

| *다* 쪽의 테이블 | ‘일’ 쪽의 테이블  |
| ------------- |----------------------| 
| 이중          | 이중                 | 
| 가져오기        | 가져오기 또는 이중       | 
| DirectQuery   | DirectQuery 또는 이중  | 

*cross-source* 관계가 강력한 것으로 간주되는 유일한 경우는 두 테이블이 모두 가져오기로 설정된 경우입니다. 다 대 다 관계는 항상 약한 관계로 간주됩니다.

관계에 의존하지 않는 *cross-source* 집계 적중의 경우 [GroupBy 열 기반 집계](#aggregation-based-on-groupby-columns)를 참조하세요. 

### <a name="relationship-based-aggregation-query-examples"></a>관계 기반 집계 쿼리 예제

**Date** 테이블의 열이 집계에 도달할 수 있는 세분성을 가지기 때문에 다음 쿼리는 집계에 도달합니다. **SalesAmount** 열은 **Sum** 집계를 사용합니다.

![성공적인 관계 기반 집계 쿼리](media/desktop-aggregations/aggregations-code_02.jpg)

다음 쿼리는 집계에 적중하지 않습니다. **SalesAmount**의 합계를 요청했지만 쿼리가 **제품** 테이블의 열에 대해 그룹화 작업을 수행하고 있으며, 이는 집계에 영향을 줄 수 있는 세분성이 아닙니다. 모델에서 관계를 관찰하는 경우 제품 하위 범주에는 여러 **제품** 행이 있을 수 있습니다. 쿼리에서 집계할 제품을 확인할 수 없습니다. 이 경우 쿼리는 DirectQuery로 되돌아가고 SQL 쿼리를 데이터 원본에 제출합니다.

![집계를 사용할 수 없는 쿼리](media/desktop-aggregations/aggregations-code_03.jpg)

집계는 단순 합계를 수행하는 간단한 계산만을 위한 것이 아닙니다. 복잡한 계산에도 활용할 수 있습니다. 개념적으로 복잡한 계산은 각 SUM, MIN, MAX 및 COUNT에 대한 하위 쿼리로 분할되고, 집계에 적중할 수 있는지 판단하기 위해 각 하위 쿼리가 평가됩니다. 이 논리는 쿼리 계획 최적화로 인해 모든 경우에 적용되는 것은 아니지만 일반적으로 적용해야 합니다. 다음 예제는 집계에 적중합니다.

![복합 집계 쿼리](media/desktop-aggregations/aggregations-code_04.jpg)

COUNTROWS 함수는 집계를 통해 이점을 얻을 수 있습니다. **Sales** 테이블에 대해 정의된 테이블 행 수 **계산** 집계가 있으므로 다음 쿼리는 집계에 적중합니다.

![COUNTROWS 집계 쿼리](media/desktop-aggregations/aggregations-code_05.jpg)

AVERAGE 함수는 집계를 통해 이점을 얻을 수 있습니다. AVERAGE가 내부적으로 COUNT로 나눈 SUM으로 접혀 있으므로 다음 쿼리는 집계에 적중합니다. **UnitPrice** 열에 SUM 및 COUNT에 대해 정의된 집계가 있으므로 집계에 적중합니다.

![평균 집계 쿼리](media/desktop-aggregations/aggregations-code_06.jpg)

경우에 따라 DISTINCTCOUNT 함수는 집계를 통해 이점을 얻을 수 있습니다. 집계 테이블에서 **CustomerKey**의 고유성을 유지하는 **CustomerKey**에 대한 GroupBy 항목이 있으므로 다음 쿼리는 집계에 적중합니다. 이 기술은 200만~500만 개 이상의 고유 값이 쿼리 성능에 영향을 줄 수 있는 성능 임계값에 여전히 도달할 수 있습니다. 그러나 세부 정보 테이블에 수십억 개의 행이 있지만 열에 200만~500만 개의 고유 값이 있는 시나리오에서 유용할 수 있습니다. 이 경우 메모리에 캐시된 경우에도 수십억 개의 행이 있는 테이블을 검사하는 것보다 DISTINCTCOUNT가 더 빨리 수행될 수 있습니다.

![DISTINCTCOUNT 집계 쿼리](media/desktop-aggregations/aggregations-code_07.jpg)

## <a name="aggregation-based-on-groupby-columns"></a>GroupBy 열을 기반으로 하는 집계 

Hadoop 기반 빅 데이터 모델에는 차원 모델과 다른 특징이 있습니다. 큰 테이블 간의 조인을 방지하기 위해 빅 데이터 모델은 대개 관계를 사용하지 않지만 팩트 테이블에 차원 특성을 비정규화합니다. *GroupBy 열 기반* 집계를 사용하여 대화형 분석을 위해 이러한 빅 데이터 모델의 잠금을 해제할 수 있습니다.

다음 표에는 집계할 **이동** 숫자 열이 있습니다. 다른 모든 열은 그룹화할 특성입니다. 테이블에는 IoT 데이터와 엄청난 수의 행이 포함됩니다. 스토리지 모드는 DirectQuery입니다. 전체 데이터 세트에 걸쳐 집계되는 데이터 원본에 대한 쿼리의 경우 엄청난 양으로 인해 속도가 느립니다. 

![IoT 테이블](media/desktop-aggregations/aggregations_09.jpg)

이 데이터 세트에서 대화형 분석을 사용하려면 대부분의 특성을 그룹화하지만 경도 및 위도와 같은 높은 카디널리티 특성은 제외하는 집계 테이블을 추가할 수 있습니다. 이렇게 하면 행 수가 크게 줄어들고 메모리 내 캐시에 쉽게 맞출 수 있을 만큼 작습니다. 

![Driver Activity Agg 테이블](media/desktop-aggregations/aggregations_10.jpg)

**집계 관리** 대화 상자에서 **드라이버 작업 집계** 테이블에 대한 집계 매핑을 정의하세요. 

![Driver Activity Agg 테이블에 대한 집계 관리 대화 상자](media/desktop-aggregations/aggregations_11.jpg)

GroupBy 열을 기반으로 하는 집계에서 **GroupBy** 항목은 선택 사항이 아닙니다. 해당 항목이 없으면 집계가 적중되지 않습니다. GroupBy 항목을 선택할 수 있을 때 관계 기반 집계를 사용하는 것과는 다릅니다.

다음 표에는 **드라이버 작업 집계** 테이블에 대한 집계가 나와 있습니다.

![Driver Activity Agg 집계 테이블](media/desktop-aggregations/aggregations-table_02.jpg)

집계된 **드라이버 작업 집계** 테이블의 스토리지 모드를 설정하여 가져올 수 있습니다.

### <a name="groupby-aggregation-query-example"></a>GroupBy 집계 쿼리 예제

**활동 날짜** 열이 집계 테이블에 포함되어 있으므로 다음 쿼리는 집계에 적중합니다. **테이블 행 수 계산** 집계는 COUNTROWS 함수에서 사용됩니다.

![성공적인 GroupBy 집계 쿼리](media/desktop-aggregations/aggregations-code_08.jpg)

특히 팩트 테이블에 필터 특성이 포함된 모델의 경우 **테이블 행 수 계산** 집계를 사용하는 것이 좋습니다. 사용자가 명시적으로 요청하지 않은 경우 Power BI에서 COUNTROWS를 사용하여 데이터 세트에 쿼리를 제출할 수 있습니다. 예를 들어 필터 대화 상자에서는 각 값에 대한 행 수를 표시합니다.

![필터 대화 상자](media/desktop-aggregations/aggregations-12.png)

## <a name="combined-aggregation-techniques"></a>결합된 집계 기술

집계에 대한 관계 및 GroupBy 열 기법을 결합할 수 있습니다. 관계를 기반으로 하는 집계에서는 비정규화된 차원 테이블을 여러 테이블로 분할해야 할 수 있습니다. 특정 차원 테이블이 비용이 많이 들고 실용적이지 않은 경우에는 해당 차원에 대한 집계 테이블에서 필요한 특성을 복제하고 다른 차원에 대한 관계를 사용할 수 있습니다.

예를 들어 다음 모델은 **판매 집계** 테이블에서 **월**, **분기**, **반기** 및 **연도**를 복제합니다. **판매 집계**와 **날짜** 테이블 간에는 관계가 없지만 **고객** 및 **제품 하위 범주**에 대한 관계가 있습니다. **판매 집계**의 스토리지 모드는 [가져오기]입니다.

![결합된 집계 기술](media/desktop-aggregations/aggregations_15.jpg)

다음 표에는 **판매 집계** 테이블에 대한 **집계 관리** 대화 상자에 설정된 항목이 나와 있습니다. **Date**가 세부 정보 테이블인 GroupBy 항목은 **Date** 특성별로 그룹화된 쿼리에 대한 집계에 강제로 적중해야 합니다. 앞의 예제와 같이 관계가 있으므로 **CustomerKey** 및 **ProductSubcategoryKey**에 대한 **GroupBy** 항목은 DISTINCTCOUNT를 제외하고 집계 적중 횟수에 영향을 주지 않습니다.

![판매 집계의 집계 테이블 항목](media/desktop-aggregations/aggregations-table_04.jpg)

### <a name="combined-aggregation-query-examples"></a>결합된 집계 쿼리 예제

집계 테이블에서 일 대 다 관계를 통해 **CalendarMonth**와 **CategoryName**에 액세스할 수 있으므로 다음 쿼리는 집계에 적중합니다. **SalesAmount**는 **SUM** 집계를 사용합니다.

![집계를 적중하는 쿼리 예제](media/desktop-aggregations/aggregations-code_09.jpg)

집계 테이블에서 **CalendarDay**를 포함하지 않으므로 다음 쿼리는 집계에 적중하지 않습니다.

![집계에 적중하지 않는 쿼리 예제](media/desktop-aggregations/aggregations-code_10.jpg)

DATESYTD 함수가 **CalendarDay** 값의 테이블을 생성하고 집계 테이블이 **CalendarDay**를 포함하지 않으므로 다음 시간 인텔리전스 쿼리는 집계에 적중하지 않습니다.

![집계에 적중하지 않는 쿼리 예제](media/desktop-aggregations/aggregations-code_11.jpg)

## <a name="aggregation-precedence"></a>집계 우선 순위

집계 우선 순위를 사용하면 단일 하위 쿼리에서 여러 집계 테이블을 고려할 수 있습니다.

다음 예는 여러 소스를 포함하는 [복합 모델](desktop-composite-models.md)입니다.

- **드라이버 작업** DirectQuery 테이블은 빅 데이터 시스템에서 제공하는 1조 개가 넘는 IoT 데이터 행을 포함합니다. 제어된 필터 컨텍스트에서 개별 IoT 판독 값을 볼 수 있도록 드릴스루 쿼리를 제공합니다.
- **드라이버 작업 집계** 테이블은 DirectQuery 모드의 중간 집계 테이블입니다. Azure SQL Data Warehouse에 10억 개가 넘는 행이 포함되며, columnstore 인덱스를 사용하여 원본에서 최적화됩니다.
- 그룹화 특성이 적고 낮은 카디널리티이므로 **드라이버 작업 Agg2** 가져오기 테이블의 세분성은 높습니다. 행 수는 수천 개만큼 적을 수 있으므로 메모리 내 캐시에 쉽게 맞출 수 있습니다. 이러한 특성은 고급 프로필의 경영진 대시보드에서 사용되므로 이러한 특성을 참조하는 쿼리는 최대한 빨리 처리해야 합니다.

> [!NOTE]
> 세부 정보 테이블에서 다른 데이터 원본을 사용하는 DirectQuery 집계 테이블은 집계 테이블이 SQL Server, Azure SQL 또는 Azure SQL Data Warehouse 원본에서 가져온 경우에만 지원됩니다.

이 모델의 메모리 공간은 비교적 작지만 큰 데이터 세트의 잠금을 해제합니다. 강점을 기반으로 하여 활용하는 아키텍처의 여러 구성 요소에 걸쳐 쿼리 로드를 분산시키므로 분산된 아키텍처를 나타냅니다.

![큰 데이터 세트의 잠금을 해제하는 작은 공간 모델용 테이블](media/desktop-aggregations/aggregations_13.jpg)

**드라이버 작업 Agg2**에 대한 **집계 관리** 대화 상자가 **우선 순위** 필드를 **드라이버 작업 집계**보다 높은 *10*으로 설정합니다. 우선 순위가 높은 설정은 집계를 사용하는 쿼리가 **드라이버 활동 Agg2**를 먼저 고려함을 의미합니다. **드라이버 작업 Agg2**에서 응답할 수 있는 세분성이 아닌 하위 쿼리는 **드라이버 작업 집계**를 대신 고려합니다. 집계 테이블 중 하나에서 응답할 수 없는 세부 정보 쿼리는 **드라이버 작업**으로 지정됩니다.

연결된 집계가 허용되지 않으므로 **세부 정보 테이블** 열에 지정된 테이블은 **드라이버 작업 집계**가 아니라 **드라이버 작업**입니다.

![집계 관리 대화 상자](media/desktop-aggregations/aggregations_14.jpg)

다음 표에는 **드라이버 작업 Agg2** 테이블에 대한 집계가 나와 있습니다.

![Driver Activity Agg2 집계 테이블](media/desktop-aggregations/aggregations-table_03.jpg)

## <a name="detect-whether-queries-hit-or-miss-aggregations"></a>쿼리가 집계에 적중했는지 아니면 무시했는지 검색

SQL 프로파일러는 메모리 내 캐시 스토리지 엔진에서 쿼리가 반환되는지 또는 DirectQuery를 통해 데이터 원본에 푸시되는지를 검색할 수 있습니다. 동일한 프로세스를 사용하여 집계가 적중되는지를 검색할 수 있습니다. 자세한 내용은 [캐시를 적중 또는 무시하는 쿼리](desktop-storage-mode.md#queries-that-hit-or-miss-the-cache)를 참조하세요. 

SQL 프로파일러는 `Query Processing\Aggregate Table Rewrite Query` 확장 이벤트도 제공합니다.

다음 JSON 코드 조각에서는 집계가 사용될 때의 이벤트 출력 예를 보여 줍니다.

- **matchingResult**는 하위 쿼리가 집계를 사용했음을 나타냅니다.
- **dataRequest**는 하위 쿼리에서 사용된 GroupBy 열과 집계된 열을 보여줍니다.
- **mapping**은 매핑된 집계 테이블의 열을 보여 줍니다.

![집계가 사용될 때의 이벤트 출력](media/desktop-aggregations/aggregations-code_01.jpg)

## <a name="keep-caches-in-sync"></a>캐시를 동기화 상태로 유지

메모리 내 캐시가 원본 데이터와 동기화된 상태로 유지되지 않으면 DirectQuery와 가져오기 및/또는 이중 스토리지 모드를 결합한 집계에서 다른 데이터가 반환될 수 있습니다. 예를 들어 쿼리 실행은 캐시된 값과 일치하도록 DirectQuery 결과를 필터링하여 데이터 문제를 마스크하려고 시도하지 않습니다. 필요한 경우 원본에서 이러한 문제를 처리하는 기술이 확립되어 있습니다. 성능 최적화는 비즈니스 요구 사항을 충족시키는 능력을 손상하지 않는 방식으로만 사용해야 합니다. 사용자는 데이터 흐름을 알고 있어야 하므로 이에 맞게 적절하게 설계해야 합니다. 

## <a name="next-steps"></a>다음 단계

복합 모델에 대한 자세한 내용은 다음을 참조하세요.

- [Power BI Desktop에서 복합 모델 사용](desktop-composite-models.md)
- [Power BI Desktop의 다 대 다 관계 적용](desktop-many-to-many-relationships.md)
- [Power BI Desktop의 스토리지 모드 관리](desktop-storage-mode.md)

DirectQuery에 대한 자세한 내용은 다음을 참조하세요.

- [Power BI에서 DirectQuery를 사용하는 방법](desktop-directquery-about.md)
- [Power BI 데이터 원본](desktop-directquery-data-sources.md)
