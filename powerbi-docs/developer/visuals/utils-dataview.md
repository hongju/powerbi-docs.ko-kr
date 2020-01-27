---
title: Power BI 시각적 개체에서 데이터 뷰 유틸리티를 사용하는 방법 소개
description: 이 문서에서는 SVG 유틸리티를 사용하여 Power BI 시각적 개체의 DataView 개체 구문 분석을 간소화하는 방법을 설명합니다.
author: vtkalek
ms.author: asander
manager: asander
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 16dc3c6ec1125f85282670091bc41057ae5b1112
ms.sourcegitcommit: 4359baa43ca01b179d28ec59f4e61ba8c07ee288
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75308666"
---
# <a name="dataviewutils"></a>DataViewUtils

`DataViewUtils`는 Power BI 사용자 지정 시각적 개체의 DataView 개체 구문 분석을 간소화하는 함수 및 클래스 세트입니다.

## <a name="installation"></a>설치

패키지를 설치하려면 현재 사용자 지정 시각적 개체가 있는 디렉터리에서 다음 명령을 실행해야 합니다.

npm install powerbi-visuals-utils-dataviewutils --save 이 명령은 패키지를 설치하고 package.json에 패키지를 종속성으로 추가합니다.

## <a name="datarolehelper"></a>DataRoleHelper

`DataRoleHelper`는 dataView 개체의 역할을 확인하는 함수를 제공합니다.

이 모듈은 다음과 같은 함수를 제공합니다.

### <a name="getmeasureindexofrole"></a>getMeasureIndexOfRole

이 함수는 역할 이름으로 측정값을 찾은 다음, 해당 인덱스를 반환합니다.

```typescript
function getMeasureIndexOfRole(grouped: DataViewValueColumnGroup[], roleName: string): number;
```

예제:

```typescript
import powerbi from "powerbi-visuals-api";
import DataViewValueColumnGroup = powerbi.DataViewValueColumnGroup;
import { dataRoleHelper } from "powerbi-visuals-utils-dataviewutils";
// ...

// This object is actually a part of the dataView object.
let columnGroup: DataViewValueColumnGroup[] = [{
    values: [
        {
            source: {
                displayName: "Microsoft",
                roles: {
                    "company": true
                }
            },
            values: []
        },
        {
            source: {
                displayName: "Power BI",
                roles: {
                    "product": true
                }
            },
            values: []
        }
    ]
}];

dataRoleHelper.getMeasureIndexOfRole(columnGroup, "product");

// returns: 1
```

### <a name="getcategoryindexofrole"></a>getCategoryIndexOfRole

이 함수는 역할 이름으로 범주를 찾은 다음, 해당 인덱스를 반환합니다.

```typescript
function getCategoryIndexOfRole(categories: DataViewCategoryColumn[], roleName: string): number;
```

예제:

```typescript
import powerbi from "powerbi-visuals-api";
import DataViewCategoryColumn = powerbi.DataViewCategoryColumn;
import { dataRoleHelper } from "powerbi-visuals-utils-dataviewutils";
// ...

// This object is actually a part of the dataView object.
let categoryGroup: DataViewCategoryColumn[] = [
    {
        source: {
            displayName: "Microsoft",
            roles: {
                "company": true
            }
        },
        values: []
    },
    {
        source: {
            displayName: "Power BI",
            roles: {
                "product": true
            }
        },
        values: []
    }
];

dataRoleHelper.getCategoryIndexOfRole(categoryGroup, "product");

// returns: 1
```

### <a name="hasrole"></a>hasRole

이 함수는 제공된 역할이 메타데이터에 정의되어 있는지 확인합니다.

```typescript
function hasRole(column: DataViewMetadataColumn, name: string): boolean;
```

예제:

```typescript
import powerbi from "powerbi-visuals-api";
import DataViewMetadataColumn = powerbi.DataViewMetadataColumn;
import { dataRoleHelper } from "powerbi-visuals-utils-dataviewutils";

// This object is actually a part of the dataView object.
let metadata: DataViewMetadataColumn = {
    displayName: "Microsoft",
    roles: {
        "company": true
    }
};

DataRoleHelper.hasRole(metadata, "company");

// returns: true
```

### <a name="hasroleindataview"></a>hasRoleInDataView

이 함수는 제공된 역할이 dataView에 정의되어 있는지 확인합니다.

```typescript
function hasRoleInDataView(dataView: DataView, name: string): boolean;
```

예제:

```typescript
import powerbi from "powerbi-visuals-api";
import DataView = powerbi.DataView;
import { dataRoleHelper } from "powerbi-visuals-utils-dataviewutils";

// This object is actually a part of the dataView object.
let dataView: DataView = {
    metadata: {
        columns: [
            {
                displayName: "Microsoft",
                roles: {
                    "company": true
                }
            },
            {
                displayName: "Power BI",
                roles: {
                    "product": true
                }
            }
        ]
    }
};

DataRoleHelper.hasRoleInDataView(dataView, "product");

// returns: true
```

### <a name="hasroleinvaluecolumn"></a>hasRoleInValueColumn

이 함수는 제공된 역할이 값 열에 정의되어 있는지 확인합니다.

```typescript
function hasRoleInValueColumn(valueColumn: DataViewValueColumn, name: string): boolean;
```

예제:

```typescript
import powerbi from "powerbi-visuals-api";
import DataViewValueColumn = powerbi.DataViewValueColumn;
import { dataRoleHelper } from "powerbi-visuals-utils-dataviewutils";

// This object is actually a part of the dataView object.
let valueColumn: DataViewValueColumn = {
    source: {
        displayName: "Microsoft",
        roles: {
            "company": true
        }
    },
    values: []
};

dataRoleHelper.hasRoleInValueColumn(valueColumn, "company");

// returns: true
```

## <a name="dataviewobjects"></a>DataViewObjects

`DataViewObjects`는 개체의 값을 추출하는 함수를 제공합니다.

이 모듈은 다음과 같은 함수를 제공합니다.

### <a name="getvalue"></a>getValue

이 함수는 주어진 개체의 값을 반환합니다.

```typescript
function getValue<T>(objects: DataViewObjects, propertyId: DataViewObjectPropertyIdentifier, defaultValue?: T): T;
```

예제:

```typescript
import powerbi from "powerbi-visuals-api";
import DataViewObjectPropertyIdentifier = powerbi.DataViewObjectPropertyIdentifier;
import { dataViewObjects } from "powerbi-visuals-utils-dataviewutils";

let property: DataViewObjectPropertyIdentifier = {
    objectName: "microsoft",
    propertyName: "bi"
};

// This object is actually a part of the dataView object.
let objects: powerbi.DataViewObjects = {
    "microsoft": {
        "windows": 5,
        "bi": "Power"
    }
};

dataViewObjects.getValue(objects, property);

// returns: Power
```

### <a name="getobject"></a>getObject

이 함수는 주어진 개체의 개체를 반환합니다.

```typescript
function getObject(objects: DataViewObjects, objectName: string, defaultValue?: IDataViewObject): IDataViewObject;
```

예제:

```typescript
import { dataViewObjects } from "powerbi-visuals-utils-dataviewutils";

// This object is actually a part of the dataView object.
let objects: powerbi.DataViewObjects = {
    "microsoft": {
        "windows": 5,
        "bi": "Power"
    }
};

dataViewObjects.getObject(objects, "microsoft");

/* returns: {
    "bi": "Power",
    "windows": 5

}*/
```

### <a name="getfillcolor"></a>getFillColor

이 함수는 개체의 단색을 반환합니다.

```typescript
function getFillColor(objects: DataViewObjects, propertyId: DataViewObjectPropertyIdentifier, defaultColor?: string): string;
```

예제:

```typescript
import powerbi from "powerbi-visuals-api";
import DataViewObjectPropertyIdentifier = powerbi.DataViewObjectPropertyIdentifier;
import { dataViewObjects } from "powerbi-visuals-utils-dataviewutils";

let property: DataViewObjectPropertyIdentifier = {
    objectName: "power",
    propertyName: "fillColor"
};

// This object is actually part of the dataView object.
let objects: powerbi.DataViewObjects = {
    "power": {
        "fillColor": {
            "solid": {
                "color": "yellow"
            }
        },
        "bi": "Power"
    }
};

dataViewObjects.getFillColor(objects, property);

// returns: yellow
```

### <a name="getcommonvalue"></a>getCommonValue

이 함수는 주어진 개체의 색이나 값을 검색하는 범용 함수입니다.

```typescript
function getCommonValue(objects: DataViewObjects, propertyId: DataViewObjectPropertyIdentifier, defaultValue?: any): any;
```

예제:

```typescript
import powerbi from "powerbi-visuals-api";
import DataViewObjectPropertyIdentifier = powerbi.DataViewObjectPropertyIdentifier;
import { dataViewObjects } from "powerbi-visuals-utils-dataviewutils";

let colorProperty: DataViewObjectPropertyIdentifier = {
    objectName: "power",
    propertyName: "fillColor"
};

let biProperty: DataViewObjectPropertyIdentifier = {
    objectName: "power",
    propertyName: "bi"
};

// This object is actually part of the dataView object.
let objects: powerbi.DataViewObjects = {
    "power": {
        "fillColor": {
            "solid": {
                "color": "yellow"
            }
        },
        "bi": "Power"
    }
};

dataViewObjects.getCommonValue(objects, colorProperty); // returns: yellow
dataViewObjects.getCommonValue(objects, biProperty); // returns: Power
```

## <a name="dataviewobject"></a>DataViewObject

`DataViewObject`는 개체의 값을 추출하는 함수를 제공합니다.

이 모듈은 다음과 같은 함수를 제공합니다.

### <a name="getvalue"></a>getValue

이 함수는 개체의 값을 속성 이름으로 반환합니다.

```typescript
function getValue<T>(object: IDataViewObject, propertyName: string, defaultValue?: T): T;
```

예제:

```typescript
import { dataViewObject } from "powerbi-visuals-utils-dataviewutils";

// This object is actually a part of the dataView object.
let object: powerbi.DataViewObject = {
    "windows": 5,
    "microsoft": "Power BI"
};

dataViewObject.getValue(object, "microsoft");

// returns: Power BI
```

### <a name="getfillcolorbypropertyname"></a>getFillColorByPropertyName

이 함수는 개체의 단색을 속성 이름으로 반환합니다.

```typescript
function getFillColorByPropertyName(object: IDataViewObject, propertyName: string, defaultColor?: string): string;
```

예제:

```typescript
import { dataViewObject } from "powerbi-visuals-utils-dataviewutils";

// This object is actually a part of the dataView object.
let object: powerbi.DataViewObject = {
    "windows": 5,
    "fillColor": {
        "solid": {
            "color": "green"
        }
    }
};

dataViewObject.getFillColorByPropertyName(object, "fillColor");

// returns: green
```

### <a name="converterhelper"></a>converterHelper

`converterHelper`는 dataView의 속성을 확인하는 함수를 제공합니다.

이 모듈은 다음과 같은 함수를 제공합니다.

### <a name="categoryisalsoseriesrole"></a>categoryIsAlsoSeriesRole

이 함수는 범주가 계열이기도 한지 확인합니다.

```typescript
function categoryIsAlsoSeriesRole(dataView: DataViewCategorical, seriesRoleName: string, categoryRoleName: string): boolean;
```

예제:

```typescript
import powerbi from "powerbi-visuals-api";
import DataViewCategorical = powerbi.DataViewCategorical;
import { converterHelper } from "powerbi-visuals-utils-dataviewutils";
// ...


// This object is actually part of the dataView object.
let categorical: DataViewCategorical = {
    categories: [{
        source: {
            displayName: "Microsoft",
            roles: {
                "power": true,
                "bi": true
            }
        },
        values: []
    }]
};

converterHelper.categoryIsAlsoSeriesRole(categorical, "power", "bi");

// returns: true
```

### <a name="getseriesname"></a>getSeriesName

이 함수는 계열의 이름을 반환합니다.

```typescript
function getSeriesName(source: DataViewMetadataColumn): PrimitiveValue;
```

예제:

```typescript
import powerbi from "powerbi-visuals-api";
import DataViewMetadataColumn = powerbi.DataViewMetadataColumn;
import { converterHelper } from "powerbi-visuals-utils-dataviewutils";

// This object is actually a part of the dataView object.
let metadata: DataViewMetadataColumn = {
    displayName: "Microsoft",
    roles: {
        "power": true,
        "bi": true
    },
    groupName: "Power BI"
};

converterHelper.getSeriesName(metadata);

// returns: Power BI
```

### <a name="isimageurlcolumn"></a>isImageUrlColumn

이 함수는 열에 이미지 URL이 포함되어 있는지 확인합니다.

```typescript
function isImageUrlColumn(column: DataViewMetadataColumn): boolean;
```

예제:

```typescript
import powerbi from "powerbi-visuals-api";
import DataViewMetadataColumn = powerbi.DataViewMetadataColumn;
import { converterHelper } from "powerbi-visuals-utils-dataviewutils";

// This object is actually a part of the dataView object.
let metadata: DataViewMetadataColumn = {
    displayName: "Microsoft",
    type: {
        misc: {
            imageUrl: true
        }
    }
};

converterHelper.isImageUrlColumn(metadata);

// returns: true
```

### <a name="isweburlcolumn"></a>isWebUrlColumn

이 함수는 열에 웹 URL이 포함되어 있는지 확인합니다.

```typescript
function isWebUrlColumn(column: DataViewMetadataColumn): boolean;
```

예제:

```typescript
import powerbi from "powerbi-visuals-api";
import DataViewMetadataColumn = powerbi.DataViewMetadataColumn;
import { converterHelper } from "powerbi-visuals-utils-dataviewutils";

// This object is actually a part of the dataView object.
let metadata: DataViewMetadataColumn = {
    displayName: "Microsoft",
    type: {
        misc: {
            webUrl: true
        }
    }
};

converterHelper.isWebUrlColumn(metadata);

// returns: true
```

### <a name="hasimageurlcolumn"></a>hasImageUrlColumn

이 함수는 dataView에 이미지 URL이 포함된 열이 있는지 확인합니다.

```typescript
function hasImageUrlColumn(dataView: DataView): boolean;
```

예제:

```typescript
import DataView = powerbi.DataView;
import converterHelper = powerbi.extensibility.utils.dataview.converterHelper;

// This object is actually part of the dataView object.
let dataView: DataView = {
    metadata: {
        columns: [
            {
                displayName: "Microsoft"
            },
            {
                displayName: "Power BI",
                type: {
                    misc: {
                        imageUrl: true
                    }
                }
            }
        ]
    }
};

converterHelper.hasImageUrlColumn(dataView);

// returns: true
```

## <a name="dataviewobjectsparser"></a>DataViewObjectsParser

`DataViewObjectsParser`는 서식 창의 속성을 구문 분석하는 가장 간단한 방법을 제공합니다.

이 클래스는 다음과 같은 메서드를 제공합니다.

### <a name="getdefault"></a>getDefault

이 정적 메서드는 DataViewObjectsParser의 인스턴스를 반환합니다.

```typescript
static getDefault(): DataViewObjectsParser;
```

예제:

```typescript
import { dataViewObjectsParser } from "powerbi-visuals-utils-dataviewutils";
// ...

dataViewObjectsParser.getDefault();

// returns: an instance of the DataViewObjectsParser
```

### <a name="parse"></a>parse

이 메서드는 서식 창의 속성을 구문 분석하고 `DataViewObjectsParser`의 인스턴스를 반환합니다.

```typescript
static parse<T extends DataViewObjectsParser>(dataView: DataView): T;
```

예제:

```typescript
import powerbi from "powerbi-visuals-api";
import IVisual = powerbi.extensibility.IVisual;
import VisualUpdateOptions = powerbi.extensibility.visual.VisualUpdateOptions;
import { dataViewObjectsParser } from "powerbi-visuals-utils-dataviewutils";

/**
 * This class describes formatting panel properties.
 * Name of the property should match its name described in the capabilities.
 */
class DataPointProperties {
    public fillColor: string = "red"; // This value is a default value of the property.
}

class PropertiesParser extends dataViewObjectsParser.DataViewObjectsParser {
    /**
     * This property describes a group of properties.
     */
    public dataPoint: DataPointProperties = new DataPointProperties();
}

export class YourVisual extends IVisual {
    // implementation of the IVisual.

    private propertiesParser: PropertiesParser;

    public update(options: VisualUpdateOptions): void {
        // Parses properties.
        this.propertiesParser = PropertiesParser.parse<PropertiesParser>(options.dataViews[0]);

        // You can use the properties after parsing
        console.log(this.propertiesParser.dataPoint.fillColor); // returns "red" as default value, it will be updated automatically after any change of the formatting panel.
    }
}
```

## <a name="enumerateobjectinstances"></a>enumerateObjectInstances

이 정적 메서드는 속성을 열거하고 `VisualObjectInstanceEnumeration`의 인스턴스를 반환합니다.

시각적 개체의 `enumerateObjectInstances` 메서드에서 실행합니다.

```typescript
static enumerateObjectInstances(dataViewObjectParser: dataViewObjectsParser.DataViewObjectsParser, options: EnumerateVisualObjectInstancesOptions): VisualObjectInstanceEnumeration;
```

예제:

```typescript
import powerbi from "powerbi-visuals-api";
import IVisual = powerbi.extensibility.IVisual;
import EnumerateVisualObjectInstancesOptions = powerbi.EnumerateVisualObjectInstancesOptions;
import VisualObjectInstanceEnumeration = powerbi.VisualObjectInstanceEnumeration;
import VisualUpdateOptions = powerbi.extensibility.visual.VisualUpdateOptions;
import { dataViewObjectsParser } from "powerbi-visuals-utils-dataviewutils";

/**
 * This class describes formatting panel properties.
 * Name of the property should match its name described in the capabilities.
 */
class DataPointProperties {
    public fillColor: string = "red";
}

class PropertiesParser extends dataViewObjectsParser.DataViewObjectsParser {
    /**
     * This property describes a group of properties.
     */
    public dataPoint: DataPointProperties = new DataPointProperties();
}

export class YourVisual extends IVisual {
    // implementation of the IVisual.

    private propertiesParser: PropertiesParser;

    public update(options: VisualUpdateOptions): void {
        // Parses properties.
        this.propertiesParser = PropertiesParser.parse<PropertiesParser>(options.dataViews[0]);
    }

    /**
     * This method will be executed only if the formatting panel is open.
     */
    public enumerateObjectInstances(options: EnumerateVisualObjectInstancesOptions): VisualObjectInstanceEnumeration {
        return PropertiesParser.enumerateObjectInstances(this.propertiesParser, options);
    }
}
```
