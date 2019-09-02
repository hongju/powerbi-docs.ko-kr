---
title: Power BI Desktop의 다 대 다 관계
description: Power BI Desktop에서 다 대 다 카디널리티와의 관계 사용
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 02/13/2019
ms.author: davidi
LocalizationGroup: Transform and shape data
ms.openlocfilehash: 97718ee6411d0063aa145e768fd20d3ebb6024b6
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "65941442"
---
# <a name="relationships-with-a-many-many-cardinality-in-power-bi-desktop"></a>Power BI Desktop에서 다 대 다 카디널리티와의 관계

Power BI Desktop의 *다 대 다 카디널리티와의 관계*를 사용하면 *다 대 다*의 카디널리티를 사용하는 테이블을 조인할 수 있습니다. 두 개 이상의 데이터 원본이 포함된 데이터 모델을 더 쉽고 직관적으로 만들 수 있습니다. *다 대 다 카디널리티와의 관계* 기능은 Power BI Desktop의 더 큰 *복합 모델* 기능의 일부입니다.

![“관계 편집” 창의 다 대 다 관계](media/desktop-many-to-many-relationships/many-to-many-relationships_01.png)

Power BI Desktop의 *다 대 다 카디널리티와의 관계* 기능은 다음 세 가지 관련 기능 중 하나입니다.

* **복합 모델**: 보고서에 DirectQuery 연결 또는 가져오기를 비롯한 두 개 이상의 데이터 연결을 다양한 조합으로 포함할 수 있습니다. 자세한 내용은 [Power BI Desktop의 복합 모델](desktop-composite-models.md)을 참조하세요.

* **다 대 다 카디널리티와의 관계**: *복합 모델*을 사용하면 테이블 간에 *다 대 다 카디널리티와의 관계*를 설정할 수 있습니다. 이 방법은 테이블의 고유한 값에 대한 요구 사항을 제거합니다. 또한 관계 설정 목적으로만 새 테이블을 도입하는 것과 같은 이전 해결 방법을 제거합니다. 이 기능은 이 문서에서 더 자세히 설명합니다.

* **스토리지 모드**: 이제 백 엔드 데이터 원본에 대한 쿼리가 필요한 시각적 개체를 지정할 수 있습니다. 쿼리가 필요 없는 시각적 개체는 DirectQuery를 기반으로 하는 경우에도 가져옵니다. 이 기능은 성능을 개선하고 백 엔드 로드를 줄이는 데 도움이 됩니다. 이전에는 슬라이서와 같은 간단한 시각적 개체도 백 엔드 원본으로 전송되는 쿼리를 시작했습니다. 자세한 내용은 [Power BI Desktop의 스토리지 모드(미리 보기)](desktop-storage-mode.md)를 참조하세요.

## <a name="what-relationships-with-a-many-many-cardinality-solves"></a>*다 대 다 카디널리티와의 관계* 문제 해결

*다 대 다 카디널리티와의 관계* 기능을 사용할 수 있게 되기 전에 두 테이블 간의 관계가 Power BI에 정의되었습니다. 관계에 포함된 테이블 열 중 하나 이상에 고유한 값이 포함되어야 합니다. 그러나 열에 고유한 값이 포함되지 않는 경우도 있습니다. 

예를 들어 두 개의 테이블에 *Country* 열이 있을 수 있지만, 양 테이블에서 *Country* 값이 고유하지 않습니다. 이러한 두 테이블을 조인하려면 별도의 해결 방법을 만들어야 합니다. 한 가지 해결 방법은 필요한 고유한 값이 포함된 추가 테이블을 만들어서 모델에 추가하는 것일 수 있습니다. *다 대 다 카디널리티와의 관계* 기능을 사용하면 **다 대 다**의 카디널리티의 관계를 사용하여 해당 테이블을 직접 조인할 수 있습니다.  

## <a name="use-relationships-with-a-many-many-cardinality"></a>*다 대 다 카디널리티와의 관계* 사용

Power BI에서 두 테이블 간 관계를 정의할 때 관계의 카디널리티를 정의해야 합니다. 예를 들어 *ProductSales*와 *Product* 간 관계(*ProductSales[ProductCode]* 및 *Product[ProductCode]* 열 사용)는 ‘다 대 일’로 정의됩니다.  각 제품에 많은 판매 정보가 있고 *Product* 테이블의 열(*ProductCode*)이 고유하므로 이 방식으로 관계를 정의합니다. 관계 카디널리티를 ‘다 대 일’, ‘일 대 다’ 또는 ‘일 대 일’로 정의하는 경우 Power BI가 유효성을 검사하여 사용자가 선택한 카디널리티가 실제 데이터와 일치하는지 확인하는 데 도움이 됩니다.   

예를 들어 다음 이미지에서 간단한 모델을 살펴보겠습니다.

![관계 보기](media/desktop-many-to-many-relationships/many-to-many-relationships_02.png)

이제 *Product* 테이블에 다음과 같이 두 개의 행만 표시된다고 가정해 보겠습니다.

![두 개의 행이 있는 Product 테이블 시각적 개체](media/desktop-many-to-many-relationships/many-to-many-relationships_03.png)

또한 *Sales* 테이블에는 C 제품 행을 포함하여 4개의 행만 있다고 가정해 보겠습니다. 참조 무결성 오류로 인해 C 제품은 *Product* 테이블에 없습니다.

![4개의 행이 있는 Sales 테이블 시각적 개체](media/desktop-many-to-many-relationships/many-to-many-relationships_04.png)

*ProductName* 및 *Price*(*Product* 테이블에 포함됨)는 각 제품의 총 *Qty*(*ProductSales* 테이블에 포함됨)와 함께 다음과 같이 표시됩니다. 

![제품 이름, 가격 및 수량을 표시하는 시각적 개체](media/desktop-many-to-many-relationships/many-to-many-relationships_05.png)

이전 이미지에서 볼 수 있듯이 C 제품의 판매와 연결된 빈 *ProductName* 행이 있습니다. 이 빈 행은 다음에 해당합니다.

* *Product* 테이블에 해당 행이 없는 *ProductSales* 테이블의 모든 행. 이 예제의 *C* 제품에서 확인한 참조 무결성 문제가 있습니다.

* 외래 키 열이 Null인 *ProductSales* 테이블의 모든 행. 

이러한 이유로 인해 두 경우에 모두 빈 행은 *ProductName* 및 *Price*를 알 수 없는 판매에 해당합니다.

그러나 테이블의 두 열이 모두 고유하지 않지만 두 개의 열에 의해 조인되는 경우가 있습니다. 예를 들어 다음 두 테이블을 살펴봅니다.

* *Sales* 테이블에는 ‘주’별 판매 데이터가 표시되고 각 행에는 해당 의 판매 유형에 대한 판매 금액이 포함됩니다.  주에는 CA, WA 및 TX가 포함됩니다. 

    ![주별 판매를 표시하는 Sales 테이블](media/desktop-many-to-many-relationships/many-to-many-relationships_06.png)

* *CityData* 테이블에는 인구 및 주(CA, WA 주 및 New York 포함)를 비롯한 도시 관련 데이터가 표시됩니다.

    ![도시, 주 및 인구를 표시하는 Sales 테이블](media/desktop-many-to-many-relationships/many-to-many-relationships_07.png)

두 테이블에 모두 *State* 열이 있고 주별 총판매액 및 각 주의 총인구를 둘 다 보고하고 싶은 경우에, *State* 열이 두 테이블에서 모두 고유하지 않다는 문제가 있습니다. 

## <a name="the-previous-workaround"></a>이전 해결 방법

2018년 7월 릴리스 이전의 Power BI Desktop 버전에서는 사용자가 이러한 테이블 간에 직접 관계를 만들 수 없었습니다. 일반적인 해결 방법은 다음을 수행하는 것입니다.

* 고유한 ‘주’ ID만 포함하는 세 번째 테이블을 만듭니다.  테이블은 다음 중 일부 또는 전부에 해당할 수 있습니다.
  * 계산된 테이블(DAX[Data Analysis Expressions]를 사용하여 정의됨).
  * 테이블 중 하나에서 가져온 고유 ID를 표시할 수 있는, 쿼리 편집기에서 정의된 쿼리를 기반으로 하는 테이블.
  * 결합된 전체 집합.

* 일반 ‘다 대 일’ 관계를 사용하여 두 개의 원본 테이블을 새 테이블과 연결합니다. 

해결 방법 테이블을 계속 표시하거나 **필드** 목록에 표시되지 않도록 숨길 수 있습니다. 테이블을 숨기면 ‘다 대 일’ 관계는 일반적으로 양방향으로 필터링하도록 설정되고 한쪽 테이블의 *State* 필드를 사용할 수 있습니다.  이후 교차 필터링이 다른 테이블에 전달됩니다. 이 방법은 다음 이미지에 표시됩니다.

![관계 보기](media/desktop-many-to-many-relationships/many-to-many-relationships_08.png)

*State*(*CityData* 테이블에 포함됨)를 총 ‘인구’ 및 총 ‘판매액’과 함께 표시하는 시각적 개체는 다음과 같이 표시됩니다.  

![테이블 시각적 개체](media/desktop-many-to-many-relationships/many-to-many-relationships_09.png)

> [!NOTE]
> 이 해결 방법에서는 *CityData* 테이블의 주가 사용되어 해당 테이블에 있는 해당 주만 나열되므로 TX가 제외됩니다. 또한 ‘다 대 일’ 관계와 달리 합계 행에는 모든 ‘판매액’(TX의 판매액 포함)이 포함되지만, 세부 정보에는 일치하지 않는 행을 포함하는 빈 행이 포함되지 않습니다.   마찬가지로 *State* 값이 Null인 ‘판매액’을 포함하는 빈 행이 없습니다. 

해당 시각적 개체에 ‘도시’도 포함하는 경우, ‘도시’별 인구가 알려지지만 ‘도시’에 대해 표시된 ‘판매액’은 단순히 해당 ‘주’의 ‘판매액’을 반복합니다.       일반적으로 이것은 다음 이미지와 같이 열의 그룹화가 일부 집계 측정값과 관련이 없는 경우입니다.

![테이블 시각적 개체](media/desktop-many-to-many-relationships/many-to-many-relationships_10.png)

이 해결 방법에서 모든 ‘주’의 조합으로 새 *Sales* 테이블을 정의하고 테이블을 **필드** 목록에 표시하도록 설정하면 다음 이미지와 같이 동일한 시각적 개체가 ‘주’(새 테이블에 포함됨)와 총 ‘인구’ 및 총 ‘판매액’을 표시합니다.    

![테이블 시각적 개체](media/desktop-many-to-many-relationships/many-to-many-relationships_11.png)

확인할 수 있듯이, *TX*(‘판매액’ 데이터와 알 수 없는 ‘인구’ 데이터 포함) 및 *New York*(알려진 ‘인구’ 데이터가 포함되지만 ‘판매액’ 데이터가 없음)이 포함됩니다.     이 해결 방법은 최적의 방법이 아니고 많은 문제가 있습니다. 다 대 다 카디널리티와의 관계를 만들면 다음 섹션에 설명된 대로 결과 문제가 해결됩니다.

## <a name="use-relationships-with-a-many-many-cardinality-instead-of-the-workaround"></a>이전 해결 방법 대신 *다 대 다 카디널리티와의 관계* 사용

Power BI Desktop의 2018년 7월 버전을 기준으로, 비슷한 해결 방법을 사용하지 않고도 앞에서 설명한 테이블과 같은 테이블을 직접 연결할 수 있습니다. 이제 관계 카디널리티를 ‘다 대 다’로 설정할 수 있습니다.  이 설정은 테이블에 고유 값이 포함되지 않음을 나타냅니다. 이 관계의 경우 다른 테이블을 필터링하는 기준 테이블을 제어하거나 각 테이블이 다른 테이블을 필터링하는 양방향 필터링을 적용할 수 있습니다.  

Power BI Desktop에서는 관계에서 열의 고유한 값이 모든 테이블에 포함되지 않는 것으로 확인될 경우 카디널리티가 기본적으로 ‘다 대 다’로 설정됩니다.  이 경우 관계 설정은 의도한 동작이며 데이터 문제의 의도하지 않은 결과가 아닌지 확인하는 경고가 표시됩니다. 

예를 들어 *CityData* 및 *Sales* 간에 직접 관계를 만드는 경우(여기서 필터는 *CityData*에서 *Sales*로 진행되어야 함) Power BI Desktop은 다음 이미지와 같이 **관계 편집** 창을 표시합니다.

![“관계 편집” 창](media/desktop-many-to-many-relationships/many-to-many-relationships_01.png)

결과 **관계** 보기에는 두 테이블 간 직접적인 다 대 다 관계가 표시됩니다. 테이블의 **필드** 목록 모양 및 시각적 개체가 만들어질 때 수행되는 후속 동작은 해결 방법을 적용했을 때와 유사합니다. 해결 방법에서 고유 ‘주’ 데이터를 표시하는 추가 테이블은 표시되지 않습니다.  예를 들어 이전 섹션에서 설명한 대로 ‘주’, ‘인구’ 및 ‘판매액’ 데이터를 표시하는 시각적 개체는 다음과 같이 표시됩니다.   

![테이블 시각적 개체](media/desktop-many-to-many-relationships/many-to-many-relationships_12.png)

*다 대 다 카디널리티와의 관계*와 더 일반적인 *다 대 일* 관계의 주요 차이점은 다음과 같습니다.

* 표시된 값은 다른 테이블의 일치하지 않는 행에 해당하는 빈 행을 포함하지 않습니다. 이러한 값은 다른 테이블의 관계에 사용된 열이 Null인 행에 해당하지도 않습니다.
* 둘 이상의 행이 관련될 수 있으므로 `RELATED()` 함수를 사용할 수 없습니다.
* 테이블에서 `ALL()` 함수를 사용해도 다 대 다 관계에 의해 관련된 다른 테이블에 적용된 필터가 제거되지 않습니다. 앞의 예제에서 다음 스크립트에 표시된 대로 정의된 측정값은 관련 *CityData* 테이블에 있는 열의 필터는 제거하지 않습니다.

    ![스크립트 예제](media/desktop-many-to-many-relationships/many-to-many-relationships_13.png)

    ‘주’, ‘판매액’ 및 ‘판매액 합계’ 데이터를 표시하는 시각적 개체는 다음과 같습니다.   

    ![테이블 시각적 개체](media/desktop-many-to-many-relationships/many-to-many-relationships_14.png)

앞의 차이점을 고려하여 `ALL(\<Table>)`을 사용한 계산(예: ‘총계의 %’)이 의도한 결과를 반환하는지 확인합니다.  


## <a name="limitations-and-considerations"></a>제한 사항 및 고려 사항

*다 대 다 카디널리티 관계* 및 복합 모델의 이 릴리스에 대한 몇 가지 제한 사항이 있습니다.

다음 Live Connect(다차원) 원본은 복합 모델과 함께 사용할 수 없습니다.

* SAP HANA
* SAP Business Warehouse
* SQL Server Analysis Services
* Power BI 데이터 세트
* Azure Analysis Services

DirectQuery를 사용하여 이러한 다차원 원본에 연결하는 경우 다른 DirectQuery 원본에 연결하거나 가져온 데이터와 결합할 수 없습니다.

*다 대 다 카디널리티 관계*를 사용할 경우에도 DirectQuery 사용에 대한 기존 제한 사항이 계속 적용됩니다. 이러한 제한 사항 중 대부분은 테이블의 스토리지 모드에 따라 테이블별로 적용됩니다. 예를 들어 가져온 테이블에서 계산된 열은 다른 테이블을 참조할 수 있지만, DirectQuery 테이블에서 계산된 열은 여전히 동일한 테이블의 열만 참조할 수 있습니다. 다른 제한 사항은 모델 내의 테이블이 DirectQuery인 경우 모델에 전체적으로 적용되는 것입니다. 예를 들어 QuickInsights 및 Q&A 기능은 모델 내의 테이블에 DirectQuery의 스토리지 모드가 있는 경우 해당 모델에서 사용할 수 없습니다. 

## <a name="next-steps"></a>다음 단계

복합 모델 및 DirectQuery에 대한 자세한 내용은 다음 문서를 참조하세요.
* [Power BI Desktop의 복합 모델](desktop-composite-models.md)
* [Power BI Desktop의 스토리지 모드(미리 보기)](desktop-storage-mode.md)
* [Power BI Desktop에서 DirectQuery 사용](desktop-directquery-about.md)
* [Power BI Desktop의 DirectQuery에서 지원하는 데이터 원본](desktop-directquery-data-sources.md)
