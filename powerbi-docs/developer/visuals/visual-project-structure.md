---
title: Power BI 시각적 개체 프로젝트 구조
description: 이 문서에서는 시각적 개체 프로젝트의 구조를 설명합니다.
author: zBritva
ms.author: v-ilgali
ms.reviewer: ''
ms.service: powerbi
ms.topic: tutorial
ms.subservice: powerbi-custom-visuals
ms.date: 03/15/2019
ms.openlocfilehash: 728aba749f80710fdc0bb1e180b3318e63caa88c
ms.sourcegitcommit: 331ebf6bcb4a5cdbdc82e81a538144a00ec935d4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/28/2019
ms.locfileid: "75542096"
---
# <a name="power-bi-visual-project-structure"></a>Power BI 시각적 개체 프로젝트 구조

pbiviz new `<visual project name>`을 실행하면 이 도구는 `<visual project name>` 폴더에 파일 및 폴더의 기본 구조를 만듭니다.

## <a name="visual-project-structure"></a>시각적 개체 프로젝트 구조

![시각적 개체 프로젝트 구조](./media/visual-project-structure.png)

* `.vscode` - VS Code 프로젝트의 설정을 포함합니다. 작업 영역을 구성하려면 `.vscode/settings.json` 파일을 편집합니다. VS Code 설정에 대한 자세한 내용은 [문서](https://code.visualstudio.com/docs/getstarted/settings)를 참조하세요.

* `assets` 폴더에는 `icon.png` 파일만 들어 있습니다. 도구는 이 파일을 Power BI 시각화 창의 시각적 개체 아이콘으로 사용합니다.

    ![시각화 창](./media/visualization-pane-analytics-tab.png)

* `node_modules` 폴더에는 [노드 패키지 관리자를 통해 설치](https://docs.npmjs.com/files/folders.html)된 모든 패키지가 들어 있습니다.

* `src` 폴더에는 시각적 개체의 소스 코드가 들어 있습니다. 기본적으로 도구는 다음 두 개의 파일을 만듭니다.

  * `visual.ts` - 시각적 개체의 기본 소스 코드입니다.

  * `settings.ts` - 시각적 개체의 설정 코드입니다. 파일에 있는 클래스는 [시각적 개체 속성 작업](./objects-properties.md#properties)을 간소화합니다.

* `style` 폴더에는 시각적 개체의 스타일이 포함된 `visual.less` 파일이 들어 있습니다.

* `capabilities.json` 파일에는 시각적 개체의 기본 속성과 설정이 포함되어 있습니다. 이 파일을 통해 시각적 개체에서 지원되는 기능, 개체, 속성, 데이터 뷰 매핑을 선언할 수 있습니다.

    기능에 대한 자세한 내용은 [문서](./capabilities.md)를 참조하세요.

* `package-lock.json`은 npm이 `node_modules` 트리 또는 `package.json`을 수정하는 모든 작업에 대해 자동으로 생성됩니다.

    `package-lock.json`에 대한 자세한 내용은 [NPM 공식 문서](https://docs.npmjs.com/files/package-lock.json)를 참조하세요.

* `package.json`은 프로젝트 패키지를 설명합니다. 일반적으로 프로젝트, 작성자, 설명, 프로젝트 종속성에 대한 정보를 포함합니다.

    `package.json`에 대한 자세한 내용은 [NPM 공식 문서](https://docs.npmjs.com/files/package.json.html)를 참조하세요.

* `pbiviz.json`은 시각적 개체 메타데이터를 포함합니다. 이 파일에서 시각적 개체의 메타데이터를 지정합니다.

    파일의 일반적인 내용:

  ```json
    {
        "visual": {
            "name": "<visual project name>",
            "displayName": "<visual project name>",
            "guid": "<visual project name>23D8B823CF134D3AA7CC0A5D63B20B7F",
            "visualClassName": "Visual",
            "version": "1.0.0",
            "description": "",
            "supportUrl": "",
            "gitHubUrl": ""
        },
        "apiVersion": "2.6.0",
        "author": { "name": "", "email": "" },
        "assets": { "icon": "assets/icon.png" },
        "externalJS": null,
        "style": "style/visual.less",
        "capabilities": "capabilities.json",
        "dependencies": null,
        "stringResources": []
    }
  ```

    라는 설치 관리자 실행 파일에 포함됩니다. 여기서

  * `name` - 시각적 개체의 내부 이름입니다.

  * `displayName` - Power BI의 UI 인터페이스에서 시각적 개체의 이름입니다.

  * `guid` - 시각적 개체의 고유 ID입니다.

  * `visualClassName` - 시각적 개체의 기본 클래스 이름입니다. Power BI는 이 클래스의 인스턴스를 만들어 Power BI 보고서에서 시각적 개체를 사용하기 시작합니다.

  * `version` - 시각적 개체의 버전 번호입니다.

  * `author` - 작성자 이름과 연락처 메일을 포함합니다.

  * `assets`의 `icon` - 시각적 개체의 아이콘 파일 경로입니다.

  * `externalJS`에는 시각적 개체에 사용된 JS 라이브러리의 경로가 포함되어 있습니다.

    > [!IMPORTANT]
    > 최신 버전의 도구 3.x.x 이상에서는 더 이상 `externalJS`를 사용하지 않습니다.

  * `style`은 스타일 파일의 경로입니다.

  * `capabilities`는 `capabilities.json` 파일의 경로입니다.

  * `dependencies`는 `dependencies.json` 파일의 경로입니다. `dependencies.json`에는 R 기반 시각적 개체에 사용된 R 패키지에 대한 정보가 포함되어 있습니다.

  * `stringResources`는 지역화가 포함된 파일의 경로 배열입니다.

  시각적 개체의 지역화에 대한 자세한 내용은 [문서](./localization.md)를 참조하세요.

* `tsconfig.json`은 TypeScript의 구성 파일입니다.

    TypeScript 구성에 대한 자세한 내용은 [공식 문서](https://www.typescriptlang.org/docs/handbook/tsconfig-json.html)를 참조하세요.

    `files` 섹션의 `tsconfig.json`에는 `pbiviz.json` 파일의 `visualClassName` 속성에 지정된 시각적 개체의 기본 클래스가 있는 *.ts 파일의 경로가 포함되어야 합니다.

* `tslint.json` 파일에는 TSLint 구성이 포함되어 있습니다.

    TSLint 구성에 대한 자세한 내용은 [공식 문서](https://palantir.github.io/tslint/usage/configuration/)를 참조하세요.

## <a name="next-steps"></a>다음 단계

* 시각적 개체, 사용자 및 Power BI가 상호 작용하는 방식을 자세히 파악하려면 [시각적 개체 개념](./power-bi-visuals-concept.md)을 참조하세요.

* [단계별 가이드를 사용](./custom-visual-develop-tutorial.md)하여 처음부터 Power BI 시각적 개체 개발을 시작합니다.
