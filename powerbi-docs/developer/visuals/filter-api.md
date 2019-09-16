---
title: Power BI 시각적 개체의 시각적 개체 필터 API
description: 이 문서에서는 Power BI 시각적 개체가 다른 시각적 개체를 필터링할 수 있는 방법을 설명합니다.
author: sranins
ms.author: rasala
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: fc0b21116888c8455d4d7b8efc5c476bfc592483
ms.sourcegitcommit: b602cdffa80653bc24123726d1d7f1afbd93d77c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70237117"
---
# <a name="the-visual-filters-api-in-power-bi-visuals"></a>Power BI 시각적 개체의 시각적 개체 필터 API

시각적 개체 필터 API를 사용하면 Power BI 시각적 개체의 데이터를 필터링할 수 있습니다. 다른 선택 항목과의 주요 차이점은 다른 시각적 개체의 강조 표시 지원과 관계없이 다른 시각적 개체가 어떤 방식으로든 필터링된다는 것입니다.

시각적 개체에 대해 필터링을 사용하려면 시각적 개체가 *capabilities.json* 코드의 `general` 섹션에 `filter` 개체를 포함해야 합니다.

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

시각적 개체 필터 API 인터페이스는 [powerbi-models](https://www.npmjs.com/package/powerbi-models) 패키지에서 사용할 수 있습니다. 패키지에는 필터 인스턴스를 만들기 위한 클래스도 포함되어 있습니다.

```cmd
npm install powerbi-models --save
```

이전(3.x.x 이전) 버전의 도구를 사용하는 경우 시각적 개체 패키지에 `powerbi-models`를 포함해야 합니다. 자세한 내용은 간단한 가이드인 [사용자 지정 시각적 개체에 고급 필터 API 추가](https://github.com/Microsoft/powerbi-visuals-sampleslicer/blob/master/doc/AddingAdvancedFilterAPI.md)를 참조하세요.

모든 필터는 다음 코드와 같이 `IFilter` 인터페이스를 확장합니다.

```typescript
export interface IFilter {
    $schema: string;
    target: IFilterTarget;
}
```
조건:
* `target`은 데이터 원본의 테이블 열입니다.

## <a name="the-basic-filter-api"></a>기본 필터 API

기본 필터 인터페이스는 다음 코드에 나와 있습니다.

```typescript
export interface IBasicFilter extends IFilter {
    operator: BasicFilterOperators;
    values: (string | number | boolean)[];
}
```

조건:
* `operator`는 *In*, *NotIn*, *All* 값을 포함하는 열거형입니다.
* `values`는 조건의 값입니다.

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

이 필터는 “`col1`이 값 1, 2 또는 3과 같은 모든 행 제공”을 의미합니다.

해당하는 SQL 구문은 다음과 같습니다.

```sql
SELECT * FROM table WHERE col1 IN ( 1 , 2 , 3 )
```

필터를 만들기 위해 `powerbi-models`의 BasicFilter 클래스를 사용할 수 있습니다.

이전 버전의 도구를 사용하는 경우, 다음 코드와 같이 `window['powerbi-models']`를 사용하여 창 개체의 모델 인스턴스를 가져와야 합니다.

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

## <a name="the-advanced-filter-api"></a>고급 필터 API

[고급 필터 API](https://github.com/Microsoft/powerbi-models)를 사용하면 *LessThan*, *Contains*, *Is*, *IsBlank* 등의 여러 조건을 기반으로 하는 복잡한 교차 시각적 개체 데이터 요소 선택 및 필터링 쿼리를 사용할 수 있습니다.

이 필터는 시각적 개체 API 1.7.0에서 도입되었습니다.

고급 필터 API를 사용하려면 `table` 및 `column` 이름이 포함된 `target`도 필요합니다. 그러나 고급 필터 API 연산자는 *And*와 *Or*입니다. 

또한 이 필터는 다음과 같이 인터페이스에 값 대신 조건을 사용합니다.

```typescript
interface IAdvancedFilterCondition {
    value: (string | number | boolean);
    operator: AdvancedFilterConditionOperators;
}
```

`operator` 매개 변수의 조건 연산자는 *None*, *LessThan*, *LessThanOrEqual*, *GreaterThan*, *GreaterThanOrEqual*, *Contains*, *DoesNotContain*, *StartsWith*, *DoesNotStartWith*, *Is*, *IsNot*, *IsBlank*, “IsNotBlank”입니다.

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

고급 필터 API를 사용하는 전체 샘플 코드를 보려면 [Sampleslicer 시각적 개체 리포지토리](https://github.com/Microsoft/powerbi-visuals-sampleslicer)로 이동합니다.

## <a name="the-tuple-filter-api-multi-column-filter"></a>튜플 필터 API(다중 열 필터)

튜플 필터 API는 시각적 개체 API 2.3.0에서 도입되었습니다. 기본 필터 API와 비슷하지만 여러 열과 테이블의 조건을 정의할 수 있습니다.

필터 인터페이스는 다음 코드에 나와 있습니다. 

```typescript
interface ITupleFilter extends IFilter {
    $schema: string;
    filterType: FilterType;
    operator: TupleFilterOperators;
    target: ITupleFilterTarget;
    values: TupleValueType[];
}
```

조건:
* `target`은 테이블 이름이 포함된 열 배열입니다.

    ```typescript
    declare type ITupleFilterTarget = IFilterTarget[];
    ```

  이 필터는 다양한 테이블의 열을 처리할 수 있습니다.

* `$schema`는 http://powerbi.com/product/schema#tuple 입니다.

* `filterType`은 *FilterType.Tuple*입니다.

* `operator`는 *In* 연산자에서만 사용할 수 있습니다.

* `values`는 값 튜플 배열이고, 각 튜플은 허용되는 대상 열 값의 조합 하나를 나타냅니다. 

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
        // the first column combination value (or the column tuple/vector value) that the filter will pass through
        {
            value: "Team1" // the value for the `Team` column of the `DataTable` table
        },
        {
            value: 5 // the value for the `Value` column of the `DataTable` table
        }
    ],
    [
        // the second column combination value (or the column tuple/vector value) that the filter will pass through
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

> [!IMPORTANT]
> 열 이름 및 조건 값의 순서가 중요합니다.

해당하는 SQL 구문은 다음과 같습니다.

```sql
SELECT * FROM DataTable WHERE ( Team = "Team1" AND Value = 5 ) OR ( Team = "Team2" AND Value = 6 );
```  

## <a name="restore-the-json-filter-from-the-data-view"></a>데이터 뷰에서 JSON 필터 복원

API 버전 2.2부터, 다음 코드와 같이 *VisualUpdateOptions*에서 JSON 필터를 복원할 수 있습니다.

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

책갈피를 전환하면 Power BI가 시각적 개체의 `update` 메서드를 호출하고, 시각적 개체는 해당 `filter` 개체를 가져옵니다. 자세한 내용은 [Power BI 시각적 개체에 대해 책갈피 지원 추가](bookmarks-support.md)를 참조하세요.

### <a name="sample-json-filter"></a>샘플 JSON 필터

다음 그림은 몇 가지 샘플 JSON 필터 코드를 보여 줍니다.

![JSON 필터 코드](./media/json-filter.png)

### <a name="clear-the-json-filter"></a>JSON 필터 지우기

필터 API는 필터의 `null` 값을 ‘다시 설정’ 또는 ‘지우기’로 허용합니다.  

```typescript
// invoke the filter
visualHost.applyJsonFilter(null, "general", "filter", FilterAction.merge);
```
