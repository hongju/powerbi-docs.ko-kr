---
title: Power BI Desktop의 측정값
description: Power BI Desktop에서 빠른 측정값과 DAX 구문을 포함하여 측정값 만들기 및 사용
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/10/2020
ms.author: davidi
LocalizationGroup: Model your data
ms.openlocfilehash: 89934ca8ed64dd5e60a52e56c6aa1c172cf10435
ms.sourcegitcommit: 4b926ab5f09592680627dca1f0ba016b07a86ec0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2020
ms.locfileid: "75837447"
---
# <a name="create-measures-for-data-analysis-in-power-bi-desktop"></a>Power BI Desktop에서 데이터 분석을 위한 측정값 만들기

Power BI Desktop에서는 몇 번의 클릭만으로 데이터에 대한 정보를 만들 수 있습니다. 그러나 가장 중요한 질문에 답변하는 데 필요한 모든 정보가 해당 데이터에 포함되지 않은 경우도 있습니다. 이러한 경우 측정값을 사용하면 도움이 될 수 있습니다.

측정값은 가장 일반적인 데이터 분석에서 사용됩니다. 합계, 평균, 최솟값, 최댓값, 개수 등의 간단한 요약을 **필드**를 통해 설정할 수 있습니다. 측정값의 계산된 결과는 보고서 조작에 대한 응답으로 항상 변경되어 빠른 동적 임시 데이터 탐색이 가능합니다. 측정값에 대해 좀 더 자세히 살펴보겠습니다. 자세한 내용은 [계산 측정값 만들기](/learn/modules/model-data-power-bi/4b-create-calculated-measures)를 참조하세요.

## <a name="understanding-measures"></a>측정값 이해

Power BI Desktop에서 측정값은 *보고서 뷰* 또는 *데이터 뷰*에서 만들고 표시합니다. 사용자가 직접 만든 측정값은 계산기 아이콘과 함께 **필드** 목록에 나타납니다. 측정값에 원하는 대로 이름을 지정하고 다른 모든 필드처럼 새 시각화나 기존 시각화에 추가할 수 있습니다.

![필드의 측정값 필드](media/desktop-measures/measuresinpbid_measinfieldlist.png)

> [!NOTE]
> 대화 상자에서 선택할 수 있는 이미 작성된 측정인 *빠른 측정*에도 관심이 있을 수 있습니다. 빠른 측정은 자동으로 생성된 DAX 수식을 검토할 수 있으므로 측정을 신속하게 작성하고 DAX(Data Analysis Expressions) 구문을 익힐 좋은 방법입니다. 자세한 내용은 [빠른 측정](desktop-quick-measures.md)을 참조하세요.
> 
> 

## <a name="data-analysis-expressions"></a>Data Analysis Expressions

측정값은 수식의 결과를 계산합니다. 고유한 측정값을 만드는 경우 [DAX(Data Analysis Expressions)](/dax/) 수식 언어를 사용합니다. DAX에는 200개가 넘는 함수, 연산자 및 구문의 라이브러리가 포함됩니다. 해당 라이브러리는 데이터 분석 필요에 대한 결과를 계산하는 측정값을 만들 때 뛰어난 유연성을 제공합니다.

DAX 수식은 Excel 수식과 매우 유사합니다. DAX에는 `DATE`, `SUM`, `LEFT`와 같이 Excel과 동일한 함수도 많습니다. 그러나 DAX의 함수는 Power BI Desktop에서처럼 관계형 데이터에서 작동합니다.

## <a name="lets-look-at-an-example"></a>예를 살펴보겠습니다.

Jan은 Contoso의 판매 관리자입니다. Jan은 다음 회계 연도의 재판매인 판매 예상액을 제공해달라는 요청을 받았습니다. 따라서 작년의 판매액을 기준으로 예측하기로 결정하고 다음 6개월 동안 예정된 다양한 프로모션의 결과로 판매액이 연간 6% 증가할 것으로 판단합니다.

Jan은 예상액을 보고하기 위해 작년의 판매 데이터를 Power BI Desktop으로 가져옵니다. Jan은 **Reseller Sales** 테이블에서 **SalesAmount** 필드를 찾습니다. 가져온 데이터에 작년의 판매액만 포함되어 있으므로 Jan은 **SalesAmount** 필드의 이름을 *Last Years Sales*로 바꿉니다. 그런 다음, **Last Years Sales**를 보고서 캔버스로 끌어옵니다. 해당 필드가 차트 시각화에서 작년의 모든 대리점 판매액의 합계인 단일 값으로 나타납니다.

Jan은 계산을 지정하지 않았지만 계산이 자동으로 제공되었음을 확인합니다. Power BI Desktop에서 **Last Years Sales**의 값을 모두 합하여 측정값을 직접 만들었습니다.

하지만 Jan은 다음 해의 판매 예상액을 계산하는 측정값이 필요하며, 이 값은 6% 예상 증가를 고려하여 작년의 판매액에 1.06을 곱한 값을 기준으로 합니다. 이 계산을 위해 Jan은 측정값을 만듭니다. *새 측정값* 기능을 사용하여 새 측정값을 만들고 다음과 같은 DAX 수식을 입력합니다.

```sql
    Projected Sales = SUM('Sales'[Last Years Sales])*1.06
```

그런 다음, 새로운 Projected Sales 측정값을 차트로 끌어옵니다.

![새 Projected Sales 시각적 개체](media/desktop-measures/measuresinpbid_lastyearsales.png)

이제 Jan은 최소한의 노력으로 신속하게 예상 판매량을 계산하는 측정값을 얻었습니다. Jan은 특정 재판매인을 필터링하거나 보고서에 다른 필드를 추가하여 예상액을 추가로 분석할 수 있습니다.

## <a name="data-categories-for-measures"></a>측정값에 대한 데이터 범주

측정값에 대한 데이터 범주를 선택할 수도 있습니다.

데이터 범주를 사용하면 무엇보다도 측정값을 사용하여 동적으로 URL을 만들고 데이터 범주를 웹 URL로 표시할 수 있습니다.

측정값을 웹 URL로 표시하는 테이블을 만들고 선택에 따라 만든 URL을 클릭할 수 있습니다. 이 접근 방식은 [URL 필터 매개 변수](service-url-filters.md)를 사용하여 다른 Power BI 보고서에 연결하려고 할 때 특히 유용합니다.

## <a name="organizing-your-measures"></a>측정값 구성

측정값에는 필드 목록에서 찾을 위치를 정의하는 *홈* 테이블이 있습니다. 모델의 테이블에서 위치를 선택하여 해당 위치를 변경할 수 있습니다.

![측정값에 대한 테이블 선택](media/desktop-measures/measures-03.png)

테이블의 필드를 *표시 폴더*로 구성할 수도 있습니다. Power BI Desktop 왼쪽 가장자리에서 **모델**을 선택합니다. **속성** 창의 사용 가능한 필드 목록에서 이동하려는 필드를 선택합니다. **표시 폴더**에서 새 폴더의 이름을 입력하여 폴더를 만듭니다. 폴더를 만들면 선택한 필드가 해당 폴더로 이동됩니다.

![측정값에 사용할 필드 만들기](media/desktop-measures/measures-04.gif)

백슬래시 문자를 사용하여 하위 폴더를 만들 수 있습니다. 예를 들어, *Finance\Currencies*는 *Finance* 폴더를 만들고 그 안에 *Currencies* 폴더를 만듭니다.

세미콜론으로 폴더 이름을 구분하여 여러 폴더에 필드를 표시할 수 있습니다. 예를 들어 *Products\Names;Departments*는 *Departments* 폴더와 *Products* 폴더 내 *Names* 폴더에 필드를 표시합니다.

측정값만 포함하는 특수 테이블을 만들 수 있습니다. 이 테이블은 항상 **필드** 맨 위에 나타납니다. 이렇게 하려면 열이 하나만 있는 테이블을 만듭니다. **데이터 입력**을 사용하여 해당 테이블을 만들 수 있습니다. 그런 다음 측정값을 해당 테이블로 이동합니다. 마지막으로, 앞에서 만든 열은 숨기되 테이블은 숨기지 않습니다. **필드** 맨 위에 있는 화살표를 선택하여 필드 목록을 닫고 다시 열어서 변경 사항을 확인합니다.

![측정값을 구성하고 필드 목록의 맨 위에 유지](media/desktop-measures/measures-05.png)

## <a name="learn-more"></a>자세한 정보

여기서는 측정값에 대한 간략한 소개만 제공했습니다. 사용자 자체 측정값을 만드는 데 도움을 주는 다양한 리소스가 준비되어 있습니다. 자세한 내용은 [자습서: Power BI Desktop에서 고유한 측정값 만들기](desktop-tutorial-create-measures.md)를 참조하세요. 샘플 파일을 다운로드하여 더 많은 측정값을 만드는 방법에 대한 단계별 학습을 진행할 수 있습니다.  

DAX에 대해 자세히 알아보려면 [Power BI Desktop의 DAX 기본 사항](desktop-quickstart-learn-dax-basics.md)을 참조하세요. [DAX(Data Analysis Expressions) 참조](/dax/)에서는 각 함수, 구문, 연산자 및 명명 규칙에 대한 자세한 문서를 제공합니다. DAX는 Excel 및 SQL Server Analysis Services의 파워 피벗에서 여러 해 동안 사용되었으므로 여러 가지 유용한 리소스를 사용할 수 있습니다. BI 커뮤니티의 영향력 있는 멤버가 DAX에 대한 지식을 공유하는 [DAX 리소스 센터 Wiki](https://social.technet.microsoft.com/wiki/contents/articles/1088.dax-resource-center.aspx)(영문)를 확인하세요.
