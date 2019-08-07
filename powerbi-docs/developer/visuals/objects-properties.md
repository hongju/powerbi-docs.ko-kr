---
title: 개체 및 속성
description: Power BI 시각적 개체의 사용자 지정 가능한 속성
author: MrMeison
ms.author: rasala
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: c22a1cfb281c9902d490e2320b85c2f6bbb63468
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/23/2019
ms.locfileid: "68424611"
---
# <a name="object-and-properties"></a>개체 및 속성

개체는 시각적 개체와 연결된 사용자 지정 가능한 속성을 설명합니다.
각 개체에 여러 개의 속성이 있을 수 있으며, 속성마다 연결된 형식이 있습니다.
형식은 속성이 무엇인지를 나타냅니다. 형식에 대한 자세한 내용은 아래를 참조하세요.

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

속성 형식에는 `ValueTypeDescriptor` 및 `StructuralTypeDescriptor`라는 두 가지 유형이 있습니다.

#### <a name="value-type-descriptor"></a>값 형식 설명자

`ValueTypeDescriptor`는 대체로 기본 형식이며 일반적으로 정적 개체로 사용됩니다.
다음은 몇 가지 일반적인 `ValueTypeDescriptor`입니다.

```typescript
export interface ValueTypeDescriptor {
    text?: boolean;
    numeric?: boolean;
    integer?: boolean;
    bool?: boolean;
}
```

#### <a name="structural-type-descriptor"></a>구조적 형식 설명자

`StructuralTypeDescriptor`는 데이터 바인딩된 개체에 주로 사용됩니다.
fill이 가장 일반적인 `StructuralTypeDescriptor`입니다.

```typescript
export interface StructuralTypeDescriptor {
    fill?: FillTypeDescriptor;
}
```

## <a name="gradient-property"></a>그라데이션 속성

그라데이션 속성은 표준 속성으로 설정할 수 없는 속성입니다. 대신, 색 선택 속성(채우기 유형)을 대체하는 규칙을 설정해야 합니다.
아래 예제를 참조하세요.

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

`"fill"` 및 `"fillRule"` 속성에 주의합니다. 첫 번째는 색 선택이고, 두 번째는 규칙 조건이 충족될 때 “fill” 속성 `visually`를 대체하는 그라데이션 대체 규칙입니다.

fill 속성과 대체 규칙 간의 연결은 `"fillRule"` 속성의 `"rule"`->`"output"` 섹션에서 설정됩니다.

`"Rule"`->`"InputRole"`은 규칙(조건)을 트리거하는 데이터 역할을 설정합니다. 이 예제에서는 데이터 역할 `"Gradient"`에 데이터가 포함된 경우 `"fill"` 속성에 규칙이 적용됩니다.

아래에서 채우기 규칙(`the last item`)을 트리거하는 데이터 역할의 예를 확인할 수 있습니다.

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

## <a name="enumerateobjectinstances-method"></a>`enumerateObjectInstances` 메서드

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

`enumerateObjectInstances`의 속성은 기능에서 정의한 속성을 반영합니다. 페이지 맨 아래에 있는 예제를 참조하세요.

### <a name="objects-selector"></a>개체 선택기

`enumerateObjectInstances`의 선택기는 각 개체가 dataView에 바인딩되는 위치를 결정합니다. 다음 네 가지 옵션이 있습니다.

#### <a name="static"></a>static

이 개체는 `dataviews[index].metadata.objects` 메타데이터에 바인딩됩니다.

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

이 개체는 만든 `selectionID`의 요소에 바인딩됩니다. 이 예제에서는 일부 dataPoints의 `selectionID`를 만들었으며 해당 ID를 반복한다고 가정합니다.

```typescript
for (let dataPoint in dataPoints) {
    ...
    selector: dataPoint.selectionID.getSelector()
}
```

#### <a name="scope-identity"></a>Scope identity

이 개체는 그룹의 교집합에 있는 특정 값에 바인딩됩니다. 예를 들어 `["Jan", "Feb", "March", ...]` 범주와 `["Small", "Medium", "Large"]` 계열이 있는 경우 `Feb` 및 `Large`와 일치하는 값의 교집합에 개체를 포함할 수 있습니다. 이 작업을 위해 두 열의 `DataViewScopeIdentity`를 모두 가져와 `identities` 변수에 푸시하고, 선택기에서 다음 구문을 사용할 수 있습니다.

```typescript
selector: {
    data: <DataViewScopeIdentity[]>identities
}
```

##### <a name="example"></a>예제

이 예제에서는 `fill` 속성 하나가 있는 customColor 개체의 objectEnumeration이 어떻게 표시되는지를 보여 줍니다. 이 개체를 `dataViews[index].metadata.objects`에 정적으로 바인딩하려고 합니다.

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
