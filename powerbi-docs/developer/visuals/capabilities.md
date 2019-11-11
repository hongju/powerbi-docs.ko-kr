---
title: Power BI 시각적 개체의 기능 및 속성
description: 이 문서에서는 Power BI 시각적 개체의 기능 및 속성을 설명합니다.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: ca29e711e12c3958b608dcc231de628cd7590988
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2019
ms.locfileid: "73880226"
---
# <a name="capabilities-and-properties-of-power-bi-visuals"></a>Power BI 시각적 개체의 기능 및 속성 

기능을 사용하여 시각적 개체 정보를 호스트에 제공합니다. 기능 모델의 모든 속성은 `optional`입니다.

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

## <a name="define-the-data-fields-that-your-visual-expects-dataroles"></a>시각적 개체에 필요한 데이터 필드 정의: dataRoles

데이터에 바인딩할 수 있는 필드를 정의하려면 `dataRoles`를 사용합니다. `dataRoles`는 모든 필수 속성을 정의하는 `DataViewRole` 개체의 배열을 사용합니다.

### <a name="properties"></a>속성

* **name**: 이 데이터 필드의 내부 이름(고유해야 함)
* **kind**: 필드 종류:
    * `Grouping`: 측정값 필드의 그룹화에 사용되는 불연속 값
    * `Measure`: 숫자 데이터 값
    * `GroupingOrMeasure`: 그룹화 또는 측정값으로 사용할 수 있는 값
* **displayName**: **속성** 창에서 사용자에게 표시되는 이름
* **description**: 필드에 대한 간략한 설명(선택 사항)
* **requiredTypes**: 이 데이터 역할에 필요한 데이터 형식. 일치하지 않는 값은 null로 설정됩니다(선택 사항).
* **preferredTypes**: 이 데이터 역할의 기본 데이터 형식(선택 사항)

### <a name="valid-data-types-in-requiredtypes-and-preferredtypes"></a>requiredTypes 및 preferredTypes의 유효한 데이터 형식

* **bool**: 부울 값
* **integer**: 정수 값
* **numeric**: 숫자 값
* **text**: 텍스트 값
* **geography**: 지리 데이터

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

위의 데이터 역할은 다음 이미지에 표시된 필드를 만듭니다.

![데이터 역할 필드](./media/data-role-display.png)

## <a name="define-how-you-want-the-data-mapped-dataviewmappings"></a>데이터 매핑 방법 정의: dataViewMappings

DataViewMappings 속성은 데이터 역할 간의 관계를 설명하고, 이러한 역할에 대해 조건부 요구 사항을 지정할 수 있도록 합니다.

대부분의 시각적 개체는 단일 매핑을 제공하지만, 여러 개의 dataViewMappings를 제공할 수 있습니다. 유효한 매핑마다 하나의 데이터 뷰를 생성합니다. 

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

자세한 내용은 [Power BI 시각적 개체의 데이터 뷰 매핑 이해](dataview-mappings.md)를 참조하세요.

## <a name="define-property-pane-options-objects"></a>속성 창 옵션 정의: objects

개체는 시각적 개체와 연결된 사용자 지정 가능한 속성을 설명합니다. 각 개체에 여러 개의 속성이 있을 수 있으며, 속성마다 연결된 형식이 있습니다. 형식은 속성이 무엇인지를 나타냅니다. 

```json
"objects": {
    "myCustomObject": {
        "displayName": "My Object Name",
        "properties": { ... }
    }
}
```

자세한 내용은 [Power BI 시각적 개체의 개체 및 속성](objects-properties.md)을 참조하세요.

## <a name="handle-partial-highlighting-supportshighlight"></a>부분 강조 표시 처리: supportsHighlight

기본적으로 이 값은 `false`로 설정되어 있으므로, 페이지의 항목을 선택하면 값이 자동으로 필터링됩니다. 이 자동 필터링은 다시 선택한 값만 표시하도록 시각적 개체를 업데이트합니다. 전체 데이터를 표시하되 선택한 항목만 강조 표시하려는 경우 *capabilities.json* 파일에서 `supportsHighlight`를 `true`로 설정해야 합니다.

자세한 내용은 [Power BI 시각적 개체에서 데이터 요소 강조 표시](highlight.md)를 참조하세요.

## <a name="handle-advanced-edit-mode-advancededitmodesupport"></a>고급 편집 모드 처리: advancedEditModeSupport

시각적 개체에서 고급 편집 모드 지원을 선언할 수 있습니다. *capabilities.json* 파일에서 달리 지정되지 않은 경우, 기본적으로 시각적 개체는 고급 편집 모드를 지원하지 않습니다.

자세한 내용은 [Power BI 시각적 개체의 고급 편집 모드](advanced-edit-mode.md)를 참조하세요.

## <a name="data-sorting-options-for-visual-sorting"></a>시각적 개체의 데이터 정렬 옵션: sorting

시각적 개체는 해당 기능을 통해 정렬 동작을 정의할 수 있습니다. *capabilities.json* 파일에서 달리 지정되지 않은 경우, 기본적으로 시각적 개체는 정렬 순서 수정을 지원하지 않습니다.

자세한 내용은 [Power BI 시각적 개체의 정렬 옵션](sort-options.md)을 참조하세요.
