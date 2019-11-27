---
title: powerbi-visuals-tools 3.x로 마이그레이션
description: 새 버전의 powerbi-visuals-tools 시작하기
author: zBritva
ms.author: v-ilgali
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: cc554bff1cbd248ccd69a80ee47b60af981cdab1
ms.sourcegitcommit: f7b28ecbad3e51f410eff7ee4051de3652e360e8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74061825"
---
# <a name="migrate-to-the-new-powerbi-visuals-tools-3xx"></a>새 powerbi-visuals-tools 3.x.x로 마이그레이션

버전 3부터 Power BI 시각적 개체 도구는 Webpack을 사용하여 사용자 지정 시각적 개체를 빌드합니다.
새 버전은 개발자가 시각적 개체를 만들 수 있는 여러 가지 새로운 기회를 제공합니다.

* 기본적으로 TypeScript v3.x.x. TypeScript 1.5부터 명명법이 변경되었습니다. [TypeScript 모듈에 대해 자세히 알아보세요](https://www.typescriptlang.org/docs/handbook/modules.html).

* ES6 모듈이 지원됩니다. 더 이상 [externalJS](migrate-to-new-tools.md#fix-loading-external-libraries)를 사용할 필요가 없습니다. 대신 ES6 imports를 사용하세요.

* 새 버전의 [D3v5](https://d3js.org/) 및 기타 ES6 모듈 기반 라이브러리가 지원됩니다.

* 줄어든 패키지 크기. Webpack은 [트리 핸드쉐이킹](https://webpack.js.org/guides/tree-shaking/)을 사용하여 사용되지 않는 코드를 제거합니다. 이는 JS의 코드를 줄여 결과적으로 시각적 개체 로드 성능이 개선됩니다.

* 향상된 API 성능.

* Globalize.js 라이브러리가 formatting-utils에 [통합](migrate-to-new-tools.md#remove-globalizejs-library)되어 있습니다.

* 도구는 [webpack-bundle-analyzer](https://github.com/webpack-contrib/webpack-bundle-analyzer)를 사용하여 시각적 개체의 코드 베이스를 표시합니다.

Power BI 시각적 개체 도구의 새 버전 마이그레이션 단계가 아래에 설명되어 있습니다.

## <a name="backward-compatibility"></a>이전 버전과의 호환성

새 도구는 이전 시각적 개체 코드 베이스에 대한 이전 버전과의 호환성을 유지하지만 외부 라이브러리를 로드하기 위해 몇 가지 변경 사항이 추가로 필요할 수 있습니다.

모듈 시스템을 지원하는 라이브러리는 Webpack 모듈 형태로 가져옵니다. 다른 모든 라이브러리와 시각적 개체 소스 코드는 하나의 모듈에 래핑됩니다.

이전 pbiviz 도구에서 사용되던 JQuery 및 Lodash 같은 전역 변수는 이제 사용되지 않습니다. 즉, 이전 시각적 개체 코드가 전역 변수로 전달되는 경우 시각적 개체가 손상될 수 있습니다.

이전 버전의 Power BI 시각적 개체 도구에서는 `powerbi.extensibility.visual` 모듈 아래에 시각적 개체 클래스를 정의해야 했습니다.

## <a name="how-to-install-powerbi-visuals-tools"></a>powerbi-visuals-tools 설치 방법

새 도구 집합은 다음 명령을 실행하여 설치할 수 있습니다.

```cmd
npm install -g powerbi-visuals-tools
```

sampleBarChart 시각적 개체 및 `package.json` 내 해당 [변경 내용](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/sample-next/package.json#L16)의 샘플:

```json
{
    "name": "visual",
    "version": "1.2.3",
    "scripts": {
        "pbiviz": "pbiviz",
        "start": "pbiviz start",
        "lint": "tslint -r \"node_modules/tslint-microsoft-contrib\"  \"+(src|test)/**/*.ts\"",
        "test": "pbiviz package --resources --no-minify --no-pbiviz"
    },
    "devDependencies": {
      "@types/d3": "5.0.0",
      "d3": "5.5.0",
      "powerbi-visuals-tools": "^3.1.0",
      "tslint": "^4.4.2",
      "tslint-microsoft-contrib": "^4.0.0"
    }
}
```

## <a name="how-to-install-power-bi-custom-visuals-api"></a>Power BI 사용자 지정 시각적 개체 API 설치 방법

새 버전의 powerbi-visual tools에서는 모든 API 버전을 내부에 포함하고 있지 않습니다. 대신 개발자가 특정 버전의 [`powerbi-visuals-api`](https://www.npmjs.com/package/powerbi-visuals-api) 패키지를 설치해야 합니다. 패키지 버전은 Power BI 사용자 지정 시각적 개체 API 버전과 일치하며 Power BI 사용자 지정 시각적 개체 API에 대한 모든 형식 정의를 제공합니다.

`npm install --save-dev powerbi-visuals-api` 명령을 실행하여 `powerbi-visuals-api`를 프로젝트의 종속성에 추가합니다.
그리고 이전 API 형식 정의에 대한 링크를 제거해야 합니다. `powerbi-visuals-api`의 형식은 Webpack에 의해 자동으로 포함되기 때문입니다. 해당하는 변경 내용은 `package.json`의 [이](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/sample-next/package.json#L14) 줄입니다.

## <a name="update-tsconfigjson"></a>`tsconfig.json` 업데이트

외부 모듈을 사용하려면 `out` 옵션을 `outDir`로 전환해야 합니다.
`"out": "./.tmp/build/visual.js",` 대신 `"outDir": "./.tmp/build/",`.

이는 TypeScript 파일이 JavaScript 파일에 독립적으로 컴파일되기 때문에 필요합니다. 그러므로 더 이상 시각적 개체 .js 파일을 출력으로 지정할 필요가 없습니다.

최신 JavaScript를 출력으로 사용하려는 경우에는 `target` 옵션을 `ES6`로 변경할 수도 있습니다. [선택 사항입니다](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/sample-next/tsconfig.json#L6).

## <a name="update-custom-visuals-utils"></a>사용자 지정 시각적 개체 유틸리티 업데이트

[powerbi-visuals-utils](https://www.npmjs.com/search?q=powerbi-visuals-utils) 중 하나를 사용하는 경우 이를 최신 버전으로 업데이트해야 합니다.

`npm install powerbi-visuals-utils-<UTILNAME> --save` 명령 (예: `npm install powerbi-visuals-utils-dataviewutils --save`)을 실행하여 TypeScript의 외부 모듈을 포함하는 새 버전을 가져옵니다.

MekkoChart [리포지토리](https://github.com/Microsoft/powerbi-visuals-mekkochart)에서 예제를 찾을 수 있습니다.
이 시각적 개체는 모든 유틸리티를 사용합니다.

## <a name="remove-globalizejs-library"></a>Globalize.js 라이브러리 제거

새 버전의 [powerbi-visuals-utils-formattingutils@4.3](https://www.npmjs.com/package/powerbi-visuals-utils-formattingutils)에는 기본적으로 globalize.js가 포함되어 있습니다.
이 라이브러리를 수동으로 프로젝트에 포함할 필요가 없습니다.
모든 필수 지역화가 자동으로 최종 패키지에 추가됩니다.

## <a name="fix-loading-external-libraries"></a>외부 라이브러리 로드 수정

대신 `pbiviz.json`의 `externalJS`배열에서 라이브러리 뒤에 새 JS 파일을 포함합니다. 예제:

```JSON
"externalJS": [
    ...
    "node_modules/lodash/lodash.min.js",
    "externalJS/init.lodash.js",
    ...
]
```

원본에서 라이브러리를 가져옵니다. `lodash-es` 예제:

```JS
import * as _ from "lodash-es";
```

여기서 `_`는 `lodash` 라이브러리의 전역 변수입니다.

## <a name="changes-in-the-visuals-sources"></a>시각적 개체 소스 변경 사항

중요한 변경 사항은 내부 모듈을 외부 모듈로 변환하는 것입니다, 내부 모듈에서 외부 모듈을 사용할 수 없기 때문입니다.

이러한 변경 사항은 샘플 가로 막대형 차트에 적용된 수정 내용을 설명합니다.

변경 사항에 대한 자세한 설명은 다음과 같습니다.

1. [소스 코드](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/sample-next/src/barChart.ts#L153)의 각 파일에서 모든 모듈 정의를 제거합니다.

    ```typescript
    module powerbi.extensibility.visual {
        ...
    }
    ```

2. [Power BI 사용자 지정 시각적 개체 API 정의를 가져옵니다](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/sample-next/src/barChart.ts#L2).

    ```typescript
    import powerbi from "powerbi-visuals-api";
    ```

3. `powerbi` 내부 모듈에서 필요한 인터페이스 또는 클래스를 [가져옵니다](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/sample-next/src/barChart.ts#L12-L23).

    ```typescript
    import PrimitiveValue = powerbi.PrimitiveValue; 
    import VisualUpdateOptions = powerbi.extensibility.visual.VisualUpdateOptions; 
    import VisualConstructorOptions = powerbi.extensibility.visual.VisualConstructorOptions; 
    import IVisualHost = powerbi.extensibility.visual.IVisualHost; 
    import IColorPalette = powerbi.extensibility.IColorPalette; 
    import IVisual = powerbi.extensibility.visual.IVisual; 
    import VisualObjectInstance = powerbi.VisualObjectInstance; 
    import VisualObjectInstanceEnumeration = powerbi.VisualObjectInstanceEnumeration; 
    import EnumerateVisualObjectInstancesOptions = powerbi.EnumerateVisualObjectInstancesOptions; 
    import Fill = powerbi.Fill; 
    import VisualTooltipDataItem = powerbi.extensibility.VisualTooltipDataItem; 
    import ISelectionManager = powerbi.extensibility.ISelectionManager; 
    ```

4. D3.js 라이브러리를 [가져옵니다](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/sample-next/src/barChart.ts#L1).

    ```typescript
    import * as d3 from "d3";
    ```

    또는 필요한 d3 라이브러리 모듈만 가져옵니다.

    ```typescript
    import { max, min } from "d3-array";
    ```

5. 시각적 개체 프로젝트에 정의된 유틸리티, 클래스, 인터페이스를 메인 소스 파일로 [가져옵니다](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/sample-next/src/barChart.ts#L4-L10).

    ```typescript
    import { getLocalizedString } from "./localization/localizationHelper";
    import { getValue, getCategoricalObjectValue } from "./objectEnumerationUtility";
    import {
        ITooltipServiceWrapper,
        TooltipEventArgs,
        createTooltipServiceWrapper
    } from "./tooltipServiceWrapper";
    ```

### <a name="import-css-styles"></a>CSS 스타일 가져오기

개발자는 새 버전의 도구를 사용하여 CSS, LESS 스타일을 TypeScript 코드로 직접 가져올 수 있습니다.

따라서 이전에 사용된 [스타일 섹션](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/sample-next/pbiviz.json#L22)은 컴파일러에서 무시됩니다.

스타일시트를 사용하려면 기본 ts 파일을 열고 다음 줄을 추가합니다.  

```typescript
import "./../style/visual.less";
```  

CSS, LESS 스타일은 자동으로 컴파일됩니다.  

### <a name="externaljs-section-in-pbivizjson"></a>pbiviz.json의 externalJS 섹션

도구에서는 `externalJS` 목록을 시각적 개체 번들로 로드하도록 [요구하지 않습니다](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/sample-next/pbiviz.json#L20). Webpack에는 가져온 라이브러리가 모두 포함되어 있기 때문입니다.

**pbivi.json의 externalJS 섹션은 비어 있어야 합니다.**

일반적인 명령 `npm run package`를 호출하여 시각적 개체 패키지를 만들거나 `npm run start`를 호출하여 개발 서버를 시작합니다.

## <a name="updating-d3js-library-to-version-5"></a>D3.js라이브러리를 버전 5로 업데이트

새 도구로 새 버전의 D3.js 라이브러리를 사용하기 시작할 수 있습니다.

시각적 개체 프로젝트에서 D3를 업데이트하는 명령을 호출합니다.

새 D3.js를 설치하는 경우 `npm install --save d3@5`.

D3.js에 대한 새 형식 정의를 설치하는 경우 `npm install --save-dev @types/d3@5`.

몇 가지 중요한 변경 사항이 있으며 새 D3.js를 사용하도록 코드를 수정해야 합니다.

1. 인터페이스 `d3.Selection<T>`이 `Selection<GElement extends BaseType, Datum, PElement extends BaseType, PDatum>`으로 [변경](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/af2ff9fb0fc70bd94ea0c604d75a362411d5abeb#diff-433142f7814fee940a0ffc98dc75bfcbR157)되었습니다.

2. `attr` 메서드를 한 번 호출하여 여러 특성을 적용할 수 없습니다. `attr` 메서드를 여러 번 호출하여 각 특성을 [전달](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/af2ff9fb0fc70bd94ea0c604d75a362411d5abeb#diff-433142f7814fee940a0ffc98dc75bfcbR278)해야 합니다. `style` 메서드도 [비슷합니다](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/af2ff9fb0fc70bd94ea0c604d75a362411d5abeb#diff-433142f7814fee940a0ffc98dc75bfcbR247).

3. D3.js v4에서 새 merge 메서드가 도입되었습니다. 이 메서드는 데이터 조인 후에 입력 및 업데이트 선택 항목을 병합하는 데 주로 사용됩니다. d3를 적절하게 사용하려면 [merge 메서드](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/83fe8d52d362dccd0034dd8e32c94080d9376b29#diff-433142f7814fee940a0ffc98dc75bfcbR272)를 호출합니다.

D3.js 라이브러리의 변경 사항을 [자세히 알아보세요](https://github.com/d3/d3/blob/master/CHANGES.md).

## <a name="babel"></a>Babel

버전 3.1부터 도구는 다양한 브라우저를 지원하기 위해 Babel을 사용하여 새로운 최신 JS 코드를 이전 ES5로 컴파일합니다.

이 옵션은 기본적으로 사용하도록 설정되지만 수동으로 [`@babel/polyfill`](https://babeljs.io/docs/en/babel-polyfill) 패키지를 가져와야 합니다.

명령을 실행하여 패키지를 설치하고

`npm install --save @babel/polyfill`

시각적 개체 코드의 시작 지점에서 패키지를 가져옵니다(일반적으로 'src/visual.ts' 파일).

`import "@babel/polyfill";`

[문서](https://babeljs.io/docs/en/)에서 Babel에 대한 자세한 내용을 알아보세요.

마지막으로 [webpack-visualizer](https://github.com/chrisbateman/webpack-visualizer)를 실행하여 시각적 개체의 코드 베이스를 표시합니다.  

![시각적 개체 코드 통계](./media/webpack-stats.png)
