---
title: 더 많은 데이터 가져오기
description: Power BI 시각적 개체에 대해 큰 데이터 세트의 분할된 가져오기 사용
author: AviSander
ms.author: asander
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: bc8ff673927fd66bf44164e4e9950c279b98c6c1
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/23/2019
ms.locfileid: "68425071"
---
# <a name="fetch-more-data-from-power-bi"></a>Power BI에서 더 많은 데이터 가져오기

더 많은 데이터 로드 API는 30K 데이터 요소인 하드 한도를 넘어서 데이터를 청크로 가져옵니다. 사용 사례에 따라 청크 크기를 구성하여 성능을 향상할 수 있습니다.  

## <a name="enable-segmented-fetch-of-large-datasets"></a>큰 데이터 세트의 분할된 가져오기 사용

`dataview` 세그먼트 모드에 필요한 dataViewMapping에 대해 시각적 개체의 `capabilities.json`에서 “window” dataReductionAlgorithm을 정의합니다.
`count`는 창 크기를 결정하고, 이 크기에 따라 각 업데이트의 `dataview`에 추가되는 새 데이터 행 수가 제한됩니다.

capabilities.json에서 추가할 내용

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

## <a name="usage-in-the-custom-visual"></a>사용자 지정 시각적 개체에서의 사용

표시 데이터가 있는지 여부는 `dataView.metadata.segment`의 존재를 검사하여 확인할 수 있습니다.

```typescript
    public update(options: VisualUpdateOptions) {
        const dataView = options.dataViews[0];
        console.log(dataView.metadata.segment);
        // output: __proto__: Object
    }
```

`options.operationKind`를 검사하여 첫 번째 업데이트인지, 후속 업데이트인지 확인할 수도 있습니다.

`VisualDataChangeOperationKind.Create`는 첫 번째 세그먼트를 의미하고, `VisualDataChangeOperationKind.Append`는 후속 세그먼트를 의미합니다.

샘플 구현은 아래 코드 조각을 참조하세요.

```typescript
// CV update implementation
public update(options: VisualUpdateOptions) {
    // indicates this is the first segment of new data.
    if (options.operationKind == VisualDataChangeOperationKind.Create) {

    }

    // on second or subesquent segments:
    if (options.operationKind == VisualDataChangeOperationKind.Append) {

    }

    // complete update implementation
}
```

UI 이벤트 처리기에서 `fetchMoreData` 메서드를 호출할 수도 있습니다.

```typescript
btn_click(){
{
    // check if more data is expected for the current dataview
    if (dataView.metadata.segment) {
        //request for more data if available, as resopnce Power BI will call update method
        let request_accepted: bool = this.host.fetchMoreData();
        // handle rejection
        if (!request_accepted) {
            // for example when the 100 MB limit has been reached
        }
    }
}
```

Power BI는 새 데이터 세그먼트를 `this.host.fetchMoreData` 메서드에 대한 응답으로 사용하여 시각적 개체의 `update` 메서드를 호출합니다.

> [!NOTE]
> Power BI는 현재, 클라이언트 메모리 제약 조건을 방지하기 위해 가져온 총 데이터를 **100MB**로 제한합니다. fetchMoreData()가 ‘false’를 반환하면 이 한도에 도달한 것을 알 수 있습니다.*
