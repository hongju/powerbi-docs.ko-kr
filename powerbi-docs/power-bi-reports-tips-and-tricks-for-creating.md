---
title: 멋진 보고서를 만드는 팁
description: Power BI 서비스 및 Power BI Desktop에서 보고서를 만들기 위한 팁과 힌트
services: powerbi
documentationcenter: ''
author: mihart
manager: kfile
backup: willthom
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 04/13/2018
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: f1b92cf370dfdfdbeadd71ee954030aa8a79d338
ms.sourcegitcommit: 493f160d04ed411ff4741c599adc63ba1f65230f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="tips-and-tricks-for-creating-reports-in-power-bi-desktop-and-power-bi-service"></a>Power BI Desktop 및 Power BI 서비스에서 보고서를 만들기 위한 팁과 힌트
데이터를 최대한 활용하려면 추가 도움이 필요하기도 합니다. Microsoft Power BI Desktop, Power BI 서비스 ‘및’ 파워 피벗 추가 기능이 사용되고 파워 쿼리가 설치 및 사용되는 Microsoft Excel 2016 또는 Excel 2013 Pro-Plus 버전에서 보고서를 만들 때 사용할 수 있는 몇 가지 팁과 힌트를 모아두었습니다.

## <a name="power-bi-desktop"></a>Power BI Desktop

### <a name="learning-to-use-the-query-editor"></a>쿼리 편집기 사용 방법 학습
Power BI Desktop의 쿼리 편집기는 Excel 2013의 파워 쿼리 추가 기능과 유사합니다. Power BI 지원에는 몇 가지 유용한 문서가 있지만 support.office.com의 파워 쿼리 설명서를 검토하여 시작할 수도 있습니다.

[파워 쿼리 리소스 센터](https://support.office.com/article/Microsoft-Power-Query-for-Excel-Help-2b433a85-ddfb-420b-9cda-fe0e60b82a94)에서 추가 정보를 가져올 수 있습니다.

또한 [수식 참조](https://support.office.com/Article/Learn-about-Power-Query-formulas-6bc50988-022b-4799-a709-f8aafdee2b2f)를 볼 수 있습니다.

### <a name="data-types-in-query-editor"></a>쿼리 편집기의 데이터 형식
Power BI Desktop의 쿼리 편집기를 사용하여 데이터를 로드하는 경우 최상의 추측 데이터 형식 검색을 수행합니다.  수식을 사용할 경우 열의 데이터 형식 설정이 유지되지 않는 경우도 있습니다. 쿼리 탭에 처음 데이터 로드, 첫 행을 머리글로 사용, 열 추가, 그룹화 기준, 병합, 추가 작업을 수행한 이후와 처음 데이터 로드를 누르기 전에 열의 데이터 형식이 올바른지 확인해야 합니다.

기억해야 할 한 가지 중요한 사항: 데이터 표의 기울임꼴은 데이터 형식이 올바르게 설정되었음을 의미하지는 않습니다. 단지 데이터가 텍스트로 간주되지 않음을 의미할 뿐입니다.

### <a name="reference-queries-in-the-query-editor"></a>쿼리 편집기에서 쿼리 참조
Power BI Desktop에 있는 쿼리 편집기의 탐색기에서 쿼리 중 하나를 마우스 오른쪽 단추로 클릭하면 “참조”에 대한 옵션을 사용할 수 있습니다.  다음과 같은 이유로 유용합니다.

* 쿼리에 대한 데이터 소스로 파일을 사용하는 경우 파일의 절대 경로가 쿼리에 저장됩니다. Power BI Desktop 파일 또는 Excel  통합 문서를 공유하거나 이동할 때 경로 업데이트 시 경로를 한 번만 업데이트하면 되므로 시간이 절약됩니다.

기본적으로 모든 쿼리는 Excel 워크시트 또는 데이터 모델(또는 둘 다)로 로드됩니다. 일부 쿼리는 중간 단계이며 최종 사용자가 사용하는 용도가 아닙니다.  위에서 언급한 대로 쿼리를 참조할 때가 바로 이러한 경우입니다.  탐색기에서 쿼리를 마우스 오른쪽 단추로 클릭하고 "로드 사용" 옵션을 설정/해제하여 쿼리 로드 동작을 제어할 수 있습니다.  "로드 사용" 옆에 확인 표시가 없는 경우 쿼리 탭에서 계속 쿼리를 사용할 수 있으며 해당 쿼리를 다른 쿼리와 함께 사용할 수 있습니다.  이 기능은 특히 병합, 추가 및 참조 변환과 조합할 때 유용합니다.  그러나 쿼리 결과가 데이터 모델에 로드되지 않으므로 쿼리가 보고서 필드 목록 또는 데이터 모델을 복잡하게 만들지 않습니다.

### <a name="scatter-charts-need-a-point-identifier"></a>지점 식별자가 필요한 분산형 차트
온도와 시간으로 구성된 간단한 테이블을 예로 들고 판독값이 사용되었습니다. 이 테이블을 분산형 차트에서 직접 그리는 경우 Power BI는 모든 값을 단일 요소로 집계합니다. 개별 데이터 요소를 표시하려면 필드 집합의 세부 정보 버킷에 필드를 추가해야 합니다.   Power BI Desktop에서 이 작업을 간단하게 수행하려면 쿼리 탭의 “열 추가” 리본에서 “인덱스 열 추가” 옵션을 사용하면 됩니다.

### <a name="reference-lines-in-your-report"></a>보고서의 참조선
Power BI Desktop에서 계산 열을 사용하여 참조선을 정의할 수 있습니다.  참조선을 만들 테이블 및 열을 식별합니다.  리본에서 "새 열"을 선택하고 수식 입력줄에서 다음 수식을 입력합니다.

    Target Value = 100

이 계산 열은 사용된 위치와 관계없이 값 100을 반환합니다.  필드 목록에 새 열이 표시됩니다.  대상 값 계산 열을 꺾은선형 차트에 추가하여 해당 특정 참조선과 모든 계열이 어떻게 관련되는지를 표시합니다.  

### <a name="sort-by-another-column"></a>다른 열 기준 정렬
Power BI에서 차트 축이나 슬라이서 또는 필터에 범주(문자열) 값을 사용하는 경우 기본 순서는 사전순입니다. 이 순서(예: 요일 또는 월)를 재정의해야 하는 경우 Power BI Desktop에서 다른 열을 기준으로 정렬하도록 지정할 수 있습니다. 자세한 내용은 [Power BI Desktop의 열 기준 정렬](desktop-sort-by-column.md)을 참조하세요.

### <a name="building-maps-more-easily-with-hints-to-bing"></a>Bing에 대한 힌트로 보다 쉽게 지도 만들기
Power BI는 Bing과 통합되어 기본 지도 좌표를 제공(지오코딩이라는 프로세스)하므로 지도를 쉽게 만들 수 있습니다.  Bing에서는 몇 가지 알고리즘과 힌트를 사용하여 올바른 위치를 가져오려고 하지만 이는 최상의 추측일 뿐입니다. 올바른 지오코딩의 가능성을 높이기 위해 다음과 같은 팁을 사용할 수 있습니다.

지도를 만들 때 일반적으로 국가, 주 및 도시를 그립니다.  Power BI Desktop에서 지리 지정 후 이름 열을 사용하면 Bing에서 사용자가 표시하려는 내용을 추측하는 데 도움이 됩니다. 예를 들어 "캘리포니아" 및 "워싱턴"과 같은 미국 주 이름 필드가 있는 경우 Bing은 "워싱턴"이라는 단어에 대해 워싱턴주 대신 워싱턴, DC의 위치를 반환할 수 있습니다.  열 "주"의 이름을 지정하면 지오코딩이 향상됩니다.  “국가” 및 “도시”라는 열에 대해서도 마찬가지입니다.   

여러 국가/지역의 컨텍스트에서 고려할 경우 일부 지정은 모호합니다.  일부 경우 한 국가/지역에서 '주'로 간주하는 내용이 '도' 또는 '카운티'나 다른 지정으로 처리됩니다.  여러 필드를 함께 추가하여 데이터 위치를 그리는 데 사용하는 열을 만들어 지오코딩의 정확도를 높일 수 있습니다.  "윌트셔"만 전달하는 대신 "윌트셔, 잉글랜드"를 전달하여 보다 정확한 지오코딩 결과를 얻는 경우를 예로 들 수 있습니다.

Power BI 서비스 또는 Desktop에서 항상 특정 위도 및 경도 위치를 제공할 수 있습니다.  이렇게 하는 경우 위치 필드도 전달해야 합니다. 그러지 않으면 기본적으로 데이터가 집계되므로 위도 및 경도 위치가 예상한 바와 일치하지 않을 수 있습니다.

### <a name="categorizing-geographic-fields-to-hint-bings-geocoding"></a>지리 필드를 분류하여 Bing의 지오코딩에 힌트 제공
필드를 올바르게 지오코딩하는 또 다른 방법은 데이터 필드에서 데이터 범주를 설정하는 것입니다.   Power BI Desktop에서 원하는 테이블을 선택하고 고급 리본으로 이동한 다음 데이터 범주를 주소, 도시, 대륙, 국가/지역, 국가, 우편 번호, 시/도로 설정합니다.  이러한 데이터 범주는 Bing에서 데이터를 올바르게 인코드하는 데 도움이 됩니다. 자세히 알아보려면 [Power BI Desktop의 데이터 분류](desktop-data-categorization.md)를 참조하세요.

### <a name="better-geocoding-with-more-specific-locations"></a>보다 구체적인 위치를 사용하여 지오코딩 향상
경우에 따라서는 매핑을 위한 데이터 범주 설정만으로는 부족할 수 있습니다.  Power BI Desktop의 쿼리 편집기를 사용하여 주소와 같은 보다 구체적인 위치를 만듭니다.  열 추가 기능을 사용하여 사용자 지정 열을 만듭니다.  그런 다음, 다음과 같이 원하는 위치를 만듭니다.

    = [Field1] & " " & [Field2]

그런 다음 지도 시각화에서 이 결과 필드를 사용합니다. 이 기능은 데이터 집합에 공통적인 배송지 주소 필드에서 주소를 만드는 데 매우 유용합니다.  한 가지 주의할 점은 연결은 텍스트 필드에만 작동한다는 사실입니다.  필요한 경우 주소를 만드는 데 번지를 사용하기 전에 번지를 텍스트 데이터 형식으로 변환합니다.

### <a name="histograms-in-the-query-stage"></a>쿼리 단계의 히스토그램
Power BI Desktop에서 히스토그램을 만드는 방법에는 여러 가지가 있지만 여기서는 가장 간단한 다음과 같은 방법으로 시작하겠습니다.

가장 간단한 히스토그램 - 히스토그램을 만들려는 필드가 포함된 쿼리를 결정합니다.  쿼리에 대한 "참조" 옵션을 사용하여 새 쿼리를 만들고 이름을 "FieldName Histogram"으로 지정합니다. "변환" 리본에서 "그룹화 기준" 옵션을 사용하고 "행 수" 집계를 선택합니다.  결과 집계 열의 데이터 형식이 숫자인지 확인합니다. 그런 다음 보고서 페이지에서 이 데이터를 시각화합니다.  이 방법은 만들기 쉽고 빠르지만 데이터 요소가 많고 시각적 개체 간에 브러시가 허용되지 않는 경우 잘 작동하지 않습니다.

버킷을 정의하여 히스토그램 만들기 - 히스토그램을 만들려는 필드가 포함된 쿼리를 결정합니다.  쿼리에 대한 "참조" 옵션을 사용하여 새 쿼리를 만들고 이름을 "FieldName"으로 지정합니다.  이제 규칙을 사용하여 버킷을 정의합니다.  열 추가 리본에서 사용자 지정 열 추가 옵션을 사용하여 사용자 지정 규칙을 만듭니다.  간단한 버킷팅 규칙은 다음과 같을 수 있습니다.

    if([FieldName] \< 2) then "\<2 min" else
    if([FieldName] \< 5) then "\<5 min" else
    if([FieldName] \< 10) then "\<10 min" else
    if([FieldName] \< 30) then "\<30 min" else
    "longer")

결과 집계 열의 데이터 형식이 숫자인지 확인합니다. 이제 가장 간단한 히스토그램에 설명된 그룹화 기준 기술을 사용하여 히스토그램을 만들 수 있습니다.  이 옵션은 더 많은 데이터 요소를 처리하지만 여전히 브러시에는 도움이 되지 않습니다.

브러시를 지원하는 히스토그램 정의 - 브러시는 사용자가 한 시각적 개체에서 데이터 요소를 선택하면 보고서 페이지의 다른 시각적 개체가 선택한 데이터 요소와 관련된 데이터 요소를 강조 표시하거나 필터링하도록 시각적 개체가 함께 연결되는 경우에 이루어집니다.  쿼리 시간에 데이터를 조작하므로 테이블 간의 관계를 만들고 히스토그램의 버킷과 관련되는 세부 항목을 알아야 하며 그 반대의 경우에도 마찬가지입니다.

히스토그램을 만들려는 필드가 포함된 쿼리에 대해 "참조" 옵션을 사용하여 프로세스를 시작합니다.  새 쿼리의 이름을 "Buckets"로 지정합니다.  이 예제에서는 원래 쿼리를 "Details"라고 부르겠습니다.  이제 히스토그램에 대한 버킷으로 사용할 열을 제외한 모든 열을 제거합니다.  이제 쿼리에서 "중복 제거" 기능을 사용합니다. 이 기능은 열을 선택한 경우의 오른쪽 클릭 메뉴에 있으므로 나머지 값은 열에서 고유 값입니다.   10진수를 사용하는 경우 먼저 버킷을 정의하여 히스토그램을 만드는 팁을 사용하여 관리 가능한 버킷 집합을 가져올 수 있습니다.  이제 쿼리 미리 보기에 표시된 데이터를 확인합니다.  빈 값이나 null이 표시되는 경우 관계를 만들기 전에 해당 데이터를 수정해야 합니다.  "데이터에 null 또는 빈 값이 있는 경우 관계 만들기"를 참조하세요.   이 방법을 사용할 경우 정렬해야 하므로 문제가 될 수 있습니다.  버킷을 제대로 정렬하려면 "정렬 순서: 원하는 순서로 범주 표시"를 참조하세요.  

>[!NOTE]
>모든 시각적 개체를 만들기 전에 정렬 순서에 대해 생각하는 것이 좋습니다.   

프로세스의 다음 단계는 버킷 열에 "Buckets" 쿼리와 "Details" 쿼리 간의 관계를 정의하는 것입니다.  Power BI Desktop의 리본에서 **관계 관리** 를 클릭합니다.  Buckets가 왼쪽 테이블에 있고 Details가 오른쪽 테이블에 있는 관계를 만들고 히스토그램에 사용할 필드를 선택합니다.

마지막 단계는 히스토그램을 만드는 것입니다.  "Buckets" 테이블에서 버킷 필드를 끕니다.  결과 세로 막대형 차트에서 기본 필드를 제거합니다.  이제 "Details" 테이블에서 같은 시각적 개체로 히스토그램 필드를 끕니다.  필드 집합에서 기본 집계를 개수로 변경합니다.  결과는 히스토그램입니다. Details 테이블에서 트리 맵과 같은 다른 시각적 개체를 만드는 경우 트리 맵에서 데이터 요소를 선택하여 히스토그램 강조 표시를 표시하고 전체 데이터 집합의 추세를 기준으로 선택한 데이터 요소에 대한 히스토그램을 표시합니다.

### <a name="histograms"></a>히스토그램
Power BI Desktop에서 계산 필드를 사용하여 히스토그램을 정의할 수 있습니다.  히스토그램을 만들 테이블 및 열을 식별합니다.  계산 영역에서 다음 수식을 입력합니다.

> Frequency:=COUNTROWS(\<Column Name\>)
>
>

변경 내용을 저장하고 보고서로 돌아갑니다.  테이블에 \<Column Name\> 및 Frequency를 추가한 다음 가로 막대형 차트로 변환합니다.  \<Column Name\>은 X축에 있고 계산 필드 Frequency는 Y축에 있는지 확인합니다.

### <a name="tips-and-tricks-for-creating-relationships-in-power-bi-desktop"></a>Power BI Desktop에서 관계를 만들기 위한 팁과 힌트
여러 원본에서 세부 데이터 집합을 로드하는 경우 종종 null 값, 빈 값 또는 중복 값과 같은 문제 때문에 관계를 만들지 못하게 됩니다.

예를 살펴보겠습니다.

활성 고객 지원 요청의 데이터 집합을 로드하고 다음과 같은 스키마가 포함된 작업 항목의 다른 데이터 집합을 로드합니다.

> CustomerInicdents: {IncidentID, CustomerName, IssueName, OpenedDate, Status} WorkItems: {WorkItemID, IncidentID, WorkItemName, OpenedDate, Status, CustomerName}
>
>

특정 CustomerName과 관련된 모든 인시던트 및 작업 항목을 추적하려고 하는 경우 이러한 두 데이터 집합 간의 관계를 간단히 만들 수 없습니다.  일부 작업 항목은 CustomerName과 관련되지 않을 수 있으므로 해당 필드가 비어 있거나 NULL이 됩니다.  지정된 CustomerName에 대한 WorkItems 및 CustomerIncidents에 레코드가 여러 개 있을 수 있습니다.  

#### <a name="creating-relationships-in-power-bi-desktop-when-the-data-has-null-or-blank-values"></a>데이터에 null 또는 빈 값이 있는 경우 Power BI Desktop에서 관계 만들기
종종 데이터 집합은 null 또는 빈 값이 있는 열을 포함합니다.  이로 인해 관계를 사용하려고 할 때 문제가 발생할 수 있습니다.  기본적으로 이 문제를 해결하는 두 가지 옵션이 있습니다.  null 또는 빈 값이 있는 행을 제거할 수 있습니다.  쿼리 탭의 필터 기능을 사용하여 이 작업을 수행하거나, 쿼리를 병합하는 경우 "keep only matching rows(일치하는 행만 유지)" 옵션을 선택할 수 있습니다. 또는 null 또는 빈 값을 관계에서 작동하는 값(일반적으로 "NULL" 및 "(비어 있음)"과 같은 문자열)으로 바꿀 수 있습니다.   여기서 올바른 방법은 없습니다. 쿼리 단계에서 행을 필터링하면 행이 제거되어 요약 통계 및 계산에 영향을 줄 수 있습니다.  후자의 방법을 사용할 경우 해당 데이터 행이 유지되지만 모델에서 관련 없는 행이 관련된 것으로 표시되어 계산이 잘못될 수 있습니다.  후자의 솔루션을 채택하는 경우 보기/차트에서 필터를 사용하여(해당하는 경우) 정확한 결과를 얻도록 합니다.  가장 중요한 것은 유지/제거되는 행을 평가하고 분석에 대한 전반적인 영향을 이해하는 것입니다.  

#### <a name="creating-relationships-in-power-bi-desktop-when-the-data-has-duplicate-values"></a>데이터에 중복 값이 있는 경우 Power BI Desktop에서 관계 만들기
여러 원본에서 세부 데이터 집합을 로드하는 경우 종종 중복 데이터값 때문에 관계를 만들지 못하게 됩니다.  두 데이터 집합의 고유 값으로 차원 테이블을 만들어 이 문제를 해결할 수 있습니다.

예를 살펴보겠습니다.

활성 고객 지원 요청의 데이터 집합을 로드하고 다음과 같은 스키마가 포함된 작업 항목의 다른 데이터 집합을 로드합니다.

> CustomerInicdents: {IncidentID, CustomerName, IssueName, OpenedDate, Status} WorkItems: {WorkItemID, IncidentID, WorkItemName, OpenedDate, Status, CustomerName}
>
>

특정 CustomerName과 관련된 모든 인시던트 및 작업 항목을 추적하려고 하는 경우 이러한 두 데이터 집합 간의 관계를 간단히 만들 수 없습니다.  일부 작업 항목은 CustomerName과 관련되지 않을 수 있으므로 해당 필드가 비어 있거나 NULL이 됩니다.  CustomerNames 테이블에 빈 값 또는 null이 있는 경우 여전히 관계를 만들지 못할 수 있습니다. 데이터에 null 또는 빈 값이 있는 경우 관계 만들기를 참조하세요.  단일 CustomerName에 대해 WorkItems 및 CustomerIncidents가 여러 개 있을 수 있습니다.  

이 경우 관계를 만들려면 두 데이터 집합의 모든 CustomerName의 논리 데이터 집합을 만들어야 합니다.  [쿼리] 탭에서 다음 시퀀스를 사용하여 논리 데이터 집합을 만들 수 있습니다.

1. 두 쿼리 모두에 대해 중복 항목을 만들어 첫 번째 항목은 이름을 **Temp** 로 지정하고 두 번째 항목은 이름을 **CustomerNames**로 지정합니다.
2. 각 쿼리에서 CustomerName 열을 *제외한* 모든 열을 제거합니다.
3. 각 쿼리에서  **중복 제거**를 사용합니다.
4. **CustomerNames** 쿼리의 리본에서 **추가** 옵션을 선택하고 쿼리 **Temp**를 선택합니다.
5. **CustomerNames** 쿼리에서 **중복 제거**를 선택합니다.

이제 CustomerIndicents와 WorkItems를 관련시키는 데 사용할 수 있는, 서로의 모든 값을 포함하는 차원 테이블이 만들어졌습니다.  

### <a name="patterns-to-jump-start-your-use-of-the-query-editor"></a>쿼리 편집기를 바로 사용할 수 있는 패턴
쿼리 편집기는 데이터를 조작하여 셰이핑하고 정리하여 시각화하거나 모델링할 수 있는 방법을 제공하는 매우 강력한 도구입니다. 알아야 할 몇 가지 패턴이 있습니다.

#### <a name="temporary-columns-can-be-deleted-after-computing-a-result"></a>결과 계산 후에는 임시 열을 삭제할 수 있습니다.
Power BI Desktop에서 종종 여러 열의 데이터를 하나의 새 열로 변환하는 계산을 만들어야 합니다.  이 작업은 복잡할 수 있습니다.  이 문제를 해결하는 한 가지 쉬운 방법은 작업을 단계로 분해하는 것입니다.  먼저 첫 열을 복제합니다. 그런 다음 임시 열 단계를 만듭니다. 그런 다음 최종 결과를 위한 열을 만듭니다.  그런 다음, 최종 데이터 집합이 복잡하게 보이지 않도록 임시 열을 삭제할 수 있습니다. 쿼리 탭에서 순서대로 단계를 실행하므로 이렇게 하는 것이 가능합니다.

#### <a name="duplicate-or-reference-queries-followed-by-merge-to-original-query"></a>쿼리를 복제하거나 참조한 후 원래 쿼리 병합
경우에 따라 데이터 집합에 대한 요약 통계를 계산하면 유용합니다.  이 작업을 쉽게 수행하려면 쿼리 탭에서 쿼리를 복제하거나 참조합니다. 그런 다음 **그룹화 기준** 을 사용하여 요약 통계를 계산합니다.  요약 통계는 비교하기 좋도록 원래 데이터에서 데이터를 정규화하는 데 도움이 됩니다.  요약 통계는 특히 개별 값을 전체적으로 비교하는 데 유용합니다.  이렇게 하려면 원래 쿼리로 이동해서 병합 옵션을 선택합니다.  그런 다음 적절한 식별자에서 일치하는 요약 통계 쿼리에서 데이터를 병합합니다.  이제 분석에 필요한 대로 데이터를 정규화할 준비가 되었습니다.

### <a name="using-dax-for-the-first-time"></a>처음으로 DAX 사용
DAX는 Power BI Desktop의 계산 수식 언어입니다.  DAX는 BI 분석에 최적화되어 있습니다.  쿼리 언어 같은 SQL만 사용한 경우 익숙한 내용과 약간 다릅니다. DAX를 학습하기 위한 문헌과 온라인에는 매우 좋은 리소스가 있습니다.

[Power BI Desktop의 DAX 기본 사항 학습](desktop-quickstart-learn-dax-basics.md)

[DAX(Data Analysis Expressions) 참조](https://msdn.microsoft.com/library/gg413422.aspx)

[DAX 리소스 센터](http://social.technet.microsoft.com/wiki/contents/articles/1088.dax-resource-center.aspx)

## <a name="power-bi-service-and-power-bi-desktop"></a>Power BI 서비스 ‘및’ Power BI Desktop

### <a name="read-the-whitepaper-principles-for-designing-power-bi-reportspower-bi-visualization-best-practicesmd"></a>백서 읽기: [Power BI 보고서 디자인 원칙](power-bi-visualization-best-practices.md)
이 문서는 Power BI에서 보고서를 디자인하는 모범 사례를 제공합니다. 계획 단계를 시작으로 보고서와 페이지 및 보고서를 구성하는 개별적인 시각적 개체에 적용할 수 있는 디자인 원칙을 설명합니다. 이러한 모범 사례의 대다수는 대시보드 디자인에도 적용됩니다.

### <a name="read-andor-watch-how-to-design-visually-stunning-reports-and-dashboards-in-power-bi"></a>"Power BI에서 시각적으로 멋진 보고서(및 대시보드)를 설계하는 방법"을 읽거나 봅니다.
커뮤니티 멤버인 Miguel Myers는 그래픽 디자이너일 뿐만 아니라 데이터 과학자입니다.

![](media/power-bi-reports-tips-and-tricks-for-creating/power-bi-reports.png)

* [블로그를 읽어보세요](https://powerbi.microsoft.com/blog/how-to-design-visually-stunning-reports/)
* [웹 세미나를 시청하세요](https://info.microsoft.com/CO-PowerBI-WBNR-FY16-04Apr-19-Design-Reports-in-PowerBI-Registration.html)

### <a name="consider-your-audience"></a>대상 그룹을 고려
의사 결정에 도움이 될 주요 메트릭은 무엇인가요? 보고서가 어떻게 사용될까요? 어떤 학습 내용 또는 문화적 가정이 디자인 선택에 영향을 줄 수 있을까요? 성공을 위해 대상 그룹은 어떤 정보를 필요로 할까요?

보고서가 어디에 표시될 예정인가요? 큰 모니터에 표시될 예정이라면 대시보드에 더 많은 콘텐츠를 넣을 수 있습니다. 태블릿에 보고서를 표시하는 경우에는 시각화 수가 적을수록 읽기 편합니다.

### <a name="tell-a-story-and-keep-it-to-one-screen"></a>스토리를 말하고 한 화면으로 유지
각 보고서 페이지에서 스토리를 한눈에 알 수 있어야 합니다. 페이지에 스크롤 막대를 사용하지 않을 수 있나요? 보고서가 너무 복잡하거나 너무 혼란스러울까요?  필수 정보를 쉽게 읽고 해석할 수 있도록 군더더기 제거

### <a name="make-the-most-important-information-biggest"></a>가장 중요한 정보를 가장 비중있게
보고서 페이지의 시각화와 텍스트의 크기가 모두 동일하면 대상 독자가 가장 중요한 사항에 집중하기 어려워집니다. 예를 들어, 카드 시각화의 경우 중요한 번호를 눈에 띄게 표시하는 좋은 방법입니다.  
![카드 시각화](media/service-dashboards-design-tips/pbi_card.png)

### <a name="but-be-sure-to-provide-context"></a>문맥 정보 제공  

텍스트 상자 및 도구 설명과 같은 기능을 사용하여 시각화에 컨텍스트를 추가합니다.

### <a name="put-the-most-important-information-in-the-upper-corner"></a>가장 중요한 정보를 상단 모서리에 놓기
대부분의 사람들이 위쪽에서 아래쪽으로 읽는 경향이 있으므로 가장 높은 수준의 세부 정보를 맨 위에 배치하고 대상 그룹이 읽어가는 방향(왼쪽-오른쪽, 오른쪽-왼쪽)으로 보다 자세한 정보를 표시합니다.

### <a name="use-the-right-visualization-for-the-data-and-format-it-for-easy-reading"></a>데이터에 적합한 시각화 사용 및 읽기 쉽게 서식 지정
다양성을 위해 여러 시각화를 사용하는 것을 피하세요.  시각화는 그림을 그리는 것이며 "읽고" 해석하기 쉬워야 합니다.  일부 데이터 및 시각화에서는 간단한 그래픽 시각화로도 충분합니다. 보다 복잡한 시각화를 호출할 수 있는 기타 데이터도 있지만 타일 및 레이블, 기타 사용자 지정 항목의 활용이 독자에게 도움이 되도록 해야 합니다.  

* 3차원 차트, 0으로 시작하지 않는 차트처럼 현실을 왜곡하는 차트를 사용할 때는 주의하세요. 인간의 뇌는 원형 모양을 해석하기 더 어렵다는 점을 유념하세요. 원형 차트, 도넛형 차트, 계기 및 기타 원형 차트 종류는 모양은 좋지만 대신 사용할 수 있는 다른 시각적 개체가 있을까요?    
* 차트 내에 있는 축의 차트 눈금, 차트 차원 순서 및 차원 값에 사용된 색이 일관되도록 하세요.    
* 정량 데이터를 적절하게 인코딩하세요. 숫자를 표시할 때는 서너 개의 숫자를 초과하지 마세요. 소수점 왼쪽 및 수백 또는 수백만 자릿수를 한두 숫자로 표시하세요(예: 3,400,000가 아닌 3.4백만).    
* 정밀도와 시간 수준을 섞어 쓰지 마세요. 시간 프레임을 잘 이해하고 있어야 합니다.  해당 연도의 특정 월에서 필터링된 차트 옆에 지난 달에 대한 하나의 차트를 포함하지 마세요.    
* 또한 동일한 눈금에 큰 측정값과 작은 측정값을 함께 사용하지 마세요(예: 꺾은선형 차트 또는 가로 막대형 차트).  예를 들어 백만 단위인 측정값과 천 단위인 측정값이 있을 수 있습니다.  이러한 큰 단위에서는 천 단위인 측정값의 차이를 파악하기 어렵습니다.  함께 사용해야 하는 경우 보조 축의 사용을 허용하는 콤보 차트 같은 시각화를 선택합니다.    
* 불필요한 데이터 레이블로 차트를 복잡하게 하지 마세요. 가로 막대형 차트의 값은 ***충분히 클 경우*** 일반적으로 실제 숫자를 표시하지 않아도 잘 이해됩니다.   
* [차트가 정렬](power-bi-report-change-sort.md)되는 방식에 주의하세요.  최상위 또는 최하위 숫자에 주목하도록 하려면 측정값을 기준으로 정렬합니다.  사람들이 여러 다른 범주 내에서 특정 범주를 신속하게 찾을 수 있도록 하려면 축을 기준으로 정렬합니다.  
* 원형 차트는 범주가 8개 미만일 경우 적합합니다. 값을 나란히 비교할 수 없으므로 원형 차트는 가로 막대형 및 세로 막대형 차트보다 값을 비교하기가 더 어렵습니다. 원형 차트는 부분을 비교하기보다는 부분에서 전체로의 관계를 파악하는 데 유용할 수 있습니다. 계기 차트는 목표의 컨텍스트에서 현재 상태를 표시하는 데 적합합니다.    

시각화 관련 지침에 대한 자세한 내용은 [Power BI에서 시각화 유형](power-bi-visualization-types-for-reports-and-q-and-a.md)을 참조하세요.  

### <a name="learn-more-about-best-practice-dashboard-design"></a>모범 사례 대시보드 디자인에 대한 자세한 정보
다음은 몇 가지 유용한 설명서입니다.

* *Storytelling with Data*. Cole Nussbaumer Knafic
* *Data points*. Nathan Yau
* *The truthful Art*. Alberto Cairo
* *Now You See It* by Stephen Few  
* *Envisioning Information* by Edward Tufte  
* *Advanced Presentations Design*. Andrew Abela   

## <a name="next-steps"></a>다음 단계
[Power BI - 기본 개념](service-basic-concepts.md)

[Power BI의 보고서](service-reports.md)

궁금한 점이 더 있나요? [Power BI 커뮤니티를 이용하세요.](http://community.powerbi.com/)
