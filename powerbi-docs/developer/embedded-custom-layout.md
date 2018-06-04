---
title: Power BI 포함 콘텐츠를 사용하는 사용자 지정 레이아웃
description: 응용 프로그램에 Power BI 콘텐츠를 포함하는 경우 사용자 지정 레이아웃에 대해 알아봅니다.
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 12/19/2017
ms.author: maghan
ms.openlocfilehash: fc684ebdf6b1ccb53bdd7794b19c1120ece635a3
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34288133"
---
# <a name="custom-layouts"></a>사용자 지정 레이아웃


원본 보고서와 다른 레이아웃으로 구성된 보고서를 포함하려면 사용자 지정 레이아웃을 사용합니다. 페이지 크기만 정의하는 경우와 시각적 크기 또는 위치 및 표시 유형을 제어하는 경우의 새 레이아웃 정의 방법은 다릅니다.

사용자 지정 레이아웃을 정의하려면 사용자 지정 레이아웃 개체를 정의하고 포함 구성의 설정 개체에 전달합니다. 또한 LayoutType을 Custom으로 설정합니다. 자세히 알아보려면 [포함 구성 세부 정보](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Embed-Configuration-Details)를 참조하세요.

```javascript
var embedConfig = {
    ...
    settings: {
            layoutType: models.LayoutType.Custom
    customLayout: {...}
    }
};
```

## <a name="object-definition"></a>개체 정의

```javascript
interface ICustomLayout {
  pageSize?: IPageSize;
  displayOption?: DisplayOption;
  pagesLayout?: PagesLayout;
}

enum PageSizeType {
  Widescreen,
  Standard,
  Cortana,
  Letter,
  Custom
}
interface IPageSize {
  type: PageSizeType;
}
interface ICustomPageSize extends IPageSize {
  width?: number;
  height?: number;
}

enum DisplayOption {
  FitToPage,
  FitToWidth,
  ActualSize
}
```

- `pageSize`: 페이지 크기를 사용하여 캔버스 영역 크기(즉, 보고서의 흰색 영역)를 제어합니다.
- `displayOptions`: 가능한 값은 FitToWidth, FitToPage 또는 ActualSize입니다. iframe에 맞게 캔버스의 크기를 조정하는 방법을 제어합니다.
- `pagesLayout`: 각 시각적 개체의 레이아웃을 제어합니다. 자세한 내용은 PagesLayout을 참조하세요.

## <a name="pages-layout"></a>페이지 레이아웃

페이지 레이아웃 개체를 정의하는 방법은 기본적으로 각 페이지의 레이아웃을 정의하고 각 페이지의 각 시각적 개체에 대한 레이아웃을 정의하는 것입니다.
PageLayout은 선택 사항입니다. 페이지의 레이아웃을 정의하지 않으면 (보고서에 저장된) 기본 레이아웃이 적용됩니다.

pagesLayout은 페이지 이름에서 PageLayout 개체로의 맵입니다. 정의:

```javascript
type PagesLayout = { [key: string]: IPageLayout; };
```

PageLayout에는 시각적 레이아웃 개체에 각 시각적 이름을 매핑하는 시각적 레이아웃 맵이 포함되어 있습니다.

```javascript
interface IPageLayout {
  visualsLayout: { [key: string]: IVisualLayout; };
}
```

## <a name="visual-layout"></a>시각적 레이아웃

시각적 레이아웃을 정의하려면 새 위치 및 크기와 새 표시 여부 상태를 전달합니다.

```javascript
interface IVisualLayout {
  x?: number;
  y?: number;
  z?: number;
  width?: number;
  height?: number;
  displayState?: IVisualContainerDisplayState;
}

interface IVisualContainerDisplayState {
  mode: VisualContainerDisplayMode;
}

enum VisualContainerDisplayMode {
  Visible,
  Hidden
}
```

- `x,y,z`: 시각적 개체의 새 위치를 정의합니다.
- `width`, height: 시각적 개체의 새 크기를 정의합니다.
- `displayState`: 시각적 개체의 표시 여부를 정의합니다.


## <a name="update-layout"></a>레이아웃 업데이트

보고서를 로드하는 동안 언제든지 updateSettings 메서드를 사용하여 보고서 레이아웃을 업데이트할 수 있습니다. [업데이트 설정](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Update-Settings)을 참조하세요.

## <a name="code-example"></a>코드 예제

```javascript
// Get models. models contains enums that can be used.
var models = window['powerbi-client'].models;
    
var embedConfiguration = {
    type: 'report',
    id: '5dac7a4a-4452-46b3-99f6-a25915e0fe55',
    embedUrl: 'https://app.powerbi.com/reportEmbed',
    tokenType: models.TokenType.Embed,
    accessToken: 'H4...rf',
    settings: {
            layoutType: models.LayoutType.Custom
        customLayout: {
            pageSize: {
                type: models.PageSizeType.Custom,
                width: 1600,
                height: 1200
            },
            displayOption: models.DisplayOption.ActualSize,
            pagesLayout: {
                "ReportSection1" : {
                    visualsLayout: {
                        "VisualContainer1": {
                            x: 1,
                            y: 1,
                            z: 1,
                            width: 400,
                            height: 300,
                            displayState: {
                                mode: models.VisualContainerDisplayMode.Visible
                            }
                        },
                        "VisualContainer2": {
                            displayState: {
                                mode: models.VisualContainerDisplayMode.Hidden
                            }
                        },
                    }
                }
            }
        }
    }
};
     
// Get a reference to the embedded report HTML element
var embedContainer = document.getElementById('embedContainer');
 
// Embed the report and display it within the div container.
var report = powerbi.embed(embedContainer, embedConfiguration);

```


## <a name="see-also"></a>참고 항목

[Power BI 대시보드, 보고서 및 타일 포함](embedding-content.md)   
[Power BI 커뮤니티에 문의](https://community.powerbi.com/)

