---
title: 일반적이고 강력한 계산에 빠른 측정 사용
description: 빠른 측정은 일반적인 계산을 신속하게 수행할 수 있도록 미리 만들어진 DAX 수식을 제공합니다.
author: davidiseminger
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 11/22/2019
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 4e5ea5e5fcbffb5c61434ecc26a90d80d1cd1736
ms.sourcegitcommit: 8e3d53cf971853c32eff4531d2d3cdb725a199af
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "74415326"
---
# <a name="use-quick-measures-for-common-calculations"></a>일반적인 계산에 빠른 측정 사용
*‘빠른 측정’* 을 사용하여 일반적이고 강력한 계산을 쉽고 빠르게 수행할 수 있습니다. 빠른 측정은 백그라운드에서 DAX(Data Analysis Expressions) 명령 집합을 실행한 후 결과를 표시하여 보고서에서 사용할 수 있습니다. DAX를 작성할 필요가 없으며, 대화 상자에서 제공하는 입력에 따라 자동으로 작성됩니다. 사용 가능한 수많은 계산 범주와 사용자 요구에 맞게 각 계산을 수정할 방법이 있습니다. 무엇보다도 빠른 측정에서 실행되는 DAX를 확인하고 바로 시작하거나 고유한 DAX 지식을 확장할 수 있습니다.

## <a name="create-a-quick-measure"></a>빠른 측정 만들기

Power BI Desktop에서 빠른 측정을 만들려면 **필드** 창에서 마우스 오른쪽 단추를 클릭하거나 특정 항목 옆의 줄임표(**...**)를 선택하고 메뉴가 나타나면 **새 빠른 측정**을 선택합니다. 

![새 빠른 측정 선택](media/desktop-quick-measures/quick-measures_01.png)

기존 시각적 개체인 경우 **값**에서 마우스 오른쪽 단추를 클릭하거나 특정 값 옆의 드롭다운 화살표를 선택하고 메뉴에서 **새 빠른 측정**을 선택합니다. 

**새 빠른 측정**을 선택하면 **빠른 측정** 창이 표시되어 원하는 계산과 계산을 실행할 필드를 선택할 수 있습니다. 

**계산 선택** 필드를 선택하여 사용 가능한 빠른 측정의 긴 목록을 확인합니다. 

![사용 가능한 빠른 측정 계산](media/desktop-quick-measures/quick-measures_04.png)

다음은 5가지 빠른 측정 계산 유형과 관련 계산입니다.

* **범주별 집계**
  * 범주별 평균
  * 범주별 차이
  * 범주별 최댓값
  * 범주별 최솟값
  * 범주에 따른 가중 평균
* **필터**
  * 필터링된 값
  * 필터링된 값과의 차이
  * 필터링된 값과의 백분율 차이
  * 신규 고객의 판매량
* **시간 인텔리전스**
  * 연초 대비 합계
  * 분기초 대비 합계
  * 월초 대비 합계
  * 전년도 대비 변화
  * 전분기 대비 변화
  * 전월 대비 변화
  * 이동 평균
* **합계**
  * 누계
  * 범주에 대한 합계(필터 적용)
  * 범주에 대한 합계(필터 적용하지 않음)
* **수학 연산**
  * 더하기
  * 빼기
  * 곱하기
  * 나누기
  * 백분율 차이
  * 상관 계수
* **텍스트**
  * 별 등급
  * 연결된 값 목록

확인하려는 새 빠른 측정, 기본 DAX 수식 또는 고려해야 할 기타 빠른 측정에 대한 아이디어를 제출하려면 이 문서의 끈 부분을 참조하세요.

> [!NOTE]
> SSAS(SQL Server Analysis Services) 라이브 연결을 사용하는 경우 일부 빠른 측정을 사용할 수 있습니다. Power BI Desktop은 연결되어 있는 SSAS 버전에서 지원되는 빠른 측정만 표시합니다. SSAS 라이브 데이터 원본에 연결되어 있는 경우 목록에 특정 빠른 측정이 표시되지 않으면 연결된 SSAS 버전이 빠른 측정을 구현하는 데 사용된 DAX 명령을 지원하지 않기 때문입니다.

빠른 측정에 사용할 계산 및 필드를 선택한 후 **확인**을 선택합니다. 새 빠른 측정이 **필드** 창에 표시되고 기본 DAX 수식이 수식 입력줄에 표시됩니다. 

## <a name="quick-measure-example"></a>빠른 측정 예제
실제 빠른 측정 작업을 살펴보겠습니다.

다음 행렬 시각적 개체는 다양한 제품에 대한 판매 테이블을 보여 줍니다. 각 범주에 대한 판매 합계가 포함된 기본 테이블입니다.

![판매 테이블을 보여 주는 행렬 시각적 개체](media/desktop-quick-measures/quick-measures_05.png)

행렬 시각적 개체를 선택한 상태에서 **값**의 **TotalSales** 옆에 있는 드롭다운 화살표를 선택한 다음, **새 빠른 측정**을 선택합니다. 

**빠른 측정** 창의 **계산**에서 **범주별 평균**을 선택합니다. 

**필드** 창에서 **평균 단가**를 **기준 값** 필드로 끌어옵니다. **범주** 필드에 **범주**를 그대로 두고 **확인**을 선택합니다. 

![](media/desktop-quick-measures/quick-measures_06.png)

**확인**을 선택하면 몇 가지 흥미로운 현상이 발생합니다.

![시각적 개체, 수식 입력줄 및 필드 목록의 새 빠른 측정](media/desktop-quick-measures/quick-measures_07.png)

1. 행렬 시각적 개체에 계산된 **평균 단가 범주별 평균**을 보여 주는 새 열이 있습니다.
   
2. 새 빠른 측정에 대한 DAX 수식이 수식 입력줄에 표시됩니다. DAX 수식에 대한 자세한 내용은 [다음 섹션](#learn-dax-by-using-quick-measures)을 참조하세요.
   
3. 새 빠른 측정이 선택되어 강조 표시된 상태로 **필드** 창에 표시됩니다. 

새 빠른 측정은 보고서를 만든 시각적 개체뿐만 아니라 보고서의 모든 시각적 개체에 사용할 수 있습니다. 다음 이미지에서는 새 빠른 측정 필드를 사용하여 만든 빠른 세로 막대형 차트 시각적 개체를 보여 줍니다.

![빠른 측정 필드를 기반으로 하는 새 가로 막대형 차트 시각적 개체](media/desktop-quick-measures/quick-measures_09.png)

## <a name="learn-dax-by-using-quick-measures"></a>빠른 측정을 사용하여 DAX 학습
빠른 측정의 가장 큰 장점은 측정값을 구현하는 DAX 수식을 보여 준다는 점입니다. **필드** 창에서 빠른 측정을 선택하면 **수식 입력줄**이 나타나 Power BI에서 측정값을 구현하기 위해 만든 DAX 수식을 보여 줍니다.

![수식 입력줄의 빠른 측정 수식](media/desktop-quick-measures/quick-measures_10.png)

수식 입력줄은 측정값의 수식을 표시할 뿐만 아니라 더욱 중요하게는 빠른 측정의 기반이 되는 DAX 수식을 만드는 방법도 보여 줍니다.

연도별 계산을 수행해야 하는데 DAX 수식을 구조화하는 방법을 확실히 모르거나 어디서 시작해야 할지 모른다고 가정해 보겠습니다. 책상에서 고민하는 대신 **전년도 대비 변화** 계산을 사용하여 빠른 측정을 만들고 시각적 개체에 어떻게 표시되는지와 DAX 수식의 작동 방식을 확인할 수 있습니다. 그런 다음, DAX 수식을 직접 변경하거나 요구 사항과 기대에 맞는 유사한 측정값을 만들 수 있습니다. 클릭 몇 번으로 가정(what-if) 질문에 즉시 응답해 주는 선생님이 있는 것과 같습니다. 

원하지 않는 경우 언제든지 모델에서 빠른 측정을 삭제할 수 있습니다. 이는 마우스 오른쪽 단추를 클릭하거나 측정값 옆의 **...** 를 선택하고 **삭제**를 선택하는 것만큼 쉽습니다. 또한 메뉴에서 **이름 바꾸기**를 선택하여 원하는 대로 빠른 측정의 이름을 바꿀 수 있습니다. 

![빠른 측정 삭제 또는 이름 바꾸기](media/desktop-quick-measures/quick-measures_11.png)

## <a name="limitations-and-considerations"></a>제한 사항 및 고려 사항
유념해야 할 몇 가지 제한 사항과 고려 사항이 있습니다.

- **필드** 창에 추가한 빠른 측정을 보고서의 시각적 개체에서 사용할 수 있습니다.
- **필드** 목록에서 측정값을 선택하고 수식 입력줄에서 수식을 확인하여 빠른 측정과 연결된 DAX를 언제든지 확인할 수 있습니다.
- 빠른 측정은 모델을 수정할 수 있는 경우에만 사용할 수 있습니다. 일부 라이브 연결로 작업하는 경우는 그렇지 않습니다. 앞에서 설명한 대로 SSAS 테이블 형식 라이브 연결은 지원됩니다.
- DirectQuery 모드에서 작업할 때는 시간 인텔리전스 빠른 측정를 빠르게 만들 수 없습니다. 이러한 빠른 측정에 사용되는 DAX 함수는 데이터 원본으로 보내지는 T-SQL 문으로 변환될 때 성능에 영향을 미칩니다.

> [!IMPORTANT]
> 빠른 측정에 대한 DAX 문은 인수 구분 기호에 쉼표만 사용합니다. Power BI Desktop이 쉼표를 소수 구분 기호로 사용하는 언어 버전인 경우 빠른 측정이 올바르게 작동하지 않습니다.

### <a name="time-intelligence-and-quick-measures"></a>시간 인텔리전스 및 빠른 측정
시간 인텔리전스 빠른 측정에서 고유한 사용자 지정 날짜 테이블을 사용할 수 있습니다. 외부 테이블 형식 모델을 사용하는 경우에는 [시간 인텔리전스에 사용할 날짜 테이블로 표시 지정](https://docs.microsoft.com/sql/analysis-services/tabular-models/specify-mark-as-date-table-for-use-with-time-intelligence-ssas-tabular)에 설명된 대로 모델을 작성할 때 테이블의 기본 날짜 열이 날짜 테이블로 표시되었는지 확인해야 합니다. 고유한 날짜 테이블을 가져오는 경우에는 [Set and use date tables in Power BI Desktop](desktop-date-tables.md)(Power BI Desktop에서 날짜 테이블 설정 및 사용)에 설명된 대로 날짜 테이블로 표시해야 합니다.

### <a name="additional-information-and-examples"></a>추가 정보 및 예제
아직 제공되지 않은 빠른 측정에 대한 아이디어가 있으신가요? 좋습니다! [Power BI Ideas](https://go.microsoft.com/fwlink/?linkid=842906)(Power BI 아이디어) 페이지를 확인하고 Power BI Desktop에 표시되었으면 하는 빠른 측정에 대한 아이디어 및 DAX 수식을 제출해 주세요. 향후 릴리스에서 빠른 측정 목록에 추가되도록 노력하겠습니다.

