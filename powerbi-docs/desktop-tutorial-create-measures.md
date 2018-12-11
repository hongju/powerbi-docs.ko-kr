---
title: '자습서: Power BI Desktop에서 고유한 측정값 만들기'
description: '자습서: Power BI Desktop에서 고유한 측정값 만들기'
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: tutorial
ms.date: 11/28/2018
ms.author: davidi
LocalizationGroup: Learn more
ms.openlocfilehash: 85c16822a51bc3c4a59bbfaa363f742f77552b72
ms.sourcegitcommit: 05303d3e0454f5627eccaa25721b2e0bad2cc781
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "52578638"
---
# <a name="tutorial-create-your-own-measures-in-power-bi-desktop"></a>자습서: Power BI Desktop에서 고유한 측정값 만들기
측정값을 사용하여 Power BI Desktop에서 가장 강력한 데이터 분석 솔루션 중 일부를 만들 수 있습니다. 측정값은 보고서를 조작할 때 데이터에서 계산을 수행하여 도움을 줍니다. 이 자습서에서는 Power BI Desktop에서 고유한 기본 측정값을 이해하고 만드는 과정을 안내합니다.

### <a name="prerequisites"></a>필수 조건
- 이 자습서는 Power BI Desktop을 사용하여 고급 모델을 만드는 방법을 이미 알고 있는 Power BI 사용자를 위한 것입니다. 데이터 가져오기 및 쿼리 편집기를 사용하여 데이터 가져오기, 여러 가지 관련 테이블 사용, 보고서 캔버스에 필드 추가와 같은 작업을 이미 알고 있어야 합니다. Power BI Desktop을 처음 사용하는 경우 [Power BI Desktop 시작](desktop-getting-started.md)을 확인해야 합니다.
  
- 가상 회사 Contoso, Inc.의 온라인 판매 데이터가 포함된 [Power BI Desktop용 Contoso 판매 샘플](http://download.microsoft.com/download/4/6/A/46AB5E74-50F6-4761-8EDB-5AE077FD603C/Contoso%20Sales%20Sample%20for%20Power%20BI%20Desktop.zip) 파일을 다운로드하세요. 이 데이터는 데이터베이스에서 가져온 것이므로 데이터 원본에 연결하거나 쿼리 편집기에서 볼 수 없습니다. 사용자 컴퓨터에서 파일을 추출한 다음, Power BI Desktop에서 엽니다.

## <a name="understand-measures"></a>측정값 이해

측정값은 대부분 자동으로 만들어집니다. Contoso 판매 샘플 파일의 필드에 있는 **Sales** 테이블의 **SalesAmount** 필드 옆에 있는 확인란을 선택하거나 **SalesAmount**를 보고서 캔버스로 끌어서 놓습니다. Sales 테이블의 SalesAmount 열에 있는 모든 값의 합계를 보여주는 새로운 세로 막대형 차트 시각화가 나타납니다.

![SalesAmount 차트](media/desktop-tutorial-create-measures/meastut_salesamountchart.png)

필드에 시그마 아이콘 ![시그마 아이콘](media/desktop-tutorial-create-measures/meastut_sigma.png) 과 함께 표시되는 모든 필드는 숫자이며 해당 값을 집계할 수 있습니다. SalesAmount 값에 대한 2백만 개의 행이 포함된 테이블을 표시하는 대신 Power BI Desktop에서는 숫자 데이터 형식을 검색하고 자동으로 측정값을 만들고 계산하여 데이터를 집계했습니다. 합계는 숫자 데이터 형식에 대한 기본 집계이지만, 평균 또는 개수와 같은 다른 집계를 쉽게 적용할 수 있습니다. 모든 측정값은 일종의 집계를 수행하므로 측정값을 이해하려면 기본적으로 집계를 이해해야 합니다. 

차트 집계를 평균으로 변경하려면 [시각화] 창의 **값** 영역에서 **SalesAmount** 옆의 아래쪽 화살표를 클릭하고 **평균**을 선택합니다. 시각화가 SalesAmount 필드에 있는 모든 판매액 값의 평균으로 변경됩니다.

![SalesAmount 평균 차트](media/desktop-tutorial-create-measures/meastut_salesamountaveragechart.png)

원하는 결과에 따라 집계 유형을 변경할 수 있지만 모든 집계 유형이 모든 숫자 데이터 형식에 적용되는 것은 아닙니다. 예를 들어 SalesAmount 필드의 경우 합계 및 평균이 적합합니다. 최소값 및 최대값도 적용할 수 있습니다. 그러나 해당 값은 숫자이지만 실제로는 통화이기 때문에 개수는 SalesAmount 필드에 적합하지 않습니다.

측정값에서 계산된 값은 보고서 조작에 대한 응답으로 변경됩니다. 예를 들어 **Geography** 테이블에서 차트로 **RegionCountryName** 필드를 끌면 각 국가에 대한 평균 판매액이 표시됩니다.

![국가별 판매액](media/desktop-tutorial-create-measures/meastut_salesamountavchartbyrcn.png)

보고서 조작으로 인해 측정값의 결과가 변경되면 측정값의 ‘컨텍스트’에 영향을 준 것입니다. 실제로 보고서 시각화를 조작할 때마다 측정값이 결과를 계산하여 표시하는 컨텍스트가 변경됩니다.

## <a name="create-and-use-your-own-measures"></a>고유한 측정값 만들기 및 사용

대부분의 경우 Power BI는 사용자가 선택한 필드 및 집계의 형식에 따라 값을 자동으로 계산하고 반환하지만, 보다 복잡한 고유 계산을 수행하기 위해 고유한 측정값을 만들 수 있습니다. Power BI Desktop에서는 DAX(Data Analysis Expressions) 수식 언어로 고유한 측정값을 만들 수 있습니다. 

DAX 수식에서는 Excel 수식과 동일한 함수, 연산자 및 구문을 많이 사용합니다. 그러나 DAX의 함수는 관계형 데이터에서 작동하고 보고서를 조작할 때 보다 동적인 계산을 수행하도록 설계되었습니다. 합계 및 평균과 같은 간단한 집계에서 보다 복잡한 통계 및 필터링 함수까지 모든 작업을 수행하는 DAX 함수는 200가지가 넘습니다. DAX에 대해 자세히 알아보는 데 도움이 되는 많은 리소스가 있습니다. 이 자습서를 완료한 후에는 [Power BI Desktop의 DAX 기본 사항](desktop-quickstart-learn-dax-basics.md)을 참조해야 합니다.

고유한 측정값을 만들면 해당 측정값이 선택한 테이블의 필드 목록에 추가되고 이를 ‘모델’ 측정값이라고 합니다. 모델 측정값의 몇 가지 장점은 원하는 대로 이름을 지정하여 쉽게 식별하도록 만들 수 있고, 다른 DAX 식의 인수로 사용할 수 있고, 복잡한 계산을 매우 빠르게 수행하도록 지정할 수 있다는 것입니다.

>[!TIP]
>Power BI Desktop의 2018년 2월 릴리스부터, 대화 상자에 입력한 내용에 따라 DAX 수식을 자동으로 작성하는 **빠른 측정**으로 많은 일반적인 계산을 사용할 수 있습니다. 이러한 빠르고 강력한 계산은 DAX를 학습하거나 고유한 사용자 지정 측정값을 시드하는 데도 적합합니다. 빠른 측정을 만들거나 탐색하려면 테이블의 **추가 옵션** 목록에서 또는 리본에 있는 [홈] 탭의 **계산**에서 **새 빠른 측정**을 선택합니다. 빠른 측정을 만들고 사용하는 방법에 대한 자세한 내용은 [빠른 측정 사용](desktop-quick-measures.md)을 참조하세요.

### <a name="create-a-measure"></a>측정값 만들기

총 판매액에서 할인액과 반품액을 빼서 순 매출액을 분석하려고 합니다. 시각화에 있는 컨텍스트에 관계없이 SalesAmount의 합계에서 DiscountAmount 및 ReturnAmount의 합계를 빼는 측정값이 필요합니다. 필드 목록에는 순매출액에 대한 필드가 없지만 고유한 측정값을 만들어 순매출액을 계산할 수 있는 구성 요소가 있습니다. 

1.  필드에서 **Sales** 테이블을 마우스 오른쪽 단추로 클릭하거나 테이블을 마우스로 가리키고 **추가 옵션** 줄임표(...)를 선택한 다음, **새 측정**을 선택합니다. 새 측정값이 Sales 테이블에 저장되고, 이 테이블에서 새 측정값을 쉽게 찾을 수 있습니다.
    
    ![새 측정값](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure.png)
    
    Power BI Desktop 리본 메뉴의 [홈] 탭에 있는 [계산] 그룹에서 **새 측정값**을 선택하여 새 측정값을 만들 수도 있습니다.
    
    ![리본의 새 측정값](media/desktop-tutorial-create-measures/meastut_netsales_newmeasureribbon.png)
    
    >[!TIP]
    >리본 메뉴에서 측정값을 만들면 측정값이 모든 테이블에서 만들어질 수 있지만, 사용하려는 테이블에서 만들면 측정값을 더 쉽게 찾을 수 있습니다. 이 경우 먼저 Sales 테이블을 선택하여 활성화한 다음, **새 측정값**을 선택합니다. 
    
    수식 입력줄이 측정값 이름을 바꾸고 DAX 수식을 입력할 수 있는 보고서 캔버스 위에 표시됩니다.
    
    ![수식 입력줄](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formulabar.png)
    
2.  기본적으로 새 측정값의 이름은 간단히 측정값입니다. 이름을 바꾸지 않으면 추가적인 새 측정값의 이름이 측정값 2, 측정값 3 등으로 지정됩니다. 측정값을 보다 쉽게 식별하려고 하므로 수식 입력줄에서 **측정값**을 강조 표시한 다음, **Net Sales**를 입력합니다.
    
3.  이제 수식 입력을 시작할 수 있습니다. 등호 기호 뒤에 먼저 **Sum**을 입력합니다. 입력할 때 입력하는 문자로 시작하는 모든 DAX 함수를 보여주는 드롭다운 제안 목록이 표시됩니다. 필요한 경우 아래로 스크롤하여 목록에서 **SUM**을 선택한 다음, Enter 키를 누릅니다.
    
    ![SUM 선택](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_s.png)
    
    SUM 함수에 전달할 수 있는 사용 가능한 모든 열의 드롭다운 제안 목록과 함께 여는 괄호가 나타납니다.
    
    ![열 선택](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_sum.png)
    
    식은 항상 여는 괄호와 닫는 괄호 사이에 나타납니다. 식에는 SUM 함수에 전달할 단일 인수인 SalesAmount 열이 포함됩니다. 목록에 Sales(SalesAmount) 값 하나만 남을 때까지 “SalesAmount”를 입력합니다. 열 이름 앞에 테이블 이름이 오는 경우 열의 ‘정규화된 이름’이라고 합니다. 정규화된 열 이름을 사용하면 수식을 읽기가 더 쉽습니다. 
    
    ![SalesAmount 선택](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_salesam.png)
    
4. **Sales[SalesAmount]** 를 선택하고 닫는 괄호를 입력합니다.
    
    > [!TIP]
    > 구문 오류는 닫는 괄호가 누락되거나 잘못 배치되어 발생하는 경우가 가장 많습니다.
    
    
    
5.  다른 두 열을 빼려면:
    1. 첫 번째 식의 닫는 괄호 뒤에 공백, 빼기 연산자(**-**) 및 공백을 차례로 입력합니다. 
    2. 다른 SUM 함수를 입력하고 **Sales[DiscountAmount]** 열을 인수로 선택할 수 있을 때까지 “DiscountAmount” 입력을 시작합니다. 닫는 괄호를 추가합니다. 
    3. 공백, 또 다른 빼기 연산자, 공백, 인수로 **Sales[ReturnAmount]** 를 사용하는 또 다른 SUM 함수 및 닫는 괄호를 차례로 입력합니다.
    
    ![수식 완료](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_discamount.png)
    
6.  Enter 키를 누르거나 수식 입력줄에서 확인 표시를 클릭하여 수식을 완료하고 유효성을 검사합니다. 이제 유효성 검사된 측정을 Sales 테이블의 필드 목록에서 사용할 수 있습니다. 
    
    ![필드 목록의 측정값](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_complete.png)
    
수식을 입력할 공간이 없거나 수식을 별도의 줄에 놓으려면 수식 입력줄 오른쪽에 있는 아래쪽 펼침 단추를 선택하여 더 많은 공간을 엽니다.

![수식 펼침 단추](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_chevron.png)

**Alt-Enter**를 눌러 수식의 일부를 다른 줄에 나누거나 **Tab** 키를 사용하여 항목을 이동할 수 있습니다.

![수식 확장됨](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_expanded.png)

### <a name="use-your-measure-in-the-report"></a>보고서에서 측정값 사용
이제 Net Sales 측정값을 보고서 캔버스에 추가하고 보고서에 추가하는 다른 모든 필드에 대해 순매출액을 계산할 수 있습니다. 국가별 순매출액을 확인하려면:

1. **Sales** 테이블에서 **Net Sales** 측정값을 선택하거나 이 측정값을 보고서 캔버스로 끌어서 놓습니다.
    
2. **Geography** 테이블에서 **RegionCountryName** 필드를 선택하거나 이 필드를 차트로 끌어서 놓습니다.
    
    ![국가별 순매출액](media/desktop-tutorial-create-measures/meastut_netsales_byrcn.png)
    
국가별 순매출액과 총 판매액의 차이를 확인하려면 **SalesAmount** 필드를 선택하거나 차트로 끌어서 놓습니다. 

![국가별 판매액 및 순매출액](media/desktop-tutorial-create-measures/meastut_netsales_byrcnandsalesamount.png)

이제 차트에는 두 가지 측정값, 자동으로 합계된 SalesAmount 및 사용자가 만든 Net Sales 측정값이 사용됩니다. 각 측정값은 다른 필드 RegionCountryName의 컨텍스트에서 계산됩니다.
    
### <a name="use-your-measure-with-a-slicer"></a>슬라이서와 함께 측정값 사용

순매출액 및 판매액을 연도별로 필터링하도록 슬라이서를 추가할 수 있습니다.
    
1.  차트 옆에 있는 빈 영역을 클릭한 다음, **시각화**에서 **테이블** 시각화를 선택합니다. 보고서 캔버스에 빈 테이블 시각화가 만들어집니다.
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_blanktable.png)
    
2.  **Calendar** 테이블에서 새 빈 테이블 시각화로 **Year** 필드를 끌어서 놓습니다. Year는 숫자 필드이기 때문에 Power BI Desktop이 해당 값의 합계를 계산하지만, 이는 집계를 의미하지는 않습니다. 
    
    ![연도 집계](media/desktop-tutorial-create-measures/meastut_netsales_yearaggtable.png)
    
3.  [시각화] 창의 **값**에서 **Year** 옆의 아래쪽 화살표를 선택한 다음, **요약 안 함**을 선택합니다. 이제 테이블에 개별 연도가 나열됩니다.
    
    ![요약 안 함](media/desktop-tutorial-create-measures/meastut_netsales_year_donotsummarize.png)
    
4.  [시각화] 창에서 **슬라이서** 아이콘을 선택하여 테이블을 슬라이서로 변환합니다.

    ![슬라이서로 변경](media/desktop-tutorial-create-measures/meastut_netsales_year_changetoslicer.png)
    
5.  **Year** 슬라이서에서 값을 선택하여 이에 따라 **국가별 순매출액 및 판매액** 차트를 필터링합니다. Net Sales 및 SalesAmount 측정값이 다시 계산되고 결과가 선택한 Year 필드의 컨텍스트에서 표시됩니다. 
    
    ![연도별로 조각화된 차트](media/desktop-tutorial-create-measures/meastut_netsales_chartslicedbyyear.png)

### <a name="use-your-measure-in-another-measure"></a>다른 측정값에서 측정값 사용

판매 단위당 순매출액이 가장 높은 제품을 찾으려고 하므로 판매 단위 수량으로 순매출액을 나누는 측정값이 필요합니다. 실제로는 Net Sales 측정값의 결과를 Sales[SalesQuantity]의 합계로 나누는 새 측정값을 만들 수 있습니다.

1.  Sales 테이블에 **Net Sales per Unit**이라는 새 측정값을 만듭니다.
    
2.  수식 입력줄에서 **Net Sales**를 입력하기 시작합니다. 제안 목록에 추가할 수 있는 항목이 표시됩니다. **[Net Sales]** 를 선택합니다.
    
    ![Net Sales를 사용하는 수식](media/desktop-tutorial-create-measures/meastut_nspu_formulastep2a.png)
    
    여는 대괄호(**[**)만 입력하여 다른 측정값을 참조할 수도 있습니다. 제안 목록에는 수식에 추가할 측정값만 표시됩니다.
    
    ![대괄호는 측정값만 표시함](media/desktop-tutorial-create-measures/meastut_nspu_formulastep2b.png)
    
3.  공백, 나누기 연산자(**/**), 다른 공백, SUM 함수를 차례로 입력한 다음, **Quantity**를 입력합니다. 이름에 Quantity가 포함된 모든 열이 제안 목록에 표시됩니다. **Sales[SalesQuantity]** 를 선택하고, 닫는 괄호를 입력하고, Enter 키를 누르거나 확인 표시를 선택하여 수식의 유효성을 검사합니다. 수식이 다음과 같이 표시됩니다.
    
    `Net Sales per Unit = [Net Sales] / SUM(Sales[SalesQuantity])`
    
4. Sales 테이블에서 **Net Sales per Unit** 측정값을 선택하거나 이 측정값을 보고서 캔버스의 빈 영역으로 끌어서 놓습니다. 차트에는 판매되는 모든 제품에 대한 단위당 순매출액이 표시되며, 이는 그다지 유용하지 않습니다. 
    
    ![단위당 전체 순매출액](media/desktop-tutorial-create-measures/meastut_nspu_chart.png)
    
5. 다른 모양으로 보려면 차트 시각화 유형을 **Treemap**으로 변경합니다.
    
    ![Treemap으로 변경](media/desktop-tutorial-create-measures/meastut_nspu_changetotreemap.png)
    
6. **Product Category** 필드를 선택하거나 이 필드를 Treemap으로 또는 [시각화] 창의 [그룹] 필드로 끌어서 놓습니다. 이제 몇 가지 유용한 정보가 제공됩니다.
    
    ![제품 범주별 Treemap](media/desktop-tutorial-create-measures/meastut_nspu_byproductcat.png)
    
7. **ProductCategory** 필드를 제거하고 대신 **ProductName** 필드를 차트로 끌어서 놓습니다. 
    
    ![제품 이름별 Treemap](media/desktop-tutorial-create-measures/meastut_nspu_byproductname.png)
    
이제 모두 완료했습니다. 즐거운 경험이었을 것입니다! 시각화를 필터링하고 서식을 지정하는 다양한 방법을 실험해 보세요.

## <a name="what-youve-learned"></a>학습한 내용
측정값을 활용하면 다양한 기능을 통해 데이터에서 원하는 인사이트를 얻을 수 있습니다. 수식 입력줄을 사용하여 측정값을 만들고, 가장 적합한 이름을 지정하고, DAX 제안 목록을 사용하여 적합한 수식 요소를 찾아 선택하는 방법을 배웠습니다. 또한 측정값의 계산 결과가 다른 필드 또는 수식의 다른 식에 따라 변경되는 컨텍스트에 대해 검토했습니다.

## <a name="next-steps"></a>다음 단계
- 자동으로 많은 일반적인 측정값을 계산하는 Power BI Desktop 빠른 측정에 대해 자세히 알아보려면 [빠른 측정을 사용하여 일반적이고 강력한 계산 수행](desktop-quick-measures.md)을 참조하세요.
  
- DAX 수식을 잘 이해하고 고급 측정값을 만들려면 [Power BI Desktop의 DAX 기본 사항](desktop-quickstart-learn-dax-basics.md)을 참조하세요. 이 문서에서는 구문, 함수 및 컨텍스트에 대한 보다 철저한 이해와 같은 DAX의 기본 개념에 중점을 둡니다.
  
- 잊지 말고 [DAX(Data Analysis Expressions) 참조](https://msdn.microsoft.com/library/gg413422.aspx)를 즐겨찾기에 추가하세요. 여기서는 DAX 구문, 연산자 및 200개가 넘는 DAX 함수에 대한 자세한 내용을 확인할 수 있습니다.

