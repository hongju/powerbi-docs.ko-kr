---
title: Power BI Desktop의 복합 모델 사용
description: Power BI Desktop에서 여러 데이터 연결 및 다 대 다 관계를 사용하여 데이터 모델 만들기
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/15/2020
ms.author: davidi
LocalizationGroup: Transform and shape data
ms.openlocfilehash: 45f7ecee11cd57a73ed0e998dad26935b560c8ad
ms.sourcegitcommit: 3d6b27e3936e451339d8c11e9af1a72c725a5668
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2020
ms.locfileid: "76161238"
---
# <a name="use-composite-models-in-power-bi-desktop"></a>Power BI Desktop의 복합 모델 사용

이전에는 Power BI Desktop에서 DirectQuery를 보고서에 사용할 때 해당 보고서에 대해 DirectQuery 또는 가져오기 등 다른 데이터 연결이 허용되지 않았습니다. 복합 모델을 사용하면 해당 제한이 제거됩니다. 둘 이상의 DirectQuery 또는 가져오기 데이터 연결의 데이터 연결을 보고서에 원하는 조합으로 원활하게 포함할 수 있습니다.

Power BI Desktop의 복합 모델 기능은 다음 세 가지 관련 기능으로 구성됩니다.

* **복합 모델**: 보고서에 DirectQuery 연결 또는 가져오기를 비롯한 여러 데이터 연결을 다양한 조합으로 포함할 수 있습니다. 이 문서에서는 복합 모델에 대해 자세히 설명합니다.

* **다 대 다 관계**: 복합 모델을 사용하면 테이블 간에 *다 대 다 관계*를 설정할 수 있습니다. 이 방법은 테이블의 고유한 값에 대한 요구 사항을 제거합니다. 또한 관계 설정 목적으로만 새 테이블을 도입하는 것과 같은 이전 해결 방법을 제거합니다. 자세한 내용은 [Power BI Desktop의 다 대 다 관계 적용](desktop-many-to-many-relationships.md)을 참조하세요.

* **스토리지 모드**: 이제 백 엔드 데이터 원본을 쿼리하는 시각적 개체를 지정할 수 있습니다. 쿼리가 필요 없는 시각적 개체는 DirectQuery를 기반으로 하는 경우에도 가져옵니다. 이 기능은 성능을 개선하고 백 엔드 로드를 줄이는 데 도움이 됩니다. 이전에는 슬라이서와 같은 간단한 시각적 개체도 백 엔드 원본에 대한 쿼리를 시작했습니다. 자세한 내용은 [Power BI Desktop의 스토리지 모드 관리](desktop-storage-mode.md)를 참조하세요.

## <a name="use-composite-models"></a>복합 모델 사용

복합 모델을 사용하면 Power BI Desktop 또는 Power BI 서비스를 사용할 때 다양한 종류의 데이터 원본에 연결할 수 있습니다. 다음과 같은 몇 가지 방법으로 이러한 데이터 연결을 만들 수 있습니다.

* 데이터를 가져오는 가장 일반적인 방법인 Power BI로 데이터를 가져옵니다.
* DirectQuery를 사용하여 원래의 원본 리포지토리에 있는 데이터에 직접 연결합니다. DirectQuery에 대한 자세한 정보는 [Power BI의 DirectQuery 사용](desktop-directquery-about.md)을 참조하세요.

DirectQuery를 사용하는 경우 복합 모델에서는 다음 중 하나 또는 둘 다를 수행하는 Power BI 모델(예: 단일 *.pbix* Power BI Desktop 파일)을 만들 수 있습니다.

* 하나 이상의 DirectQuery 원본의 데이터를 결합합니다.
* DirectQuery 원본의 데이터와 가져오기 데이터를 결합합니다.

예를 들어, 복합 모델을 사용하면 다음과 같은 유형의 데이터를 결합하는 모델을 빌드할 수 있습니다.

* 엔터프라이즈 데이터 웨어하우스의 판매 데이터.
* 부서별 SQL Server 데이터베이스의 판매 대상 데이터.
* 스프레드시트에서 가져온 데이터입니다.

둘 이상의 DirectQuery 원본의 데이터를 결합하거나 DirectQuery와 가져오기 데이터를 결합하는 모델을 복합 모델이라고 합니다.

서로 다른 원본에서 테이블을 가져온 경우에도 평소와 같이 테이블 간에 관계를 만들 수 있습니다. 교차 원본인 관계는 실제 카디널리티에 관계없이 다 대 다 카디널리티로 생성됩니다. 일 대 다, 다 대 일 또는 일 대 일로 변경할 수 있습니다. 어떤 카디널리티를 설정하건 교차 원본 관계의 동작은 각기 다릅니다. DAX(Data Analysis Expressions) 함수를 사용하여 `many` 쪽에서 `one` 쪽의 값을 검색할 수 없습니다. 동일한 원본 내의 다 대 다 관계와 성능 영향을 비교해서 확인할 수도 있습니다.

> [!NOTE]
> 복합 모델의 컨텍스트 내에서 모든 가져온 테이블은 실제 기본 데이터 원본과 관계없이 실질적으로 단일 원본입니다.

## <a name="example-of-a-composite-model"></a>복합 모델의 예

복합 모델의 예로는 DirectQuery를 사용하여 SQL Server의 회사 데이터 웨어하우스에 연결된 보고서를 고려해 보세요. 이 경우 데이터 웨어하우스에는 다음 이미지와 같이 **국가별 영업**, **분기** 및 **Bike(제품)** 데이터가 포함됩니다.

![복합 모델에 대한 관계 보기](media/desktop-composite-models/composite-models_04.png)

이 시점에서 이 원본의 필드를 사용하여 단순한 시각적 개체를 빌드할 수 있습니다. 다음 이미지는 선택한 분기에 대한 *ProductName*별 총 매출을 보여줍니다.

![데이터 기반 시각적 개체](media/desktop-composite-models/composite-models_05.png)

그러나 각 제품에 할당된 제품 관리자에 대한 데이터가 마케팅 우선 순위와 함께 Office Excel 스프레드시트에 있는 경우에는 어떻게 될까요? **제품 관리자**에서 **판매액**을 보려는 경우 이 로컬 데이터를 회사 데이터 웨어하우스에 추가하지 못할 수 있습니다. 아니면 잘해야 몇 달이 걸릴 수도 있습니다.

DirectQuery를 사용하는 대신 데이터 웨어하우스에서 해당 판매 데이터를 가져올 수 있습니다. 그런 다음, 판매 데이터를 스프레드시트에서 가져온 데이터와 결합할 수 있습니다. 그러나 해당 방법은 처음부터 DirectQuery를 사용하도록 한 이유 때문에 불합리적입니다. 이유는 다음과 같습니다.

* 보안 규칙의 일부 조합이 기본 원본에 적용됩니다.
* 최신 데이터를 볼 수 있어야 합니다.
* 데이터의 순수한 규모입니다.

여기에 복합 모델이 도입되었습니다. 복합 모델에서는 DirectQuery를 사용하여 데이터 웨어하우스에 연결한 다음, 추가 원본에 **데이터 가져오기**를 사용할 수 있습니다. 이 예제에서는 먼저 회사 데이터 웨어하우스에 대한 DirectQuery 연결을 설정합니다. **데이터 가져오기**를 사용하고 **Excel**을 선택한 다음, 로컬 데이터가 포함된 스프레드시트로 이동합니다. 마지막으로 *제품명*, 할당된 **판매 관리자** 및 **우선 순위**가 포함된 스프레드시트를 가져옵니다.  

![탐색기 창](media/desktop-composite-models/composite-models_06.png)

**필드** 목록에는 SQL Server의 원래 **Bike** 테이블과 새 **ProductManagers** 테이블이라는 두 개의 테이블이 표시됩니다. 새 테이블에는 Excel에서 가져온 데이터가 포함됩니다.

![테이블의 필드 보기](media/desktop-composite-models/composite-models_07.png)

마찬가지로 Power BI Desktop의 **관계** 보기에 이제 **ProductManagers**라는 추가 테이블이 표시됩니다.

![테이블의 관계 보기](media/desktop-composite-models/composite-models_08.png)

이제 이 테이블을 모델의 다른 테이블과 연결해야 합니다. 항상 그렇듯이 SQL Server에서 **Bike** 테이블과 가져온 **ProductManagers** 테이블 간의 관계를 만듭니다. 즉, **Bike[ProductName]** 와 **ProductManagers[ProductName]** 간의 관계입니다. 앞에서 설명한 것처럼 원본 간의 모든 관계는 기본적으로 다 대 다 카디널리티로 설정됩니다.

![“관계 만들기” 창](media/desktop-composite-models/composite-models_09.png)

이제 이 관계를 설정했으므로 예상대로 Power BI Desktop의 **관계 보기**에 표시됩니다.

![새 관계 보기](media/desktop-composite-models/composite-models_10.png)

이제 **필드** 목록의 필드 중 하나를 사용하여 시각적 개체를 만들 수 있습니다. 이 방법은 여러 원본의 데이터를 원활하게 혼합합니다. 예를 들어, 각 *제품 관리자*의 총 *SalesAmount*가 다음 이미지에 표시됩니다.

![필드 창](media/desktop-composite-models/composite-models_11.png)

다음 예제는 **제품** 또는 **고객**과 같이 다른 곳에서 가져온 일부 추가 데이터로 확장되는 *차원* 테이블의 일반적인 경우를 표시합니다. 테이블에 DirectQuery를 사용하여 다양한 원본에 연결할 수도 있습니다. 예제를 계속 진행하기 위해 **Country** 및 **Period**별 **Sales Targets**가 별도의 부서별 데이터베이스에 저장된다고 가정합니다. 일반적으로 다음 이미지와 같이 **데이터 가져오기**를 사용하여 해당 데이터에 연결할 수 있습니다.

![탐색기 창](media/desktop-composite-models/composite-models_12.png)

이전에 수행한 작업처럼 새 테이블과 모델의 다른 테이블 간에 관계를 만든 다음, 테이블 데이터를 결합하는 시각적 개체를 만들 수 있습니다. 새로운 관계를 설정한 **관계 보기**를 다시 살펴보겠습니다.

![여러 테이블이 있는 관계 보기](media/desktop-composite-models/composite-models_13.png)

다음 이미지는 새 데이터 및 생성된 관계를 기반으로 합니다. 왼쪽 아래의 시각적 개체에서는 *판매액* 대 *대상*이 표시되고 편찬 계산에서는 차이가 표시됩니다. **판매액** 및 **대상** 데이터는 서로 다른 두 SQL Server 데이터베이스에서 가져옵니다.

![더 많은 데이터를 보여주는 이미지](media/desktop-composite-models/composite-models_14.png)

## <a name="set-the-storage-mode"></a>스토리지 모드 설정

복합 모델의 각 테이블에는 테이블이 DirectQuery를 기반으로 하는지 가져오기를 기반으로 하는지 나타내는 스토리지 모드가 있습니다. 스토리지 모드는 **속성** 창에서 보고 수정할 수 있습니다. 스토리지 모드를 표시하려면 **필드** 목록에서 테이블을 마우스 오른쪽 단추로 클릭한 다음, **속성**을 선택합니다. 다음 이미지는 **SalesTargets** 테이블의 스토리지 모드를 보여줍니다.

각 테이블의 도구 설명에서도 스토리지 모드를 볼 수 있습니다.

![스토리지 모드를 표시하는 도구 설명](media/desktop-composite-models/composite-models_16.png)

DirectQuery의 일부 테이블과 일부 가져오기 테이블을 포함하는 Power BI Desktop 파일( *.pbix* 파일)의 경우 상태 표시줄에 **혼합**이라는 스토리지 모드가 표시됩니다. 상태 표시줄에서 해당 용어를 클릭하여 모든 테이블을 가져오기로 쉽게 전환할 수 있습니다.

스토리지 모드에 대한 자세한 내용은 [Power BI Desktop의 스토리지 모드 관리](desktop-storage-mode.md)를 참조하세요.  

> [!NOTE]
> Power BI Desktop 및 Power BI 서비스에서 *혼합* 스토리지 모드를 사용할 수 있습니다.

## <a name="calculated-tables"></a>계산 테이블

DirectQuery를 사용하는 모델에 계산된 테이블을 추가할 수 있습니다. 계산된 테이블을 정의하는 DAX(데이터 분석 식)는 가져온 테이블이나 DirectQuery 테이블 또는 둘의 조합을 참조할 수 있습니다.

계산된 테이블은 항상 가져오며 테이블을 새로 고칠 때 해당 데이터가 새로 고쳐집니다. 계산된 테이블이 DirectQuery 테이블을 참조하는 경우 DirectQuery 테이블을 참조하는 시각적 개체는 항상 기본 원본의 최신 값을 표시합니다. 또는 계산된 테이블을 참조하는 시각적 개체는 계산된 테이블을 마지막으로 새로 고친 시점의 값을 보여줍니다.

## <a name="security-implications"></a>보안 의미

복합 모델에는 일부 보안 의미가 있습니다. 한 데이터 원본에 전송된 쿼리는 다른 원본에서 검색된 데이터 값을 포함할 수 있습니다. 이전 예제에서 **제품 관리자**별 **(판매액)** 을 보여주는 시각적 개체는 SQL 쿼리를 판매 관계형 데이터베이스로 보냅니다. 해당 SQL 쿼리에는 제품 관리자 및 관련 제품의 이름이 포함될 수 있습니다.

![보안 의미를 표시하는 스크립트](media/desktop-composite-models/composite-models_17.png)

따라서 스프레드시트에 저장된 정보가 이제 관계형 데이터베이스로 전송되는 쿼리에 포함됩니다. 이 정보가 기밀인 경우에는 보안 의미를 고려해야 합니다. 특히 다음 사항을 고려하세요.

* 추적 또는 감사 로그를 볼 수 있는 데이터베이스의 관리자는 원래 원본에 있는 데이터에 대한 사용 권한 없이도 이 정보를 볼 수 있습니다. 이 예제서는 관리자가 Excel 파일에 대한 사용 권한이 필요합니다.

* 각 원본에 대한 암호화 설정을 고려해야 합니다. 암호화된 연결을 통해 한 원본에서 정보를 검색한 다음, 암호화되지 않은 연결을 통해 다른 원본으로 전송되는 쿼리에 실수로 이 정보가 포함되는 것을 방지하려고 합니다.

보안에 미치는 영향을 고려했는지 확인할 수 있도록 복합 모델을 만들 때 Power BI Desktop에 경고 메시지가 표시됩니다.  

비슷한 이유로 신뢰할 수 없는 원본에서 전송된 Power BI Desktop 파일을 열 때 주의하세요. 파일에 복합 모델이 포함되는 경우 파일을 여는 사용자의 자격 증명을 사용하여 한 원본에서 검색하는 정보는 쿼리의 일부로 다른 데이터 원본으로 보내집니다. 이 정보는 Power BI Desktop 파일의 악의적인 작성자가 볼 수 있습니다. 여러 원본이 포함된 Power BI Desktop 파일을 처음 열면 Power BI Desktop에 경고가 표시됩니다. 이 경고는 네이티브 SQL 쿼리가 포함된 파일을 열 때 표시되는 경고와 비슷합니다.  

## <a name="performance-implications"></a>성능 의미  

DirectQuery를 사용할 때는 주로 사용자에게 좋은 환경을 제공할 충분한 리소스가 백 엔드 원본에 있는지 확인하기 위해 항상 성능을 고려해야 합니다. 좋은 환경이란 시각적 개체가 5초 이내의 새로 고쳐진다는 것을 의미합니다. 성능에 대한 추가 조언은 [Power BI에서 DirectQuery를 사용하는 방법](desktop-directquery-about.md)을 참조하세요.

복합 모델을 사용하면 추가 성능 고려 사항이 추가됩니다. 단일 시각적 개체는 여러 원본에 쿼리를 보낼 수 있으며, 이는 한 쿼리에서 두 번째 원본으로 결과를 전달하는 경우가 많습니다. 이 상황에서는 다음과 같은 실행 형식이 발생할 수 있습니다.

* **많은 리터럴 값을 포함하는 SQL 쿼리**: 예를 들어, 선택한 ‘**제품 관리자**’ 집합의 총 ‘**판매액**’을 요청하는 시각적 개체는 먼저 해당 제품 관리자가 관리하는 ‘**제품**’을 찾아야 합니다. 이 시퀀스는 `WHERE` 절에 모든 제품 ID가 포함된 SQL 쿼리를 시각적 개체가 보내기 전에 수행해야 합니다.

* **하위 수준의 세분성으로 쿼리하고 데이터가 나중에 로컬로 집계되는 SQL 쿼리**: **제품 관리자**의 필터 조건을 충족하는 **제품**의 수가 증가함에 따라 모든 제품을 `WHERE` 절에 포함하는 것은 비효율적이거나 불가능해질 수 있습니다. 대신 **제품**의 하위 수준에서 관계형 원본을 쿼리한 다음, 로컬로 결과를 집계할 수 있습니다. **제품**의 카디널리티가 1백만 개 제한을 초과하면 쿼리가 실패합니다.

* **여러 SQL 쿼리, 값별로 그룹당 하나**: 집계에서 **DistinctCount**를 사용하고 다른 원본의 열로 그룹화할 때 외부 원본이 그룹을 정의하는 많은 리터럴 값의 효율적인 전달을 지원하지 않는 경우 값별로 그룹당 하나의 SQL 쿼리를 보내야 합니다.

   스프레드시트에서 가져온 **제품 관리자**별 SQL Server 테이블에서 **CustomerAccountNumber**의 고유 개수를 요청하는 시각적 개체는 SQL Server로 전송되는 쿼리에서 **Product Managers** 테이블의 세부 정보를 전달해야 합니다. 예를 들어 Redshift 같은 다른 원본에서는 이 작업을 수행할 수 없습니다. 대신 쿼리가 실패하는 실제적인 제한까지 **판매 관리자**당 하나의 SQL 쿼리가 전송됩니다.

이러한 각각의 사례에는 성능에 대한 고유한 의미가 있으며 정확한 세부 정보는 각 데이터 원본에 따라 달라집니다. 두 원본을 조인하는 관계에 사용되는 열의 카디널리티가 수천 개로 낮게 유지되지만 성능에 영향을 미치지 않아야 합니다. 이 카디널리티가 증가함에 따라 결과 성능에 미치는 영향에 더 많은 주의를 기울여야 합니다.

또한 다 대 다 관계의 사용은 세부 값을 로컬로 집계하는 대신 각 합계 또는 소계 수준에 대한 기본 원본에 개별 쿼리를 보내야 함을 의미합니다. 합계가 있는 간단한 테이블 시각적 개체는 하나가 아닌 두 개의 SQL 쿼리를 보냅니다.

## <a name="limitations-and-considerations"></a>제한 사항 및 고려 사항

복합 모델의 이 릴리스에는 몇 가지 제한 사항이 있습니다.

현재 SQL, Oracle 및 Teradata 데이터 원본에 연결하는 복합 모델에 대해서만 [증분 새로 고침](service-premium-incremental-refresh.md)이 지원됩니다.

다음 Live Connect 다차원 원본은 복합 모델과 함께 사용할 수 없습니다.

* SAP HANA
* SAP Business Warehouse
* SQL Server Analysis Services
* Power BI 데이터 세트
* Azure Analysis Services

DirectQuery를 사용하여 이러한 다차원 원본에 연결하는 경우 다른 DirectQuery 원본에 연결하거나 가져오기 데이터와 결합할 수 없습니다.

복합 모델을 사용하면 DirectQuery의 기존 제한 사항이 여전히 적용됩니다. 이러한 제한 사항 중 대부분은 테이블의 스토리지 모드에 따라 테이블별로 적용됩니다. 예를 들어 가져오기 테이블에서 계산된 열은 다른 테이블을 참조할 수 있지만, DirectQuery 테이블에서 계산된 열은 여전히 동일한 테이블의 열만 참조할 수 있습니다. 다른 제한 사항은 모델 내의 테이블이 DirectQuery인 경우 모델에 전체적으로 적용됩니다. 예를 들어 QuickInsights 및 Q&amp;A 기능은 모델 내의 테이블에 DirectQuery의 스토리지 모드가 있는 경우 모델에서 사용할 수 없습니다.

## <a name="next-steps"></a>다음 단계

복합 모델 및 DirectQuery에 대한 자세한 내용은 다음 문서를 참조하세요.

* [Power BI Desktop의 다 대 다 관계](desktop-many-to-many-relationships.md)
* [Power BI Desktop의 스토리지 모드](desktop-storage-mode.md)
* [Power BI의 DirectQuery 사용](desktop-directquery-about.md)
* [Power BI의 DirectQuery에서 지원하는 데이터 원본](desktop-directquery-data-sources.md)

