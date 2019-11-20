---
title: Power BI 시각적 개체에 대해 책갈피 지원 추가
description: Power BI 시각적 개체는 책갈피 전환을 처리할 수 있습니다.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: aed8317c36cdd118b03bff2db93788f493ac9ad2
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2019
ms.locfileid: "73880259"
---
# <a name="add-bookmark-support-for-power-bi-visuals"></a>Power BI 시각적 개체에 대해 책갈피 지원 추가

Power BI 보고서 책갈피를 사용하면 구성된 보고서 페이지 뷰, 시각적 개체의 선택 상태 및 필터링 상태를 캡처할 수 있습니다. 그러나 책갈피를 지원하고 변경 내용에 올바르게 대응하려면 Power BI 시각적 개체 쪽의 추가 작업이 필요합니다.

책갈피에 대한 자세한 내용은 [책갈피를 사용하여 Power BI에서 정보 공유 및 스토리 빌드](https://docs.microsoft.com/power-bi/desktop-bookmarks)를 참조하세요.

## <a name="report-bookmarks-support-in-your-visual"></a>시각적 개체의 보고서 책갈피 지원

시각적 개체가 다른 시각적 개체와 상호 작용하거나, 데이터 요소를 선택하거나, 다른 시각적 개체를 필터링하는 경우 속성에서 상태를 복원해야 합니다.

## <a name="add-report-bookmarks-support"></a>보고서 책갈피 지원 추가

1. 필수 유틸리티인 [powerbi-visuals-utils-interactivityutils](https://github.com/Microsoft/PowerBI-visuals-utils-interactivityutils/) 버전 3.0.0 이상을 설치(또는 업데이트)합니다. 상태 선택 또는 필터를 조작하기 위한 추가 클래스를 포함합니다. 이 클래스는 필터 시각적 개체 및 `InteractivityService`를 사용하는 모든 시각적 개체에 필요합니다.

2. `SelectionManager` 인스턴스에서 `registerOnSelectCallback`을 사용하려면 시각적 개체 API를 버전 1.11.0으로 업데이트합니다. 이 작업은 `InteractivityService`가 아닌 일반 `SelectionManager`를 사용하는 필터 이외의 시각적 개체에 필요합니다.

### <a name="how-power-bi-visuals-interact-with-power-bi-in-report-bookmarks"></a>보고서 책갈피에서 Power BI 시각적 개체가 Power BI와 상호 작용하는 방법

다음 시나리오를 살펴봅시다. 각 책갈피에서 다른 선택 상태를 사용하여 보고서 페이지에 여러 개의 책갈피를 만들려고 합니다.

먼저 시각적 개체에서 데이터 요소를 선택합니다. 시각적 개체는 선택 항목을 호스트에 전달하여 Power BI 및 다른 시각적 개체와 상호 작용합니다. **책갈피** 창에서 **추가**를 선택하면, Power BI는 현재 선택을 새 책갈피에 저장합니다.

선택을 변경하고 새 책갈피를 추가할 때마다 이 작업이 반복해서 수행됩니다. 책갈피를 만든 후에 책갈피 간에 전환할 수 있습니다.

책갈피를 선택하면, Power BI는 저장된 필터 또는 선택 상태를 복원하고 시각적 개체에 전달합니다. 다른 시각적 개체는 책갈피에 저장된 상태에 따라 강조 표시되거나 필터링됩니다. Power BI 호스트가 작업을 수행합니다. 시각적 개체는 새 선택 상태를 올바르게 반영해야 합니다(예: 렌더링된 데이터 요소의 색 변경).

새 선택 상태는 `update` 메서드를 통해 시각적 개체에 전달됩니다. `options` 인수에는 특수 속성인 `options.jsonFilters`가 포함되어 있습니다. 해당 JSONFilter 속성에는 `Advanced Filter` 및 `Tuple Filter`가 포함될 수 있습니다.

시각적 개체는 필터 값을 복원하여 선택한 책갈피에 해당하는 시각적 개체 상태를 표시해야 합니다. 또는 시각적 개체가 선택 항목만 사용하는 경우, ISelectionManager의 `registerOnSelectCallback` 메서드로 등록된 특수 콜백 함수 호출을 사용할 수 있습니다.

### <a name="visuals-with-selection"></a>선택 항목을 사용하는 시각적 개체

[선택 항목](https://github.com/Microsoft/PowerBI-visuals/blob/master/Tutorial/Selection.md)을 사용하여 시각적 개체가 다른 시각적 개체와 상호 작용하는 경우, 다음 두 가지 방법 중 하나로 책갈피를 추가할 수 있습니다.

* 시각적 개체가 [InteractivityService](https://github.com/Microsoft/powerbi-visuals-utils-interactivityutils/blob/master/docs/api/interactivityService.md)를 아직 사용하지 않은 경우, `FilterManager.restoreSelectionIds` 메서드를 사용할 수 있습니다.

* 시각적 개체가 이미 [InteractivityService](https://github.com/Microsoft/powerbi-visuals-utils-interactivityutils/blob/master/docs/api/interactivityService.md)를 사용하여 선택 항목을 관리하는 경우에는 `InteractivityService` 인스턴스에서 `applySelectionFromFilter` 메서드를 사용해야 합니다.

#### <a name="use-iselectionmanagerregisteronselectcallback"></a>ISelectionManager.registerOnSelectCallback 사용

책갈피를 선택하면, Power BI는 해당 선택 항목을 사용하여 시각적 개체의 `callback` 메서드를 호출합니다. 

```typescript
this.selectionManager.registerOnSelectCallback(
    (ids: ISelectionId[]) => {
        //called when a selection was set by Power BI
    });
);
```

[visualTransform](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/master/src/barChart.ts#L74) 메서드에서 만든 시각적 개체에 데이터 요소가 있다고 가정해 봅시다.

`datapoints`는 다음과 같습니다.

```typescript
visualDataPoints.push({
    category: categorical.categories[0].values[i],
    color: getCategoricalObjectValue<Fill>(categorical.categories[0], i, 'colorSelector', 'fill', defaultColor).solid.color,
    selectionId: host.createSelectionIdBuilder()
        .withCategory(categorical.categories[0], i)
        .createSelectionId(),
    selected: false
});
```

이제 데이터 요소로 `visualDataPoints`가 있고, `ids` 배열이 `callback` 함수에 전달되었습니다.

이 시점에서 시각적 개체는 `ISelectionId[]` 배열을 `visualDataPoints` 배열의 선택 항목과 비교하고 해당하는 데이터 요소를 선택된 것으로 표시해야 합니다.

```typescript
this.selectionManager.registerOnSelectCallback(
    (ids: ISelectionId[]) => {
        visualDataPoints.forEach(dataPoint => {
            ids.forEach(bookmarkSelection => {
                if (bookmarkSelection.equals(dataPoint.selectionId)) {
                    dataPoint.selected = true;
                }
            });
        });
    });
);
```

데이터 요소를 업데이트하면 `filter` 개체에 저장된 현재 선택 상태가 반영됩니다. 그런 다음, 데이터 요소가 렌더링될 때 사용자 지정 시각적 개체의 선택 상태가 책갈피 상태와 일치하게 됩니다.

### <a name="use-interactivityservice-for-control-selections-in-the-visual"></a>시각적 개체에서 컨트롤 선택에 InteractivityService 사용

시각적 개체가 `InteractivityService`를 사용하는 경우, 시각적 개체에서 책갈피를 지원하기 위한 추가 작업이 필요하지 않습니다.

책갈피를 선택하면, 유틸리티가 시각적 개체의 선택 상태를 처리합니다.

### <a name="visuals-with-a-filter"></a>필터를 사용하는 시각적 개체

시각적 개체가 날짜 범위별 데이터 필터를 만든다고 가정해 보겠습니다. 범위의 시작 날짜와 종료 날짜로 `startDate` 및 `endDate`가 있습니다.

시각적 개체는 고급 필터를 만들고 호스트 메서드 `applyJsonFilter`를 호출하여 관련 조건에 따라 데이터를 필터링합니다.

대상은 필터링에 사용되는 테이블입니다.

```typescript
import { AdvancedFilter } from "powerbi-models";

const filter: IAdvancedFilter = new AdvancedFilter(
    target,
    "And",
    {
        operator: "GreaterThanOrEqual",
        value: startDate
            ? startDate.toJSON()
            : null
    },
    {
        operator: "LessThanOrEqual",
        value: endDate
            ? endDate.toJSON()
            : null
    });

this.host.applyJsonFilter(
    filter,
    "general",
    "filter",
    (startDate && endDate)
        ? FilterAction.merge
        : FilterAction.remove
);
```

책갈피를 선택할 때마다 사용자 지정 시각적 개체는 `update` 호출을 가져옵니다.

사용자 지정 시각적 개체는 개체의 필터를 확인해야 합니다.

```typescript
const filter: IAdvancedFilter = FilterManager.restoreFilter(
    && options.jsonFilters
    && options.jsonFilters[0] as any
) as IAdvancedFilter;
```

`filter` 개체가 null이 아니면 시각적 개체는 개체에서 필터 조건을 복원해야 합니다.

```typescript
const jsonFilters: AdvancedFilter = this.options.jsonFilters as AdvancedFilter[];

if (jsonFilters
    && jsonFilters[0]
    && jsonFilters[0].conditions
    && jsonFilters[0].conditions[0]
    && jsonFilters[0].conditions[1]
) {
    const startDate: Date = new Date(`${jsonFilters[0].conditions[0].value}`);
    const endDate: Date = new Date(`${jsonFilters[0].conditions[1].value}`);

    // apply restored conditions
} else {
    // apply default settings
}
```

그런 다음, 시각적 개체는 내부 상태를 현재 조건에 따라 변경해야 합니다. 내부 상태에는 데이터 요소 및 시각화 개체(선, 사각형 등)가 포함됩니다.

> [!IMPORTANT]
> 보고서 책갈피 시나리오에서는 시각적 개체가 다른 시각적 개체를 필터링하기 위해 `applyJsonFilter`를 호출하면 안 됩니다. Power BI에서 이미 필터링됩니다.

Timeline Slicer 시각적 개체가 범위 선택기를 해당 데이터 범위로 변경합니다.

자세한 내용은 [Timeline Slicer 리포지토리](https://github.com/Microsoft/powerbi-visuals-timeline/commit/606f1152f59f82b5b5a367ff3b117372d129e597?diff=unified#diff-b6ef9a9ac3a3225f8bd0de84bee0a0df)를 참조하세요.

### <a name="filter-the-state-to-save-visual-properties-in-bookmarks"></a>책갈피에 시각적 개체 속성을 저장하는 필터 상태

`filterState` 속성은 일부 필터링의 속성을 만듭니다. 시각적 개체는 책갈피에 다양한 값을 저장할 수 있습니다.

속성 값을 필터 상태로 저장하려면 *capabilities.json*에서 개체 속성을 `"filterState": true`로 표시합니다.

예를 들어 Timeline Slicer는 `Granularity` 속성 값을 필터에 저장합니다. 이렇게 하면 책갈피를 변경할 때 현재 세분성이 변경됩니다.

자세한 내용은 [Timeline Slicer 리포지토리](https://github.com/microsoft/powerbi-visuals-timeline/commit/8b7d82dd23cd2bd71817f1bc5d1e1732347a185e#diff-290828b604cfa62f1cb310f2e90c52fdR334)를 참조하세요.
