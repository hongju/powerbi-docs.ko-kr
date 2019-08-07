---
title: 데이터 보기 매핑
description: 시각적 개체에 전달하기 전에 Power BI에서 데이터를 변환하는 방법
author: asander
ms.author: asander
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: ff70b2f12921694617a736164484df1326471eea
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/23/2019
ms.locfileid: "68425186"
---
# <a name="data-view-mappings-in-power-bi-visuals"></a>Power BI 시각적 개체의 데이터 뷰 매핑

`dataViewMappings`는 데이터 역할 간의 관계를 설명하고, 이러한 역할에 대해 조건부 요구 사항을 지정할 수 있도록 합니다.
각 `dataMappings`의 섹션이 있습니다.

각 유효한 매핑은 `DataView`를 생성하지만, 현재는 시각적 개체당 하나의 쿼리만 수행할 수 있으므로 대부분의 경우 `DataView` 한 개만 생성됩니다. 그러나 각기 다른 조건으로 여러 데이터 매핑을 제공할 수 있습니다.

```json
"dataViewMappings": [
    {
        "conditions": [ ... ],
        "categorical": { ... },
        "single": { ... },
        "table": { ... },
        "matrix": { ... }
    }
]
```

> [!NOTE]
> 중요한 점은 Power BI는 유효한 매핑이 `dataViewMappings`에 채워진 경우에만 DataView에 대한 매핑을 만든다는 사실입니다.

즉, 다음 예제와 같이 `dataViewMappings`에 `categorical`이 정의되어 있지만 `table`, `single` 등의 다른 매핑은 정의되지 않은 경우입니다.
```json
"dataViewMappings": [
    {
        "categorical": { ... }
    }
]
```

Power BI는 단일 `categorical` 매핑을 사용하여 `DataView`를 생성합니다(`table` 및 다른 매핑은 `undefined`가 됨).
```javascript
{
    "categorical": {
        "categories": [ ... ],
        "values": [ ... ]
    },
    "metadata": { ... }
}
```

## <a name="conditions"></a>조건

특정 데이터 매핑의 조건을 설명합니다. 여러 조건 집합을 제공할 수 있으며, 데이터가 설명된 조건 집합 중 하나와 일치하면 시각적 개체는 데이터를 유효한 것으로 허용합니다.

현재, 각 필드에 대해 최소값과 최대값을 지정할 수 있습니다. 이 값은 해당 데이터 역할에 바인딩할 수 있는 필드 수를 나타냅니다. 

> [!NOTE]
> 조건에서 데이터 역할을 생략하면 필드를 원하는 개수만큼 포함할 수 있습니다.

### <a name="example-1"></a>예제 1

여러 필드를 각 데이터 역할로 끌어올 수 있습니다. 이 예제에서는 범주를 데이터 필드 한 개로 제한하고, 측정값을 데이터 필드 두 개로 제한합니다.

```json
"conditions": [
    { "category": { "max": 1 }, "y": { "max": 2 } },
]
```

### <a name="example-2"></a>예제 2

이 예제에서는 두 조건 중 하나가 필수입니다. 정확히 범주 데이터 필드 한 개와 측정값 두 개 또는 정확히 범주 두 개와 측정값 한 개를 사용해야 합니다.

```json
"conditions": [
    { "category": { "min": 1, "max": 1 }, "measure": { "min": 2, "max": 2 } },
    { "category": { "min": 2, "max": 2 }, "measure": { "min": 1, "max": 1 } }
]
```

## <a name="single-data-mapping"></a>단일 데이터 매핑

단일 데이터 매핑은 가장 간단한 형태의 데이터 매핑입니다. 단일 측정값 필드를 허용하고 합계를 제공합니다. 필드가 숫자이면 합계를 제공합니다. 숫자가 아니면 고유 값 개수를 제공합니다.

단일 데이터 매핑을 사용하려면 매핑할 데이터 역할의 이름을 정의해야 합니다. 이 매핑은 단일 측정값 필드에만 적용됩니다. 두 번째 필드를 할당하면 데이터 뷰가 생성되지 않습니다. 따라서 데이터를 단일 필드로 제한하는 조건을 포함하는 것도 좋은 방법입니다.

> [!NOTE]
> 이 데이터 매핑은 다른 데이터 매핑과 함께 사용할 수 없습니다. 데이터를 단일 숫자 값으로 줄이기 위한 것입니다.

### <a name="example-3"></a>예제 3

```json
"dataViewMappings": {
    "conditions": [
        { "Y": { "max": 1 } }
    ],
    "single": {
        "role": "Y"
    }
}  
```

결과 데이터 뷰에는 다른 유형(테이블, 범주 등)이 계속 포함되지만, 각 매핑에는 단일 값만 포함됩니다. 모범 사례는 단일 필드의 값에만 액세스하는 것입니다.

```JSON
{
    "dataView": [
        {
            "metadata": null,
            "categorical": null,
            "matrix": null,
            "table": null,
            "tree": null,
            "single": {
                "value": 94163140.3560001
            }
        }
    ]
}
```

## <a name="categorical-data-mapping"></a>범주 데이터 매핑

범주 데이터 매핑은 하나 또는 두 개의 독립적인 데이터 그룹화를 가져오는 데 사용됩니다.

### <a name="example-4"></a>예제 4

다음은 DataRoles에 대한 이전 예제의 정의입니다.

```json
"dataRole":[
    {
        "displayName": "Category",
        "name": "category",
        "kind": "Grouping"
    },
    {
        "displayName": "Y Axis",
        "name": "measure",
        "kind": "Measure"
    }
]
```

이제 매핑을 위해 다음을 사용합니다.

```json
"dataViewMappings": {
    "categorical": {
        "categories": {
            "for": { "in": "category" }
        },
        "values": {
            "select": [
                { "bind": { "to": "measure" } }
            ]
        }
    }
}
```

이 간단한 예제는 “`category`로 끌어오는 모든 필드에 대해 해당 데이터가 `categorical.categories`로 매핑되도록 `category` DataRole을 매핑합니다. 또한 `measure` DataRole을 `categorical.values`에 매핑합니다.”로 명료하게 정의합니다.

* **for...in** - 이 데이터 역할의 모든 항목을 데이터 쿼리에 포함합니다.
* **bind...to** - for...in과 동일한 결과를 생성하지만 DataRole에 단일 필드로 제한하는 조건이 포함될 것으로 예상됩니다.

### <a name="example-5"></a>예제 5

이 예제에서는 이전 예제의 처음 두 개 DataRoles를 사용하고 `grouping` 및 `measure2`도 추가로 정의합니다.

```json
"dataRole":[
    {
        "displayName": "Category",
        "name": "category",
        "kind": "Grouping"
    },
    {
        "displayName": "Y Axis",
        "name": "measure",
        "kind": "Measure"
    },
    {
        "displayName": "Grouping with",
        "name": "grouping",
        "kind": "Grouping"
    },
    {
        "displayName": "X Axis",
        "name": "measure2",
        "kind": "Grouping"
    }
]
```

이제 매핑을 위해 다음을 사용합니다.

```json
"dataViewMappings":{
    "categorical": {
        "categories": {
            "for": { "in": "category" }
        },
        "values": {
            "group": {
                "by": "grouping",
                "select":[
                    { "bind": { "to": "measure" } },
                    { "bind": { "to": "measure2" } }
                ]
            }
        }
    }
}
```

여기서 차이점은 categorical.values를 매핑하는 방법에 있습니다. “`measure` 및 `measure2` 데이터 역할을 `grouping` 데이터 역할로 그룹화되도록 매핑합니다.”로 정의합니다.

### <a name="example-6"></a>예제 6

다음은 dataRoles입니다.

```json
"dataRoles": [
    {
        "displayName": "Categories",
        "name": "category",
        "kind": "Grouping"
    },
    {
        "displayName": "Measures",
        "name": "measure",
        "kind": "Measure"
    },
    {
        "displayName": "Series",
        "name": "series",
        "kind": "Measure"
    }
]
```

다음은 dataViewMapping입니다.

```json
"dataViewMappings": [
    {
        "categorical": {
            "categories": {
                "for": {
                    "in": "category"
                }
            },
            "values": {
                "group": {
                    "by": "series",
                    "select": [{
                            "for": {
                                "in": "measure"
                            }
                        }
                    ]
                }
            }
        }
    }
]
```

범주 `dataview`는 다음과 같이 시각화할 수 있습니다.

| 범주별 |  |  | | | |
|-----|-----|------|------|------|------|
| | 연도 | 2013 | 2014 | 2015 | 2016 |
| 국가 | | |
| 미국 | | x | x | 125 | 100 |
| 캐나다 | | x | 50 | 200 | x |
| 멕시코 | | 300 | x | x | x |
| 영국 | | x | x | 75 | x |

Power BI는 범주 dataview로 생성합니다. 범주 집합입니다.

```JSON
{
    "categorical": {
        "categories": [
            {
                "source": {...},
                "values": [
                    "Canada",
                    "Mexico",
                    "UK",
                    "USA"
                ],
                "identity": [...],
                "identityFields": [...],
            }
        ]
    }
}
```

각 범주도 값 집합에 매핑됩니다. 각 값은 계열(연도)별로 그룹화됩니다.

예를 들어 2013년의 캐나다 판매량은 null이고, 2014년의 캐나다 판매량은 50입니다.

```JSON
{
    "values": [
        {
            "source": {...},
            "values": [
                null,
                300,
                null,
                null
            ],
            "identity": [...],
        },
        {
            "source": {...},
            "values": [
                50,
                null,
                150,
                null
            ],
            "identity": [...],
        },
        {
            "source": {...},
            "values": [
                200,
                null,
                null,
                125
            ],
            "identity": [...],
        },
        {
            "source": {...},
            "values": [
                null,
                null,
                null,
                100
            ],
            "identity": [...],
        }
    ]
}
```

## <a name="table-data-mapping"></a>테이블 데이터 매핑

테이블 데이터 뷰는 간단한 데이터 매핑입니다. 기본적으로 숫자 데이터 요소를 집계할 수 있는 데이터 요소 목록입니다.

### <a name="example-7"></a>예제 7

다음은 지정된 기능입니다.

```json
"dataRoles": [
    {
        "displayName": "Values",
        "name": "values",
        "kind": "Measure"
    }
]
```

```json
"dataViewMappings": [
    {
        "table": {
            "rows": {
                "for": {
                    "in": "values"
                }
            }
        }
    }
]
```

테이블 `dataview`는 다음과 같이 시각화할 수 있습니다.  

| 국가| 연도 | 판매 |
|-----|-----|------|
| 미국 | 2016 | 100 |
| 미국 | 2015 | 50 |
| 캐나다 | 2015 | 200 |
| 캐나다 | 2015 | 50 |
| 멕시코 | 2013 | 300 |
| 영국 | 2014 | 150 |
| 미국 | 2015 | 75 |

Power BI는 테이블 dataview로 생성합니다. 순서가 있다고 가정하지 마세요.

```JSON
{
    "table" : {
        "columns": [...],
        "rows": [
            [
                "Canada",
                2014,
                50
            ],
            [
                "Canada",
                2015,
                200
            ],
            [
                "Mexico",
                2013,
                300
            ],
            [
                "UK",
                2014,
                150
            ],
            [
                "USA",
                2015,
                100
            ],
            [
                "USA",
                2015,
                75
            ],
            [
                "USA",
                2016,
                100
            ]
        ]
    }
}
```

원하는 필드를 선택하고 합계를 클릭하면 데이터를 집계할 수 있습니다.  

![데이터 집계](./media/data-aggregation.png)

## <a name="matrix-data-mapping"></a>행렬 데이터 매핑

행렬 데이터 매핑은 테이블 데이터 매핑과 유사하지만 행이 계층적으로 표시됩니다. 또한 `dataRole` 값 중 하나를 열 머리글 값으로 사용할 수 있습니다.

```json
{
    "dataRoles": [
        {
            "name": "Category",
            "displayName": "Category",
            "displayNameKey": "Visual_Category",
            "kind": "Grouping"
        },
        {
            "name": "Column",
            "displayName": "Column",
            "displayNameKey": "Visual_Column",
            "kind": "Grouping"
        },
        {
            "name": "Measure",
            "displayName": "Measure",
            "displayNameKey": "Visual_Values",
            "kind": "Measure"
        }
    ],
    "dataViewMappings": [
        {
            "matrix": {
                "rows": {
                    "for": {
                        "in": "Category"
                    }
                },
                "columns": {
                    "for": {
                        "in": "Column"
                    }
                },
                "values": {
                    "select": [
                        {
                            "for": {
                                "in": "Measure"
                            }
                        }
                    ]
                }
            }
        }
    ]
}
```

Power BI는 계층적 데이터 구조를 만듭니다. 트리의 루트에는 `Category` 데이터 역할의 첫 번째 열 데이터가 포함되고, 데이터 역할의 두 번째 열이 자식으로 포함됩니다.

데이터 세트:

| 부모 | 자식 | 손자 | 열 | 값 |
|-----|-----|------|-------|-------|
| Parent1 | Child1 | Grand child1 | Col1 | 5 |
| Parent1 | Child1 | Grand child1 | Col2 | 6 |
| Parent1 | Child1 | Grand child2 | Col1 | 7 |
| Parent1 | Child1 | Grand child2 | Col2 | 8 |
| Parent1 | Child2 | Grand child3 | Col1 | 5 |
| Parent1 | Child2 | Grand child3 | Col2 | 3 |
| Parent1 | Child2 | Grand child4 | Col1 | 4 |
| Parent1 | Child2 | Grand child4 | Col2 | 9 |
| Parent1 | Child2 | Grand child5 | Col1 | 3 |
| Parent1 | Child2 | Grand child5 | Col2 | 5 |
| Parent2 | Child3 | Grand child6 | Col1 | 1 |
| Parent2 | Child3 | Grand child6 | Col2 | 2 |
| Parent2 | Child3 | Grand child7 | Col1 | 7 |
| Parent2 | Child3 | Grand child7 | Col2 | 1 |
| Parent2 | Child3 | Grand child8 | Col1 | 10 |
| Parent2 | Child3 | Grand child8 | Col2 | 13 |

Power BI의 핵심 행렬 시각적 개체는 테이블처럼 렌더링합니다.

![행렬 시각적 개체](./media/matrix-visual-smaple.png)

시각적 개체는 아래에 설명된 데이터 구조를 갖습니다(처음 두 행만 표시됨).

```json
{
    "metadata": {...},
    "matrix": {
        "rows": {
            "levels": [...],
            "root": {
                "childIdentityFields": [...],
                "children": [
                    {
                        "level": 0,
                        "levelValues": [...],
                        "value": "Parent1",
                        "identity": {...},
                        "childIdentityFields": [...],
                        "children": [
                            {
                                "level": 1,
                                "levelValues": [...],
                                "value": "Child1",
                                "identity": {...},
                                "childIdentityFields": [...],
                                "children": [
                                    {
                                        "level": 2,
                                        "levelValues": [...],
                                        "value": "Grand child1",
                                        "identity": {...},
                                        "values": {
                                            "0": {
                                                "value": 5 // value for Col1
                                            },
                                            "1": {
                                                "value": 6 // value for Col2
                                            }
                                        }
                                    },
                                    ...
                                ]
                            },
                            ...
                        ]
                    },
                    ...
                ]
            }
        },
        "columns": {
            "levels": [...],
            "root": {
                "childIdentityFields": [...],
                "children": [
                    {
                        "level": 0,
                        "levelValues": [...],
                        "value": "Col1",
                        "identity": {...}
                    },
                    {
                        "level": 0,
                        "levelValues": [...],
                        "value": "Col2",
                        "identity": {...}
                    },
                    ...
                ]
            }
        },
        "valueSources": [...]
    }
}
```

## <a name="data-reduction-algorithm"></a>데이터 감소 알고리즘

DataView에 수신되는 데이터양을 제어하려는 경우 `DataReductionAlgorithm`을 적용할 수 있습니다.

기본적으로 모든 사용자 지정 시각적 개체에는 “count”가 1000개 데이터 요소로 설정된 위쪽 DataReductionAlgorithm이 적용되어 있습니다. capabilities.json에서 다음 속성을 설정하는 것과 같습니다.

```json
"dataReductionAlgorithm": {
    "top": {
        "count": 1000
    }
}
```

‘count’ 값을 최대 30000까지 임의의 정수 값으로 수정할 수 있습니다. R 기반 사용자 지정 시각적 개체는 최대 150000개의 행을 지원할 수 있습니다.

## <a name="data-reduction-algorithm-types"></a>데이터 감소 알고리즘 유형

`DataReductionAlgorithm` 설정에는 다음 네 가지 유형이 있습니다.

* `top` - 데이터를 데이터 세트의 위쪽에서 가져온 값으로 제한하려는 경우에 사용합니다. 데이터 세트에서 위쪽 첫 번째 “count” 값을 가져옵니다.
* `bottom` - 데이터를 데이터 세트의 아래쪽에서 가져온 값으로 제한하려는 경우에 사용합니다. 데이터 세트에서 마지막 “count” 값을 가져옵니다.
* `sample` - “count” 개수의 항목으로 제한된 간단한 샘플링 알고리즘을 통해 데이터 세트를 줄입니다. 즉, 첫 번째 항목과 마지막 항목이 포함되고 그 사이에 동일한 간격으로 “count” 개수의 항목이 포함됩니다.
예를 들어 데이터 세트 [0, 1, 2, ... 100]과 `count: 9`가 있는 경우 [0, 10, 20 ... 100] 값이 표시됩니다.
* `window` - “count” 개수의 요소를 포함하는 데이터 요소 ‘창’을 한 번에 하나씩 로드합니다. 현재 `top`과 `window`는 동일합니다. 창 설정을 완전히 지원하기 위한 작업을 진행 중입니다.

## <a name="data-reduction-algorithm-usage"></a>데이터 감소 알고리즘 사용

범주, 테이블 또는 행렬 `dataview` 매핑에 `DataReductionAlgorithm`을 사용할 수 있습니다.

범주 데이터 매핑의 경우 `categories` 및/또는 `values` 그룹 섹션에 설정할 수 있습니다.

### <a name="example-8"></a>예제 8

```json
"dataViewMappings": {
    "categorical": {
        "categories": {
            "for": { "in": "category" },
            "dataReductionAlgorithm": {
                "window": {
                    "count": 300
                }
            }  
        },
        "values": {
            "group": {
                "by": "series",
                "select": [{
                        "for": {
                            "in": "measure"
                        }
                    }
                ],
                "dataReductionAlgorithm": {
                    "top": {
                        "count": 100
                    }
                }  
            }
        }
    }
}
```

테이블 `dataview` 매핑의 `rows` 섹션에 데이터 감소 알고리즘을 적용할 수 있습니다.

### <a name="example-9"></a>예제 9

```json
"dataViewMappings": [
    {
        "table": {
            "rows": {
                "for": {
                    "in": "values"
                },
                "dataReductionAlgorithm": {
                    "top": {
                        "count": 2000
                    }
                } 
            }
        }
    }
]
```

`matrix` `dataview` 매핑의 `rows` 및/또는 `columns` 섹션에 데이터 감소 알고리즘을 적용할 수 있습니다.
