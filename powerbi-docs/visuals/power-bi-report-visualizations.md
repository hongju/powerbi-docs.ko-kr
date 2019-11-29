---
title: Power BI 서비스 및 Desktop의 보고서 시각화 개요
description: Microsoft Power BI의 보고서 시각화(시각적 개체)에 대한 개요입니다.
author: mihart
ms.author: mihart
ms.reviewer: ''
featuredvideoid: SYk_gWrtKvM
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 10/28/2019
LocalizationGroup: Visualizations
ms.openlocfilehash: 02617e690c347448ecb1c313bc86969dabeb9984
ms.sourcegitcommit: 08b73af260ded51daaa6749338cb85db2eab587f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2019
ms.locfileid: "74099079"
---
# <a name="visualizations-in-power-bi-reports"></a>Power BI 보고서의 시각화

시각화(줄여서 시각적 개체라고 함)는 데이터에서 발견된 인사이트를 표시합니다. Power BI 보고서에 시각적 개체가 하나 있는 단일 페이지가 포함될 수도 있고 시각적 개체로 가득한 여러 페이지가 포함될 수도 있습니다. Power BI 서비스에서 시각적 개체를 [보고서에서 대시보드에 고정](../service-dashboard-pin-tile-from-report.md)할 수 있습니다.

보고서 *디자이너*와 보고서 *소비자* 사이를 구분하는 것이 중요합니다.  보고서를 빌드하거나 수정하는 사용자는 디자이너입니다.  디자이너는 보고서 및 보고서의 기본 데이터 세트를 편집할 수 있는 권한이 있습니다. 즉, Power BI Desktop에서는 데이터 뷰에서 데이터 세트를 열고 보고서 보기에서 시각적 개체를 만들 수 있습니다. Power BI service 서비스에서는 [편집용 보기](../consumer/end-user-reading-view.md)의 보고서 편집기에서 데이터 세트 또는 보고서를 열 수 있습니다. 보고서 또는 대시보드가 [사용자와 공유](../consumer/end-user-shared-with-me.md)되는 경우 사용자는 보고서 *소비자*입니다. 사용자는 보고서와 시각적 개체를 보고 조작할 수 있지만, *‘디자이너’* 만큼 다양한 변경 작업을 수행할 수는 없습니다.

Power BI 시각화 창에서 바로 사용할 수 있는 다양한 시각적 개체 유형이 있습니다.

![각 시각화 개체 유형의 아이콘이 있는 창](media/power-bi-report-visualizations/power-bi-icons.png)

더 많은 선택 옵션을 보려면 [Microsoft AppSource 커뮤니티 사이트](https://appsource.microsoft.com)를 방문하여 Microsoft와 커뮤니티에서 제공하는 [사용자 지정 시각적 개체](../developer/visuals/custom-visual-develop-tutorial.md)를 찾아서 [다운로드](https://appsource.microsoft.com/marketplace/apps?page=1&product=power-bi-visuals)하세요.

<iframe width="560" height="315" src="https://www.youtube.com/embed/SYk_gWrtKvM?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>


Power BI를 처음 사용하거나 복습이 필요하면, 아래 링크를 사용하여 Power BI 시각화의 기본 사항을 알아봅니다.  또는, 목차(문서의 왼쪽에 있는)를 사용하여 훨씬 더 유용한 정보를 찾아봅니다.

## <a name="add-a-visualization-in-power-bi"></a>Power BI에서 시각적 개체 추가

보고서의 페이지에 [시각화를 만듭니다](power-bi-report-add-visualizations-i.md). [사용 가능한 시각화 및 사용 가능한 시각화 자습서의 목록](power-bi-visualization-types-for-reports-and-q-and-a.md)을 찾아봅니다. 

## <a name="upload-a-custom-visualization-and-use-it-in-power-bi"></a>사용자 지정 시각적 개체의 업로드 및 Power BI에서 사용

직접 만든 또는 [Microsoft AppSource 커뮤니티 사이트](https://appsource.microsoft.com/marketplace/apps?product=power-bi-visuals)에서 찾은 사용자 지정 시각적 개체를 추가합니다. 창의성을 발휘하고 싶으신가요? 소스 코드를 더 자세히 살펴보고 [개발자 도구](../developer/visuals/custom-visual-develop-tutorial.md)를 사용하여 새로운 시각적 개체를 만들고 [커뮤니티에도 공유](../developer/office-store.md)해 주세요. 사용자 지정 시각적 개체를 개발하는 방법을 자세히 알아보려면 [Power BI 사용자 지정 시각적 개체 개발](../developer/visuals/custom-visual-develop-tutorial.md)을 참조하세요.

## <a name="personalize-your-visualization-pane-preview"></a>시각화 창 개인 설정(미리 보기)

여러 보고서에서 동일한 사용자 지정 시각적 개체를 사용하는 경우 시각화 창에 사용자 지정 시각화를 고정할 수 있습니다. 시각화를 고정하려면 시각적 개체를 마우스 오른쪽 단추로 클릭하여 창에 고정합니다.

![시각화 창에 고정](media/power-bi-report-visualizations/power-bi-pin-custom-visual-option.png)

시각적 개체가 고정되면 다른 기본 제공 시각적 개체와 함께 라이브로 이동합니다. 이제 시각적 개체가 로그인한 계정에 연결되었므로, 로그인했다고 가정할 경우 사용자가 새로 작성하는 모든 보고서에 이 시각적 개체가 자동으로 포함됩니다. 따라서 모든 단일 보고서에 추가할 필요 없이 특정 시각적 개체를 쉽게 표준화할 수 있습니다.

![개인 설정된 시각화 창](media/power-bi-report-visualizations/power-bi-personalized-visualization-pane.png)

이 기능은 미리 보기 상태이지만 Power BI Desktop에서는 고정된 시각적 개체만 볼 수 있습니다. 또한 이 기능을 사용하려면 로그인해야 합니다.

## <a name="change-the-visualization-type"></a>시각화 유형 변경

[시각화 형식을 변경](power-bi-report-change-visualization-type.md)하여 어떤 것이 데이터와 가장 최적으로 작동하는지 봅니다.

## <a name="pin-the-visualization"></a>시각화 고정

Power BI에서 원하는 방식의 시각화가 있는 경우 타일 형태로 [대시보드에 고정](../service-dashboard-pin-tile-from-report.md)할 수 있습니다. 시각화를 고정한 후 보고서에 사용되는 시각화를 변경하면 대시보드의 타일이 변경되지 않습니다. 꺾은선형 차트인 경우 보고서에서 도넛형 차트로 변경하더라도 꺾은선형 차트를 유지합니다.

## <a name="limitations-and-considerations"></a>제한 사항 및 고려 사항
- 데이터 원본 필드 수(측정값 또는 열)에 따라 시각적 개체가 느리게 로드될 수 있습니다.  가독성과 성능상의 이유로 모두 총10~20개 필드로 시각적 개체를 제한하는 것이 좋습니다. 

- 시각적 개체 상한은 100개의 필드(측정값 또는 열)입니다. 시각적 개체를 로딩하지 못하는 경우에는 필드 수를 줄이세요.   

## <a name="next-steps"></a>다음 단계

* [Power BI의 시각화 유형](power-bi-visualization-types-for-reports-and-q-and-a.md)
* [사용자 지정 시각적 개체](../developer/power-bi-custom-visuals.md)
