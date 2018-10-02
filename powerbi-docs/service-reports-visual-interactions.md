---
title: 보고서에서 시각적 개체가 조작되는 방식 변경
description: Microsoft Power BI 서비스 보고서 및 Power BI Desktop 보고서에 시각적 상호 작용을 설정하는 방법에 대한 설명서입니다.
author: mihart
manager: kfile
ms.reviewer: ''
featuredvideoid: N_xYsCbyHPw
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 09/24/2018
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: c3671ae626496bf80ac4b212a755bb13f82ec66b
ms.sourcegitcommit: ce8332a71d4d205a1f005b703da4a390d79c98b6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/27/2018
ms.locfileid: "47418441"
---
# <a name="visualization-interactions-in-a-power-bi-report"></a>Power BI 보고서의 시각화 조작
보고서에 대한 편집 권한이 있는 경우 **시각적 상호 작용**을 사용하여 보고서 페이지의 시각화들이 서로 영향을 주는 방식을 변경할 수 있습니다. 

기본적으로 보고서 페이지의 시각화는 페이지에서 다른 시각화를 교차 필터링 및 교차 강조 표시하는 데 사용할 수 있습니다.
예를 들어 지도 시각화에서 시/도를 선택하면 세로 막대형 차트가 강조 표시되고 해당 시/도에 적용되는 데이터만 표시하도록 꺾은선형 차트가 필터링됩니다.
[필터링 및 강조 표시 정보](power-bi-reports-filters-and-highlighting.md)를 참조하세요. 또한 [드릴링](consumer/end-user-drill.md)을 지원하는 시각화가 있는 경우 기본적으로 하나의 시각화 드릴링이 보고서 페이지의 다른 시각화에 영향을 주지 않습니다. 그러나 이러한 기본 동작 모두를 재정의하고 상호 작용을 시각화 단위로 설정할 수 있습니다.

이 문서에서는 Power BI 서비스 [편집용 보기](service-interact-with-a-report-in-editing-view.md)와 Power BI Desktop에서 **시각적 상호 작용**을 사용하는 방법을 보여줍니다. 보고서를 공유하는 경우 시각적 상호 작용 설정을 변경할 수 없습니다.

> [!NOTE]
> *교차 필터* 및 *교차 강조 표시*는 여기서 설명하는 동작을 **필터** 창에서 시각화를 필터링하고 강조 표시할 때 나타나는 결과와 구분하는 데 사용합니다.  
> 
> 

<iframe width="560" height="315" src="https://www.youtube.com/embed/N_xYsCbyHPw?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

1. 시각화를 선택하여 활성화합니다.  
2. **시각적 상호 작용** 옵션을 표시합니다.
    - Power BI 서비스에서 보고서 메뉴 모음에서 드롭다운을 선택합니다.

       ![시각적 개체 상호 작용 드롭다운](media/service-reports-visual-interactions/power-bi-visual-interaction.png)

    - 바탕 화면에서 **서식 > 상호 작용** 을 선택합니다.

        ![형식 및 상호 작용 선택](media/service-reports-visual-interactions/pbi-visual-interaction-desktop.png)

3. 시각화 상호 작용 컨트롤을 켜려면 **상호 작용 편집**을 선택합니다. Power BI는 보고서 페이지의 다른 모든 시각화에 교차 필터 및 교차 강조 표시 아이콘을 추가합니다.
   
    ![시각적 상호 작용이 설정된 보고서](media/service-reports-visual-interactions/power-bi-icons-on.png)
3. 선택한 시각화가 서로 간에 어떤 영향을 미쳐야 하는지 확인합니다.  그리고 필요에 따라 보고서 페이지의 다른 모든 시각화에 대해 이 작업을 반복합니다.
   
   * 시각화를 교차 필터링해야 하는 경우 **필터** 아이콘 ![필터 아이콘](media/service-reports-visual-interactions/pbi-filter-icon-outlined.png)을 선택합니다.
   * 시각화를 교차 강조 표시해야 하는 경우 **강조 표시** 아이콘 ![강조 표시 아이콘](media/service-reports-visual-interactions/pbi-highlight-icon-outlined.png)을 선택합니다.
   * 영향을 미치지 않아야 할 경우 **영향을 주지 않음** 아이콘 ![영향을 주지 않음 아이콘](media/service-reports-visual-interactions/pbi-noimpact-icon-outlined.png)을 선택합니다.

4. 드릴링 컨트롤을 켜려면 **기타 시각적 개체 드릴 필터링**을 선택합니다.  이제 시각화에서 드릴다운(및 드릴업)하면 보고서 페이지의 다른 시각화가 현재 드릴링 선택을 반영하도록 변경됩니다. 

   ![컨트롤을 드릴링하도록 설정하는 비디오](media/service-reports-visual-interactions/drill2.gif)

