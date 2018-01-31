---
title: "Power BI의 SAP HANA용 DirectQuery"
description: "SAP HANA에 DirectQuery를 사용하는 경우 고려 사항"
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/24/2018
ms.author: davidi
ms.openlocfilehash: 2b2e59371c96928a2b7c6b23bd393a80ecc3041a
ms.sourcegitcommit: 7249ff35c73adc2d25f2e12bc0147afa1f31c232
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2018
---
# <a name="directquery-and-sap-hana"></a>DirectQuery 및 SAP HANA
**DirectQuery**를 사용하여 **SAP HANA** 데이터 원본에 직접 연결할 수 있습니다.

**SAP HANA**를 사용할 때는 다음을 보장하기 위해 연결이 처리되는 방식에 대한 몇 가지 측면을 이해하는 것이 중요합니다.

* SAP HANA 뷰에 비가산적 측정값(예: 단순한 합계가 아닌 고유 카운트, 평균)이 포함된 경우 결과가 예상대로 나와야 합니다.
* 결과 쿼리가 효율적이어야 합니다.

**데이터 가져오기** 또는 **쿼리 편집기**에 정의된 쿼리에서 집계를 수행할 때는 잠시 시간을 내어 **SQL Server**와 같은 관계형 원본의 동작을 명확히 하고 시작하는 것이 좋습니다. 다음에 나오는 예에서 **쿼리 편집기**에 정의된 쿼리는 **ProductID**별 평균 가격을 반환합니다.

![](media/desktop-directquery-sap-hana/directquery-sap-hana_01.png)

데이터를 Power BI(및 DirectQuery 사용)로 가져오는 경우 결과는 다음과 같습니다.

* **쿼리 편집기**에서 작성한 쿼리에 정의된 집계 수준에서 데이터를 가져옵니다. 예를 들어, 제품별 평균 가격입니다. 그 결과, 시각적 개체에 사용할 수 있는 *ProductID* 및 *AveragePrice*라는 두 열이 있는 테이블이 생성됩니다.
* 시각적 개체에서 모든 후속 집계(예: *Sum*, *평균*, *Average* 등)는 가져온 데이터에 대해 수행됩니다.  예를 들어, 시각적 개체에 *AveragePrice*를 포함하면 기본적으로 *Sum* 집계를 사용하고 각 *ProductID*에 대한 *AveragePrice* 합계를 반환합니다(이 경우 13.67). 시각적 개체에 사용된 다른 대체 집계 함수(예: *Min*, *Average* 등)도 마찬가지입니다. 예를 들어, *AveragePrice*의 *Average*는 6.66, 4, 3의 평균(4.56)을 반환하며 기본 테이블에 있는 6개 레코드에서 *Price*의 평균(5.17)이 *아닙니다*.

가져오기 대신 **DirectQuery**를 사용하면 동일한 의미 체계가 적용되고 결과는 정확히 동일합니다.

* 동일한 쿼리가 제공되면, 데이터를 실제로 가져오지 않더라도 논리적으로 정확히 동일한 데이터가 보고 계층에 표시됩니다.
* 시각적 개체에서 모든 후속 집계(*Sum*, *평균*, *Average* 등)는 쿼리에서 해당 논리 테이블을 통해 다시 수행됩니다. 마찬가지로 *AveragePrice*의 *Average*를 포함하는 시각적 개체는 동일한 4.56을 반환합니다.

이제 **SAP HANA**를 살펴보겠습니다. Power BI는 SAP HANA에서, 둘 다 측정값을 포함할 수 있는 *분석 뷰* 및 *계산 뷰* 모두로 작동할 수 있습니다. 그러나 현재 SAP HANA에 대한 접근 방식은 이전에 설명한 것과 동일한 원칙을 따릅니다. **데이터 가져오기** 또는 **쿼리 편집기**에 정의된 쿼리에 따라 사용 가능한 데이터가 결정되고 시각적 개체의 모든 후속 집계가 데이터에 대해 수행되며 가져오기 및 DirectQuery 모두에 동일하게 적용됩니다.

그러나 HANA의 특성에 따라, 초기 **데이터 가져오기** 대화 상자 또는 **쿼리 편집기**에 정의된 쿼리는 항상 집계 쿼리이며, 일반적으로 사용되는 실제 집계가 HANA 뷰로 정의된 측정값을 포함합니다.

위의 SQL Server 예제와 동등한 것으로, **ID**, **ProductID**, **DepotID**를 포함하고, 뷰에서 **Average of Price**로 정의된 **AveragePrice**가 있는 측정값을 포함하는 HANA 보기가 있습니다.

![](media/desktop-directquery-sap-hana/directquery-sap-hana_02.png)

**데이터 가져오기** 환경에서 **ProductID** 및 **AveragePrice** 측정값을 선택했다면, 뷰에 대해 쿼리를 정의하고 데이터 집계를 요청한 것입니다(위의 예제에서는, 간단한 설명을 위해 실제 HANA SQL 구문과 일치하지 않는 의사(pseudo) SQL을 사용). 그런 다음 시각적 개체에 정의된 추가 집계는 이러한 쿼리의 결과를 추가로 집계합니다. 다시, **SQL Server**에 대해 위에서 설명한 것처럼, 이 내용은 가져오기 및 DirectQuery 경우 모두에 적용됩니다. DirectQuery의 경우 **데이터 가져오기** 또는 **쿼리 편집기**의 쿼리가 HANA로 전송되는 하위 SELECT에 사용되므로 실제로 추가 집계하기 전에 모든 데이터를 읽을 수 있는 것은 아닙니다.

따라서 HANA를 통해 DirectQuery를 사용하는 경우 다음과 같은 중요 고려 사항이 있습니다.

* HANA의 측정값이 비가산적(예: 단순한 *Sum*, *Min*, *Max*가 아님)일 때는 항상 시각적 개체에서 수행되는 추가 집계에 주의를 기울여야 합니다.
* **데이터 가져오기** 또는 **쿼리 편집기**에서는, 결과가 HANA로 보낼 수 있는 적절한 쿼리여야 한다는 사실을 유념하여 필요한 데이터를 검색하는 데 필요한 열만 포함해야 합니다. 예를 들어 수십 개의 열을 선택했고, 이후 시각적 개체에 이 열이 필요할 것으로 생각되면, DirectQuery의 간단한 시각적 개체라고 하더라도 하위 SELECT에 사용된 집계 쿼리가 수십 개의 열을 포함한다는 것을 의미하며 이것은 일반적으로 성능 저하를 나타냅니다.

예를 살펴보겠습니다. 다음 예제에서는 **데이터 가져오기** 대화 상자에서 5개의 열(CalendarQuarter, Color, LastName, ProductLine, SalesOrderNumber)과 OrderQuantity 측정값을 선택하면, 나중에 Min OrderQuantity가 포함된 간단한 시각적 개체가 생성되고 그 결과 HANA에 다음 SQL 쿼리가 발생합니다. 음영 처리된 부분은 하위 SELECT로, **데이터 가져오기** / **쿼리 편집기**의 쿼리를 포함합니다. 이 하위 SELECT가 매우 높은 카디널리티 결과를 제공하면 결과 HANA 성능이 저하될 가능성이 높습니다.

![](media/desktop-directquery-sap-hana/directquery-sap-hana_03.png)

따라서 **데이터 가져오기** 또는 **쿼리 편집기**에서 선택한 항목은 HANA에 적당한 쿼리이면서 필요한 항목으로 제한해야 합니다.

### <a name="next-steps"></a>다음 단계
DirectQuery에 대한 자세한 내용은 다음 리소스를 참조하세요.

* [Power BI의 DirectQuery](desktop-directquery-about.md)
* [DirectQuery에서 지원하는 데이터 원본](desktop-directquery-data-sources.md)
* [DirectQuery 및 SAP BW](desktop-directquery-sap-bw.md)
* [온-프레미스 데이터 게이트웨이](service-gateway-onprem.md)

