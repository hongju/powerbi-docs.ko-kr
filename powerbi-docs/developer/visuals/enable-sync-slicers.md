---
title: 슬라이서 동기화 사용
description: Power BI 시각적 개체에 대해 슬라이서 동기화 기능을 추가하는 방법
author: EugeneElkin
ms.author: v-evelk
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 9966475e8bcaccad2090451b47ef09ef0a9af125
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/23/2019
ms.locfileid: "68425025"
---
# <a name="sync-slicers"></a>슬라이서 동기화

[슬라이서 동기화](https://docs.microsoft.com/power-bi/desktop-slicers)를 지원하려면 사용자 지정 슬라이서 시각적 개체에서 API 1.13 이상을 사용해야 합니다.

두 번째 필요한 측면은 `capabilities.json`에서 사용하도록 설정된 옵션입니다(아래 샘플 참조).

```json
{
    ...
    "supportsHighlight": true,
    "suppressDefaultTitle": true,
    "supportsSynchronizingFilterState": true,
    "sorting": {
        "default": {}
    }
}
```

`capabilities.json`에서 변경한 후 사용자 지정 슬라이서 시각적 개체를 클릭하면 슬라이서 동기화 옵션 패널을 볼 수 있습니다.

> [!NOTE]
> 슬라이서에 필드(범주 또는 측정값)가 두 개 이상 있는 경우 슬라이서 동기화는 여러 필드를 지원하지 않으므로 기능을 사용할 수 없습니다.

![슬라이서 동기화 패널](./media/sync-slicers-panel.png)

이 패널에서 여러 보고서 페이지에 대해 슬라이서 표시 유형 및 해당 필터링을 적용할 수 있는 것을 확인할 수 있습니다.
