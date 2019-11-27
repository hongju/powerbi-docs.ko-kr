---
title: Power BI 시각적 개체 InteractivityUtils
description: 이 문서에서는 InteractivityUtils를 사용하여 Power BI 시각적 개체에 선택 항목을 추가하는 방법을 설명합니다.
author: zBritva
ms.author: v-ilgali
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 8a9218085b0da655d1ce4b3ece0b2666c4826c86
ms.sourcegitcommit: f7b28ecbad3e51f410eff7ee4051de3652e360e8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74061871"
---
# <a name="microsoft-power-bi-visuals-interactivity-utils"></a>Microsoft Power BI 시각적 개체 InteractivityUtils

InteractivityUtils는 Power BI 사용자 지정 시각적 개체에 대한 교차 선택 및 교차 필터링 구현을 간소화하기 위한 함수와 클래스의 집합입니다.

## <a name="installation"></a>설치

> [!NOTE]
> 이전 버전의 powerbi-visuals-tools(3.x.x 미만 버전 번호)를 계속 사용하는 경우 새 버전의 도구(3.x.x)를 설치합니다.

> [!IMPORTANT]
> 새로 업데이트된 InteractivityUtils는 최신 버전의 도구만 지원합니다. [최신 도구를 사용하도록 시각적 개체를 업데이트하는 방법에 대해 자세히 알아보기](migrate-to-new-tools.md)

패키지를 설치하려면 현재 사용자 지정 시각적 개체가 있는 디렉터리에서 다음 명령을 실행해야 합니다.

```bash
npm install powerbi-visuals-utils-interactivityutils --save
```

버전 3.0 이상부터는 종속성을 해결하기 위해 ```powerbi-models```도 설치해야 합니다.

```bash
npm install powerbi-models --save
```

InteractivityUtils를 사용하려면 시각적 개체의 소스 코드에 필요한 구성 요소를 가져와야 합니다.

```typescript
import { interactivitySelectionService } from "powerbi-visuals-utils-interactivityutils";
```

### <a name="including-css-artifacts-to-the-custom-visual"></a>사용자 지정 시각적 개체에 CSS 아티팩트 포함

사용자 지정 시각적 개체에 패키지를 사용하려면 다음 CSS 파일을 `your.less` 파일로 가져와야 합니다.

`node_modules/powerbi-visuals-utils-interactivityutils/lib/index.css`

결과적으로 다음과 같은 파일 구조를 갖게 됩니다.

```less
@import (less) "node_modules/powerbi-visuals-utils-interactivityutils/lib/index.css";
```

> [!NOTE]
> Power BI 시각적 개체 도구는 외부 CSS 규칙을 래핑하므로 .css 파일을 .less 파일로 가져와야 합니다.

## <a name="usage"></a>사용

### <a name="define-interface-for-data-points"></a>데이터 요소에 대한 인터페이스 정의

일반적으로 데이터 요소는 선택 항목 및 값을 포함합니다. 인터페이스는 `SelectableDataPoint` 인터페이스를 확장합니다. `SelectableDataPoint`에는 이미 속성이 포함되어 있습니다.

```typescript
  /** Flag for identifying that data point was selected */
  selected: boolean;
  /** Identity for identifying the selectable data point for selection purposes */
  identity: powerbi.extensibility.ISelectionId;
  /**
   * A specific identity for when data points exist at a finer granularity than
   * selection is performed.  For example, if your data points should select based
   * only on series even if they exist as category/series intersections.
   */
  specificIdentity?: powerbi.extensibility.ISelectionId;
```

InteractivityUtils를 사용하는 첫 번째 단계는 InteractivityUtils 인스턴스를 만들고 개체를 시각적 개체의 속성으로 저장하는 것입니다.

```typescript
export class Visual implements IVisual {
  // ...
  private interactivity: interactivityBaseService.IInteractivityService<VisualDataPoint>;
  // ...
  constructor(options: VisualConstructorOptions) {
      // ...
      this.interactivity = interactivitySelectionService.createInteractivitySelectionService(this.host);
      // ...
  }
}
```

```typescript
import { interactivitySelectionService } from "powerbi-visuals-utils-interactivityutils";

export interface VisualDataPoint extends interactivitySelectionService.SelectableDataPoint {
    value: powerbi.PrimitiveValue;
}
```

두 번째 단계는 기본 동작 클래스를 확장하는 것입니다.

> [!NOTE]
> [5.6.x 버전 InteractivityUtils](https://www.npmjs.com/package/powerbi-visuals-utils-interactivityutils/v/5.6.0)에 도입된 BaseBehavior. 이전 버전을 사용하는 경우 아래 샘플에서 동작 클래스를 만듭니다(`BaseBehavior` 클래스는 동일).

동작 클래스의 옵션에 대한 인터페이스를 정의합니다.

```typescript
import { SelectableDataPoint } from "./interactivitySelectionService";

import {
    IBehaviorOptions,
    BaseDataPoint
} from "./interactivityBaseService";

export interface BaseBehaviorOptions<SelectableDataPointType extends BaseDataPoint> extends IBehaviorOptions<SelectableDataPointType> {
    /** D3 selection object of main elements on the chart */
    elementsSelection: Selection<any, SelectableDataPoint, any, any>;
    /** D3 selection object of some element on backgroup to hadle click of reset selection */
    clearCatcherSelection: d3.Selection<any, any, any, any>;
}
```

`visual behaviour`에 대한 클래스를 정의합니다. `click`, `contextmenu` 마우스 이벤트를 처리하는 클래스입니다.
클릭을 사용하여 데이터 요소를 선택하는 경우 시각적 개체가 선택 처리기를 호출하여 데이터 요소를 선택합니다. 또는 사용자가 시각적 개체의 배경을 클릭하면 선택을 취소합니다. 그리고 클래스에는 `bindClick`, `bindClearCatcher`, `bindContextMenu`와 같은 메서드가 있습니다.

```typescript
export class Behavior<SelectableDataPointType extends BaseDataPoint> implements IInteractiveBehavior {
    /** D3 selection object of main elements on the chart */
    protected options: BaseBehaviorOptions<SelectableDataPointType>;
    protected selectionHandler: ISelectionHandler;

    protected bindClick() {
      // ...
    }

    protected bindClearCatcher() {
      // ...
    }

    protected bindContextMenu() {
      // ...
    }

    public bindEvents(
        options: BaseBehaviorOptions<SelectableDataPointType>,
        selectionHandler: ISelectionHandler): void {
      // ...
    }

    public renderSelection(hasSelection: boolean): void {
      // ...
    }
}
```

또는 `BaseBehavior` 클래스를 확장할 수 있습니다.

```typescript
import powerbi from "powerbi-visuals-api";
import { interactivitySelectionService, baseBehavior } from "powerbi-visuals-utils-interactivityutils";

export interface VisualDataPoint extends interactivitySelectionService.SelectableDataPoint {
    value: powerbi.PrimitiveValue;
}

export class Behavior extends baseBehavior.BaseBehavior<VisualDataPoint> {
  // ...
}
```

요소에 대한 클릭을 처리하려면 D3 선택 개체의 `on` 메서드를 호출합니다(elementsSelection 및 clearCatcherSelection의 경우도 마찬가지).

```typescript
protected bindClick() {
  const {
      elementsSelection
  } = this.options;

  elementsSelection.on("click", (datum) => {
      const mouseEvent: MouseEvent = getEvent() as MouseEvent || window.event as MouseEvent;
      mouseEvent && this.selectionHandler.handleSelection(
          datum,
          mouseEvent.ctrlKey);
  });
}
```

`contextmenu` 이벤트에 대한 유사한 처리기를 추가하여 선택 관리자의 `showContextMenu` 메서드를 호출합니다.

```typescript
protected bindContextMenu() {
    const {
        elementsSelection
    } = this.options;

    elementsSelection.on("contextmenu", (datum) => {
        const event: MouseEvent = (getEvent() as MouseEvent) || window.event as MouseEvent;
        if (event) {
            this.selectionHandler.handleContextMenu(
                datum,
                {
                    x: event.clientX,
                    y: event.clientY
                });
            event.preventDefault();
        }
    });
}
```

InteractivityUtils는 `bindEvents` 메서드를 호출하여 함수를 처리기에 할당하고 `bindClick`, `bindClearCatcher` 및 `bindContextMenu` 호출을 `bindEvents` 메서드에 추가합니다.

```typescript
  public bindEvents(
      options: BaseBehaviorOptions<SelectableDataPointType>,
      selectionHandler: ISelectionHandler): void {

      this.options = options;
      this.selectionHandler = selectionHandler;

      this.bindClick();
      this.bindClearCatcher();
      this.bindContextMenu();
  }
```

`renderSelection` 메서드는 차트에서 요소의 시각적 상태를 업데이트합니다.

`renderSelection` 메서드 구현 샘플:

```typescript
public renderSelection(hasSelection: boolean): void {
    this.options.elementsSelection.style("opacity", (category: any) => {
        if (category.selected) {
            return 0.5;
        } else {
            return 1;
        }
    });
}
```

마지막 단계는 `visual behavior`의 인스턴스를 만들고 InteractivityUtils 인스턴스의 `bind` 메서드를 호출하는 것입니다.

```typescript
this.interactivity.bind(<BaseBehaviorOptions<VisualDataPoint>>{
    behavior: this.behavior,
    dataPoints: this.categories,
    clearCatcherSelection: select(this.target),
    elementsSelection: selectionMerge
});
```

* `selectionMerge`는 D3 선택 개체로서, 시각적 개체에 선택할 수 있는 모든 요소를 나타냅니다.

* `select(this.target)`는 D3 선택 개체로서, 시각적 개체의 주 DOm 요소를 나타냅니다.

* `this.categories`는 요소가 포함된 데이터 요소로서, 인터페이스는 `VisualDataPoint`(또는 `categories: VisualDataPoint[];`)입니다.

* `this.behavior`는 시각적 개체의 생성자에서 만들어진 `visual behavior`의

  새 인스턴스입니다.

  ```typescript
  export class Visual implements IVisual {
    // ...
    constructor(options: VisualConstructorOptions) {
        // ...
        this.behavior = new Behavior();
    }
    // ...
  }
  ```

이제 시각적 개체를 처리기에서 선택할 수 있습니다.

## <a name="next-steps"></a>다음 단계

* [책갈피 전환에서 선택 항목을 처리하는 방법 읽기](bookmarks-support.md#visuals-with-selection)

* [시각적 개체 데이터 요소에 대한 상황에 맞는 메뉴를 추가하는 방법 읽기](context-menu.md)

* [선택 관리자를 사용하여 Power BI 시각적 개체에 선택 항목을 추가하는 방법 읽기](selection-api.md)
