---
title: Power BI 시각적 개체에서 SVG 유틸리티를 사용하는 방법 소개
description: 이 문서에서는 SVG 유틸리티를 사용하여 Power BI 사용자 지정 시각적 개체의 SVG 조작을 간소화하는 방법을 설명합니다.
author: vtkalek
ms.author: asander
manager: asander
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 15398c0e8d7322e29c502f49b8c1ea0798f52afe
ms.sourcegitcommit: 4359baa43ca01b179d28ec59f4e61ba8c07ee288
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75308528"
---
# <a name="svg-utils"></a>SVG 유틸리티

SVGUtils는 Power BI 사용자 지정 시각적 개체의 SVG 조작을 간소화하는 함수 및 클래스 세트입니다.

## <a name="installation"></a>설치

패키지를 설치하려면 현재 시각적 개체가 있는 디렉터리에서 다음 명령을 실행해야 합니다.

```bash
npm install powerbi-visuals-utils-svgutils --save
```

## <a name="cssconstants"></a>CssConstants

`CssConstants` 모듈은 클래스 선택기 작업을 위한 특수 함수와 인터페이스를 제공합니다.

`powerbi.extensibility.utils.svg.CssConstants` 모듈은 다음과 같은 함수와 인터페이스를 제공합니다.

## <a name="classandselector"></a>ClassAndSelector

이 인터페이스는 클래스 선택기의 일반 속성을 설명합니다.

```typescript
interface ClassAndSelector {
  class: string;
  selector: string;
}
```

### <a name="createclassandselector"></a>createClassAndSelector

이 함수는 주어진 클래스 이름을 사용하여 ClassAndSelector의 인스턴스를 만듭니다.

```typescript
function createClassAndSelector(className: string): ClassAndSelector;
```

예제:

```typescript
import { CssConstants } from "powerbi-visuals-utils-svgutils";
import createClassAndSelector = CssConstants.createClassAndSelector;
import ClassAndSelector = CssConstants.ClassAndSelector;

let divSelector: ClassAndSelector = createClassAndSelector("sample-block");

divSelector.selector === ".sample-block"; // returns: true
divSelector.class === "sample-block"; // returns: true
```

## <a name="manipulation"></a>manipulation

`manipulation`에서는 SVG transform 속성에 사용할 문자열을 생성하는 몇 가지 특수 함수를 제공합니다.

이 모듈은 다음과 같은 함수를 제공합니다.

### <a name="translate"></a>translate

이 함수는 SVG transform 속성에 사용할 translate 문자열을 만듭니다.

```typescript
function translate(x: number, y: number): string;
```

예제:

```typescript
import { manipulation } from "powerbi-visuals-utils-svgutils";
// ...

manipulation.translate(100, 100);

// returns: translate(100,100)
```

### <a name="translatexwithpixels"></a>translateXWithPixels

이 함수는 SVG transform 속성에 사용할 translateX 문자열을 만듭니다.

```typescript
function translateXWithPixels(x: number): string;
```

예제:

```typescript
import { manipulation } from "powerbi-visuals-utils-svgutils";
// ...

manipulation.translateXWithPixels(100);

// returns: translateX(100px)
```

### <a name="translatewithpixels"></a>translateWithPixels

이 함수는 SVG transform 속성에 사용할 translate 문자열을 만듭니다.

```typescript
function translateWithPixels(x: number, y: number): string;
```

예제:

```typescript
import { manipulation } from "powerbi-visuals-utils-svgutils";
// ...

manipulation.translateWithPixels(100, 100);

// returns: translate(100px,100px)
```

### <a name="translateandrotate"></a>translateAndRotate

이 함수는 SVG transform 속성에 사용할 translate-rotate 문자열을 만듭니다.

```typescript
function translateAndRotate(
  x: number,
  y: number,
  px: number,
  py: number,
  angle: number
): string;
```

예제:

```typescript
import { manipulation } from "powerbi-visuals-utils-svgutils";
// ...

manipulation.translateAndRotate(100, 100, 50, 50, 35);

// returns: translate(100,100) rotate(35,50,50)
```

### <a name="scale"></a>소수 자릿수

이 함수는 CSS transform 속성에 사용할 scale 문자열을 만듭니다.

```typescript
function scale(scale: number): string;
```

예제:

```typescript
import { manipulation } from "powerbi-visuals-utils-svgutils";
// ...

manipulation.scale(50);

// returns: scale(50)
```

### <a name="transformorigin"></a>transformOrigin

이 함수는 CSS transform-origin 속성에 사용할 transform-origin 문자열을 만듭니다.

```typescript
function transformOrigin(xOffset: string, yOffset: string): string;
```

예제:

```typescript
import { manipulation } from "powerbi-visuals-utils-svgutils";
// ...

manipulation.transformOrigin(5, 5);

// returns: 5 5
```

### <a name="flushalld3transitions"></a>flushAllD3Transitions

이 함수는 D3의 모든 전환을 강제로 완료합니다.

```typescript
function flushAllD3Transitions(): void;
```

예제:

```typescript
import { manipulation } from "powerbi-visuals-utils-svgutils";
// ...

manipulation.flushAllD3Transitions();

// forces every transition of D3 to complete
```

### <a name="parsetranslatetransform"></a>parseTranslateTransform

이 함수는 “transform(x, y)” 값을 사용하여 transform 문자열을 구문 분석합니다.

```typescript
function parseTranslateTransform(input: string): { x: string; y: string };
```

예제:

```typescript
import { manipulation } from "powerbi-visuals-utils-svgutils";
// ...

manipulation.parseTranslateTransform("translate(100px,100px)");

// returns: { "x":"100px", "y":"100px" }
```

### <a name="createarrow"></a>createArrow

이 함수는 화살표를 만듭니다.

```typescript
function createArrow(
  width: number,
  height: number,
  rotate: number
): { path: string; transform: string };
```

예제:

```typescript
import { manipulation } from "powerbi-visuals-utils-svgutils";
// ...

manipulation.createArrow(10, 20, 5);

/* returns: {
    "path": "M0 0L0 20L10 10 Z",
    "transform": "rotate(5 5 10)"
}*/
```

## <a name="rect"></a>Rect

`Rect` 모듈은 사각형을 조작하는 몇 가지 특수 함수를 제공합니다.

이 모듈은 다음과 같은 함수를 제공합니다.

### <a name="getoffset"></a>getOffset

이 함수는 사각형의 오프셋을 반환합니다.

```typescript
function getOffset(rect: IRect): IPoint;
```

예제:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.getOffset({ left: 25, top: 25, width: 100, height: 100 });

/* returns: {
    x: 25,
    y: 25
}*/
```

### <a name="getsize"></a>getSize

이 함수는 사각형의 크기를 반환합니다.

```typescript
function getSize(rect: IRect): ISize;
```

예제:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.getSize({ left: 25, top: 25, width: 100, height: 100 });

/* returns: {
    width: 100,
    height: 100
}*/
```

### <a name="setsize"></a>setSize

이 함수는 사각형의 크기를 수정합니다.

```typescript
function setSize(rect: IRect, value: ISize): void;
```

예제:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

let rectangle = { left: 25, top: 25, width: 100, height: 100 };

Rect.setSize(rectangle, { width: 250, height: 250 });

// rectangle === { left: 25, top: 25, width: 250, height: 250 }
```

### <a name="right"></a>right

이 함수는 사각형의 오른쪽 위치를 반환합니다.

```typescript
function right(rect: IRect): number;
```

예제:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.right({ left: 25, top: 25, width: 100, height: 100 });

// returns: 125
```

### <a name="bottom"></a>bottom

이 함수는 사각형의 아래쪽 위치를 반환합니다.

```typescript
function bottom(rect: IRect): number;
```

예제:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.bottom({ left: 25, top: 25, width: 100, height: 100 });

// returns: 125
```

### <a name="topleft"></a>topLeft

이 함수는 사각형의 왼쪽 위 위치를 반환합니다.

```typescript
function topLeft(rect: IRect): IPoint;
```

예제:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.topLeft({ left: 25, top: 25, width: 100, height: 100 });

// returns: { x: 25, y: 25 }
```

### <a name="topright"></a>topRight

이 함수는 사각형의 오른쪽 위 위치를 반환합니다.

```typescript
function topRight(rect: IRect): IPoint;
```

예제:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.topRight({ left: 25, top: 25, width: 100, height: 100 });

// returns: { x: 125, y: 25 }
```

### <a name="bottomleft"></a>bottomLeft

이 함수는 사각형의 왼쪽 아래 위치를 반환합니다.

```typescript
function bottomLeft(rect: IRect): IPoint;
```

예제:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.bottomLeft({ left: 25, top: 25, width: 100, height: 100 });

// returns: { x: 25, y: 125 }
```

### <a name="bottomright"></a>bottomRight

이 함수는 사각형의 오른쪽 아래 위치를 반환합니다.

```typescript
function bottomRight(rect: IRect): IPoint;
```

### <a name="example"></a>예제

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.bottomRight({ left: 25, top: 25, width: 100, height: 100 });

// returns: { x: 125, y: 125 }
```

### <a name="clone"></a>복제

이 함수는 사각형의 복사본을 만듭니다.

```typescript
function clone(rect: IRect): IRect;
```

예제:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.clone({ left: 25, top: 25, width: 100, height: 100 });

/* returns: {
    left: 25, top: 25, width: 100, height: 100}
*/
```

### <a name="tostring"></a>toString

이 함수는 사각형을 문자열로 변환합니다.

```typescript
function toString(rect: IRect): string;
```

예제:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.toString({ left: 25, top: 25, width: 100, height: 100 });

// returns: {left:25, top:25, width:100, height:100}
```

### <a name="offset"></a>offset

이 함수는 사각형에 주어진 오프셋을 적용합니다.

```typescript
function offset(rect: IRect, offsetX: number, offsetY: number): IRect;
```

예제:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.offset({ left: 25, top: 25, width: 100, height: 100 }, 50, 50);

/* returns: {
    left: 75,
    top: 75,
    width: 100,
    height: 100
}*/
```

### <a name="add"></a>add

이 함수는 두 번째 사각형에 첫 번째 사각형을 추가합니다.

```typescript
function add(rect: IRect, rect2: IRect): IRect;
```

예제:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.add(
  { left: 25, top: 25, width: 100, height: 100 },
  { left: 50, top: 50, width: 75, height: 75 }
);

/* returns: {
    left: 75,
    top: 75,
    height: 175,
    width: 175
}*/
```

### <a name="getclosestpoint"></a>getClosestPoint

이 함수는 사각형에서 주어진 지점에 가장 가까운 지점을 반환합니다.

```typescript
function getClosestPoint(rect: IRect, x: number, y: number): IPoint;
```

예제:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.getClosestPoint({ left: 0, top: 0, width: 100, height: 100 }, 50, 50);

/* returns: {
    x: 50,
    y: 50
}*/
```

### <a name="equal"></a>equal

이 함수는 사각형을 비교하고 같으면 true를 반환합니다.

```typescript
function equal(rect1: IRect, rect2: IRect): boolean;
```

예제:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.equal(
  { left: 0, top: 0, width: 100, height: 100 },
  { left: 50, top: 50, width: 100, height: 100 }
);

// returns: false
```

### <a name="equalwithprecision"></a>equalWithPrecision

이 함수는 값의 정밀도를 고려하여 사각형을 비교합니다.

```typescript
function equalWithPrecision(rect1: IRect, rect2: IRect): boolean;
```

예제:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.equalWithPrecision(
  { left: 0, top: 0, width: 100, height: 100 },
  { left: 50, top: 50, width: 100, height: 100 }
);

// returns: false
```

### <a name="isempty"></a>isEmpty

이 함수는 사각형이 비어 있는지 확인합니다.

```typescript
function isEmpty(rect: IRect): boolean;
```

예제:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.isEmpty({ left: 0, top: 0, width: 0, height: 0 });

// returns: true
```

### <a name="containspoint"></a>containsPoint

이 함수는 사각형에 지점이 포함되는지 확인합니다.

```typescript
function containsPoint(rect: IRect, point: IPoint): boolean;
```

예제:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.containsPoint(
  { left: 0, top: 0, width: 100, height: 100 },
  { x: 50, y: 50 }
);

// returns: true
```

### <a name="isintersecting"></a>isIntersecting

이 함수는 사각형이 교차하는지 확인합니다.

```typescript
function isIntersecting(rect1: IRect, rect2: IRect): boolean;
```

예제:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.isIntersecting(
  { left: 0, top: 0, width: 100, height: 100 },
  { left: 0, top: 0, width: 50, height: 50 }
);

// returns: true
```

### <a name="intersect"></a>intersect

이 함수는 사각형의 교집합을 반환합니다.

```typescript
function intersect(rect1: IRect, rect2: IRect): IRect;
```

예제:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.intersect(
  { left: 0, top: 0, width: 100, height: 100 },
  { left: 0, top: 0, width: 50, height: 50 }
);

/* returns: {
    left: 0,
    top: 0,
    width: 50,
    height: 50
}*/
```

### <a name="combine"></a>combine

이 함수는 사각형을 결합합니다.

```typescript
function combine(rect1: IRect, rect2: IRect): IRect;
```

예제:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.combine(
  { left: 0, top: 0, width: 100, height: 100 },
  { left: 0, top: 0, width: 50, height: 120 }
);

/* returns: {
    left: 0,
    top: 0,
    width: 100,
    height: 120
}*/
```

### <a name="getcentroid"></a>getCentroid

이 함수는 사각형의 중심점을 반환합니다.

```typescript
function getCentroid(rect: IRect): IPoint;
```

예제:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.getCentroid({ left: 0, top: 0, width: 100, height: 100 });

/* returns: {
    x: 50,
    y: 50
}*/
```

## <a name="pointer"></a>포인터(pointer)

`pointer` 모듈은 포인터 위치를 가져오는 특수 함수를 제공합니다.

이 모듈은 다음과 같은 함수를 제공합니다.

### <a name="getcoordinates"></a>getCoordinates

이 함수는 포인터 위치를 반환합니다.

```typescript
function getCoordinates(rootNode: Element, isPointerEvent: boolean): number[];
```

예제:

```typescript
import { pointer } from "powerbi-visuals-utils-svgutils";

let bodySelection = d3.select("body");

bodySelection
  .append("div")
  .style({
    width: "100px",
    height: "100px",
    "background-color": "green"
  })
  .on("click", () => {
    pointer.getCoordinates(bodySelection.node(), true);
  });

// click element, after that you will get position of the pointer
```
