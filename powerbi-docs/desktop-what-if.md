---
title: 가상 매개 변수를 사용하여 변수 시각화
description: 고유한 가상 변수를 만들어서 Power BI 보고서에서 변수 구상 및 시각화
author: davidiseminger
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/21/2020
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 8a72bc43bcceae6e676728934ceec81c8cb27d04
ms.sourcegitcommit: 02342150eeab52b13a37b7725900eaf84de912bc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2020
ms.locfileid: "76539434"
---
# <a name="create-and-use-what-if-parameters-to-visualize-variables-in-power-bi-desktop"></a>What if 매개 변수를 만들고 이러한 매개 변수를 사용하여 Power BI Desktop에서 변수 시각화

*Power BI Desktop* 2018년 8월 릴리스에서부터는 보고서에 대한 *가상* 변수를 만들고, 슬라이서인 변수와 상호 작용하고, 보고서에서 다른 키 값을 시각화하고 수치화할 수 있습니다.

![새 매개 변수 옵션](media/desktop-what-if/what-if_01.png)

Power BI Desktop의 **모델링** 탭에서 ‘가상’ 매개 변수를 만듭니다.  이 탭을 선택하면 매개 변수를 구성할 수 있는 대화 상자가 나타납니다.

## <a name="creating-a-what-if-parameter"></a>가상 매개 변수 만들기

가상 매개 변수를 만들려면 Power BI Desktop의 **모델링** 탭에서 **새 매개 변수**를 선택합니다. 다음 이미지에서는 *할인율*이라는 매개 변수를 만들고 **10진수**로 해당 데이터 형식을 설정했습니다. **최솟**값은 0입니다. **최대**값은 0.50(50%)입니다. 또한 **증가**를 0.05 또는 5%로 설정했습니다. 보고서에서 상호 작용할 때 매개 변수를 조정하는 정도입니다.

![가상 매개 변수 값](media/desktop-what-if/what-if_02.png)

> [!NOTE]
> 10진수의 경우 .50이 아니라 0.50과 같이 값 앞에 0을 사용하도록 합니다. 그렇지 않으면 숫자의 유효성을 검사할 수 없고 **확인** 단추를 선택할 수 없습니다.
> 
> 

편의상 **이 페이지에 슬라이서 추가** 확인란은 현재 보고서 페이지에 가상 매개 변수를 포함한 슬라이서를 자동으로 배치합니다.

![현재 보고서 페이지의 새 슬라이서](media/desktop-what-if/what-if_03.png)

매개 변수를 만들 뿐만 아니라 가상 매개 변수를 만드는 작업은 가상 매개 변수의 현재 값을 시각화하는 데 사용할 수 있는 측정값을 만듭니다.

![가상 매개 변수에 대해 만들어진 측정값](media/desktop-what-if/what-if_04.png)

가상 매개 변수를 만들면 매개 변수 및 측정값은 모두 모델의 일부가 된다는 점에 유의해야 합니다. 따라서 보고서 전체에서 사용 가능하고 다른 보고서 페이지에서 사용할 수 있습니다. 모델의 일부이기 때문에 보고서 페이지에서 슬라이서를 삭제할 수 있습니다. 슬라이서를 다시 원하는 경우 **필드** 목록에서 가상 매개 변수를 잡고 캔버스로 끌어온 다음 시각적 개체를 슬라이서로 변경하세요.

## <a name="using-a-what-if-parameter"></a>가상 매개 변수 사용

가상 매개 변수를 사용하는 간단한 예제를 만들어 보겠습니다. 이전 섹션에서 가상 매개 변수를 만들었습니다. 이제 슬라이더로 값을 조정하는 새 측정값을 만들어 사용할 수 있습니다.

![매개 변수와 함께 사용할 새 측정값을 추가합니다.](media/desktop-what-if/what-if_05.png)

새 측정값은 단순히 할인율이 적용된 총 판매액입니다. 물론 복잡하고 흥미로운 측정값을 만들어서 보고서의 고객이 가상 매개 변수의 변수를 시각화할 수 있습니다. 예를 들어, 영업 사원이 특정 판매 목표 또는 백분율을 달성하는 경우 자신의 인센티브를 확인하거나 대폭 할인으로 판매가 증가한 효과를 확인할 수 있도록 보고서를 만들 수 있습니다.

수식 입력줄에 측정값 수식을 입력하고, 수식 이름을 *할인 후 판매액*으로 지정합니다.

![할인 이후 판매액 정의](media/desktop-what-if/what-if_06.png)

그런 다음, 축에서 **OrderDate**를 포함하는 열 시각적 개체를 만들고 **SalesAmount**와 방금 만든 측정값 **‘할인 후 판매액’** 을 값으로 만듭니다.

![SalesAmount의 시각화](media/desktop-what-if/what-if_07.png)

그런 다음 슬라이더를 이동하면 **할인 후 판매액** 열이 할인된 판매액을 반영하는 것을 확인할 수 있습니다.

![슬라이더가 시각화와 직접 상호작용](media/desktop-what-if/what-if_08.png)

이제 필요한 항목이 모두 준비되었습니다. 모든 종류의 상황에서 가상 매개 변수를 사용할 수 있습니다. 이러한 매개 변수는 보고서의 소비자가 보고서에서 만든 다양한 시나리오와 상호 작용하도록 할 수 있습니다.
