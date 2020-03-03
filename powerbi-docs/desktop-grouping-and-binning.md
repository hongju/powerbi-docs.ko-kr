---
title: Power BI Desktop에서 그룹화 및 범주화 사용
description: Power BI Desktop에서 요소의 그룹화 및 범주화 방법 알아보기
author: davidiseminger
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 12/18/2019
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 525f7bf4c967722d8f98a9184127bc8c7907cea1
ms.sourcegitcommit: b68a47b1854588a319a5a2d5d6a79bba2da3a4e6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "75729926"
---
# <a name="use-grouping-and-binning-in-power-bi-desktop"></a>Power BI Desktop에서 그룹화 및 범주화 사용
Power BI Desktop에서는 시각적 개체를 만들 때 기본 데이터에서 발견되는 값을 기반으로 청크(또는 그룹)에 데이터를 집계합니다. 대개는 좋지만 이러한 청크를 표시하는 방법을 구체화하고자 하는 때가 있을 수 있습니다. 예를 들어 하나의 큰 범주(하나의 *그룹*)에 세 가지 범주의 제품을 배치할 수 있습니다. 또는 923,983달러 크기의 청크 대신 1,000,000달러 bin 크기로 판매액을 배치하여 표시할 수 있습니다.

Power BI Desktop에서 데이터 포인트를 *그룹화*하여 시각적 개체에서 데이터와 추세를 더욱 명확하게 보고 분석하고 탐색할 수 있습니다. ‘bin 크기’를 정의하여 의미 있는 방식으로 데이터 시각화를 향상하도록 크기가 같은 그룹에 값을 입력할 수도 있습니다.  이러한 작업을 일반적으로 ‘범주화’라고 합니다. 

## <a name="using-grouping"></a>그룹화 사용
그룹화를 사용하려면 Ctrl+클릭을 사용하여 시각적 개체의 두 개 이상 요소를 다중 요소로 선택합니다. 그런 다음, 다중 선택 요소 중 하나를 마우스 오른쪽 단추로 클릭하고 상황에 맞는 메뉴에서 **그룹화**를 선택합니다.

![그룹화 명령, 그래프, 그룹화, Power BI Desktop](media/desktop-grouping-and-binning/grouping-binning_1.png)

그룹이 만들어지면 시각적 개체의 **범례** 버킷에 추가됩니다. 그룹은 **필드** 목록에도 표시됩니다.

![범례 및 필드 목록, 그룹화, Power BI Desktop](media/desktop-grouping-and-binning/grouping-binning_2.png)

그룹이 있으면 쉽게 해당 그룹의 멤버를 편집할 수 있습니다. **범례** 버킷 또는 **필드** 목록에서 필드를 마우스 오른쪽 단추로 클릭하고 **그룹 편집**을 선택하세요.

![그룹 편집 명령, 범례 및 필드 목록, Power BI Desktop](media/desktop-grouping-and-binning/grouping-binning_3.png)

**그룹** 대화 상자에서 새 그룹을 만들거나 기존 그룹을 수정할 수 있습니다. 어떤 그룹이든 ‘이름 바꾸기’를 수행할 수도 있습니다.  **그룹 및 멤버** 상자에서 그룹 제목을 두 번 클릭하고 새 이름을 입력하기만 하면 됩니다.

그룹을 사용하여 모든 종류의 작업을 수행할 수 있습니다. **그룹화되지 않은 값** 목록의 항목을 새 그룹 또는 기존 그룹 중 하나에 추가할 수 있습니다. 새 그룹을 만들려면 **그룹화되지 않은 값** 상자에서 항목을 두 개 이상 선택하고(Ctrl+클릭 사용) 해당 상자 아래의 **그룹화** 단추를 선택합니다.

그룹화되지 않은 값을 기존 그룹에 추가할 수 있습니다. **그룹화되지 않은 값** 중 하나를 선택하고, 값을 추가할 기존 그룹을 선택하고, **그룹화** 단추를 선택하기만 하면 됩니다. 그룹에서 항목을 제거하려면 **그룹 및 멤버** 상자에서 항목을 선택하고 **그룹 해제**를 선택합니다. 그룹화되지 않은 범주를 **기타** 그룹으로 이동하거나 그룹화되지 않은 상태로 유지할 수도 있습니다.

![그룹 대화 상자, Power BI Desktop](media/desktop-grouping-and-binning/grouping-binning_4.png)

> [!NOTE]
> 기존 시각적 개체에서 여러 항목을 선택하지 않아도 **필드**의 어떤 필드에 대해서든 그룹을 만들 수 있습니다. 필드를 마우스 오른쪽 단추로 클릭하고 표시되는 메뉴에서 **새 그룹**을 선택합니다.

## <a name="using-binning"></a>범주화 사용하기
**Power BI Desktop**에서 수치 및 시간 필드에 대한 bin 크기를 설정할 수 있습니다. 범주화를 사용하여 Power BI Desktop이 표시하는 데이터를 적절한 크기로 만들 수 있습니다.

bin 크기를 적용하려면 **필드**를 마우스 오른쪽 단추로 클릭하고 **새 그룹**을 선택합니다.

![새 그룹 명령, 필드 목록 Power BI Desktop](media/desktop-grouping-and-binning/grouping-binning_5.png)

**그룹** 대화 상자에서 **bin 크기**를 원하는 크기로 설정합니다.

![bin 크기, 그룹 대화 상자, Power BI Desktop](media/desktop-grouping-and-binning/grouping-binning_6.png)

**확인**을 선택하면 **필드** 창에 새 필드가 **(bins)** 와 함께 표시됩니다. 그러면 캔버스에 해당 필드를 끌어 놓아 시각적 개체에서 bin 크기를 사용할 수 있습니다.

![캔버스로 bins 필드 끌기, Power BI Desktop](media/desktop-grouping-and-binning/grouping-binning_7.png)

*범주화* 작업을 보려면 이 [비디오](https://www.youtube.com/watch?v=BRvdZSfO0DY)를 보세요.

*그룹화* 및 *범주화*를 사용하여 보고서에 시각적 개체에서 데이터를 원하는 방식으로 바로 표시되도록 하면 됩니다.
