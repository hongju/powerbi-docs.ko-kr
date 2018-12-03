---
title: Power BI Desktop에서 숫자 범위 슬라이서 사용
description: Power BI Desktop에서 숫자 범위를 제한하는 슬라이서를 사용하는 방법을 알아봅니다
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 11/28/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: f997ee7574c5dd9dc6b4d28767d599a97bf297ed
ms.sourcegitcommit: 2ae660a7b70fce23eb58b159d049eca44a664f2c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/30/2018
ms.locfileid: "52669845"
---
# <a name="use-the-numeric-range-slicer-in-power-bi-desktop"></a>Power BI Desktop에서 숫자 범위 슬라이서 사용
**숫자 범위 슬라이서**를 사용하여 데이터 모델의 모든 숫자 열에 모든 종류의 필터를 적용할 수 있습니다. **사이** 숫자, 숫자**보다 작거나 같음** 또는 숫자**보다 크거나 같음**을 필터링하도록 선택할 수 있습니다. 간단하게 들릴 수도 있지만 데이터를 필터링하는 매우 강력한 방법입니다.

![숫자 범위 슬라이서를 사용한 시각적 개체](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-0.png)

## <a name="using-the-numeric-range-slicer"></a>숫자 범위 슬라이서 사용
다른 슬라이서와 마찬가지로 숫자 범위 슬라이서를 사용할 수 있습니다. 보고서에 **슬라이서** 시각적 개체를 만들기만 하면 **필드** 값에 숫자 값을 선택합니다. 다음 이미지에서는 *LineTotal* 필드가 선택되어 있습니다.

![숫자 범위 슬라이서 만들기](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-1-create.png)

**숫자 범위 슬라이서**의 오른쪽 위 모서리에서 아래쪽 화살표 링크를 선택하면 메뉴가 나타납니다.

![숫자 범위 슬라이서 메뉴](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-2-between.png)

숫자 범위에 대해 다음과 같은 세 가지 중에서 선택할 수 있습니다.

* 사이
* 보다 작거나 같음
* 보다 크거나 같음

메뉴에서 **사이**를 선택하면 슬라이더가 나타나고 숫자 사이에 해당하는 숫자 값으로 필터링할 수 있습니다. 슬라이더 막대 자체를 사용하는 것 외에도 상자 중 하나를 클릭하고 값을 입력할 수 있습니다. 특정 정수를 조각화하는 경우 유용하지만 슬라이서 막대를 이동하는 세분성으로 인해 해당 숫자에 정확하게 맞추기가 어렵습니다.

다음 이미지에서 보고서 페이지는 2500.00과 6000.00 간의 범위로 지정된 *LineTotal* 값으로 필터링됩니다.

![사이를 사용한 숫자 범위 슬라이서](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-3-between-range.png)

**보다 작거나 같음**을 선택하면 슬라이더 막대의 왼쪽(낮은 값) 핸들이 사라지고 슬라이더 막대의 상한만을 조정할 수 있습니다. 다음 이미지에서는 슬라이더 막대를 최대 5928.19로 설정합니다.

![보다 작음을 사용한 숫자 범위 슬라이서](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-4-less-than.png)

마지막으로 **보다 크거나 같음**을 선택한 경우 오른쪽(높은 값) 슬라이더 막대 핸들이 사라지고 다음 이미지에 표시된 대로 낮은 값을 조정할 수 있습니다. 이제 4902.99보다 크거나 같은 *LineTotal* 값이 있는 항목만이 보고서 페이지의 시각적 개체에 표시됩니다.

![보다 큼을 사용한 숫자 범위 슬라이서](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-5-greater-than.png)

## <a name="snap-to-whole-numbers-with-the-numeric-range-slicer"></a>숫자 범위 슬라이서를 사용하여 정수로 맞춤

숫자 범위 슬라이서는 기본 필드의 데이터 유형이 **정수**인 경우 정수로 맞춰집니다. 슬라이서를 깔끔하게 정수로 맞출 수 있습니다. **10진수** 유형 필드에서는 숫자의 분수를 입력하거나 선택할 수 있습니다. 텍스트 상자에 적용된 서식은 더 정밀한 숫자를 입력하거나 선택할 수 있더라도 필드에 설정된 서식과 매칭됩니다.


## <a name="limitations-and-considerations"></a>제한 사항 및 고려 사항
현재 다음과 같은 제한 사항 및 고려 사항이 **숫자 범위 슬라이서**에 적용됩니다.

* 현재 **숫자 범위 슬라이서**는 집계된 값이 아닌 데이터에 있는 모든 기본 행을 필터링합니다. 예를 들어 *판매량* 필드를 사용한 경우 시각적 개체의 각 데이터 요소에 대한 *판매량* 의 총합이 아닌 *판매량* 에 따른 각 트랜잭션을 기반으로 필터링됩니다.
* 현재는 측정값으로 작동하지 않습니다.
* 기본 열에 있는 값의 범위를 벗어난 경우에도 숫자 슬라이서의 텍스트 상자에 원하는 수를 입력할 수 있습니다. 데이터가 앞으로 변경될 수 있다는 것을 아는 경우 필터를 설정할 수 있습니다.
