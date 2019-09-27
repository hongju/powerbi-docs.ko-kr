---
title: Power BI 시각적 개체에서 슬라이서 동기화 기능 사용
description: 이 문서에서는 Power BI 시각적 개체에 슬라이서 동기화 기능을 추가하는 방법을 설명합니다.
author: KesemSharabi
ms.author: kesharab
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 47f0148528d1ccfd451aa8e8ed87b4bec99d087e
ms.sourcegitcommit: e2de2e8b8e78240c306fe6cca820e5f6ff188944
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2019
ms.locfileid: "71194390"
---
# <a name="sync-slicers-in-power-bi-visuals"></a>Power BI 시각적 개체의 슬라이서 동기화

[슬라이서 동기화](https://docs.microsoft.com/power-bi/desktop-slicers) 기능을 지원하려면 사용자 지정 슬라이서 시각적 개체가 API 버전 1.13 이상을 사용해야 합니다.

또한 다음 코드와 같이 *capabilities.json* 파일에서 옵션을 사용하도록 설정해야 합니다.

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

*capabilities.json* 파일을 업데이트한 후에 사용자 지정 슬라이서 시각적 개체를 선택하면 **슬라이서 동기화** 옵션 창을 볼 수 있습니다.

> [!NOTE]
> 슬라이서 동기화 기능은 하나의 필드만 지원합니다. 슬라이서에 둘 이상의 필드(**범주** 또는 **측정값**)가 있으면, 이 기능을 사용할 수 없습니다.

![“슬라이서 동기화” 창](./media/sync-slicers-panel.png)

**슬라이서 동기화** 창에서 여러 보고서 페이지에 슬라이서 표시 유형과 해당 필터링을 적용할 수 있는 것을 확인할 수 있습니다.
