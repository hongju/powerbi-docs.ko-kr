---
title: 강조 표시
description: Power BI 시각적 개체의 데이터 요소 선택 항목 강조 표시
author: sranins
ms.author: rasala
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 1ee45781ddc29eee9eeab23a5d748fb7752fe907
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/23/2019
ms.locfileid: "68424818"
---
# <a name="highlight-data-points-in-power-bi-visuals"></a>Power BI 시각적 개체에서 데이터 요소 강조 표시

기본적으로 요소를 선택할 때마다 `dataView` 개체의 `values` 배열이 선택한 값으로만 필터링됩니다. 그러면 페이지의 다른 모든 시각적 개체에 선택한 데이터만 표시됩니다.

![강조 표시 ‘dataview’ 기본 동작](./media/highlight-dataview.png)

`capabilities.json`의 `supportsHighlight` 속성을 `true`로 설정하면 필터링되지 않은 전체 `values` 배열과 `highlights` 배열을 받게 됩니다. `highlights` 배열의 길이는 values 배열과 같으며, 선택하지 않은 값은 `null`로 설정됩니다. 이 속성이 사용하도록 설정된 경우, 시각적 개체는 `values` 배열을 `highlights` 배열과 비교하여 적절한 데이터를 강조 표시해야 합니다.

![강조 표시 ‘dataview’ supportshighlight](./media/highlight-dataview-supports.png)

이 예제에서는 선택된 막대 1개를 확인할 수 있습니다. 또한 highlights 배열의 유일한 값입니다. 여러 개의 선택 항목과 부분 강조 표시가 있을 수도 있습니다. values 및 highlights 배열에 해당하는 숫자 값이 있지만 서로 다릅니다.
