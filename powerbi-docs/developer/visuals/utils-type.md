---
title: Power BI 시각적 개체에서 형식 유틸리티를 사용하는 방법 소개
description: 이 문서에서는 SVG 유틸리티를 사용하여 Power BI 시각적 개체의 기본 형식을 확장하는 방법을 설명합니다.
author: KesemSharabi
ms.author: kesharab
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 206fda4e64dd13782753bfd067c962b3079bb4ff
ms.sourcegitcommit: 0cc594ebb78a6d0e88784673ed09f8aefd10c7a7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76818735"
---
# <a name="type-utils"></a>형식 유틸리티

TypeUtils는 Power BI 시각적 개체의 기본 형식을 확장하는 함수 및 클래스 세트입니다.

## <a name="installation"></a>설치

패키지를 설치하려면 현재 사용자 지정 시각적 개체가 있는 디렉터리에서 다음 명령을 실행해야 합니다.

npm install powerbi-visuals-utils-typeutils --save 이 명령은 패키지를 설치하고 package.json에 패키지를 종속성으로 추가합니다.

## <a name="double"></a>Double

`Double`은 숫자의 정밀도를 조작하는 기능을 제공합니다.

이 모듈은 다음과 같은 함수를 제공합니다.

### <a name="pow10"></a>pow10

이 함수는 10의 거듭제곱을 반환합니다.

```typescript
function pow10(exp: number): number;
```

예제:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.pow10(25);

// returns: 1e+25
```

### <a name="log10"></a>log10

이 함수는 숫자의 밑수 10 로그를 반환합니다.

```typescript
function log10(val: number): number;
```

예제:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.log10(25);

// returns: 1
```

## <a name="getprecision"></a>getPrecision

이 함수는 숫자의 정밀도를 나타내는 10의 거듭제곱을 반환합니다.

```typescript
function getPrecision(x: number, decimalDigits?: number): number;
```

예제:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.getPrecision(562344, 6);

// returns: 0.1
```

### <a name="equalwithprecision"></a>equalWithPrecision

이 함수는 두 숫자 사이의 델타가 제공된 정밀도보다 작은지 확인합니다.

```typescript
function equalWithPrecision(x: number, y: number, precision?: number): boolean;
```

예제:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.equalWithPrecision(1, 1.005, 0.01);

// returns: true
```

### <a name="lesswithprecision"></a>lessWithPrecision

이 함수는 첫 번째 값이 두 번째 값보다 작은지 확인합니다.

```typescript
function lessWithPrecision(x: number, y: number, precision?: number): boolean;
```

예제:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.lessWithPrecision(0.995, 1, 0.001);

// returns: true
```

### <a name="lessorequalwithprecision"></a>lessOrEqualWithPrecision

이 함수는 첫 번째 값이 두 번째 값보다 작거나 같은지 확인합니다.

```typescript
function lessOrEqualWithPrecision(x: number, y: number, precision?: number): boolean;
```

예제:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.lessOrEqualWithPrecision(1.005, 1, 0.01);

// returns: true
```

### <a name="greaterwithprecision"></a>greaterWithPrecision

이 함수는 첫 번째 값이 두 번째 값보다 큰지 확인합니다.

```typescript
function greaterWithPrecision(x: number, y: number, precision?: number): boolean;
```

예제:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.greaterWithPrecision(1, 0.995, 0.01);

// returns: false
```

### <a name="greaterorequalwithprecision"></a>greaterOrEqualWithPrecision

이 함수는 첫 번째 값이 두 번째 값보다 크거나 같은지 확인합니다.

```typescript
function greaterOrEqualWithPrecision(x: number, y: number, precision?: number): boolean;
```

예제:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.greaterOrEqualWithPrecision(1, 1.005, 0.01);

// returns: true
```

### <a name="floorwithprecision"></a>floorWithPrecision

이 함수는 숫자를 제공된 정밀도로 내립니다.

```typescript
function floorWithPrecision(x: number, precision?: number): number;
```

예제:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.floorWithPrecision(5.96, 0.001);

// returns: 5
```

### <a name="ceilwithprecision"></a>ceilWithPrecision

이 함수는 숫자를 제공된 정밀도로 올립니다(`ceils`).

```typescript
function ceilWithPrecision(x: number, precision?: number): number;
```

예제:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.ceilWithPrecision(5.06, 0.001);

// returns: 6
```

### <a name="floortoprecision"></a>floorToPrecision

이 함수는 숫자를 제공된 정밀도로 내립니다.

```typescript
function floorToPrecision(x: number, precision?: number): number;
```

예제:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.floorToPrecision(5.96, 0.1);

// returns: 5.9
```

### <a name="ceiltoprecision"></a>ceilToPrecision

이 함수는 숫자를 제공된 정밀도로 올립니다(`ceils`).

```typescript
function ceilToPrecision(x: number, precision?: number): number;
```

예제:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.ceilToPrecision(-506, 10);

// returns: -500
```

### <a name="roundtoprecision"></a>roundToPrecision

이 함수는 숫자를 제공된 정밀도로 반올림합니다.

```typescript
function roundToPrecision(x: number, precision?: number): number;
```

예제:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.roundToPrecision(596, 10);

// returns: 600
```

### <a name="ensureinrange"></a>ensureInRange

이 함수는 min과 max 사이의 숫자를 반환합니다.

```typescript
function ensureInRange(x: number, min: number, max: number): number;
```

예제:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.ensureInRange(-27.2, -10, -5);

// returns: -10
```

### <a name="round"></a>round

이 함수는 숫자를 반올림합니다.

```typescript
function round(x: number): number;
```

예제:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.round(27.45);

// returns: 27
```

### <a name="removedecimalnoise"></a>removeDecimalNoise

이 함수는 소수 노이즈를 제거합니다.

```typescript
function removeDecimalNoise(value: number): number;
```

예제:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.removeDecimalNoise(21.493000000000002);

// returns: 21.493
```

### <a name="isinteger"></a>isInteger

이 함수는 숫자가 정수인지 확인합니다.

```typescript
function isInteger(value: number): boolean;
```

예제:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.isInteger(21.493000000000002);

// returns: false
```

### <a name="toincrement"></a>toIncrement

이 함수는 숫자를 제공된 숫자만큼 늘리고 반올림된 숫자를 반환합니다.

```typescript
function toIncrement(value: number, increment: number): number;
```

예제:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.toIncrement(0.6383723, 0.05);

// returns: 0.65
```

## <a name="prototype"></a>원형 구축

`Prototype`은 개체 상속 기능을 제공합니다.

이 모듈은 다음과 같은 함수를 제공합니다.

## <a name="inherit"></a>inherit

이 함수는 제공된 개체를 프로토타입으로 사용하여 새 개체를 반환합니다.

```typescript
function inherit<T>(obj: T, extension?: (inherited: T) => void): T;
```

예제:

```typescript
import { prototype } from "powerbi-visuals-utils-typeutils";
// ...

let base = { Microsoft: "Power BI" };

prototype.inherit(base);

/* returns: {
    __proto__: {
        Microsoft: "Power BI"
    }
}*/
```

## <a name="inheritsingle"></a>inheritSingle

이 함수는 프로토타입이 설정되지 않은 경우에만 제공된 개체를 프로토타입으로 사용하여 새 개체를 반환합니다.

```typescript
function inheritSingle<T>(obj: T): T;
```

예제:

```typescript
import { prototype } from "powerbi-visuals-utils-typeutils";
// ...

let base = { Microsoft: "Power BI" };

prototype.inheritSingle(base);

/* returns: {
    __proto__: {
        Microsoft: "Power BI"
    }
}*/
```

## <a name="pixelconverter"></a>PixelConverter

`PixelConverter`는 픽셀을 포인트로 변환하고 포인트를 픽셀로 변환하는 기능을 제공합니다.

이 모듈은 다음과 같은 함수를 제공합니다.

## <a name="tostring"></a>toString

이 함수는 픽셀 값을 문자열로 변환합니다.

```typescript
function toString(px: number): string;
```

예제:

```typescript
import { pixelConverter } from "powerbi-visuals-utils-typeutils";
// ...

pixelConverter.toString(25);

// returns: 25px
```

## <a name="frompoint"></a>fromPoint

이 함수는 제공된 포인트 값을 픽셀 값으로 변환하고 문자열 해석을 반환합니다.

```typescript
function fromPoint(pt: number): string;
```

예제:

```typescript
import { pixelConverter } from "powerbi-visuals-utils-typeutils";
// ...

pixelConverter.fromPoint(8);

// returns: 33.33333333333333px
```

## <a name="frompointtopixel"></a>fromPointToPixel

이 함수는 제공된 포인트 값을 픽셀 값으로 변환합니다.

```typescript
function fromPointToPixel(pt: number): number;
```

예제:

```typescript
import { pixelConverter } from "powerbi-visuals-utils-typeutils";
// ...

pixelConverter.fromPointToPixel(8);

// returns: 10.666666666666666
```

## <a name="topoint"></a>toPoint

이 함수는 픽셀 값을 포인트 값으로 변환합니다.

```typescript
function toPoint(px: number): number;
```

예제:

```typescript
import { pixelConverter } from "powerbi-visuals-utils-typeutils";
// ...

pixelConverter.toPoint(8);

// returns: 6
```
