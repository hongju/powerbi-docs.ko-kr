---
title: 이벤트 렌더링
description: Power BI 시각적 개체는 Power Point/PDF로 내보낼 준비가 되었음을 Power BI에 알릴 수 있습니다.
author: Yarovinsky
ms.author: alexyar
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 46166b3503a770e033b98474fcf9240235296cc2
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/23/2019
ms.locfileid: "68425094"
---
# <a name="event-service"></a>이벤트 서비스

새 API는 렌더링 중에 호출되어야 하는 세 가지 메서드(시작됨, 완료됨 또는 실패)로 구성됩니다.

렌더링이 시작되면 사용자 지정 시각적 개체 코드에서 renderingStarted 메서드를 호출하여 렌더링 프로세스가 시작되었음을 나타냅니다.

렌더링이 성공적으로 완료되면 사용자 지정 시각적 개체 코드에서 즉시 `renderingFinished` 메서드를 호출하여 시각적 개체 이미지가 준비되었음을 수신기(**주로 ‘PDF로 내보내기’ 및 ‘PowerPoint로 내보내기’** )에 알립니다.

렌더링 프로세스 중에 문제가 발생하여 사용자 지정 시각적 개체를 완료할 수 없는 경우 사용자 지정 시각적 개체 코드에서 `renderingFailed` 메서드를 호출하여 렌더링 프로세스가 완료되지 않았음을 수신기에 알려야 합니다. 이 메서드는 실패 원인을 나타내는 선택적 문자열도 제공합니다.

## <a name="usage"></a>사용량

```typescript
export interface IVisualHost extends extensibility.IVisualHost {
    eventService: IVisualEventService ;
}

/**
 * An interface for reporting rendering events
 */
export interface IVisualEventService {
    /**
     * Should be called just before the actual rendering was started. 
     * Usually at the very start of the update method.
     *
     * @param options - the visual update options received as update parameter
     */
    renderingStarted(options: VisualUpdateOptions): void;

    /**
     * Shoudl be called immediately after finishing successfull rendering.
     * 
     * @param options - the visual update options received as update parameter
     */
    renderingFinished(options: VisualUpdateOptions): void;

    /**
     * Called when rendering failed with optional reason string
     * 
     * @param options - the visual update options received as update parameter
     * @param reason - the option failure reason string
     */
    renderingFailed(options: VisualUpdateOptions, reason?: string): void;
}
```

### <a name="simple-sample-the-visual-hasnt-any-animations-on-rendering"></a>간단한 샘플입니다. 이 시각적 개체는 렌더링 시 애니메이션이 없습니다.

```typescript
    export class Visual implements IVisual {
        ...
        private events: IVisualEventService;
        ...

        constructor(options: VisualConstructorOptions) {
            ...
            this.events = options.host.eventService;
            ...
        }

        public update(options: VisualUpdateOptions) {
            this.events.renderingStarted(options);
            ...
            this.events.renderingFinished(options);
        }
```

### <a name="sample-the-visual-with-animation"></a>샘플입니다. 애니메이션이 포함된 시각적 개체

시각적 개체에 렌더링할 애니메이션 또는 비동기 함수가 있는 경우 애니메이션 이후 또는 비동기 함수 내에서 `renderingFinished` 메서드를 호출해야 합니다.

```typescript
    export class Visual implements IVisual {
        ...
        private events: IVisualEventService;
        private element: HTMLElement;
        ...

        constructor(options: VisualConstructorOptions) {
            ...
            this.events = options.host.eventService;
            this.element = options.element;
            ...
        }

        public update(options: VisualUpdateOptions) {
            this.events.renderingStarted(options);
            ...
            // read more https://github.com/d3/d3-transition/blob/master/README.md#transition_end
            d3.select(this.element).transition().duration(100).style("opacity","0").end().then(() => {
                // renderingFinished called after transition end
                this.events.renderingFinished(options);
            });
        }
```

## <a name="rendering-events-for-visual-certification"></a>시각적 개체 인증을 위한 렌더링 이벤트

시각적 개체의 렌더링 이벤트 지원은 시각적 개체 인증 요구 사항 중 하나입니다. [인증 요구 사항에 대한 자세한 정보](https://docs.microsoft.com/power-bi/power-bi-custom-visuals-certified?#certification-requirements)
