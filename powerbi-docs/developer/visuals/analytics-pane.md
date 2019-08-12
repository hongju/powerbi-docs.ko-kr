---
title: 분석 창
description: Power BI 시각적 개체에 동적 참조선을 만드는 방법
author: Guy-Moses
ms.author: guymos
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: b3b50f8dbcf40a3923e86422e24f8ed020894445
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/23/2019
ms.locfileid: "68425531"
---
# <a name="analytics-pane-in-power-bi-visuals"></a>Power BI 시각적 개체의 분석 창

**분석 창은**은 2018년 11월에 [네이티브 시각적 개체에 대해 도입](https://docs.microsoft.com/power-bi/desktop-analytics-pane)되었습니다.
API v2.5.0을 사용하는 사용자 지정 시각적 개체는 **분석 창**에서 해당 속성을 제공하고 관리할 수 있습니다.

![분석 창](./media/visualization-pane-analytics-tab.png)

시각적 개체의 capabilities.json 파일에서 개체를 정의하여, [서식 창에서 속성을 관리](https://docs.microsoft.com/power-bi/developer/custom-visual-develop-tutorial-format-options)하는 방법과 비슷하게 처리됩니다. 

차이점은 다음과 같습니다.

1. `object` 정의 아래에 값이 2인 `objectCategory` 필드를 추가합니다.

    > [!NOTE]
    > `objectCategory` 필드는 API 2.5.0에서 도입된 선택적 필드입니다. 개체가 제어하는 시각적 개체의 측면을 정의합니다(1 = 서식, 2 = 분석). “서식”은 모양 및 느낌, 색, 축, 레이블 등에 사용됩니다. “분석”은 예측, 추세선, 참조선 및 도형에 사용됩니다.
    >
    > 생략하면, `objectCategory`는 기본적으로 “서식”으로 설정됩니다.

2. 개체에는 다음 두 가지 속성이 있어야 합니다.
    1. bool 형식의 `show`(기본값은 false임)
    2. 텍스트 형식의 `displayName` 선택한 기본값이 인스턴스의 초기 표시 이름이 됩니다.

```json
{
  "objects": {
    "YourAnalyticsPropertiesCard": {
      "displayName": "Your analytics properties card's name",
      "objectCategory": 2,
      "properties": {
        "show": {
          "type": {
            "bool": true
          }
        },
        "displayName": {
          "type": {
            "text": true
          }
        },
      ... //any other properties for your Analytics card
      }
    }
  ...
  }
}
```

다른 모든 속성도 서식 개체와 동일한 방식으로 정의할 수 있습니다. 개체 열거형은 **서식 창**과 정확히 동일하게 수행됩니다.

‘알려진 제한 사항 및 문제’****

  1. 다중 인스턴스는 아직 지원되지 않습니다. 개체에 static 이외의 [selector](https://microsoft.github.io/PowerBI-visuals/docs/concepts/objects-and-properties/#selector)(즉, “selector”: null)를 사용할 수 없으며, 사용자 지정 시각적 개체에 카드의 여러 사용자 정의 인스턴스를 사용할 수 없습니다.
  2. `integer` 형식의 속성이 올바르게 표시되지 않습니다. 해결 방법으로, `numeric` 형식을 대신 사용합니다.

> [!NOTE]
> 새 정보를 추가하거나 제공된 정보를 새롭게 조명하는 개체에 대해서만 분석 창을 사용합니다. 예를 들어 중요한 추세를 보여 주는 동적 참조선이 있습니다.
> 시각적 개체의 모양과 느낌(즉, 서식)을 제어하는 모든 옵션은 서식 창에 유지해야 합니다.
