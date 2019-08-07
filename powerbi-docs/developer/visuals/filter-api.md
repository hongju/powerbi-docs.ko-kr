---
title: 시각적 개체 필터 API
description: Power BI 시각적 개체가 다른 시각적 개체를 필터링할 수 있는 방법
author: sranins
ms.author: rasala
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 50e9601faf497675ebc3f24609a856a600e3bcb1
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/23/2019
ms.locfileid: "68425048"
---
# <a name="power-bi-visual-filters-api"></a>Power BI 시각적 개체 필터 API

필터 시각적 개체는 데이터 필터링을 허용합니다. 선택과의 주요 차이점은 다른 시각적 개체의 강조 표시 지원과 관계없이 다른 시각적 개체가 어떤 방식으로든 필터링된다는 것입니다.

시각적 개체에 대해 필터링을 사용하려면 시각적 개체가 capabilities.json 콘텐츠의 `general` 섹션에 `filter` 개체를 포함해야 합니다.

```json
"objects": {
        "general": {
            "displayName": "General",
            "displayNameKey": "formattingGeneral",
            "properties": {
                "filter": {
                    "type": {
                        "filter": true
                    }
                }
            }
        }
    }
```

필터 API 인터페이스는 [`powerbi-models`](https://www.npmjs.com/package/powerbi-models) 패키지에서 사용할 수 있습니다. 패키지에는 필터 인스턴스를 만들기 위한 클래스도 포함되어 있습니다.

```cmd
npm install powerbi-models --save
```

이전 버전 도구(3.x.x 이전 버전)를 사용하는 경우 시각적 패키지에 `powerbi-models`를 포함해야 합니다. [패키지를 포함하는 방법에 대한 간략한 가이드](https://github.com/Microsoft/powerbi-visuals-sampleslicer/blob/master/doc/AddingAdvancedFilterAPI.md)

모든 필터는 `IFilter` 인터페이스를 확장합니다.

```typescript
export interface IFilter {
    $schema: string;
    target: IFilterTarget;
}
```

`target` - 데이터 원본의 테이블 열입니다.

## <a name="basic-filter-api"></a>기본 필터 API

기본 필터 인터페이스는 다음과 같습니다.

```typescript
export interface IBasicFilter extends IFilter {
    operator: BasicFilterOperators;
    values: (string | number | boolean)[];
}
```

`operator` - 값이 “In”, “NotIn”, “All”인 열거형입니다.

`values` - 조건의 값입니다.

기본 필터 예제:

```typescript
let basicFilter = {
    target: {
        column: "Col1"
    },
    operator: "In",
    values: [1,2,3]
}
```

이 필터는 “`col1`이 값 1, 2, 3 중 하나와 같은 모든 행 제공”을 의미합니다.

해당하는 SQL 구문은 다음과 같습니다.

```sql
SELECT * FROM table WHERE col1 IN ( 1 , 2 , 3 )
```

필터를 만들기 위해 `powerbi-models`의 BasicFilter 클래스를 사용할 수 있습니다.

이전 버전의 도구를 사용하는 경우 `window['powerbi-models']`를 통해 창 개체의 모델 인스턴스를 가져와야 합니다.

```javascript
let categories: DataViewCategoricalColumn = this.dataView.categorical.categories[0];

let target: IFilterColumnTarget = {
    table: categories.source.queryName.substr(0, categories.source.queryName.indexOf('.')),
    column: categories.source.displayName
};

let values = [ 1, 2, 3 ];

let filter: IBasicFilter = new window['powerbi-models'].BasicFilter(target, "In", values);
```

시각적 개체는 생성자의 시각적 개체에 제공된 호스트 인터페이스 IVisualHost의 applyJsonFilter() 메서드를 사용하여 필터를 호출합니다.

```typescript
visualHost.applyJsonFilter(filter, "general", "filter", FilterAction.merge);
```

## <a name="advanced-filter-api"></a>고급 필터 API

[고급 필터 API](https://github.com/Microsoft/powerbi-models)를 사용하면 여러 조건(예: “LessThan”, “Contains”, “Is”, “IsBlank” 등)을 기준으로 복잡한 교차 시각적 개체 데이터 요소 선택/필터링 쿼리를 사용할 수 있습니다.

이 필터는 시각적 개체 API 1.7.0에서 도입되었습니다.

또한 고급 필터 API를 사용하려면 `target`에 `table` 및 `column` 이름이 포함되어 있어야 합니다. 그러나 고급 필터 API 연산자는 `"And" | "Or"`입니다. 

뿐만 아니라, 이 필터는 다음과 같이 인터페이스에 값 대신 조건을 사용합니다.

```typescript
interface IAdvancedFilterCondition {
    value: (string | number | boolean);
    operator: AdvancedFilterConditionOperators;
}
```

`operator` 매개 변수의 조건 연산자는 `"None" | "LessThan" | "LessThanOrEqual" | "GreaterThan" | "GreaterThanOrEqual" | "Contains" | "DoesNotContain" | "StartsWith" | "DoesNotStartWith" | "Is" | "IsNot" | "IsBlank" | "IsNotBlank"`입니다.

```javascript
let categories: DataViewCategoricalColumn = this.dataView.categorical.categories[0];

let target: IFilterColumnTarget = {
    table: categories.source.queryName.substr(0, categories.source.queryName.indexOf('.')), // table
    column: categories.source.displayName // col1
};

let conditions: IAdvancedFilterCondition[] = [];

conditions.push({
    operator: "LessThan",
    value: 0
});

let filter: IAdvancedFilter = new window['powerbi-models'].AdvancedFilter(target, "And", conditions);

// invoke the filter
visualHost.applyJsonFilter(filter, "general", "filter", FilterAction.merge);
```

해당하는 SQL 구문은 다음과 같습니다.

```sql
SELECT * FROM table WHERE col1 < 0;
```

고급 필터 API를 사용하는 전체 샘플 코드는 [`Sampleslicer visual` 리포지토리](https://github.com/Microsoft/powerbi-visuals-sampleslicer)에서 확인할 수 있습니다.

## <a name="tuple-filter-api-multi-column-filter"></a>튜플 필터 API(다중 열 필터)

튜플 필터 API는 시각적 개체 API 2.3.0에서 도입되었습니다.

튜플 필터 API는 기본 필터와 비슷하지만 여러 열과 테이블에 대한 조건을 정의할 수 있습니다.

또한 필터에는 인터페이스가 있습니다. 

```typescript
interface ITupleFilter extends IFilter {
    $schema: string;
    filterType: FilterType;
    operator: TupleFilterOperators;
    target: ITupleFilterTarget;
    values: TupleValueType[];
}
```

`target`은 테이블 이름이 포함된 열 배열입니다.

```typescript
declare type ITupleFilterTarget = IFilterTarget[];
```

  이 필터는 여러 테이블의 열을 처리할 수 있습니다.

`$schema`는 “http://powerbi.com/product/schema#tuple”입니다.

`filterType`은 “`FilterType.Tuple`”입니다.

`operator`에는 `"In"` 연산자만 사용할 수 있습니다.

`values`는 값 튜플 배열이고, 각 튜플은 대상 열 값의 허용되는 조합 하나를 나타냅니다. 

```typescript
declare type TupleValueType = ITupleElementValue[];

interface ITupleElementValue {
    value: PrimitiveValueType
}
```

전체 예제:

```typescript
let target: ITupleFilterTarget = [
    {
        table: "DataTable",
        column: "Team"
    },
    {
        table: "DataTable",
        column: "Value"
    }
];

let values = [
    [
        // the 1st column combination value (aka column tuple/vector value) that the filter will pass through
        {
            value: "Team1" // the value for `Team` column of `DataTable` table
        },
        {
            value: 5 // the value for `Value` column of `DataTable` table
        }
    ],
    [
        // the 2nd column combination value (aka column tuple/vector value) that the filter will pass through
        {
            value: "Team2" // the value for `Team` column of `DataTable` table
        },
        {
            value: 6 // the value for `Value` column of `DataTable` table
        }
    ]
];

let filter: ITupleFilter = {
    $schema: "http://powerbi.com/product/schema#tuple",
    filterType: FilterType.Tuple,
    operator: "In",
    target: target,
    values: values
}

// invoke the filter
visualHost.applyJsonFilter(filter, "general", "filter", FilterAction.merge);
```

**열 이름 순서와 조건 값이 중요합니다.**

해당하는 SQL 구문은 다음과 같습니다.

```sql
SELECT * FROM DataTable WHERE ( Team = "Team1" AND Value = 5 ) OR ( Team = "Team2" AND Value = 6 );
```  

## <a name="restoring-json-filter-from-dataview"></a>DataView에서 JSON 필터 복원

API 2.2부터 **VisualUpdateOptions**에서 **JSON 필터**를 복원할 수 있습니다.

```typescript
export interface VisualUpdateOptions extends extensibility.VisualUpdateOptions {
    viewport: IViewport;
    dataViews: DataView[];
    type: VisualUpdateType;
    viewMode?: ViewMode;
    editMode?: EditMode;
    operationKind?: VisualDataChangeOperationKind;
    jsonFilters?: IFilter[];
}
```

스위치 책갈피를 사용하고 시각적 개체가 해당 `filter` 개체를 가져오는 경우 Power BI는 시각적 개체의 `update` 메서드를 호출합니다.
[책갈피 지원에 대한 자세한 정보](bookmarks-support.md)

### <a name="sample-json-filter"></a>샘플 JSON 필터

![JSON 필터 스크린샷](./media/json-filter.png)

### <a name="clear-json-filter"></a>JSON 필터 지우기

필터 API는 필터의 `null` 값을 재설정 또는 지우기로 허용합니다.

```typescript
// invoke the filter
visualHost.applyJsonFilter(null, "general", "filter", FilterAction.merge);
```
