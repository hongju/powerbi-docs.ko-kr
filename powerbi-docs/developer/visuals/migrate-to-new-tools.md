---
title: powerbi-visuals-tools 버전 3.x로 마이그레이션
description: 새로운 버전의 powerbi-visuals-tools 시작하기
author: KesemSharabi
ms.author: kesharab
ms.reviewer: rkarlin
manager: rkarlin
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: d9af0ab870732990201ab3478d71fdafa9e13439
ms.sourcegitcommit: 8e3d53cf971853c32eff4531d2d3cdb725a199af
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "76818827"
---
# <a name="migrate-to-the-new-powerbi-visuals-tools-version-3x"></a>새로운 powerbi-visuals-tools 버전 3.*x*로 마이그레이션

Power BI 시각적 개체 도구(powerbi-visuals-tools 또는 `pbiviz`) 버전 3부터는 사용자 지정 시각적 개체를 빌드하는 데 webpack이 사용됩니다.
새로운 버전에서는 다음과 같이 개발자가 시각적 개체를 만드는 방법이 개선되었습니다.

- 기본적으로 TypeScript 버전 3.*x*가 사용됩니다. TypeScript 1.5부터 명명법이 변경되었습니다. [TypeScript 모듈에 대해 자세히 알아보세요](https://www.typescriptlang.org/docs/handbook/modules.html).

- ES6(ECMAScript 6) 모듈이 지원됩니다. 이제부터 [externalJS](migrate-to-new-tools.md#configure-loading-of-external-libraries) 대신 ES6 가져오기를 사용하세요.

- 새로운 버전의 [D3v5](https://d3js.org/)(Data-Driven Documents) 및 기타 ES6 모듈 기반 라이브러리가 지원됩니다.

- 줄어든 패키지 크기. webpack에서 [트리 셰이킹](https://webpack.js.org/guides/tree-shaking/)을 사용하여 미사용 코드를 제거합니다. 이를 통해 JavaScript 코드가 제거되며 시각적 개체 로드 성능이 향상됩니다.

- 향상된 API 성능.

- Globalize.js 라이브러리가 FormattingUtils에 [통합되었습니다](migrate-to-new-tools.md#remove-the- globalizejs-library).

- Power BI 시각적 개체 도구는 [webpack-bundle-analyzer](https://github.com/webpack-contrib/webpack-bundle-analyzer)를 사용하여 시각적 개체의 코드를 표시합니다.

이 문서에서는 새로운 버전의 Power BI 시각적 개체 도구를 위한 모든 마이그레이션 단계를 설명합니다.

## <a name="backward-compatibility"></a>이전 버전과의 호환성

새로운 도구는 이전 시각적 개체 코드 베이스를 위해 이전 버전과의 호환성을 유지하지만 외부 라이브러리를 로드하려면 추가로 몇 가지 변경 사항이 필요할 수 있습니다.

모듈 시스템을 지원하는 라이브러리는 webpack 모듈로 가져옵니다. 다른 모든 라이브러리와 시각적 개체 소스 코드는 하나의 모듈로 래핑됩니다.

이전 Power BI 시각적 개체 도구에서 사용되던 JQuery 및 Lodash 같은 전역 변수는 이제 사용되지 않습니다. 시각적 개체의 기존 코드에서 전역 변수를 사용하는 경우, 새로운 도구에서는 해당 시각적 개체가 작동하지 않습니다.

이전 버전의 Power BI 시각적 개체 도구에서는 `powerbi.extensibility.visual` 모듈 아래에서 시각적 개체 클래스를 정의해야 했습니다. 새 버전의 도구에서는 대신 기본 TypeScript(.ts) 파일에 시각적 개체 클래스를 정의해야 합니다. 일반적으로 이 파일은 `src/visual.ts`입니다.

## <a name="install-powerbi-visuals-tools"></a>powerbi-visuals-tools 설치

다음 명령을 실행하여 새 도구를 설치합니다.

```cmd
npm install -g powerbi-visuals-tools
```

다음 코드는 새로운 도구와 함께 작동하도록 시각적 개체 프로젝트를 업데이트한 후에 [sampleBarChart visual repository](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/blob/471f103fcef9af93cff76cbac9c7fc67564acd4b/package.json#L15)에 있는 `package.json` 파일에 포함된 것입니다.

```json
{
    "name": "visual",
    "version": "3.0.0",
    "scripts": {
        "pbiviz": "pbiviz",
        "start": "pbiviz start",
        "package": "pbiviz package",
        "lint": "tslint -r \"node_modules/tslint-microsoft-contrib\"  \"+(src|test)/**/*.ts\"",
        "test": "pbiviz package --resources --no-minify --no-pbiviz"
    },
    "devDependencies": {
        "@types/d3": "5.7.2",
        "d3": "5.12.0",
        "powerbi-visuals-api": "^2.6.1",
        "powerbi-visuals-tools": "^3.1.7",
        "powerbi-visuals-utils-dataviewutils": "^2.2.1",
        "powerbi-visuals-utils-formattingutils": "^4.4.2",
        "powerbi-visuals-utils-interactivityutils": "^5.6.0",
        "powerbi-visuals-utils-tooltiputils": "^2.3.1",
        "tslint": "^5.20.0",
        "tslint-microsoft-contrib": "^6.2.0"
    }
}
```

## <a name="install-the-power-bi-custom-visuals-api"></a>Power BI 사용자 지정 시각적 개체 API 설치

새로운 버전의 powerbi-visual-tools에는 일부 API 버전이 포함되어 있지 않습니다. 따라서 특정 버전의 [powerbi-visuals-api](https://www.npmjs.com/package/powerbi-visuals-api) 패키지를 설치해야 합니다. Power BI 사용자 지정 시각적 개체의 API 버전과 일치하는 버전의 패키지를 선택합니다. 패키지는 Power BI 사용자 지정 시각적 개체 API를 위한 모든 형식 정의를 제공합니다.

다음 명령을 실행하여 프로젝트의 프로젝트 종속성에 `powerbi-visuals-api`를 추가합니다.

```cmd
npm install --save-dev powerbi-visuals-api
```

또한, webpack에는 `powerbi-visuals-api`의 형식이 자동으로 포함되므로 이전 API 형식 정의에 대한 링크를 모두 제거합니다. 해당 변경 사항은 [package.json](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/blob/471f103fcef9af93cff76cbac9c7fc67564acd4b/package.json#L14) 및 [tsconfig.json](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/blob/471f103fcef9af93cff76cbac9c7fc67564acd4b/tsconfig.json#L14)에 있습니다.

## <a name="update-tsconfigjson"></a>tsconfig.json 업데이트

외부 모듈을 사용하려면 `out` 옵션을 `outDir`로 변경합니다. 예를 들어, `"out": "./.tmp/build/visual.js",` 대신 `"outDir": "./.tmp/build/",`을 사용합니다.

이 변경 사항은 TypeScript 파일이 독립적으로 JavaScript 파일로 컴파일되기 때문에 필요합니다. 따라서 더 이상 visual.js 파일을 출력으로 지정할 필요가 없는 것입니다.

최신 JavaScript를 출력으로 사용하려면 `target` 옵션을 `ES6`으로 변경하면 됩니다. 이 변경 사항은 [선택 사항](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/blob/471f103fcef9af93cff76cbac9c7fc67564acd4b/tsconfig.json#L7)입니다.

## <a name="update-custom-visuals-utilities"></a>사용자 지정 시각적 개체 유틸리티 업데이트

[powerbi-visuals-utils](https://www.npmjs.com/search?q=powerbi-visuals-utils) 패키지를 사용하는 경우에는 패키지도 최신 버전으로 업데이트합니다. 이렇게 하려면 다음 명령을 실행합니다.

```cmd
npm install powerbi-visuals-utils-<UTILNAME> --save
```

예를 들어, TypeScript의 외부 모듈과 함께 새로운 버전을 가져오려면 다음을 실행합니다. 

```cmd
npm install powerbi-visuals-utils-dataviewutils --save
```

모든 `powerbi-visuals-utils` 패키지를 사용하는 시각적 개체의 예는 [MekkoChart 리포지토리](https://github.com/Microsoft/powerbi-visuals-mekkochart)를 참조하세요.

## <a name="remove-the-globalizejs-library"></a>Globalize.js 라이브러리 제거

새로운 버전의 [powerbi-visuals-utils-formattingutils@4.3](https://www.npmjs.com/package/powerbi-visuals-utils-formattingutils)은 Globalize.js를 포함합니다. 따라서 프로젝트에 이 라이브러리를 수동으로 포함시킬 필요가 없습니다. 모든 필수 지역화가 자동으로 최종 패키지에 추가됩니다.

## <a name="configure-loading-of-external-libraries"></a>외부 라이브러리 로드 구성

`pbiviz.json`의 `externalJS` 배열에서 라이브러리 뒤에 새로운 JavaScript 파일을 포함시킵니다. 예:

```JSON
"externalJS": [
    ...
    "node_modules/lodash/lodash.min.js",
    "externalJS/init.lodash.js",
    ...
]
```

소스 코드에서 라이브러리를 가져옵니다. 예를 들어, `lodash-es`의 경우 다음 문을 사용합니다.

```JS
import * as _ from "lodash-es";
```

앞의 예에서 `_`는 `lodash` 라이브러리의 전역 변수입니다.

## <a name="make-changes-in-the-sources-of-your-visuals"></a>시각적 개체 소스에서 변경 사항 적용

가장 중요한 변경 사항은 내부 모듈을 외부 모듈로 변환하는 것입니다. 내부 모듈에서는 외부 모듈을 사용할 수 없기 때문입니다.

다음은 적용해야 하는 변경 사항에 대한 자세한 설명입니다. 수정 내용은 막대형 차트 사용자 지정 시각적 개체 코드 샘플의 맥락에서 설명됩니다.

1. 각 [소스 코드](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/commit/72ec605ce6a311a6cc004453b07973b6ed5e61f9#diff-433142f7814fee940a0ffc98dc75bfcbL1-L3) 파일에서 모든 모듈 정의를 제거합니다.

    ```typescript
    module powerbi.extensibility.visual {
        ...
    }
    ```

2. [Power BI 사용자 지정 시각적 개체 API 정의를 가져옵니다](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/commit/72ec605ce6a311a6cc004453b07973b6ed5e61f9#diff-433142f7814fee940a0ffc98dc75bfcbR4).

    ```typescript
    import powerbi from "powerbi-visuals-api";
    ```

3. `powerbi` 내부 모듈에서 [필요한 인터페이스 또는 클래스를 가져옵니다](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/commit/72ec605ce6a311a6cc004453b07973b6ed5e61f9#diff-433142f7814fee940a0ffc98dc75bfcbR12-R35).

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

4. [D3.js 라이브러리를 가져옵니다](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/commit/72ec605ce6a311a6cc004453b07973b6ed5e61f9#diff-433142f7814fee940a0ffc98dc75bfcbR2).

    ```typescript
    import * as d3 from "d3";
    ```

    또는 필요한 D3 라이브러리 모듈만 가져옵니다.

    ```typescript
    import { max, min } from "d3-array";
    ```

5. [시각적 개체 프로젝트에 정의된 유틸리티, 클래스 및 인터페이스를](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/commit/72ec605ce6a311a6cc004453b07973b6ed5e61f9#diff-433142f7814fee940a0ffc98dc75bfcbR38-R41) 메인 소스 파일로 가져옵니다.

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

새로운 버전의 도구에서는 `CSS` 및 `Less` 스타일을 TypeScript 코드로 직접 가져올 수 있습니다. 이전에 사용된 [스타일 선택](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/blob/471f103fcef9af93cff76cbac9c7fc67564acd4b/pbiviz.json#L21)은 컴파일러에서 무시됩니다.

스타일시트를 사용하려면 기본 TypeScript(.ts) 파일을 열고 다음 줄을 추가합니다.  

```typescript
import "./../style/visual.less";
```  

`CSS` 및 `Less` 스타일이 자동으로 컴파일됩니다.

### <a name="externaljs-section-in-pbivizjson"></a>pbiviz.json의 externalJS 섹션

webpack에는 모든 가져온 라이브러리가 포함되어 있으므로 [`externalJS` 라이브러리 목록이 시각적 개체 번들에 로드될 필요가 없습니다](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/commit/72ec605ce6a311a6cc004453b07973b6ed5e61f9#diff-a1a7bbee7e7d2f9d449f4b534532bcf2R20).

> [!NOTE]
> `pbiviz.json`에서 `externalJS` 섹션을 비워 둡니다.

일반적인 명령 `npm run package`를 사용하여 시각적 개체 패키지를 만들거나 `npm run start`를 사용하여 개발 서버를 시작합니다.

## <a name="update-the-d3js-library-to-version-5"></a>D3.js 라이브러리를 버전 5로 업데이트

새로운 시각적 개체 도구에서는 새로운 버전의 D3.js 라이브러리를 사용할 수 있습니다. 다음 명령을 실행하여 시각적 개체 프로젝트에서 D3를 업데이트합니다.

- 새 D3.js를 설치하는 경우 `npm install --save d3@5`.

- D3.js에 대한 새 형식 정의를 설치하는 경우 `npm install --save-dev @types/d3@5`.

> [!IMPORTANT]
> D3 버전 5에는 호환성이 손상되는 몇 가지 변경 사항이 적용되었습니다.

새로운 D3.js와 작동하도록 코드를 수정합니다.

- 인터페이스 `d3.Selection<T>`가 `Selection<GElement extends BaseType, Datum, PElement extends BaseType, PDatum>`으로 [변경되었습니다](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/af2ff9fb0fc70bd94ea0c604d75a362411d5abeb#diff-433142f7814fee940a0ffc98dc75bfcbR157).

- `attr` 메서드를 한 번 호출하여 여러 특성을 적용할 수 없습니다. 대신 [개별적인 호출에서 각 특성을 `attr`로 전달](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/af2ff9fb0fc70bd94ea0c604d75a362411d5abeb#diff-433142f7814fee940a0ffc98dc75bfcbR278)해야 합니다. [`style` 메서드도 개별적으로 호출](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/af2ff9fb0fc70bd94ea0c604d75a362411d5abeb#diff-433142f7814fee940a0ffc98dc75bfcbR247)합니다.

- D3.js 버전 4부터 새로운 `merge` 메서드가 도입되었습니다. 이 메서드는 데이터 조인 작업 후에 `enter` 선택 항목과 `update` 선택 항목을 병합하는 데 주로 사용됩니다. D3를 올바르게 사용하려면 [`merge` 메서드를 호출](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/83fe8d52d362dccd0034dd8e32c94080d9376b29#diff-433142f7814fee940a0ffc98dc75bfcbR272)합니다.

D3.js 라이브러리의 변경 사항에 대해 [자세히 알아보세요](https://github.com/d3/d3/blob/master/CHANGES.md).

## <a name="install-babel-and-core-js"></a>Babel 및 core-js 설치

버전 3.1부터 시각적 개체는 다양한 브라우저를 지원하기 위해 Babel을 사용하여 최신 JavaScript 코드를 이전의 ES5(ECMAScript 5)로 컴파일합니다.

Babel 옵션은 기본적으로 사용하도록 설정되지만 [`core-js`](https://www.npmjs.com/package/core-js) 패키지는 수동으로 가져와야 합니다. 다음 명령을 실행하여 패키지를 설치합니다.

```cmd
npm install --save core-js
```

그런 다음 시각적 코드의 시작 지점에서 패키지를 가져옵니다. 일반적으로 이 파일은 ‘src/visual.ts’입니다.

```JS
import "core-js/stable";
```

[문서](https://babeljs.io/docs/en/)에서 Babel에 대한 자세한 내용을 알아보세요.
