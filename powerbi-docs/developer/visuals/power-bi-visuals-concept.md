---
title: Power BI 시각적 개체 개념
description: 이 문서에서는 시각적 개체가 Power BI와 통합되는 방법과 사용자가 Power BI의 시각적 개체와 상호 작용하는 방법을 설명합니다.
author: KesemSharabi
ms.author: kesharab
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: bb0834527ba23c6cfcc155cc65cd0318b296ba84
ms.sourcegitcommit: 052df769e6ace7b9848493cde9f618d6a2ae7df9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/14/2020
ms.locfileid: "75925603"
---
# <a name="visuals-in-power-bi"></a>Power BI의 시각적 개체

이 문서에서는 시각적 개체가 Power BI와 통합되는 방법과 사용자가 Power BI의 시각적 개체와 상호 작용하는 방법을 설명합니다. 

다음 그림은 책갈피 선택과 같이 사용자가 수행하는 일반적인 시각적 개체 기반 작업이 Power BI에서 처리되는 방법을 보여 줍니다.

![Power BI 시각적 개체 작업 다이어그램](./media/visual-concept.svg)

## <a name="visuals-get-updates-from-power-bi"></a>Power BI에서 시각적 개체 업데이트 가져오기

시각적 개체는 `update` 메서드를 호출하여 Power BI에서 업데이트를 가져옵니다. `update` 메서드는 일반적으로 시각적 개체의 기본 논리를 포함하며, 차트를 렌더링하거나 데이터를 시각화합니다.

시각적 개체가 `update` 메서드를 호출하면 업데이트가 트리거됩니다.

## <a name="action-and-update-patterns"></a>작업 및 업데이트 패턴

Power BI에서의 작업 및 후속 업데이트는 다음 세 가지 패턴 중 하나로 이루어집니다.

* 사용자가 Power BI를 통해 시각적 개체와 상호 작용.
* 사용자가 시각적 개체와 직접 상호 작용.
* 시각적 개체가 Power BI와 상호 작용.

### <a name="user-interacts-with-a-visual-through-power-bi"></a>사용자가 Power BI를 통해 시각적 개체와 상호 작용

* 사용자가 시각적 개체의 속성 패널을 엽니다.

    사용자가 시각적 개체의 속성 패널을 열면 Power BI는 시각적 개체의 *capabilities.json* 파일에서 지원되는 개체와 속성을 가져옵니다. Power BI는 실제 속성 값을 받기 위해 시각적 개체의 `enumerateObjectInstances` 메서드를 호출합니다. 시각적 개체는 속성의 실제 값을 반환합니다.

    자세한 내용은 [Power BI 시각적 개체의 기능 및 속성](capabilities.md)을 참조하세요.

* 사용자가 서식 패널에서 [시각적 개체의 속성을 변경](../../visuals/power-bi-visualization-customize-title-background-and-legend.md)합니다.

    사용자가 서식 패널에서 속성의 값을 변경하면 Power BI는 시각적 개체의 `update` 메서드를 호출합니다. Power BI는 새 `options` 개체를 `update` 메서드로 전달합니다. 개체에는 새 값이 포함되어 있습니다.

    자세한 내용은 [Power BI 시각적 개체의 개체 및 속성](objects-properties.md)을 참조하세요.

* 사용자가 시각적 개체의 크기를 조정합니다.

    사용자가 시각적 개체의 크기를 변경하면 Power BI는 새 `options` 개체를 사용하여 `update` 메서드를 호출합니다. `options` 개체에는 시각적 개체의 새 너비와 높이를 포함하는 중첩된 `viewport` 개체가 있습니다.

* 사용자가 보고서, 페이지 또는 시각적 개체 수준에서 필터를 적용합니다.

    Power BI는 필터 조건에 따라 데이터를 필터링합니다. Power BI는 시각적 개체의 `update` 메서드를 호출하여 새 데이터로 시각적 개체를 업데이트합니다.

    시각적 개체는 중첩된 개체 중 하나에 새 데이터가 있으면 `options` 개체의 새 업데이트를 가져옵니다. 업데이트가 이루어지는 방법은 시각적 개체의 데이터 뷰 매핑 구성에 따라 달라집니다.

    자세한 내용은 [Power BI 시각적 개체의 데이터 뷰 매핑 이해](dataview-mappings.md)를 참조하세요.

* 사용자가 보고서의 다른 시각적 개체에서 데이터 요소를 선택합니다.

    사용자가 보고서의 다른 시각적 개체에서 데이터 요소를 선택하면 Power BI는 선택된 데이터 요소를 필터링하거나 강조 표시하고 시각적 개체의 `update` 메서드를 호출합니다. 시각적 개체는 필터링된 새 데이터를 가져오거나 강조 표시의 배열이 있는 동일한 데이터를 가져옵니다.

    자세한 내용은 [Power BI 시각적 개체에서 데이터 요소 강조 표시](highlight.md)를 참조하세요.

* 사용자가 보고서의 책갈피 패널에서 책갈피를 선택합니다.

    사용자가 보고서의 책갈피 패널에서 책갈피를 선택하면 다음 두 가지 작업 중 하나가 발생할 수 있습니다.

    * Power BI가 `registerOnSelectionCallback` 메서드에 의해 전달 및 등록된 함수를 호출 합니다. 콜백 함수가 해당 책갈피에 대한 선택 항목의 배열을 가져옵니다.

    * Power BI는 `options` 개체 내의 해당 `filter` 개체를 사용하여 `update` 메서드를 호출합니다.

    어느 경우든 시각적 개체는 받은 선택 항목 또는 `filter` 개체에 따라 상태를 변경해야 합니다.

    책갈피와 필터에 대한 자세한 내용은 [Power BI 시각적 개체의 시각적 개체 필터 API](filter-api.md)를 참조하세요.

### <a name="user-interacts-with-the-visual-directly"></a>사용자가 시각적 개체와 직접 상호 작용

* 사용자가 마우스로 데이터 요소를 가리킵니다.

    시각적 개체는 Power BI 도구 설명 API를 통해 데이터 요소에 대한 추가 정보를 표시할 수 있습니다. 사용자가 시각적 개체 요소를 마우스로 가리키면 시각적 개체는 이벤트를 처리하고 연결된 도구 설명 요소에 대한 데이터를 표시할 수 있습니다. 시각적 개체는 표준 도구 설명 또는 보고서 페이지 도구 설명을 표시할 수 있습니다.

    자세한 내용은 [Power BI 시각적 개체의 도구 설명](add-tooltips.md)을 참조하세요.

* 사용자가 시각적 개체 속성을 변경합니다. (예를 들어 사용자가 트리를 확장하고 시각적 개체가 시각적 개체 속성의 상태를 저장합니다.)

    시각적 개체는 Power BI API를 통해 속성 값을 저장할 수 있습니다. 예를 들어 사용자가 시각적 개체와 상호 작용하고 시각적 개체가 속성 값을 저장하거나 업데이트해야 하는 경우, 시각적 개체는 `presistProperties` 메서드를 호출할 수 있습니다.

* 사용자가 URL을 선택합니다.

    기본적으로 시각적 개체는 URL을 직접 열 수 없습니다. 대신 시각적 개체는 `launchUrl` 메서드를 호출하고 URL을 매개 변수로 전달하여 새 탭에서 URL을 열 수 있습니다.

    자세한 내용은 [시작 URL 만들기](launch-url.md)를 참조하세요.

* 사용자가 시각적 개체를 통해 필터를 적용합니다.

    시각적 개체는 `applyJsonFilter` 메서드를 호출하고 다른 시각적 개체의 데이터를 위한 필터에 조건을 전달할 수 있습니다. 기본, 고급, 튜플 필터를 비롯한 여러 가지 유형의 필터를 사용할 수 있습니다.

    자세한 내용은 [Power BI 시각적 개체의 시각적 개체 필터 API](filter-api.md)를 참조하세요.

* 사용자가 시각적 개체의 요소를 선택합니다.

    Power BI 시각적 개체에서의 선택에 대한 자세한 내용은 [Power BI 시각적 개체 선택을 사용하여 대화형 작업 추가](selection-api.md)를 참조하세요.

### <a name="visual-interacts-with-power-bi"></a>시각적 개체의 Power BI와의 상호 작용

* 시각적 개체가 Power BI에서 더 많은 데이터를 요청합니다.

    시각적 개체가 데이터를 파트별로 처리합니다. `fetchMoreData` API 메서드는 데이터 세트의 다음 데이터 조각을 요청합니다.

    자세한 내용은 [Power BI에서 더 많은 데이터 가져오기](fetch-more-data.md)를 참조하세요.

* 이벤트 서비스가 트리거됩니다.

    Power BI는 보고서를 PDF로 내보내거나 전자 메일을 통해 보고서를 보낼 수 있습니다(인증된 시각적 개체에만 적용). 렌더링이 완료되고 시각적 개체가 PDF 또는 전자 메일로 캡처될 준비가 되었다고 Power BI에 알리려면 시각적 개체가 렌더링 이벤트 API를 호출해야 합니다.

    자세한 내용은 [Power BI에서 PDF로 보고서 내보내기](../../consumer/end-user-pdf.md)를 참조하세요.

    이벤트 서비스에 대해 알아보려면 [Power BI 시각적 개체에서 이벤트 렌더링](event-service.md)을 참조하세요.

## <a name="next-steps"></a>다음 단계

시각화를 만들어 Microsoft AppSource에 추가하는 데 관심이 있으신가요? 아래 문서를 참조하세요.

* [Power BI 시각적 개체 개발](./custom-visual-develop-tutorial.md)
* [파트너 센터에 Power BI 시각적 개체 게시](../office-store.md)
