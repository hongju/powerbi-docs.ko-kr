---
title: Power BI 시각적 개체 개념
description: 이 문서에서는 시각적 개체와 Power BI의 통합 방법에 대해 설명합니다.
author: zBritva
ms.author: v-ilgali
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 36742917829013a6efca9d74f88b01bc686437a8
ms.sourcegitcommit: f77b24a8a588605f005c9bb1fdad864955885718
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2019
ms.locfileid: "74700849"
---
# <a name="power-bi-visual-concept"></a>Power BI 시각적 개체 개념

이 문서에서는 사용자 및 시각적 개체가 Power BI와 상호 작용하는 방법과 사용자가 Power BI 시각적 개체와 상호 작용하는 방법을 설명합니다. 다이어그램에서는 시각적 개체에 직접 영향을 주거나 Power BI를 통해 영향을 주는 작업(예: 사용자가 책갈피 선택)이 표시됩니다.

![Power BI 시각적 개체](./media/visual-concept.svg)

## <a name="the-visual-gets-update-from-power-bi"></a>시각적 개체가 Power BI에서 업데이트를 가져옵니다.

시각적 개체에는 `update` 메서드가 있고 이 메서드는 일반적으로 시각적 개체의 기본 논리를 포함하며 차트를 렌더링하거나 데이터를 시각화합니다.

업데이트 수가 많을수록 `update` 메서드가 호출됩니다.

### <a name="user-interacts-with-visual-through-power-bi"></a>사용자가 Power BI를 통해 시각적 개체와 상호 작용합니다.

* 사용자가 시각적 개체 속성 패널을 엽니다.

    Power BI는 시각적 개체 `capabilities.json`에서 지원되는 개체 및 속성을 가져오고 실제 속성 값을 수신하기 위해 Power BI에서 시각적 개체의 `enumerateObjectInstances` 메서드를 호출합니다.

    시각적 개체는 실제 속성 값을 반환해야 합니다.

    자세한 내용은 [시각적 개체 기능에 대해 자세히 참조하세요](capabilities.md).

* 서식 패널에서 [시각적 개체의 속성을 변경](../../visuals/power-bi-visualization-customize-title-background-and-legend.md)합니다.

    속성의 값을 변경한 후 Power BI는 시각적 개체의 `update` 메서드를 호출하고 새 `options`을(를) 개체의 새 값과 함께 업데이트 메서드로 전달합니다.

    자세한 내용은 [시각적 개체의 개체 및 속성에 대해 확인하세요](objects-properties.md).

* 사용자가 시각적 개체의 크기를 조정합니다.

    사용자가 시각적 개체의 크기를 변경하면 Power BI는 새 `option` 개체를 사용하여 `update` 메서드를 호출합니다. 옵션에는 시각적 개체의 새 너비와 높이가 적용된 중첩된 `viewport` 개체가 포함됩니다.

* 사용자가 보고서, 페이지 또는 시각적 수준 필터를 적용합니다.

    Power BI는 필터 조건에 따라 데이터를 필터링하고 시각적 개체의 `update` 메서드를 호출하여 시각적 개체에 새 데이터를 제공합니다.

    시각적 개체는 중첩된 개체 중 하나에 새 데이터를 포함하는 `options`의 새 업데이트를 가져옵니다. 시각적 개체의 데이터 뷰 매핑 구성에 따라 달라집니다.

    자세한 내용은 [데이터 뷰 매핑에 대해 확인하세요](dataview-mappings.md).

* 사용자가 보고서의 다른 시각적 개체에서 데이터 요소를 선택합니다.

    Power BI는 선택된 데이터 요소를 필터링하거나 강조 표시하고 시각적 개체의 `update` 메서드를 호출합니다.

    시각적 개체는 강조 표시의 배열을 사용하여 새 필터링된 데이터 또는 동일한 데이터를 가져옵니다.

    자세한 내용은 [시각적 개체에서 데이터를 강조 표시하는 방법을 참조하세요](highlight.md).

* 사용자가 보고서의 책갈피 패널에서 책갈피를 선택합니다.

    두 가지 동작이 발생할 수 있습니다.

    1. Power BI는 메서드 `registerOnSelectionCallback`에서 등록된 함수를 호출하고, 호출 함수는 해당 책갈피의 선택 영역 배열을 가져옵니다.

    2. Power BI는 `options` 내의 해당 필터 개체를 사용하여 `update` 메서드를 호출합니다.

    두 경우 모두 시각적 개체는 받은 선택 항목 또는 필터 개체에 따라 시각화 상태를 변경해야 합니다.

    책갈피에 대 한 자세한 내용은 [책갈피를 처리하는 방법을 참조하세요](filter-api.md).

    필터에 대한 자세한 내용은 [Power BI 시각적 개체가 다른 시각적 개체에서 데이터를 필터링하는 방법을 참조하세요](filter-api.md).

### <a name="user-interacts-with-visual-directly"></a>사용자가 시각적 개체와 직접 상호 작용

* 사용자가 데이터 요소를 마우스로 가리키기

    시각적 개체는 Power BI 도구 설명 API를 통해 데이터 요소에 대한 추가 정보를 표시할 수 있습니다.
    사용자가 시각적 요소를 마우스로 가리키면 시각적 개체에서 이벤트를 처리하고 도구 설명 요소에 데이터를 표시할 수 있습니다.

    시각적 개체에는 표준 도구 설명 또는 보고서 페이지 도구 설명이 표시될 수 있습니다.

    자세한 내용은 가이드 [도구 설명을 추가하는 방법](add-tooltips.md)을 참조하세요.

* 사용자가 시각적 개체 속성을 변경합니다. 예를 들어 사용자가 트리를 확장하면 시각적 개체가 상태를 속성에 저장합니다.

    시각적 개체는 Power BI API를 통해 속성 값을 저장할 수 있습니다. 예를 들어 사용자가 시각적 개체와 상호 작용하는 경우입니다. 시각적 개체는 속성 값을 저장하거나 업데이트해야 합니다. 시각적 개체는 이에 대한 `presistProperties` 메서드를 호출할 수 있습니다.

* 사용자가 URL 링크를 클릭합니다.

    기본적으로 시각적 개체는 URL을 열 수 없습니다. 새 탭에서 URL을 열려면 시각적 개체는 `launchURL` 메서드를 호출하고 URL을 매개 변수로 전달해야 합니다.

    자세한 내용은 [URL API 시작](launch-url.md)를 참조하세요.

* 사용자가 시각적 개체를 사용하여 필터를 적용합니다.

    시각적 개체는 `applyJSONFilter`를 호출하고 다른 시각적 개체의 데이터를 필터링하기 위한 필터링 조건을 전달합니다.

    시각적 개체는 여러 유형의 필터를 사용할 수 있습니다(예: 기본 필터, 고급 필터, 튜플 필터).

    필터에 대한 자세한 내용은 [Power BI 시각적 개체가 다른 시각적 개체에서 데이터를 필터링하는 방법을 참조하세요](filter-api.md).

* 사용자가 시각적 개체의 요소를 클릭/선택합니다.

    선택 항목에 대한 자세한 내용은 [시각적 개체의 상호 작용 방법을 참조하세요](selection-api.md).

### <a name="the-visual-interacts-with-power-bi"></a>시각적 개체와 Power BI가 상호 작용

* 시각적 개체는 Power BI에서 더 많은 데이터를 요청합니다.

    시각적 개체는 데이터를 파트별로 처리할 수 있습니다. FetchMoreData API 메서드는 데이터 세트의 다음 조각을 요청합니다.

    `fetchMoreData`에 대한 자세한 내용은 [Power BI에서 더 많은 데이터를 가져오는 방법을 확인하세요](fetch-more-data.md).

* 이벤트 서비스

    Power BI는 보고서를 PDF로 내보내거나 메일(인증된 시각적 개체만 지원됨)로 보낼 수 있습니다. 렌더링이 완료되고 PDF/메일을 캡처할 준비가 되었음을 Power BI에 알리려면 시각적 개체는 렌더링 이벤트 API를 호출해야 합니다.

    자세한 내용은 [Power BI의 보고서를 PDF로 내보내는 방법을 참조하세요](../../consumer/end-user-pdf.md).

    [이벤트 서비스에 대한 자세한 정보](event-service.md)를 알아봅니다.

## <a name="next-steps"></a>다음 단계

웹 개발자로서 고유한 시각화를 만들고 AppSource에 추가하는 데 관심이 있나요? [Power BI 사용자 지정 시각적 개체 개발](./custom-visual-develop-tutorial.md)을 참조하고, [AppSource에 Power BI 시각적 개체를 게시](../office-store.md)하는 방법을 알아봅니다.
