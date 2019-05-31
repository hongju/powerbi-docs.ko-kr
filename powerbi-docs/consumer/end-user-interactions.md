---
title: 보고서에서 시각적 개체가 조작되는 방식 이해
description: 보고서 페이지에서 시각적 개체가 상호 작용하는 방법을 설명하는 Power BI 최종 사용자를 위한 설명서입니다.
author: mihart
manager: kvivek
ms.custom: seodec18
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 05/29/2019
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: 7148a52d7c7475fbe685f83b1e1cc325521460db
ms.sourcegitcommit: d88cc6a87d4ba82ad2c4d496a3634f927e4ac529
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/30/2019
ms.locfileid: "66413155"
---
# <a name="how-visuals-cross-filter-each-other-in-a-power-bi-report"></a>Power BI 보고서에서 시각적 개체가 서로 교차 필터링되는 방식
Power BI의 뛰어난 기능 중 하나는 보고서 페이지의 모든 시각적 개체가 상호 연결되는 방식입니다. 시각적 개체 중 하나에서 데이터 요소를 선택하는 경우 페이지에서 해당 데이터를 포함하는 다른 모든 시각적 개체는 해당 선택 사항에 따라 변경됩니다. 

![시각적 개체의 상호 작용에 대한 비디오](media/end-user-interactions/interactions.gif)

기본적으로 보고서 페이지에 하나의 시각화에서 데이터 요소를 교차 필터링을 선택 하면 교차 강조 표시 하 고 페이지의 다른 시각화 요소를 드릴 합니다. 

이 유용할 수 있습니다 다른 데이터에 어떻게 하나의 값을 식별 하에 기여 합니다. 예를 들어, 월 차트 별 총 단위의 각 열 세그먼트에서 기여도 강조 표시 도넛형 차트에서 조정 세그먼트를 선택 하 고 오른쪽의 꺾은선형 차트가 필터링 했습니다.

![시각적 개체 상호 작용의 이미지](media/end-user-interactions/power-bi-interactions.png)

[필터링 및 강조 표시 정보](../power-bi-reports-filters-and-highlighting.md)를 참조하세요. 

페이지의 시각적 개체가 상호 작용하는 방법은 보고서 ‘디자이너’에 의해 설정됩니다.  디자이너는 시각적 개체 상호 작용을 설정하거나 끄고, 기본 교차 필터링, 크로스 강조 표시 및 드릴링 동작을 변경할 수 있는 옵션이 있습니다. 
  
> [!NOTE]
> *교차 필터* 및 *교차 강조 표시*는 여기서 설명하는 동작을 **필터** 창에서 시각화를 필터링하고 강조 표시할 때 나타나는 결과와 구분하는 데 사용합니다.  

## <a name="considerations-and-troubleshooting"></a>고려 사항 및 문제 해결
- 보고서의 시각화를 지 원하는 경우 [드릴](../power-bi-visualization-drill-down.md), 기본적으로 하나의 시각화 드릴링 영향을 주지 않습니다 보고서 페이지의 다른 시각화 요소에 있습니다.     
- VisualA visualB 상호 작용할 수를 사용 하면 visualA에서 시각적 개체 수준 필터 visualB에 적용 됩니다.

## <a name="next-steps"></a>다음 단계
[보고서 필터를 사용하는 방법](../power-bi-how-to-report-filter.md)
