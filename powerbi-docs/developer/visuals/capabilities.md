---
title: 기능
description: Power BI 시각적 개체 기능 및 속성
author: asander
ms.author: asander
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: f6bb4293a44f98f2f8098fb197c7b406b618d211
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/23/2019
ms.locfileid: "68425462"
---
# <a name="power-bi-visual-capabilities"></a>Power BI 시각적 개체 기능

기능은 시각적 개체 정보를 호스트에 제공합니다. 기능 모델의 모든 속성은 `optional`입니다.

시각적 개체 기능의 루트 개체는 `dataRoles`, `dataViewMappings` 등입니다.

```json
{
    "dataRoles": [ ... ],
    "dataViewMappings": [ ... ],
    "objects":  { ... },
    "supportsHighlight": true|false,
    "advancedEditModeSupport": 0|1|2,
    "sorting": { ... }
}

```

## <a name="define-the-data-fields-your-visual-expects---dataroles"></a>시각적 개체에 필요한 데이터 필드 정의 - `dataRoles`

데이터에 바인딩할 수 있는 필드를 정의하기 위해 `dataRoles`를 사용합니다. dataRoles는 필요한 모든 속성을 정의하는 `DataViewRole` 개체 배열을 사용합니다.

### <a name="properties"></a>속성

* **name** - 이 데이터 필드의 내부 이름(고유해야 함)
* **kind** - 필드 종류:
    * `Grouping` - 측정값 필드의 그룹화에 사용되는 불연속 값
    * `Measure` - 숫자 데이터 값
    * `GroupingOrMeasure` - 그룹화 또는 측정값으로 사용할 수 있음
* **displayName** - 속성 창에서 사용자에게 표시되는 이름
* **description** - 필드에 대한 간략한 설명(선택 사항)
* **requiredTypes** - 이 데이터 역할에 필요한 데이터 형식. 일치하지 않는 값은 모두 null로 설정됩니다(선택 사항).
* **preferredTypes** - 이 데이터 역할의 기본 데이터 형식(선택 사항)

### <a name="valid-data-types-in-requiredtypes-and-preferredtypes"></a>“requiredTypes” 및 “preferredTypes”의 유효한 데이터 형식

* **bool** - 부울 값
* **integer** - 정수 값
* **numeric** - 숫자 값
* **text** - 텍스트 값
* **geography** - 지리 데이터

### <a name="example"></a>예제

```json
"dataRoles": [
    {
        "displayName": "My Category Data",
        "name": "myCategory",
        "kind": "Grouping",
        "requiredTypes": [
            {
                "text": true
            },
            {
                "numeric": true
            },
            {
                "integer": true
            }
        ],
        "preferredTypes": [
            {
                "text": true
            }
        ]
    },
    {
        "displayName": "My Measure Data",
        "name": "myMeasure",
        "kind": "Measure",
        "requiredTypes": [
            {
                "integer": true
            },
            {
                "numeric": true
            }
        ],
        "preferredTypes": [
            {
                "integer": true
            }
        ]
    },
    {
        "displayNameKey": "Visual_Location",
        "name": "Locations",
        "kind": "Measure",
        "displayName": "Locations",
        "requiredTypes": [
            {
                "geography": {
                    "address": true
                }
            },
            {
                "geography": {
                    "city": true
                }
            },
            {
                "geography": {
                    "continent": true
                }
            },
            {
                "geography": {
                    "country": true
                }
            },
            {
                "geography": {
                    "county": true
                }
            },
            {
                "geography": {
                    "place": true
                }
            },
            {
                "geography": {
                    "postalCode": true
                }
            },
            {
                "geography": {
                    "region": true
                }
            },
            {
                "geography": {
                    "stateOrProvince": true
                }
            }
        ]
    }
]
```

위의 데이터 역할은 다음 필드를 만듭니다.

![데이터 역할 표시](./media/data-role-display.png)

## <a name="define-how-you-want-the-data-mapped---dataviewmappings"></a>데이터 매핑 방법 정의 - `dataViewMappings`

DataViewMapping은 데이터 역할 간의 관계를 설명하고, 이러한 역할에 대해 조건부 요구 사항을 지정할 수 있도록 합니다.

대부분의 시각적 개체는 단일 매핑을 제공하지만, 여러 개의 dataViewMappings를 제공할 수 있습니다. 유효한 매핑마다 하나의 DataView를 생성합니다. 

```json
"dataViewMappings": [
    {
        "conditions": [ ... ],
        "categorical": { ... },
        "table": { ... },
        "single": { ... },
        "matrix": { ... }
    }
]
```

[DataViewMappings에 대한 자세한 정보](dataview-mappings.md)

## <a name="define-property-pane-options---objects"></a>속성 창 옵션 정의 - `objects`

개체는 시각적 개체와 연결된 사용자 지정 가능한 속성을 설명합니다.
각 개체에 여러 개의 속성이 있을 수 있으며, 속성마다 연결된 형식이 있습니다.
형식은 속성이 무엇인지를 나타냅니다. 형식에 대한 자세한 내용은 아래를 참조하세요.

```json
"objects": {
    "myCustomObject": {
        "displayName": "My Object Name",
        "properties": { ... }
    }
}
```

[개체에 대한 자세한 정보](objects-properties.md)

## <a name="handle-partial-highlighting---supportshighlight"></a>부분 강조 표시 처리 - `supportsHighlight`

기본적으로 이 값은 false로 설정되어 있으므로 페이지의 항목을 선택하면 “값”이 자동으로 필터링되고, 시각적 개체가 선택한 값만 표시하도록 업데이트됩니다. 전체 데이터를 표시하되 선택한 항목만 강조 표시하려는 경우 capabilities.json에서 `supportsHighlight`를 true로 설정해야 합니다.

[강조 표시에 대한 자세한 정보](highlight.md)

## <a name="handle-advanced-edit-mode---advancededitmodesupport"></a>고급 편집 모드 처리 - `advancedEditModeSupport`

시각적 개체에서 고급 편집 모드 지원을 선언할 수 있습니다.
capabilities.json에서 달리 지정되지 않은 경우, 기본적으로 시각적 개체는 고급 편집 모드를 지원하지 않습니다.

[advancedEditModeSupport에 대한 자세한 정보](advanced-edit-mode.md)

## <a name="data-sorting-options-for-visual---sorting"></a>시각적 개체의 데이터 정렬 옵션 - `sorting`

시각적 개체는 해당 기능을 통해 정렬 동작을 정의할 수 있습니다.
capabilities.json에서 달리 지정되지 않은 경우, 기본적으로 시각적 개체는 정렬 순서 수정을 지원하지 않습니다.

[정렬에 대한 자세한 정보](sort-options.md)
