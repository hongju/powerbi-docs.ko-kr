---
title: Power BI 보고서의 필터 유형
description: Power BI의 보고서에 페이지 필터, 시각화 필터 또는 보고서 필터 추가
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 06/25/2019
ms.author: maggies
LocalizationGroup: Reports
ms.openlocfilehash: c96b4ebae574a3b6a6fa54c5f5dc99b5bc948a90
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2019
ms.locfileid: "73874417"
---
# <a name="types-of-filters-in-power-bi-reports"></a>Power BI 보고서의 필터 유형

필터는 같은 방식으로 만들어 지지 않으므로 모두 같은 방식으로 동작하지는 않습니다. 만드는 방법에 따라 편집 모드에서 새 필터 창에서 작동하는 방식이 다릅니다. 이 문서에서는 필터를 만드는 다양한 방식 및 필터별로 서로 다른 기능 등, 다양한 종류의 필터에 대해 설명합니다. [보고서에 필터를 추가](power-bi-report-add-filter.md)하는 방법에 대해 읽어 보세요. 

![필터 창](media/power-bi-report-filter-types/power-bi-filter-pane.png)

가장 일반적인 두 필터 유형(수동 및 자동)으로 시작하겠습니다.

## <a name="manual-filters"></a>수동 필터 

수동 필터는 보고서 작성자가 새 필터 창의 어느 위치나 끌어서 놓을 수 있는 필터입니다. 보고서에 대한 편집 권한이 있는 사용자는 새 창에서 이 필터를 편집, 삭제, 지우기, 숨기기, 잠금, 이름 바꾸기 또는 정렬할 수 있습니다.

## <a name="automatic-filters"></a>자동 필터 

자동 필터는 시각적 개체를 작성할 때 필터 창의 시각적 개체 수준에 자동으로 추가되는 필터입니다. 이 필터는 시각적 개체를 구성하는 필드를 기반으로 합니다. 보고서에 대한 편집 권한이 있는 사용자는 새 창에서 이 필터를 편집, 지우기, 숨기기, 잠금, 이름 바꾸기 또는 정렬할 수 있습니다. 시각적 개체는 이러한 필드를 참조하므로, 사용자가 자동 필터를 삭제할 수 없습니다.

## <a name="more-advanced-filters"></a>추가 고급 필터

다음 필터 유형은 덜 일반적이지만, 보고서에 표시되는 경우 이를 이해하는 것이 중요합니다. 또한 보고서에 적합한 필터만 만드는 데 유용할 수 있습니다.

## <a name="include-and-exclude-filters"></a>포함/제외 필터

포함/제외 필터는 시각적 개체에 포함 또는 제외 기능을 사용할 때 자동으로 필터 창에 추가됩니다. 보고서에 대한 편집 권한이 있는 사용자는 새 창에서 이 필터를 삭제, 잠금, 숨기기 또는 정렬할 수 있습니다. 시각적 개체의 포함 및 제외 기능과 연관되어 있으므로 포함 또는 제외 필터를 편집하거나 지우거나 그 이름을 바꿀 수 없습니다.

![제외 필터](media/power-bi-report-filter-types/power-bi-filters-exclude.png)

## <a name="drill-down-filters"></a>드릴다운 필터

드릴다운 필터는 보고서의 시각적 개체에 드릴다운 기능을 사용할 때 자동으로 필터 창에 추가됩니다. 보고서에 대한 편집 권한이 있는 사용자는 새 창에서 필터를 편집하거나 지울 수 있습니다. 시각적 개체의 드릴다운 기능과 연관되어 있기 때문에 이 필터를 삭제, 숨기기, 잠금, 이름 바꾸기 또는 정렬할 수 없습니다. 드릴다운 필터를 제거하려면 시각적 개체의 드릴업 단추를 클릭합니다.

![드릴다운 필터](media/power-bi-report-filter-types/power-bi-filters-drill-down.png)

## <a name="cross-drill-filters"></a>크로스드릴 필터

크로스드릴 필터는 교차 필터 또는 교차 강조 표시 기능을 통해 드릴다운 필터가 보고서 페이지의 다른 시각적 개체에 전달될 때 자동으로 새 창에 추가됩니다. 시각적 개체의 드릴다운 기능과 연관되어 있기 때문에, 보고서에 대한 편집 권한이 있는 사용자는 이 필터를 삭제, 지우기, 숨기기, 잠금, 이름 바꾸기 또는 정렬할 수 없습니다. 다른 시각적 개체의 드릴다운을 통해 나온 것이므로 이 필터를 편집할 수도 없습니다. 드릴다운 필터를 제거하려면 필터를 전달하는 시각적 개체의 드릴업 단추를 클릭합니다.

## <a name="drillthrough-filters"></a>드릴스루 필터

드릴스루 필터는 드릴스루 기능을 통해 한 페이지에서 다른 페이지로 전달됩니다. 드릴스루 창에 표시됩니다. 두 가지 유형의 드릴스루 필터가 있습니다. 첫 번째 유형은 드릴스루 호출하는 유형입니다. 보고서 편집자는 이 유형의 필터를 편집, 삭제, 지우기, 숨기기 또는 잠글 수 있습니다. 두 번째 유형은 소스 페이지의 페이지 수준 필터를 기반으로 대상에 전달되는 드릴스루 필터입니다. 보고서 편집자는 이 임시 유형의 드릴스루 필터를 편집, 삭제 또는 지울 수 있습니다. 이 필터를 잠그거나 최종 사용자에게 숨길 수 없습니다.

## <a name="url-filters"></a>URL 필터

URL 필터는 URL 쿼리 매개 변수를 추가하여 새 창에 추가됩니다. 보고서에 대한 편집 권한이 있는 사용자는 새 창에서 필터를 편집, 삭제 또는 지울 수 있습니다. URL 매개 변수와 연관되어 있기 때문에 이 필터를 숨기기, 잠금, 이름 바꾸기 또는 정렬할 수 없습니다. 필터를 제거하려면 URL에서 매개 변수를 제거합니다. 다음은 매개 변수가 있는 URL 예입니다.

app.powerbi.com/groups/me/apps/*app-id*/reports/*report-id*/ReportSection?filter=Stores~2FStatus%20eq%20'Off'

![URL 필터](media/power-bi-report-filter-types/power-bi-filter-url.png)

[URL 필터](service-url-filters.md)에 대해 자세히 읽어 보세요.

## <a name="pass-through-filters"></a>통과 필터

통과 필터는 질문 및 답변을 통해 작성된 시각적 개체 수준 필터입니다. 작성자는 새 창에서 이러한 필터를 삭제, 숨기기 또는 정렬할 수 있습니다. 하지만 이러한 필터를 이름 바꾸기, 편집, 지우기 또는 잠글 수는 없습니다.

![질문 및 답변을 통한 통과 필터](media/power-bi-report-filter-types/power-bi-filters-qna.png)

## <a name="comparing-filter-types"></a>필터 유형 비교

다음 표에서는 작성자가 다양한 유형의 필터를 사용하여 수행할 수 있는 일을 비교합니다.

| 필터 형식 | 편집 | 지우기 | 삭제 | 숨기기 | 잠금 | 정렬 | 이름 바꾸기 |
|----|----|----|----|----|----|----|----|
| 수동 필터 | Y | Y | Y | Y | Y | Y | Y |
| 자동 필터 | Y | Y | N | Y | Y | Y | Y |
| 포함/제외 필터 | N | N | Y | Y | Y | Y | N |
| 드릴다운 필터 | Y | Y | N | N | N | N | N |
| 크로스드릴 필터 | N | N | N | N | N | N | N |
| 드릴스루 필터(드릴스루 호출) | Y | Y | Y | Y | Y | N | N |
| 드릴스루 필터(임시) | Y | Y | Y | N | N | N | N |
| URL 필터 - 임시 | Y | Y | Y | N | N | N | N |
| 통과 필터 | N | N | Y | Y | N | Y | N |



## <a name="next-steps"></a>다음 단계

[보고서에 필터 추가](power-bi-report-add-filter.md)

[보고서 필터 창 둘러보기](consumer/end-user-report-filter.md)

[필터 및 보고서에서 강조 표시](power-bi-reports-filters-and-highlighting.md)

궁금한 점이 더 있나요? [Power BI 커뮤니티를 이용하세요.](https://community.powerbi.com/)

