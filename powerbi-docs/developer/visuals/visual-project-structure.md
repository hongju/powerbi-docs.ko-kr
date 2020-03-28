---
title: Power BI 시각적 개체 프로젝트 구조
description: 이 문서에서는 Power BI 시각적 개체 프로젝트의 폴더 및 파일 구조를 설명합니다.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.topic: conceptual
ms.subservice: powerbi-custom-visuals
ms.date: 01/12/2020
ms.openlocfilehash: 16e7a317102602ffb4faf04da0ed2cae588a2a4d
ms.sourcegitcommit: 052df769e6ace7b9848493cde9f618d6a2ae7df9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/14/2020
ms.locfileid: "75925522"
---
# <a name="power-bi-visual-project-structure"></a>Power BI 시각적 개체 프로젝트 구조

새 Power BI 시각적 개체 만들기를 시작하는 가장 좋은 방법은 Power BI 시각적 개체 [pbiviz](https://www.npmjs.com/package/powerbi-visuals-tools) 도구를 사용하는 것입니다.

새 시각적 개체를 만들려면 Power BI 시각적 개체를 저장할 디렉터리로 이동하고 명령을 실행합니다.

`pbiviz new <visual project name>`

이 명령을 실행하면 다음 파일이 포함된 Power BI 시각적 개체 폴더가 생깁니다.

```markdown
project
├───.vscode
│   ├───launch.json
│   └───settings.json
├───assets
│   └───icon.png
├───node_modules
├───src
│   ├───settings.ts
│   └───visual.ts
├───style
│   └───visual.less
├───capabilities.json
├───package-lock.json
├───package.json
├───pbiviz.json
├───tsconfig.json
└───tslint.json
```

## <a name="folder-and-file-description"></a>폴더 및 파일 설명

이 섹션에서는 디렉터리에서 Power BI 시각적 개체 **pbiviz** 도구가 만드는 각 폴더와 파일에 대한 정보를 제공합니다.  

### <a name="vscode"></a>.vscode

이 폴더에는 VS 코드 프로젝트 설정이 포함되어 있습니다.

작업 영역을 구성하려면 `.vscode/settings.json` 파일을 편집합니다.

자세한 내용은 [사용자 및 작업 영역 설정](https://code.visualstudio.com/docs/getstarted/settings)을 참조하세요.

### <a name="assets"></a>assets

이 폴더에는 `icon.png` 파일이 포함되어 있습니다.

Power BI 시각적 개체 도구는 Power BI 시각화 창에서 이 파일을 새 Power BI 시각적 개체 아이콘으로 사용합니다.

<!--- ![Visualization pane](./media/visualization-pane-analytics-tab.png) --->

### <a name="src"></a>src

이 폴더에는 시각적 개체의 소스 코드가 포함되어 있습니다.

Power BI 시각적 개체 도구는 이 폴더에서 다음 파일을 만듭니다.
* `visual.ts` - 시각적 개체의 기본 소스 코드.
* `settings.ts` - 시각적 개체의 설정 코드. 파일의 클래스는 [시각적 개체의 속성](./objects-properties.md#properties)을 정의하기 위한 인터페이스를 제공합니다.

### <a name="style"></a>style

이 폴더에는 시각적 개체의 스타일이 보관된 `visual.less` 파일이 포함되어 있습니다.

### <a name="capabilitiesjson"></a>capabilities.json

이 파일에는 시각적 개체의 기본 속성 및 설정(또는 [기능](./capabilities.md))이 포함되어 있습니다. 이 파일을 통해 시각적 개체에서 지원되는 기능, 개체, 속성, [데이터 뷰 매핑](./dataview-mappings.md)을 선언할 수 있습니다.

### <a name="package-lockjson"></a>package-lock.json

이 파일은 *npm*이 `node_modules` 트리 또는 `package.json` 파일을 수정하는 모든 작업에 대해 자동으로 생성됩니다.

이 파일에 대한 자세한 내용은 공식 [npm-package-lock.json](https://docs.npmjs.com/files/package-lock.json) 설명서를 참조하세요.

### <a name="packagejson"></a>package.json

이 파일은 프로젝트 패키지를 설명합니다. 작성자, 설명, 프로젝트 종속성 등 프로젝트에 대한 정보가 포함되어 있습니다.

이 파일에 대한 자세한 내용은 공식 [npm-package.json](https://docs.npmjs.com/files/package.json.html) 설명서를 참조하세요.

### <a name="pbivizjson"></a>pbiviz.json

이 파일에는 시각적 개체 메타데이터가 포함되어 있습니다.

메타데이터 항목을 설명하는 주석이 있는 예시 `pbiviz.json` 파일을 보려면 [메타데이터 항목](#metadata-entries) 섹션을 참조하세요.

### <a name="tsconfigjson"></a>tsconfig.json

[TypeScript](https://www.typescriptlang.org/docs/handbook/tsconfig-json.html)의 구성 파일입니다.

이 파일에는 `pbiviz.json` 파일의 `visualClassName` 속성에 지정된 시각적 개체의 기본 클래스가 있는 **\*.ts** 파일의 경로가 포함되어야 합니다.

### <a name="tslintjson"></a>tslint.json

이 파일에는 [TSLint 구성](https://palantir.github.io/tslint/usage/configuration/)이 포함되어 있습니다.

## <a name="metadata-entries"></a>메타데이터 항목

`pbiviz.json` 파일의 다음 코드 캡션에 있는 주석은 메타데이터 항목을 설명합니다.

> [!NOTE]
> * **pbiviz** 도구 버전 3.x.x부터는 `externalJS`가 지원되지 않습니다.
> * 지역화 지원을 위해 [시각적 개체에 Power BI 로캘을 추가](./localization.md)합니다.

```json
{
  "visual": {
     // The visual's internal name.
    "name": "<visual project name>",

    // The visual's display name.
    "displayName": "<visual project name>",

    // The visual's unique ID.
    "guid": "<visual project name>23D8B823CF134D3AA7CC0A5D63B20B7F",

    // The name of the visual's main class. Power BI creates the instance of this class to start using the visual in a Power BI report.
    "visualClassName": "Visual",

    // The visual's version number.
    "version": "1.0.0",
    
    // The visual's description (optional)
    "description": "",

    // A URL linking to the visual's support page (optional).
    "supportUrl": "",

    // A link to the source code available from GitHub (optional).
    "gitHubUrl": ""
  },
  // The version of the Power BI API the visual is using.
  "apiVersion": "2.6.0",

  // The name of the visual's author and email.
  "author": { "name": "", "email": "" },

  // 'icon' holds the path to the icon file in the assets folder; the visual's display icon.
  "assets": { "icon": "assets/icon.png" },

  // Contains the paths for JS libraries used in the visual.
  // Note: externalJS' isn't used in the Power BI visuals tool version 3.x.x or higher.
  "externalJS": null,

  // The path to the 'visual.less' style file.
  "style": "style/visual.less",

  // The path to the `capabilities.json` file.
  "capabilities": "capabilities.json",

  // The path to the `dependencies.json` file which contains information about R packages used in R based visuals.
  "dependencies": null,

  // An array of paths to files with localizations.
  "stringResources": []
}
```

## <a name="next-steps"></a>다음 단계

* 시각적 개체, 사용자, Power BI 간의 상호 작용을 이해하려면 [Power BI 시각적 개체 개념](./power-bi-visuals-concept.md)을 참조하세요.

* [단계별 가이드를 사용](./custom-visual-develop-tutorial.md)하여 처음부터 자체 Power BI 시각적 개체 개발을 시작합니다.
