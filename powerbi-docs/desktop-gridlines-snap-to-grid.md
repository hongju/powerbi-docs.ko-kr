---
title: "Power BI Desktop 보고서에서 눈금선 및 눈금에 맞춤 사용"
description: "Power BI Desktop 보고서에서 눈금선, 눈금에 맞춤, z-순서, 맞춤 및 균등 맞춤 사용"
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
ms.openlocfilehash: 232b75b5abdbeebcd1f9bab3455edb4ce0ae3b30
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2017
---
# <a name="use-gridlines-and-snap-to-grid-in-power-bi-desktop-reports"></a>Power BI Desktop 보고서에서 눈금선 및 눈금에 맞춤 사용
**Power BI Desktop** 보고서 캔버스는 보고서 페이지에서 시각적 개체를 깔끔하게 정렬할 수 있는 눈금선을 제공하고 눈금에 맞춤 기능도 제공하여 보고서의 시각적 개체를 깨끗하게 정리하고 맞추고 균등하게 배치할 수 있도록 합니다.

또한 **Power BI Desktop**에서 보고서에서 개체의 z-순서(앞으로 가져 오기, 뒤로 보내기)를 조정하고 선택한 시각적 개체를 캔버스에 정렬하거나 균등하게 배분할 수도 있습니다.

![](media/desktop-gridlines-snap-to-grid/snap-to-grid_0.png)

### <a name="enabling-gridlines-and-snap-to-grid"></a>눈금선 및 눈금에 맞춤 사용
눈금선 및 눈금에 맞춤을 사용하려면 **보기** 리본을 선택한 다음 **눈금선 표시** 및 **개체를 눈금에 맞춤**의 확인란을 사용하도록 설정합니다. 하나 또는 두 개의 상자를 선택할 수 있으며 각각 독립적으로 작동합니다.

![](media/desktop-gridlines-snap-to-grid/snap-to-grid_1.png)

> [!NOTE]
> **눈금선 표시** 및 **개체를 눈금에 맞춤**을 사용하지 않는 경우 모든 데이터 원본에 연결하면 사용할 수 없게 됩니다.
> 
> 

### <a name="using-gridlines"></a>눈금선 사용
눈금선은 두 개 이상의 시각적 개체를 제대로 정렬하였는지 여부를 확인할 수 있는 시각적 가이드입니다. 두 개 이상의 시각적 개체를 가로 또는 세로로 정렬할지 여부를 결정하려는 경우 눈금선을 사용하여 해당 테두리를 시각적으로 정렬할지 여부를 결정합니다.

선택한 모든 시각적 개체의 테두리를 표시하도록 CTRL+클릭을 선택하여 시각적 개체를 제대로 정렬했는지 여부를 쉽게 확인할 수 있습니다.

![](media/desktop-gridlines-snap-to-grid/snap-to-grid_2.png)

#### <a name="using-gridlines-inside-visuals"></a>시각적 개체 내의 눈금선 사용
Power BI에는 데이터 요소와 값을 비교하기 위한 시각적 지침을 제공하는 시각적 개체 내부의 눈금선도 있습니다. **Power BI Desktop**의 2017년 9월 릴리스부터 **시각화** 창의 **서식** 섹션에서 찾을 수 있는 **X-축** 또는 **Y-축** 카드를 사용하여 시각적 개체 내에서 눈금선을 관리할 수 있습니다(시각적 형식에 따라 적절하게). 시각적 개체 내에서 눈금선의 다음 요소를 관리할 수 있습니다.

* 눈금선 켜기 또는 끄기
* 눈금선의 색 변경
* 눈금선의 선(두께) 조정
* 실선, 파선 또는 점선과 같이 시각적 개체에서 눈금선의 선 스타일을 선택합니다.

눈금선의 특정 요소를 수정하면 특히 시각적 개체에 어두운 배경을 사용하는 보고서에서 유용할 수 있습니다. 다음 이미지에서는 **X-축** 카드에서 *눈금선* 섹션을 보여줍니다.

![](media/desktop-gridlines-snap-to-grid/snap-to-grid_9.png)

### <a name="using-snap-to-grid"></a>눈금에 맞춤 사용
**개체를 눈금에 맞춤**을 사용하도록 설정한 경우 이동시키거나 크기를 조정한 **Power BI Desktop** 캔버스의 모든 시각적 개체는 가장 가까운 눈금 축에 정렬되어 둘 이상의 시각적 개체가 동일한 수평 또는 수직 위치나 크기로 쉽게 정렬될 수 있습니다.

![](media/desktop-gridlines-snap-to-grid/snap-to-grid_3.png)

**눈금선** 및 **눈금에 맞춤**을 사용하여 보고서에서 시각적 개체를 쉽고 깔끔하게 정렬하는 방법은 여기까지입니다.

### <a name="using-z-order-align-and-distribute"></a>z 순서 사용, 맞춤 및 균등 맞춤
보고서에서 종종 요소의 z 순서라고도 하는 시각적 개체의 전후 순서를 관리할 수도 있습니다. 이렇게 하면 원하는 방식으로 시각적 개체를 겹쳐서 각 시각적 개체의 전후 순서를 조정할 수 있습니다. 이러한 순서 지정은 **서식** 리본의 **정렬** 섹션에 있는 **앞으로 가져오기** 및 **뒤로 보내기** 단추를 사용하여 수행됩니다. 시각적 개체를 선택하지 않으면 이 단추들은 사용할 수 없습니다.

![](media/desktop-gridlines-snap-to-grid/snap-to-grid_4.png)

또한 **서식** 리본을 사용하면 여러 가지 다양한 방법으로 시각적 개체를 정렬할 수 있습니다. 이렇게 하면 페이지에서 가장 잘 보이고 작동한다고 생각되는 모양으로 정렬된 시각적 개체를 표시할 수 있습니다.

![](media/desktop-gridlines-snap-to-grid/snap-to-grid_5.png)

하나의 시각적 개체를 선택하는 경우 **맞춤** 단추를 사용하여 다음 이미지와 같이 해당 시각적 개체를 보고서 캔버스의 가장자리(또는 가운데)에 맞춥니다.

![](media/desktop-gridlines-snap-to-grid/snap-to-grid_6.png)

둘 이상의 시각적 개체를 선택하는 경우 이 개체들은 함께 맞추어지며, 원하는 대로 맞추기 위해 시각적 개체의 기존 맞춤 경계를 사용합니다. 예를 들어 두 개의 시각적 개체를 선택하고 *왼쪽 맞춤* 단추를 선택하면 선택한 모든 시각적 개체의 가장 왼쪽 경계에 맞춰집니다.

![](media/desktop-gridlines-snap-to-grid/snap-to-grid_7.png)

또한 보고서 캔버스 전체에서 시각적 개체를 수직 또는 수평으로 균등하게 맞출 수 있습니다. **서식** 리본에서 **균등 맞춤** 단추를 사용만 하면 됩니다.

![](media/desktop-gridlines-snap-to-grid/snap-to-grid_8.png)

이러한 눈금선, 맞춤 및 균등 맞춤 도구에서 몇 가지 항목을 선택하면 원하는 방식으로 보고서를 볼 수 있습니다.

