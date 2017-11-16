---
title: "보고서에서 시각적 개체가 조작되는 방식 변경"
description: "Microsoft Power BI 보고서에 시각적 상호 작용을 설정하는 방법에 대한 설명서입니다."
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: N_xYsCbyHPw
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 09/25/2017
ms.author: mihart
ms.openlocfilehash: 126bd40e98a88138a2732155f9792d65666e52c7
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2017
---
# <a name="visualization-interactions-in-a-power-bi-report"></a>Power BI 보고서의 시각화 조작
기본적으로 보고서 페이지의 시각화는 페이지에서 다른 시각화를 교차 필터링 및 교차 강조 표시하는 데 사용할 수 있습니다.
예를 들어 지도 시각화에서 시/도를 선택하면 세로 막대형 차트가 강조 표시되고 해당 시/도에 적용되는 데이터만 표시하도록 꺾은선형 차트가 필터링됩니다.
[필터링 및 강조 표시 정보](power-bi-reports-filters-and-highlighting.md)를 참조하세요.

이 기본 동작을 변경하려면 **시각적 개체 조작** 컨트롤을 사용합니다. 시각적 개체 조작은 [편집용 보기](service-interact-with-a-report-in-editing-view.md)에서만 사용 가능합니다. 보고서를 사용자와 공유하는 경우 시각적 개체 조작에 대한 액세스가 없습니다.

> [!NOTE]
> *교차 필터* 및 *교차 강조 표시*는 여기서 설명하는 동작을 **필터** 창에서 시각화를 필터링하고 강조 표시할 때 나타나는 결과와 구분하는 데 사용합니다.  
> 
> 

<iframe width="560" height="315" src="https://www.youtube.com/embed/N_xYsCbyHPw?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

1. 시각화를 선택하여 활성화합니다.  
2. 위쪽 메뉴 모음에서 선택하여 **시각적 개체 조작** 을 켭니다. 보고서 페이지의 다른 시각화 위를 마우스로 가리키면 필터 및 강조 표시 아이콘이 나타납니다.
   
    ![](media/service-reports-visual-interactions/pbi-visual-interaction-icon.png)
3. 선택한 시각화가 서로 간에 어떤 영향을 미쳐야 하는지 확인합니다.  
   
   * 다른 시각화를 교차 필터링해야 하는 경우 **필터** 아이콘 ![](media/service-reports-visual-interactions/pbi-filter-icon-outlined.png)을 선택합니다.
   * 다른 시각화를 교차 강조 표시해야 하는 경우 **강조 표시** 아이콘 ![](media/service-reports-visual-interactions/pbi-highlight-icon-outlined.png)을 선택합니다.
   * 영향을 미치지 않아야 할 경우 **영향을 주지 않음** 아이콘 ![](media/service-reports-visual-interactions/pbi-noimpact-icon-outlined.png)을 선택합니다.
4. 필요에 따라 보고서 페이지의 다른 모든 시각화에 대해 이 작업을 반복합니다.

### <a name="next-steps"></a>다음 단계
[보고서 필터를 사용하는 방법](power-bi-how-to-report-filter.md)

[필터 및 보고서에서 강조 표시](power-bi-reports-filters-and-highlighting.md)

[Power BI - 기본 개념](service-basic-concepts.md)

궁금한 점이 더 있나요? [Power BI 커뮤니티를 이용하세요.](http://community.powerbi.com/)

