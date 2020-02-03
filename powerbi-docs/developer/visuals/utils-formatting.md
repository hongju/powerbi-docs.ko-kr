---
title: Power BI 시각적 개체에서 서식 유틸리티 사용 소개
description: 이 문서에서는 서식 유틸리티를 사용하여 값의 형식을 지정하고 Power BI 시각적 개체의 값에 지역화를 적용하는 방법을 설명합니다.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: rkarlin
manager: rkarlin
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 9ae7e4b976cef2217c3742ef808a9a7063695cbc
ms.sourcegitcommit: 0cc594ebb78a6d0e88784673ed09f8aefd10c7a7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76819471"
---
# <a name="formatting-utils"></a>유틸리티 서식 지정

서식 유틸리티에는 값에 서식을 지정하는 데 사용할 클래스, 인터페이스 및 메서드가 포함됩니다. 문자열을 처리하고 SVG/HTML 문서의 텍스트 크기를 측정하는 확장 메서드도 포함됩니다.

## <a name="text-measurement-service"></a>텍스트 측정 서비스

이 모듈은 다음과 같은 함수와 인터페이스를 제공합니다.

### <a name="textproperties-interface"></a>TextProperties 인터페이스

이 인터페이스는 텍스트의 일반 속성을 설명합니다.

```typescript
interface TextProperties {
    text?: string;
    fontFamily: string;
    fontSize: string;
    fontWeight?: string;
    fontStyle?: string;
    fontVariant?: string;
    whiteSpace?: string;
}
```

### <a name="measuresvgtextwidth"></a>measureSvgTextWidth

이 함수는 지정된 SVG 텍스트 속성을 사용하여 텍스트의 너비를 측정합니다.

```typescript
function measureSvgTextWidth(textProperties: TextProperties, text?: string): number;
```

`measureSvgTextWidth` 사용 예제:

```typescript
import { textMeasurementService } from "powerbi-visuals-utils-formattingutils";
import TextProperties = textMeasurementService.TextProperties;
// ...

let textProperties: TextProperties = {
    text: "Microsoft PowerBI",
    fontFamily: "sans-serif",
    fontSize: "24px"
};

textMeasurementService.measureSvgTextWidth(textProperties);

// returns: 194.71875
```

### <a name="measuresvgtextrect"></a>measureSvgTextRect

이 함수는 지정된 SVG 텍스트 속성을 사용하여 직사각형을 반환합니다.

```typescript
function measureSvgTextRect(textProperties: TextProperties, text?: string): SVGRect;
```

`measureSvgTextRect` 사용 예제:

```typescript
import { textMeasurementService } from "powerbi-visuals-utils-formattingutils";
import TextProperties = textMeasurementService.TextProperties;
// ...

let textProperties: TextProperties = {
    text: "Microsoft PowerBI",
    fontFamily: "sans-serif",
    fontSize: "24px"
};

textMeasurementService.measureSvgTextRect(textProperties);

// returns: { x: 0, y: -22, width: 194.71875, height: 27 }
```

### <a name="measuresvgtextheight"></a>measureSvgTextHeight

이 함수는 지정된 SVG 텍스트 속성을 사용하여 텍스트의 높이를 측정합니다.

```typescript
function measureSvgTextHeight(textProperties: TextProperties, text?: string): number;
```

`measureSvgTextHeight` 사용 예제:

```typescript
import { textMeasurementService } from "powerbi-visuals-utils-formattingutils";
import TextProperties = textMeasurementService.TextProperties;
// ...


let textProperties: TextProperties = {
    text: "Microsoft PowerBI",
    fontFamily: "sans-serif",
    fontSize: "24px"
};

textMeasurementService.measureSvgTextHeight(textProperties);

// returns: 27
```

### <a name="estimatesvgtextbaselinedelta"></a>estimateSvgTextBaselineDelta

이 함수는 지정된 SVG 텍스트 속성을 사용하여 기준을 반환합니다.

```typescript
function estimateSvgTextBaselineDelta(textProperties: TextProperties): number;
```

예제:

```typescript
import { textMeasurementService } from "powerbi-visuals-utils-formattingutils";
import TextProperties = textMeasurementService.TextProperties;
// ...

let textProperties: TextProperties = {
    text: "Microsoft PowerBI",
    fontFamily: "sans-serif",
    fontSize: "24px"
};

textMeasurementService.estimateSvgTextBaselineDelta(textProperties);

// returns: 5
```

### <a name="estimatesvgtextheight"></a>estimateSvgTextHeight

이 함수는 지정된 SVG 텍스트 속성을 사용하여 텍스트의 높이를 추정합니다.

```typescript
function estimateSvgTextHeight(textProperties: TextProperties, tightFightForNumeric?: boolean): number;
```

`estimateSvgTextHeight` 사용 예제:

```typescript
import { textMeasurementService } from "powerbi-visuals-utils-formattingutils";
import TextProperties = textMeasurementService.TextProperties;
// ...

let textProperties: TextProperties = {
    text: "Microsoft PowerBI",
    fontFamily: "sans-serif",
    fontSize: "24px"
};

textMeasurementService.estimateSvgTextHeight(textProperties);

// returns: 27
```

[여기](https://github.com/Microsoft/powerbi-visuals-sankey/blob/4d544ea145b4e15006083a3610dfead3da5f61a4/src/visual.ts#L372)에서 사용자 지정 시각적 개체의 예제 코드를 살펴보세요.

### <a name="measuresvgtextelementwidth"></a>measureSvgTextElementWidth

이 함수는 svgElement의 너비를 측정합니다.

```typescript
function measureSvgTextElementWidth(svgElement: SVGTextElement): number;
```

measureSvgTextElementWidth 사용 예제:

```typescript
import { textMeasurementService } from "powerbi-visuals-utils-formattingutils";
// ...

let svg: D3.Selection = d3.select("body").append("svg");

svg.append("text")
    .text("Microsoft PowerBI")
    .attr({
        "x": 25,
        "y": 25
    })
    .style({
        "font-family": "sans-serif",
        "font-size": "24px"
    });

let textElement: D3.Selection = svg.select("text");

textMeasurementService.measureSvgTextElementWidth(textElement.node());

// returns: 194.71875
```

### <a name="getmeasurementproperties"></a>getMeasurementProperties

이 함수는 지정된 DOM 요소의 텍스트 측정 속성을 가져옵니다.

```typescript
function getMeasurementProperties(element: Element): TextProperties;
```

`getMeasurementProperties` 사용 예제:

```typescript
import { textMeasurementService } from "powerbi-visuals-utils-formattingutils";
// ...

let element: JQuery = $(document.createElement("div"));

element.text("Microsoft PowerBI");

element.css({
    "width": 500,
    "height": 500,
    "font-family": "sans-serif",
    "font-size": "32em",
    "font-weight": "bold",
    "font-style": "italic",
    "white-space": "nowrap"
});

textMeasurementService.getMeasurementProperties(element.get(0));

/* returns: {
    fontFamily:"sans-serif",
    fontSize: "32em",
    fontStyle: "italic",
    fontVariant: "",
    fontWeight: "bold",
    text: "Microsoft PowerBI",
    whiteSpace: "nowrap"
}*/
```

### <a name="getsvgmeasurementproperties"></a>getSvgMeasurementProperties

이 함수는 지정된 SVG 텍스트 요소의 텍스트 측정 속성을 가져옵니다.

```typescript
function getSvgMeasurementProperties(svgElement: SVGTextElement): TextProperties;
```

`getSvgMeasurementProperties` 사용 예제:

```typescript
import { textMeasurementService } from "powerbi-visuals-utils-formattingutils";
// ...

let svg: D3.Selection = d3.select("body").append("svg");

let textElement: D3.Selection = svg.append("text")
    .text("Microsoft PowerBI")
    .attr({
        "x": 25,
        "y": 25
    })
    .style({
        "font-family": "sans-serif",
        "font-size": "24px"
    });

textMeasurementService.getSvgMeasurementProperties(textElement.node());

/* returns: {
    "text": "Microsoft PowerBI",
    "fontFamily": "sans-serif",
    "fontSize": "24px",
    "fontWeight": "normal",
    "fontStyle": "normal",
    "fontVariant": "normal",
    "whiteSpace": "nowrap"
}*/
```

## <a name="getdivelementwidth"></a>getDivElementWidth

이 함수는 div 요소의 너비를 반환합니다.

```typescript
function getDivElementWidth(element: JQuery): string;
```

`getDivElementWidth` 사용 예제:

```typescript
import { textMeasurementService } from "powerbi-visuals-utils-formattingutils";
// ...

let svg: Element = d3.select("body")
    .append("div")
    .style({
        "width": "150px",
        "height": "150px"
    })
    .node();

textMeasurementService.getDivElementWidth(svg)

// returns: 150px
```

### <a name="gettailoredtextordefault"></a>getTailoredTextOrDefault

레이블 텍스트 크기를 사용 가능한 크기와 비교하고 사용 가능한 크기가 더 작은 경우 줄임표를 렌더링합니다.

```typescript
function getTailoredTextOrDefault(textProperties: TextProperties, maxWidth: number): string;
```

`getTailoredTextOrDefault` 사용 예제:

```typescript
import { textMeasurementService } from "powerbi-visuals-utils-formattingutils";
import TextProperties = textMeasurementService.TextProperties;
// ...

let textProperties: TextProperties = {
    text: "Microsoft PowerBI!",
    fontFamily: "sans-serif",
    fontSize: "24px"
};

textMeasurementService.getTailoredTextOrDefault(textProperties, 100);

// returns: Micros...
```

## <a name="string-extensions"></a>문자열 확장

이 모듈은 다음과 같은 함수를 제공합니다.

## <a name="endswith"></a>endsWith

이 함수는 문자열이 substring으로 끝나는지 확인합니다.

```typescript
function endsWith(str: string, suffix: string): boolean;
```

`endsWith` 사용 예제:

```typescript
import { stringExtensions } from "powerbi-visuals-utils-formattingutils";
// ...

stringExtensions.endsWith("Power BI", "BI");

// returns: true
```

### <a name="equalignorecase"></a>equalIgnoreCase

이 함수는 대소문자를 무시한 채로 문자열을 비교합니다.

```typescript
function equalIgnoreCase(a: string, b: string): boolean;
```

`equalIgnoreCase` 사용 예제:

```typescript
import { stringExtensions } from "powerbi-visuals-utils-formattingutils";
// ...

stringExtensions.equalIgnoreCase("Power BI", "power bi");

// returns: true
```

### <a name="startswith"></a>startsWith

이 함수는 문자열이 substring으로 시작하는지 확인합니다.

```typescript
function startsWith(a: string, b: string): boolean;
```

`startsWith` 사용 예제:

```typescript
import { stringExtensions } from "powerbi-visuals-utils-formattingutils";
// ...

stringExtensions.startsWith("Power BI", "Power");

// returns: true
```

### <a name="contains"></a>포함

이 함수는 문자열이 지정된 substring을 포함하는지 확인합니다.

```typescript
function contains(source: string, substring: string): boolean;
```

`contains` 메서드 사용 예제:

```typescript
import { stringExtensions } from "powerbi-visuals-utils-formattingutils";
// ...

stringExtensions.contains("Microsoft Power BI Visuals", "Power BI");

// returns: true
```

### <a name="isnullorempty"></a>isNullOrEmpty

문자열이 Null인지 정의되지 않았는지 또는 비어 있는지 확인합니다.

```typescript
function isNullOrEmpty(value: string): boolean;
```

`isNullOrEmpty` 메서드 예제:

```typescript
import { stringExtensions } from "powerbi-visuals-utils-formattingutils";
// ...

stringExtensions.isNullOrEmpty(null);

// returns: true
```

## <a name="value-formatter"></a>값 포맷터

이 모듈은 다음과 같은 함수, 인터페이스, 클래스를 제공합니다.

## <a name="ivalueformatter"></a>IValueFormatter

이 인터페이스는 포맷터의 공용 메서드와 속성을 설명합니다.

```typescript
interface IValueFormatter {
    format(value: any): string;
    displayUnit?: DisplayUnit;
    options?: ValueFormatterOptions;
}
```

### <a name="ivalueformatterformat"></a>IValueFormatter.format

이 메서드는 지정된 값의 형식을 지정합니다.

```typescript
function format(value: any, format?: string, allowFormatBeautification?: boolean): string;
```

`IValueFormatter.format` 예제:

#### <a name="the-thousand-formats"></a>천 단위 형식

```typescript
import { valueFormatter } from "powerbi-visuals-utils-formattingutils";

let iValueFormatter = valueFormatter.create({ value: 1001 });

iValueFormatter.format(5678);

// returns: "5.68K"
```

#### <a name="the-million-formats"></a>백만 단위 형식

```typescript
import { valueFormatter } from "powerbi-visuals-utils-formattingutils";

let iValueFormatter = valueFormatter.create({ value: 1e6 });

iValueFormatter.format(1234567890);

// returns: "1234.57M"
```

#### <a name="the-billion-formats"></a>10억 단위 형식

```typescript
import { valueFormatter } from "powerbi-visuals-utils-formattingutils";

let iValueFormatter = valueFormatter.create({ value: 1e9 });

iValueFormatter.format(1234567891236);

// returns: 1234.57bn
```

#### <a name="the-trillion-format"></a>1조 단위 형식

```typescript
import { valueFormatter } from "powerbi-visuals-utils-formattingutils";

let iValueFormatter = valueFormatter.create({ value: 1e12 });

iValueFormatter.format(1234567891236);

// returns: 1.23T
```

#### <a name="the-exponent-format"></a>지수 형식

```typescript
import { valueFormatter } from "powerbi-visuals-utils-formattingutils";

let iValueFormatter = valueFormatter.create({ format: "E" });

iValueFormatter.format(1234567891236);

// returns: 1.234568E+012
```

### <a name="the-culture-selector"></a>문화권 선택기

```typescript
import { valueFormatter } from "powerbi-visuals-utils-formattingutils";

let valueFormatterUK = valueFormatter.create({ cultureSelector: "en-GB" });

valueFormatterUK.format(new Date(2007, 2, 3, 17, 42, 42));

// returns: 03/03/2007 17:42:42

let valueFormatterUSA = valueFormatter.create({ cultureSelector: "en-US" });

valueFormatterUSA.format(new Date(2007, 2, 3, 17, 42, 42));

// returns: 3/3/2007 5:42:42 PM
```

#### <a name="the-percentage-format"></a>백분율 형식

```typescript
import { valueFormatter } from "powerbi-visuals-utils-formattingutils";

let iValueFormatter = valueFormatter.create({ format: "0.00 %;-0.00 %;0.00 %" });

iValueFormatter.format(0.54);

// returns: 54.00 %
```

#### <a name="the-dates-format"></a>날짜 형식

```typescript
import { valueFormatter } from "powerbi-visuals-utils-formattingutils";

let date = new Date(2016, 10, 28, 15, 36, 0),
    iValueFormatter = valueFormatter.create({});

iValueFormatter.format(date);

// returns: 11/28/2016 3:36:00 PM
```

#### <a name="the-boolean-format"></a>부울 형식

```typescript
import { valueFormatter } from "powerbi-visuals-utils-formattingutils";

let iValueFormatter = valueFormatter.create({});

iValueFormatter.format(true);

// returns: True
```

#### <a name="the-customized-precision"></a>사용자 지정 정밀도

```typescript
import { valueFormatter } from "powerbi-visuals-utils-formattingutils";

let iValueFormatter = valueFormatter.create({ value: 0, precision: 3 });

iValueFormatter.format(3.141592653589793);

// returns: 3.142
```

[여기](https://github.com/Microsoft/powerbi-visuals-sankey/blob/4d544ea145b4e15006083a3610dfead3da5f61a4/src/visual.ts#L359)에서 사용자 지정 시각적 개체의 예제 코드를 살펴보세요.

## <a name="valueformatteroptions"></a>ValueFormatterOptions

이 인터페이스는 IValueFormatter의 `options`와 ‘create’ 함수의 옵션을 설명합니다.

```typescript
import { valueFormatter } from "powerbi-visuals-utils-formattingutils";
import ValueFormatterOptions = valueFormatter.ValueFormatterOptions;

interface ValueFormatterOptions {
    /** The format string to use. */
    format?: string;
    /** The data value. */
    value?: any;
    /** The data value. */
    value2?: any;
    /** The number of ticks. */
    tickCount?: any;
    /** The display unit system to use */
    displayUnitSystemType?: DisplayUnitSystemType;
    /** True if we are formatting single values in isolation (e.g. card), as opposed to multiple values with a common base (e.g. chart axes) */
    formatSingleValues?: boolean;
    /** True if we want to trim off unnecessary zeroes after the decimal and remove a space before the % symbol */
    allowFormatBeautification?: boolean;
    /** Specifies the maximum number of decimal places to show*/
    precision?: number;
    /** Detect axis precision based on value */
    detectAxisPrecision?: boolean;
    /** Specifies the column type of the data value */
    columnType?: ValueTypeDescriptor;
    /** Specifies the culture */
    cultureSelector?: string;
}
```

## <a name="create"></a>만들기

이 메서드는 IValueFormatter의 인스턴스를 만듭니다.

```typescript
import { valueFormatter } from "powerbi-visuals-utils-formattingutils";
import create = valueFormatter.create;

function create(options: ValueFormatterOptions): IValueFormatter;
```

### <a name="example-of-using-create"></a>create 사용 예제

```typescript
import { valueFormatter } from "powerbi-visuals-utils-formattingutils";

valueFormatter.create({});

// returns: an instance of IValueFormatter.
```

## <a name="next-steps"></a>다음 단계

[Power BI 사용자 지정 시각적 개체에 지역화 추가](localization.md)  
