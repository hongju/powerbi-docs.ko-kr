---
title: Power BI에서 더 많은 데이터 가져오기
description: 이 문서에서는 Power BI 시각적 개체에 대해 큰 데이터 세트의 분할된 가져오기를 사용하도록 설정하는 방법을 설명합니다.
author: AviSander
ms.author: asander
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 7e5ecc0e317a21d10e76e9413926822ac4d6760b
ms.sourcegitcommit: b602cdffa80653bc24123726d1d7f1afbd93d77c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70237149"
---
# <a name="fetch-more-data-from-power-bi"></a>Power BI에서 더 많은 데이터 가져오기

이 문서에서는 30KB 데이터 요소의 하드 한도를 무시하기 위해 더 많은 데이터를 로드하는 방법을 설명합니다. 이 방법은 데이터를 청크로 제공합니다. 성능을 향상하기 위해 사용 사례에 맞게 청크 크기를 구성할 수 있습니다.  

## <a name="enable-a-segmented-fetch-of-large-datasets"></a>큰 데이터 세트의 분할된 가져오기 사용

`dataview` 세그먼트 모드의 경우, 필요한 dataViewMapping에 대한 시각적 개체의 *capabilities.json* 파일에서 dataReductionAlgorithm의 창 크기를 정의합니다. `count`는 창 크기를 결정하고, 이 크기에 따라 각 업데이트에서 `dataview`에 추가될 수 있는 새 데이터 행 수가 제한됩니다.

다음 코드를 *capabilities.json* 파일에 추가합니다.

```typescript
"dataViewMappings": [
    {
        "table": {
            "rows": {
                "for": {
                    "in": "values"
                },
                "dataReductionAlgorithm": {
                    "window": {
                        "count": 100
                    }
                }
            }
    }
]
```

새 세그먼트가 기존 `dataview`에 추가되고, 시각적 개체에 `update` 호출로 제공됩니다.

## <a name="usage-in-the-power-bi-visual"></a>Power BI 시각적 개체에서 사용

`dataView.metadata.segment`가 있는지 검사하여 데이터가 있는지 여부를 확인할 수 있습니다.

```typescript
    public update(options: VisualUpdateOptions) {
        const dataView = options.dataViews[0];
        console.log(dataView.metadata.segment);
        // output: __proto__: Object
    }
```

`options.operationKind`를 검사하여 첫 번째 업데이트인지, 후속 업데이트 인지 확인할 수도 있습니다. 다음 코드에서 `VisualDataChangeOperationKind.Create`는 첫 번째 세그먼트를 나타내고, `VisualDataChangeOperationKind.Append`는 후속 세그먼트를 나타냅니다.

샘플 구현은 다음 코드 조각을 참조하세요.

```typescript
// CV update implementation
public update(options: VisualUpdateOptions) {
    // indicates this is the first segment of new data.
    if (options.operationKind == VisualDataChangeOperationKind.Create) {

    }

    // on second or subsequent segments:
    if (options.operationKind == VisualDataChangeOperationKind.Append) {

    }

    // complete update implementation
}
```

다음과 같이 UI 이벤트 처리기에서 `fetchMoreData` 메서드를 호출할 수도 있습니다.

```typescript
btn_click(){
{
    // check if more data is expected for the current data view
    if (dataView.metadata.segment) {
        //request for more data if available; as a response, Power BI will call update method
        let request_accepted: bool = this.host.fetchMoreData();
        // handle rejection
        if (!request_accepted) {
            // for example, when the 100 MB limit has been reached
        }
    }
}
```

`this.host.fetchMoreData` 메서드 호출에 대한 응답으로, Power BI는 새 데이터 세그먼트를 사용하여 시각적 개체의 `update` 메서드를 호출합니다.

> [!NOTE]
> 클라이언트 메모리 제약 조건을 방지하기 위해, Power BI는 현재 가져온 데이터 합계를 100MB로 제한합니다. FetchMoreData()가 `false`를 반환하면 한도에 도달한 것을 알 수 있습니다.
