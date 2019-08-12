---
title: 책갈피
description: Power BI 시각적 개체는 책갈피 전환을 처리할 수 있습니다.
author: zBritva
ms.author: v-ilgali
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 90e3fc73cd49a5c84a5c2acc68a8cf5e0e4aa42b
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/23/2019
ms.locfileid: "68425508"
---
# <a name="add-bookmarks-support-for-power-bi-visuals"></a>Power BI 시각적 개체에 대해 책갈피 지원 추가

Power BI 보고서 책갈피를 사용하면 구성된 보고서 페이지 뷰, 시각적 개체의 선택 상태 및 필터링 상태를 캡처할 수 있습니다. 그러나 책갈피를 지원하고 변경 내용에 올바르게 대응하려면 사용자 지정 시각적 개체 쪽의 추가 작업이 필요합니다.

[설명서](https://docs.microsoft.com/power-bi/desktop-bookmarks)에서 책갈피에 대해 자세히 알아보세요.

## <a name="report-bookmarks-support-in-your-visual"></a>시각적 개체의 보고서 책갈피 지원

시각적 개체가 다른 시각적 개체와 상호 작용하거나, 데이터 요소를 선택하거나, 다른 시각적 개체를 필터링하는 경우 속성에서 상태를 복원해야 합니다.

## <a name="how-to-add-report-bookmarks-support"></a>보고서 책갈피 지원을 추가하는 방법

1. 필수 유틸리티 `powerbi-visuals-utils-interactivityutils`(https://github.com/Microsoft/PowerBI-visuals-utils-interactivityutils/) 버전 3.0.0 이상을 설치(또는 업데이트)합니다. 상태 선택 또는 필터를 사용하여 조작할 추가 클래스를 포함합니다. 이 클래스는 필터 시각적 개체 및 `InteractivityService`를 사용하는 모든 시각적 개체에 필요합니다.

2. 시각적 개체 API를 1.11.0으로 업데이트하여 `SelectionManager` 인스턴스에서 `registerOnSelectCallback`을 사용합니다. 이 작업은 `InteractivityService`가 아닌 일반 `SelectionManager`를 사용하는 비필터 시각적 개체에 필요합니다.

### <a name="how-custom-visuals-interact-with-power-bi-in-the-report-bookmarks-scenario"></a>보고서 책갈피 시나리오에서 사용자 지정 시각적 개체가 Power BI와 상호 작용하는 방법

다음 예제를 살펴보겠습니다. 사용자가 각 책갈피에서 다른 선택 상태를 사용하여 보고서 페이지에 여러 개의 책갈피를 만듭니다.

먼저 사용자가 시각적 개체의 데이터 요소를 선택합니다. 시각적 개체는 선택 항목을 호스트에 전달하여 Power BI 및 다른 시각적 개체와 상호 작용합니다. 사용자가 `Bookmark panel`에서 “추가”를 선택하면 Power BI는 현재 선택 항목을 새 책갈피에 대해 저장합니다.

이 작업은 사용자가 선택 항목을 변경하고 새 책갈피를 추가할 때마다 반복해서 수행됩니다.
사용자는 책갈피를 만든 후에 책갈피 간에 전환할 수 있습니다.

사용자가 책갈피를 선택하면 Power BI는 저장된 필터 또는 선택 상태를 복원하고 시각적 개체에 전달합니다. 다른 시각적 개체는 책갈피에 저장된 상태에 따라 강조 표시되거나 필터링됩니다. Power BI 호스트가 작업을 수행합니다. 시각적 개체는 새 선택 상태를 올바르게 반영해야 합니다(예: 렌더링된 데이터 요소의 색 변경).

새 선택 상태는 `update` 메서드를 통해 시각적 개체에 전달됩니다. `options` 인수에는 특수 속성인 `options.jsonFilters`가 포함됩니다. JSONFilter 속성은 `Advanced Filter` 및 `Tuple Filter`를 포함할 수 있습니다.

시각적 개체는 필터 값을 복원하여 선택한 책갈피에 해당하는 시각적 개체의 상태를 표시해야 합니다.

또는 시각적 개체가 선택 항목만 사용하는 경우 ISelectionManager의 특수 콜백 함수 호출 등록된 `registerOnSelectCallback` 메서드를 사용합니다.

### <a name="visuals-with-selections"></a>선택 항목을 사용하는 시각적 개체

시각적 개체가 [선택 항목](https://github.com/Microsoft/PowerBI-visuals/blob/master/Tutorial/Selection.md)을 사용하여 다른 시각적 개체와 상호 작용하는 경우 책갈피를 추가하는 방법에는 두 가지가 있습니다.

* 시각적 개체에서 이전에 **[`InteractivityService`](https://github.com/Microsoft/powerbi-visuals-utils-interactivityutils/blob/master/docs/api/interactivityService.md)를 사용하지 않은 경우** `FilterManager.restoreSelectionIds` 메서드를 사용할 수 있습니다.

* 시각적 개체에서 이미 **[`InteractivityService`](https://github.com/Microsoft/powerbi-visuals-utils-interactivityutils/blob/master/docs/api/interactivityService.md)** 를 사용하여 선택 항목을 관리하는 경우 `InteractivityService` 인스턴스에서 `applySelectionFromFilter` 메서드를 사용해야 합니다.

#### <a name="using-iselectionmanagerregisteronselectcallback"></a>`ISelectionManager.registerOnSelectCallback` 사용

사용자가 책갈피를 클릭하면 Power BI는 해당 선택 항목을 사용하여 시각적 개체의 `callback` 메서드를 호출합니다. 

```typescript
this.selectionManager.registerOnSelectCallback(
    (ids: ISelectionId[]) => {
        //called when a selection was set by Power BI
    });
);
```

[`'visualTransform'`](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/master/src/barChart.ts#L74) 메서드에서 만든 시각적 개체에 데이터 요소가 있다고 가정해 보겠습니다.

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

따라서 데이터 요소로 `visualDataPoints`가 있고 `ids` 배열이 `callback` 함수에 전달되었습니다.

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

데이터 요소를 업데이트하면 시각적 개체는 `filter` 개체에 저장된 현재 선택 상태를 반영합니다. 그런 다음, 데이터 요소가 렌더링될 때 사용자 지정 시각적 개체의 선택 상태가 책갈피의 상태와 일치하게 됩니다.

### <a name="using-interactivityservice-for-control-selections-in-the-visual"></a>시각적 개체에서 컨트롤 선택에 `InteractivityService` 사용

시각적 개체가 `InteractivityService`를 사용하는 경우 시각적 개체에서 책갈피를 지원하기 위한 추가 작업이 필요하지 않습니다.

사용자가 책갈피를 선택하면 유틸리티에서 시각적 개체의 선택 상태를 처리합니다.

### <a name="visuals-with-filter"></a>필터를 사용하는 시각적 개체

시각적 개체가 날짜 범위별 데이터 필터를 만든다고 가정해 보겠습니다. 따라서 범위의 시작과 끝으로 `startDate` 및 `endDate`가 있습니다.
시각적 개체는 고급 필터를 만들고 호스트 메서드 `applyJsonFilter`를 호출하여 관련 조건에 따라 데이터를 필터링합니다.
`target`은 필터링할 테이블입니다.

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

사용자가 책갈피를 클릭할 때마다 사용자 지정 시각적 개체는 `update` 호출을 가져옵니다.

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

그런 다음, 시각적 개체는 데이터 요소 및 시각화 개체(선, 사각형 등)와 같은 내부 상태를 현재 조건에 따라 변경해야 합니다.

> [!IMPORTANT]
> 보고서 책갈피 시나리오에서는 시각적 개체가 다른 시각적 개체를 필터링하기 위해 `applyJsonFilter`를 호출하면 안 됩니다. Power BI에서 이미 필터링됩니다.

Timeline Slicer 시각적 개체는 데이터 범위에 일치하도록 범위 선택기를 변경합니다.

자세한 내용은 [Timeline Slicer 리포지토리](https://github.com/Microsoft/powerbi-visuals-timeline/commit/606f1152f59f82b5b5a367ff3b117372d129e597?diff=unified#diff-b6ef9a9ac3a3225f8bd0de84bee0a0df)를 참조하세요.

### <a name="filter-state-to-save-visual-properties-in-bookmarks"></a>책갈피에 시각적 개체 속성을 저장하는 필터 상태

`filterState` 속성은 일부 필터링의 속성을 만듭니다. 시각적 개체는 책갈피에 여러 개의 값을 저장할 수 있습니다.

속성 값을 필터 상태로 저장하려면 `capabilities.json`에서 개체 속성을 `"filterState": true`로 표시해야 합니다.

예를 들어 `Timeline Slicer`는 `Granularity` 속성 값을 필터에 저장합니다. 또한 사용자가 책갈피를 변경할 때 현재 세분성을 변경할 수 있도록 허용합니다.

자세한 내용은 [Timeline Slicer 리포지토리](https://github.com/microsoft/powerbi-visuals-timeline/commit/8b7d82dd23cd2bd71817f1bc5d1e1732347a185e#diff-290828b604cfa62f1cb310f2e90c52fdR334)를 참조하세요.
