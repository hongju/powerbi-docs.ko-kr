---
title: '자습서:  Power BI Desktop에서 데이터 셰이핑 및 결합'
description: 이 자습서에서는 Power BI Desktop에서 데이터를 셰이핑하고 결합하는 방법을 알아봅니다.
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: tutorial
ms.date: 10/18/2019
ms.author: davidi
LocalizationGroup: Transform and shape data
ms.openlocfilehash: d6a36f8ef3ef5d668fe8d6021758b651cdbf7fd5
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2019
ms.locfileid: "73877814"
---
# <a name="tutorial-shape-and-combine-data-in-power-bi-desktop"></a>자습서:  Power BI Desktop에서 데이터 셰이핑 및 결합

Power BI Desktop을 사용하면 다양한 유형의 데이터 원본에 연결한 다음, 요구 사항에 맞게 데이터를 셰이핑하여 다른 사용자와 공유할 시각적 보고서를 만들 수 있습니다. 데이터 ‘셰이핑’은 열 또는 테이블 이름 바꾸기, 텍스트를 숫자로 변경, 행 제거, 첫 행을 머리글로 설정 등의 데이터 변환을 의미합니다.  데이터 ‘결합’은 둘 이상의 데이터 원본에 연결하고 필요에 따라 셰이핑한 다음, 하나의 유용한 쿼리로 통합하는 것을 의미합니다. 

이 자습서에서는 다음 작업을 수행하는 방법을 알아봅니다.

* 쿼리 편집기를 사용하여 데이터 셰이핑
* 다양한 데이터 원본에 연결
* 데이터 원본을 결합하고 보고서에서 사용할 데이터 모델 만들기

이 자습서에서는 가장 일반적인 작업을 강조해서, Power BI Desktop을 사용하여 쿼리를 셰이핑하는 방법을 설명합니다. 처음부터 직접 쿼리를 만드는 방법을 포함하여 여기에 사용된 쿼리는 [Power BI Desktop 시작](desktop-getting-started.md)에서 자세히 설명합니다.

Power BI Desktop의 쿼리 편집기에서는 오른쪽 클릭 메뉴와 **변환** 리본을 많이 사용합니다. 리본에서 선택할 수 있는 옵션은 대부분 항목(예: 열)을 마우스 오른쪽 단추로 클릭하고 표시되는 메뉴에서 선택하여 사용할 수도 있습니다.

## <a name="shape-data"></a>데이터 모양 지정
쿼리 편집기에서 데이터를 셰이핑하는 경우 쿼리 편집기에서 데이터를 로드하여 표시할 때 데이터 조정을 위해 수행할 단계별 지침을 제공합니다. 원래 데이터 원본은 영향을 받지 않습니다. 이 특정 데이터 보기만 조정되거나 ‘셰이핑’됩니다. 

지정한 단계(테이블 이름 바꾸기, 데이터 형식 변환, 열 삭제 등)는 쿼리 편집기에서 기록됩니다. 이 쿼리가 데이터 원본에 연결될 때마다 쿼리 편집기에서 해당 단계를 수행하여 데이터가 항상 지정된 방식으로 셰이핑되도록 합니다. 이 프로세스는 쿼리 편집기를 사용할 때마다 또는 Power BI 서비스 등에서 공유 쿼리를 사용하는 모든 사용자에 대해 수행됩니다. 이러한 단계는 **쿼리 설정** 창의 **적용된 단계** 아래에 순차적으로 캡처됩니다. 다음 몇 개의 단락에서 각 단계를 살펴봅니다.

![쿼리 설정의 적용된 단계](media/desktop-shape-and-combine-data/shapecombine_querysettingsfinished2.png)

[Power BI Desktop 시작](desktop-getting-started.md)에서 웹 데이터 원본에 연결하여 찾은 은퇴 데이터를 사용하여 요구 사항에 맞게 데이터를 셰이핑합시다. 사용자 지정 열을 추가하여 모든 데이터가 같은 요소라는 것을 전제로 순위를 계산하고 이 열을 기존 열인 **Rank**와 비교하겠습니다.  

1. **열 추가** 리본에서 사용자 지정 열을 추가할 수 있는 **사용자 지정 열**을 선택합니다.

    ![사용자 지정 열 선택](media/desktop-shape-and-combine-data/shapecombine_customcolumn.png)

1. **사용자 지정 열** 창의 **새 열 이름**에 ‘New Rank’를 입력합니다.  **사용자 지정 열 수식**에 다음 데이터를 입력합니다.

    ```
    ([Cost of living] + [Weather] + [Health care quality] + [Crime] + [Tax] + [Culture] + [Senior] + [#"Well-being"]) / 8
    ```
 
1. 상태 메시지가 ‘구문 오류가 검색되지 않았습니다.’인지 확인하고 **확인**을 선택합니다. 

    ![구문 오류가 없는 사용자 지정 열 페이지](media/desktop-shape-and-combine-data/shapecombine_customcolumndialog.png)

1. 열 데이터를 일관성 있게 유지하려면 새 열 값을 정수로 변환합니다. 변경하려면 열 머리글을 마우스 오른쪽 단추로 클릭하고 **형식 변경 \> 정수**를 선택합니다. 

    둘 이상의 열을 선택해야 하는 경우, 열을 하나 선택하고 **Shift** 키를 누른 채 인접한 열을 추가로 선택한 다음, 열 머리글을 마우스 오른쪽 단추로 클릭합니다. **Ctrl** 키를 사용하여 인접하지 않은 열을 선택할 수도 있습니다.

    ![정수 열 데이터 선택](media/desktop-shape-and-combine-data/shapecombine_changetype2.png)

1. 열 데이터 형식을 현재 데이터 형식에서 다른 데이터 형식으로 ‘변환’하려면 **변환** 리본에서 **데이터 형식 텍스트**를 선택합니다.  

   ![데이터 형식 텍스트 선택](media/desktop-shape-and-combine-data/queryoverview_transformribbonarrow.png)

1. **쿼리 설정**의 **적용된 단계**는 데이터에 적용된 셰이핑 단계를 반영합니다. 셰이핑 프로세스에서 단계를 제거하려면 단계 왼쪽에 있는 **X**를 선택합니다. 

    다음 이미지에서 **적용된 단계** 목록에는 지금까지 추가한 단계가 반영되어 있습니다. 
     - **원본**: 웹 사이트에 연결합니다.
     - **탐색**: 테이블을 선택합니다. 
     - **변경된 형식**: 텍스트 기반 숫자 열을 *‘텍스트’* 에서 ‘*정수*’로 변경합니다. 
     - **사용자 지정 추가됨**: 사용자 지정 열을 추가합니다.
     - **변경된 형식1**: 마지막 적용된 단계입니다.

       ![적용된 단계 목록](media/desktop-shape-and-combine-data/shapecombine_appliedstepsearly2.png)

## <a name="adjust-data"></a>데이터 조정

이 쿼리를 사용하려면 먼저 다음과 같은 몇 가지 변경 작업을 수행하여 데이터를 조정해야 합니다.

   - 열을 제거하여 순위를 조정합니다.

       **Cost of living**은 결과의 요소가 아니라고 결정했습니다. 이 열을 제거해도 데이터가 변경되지 않습니다. 

   - 몇 가지 오류를 수정합니다.

       열을 제거했기 때문에 **New Rank** 열의 계산을 다시 조정해야 하며, 수식 변경이 포함됩니다.

   - 데이터를 정렬합니다.

       **New Rank** 및 **Rank** 열을 기준으로 데이터를 정렬합니다.
 
   - 데이터를 바꿉니다.

       특정 값을 바꾸는 방법 및 **적용된 단계**의 삽입 필요성을 강조해서 설명합니다.

   - 테이블 이름을 변경합니다. 

       **테이블 0**은 테이블에 유용한 설명자가 아니므로 테이블 이름을 변경합니다.

1. **Cost of living** 열을 제거하려면 열을 선택하고 리본에서 **홈** 탭을 선택한 다음, **열 제거**를 선택합니다.

    ![열 제거 선택](media/desktop-shape-and-combine-data/shapecombine_removecolumnscostofliving.png)

   단계의 순서 때문에 **New Rank** 값은 변경되지 않았습니다. 쿼리 편집기에서 단계를 순차적이지만 서로 독립적이므로 기록하기 때문에 각 **적용된 단계**를 시퀀스에서 위나 아래로 이동할 수 있습니다. 

1. 단계를 마우스 오른쪽 단추로 클릭합니다. 쿼리 편집기에서 다음 작업을 수행할 수 있는 메뉴를 제공합니다. 
   - **이름 바꾸기**: 단계의 이름을 바꿉니다.
   - **삭제**: 단계를 삭제합니다.
   - **끝까지** **삭제**: 현재 단계와 모든 후속 단계를 제거합니다.
   - **위로 이동**: 목록에서 단계를 위로 이동합니다.
   - **아래로 이동**: 목록에서 단계를 아래로 이동합니다.

1. 마지막 단계인 **열 제거됨**을 **사용자 지정 추가됨** 단계 바로 위로 이동합니다.

   ![적용된 단계에서 단계를 위로 이동](media/desktop-shape-and-combine-data/shapecombine_movestep.png)

1. **사용자 지정 추가됨** 단계를 선택합니다. 

   이제 데이터에 ‘오류’가 표시되며, 오류를 수정해야 합니다. 

   ![열 데이터의 오류 결과](media/desktop-shape-and-combine-data/shapecombine_error2.png)

   각 오류에 대한 자세한 내용을 확인할 수 있는 몇 가지 방법이 있습니다. ‘오류’ 단어를 클릭하지 않고 셀을 선택하면, 쿼리 편집기에서 창의 맨 아래에 오류 정보가 표시됩니다. 

   ![쿼리 편집기의 오류 정보](media/desktop-shape-and-combine-data/shapecombine_errorinfo2.png)

   ‘오류’ 단어를 직접 선택하면, 쿼리 편집기는 **쿼리 설정** 창에 **적용된 단계**를 만들고 오류 정보를 표시합니다.  

1. 여기서는 오류 정보를 표시할 필요가 없으므로 **취소**를 선택합니다.

1. 오류를 수정하려면 **New Rank** 열을 선택한 다음, **보기** 탭에서 **수식 입력줄** 확인란을 선택하여 열의 데이터 수식을 표시합니다. 

   ![수식 입력줄 선택](media/desktop-shape-and-combine-data/shapecombine_formulabar.png)

1. ‘Cost of living’ 매개 변수를 제거하고 수식을 다음과 같이 변경하여 제수를 줄입니다.  
   ```
    Table.AddColumn(#"Removed Columns", "New Rank", each ([Weather] + [Health care quality] + [Crime] + [Tax] + [Culture] + [Senior] + [#"Well-being"]) / 7)
   ```

1. 수식 상자 왼쪽에 있는 녹색 확인 표시를 선택하거나 **Enter** 키를 누릅니다.

  쿼리 편집기에서 데이터를 수정된 값으로 바꾸고, **사용자 지정 추가됨** 단계가 오류 없이 완료됩니다.

   > [!NOTE]
   > 리본이나 오른쪽 클릭 메뉴를 사용하여 오류가 있는 행을 모두 제거하는 **오류 제거**를 선택할 수도 있습니다. 그러나 이 자습서에서는 테이블의 데이터를 유지하려고 하므로 이 옵션을 선택하지 않았습니다.

1. **New Rank** 열을 기준으로 데이터를 정렬합니다. 먼저 마지막 적용된 단계인 **변경된 형식1**을 선택하여 가장 최근 데이터에 액세스합니다. 그런 다음, **New Rank** 열 머리글 옆에 있는 드롭다운을 선택하고 **오름차순 정렬**을 선택합니다.

   ![New Rank 열의 데이터 정렬](media/desktop-shape-and-combine-data/shapecombine_sort.png)

   이제 데이터가 **New Rank**에 따라 정렬되었습니다. 그러나 **Rank** 열을 확인하면 **New Rank** 값이 동률인 경우 데이터가 제대로 정렬되지 않음을 알 수 있습니다. 다음 단계에서 이 문제를 해결하겠습니다.

1. 데이터 정렬 문제를 해결하려면 **New Rank** 열을 선택하고 **수식 입력줄**의 수식을 다음 수식으로 변경합니다.

   ```
    = Table.Sort(#"Changed Type1",{{"New Rank", Order.Ascending},{"Rank", Order.Ascending}})
   ```

1. 수식 상자 왼쪽에 있는 녹색 확인 표시를 선택하거나 **Enter** 키를 누릅니다. 

   이제 **New Rank**와 **Rank** 둘 다에 따라 행이 정렬되었습니다. 또한 목록에서 **적용된 단계** 를 선택하고 시퀀스의 해당 지점에서 데이터 셰이핑을 계속할 수 있습니다. 쿼리 편집기가 현재 선택한 **적용된 단계** 바로 뒤에 새 단계를 자동으로 삽입합니다. 

1. **적용된 단계**에서 사용자 지정 열 앞에 있는 단계(**열 제거** 단계)를 선택합니다. 여기서는 Arizona의 **Weather** 순위 값을 바꾸겠습니다. Arizona의 **Weather** 순위가 포함된 셀을 마우스 오른쪽 단추로 클릭하고 **값 바꾸기**를 선택합니다. 현재 선택된 **적용된 단계**를 확인합니다.

   ![열의 값 바꾸기 선택](media/desktop-shape-and-combine-data/shapecombine_replacevalues2.png)

1. **삽입**을 선택합니다.

    단계를 삽입하기 때문에 쿼리 편집기에서 계속할 경우 후속 단계로 인해 쿼리가 중단될 수 있다고 경고합니다. 

    ![단계 삽입 확인](media/desktop-shape-and-combine-data/shapecombine_insertstep.png)

1. 데이터 값을 _51_로 변경합니다. 

   쿼리 편집기에서 Arizona의 데이터를 바꿉니다. 새 **적용된 단계**를 만들 때 쿼리 편집기는 작업에 따라 단계 이름을 지정합니다(이 예제에서는 **값 바뀜**). 쿼리에 동일한 이름을 가진 단계가 둘 이상 있을 경우 쿼리 편집기에서 각 후속 **적용된 단계**에 번호를 순서대로 추가하여 구분합니다.

1. 마지막 **적용된 단계**인 **행 정렬됨**을 선택합니다. 

   Arizona의 새 순위와 관련해서 데이터가 변경된 것을 확인합니다. 이 순위 변경은 **사용자 지정 추가됨** 단계 앞의 올바른 위치에 **값 바뀜** 단계를 삽입했기 때문입니다.

1. 마지막으로, 해당 테이블의 이름을 설명이 포함된 다른 이름으로 변경하려고 합니다. **쿼리 설정** 창의 **속성** 아래에 테이블의 새 이름을 입력하고 **입력**을 선택합니다. 이 테이블의 이름을 *RetirementStats*로 지정합니다.

   ![쿼리 설정의 테이블 이름 바꾸기](media/desktop-shape-and-combine-data/shapecombine_renametable2.png)

   보고서를 만들 때, 특히 여러 데이터 원본에 연결하는 경우 설명이 포함된 테이블 이름이 있으면 도움이 되며, 테이블 이름은 **보고서** 보기의 **필드** 창에 나열됩니다.

   이제 필요한 범위까지 데이터를 셰이핑했습니다. 이제 다른 데이터 소스에 연결하고 데이터를 결합하겠습니다.

## <a name="combine-data"></a>데이터 결합
다양한 주와 관련된 데이터는 흥미로우며, 추가적인 분석 활동과 쿼리 작성에 유용합니다. 그러나 한 가지 문제가 있습니다. 대부분의 데이터는 주의 전체 이름이 아니라 주 코드를 나타내는 2자로 된 약어를 사용합니다. 주 이름을 해당 약어에 연결하는 방법이 필요합니다.

다행히 이 작업을 수행하는 다른 공용 데이터 원본이 있지만 은퇴 테이블에 연결하려면 상당한 셰이핑 작업이 필요합니다. 데이터를 셰이핑하려면 다음 단계를 수행합니다.

1. 쿼리 편집기의 **홈** 리본에서 **새 원본 \> 웹**을 선택합니다. 

2. 주 약어의 웹 사이트 주소( *https://en.wikipedia.org/wiki/List_of_U.S._state_abbreviations* )를 입력하고 **연결**을 선택합니다.

   탐색기에 웹 사이트의 콘텐츠가 표시됩니다.

    ![탐색기 페이지](media/desktop-shape-and-combine-data/designer_gsg_usstateabbreviationsnavigator2.png)

1. **코드 및 약어**를 선택합니다. 

   > [!TIP]
   > 이 테이블의 데이터를 원하는 항목으로 줄이려면 상당한 셰이핑이 필요합니다. 아래 단계를 수행하는 더 빠르거나 쉬운 방법이 있나요? 예, 두 테이블 간의 관계를 만들고 해당 관계를 기반으로 데이터의 모양을 지정할 수 있습니다.  다음 단계도 테이블 작업 방법을 배우는 데 유용하지만, 관계를 통해 여러 테이블의 데이터를 빠르게 사용할 수 있습니다.
> 
> 

데이터를 셰이핑하려면 다음 단계를 수행합니다.

1. 상위 행을 제거합니다. 상위 행은 웹 페이지의 테이블을 만든 방식의 결과이므로 필요하지 않습니다. **홈** 리본에서 **행 감소 \>행 제거 \>상위 행 제거**를 선택합니다.

    ![상위 행 제거 선택](media/desktop-shape-and-combine-data/shapecombine_removetoprows.png)

    제거할 행 수를 지정할 수 있는 **상위 행 제거** 창이 나타납니다.

    > [!NOTE]
    > 실수로 Power BI에서 테이블 머리글을 데이터 테이블의 행으로 가져오는 경우 리본 메뉴의 **홈** 탭이나 **변환** 탭에서 **첫 행을 머리글로 사용**을 선택할 수 있습니다.

1. 하위 26개 행을 제거합니다. 해당 행은 포함할 필요가 없는 미국 지역입니다. **홈** 리본에서 **행 감소 \> 행 제거 \>하위 행 제거**를 선택합니다.

    ![하위 행 제거 선택](media/desktop-shape-and-combine-data/shapecombine_removebottomrows.png)

1. RetirementStats 테이블에는 워싱턴 DC 정보가 없으므로 목록에서 필터링해야 합니다. **영역 상태** 드롭다운을 선택하고 **연방 구역** 옆에 있는 확인란의 선택을 취소합니다.

    ![연방 구역 확인란 선택 취소](media/desktop-shape-and-combine-data/shapecombine_filterdc.png)

1. 몇 개의 불필요한 열을 제거합니다. 각 주와 2자로 된 공식 약어 간의 매핑만 필요하므로 **Column1**, **Column3**, **Column4**, **Column6**~**Column11** 열을 제거할 수 있습니다. 먼저 **Column1**을 선택하고 **Ctrl** 키를 누른 채 제거할 다른 열을 각각 선택합니다. 리본의 **홈** 탭에서 **열 제거 \> 열 제거**를 선택합니다.

   ![열 제거](media/desktop-shape-and-combine-data/shapecombine_removecolumns.png)

   > [!NOTE]
   > 이 시점에서 쿼리 편집기에서 적용된 단계의 *시퀀스*가 중요하며 데이터의 셰이핑 방식에 영향을 줄 수 있음에 주목하는 것이 좋습니다. 또한 한 단계가 다른 후속 단계에 미칠 수 있는 영향을 고려하는 것이 중요합니다. 적용된 단계에서 한 단계를 제거하면 쿼리의 단계 시퀀스 영향 때문에 후속 단계가 의도한 대로 동작하지 않을 수 있습니다.

   > [!NOTE]
   > 너비를 줄이기 위해 쿼리 편집기 창의 크기를 조정할 때 보이는 공간을 최대한 활용하기 위해 일부 리본 항목이 압축됩니다. 쿼리 편집기 창의 너비를 늘리면 늘어난 리본 영역을 최대한 활용하기 위해 리본 항목이 확장됩니다.

1. 열과 테이블의 이름을 바꿉니다. 열 이름을 바꾸는 방법에는 여러 가지가 있습니다. 열을 선택하고 리본의 **변환** 탭에서 **이름 바꾸기**를 선택하거나, 마우스 오른쪽 단추를 클릭하고 **이름 바꾸기**를 선택합니다. 다음 그림에는 두 옵션을 가리키는 화살표가 있습니다. 하나만 선택해야 합니다.

   ![쿼리 편집기에서 열 이름 바꾸기](media/desktop-shape-and-combine-data/shapecombine_rename.png)

1. 열 이름을 *State Name* 및 *State Code*로 바꿉니다. 테이블 이름을 바꾸려면 **쿼리 설정** 창에서 **이름**을 입력합니다. 이 테이블의 이름을 *StateCodes*로 지정합니다.

## <a name="combine-queries"></a>쿼리 결합

이제 StateCodes 테이블을 원하는 방식으로 셰이핑했으므로 두 개의 테이블 또는 쿼리를 하나로 결합합시다. 현재 테이블은 데이터에 적용한 쿼리의 결과이기 때문에 ‘쿼리’라고도 합니다. 

쿼리를 결합하는 두 가지 주요 방법은 ‘병합’과 ‘추가’입니다.  

- 다른 쿼리에 추가하려는 열이 하나 이상 있는 경우 쿼리를 *병합*합니다. 
- 기존 쿼리에 추가하려는 데이터 행이 더 있는 경우 쿼리를 *추가*합니다.

이 예제에서는 쿼리를 병합하려고 합니다. 이 작업을 수행하려면 다음 단계를 따릅니다.
 
1. 쿼리 편집기의 왼쪽 창에서 다른 쿼리를 병합하려는 쿼리를 선택합니다.  이 예제에서는 **RetirementStats**입니다. 

1. 리본의 **홈** 탭에서 **결합 \> 쿼리 병합**을 선택합니다.

   ![쿼리 병합 선택](media/desktop-shape-and-combine-data/shapecombine_mergequeries.png)

   전송하지 않으려는 데이터를 포함하거나 전송하지 않고 데이터가 결합되도록 개인 정보 수준을 설정하라는 메시지가 표시될 수 있습니다.

   **병합** 창이 나타납니다. 선택한 테이블에 병합하려는 테이블 및 병합에 사용할 일치 열을 선택하라는 메시지가 표시됩니다. 

1. RetirementStats 테이블에서 **State**를 선택한 다음, **StateCodes** 쿼리를 선택합니다. 

   올바른 일치 열을 선택하면 **확인** 단추가 활성화됩니다.

   ![병합 창](media/desktop-shape-and-combine-data/shapecombine_merge2.png)

1. **확인**을 선택합니다.

   쿼리 편집기는 기존 쿼리와 병합된 테이블(쿼리)의 내용을 포함하는 **NewColumn** 열을 쿼리의 끝에 만듭니다. 병합된 쿼리의 모든 열이 **NewColumn** 열에 압축되지만, 테이블을 **확장**하고 원하는 열을 모두 포함할 수 있습니다.

   ![NewColumn 열](media/desktop-shape-and-combine-data/shapecombine_mergenewcolumn.png)

1. 병합된 테이블을 확장하고 포함할 열을 선택하려면 확장 아이콘(![확장 아이콘](media/desktop-shape-and-combine-data/icon.png))을 선택합니다. 

   **확장** 창이 나타납니다.

   ![쿼리의 NewColumn](media/desktop-shape-and-combine-data/shapecombine_mergeexpand.png)

1. 이 예제에서는 **State Code** 열만 필요합니다. 해당 열을 선택하고 **원래 열 이름을 접두사로 사용**의 선택을 취소한 다음, **확인**을 선택합니다.

   **원래 열 이름을 접두사로 사용** 확인란을 선택된 상태로 두면, 병합된 열의 이름은 **NewColumn.State Code**가 됩니다.

   > [!NOTE]
   > NewColumn 테이블에 가져오는 방법을 알아보고 싶으세요? 몇 가지를 실험한 후 결과가 만족스럽지 않으면 **쿼리 설정** 창의 **적용된 단계** 목록에서 해당 단계를 삭제합니다. 쿼리가 해당 **확장** 단계를 적용하기 전의 상태로 돌아갑니다. 확장 프로세스가 원하는 방식으로 표시될 때까지 원하는 횟수만큼 이 작업을 수행할 수 있습니다.

   이제 각각 요구 사항에 맞게 셰이핑된 두 개의 데이터 원본을 결합하는 단일 쿼리(테이블)가 생성되었습니다. 이 쿼리는 임의 주의 주택 비용 통계, 인구 통계 또는 구직 기회와 같은 흥미로운 여러 추가 데이터 연결의 기초로 사용할 수 있습니다.

1. 변경 내용을 적용하고 쿼리 편집기를 닫으려면 **홈** 리본 탭에서 **닫기 및 적용**을 선택합니다. 

   변환된 데이터 세트는 Power BI Desktop에 표시되고 보고서를 만드는 데 사용할 준비가 되었습니다.

   ![닫기 및 적용 선택](media/desktop-shape-and-combine-data/shapecombine_closeandapply.png)

## <a name="next-steps"></a>다음 단계
Power BI Desktop 및 해당 기능에 대한 자세한 내용은 다음 리소스를 참조하세요.

* [Power BI Desktop이란?](desktop-what-is-desktop.md)
* [Power BI Desktop을 사용한 쿼리 개요](desktop-query-overview.md)
* [Power BI Desktop의 데이터 원본](desktop-data-sources.md)
* [Power BI Desktop에서 데이터에 연결](desktop-connect-to-data.md)
* [Power BI Desktop의 일반적인 쿼리 작업](desktop-common-query-tasks.md)   

