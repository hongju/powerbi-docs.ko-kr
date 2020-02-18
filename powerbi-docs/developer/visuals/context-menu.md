---
title: Power BI 시각적 개체의 기능 및 속성
description: 이 문서에서는 Power BI 시각적 개체의 기능 및 속성을 설명합니다.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: rkarlin
manager: rkarlin
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 7d24ea77fd73ca6a83176d1b8560c88fa98a8d6b
ms.sourcegitcommit: 0cc594ebb78a6d0e88784673ed09f8aefd10c7a7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76819195"
---
# <a name="add-context-menu-to-power-bi-visual"></a>Power BI 시각적 개체에 상황에 맞는 메뉴 추가

`selectionManager.showContextMenu()`를 매개 변수 `selectionId` 및 위치(`{x:, y:}` 개체)와 함께 사용하여 Power BI가 시각적 개체에 대한 상황에 맞는 메뉴를 표시하도록 할 수 있습니다.

> [!IMPORTANT]
> `selectionManager.showContextMenu()`는 시각적 개체 API 2.2.0에서 도입되었습니다.

일반적으로 이 도구는 참조를 위해 샘플 막대형 차트에 추가된 오른쪽 클릭 이벤트(또는 터치 디바이스의 경우 길게 누르기)로 추가 되었습니다.

```typescript
    public update(options: VisualUpdateOptions) {
        //...
        //handle context menu
        this.svg.on('contextmenu', () => {
            const mouseEvent: MouseEvent = d3.event as MouseEvent;
            const eventTarget: EventTarget = mouseEvent.target;
            let dataPoint = d3.select(eventTarget).datum();
            this.selectionManager.showContextMenu(dataPoint? dataPoint.selectionId : {}, {
                x: mouseEvent.clientX,
                y: mouseEvent.clientY
            });
            mouseEvent.preventDefault();
        });
```
