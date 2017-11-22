---
title: "자습서: Power BI Desktop에서 계산 열 만들기"
description: "자습서: Power BI Desktop에서 계산 열 만들기"
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
ms.date: 09/06/2017
ms.author: davidi
ms.openlocfilehash: 7e959054300dafcab5f38bfce121fe0ac91dca06
ms.sourcegitcommit: f2b38777ca74c28f81b25e2f739e4835a0ffa75d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2017
---
# <a name="tutorial-create-calculated-columns-in-power-bi-desktop"></a>자습서: Power BI Desktop에서 계산 열 만들기
분석 중인 데이터에 원하는 결과를 얻는 데 필요한 특정 필드가 없는 경우도 있습니다. 이때 계산된 열이 사용됩니다. 계산된 열은 DAX(Data Analysis Expressions) 수식을 사용하여 열의 값을 정의합니다. 이러한 값은 모델에 있는 다른 몇 개 열의 텍스트 값을 결합하든, 다른 값에서 숫자 값을 계산하든 간에 거의 모든 값이 될 수 있습니다. 예를 들어 데이터에 City 및 State 열이 필드 목록의 필드로 포함되어 있지만 Miami, FL와 같이 하나의 Location 필드에 두 필드를 단일 값으로 포함하려 한다고 가정합니다. 계산된 열은 바로 이런 용도로 사용됩니다.

계산된 열은 둘 다 DAX 수식을 기반으로 한다는 점에서 측정값과 비슷하지만 사용하는 방법이 서로 다릅니다. 측정값은 표의 행이나 시각화의 축, 범례 또는 그룹 영역에 있는 다른 필드에 따라 결과를 계산하기 위해 시각화의 Values 영역에서 자주 사용됩니다. 반면, 계산된 열은 표의 해당 행이나 축, 범례 또는 그룹 영역에 열의 결과를 표시하려는 경우에 사용됩니다.

이 자습서에서는 Power BI Desktop에서 사용자 고유의 계산된 열 중 일부를 이해하고 만드는 과정을 안내합니다. 이는 Power BI Desktop을 사용하여 고급 모델을 만드는 방법을 이미 알고 있는 Power BI 사용자를 위한 것입니다. 쿼리를 사용하여 데이터 가져오기, 여러 가지 관련 테이블 사용, 보고서 캔버스에 필드 추가와 같은 작업을 이미 알고 있어야 합니다. Power BI Desktop을 처음 사용하는 경우 [Power BI Desktop 시작](desktop-getting-started.md)을 확인해야 합니다.

이 자습서의 단계를 완료하려면 [Power BI Desktop용 Contoso 판매 샘플](http://download.microsoft.com/download/4/6/A/46AB5E74-50F6-4761-8EDB-5AE077FD603C/Contoso%20Sales%20Sample%20for%20Power%20BI%20Desktop.zip) 파일을 다운로드해야 합니다. 동일한 샘플 파일이 [Power BI Desktop에서 사용자 고유의 측정값 만들기](desktop-tutorial-create-measures.md) 자습서에도 사용됩니다. 가상 회사인 Contoso, Inc.의 판매 데이터가 이미 포함되어 있습니다. 파일의 데이터는 데이터베이스에서 가져온 것이므로 데이터 소스에 연결하거나 Query Editor에서 볼 수 없습니다. 파일이 사용자 컴퓨터에 있는 경우 계속 진행하여 Power BI Desktop에서 엽니다.

## <a name="lets-create-a-calculated-column"></a>계산된 열을 만들어 보겠습니다.
휴대폰 – 액세서리, 휴대폰 – 스마트폰 및 PDA 등과 같이 제품 범주와 제품 하위 범주를 행에 하나의 값으로 표시하려 한다고 가정합니다. 리포트 보기 또는 데이터 보기에서(여기서는 리포트 보기를 사용합니다.) 필드 목록의 제품 표를 보면 원하는 사항을 제공하는 필드가 없습니다. 그러나 ProductCategory 필드와 ProductSubcategory 필드가 해당 표에 각각 포함되어 있습니다.

 ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_nonewcol.png)

새 계산된 열을 만들어 이러한 두 열의 값을 새 열의 새로운 값으로 결합합니다. 서로 다른 두 표의 데이터를 하나의 열로 결합해야 합니다. DAX를 사용하여 새 열을 만들기 때문에 표 간의 기존 관계를 포함하여 이미 보유한 모델을 최대한 활용할 수 있습니다.

### <a name="to-create-a-productfullcategory-column"></a>ProductFullCategory 열을 만들려면
1.  필드 목록의 **ProductSubcategory** 표에서 아래쪽 화살표를 마우스 오른쪽 단추로 클릭하거나 클릭한 다음 **새 열**을 클릭합니다. 그러면 ProductSubcategory 표에 새 열이 추가됩니다.
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_newcolumn.png)
    
    보고서 캔버스 또는 데이터 표의 맨 위에 수식 입력줄이 나타납니다. 여기서 열의 이름을 바꾸고 DAX 수식을 입력할 수 있습니다.
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_newcolumnformula.png)
    
    기본적으로 새 계산된 열의 이름은 열로 지정됩니다. 이름을 바꾸지 않을 경우 다른 열을 만들면 열 2, 열 3 등으로 이름이 지정됩니다. 열을 식별하기 쉽도록 새 열에 새로운 이름을 지정하겠습니다.
    
2.  수식 입력줄에 **열** 이름이 이미 강조 표시되어 있으므로 **ProductFullCategory**를 입력하면 됩니다.
    
    이제 수식 입력을 시작할 수 있습니다. 새 열의 값을 ProductCategory 표의 ProductCategory 이름으로 시작하려고 합니다. 이 열은 다른 관련된 표에 있으므로 [RELATED](https://msdn.microsoft.com/library/ee634202.aspx) 함수를 사용하여 가져오겠습니다.
    
3.  등호 기호 뒤에 **R**을 입력합니다. 드롭다운 추천 목록에 문자 R로 시작하는 모든 DAX 함수가 나타나는 것을 확인할 수 있습니다. 더 많이 입력할수록 필요한 함수에 더 가깝게 조정된 추천 목록이 더 많이 표시됩니다. 함수 옆에 함수에 대한 설명이 표시됩니다. 아래로 스크롤하여 **RELATED**를 선택하고 Enter 키를 누릅니다.
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_pfc_1.png)
    
    RELATED 함수에 전달할 수 있는 사용 가능한 모든 열의 다른 제안 목록과 함께 여는 괄호가 나타납니다. 필요한 매개 변수에 대한 설명 및 세부 정보도 표시됩니다.
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_pfc_2.png)
    
    식은 항상 여는 괄호와 닫는 괄호 사이에 나타납니다. 이 경우 RELATED 함수로 전달된 단일 인수, 즉 값을 반환할 관련된 열이 식에 포함됩니다. 열 목록이 관련된 열만 표시하도록 자동으로 축소됩니다. 이 경우 ProductCategory 표의 ProductCategory 열을 표시하려고 합니다.
    
    **ProductCategory[ProductCategory]**를 선택하고 닫는 괄호를 입력합니다.
    
    > [!TIP]
    > 구문 오류는 닫는 괄호가 누락되거나 잘못 배치되어 발생하는 경우가 가장 많습니다. 그러나 잊는 경우에 종종 Power BI Desktop이 이를 추가합니다.
    > 
    > 
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_pfc_3.png)
    
4. 대시 기호를 추가하여 각 값을 구분하려고 하므로 첫 번째 식의 닫는 괄호 뒤에 공백, 앰퍼샌드(&), 따옴표, 공백, 대시(-), 다른 공백, 닫는 따옴표, 다른 앰퍼샌드를 입력합니다. 이제 수식이 다음과 같이 표시됩니다.
    
    **ProductFullCategory = RELATED(ProductCategory[ProductCategory]) & " - " &**
    
    > [!TIP]
    > 수식 입력줄의 오른쪽에 있는 아래쪽 펼침 단추를 클릭해서 수식 편집기를 엽니다. 한 줄 아래로 이동하려면 Alt+Enter를 클릭하고 눌러서 이동합니다.
    > 
    > 
    
5.  끝으로, 다른 왼쪽 괄호를 입력하고 **[ProductSubcategory]** 열을 선택하여 수식을 마칩니다. 수식이 다음과 같이 표시됩니다.
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_pfc_5.png)
    
    ProductSubcategory 열을 호출하는 두 번째 식에서는 다른 RELATED 함수를 사용하지 않았습니다. 새 열을 만들려는 표에 이 열이 이미 있기 때문입니다. 표 이름을 포함(정규화됨)하거나 포함하지 않고(정규화되지 않음) [ProductCategory]를 입력할 수 있습니다.
    
6.  Enter 키를 누르거나 수식 입력줄에 있는 확인 표시를 클릭하여 수식을 완료합니다. 수식의 유효성이 검사되고 **ProductSubcategory** 표의 필드 목록에 추가됩니다.
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_pfc_6.png)
    
    필드 목록에서 계산된 열에는 특수 아이콘이 있습니다. 포함된 수식을 표시합니다. Power BI Desktop에서만 나타납니다. PowerBI 서비스(Power BI 사이트)에서는 수식을 변경할 수 없으므로 계산된 열 필드에는 아이콘이 없습니다.
    
## <a name="lets-add-our-new-column-to-a-report"></a>보고서에 새 열을 추가하겠습니다.
이제 보고서 캔버스에 새로운 ProductFullCategory 열을 추가할 수 있습니다. ProductFullCategory별 SalesAmount를 살펴보겠습니다.

**ProductSubcategory** 표의 **ProductFullCategory** 열을 보고서 캔버스로 끌어 놓고 **Sales** 표의 **SalesAmount** 필드를 차트로 끌어 놓습니다.

![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_report_1.png)

## <a name="lets-create-another"></a>열을 하나 더 만들겠습니다.
이제 계산된 열을 만드는 방법을 배웠으므로 하나 더 만들겠습니다.

Power BI Desktop용 Contoso Sales Sample 모델에는 활성 및 비활성 상점에 대한 판매 데이터가 포함되어 있습니다. 비활성 상점에 대해 표시되는 데이터가 그렇게 식별될 수 있기를 원합니다. 실제로 Active StoreName이라는 필드를 만들려고 합니다. 이 작업을 위해 다른 열을 만들겠습니다. 이 경우 상점이 비활성 상태이면 새로운 Active StoreName 열을 필드로 만들어 상점 이름을 "Inactive"로 표시하지만 활성 상점이면 상점의 실제 이름을 표시하려고 합니다.

Stores 표에는 Status라는 열이 있고, 활성 상점을 나타내는 On 값과 비활성 상점을 나타내는 Off 값을 포함합니다. Status 열에서 각 행의 값을 테스트하여 새 열에 새로운 값을 만들 수 있습니다.

### <a name="to-create-an-active-storename-column"></a>Active StoreName 열을 만들려면
1.  **매장** 표에 **Active StoreName**이라는 새 계산된 열을 만듭니다.
    
    DAX 수식은 이 열에서 각 상점의 상태를 확인합니다. 상점 상태가 On이면 수식이 상점 이름을 반환합니다. Off이면 "Inactive" 이름이 지정됩니다. 이 작업을 위해 논리 [IF](https://msdn.microsoft.com/library/ee634824.aspx) 함수를 사용하여 상점 상태를 테스트하고 결과가 true 또는 false이면 특정 값을 반환합니다.
    
2.  **IF** 입력을 시작합니다. 제안 목록에 추가할 수 있는 항목이 표시됩니다. **IF**를 선택합니다.
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_activestore_1.png)
    
    IF에 대한 첫 번째 인수는 논리 테스트입니다. 상점 상태가 "On"인지 여부를 테스트하려고 합니다.
    
3.  여는 대괄호 **[**를 입력합니다. 그러면 Stores 표에서 열을 선택할 수 있습니다. **[상태]**를 선택합니다.
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_activestore_2.png)
    
4.  **[상태]** 바로 뒤에 **="On"**을 입력한 다음 쉼표(**,**)를 입력하여 두 번째 인수를 입력합니다. 도구 설명에서 결과가 true인 경우에 대한 값을 추가해야 한다고 제안합니다.
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_activestore_3.png)
    
5.  상점이 On이면 상점 이름을 표시하려고 합니다. 여는 대괄호 **[** 를 입력하고 **[StoreName]** 열을 선택한 다음 세 번째 인수를 입력할 수 있도록 다른 쉼표를 입력합니다.
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_activestore_step5.png)
    
6.  결과가 false인 경우에 대한 값이 필요합니다. 이 경우 값을 **“비활성”**으로 설정하려고 합니다.
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_activestore_step6.png)
    
7.  Enter 키를 누르거나 수식 입력줄에 있는 확인 표시를 클릭하여 수식을 완료합니다. 수식의 유효성이 검사되고 Stores 표의 필드 목록에 추가됩니다.
    
    다른 필드와 마찬가지로 새로운 Active StoreName 열을 시각화에 사용할 수 있습니다. 이 차트에서 On 상태의 상점은 이름으로 개별적으로 표시되지만 Off 상태의 상점은 함께 그룹화되어 Inactive로 표시됩니다. 
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_activestore_viz.png)
    
## <a name="what-weve-learned"></a>학습한 내용
계산된 열은 데이터를 보강하고 쉽게 통찰력을 제공할 수 있습니다. 수식 입력줄을 사용하여 계산된 열을 만드는 방법, 제안 목록을 사용하는 방법 및 새 열에 최선의 이름을 지정하는 방법을 배웠습니다.

## <a name="next-steps"></a>다음 단계
DAX 수식을 심층 분석하고 고급 DAX 수식을 사용하여 계산된 열을 만들려는 경우 [Power BI Desktop의 DAX Basics](desktop-quickstart-learn-dax-basics.md)를 참조하세요. 이 문서에서는 구문, 함수 및 컨텍스트에 대한 보다 철저한 이해와 같은 DAX의 기본 개념에 중점을 둡니다.

잊지 말고 [DAX(Data Analysis Expressions) 참조](https://msdn.microsoft.com/library/gg413422.aspx)를 즐겨찾기에 추가하세요. 여기서는 DAX 구문, 연산자 및 200개가 넘는 DAX 함수에 대한 자세한 내용을 확인할 수 있습니다.

