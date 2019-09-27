---
title: Power BI 시각적 개체의 개체 및 속성
description: 이 문서에서는 Power BI 시각적 개체의 사용자 지정 가능한 속성을 설명합니다.
author: KesemSharabi
ms.author: kesharab
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: b2043c6727e4cf8c5c46c4e277b01a9ea04a969b
ms.sourcegitcommit: e2de2e8b8e78240c306fe6cca820e5f6ff188944
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2019
ms.locfileid: "71193530"
---
# <a name="objects-and-properties-of-power-bi-visuals"></a>Power BI 시각적 개체의 개체 및 속성

개체는 시각적 개체와 연결된 사용자 지정 가능한 속성을 설명합니다. 각 개체에 여러 개의 속성이 있을 수 있으며, 속성마다 해당 속성이 무엇인지를 설명하는 연결된 형식이 있습니다. 이 문서에서는 개체와 속성 형식에 대한 정보를 제공합니다.

`myCustomObject`는 `dataView` 및 `enumerateObjectInstances` 내에서 개체를 참조하는 데 사용되는 내부 이름입니다.

```json
"objects": {
    "myCustomObject": {
        "displayName": "My Object Name",
        "properties": { ... }
    }
}
```

## <a name="display-name"></a>표시 이름

`displayName`은 속성 창에 표시되는 이름입니다.

## <a name="properties"></a>속성

`properties`는 개발자가 정의한 속성 맵입니다.

```json
"properties": {
    "myFirstProperty": {
        "displayName": "firstPropertyName",
        "type": ValueTypeDescriptor | StructuralTypeDescriptor
    }
}
```

> [!NOTE]
> `show`는 스위치가 개체를 토글할 수 있도록 하는 특수 속성입니다.

예제:

```json
"properties": {
    "show": {
        "displayName": "My Property Switch",
        "type": {"bool": true}
    }
}
```

### <a name="property-types"></a>속성 형식

`ValueTypeDescriptor` 및 `StructuralTypeDescriptor`라는 두 가지 속성 형식이 있습니다.

#### <a name="value-type-descriptor"></a>값 형식 설명자

`ValueTypeDescriptor` 형식은 대체로 기본 형식이며, 일반적으로 정적 개체로 사용됩니다.

몇 가지 일반적인 `ValueTypeDescriptor` 요소는 다음과 같습니다.

```typescript
export interface ValueTypeDescriptor {
    text?: boolean;
    numeric?: boolean;
    integer?: boolean;
    bool?: boolean;
}
```

#### <a name="structural-type-descriptor"></a>구조적 형식 설명자

`StructuralTypeDescriptor` 형식은 데이터 바인딩된 개체에 주로 사용됩니다.
가장 일반적인 `StructuralTypeDescriptor` 형식은 *fill*입니다.

```typescript
export interface StructuralTypeDescriptor {
    fill?: FillTypeDescriptor;
}
```

## <a name="gradient-property"></a>그라데이션 속성

그라데이션 속성은 표준 속성으로 설정할 수 없는 속성입니다. 대신, 색 선택기 속성(*채우기* 유형)을 대체하는 규칙을 설정해야 합니다.

예제는 다음 코드에 나와 있습니다.

```json
"properties": {
    "showAllDataPoints": {
        "displayName": "Show all",
        "displayNameKey": "Visual_DataPoint_Show_All",
        "type": {
            "bool": true
        }
    },
    "fill": {
        "displayName": "Fill",
        "displayNameKey": "Visual_Fill",
        "type": {
            "fill": {
                "solid": {
                    "color": true
                }
            }
        }
    },
    "fillRule": {
        "displayName": "Color saturation",
        "displayNameKey": "Visual_ColorSaturation",
        "type": {
            "fillRule": {}
        },
        "rule": {
            "inputRole": "Gradient",
            "output": {
                "property": "fill",
                    "selector": [
                        "Category"
                    ]
            }
        }
    }
}
```

*fill* 및 *fillrule* 속성에 주의합니다. 첫 번째 속성은 색 선택기이고, 두 번째 속성은 규칙 조건이 충족될 때 ‘fill’ 속성 `visually`를 바꾸는 그라데이션 대체 규칙입니다. 

‘fill’ 속성과 대체 규칙 간의 이러한 연결은 *fillRule* 속성의 `"rule"`>`"output"` 섹션에서 설정됩니다. 

`"Rule"`>`"InputRole"` 속성은 규칙(조건)을 트리거하는 데이터 역할을 설정합니다. 이 예제에서는 데이터 역할 `"Gradient"`에 데이터가 포함된 경우 `"fill"` 속성에 규칙이 적용됩니다.

채우기 규칙(`the last item`)을 트리거하는 데이터 역할의 예는 다음 코드에 나와 있습니다.

```json
{
    "dataRoles": [
            {
                "name": "Category",
                "kind": "Grouping",
                "displayName": "Details",
                "displayNameKey": "Role_DisplayName_Details"
            },
            {
                "name": "Series",
                "kind": "Grouping",
                "displayName": "Legend",
                "displayNameKey": "Role_DisplayName_Legend"
            },
            {
                "name": "Gradient",
                "kind": "Measure",
                "displayName": "Color saturation",
                "displayNameKey": "Role_DisplayName_Gradient"
            }
    ]
}
```

## <a name="the-enumerateobjectinstances-method"></a>enumerateObjectInstances 메서드

개체를 효과적으로 사용하려면 `enumerateObjectInstances`라는 함수가 사용자 지정 시각적 개체에 필요합니다. 이 함수는 속성 창을 개체로 채우고, dataView 내에서 개체가 바인딩되어야 하는 위치도 결정합니다.  

일반적인 설정은 다음과 같습니다.

```typescript
public enumerateObjectInstances(options: EnumerateVisualObjectInstancesOptions): VisualObjectInstanceEnumeration {
    let objectName: string = options.objectName;
    let objectEnumeration: VisualObjectInstance[] = [];

    switch( objectName ) {
        case 'myCustomObject':
            objectEnumeration.push({
                objectName: objectName,
                properties: { ... },
                selector: { ... }
            });
            break;
    };

    return objectEnumeration;
}
```

### <a name="properties"></a>속성

`enumerateObjectInstances`의 속성은 기능에서 정의된 속성을 반영합니다. 예제를 보려면 이 문서의 끝으로 이동합니다.

### <a name="objects-selector"></a>개체 선택기

`enumerateObjectInstances`의 선택기는 dataView에서 각 개체가 바인딩되는 위치를 결정합니다. 다음 네 가지 옵션이 있습니다.

#### <a name="static"></a>static

이 개체는 여기에 표시된 것처럼 `dataviews[index].metadata.objects` 메타데이터에 바인딩됩니다.

```typescript
selector: null
```

#### <a name="columns"></a>columns

이 개체는 `QueryName`이 일치하는 열에 바인딩됩니다.

```typescript
selector: {
    metadata: 'QueryName'
}
```

#### <a name="selector"></a>selector

이 개체는 만든 `selectionID`의 요소에 바인딩됩니다. 이 예제에서는 일부 데이터 요소의 `selectionID`를 만들었으며, 해당 ID를 반복한다고 가정해 봅시다.

```typescript
for (let dataPoint in dataPoints) {
    ...
    selector: dataPoint.selectionID.getSelector()
}
```

#### <a name="scope-identity"></a>Scope identity

이 개체는 그룹의 교집합에 있는 특정 값에 바인딩됩니다. 예를 들어 `["Jan", "Feb", "March", ...]` 범주와 `["Small", "Medium", "Large"]` 계열이 있는 경우, `Feb` 및 `Large`와 일치하는 값의 교집합에 개체를 포함할 수 있습니다. 이 작업을 위해 두 열의 `DataViewScopeIdentity`를 모두 가져와 `identities` 변수에 밀어넣고, 선택기에서 다음 구문을 사용할 수 있습니다.

```typescript
selector: {
    data: <DataViewScopeIdentity[]>identities
}
```

##### <a name="example"></a>예제

다음 예제에서는 *fill* 속성 하나가 있는 customColor 개체의 objectEnumeration이 어떻게 표시되는지를 보여 줍니다. 이 개체를 다음과 같이 `dataViews[index].metadata.objects`에 정적으로 바인딩하려고 합니다.

```typescript
objectEnumeration.push({
    objectName: "customColor",
    displayName: "Custom Color",
    properties: {
        fill: {
            solid: {
                color: dataPoint.color
            }
        }
    },
    selector: null
});
```
