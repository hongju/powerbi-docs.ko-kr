---
title: Power BI Desktop에서 숫자 범위 슬라이서 사용
description: Power BI Desktop에서 숫자 범위를 제한하는 슬라이서를 사용하는 방법을 알아봅니다
services: powerbi
documentationcenter: ''
author: davidiseminger
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 05/02/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: f9ef31815f82775fd228f170073ee576c299ed45
ms.sourcegitcommit: f679c05d029ad0765976d530effde744eac23af5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="use-the-numeric-range-slicer-in-power-bi-desktop"></a>Power BI Desktop에서 숫자 범위 슬라이서 사용
**숫자 범위 슬라이서**를 사용하여 데이터 모델의 모든 숫자 열에 모든 종류의 필터를 적용할 수 있습니다. **사이** 숫자, 숫자**보다 작거나 같음** 또는 숫자**보다 크거나 같음**을 필터링하도록 선택할 수 있습니다. 간단하게 들릴 수도 있지만 데이터를 필터링하는 매우 강력한 방법입니다.

![](media/desktop-slicer-numeric-range/slicer-numeric-range_2.png)

## <a name="using-the-numeric-range-slicer"></a>숫자 범위 슬라이서 사용
다른 슬라이서와 마찬가지로 숫자 범위 슬라이서를 사용할 수 있습니다. 보고서에 **슬라이서** 시각적 개체를 만들기만 하면 **필드** 값에 숫자 값을 선택합니다. 다음 이미지에서는 *UnitPrice* 필드를 선택합니다.

![](media/desktop-slicer-numeric-range/slicer-numeric-range_3.png)

**숫자 범위 슬라이서**의 오른쪽 위 모서리에서 캐럿을 선택하면 메뉴가 나타납니다.

![](media/desktop-slicer-numeric-range/slicer-numeric-range_4.png)

숫자 범위에 대해 다음과 같은 세 가지 중에서 선택할 수 있습니다.

* 사이
* 보다 작거나 같음
* 보다 크거나 같음

메뉴에서 **사이**를 선택하면 슬라이더가 나타나고 숫자 사이에 해당하는 숫자 값으로 필터링할 수 있습니다. 슬라이더 막대 자체를 사용하는 것 외에도 상자 중 하나를 클릭하고 값을 입력할 수 있습니다. 특정 정수를 조각화하는 경우 유용하지만 슬라이서 막대를 이동하는 세분성으로 인해 해당 숫자에 정확하게 맞추기가 어렵니다.

다음 이미지에서 보고서 페이지는 500과 1500 간의 범위로 지정된 *UnitPrice* 값으로 필터링됩니다.

![](media/desktop-slicer-numeric-range/slicer-numeric-range_5.png)

**보다 작거나 같음**을 선택하면 슬라이더 막대의 왼쪽(낮은 값) 핸들이 사라지고 슬라이더 막대의 상한만을 조정할 수 있습니다. 다음 이미지에서는 슬라이더 막대를 497.17로 설정합니다.

![](media/desktop-slicer-numeric-range/slicer-numeric-range_6.png)

마지막으로 **보다 크거나 같음**을 선택한 경우 오른쪽(높은 값) 슬라이더 막대 핸들이 사라지고 다음 이미지에 표시된 대로 낮은 값을 조정할 수 있습니다. 이제 750.56보다 크거나 같은 *UnitPrice* 값이 있는 항목만이 보고서 페이지의 시각적 개체에 표시됩니다.

![](media/desktop-slicer-numeric-range/slicer-numeric-range_7.png)

## <a name="snap-to-whole-numbers-with-the-numeric-range-slicer-preview"></a>숫자 범위 슬라이서를 사용하여 정수로 맞춤(미리 보기)

**Power BI Desktop**의 2018년 2월 릴리스부터 숫자 범위 슬라이서가 정수로 맞춰집니다. 슬라이서를 깔끔하게 정수로 맞출 수 있습니다. 정수로 맞추는 기능은 10진수 필터에 적용되지 않습니다.


## <a name="limitations-and-considerations"></a>제한 사항 및 고려 사항
현재 다음과 같은 제한 사항 및 고려 사항은 **숫자 범위 슬라이서**에 적용됩니다.

* 현재 **숫자 범위 슬라이서**는 집계된 값이 아닌 데이터에 있는 모든 기본 행을 필터링합니다. 예를 들어 *판매량* 필드를 사용한 경우 시각적 개체의 각 데이터 요소에 대한 *판매량* 의 총합이 아닌 *판매량* 에 따른 각 트랜잭션을 기반으로 필터링됩니다.
* 현재는 측정값으로 작동하지 않습니다.
* 현재 **숫자 범위 슬라이서**는 **Power BI Desktop**에서 사용할 수 없습니다. **숫자 범위 슬라이서**를 사용하는 보고서가 **Power BI 서비스**에 게시되는 경우 필터는 여전히 적용되지만 목록 슬라이서로 표시됩니다.

