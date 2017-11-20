---
title: "보고서에 사용자 지정 시각화 추가"
description: "Power BI 보고서에 사용자 지정 시각적 개체 추가"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: gido6wr5pvE
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 09/03/2017
ms.author: mihart
ms.openlocfilehash: c6c9065238ece60088c1e37fe699a384ea5d70b6
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2017
---
# <a name="add-a-custom-visualization-to-a-report"></a>보고서에 사용자 지정 시각화 추가
[사용자 지정 시각적 템플릿를 다운로드](service-custom-visuals-office-store.md)하여 컴퓨터 또는 다른 위치에 저장했습니다.  다음 단계는 시각화 창에 옵션으로 추가할 수 있게 시각적 템플릿을 보고서로 가져오는 것입니다.

![](media/power-bi-report-add-custom-visual/pbi-custom-viz-icon.png)

Will이 사용자 지정 시각적 개체를 다운로드하여 보고서에 추가하는 과정을 시청합니다. 그런 다음 비디오 아래에 있는 단계별 지침을 따라서 직접 시도해 볼 수 있습니다.

<iframe width="560" height="315" src="https://www.youtube.com/embed/gido6wr5pvE" frameborder="0" allowfullscreen></iframe>

> [!IMPORTANT]
> 사용자 지정 시각적 템플릿은 가져올 때 특정 보고서에 추가됩니다. 다른 보고서에서 시각적 템플릿을 사용하려는 경우 또한 해당 보고서로 가져와야 합니다. 사용자 지정 시각적 개체가 있는 보고서가 **다른 이름으로 저장** 옵션을 사용하여 저장될 때 사용자 지정 시각적 템플릿의 복사본이 새 보고서와 함께 저장됩니다.
> 
> 

1. [Power BI](http://app.powerbi.com)를 열고 사용자 지정 시각화를 추가하려는 보고서를 선택합니다.  
2. [편집용 보기](service-interact-with-a-report-in-editing-view.md)에서 보고서를 엽니다.
3. **시각화** 창에서 줄임표(...)를 선택합니다.
   
    ![](media/power-bi-report-add-custom-visual/pbi_customvizellipses.jpg)
4. **가져오기** 를 선택하고 다운로드한 사용자 지정 시각화(.pbiviz 파일)를 저장한 위치로 이동합니다.
5. 
   >[!IMPORTANT]
   >경고를 검토하고 신뢰할 수 있는 원본에서 가져온 시각적 개체를 확인합니다. Power BI 시각적 갤러리, 전자 메일 또는 다른 원본을 통해 가져온 특정 사용자 지정 시각적 개체를 사용할지 확실하지 않은 경우 Microsoft는 IT 부서와 작업하는 것을 추천합니다. [보안 및 개인 정보에 대한 사용자 지정 시각적 개체 검토](service-custom-visuals-review-for-security-and-privacy.md)를 참조하세요.
6. **열기**를 선택합니다. 사용자 지정 시각화 아이콘( *템플릿* 이라고도 함)이 시각화 창에 추가됩니다.
   
    ![](media/power-bi-report-add-custom-visual/pbi_customvizaddedicon.jpg)
   
    사용자 지정 시각적 템플릿은 가져올 때 특정 보고서의 시각화 창에 추가됩니다. 이제 해당 보고서에서 선택하여 사용할 수 있습니다.
    다른 보고서에서 시각적 개체를 사용하려는 경우 또한 해당 보고서의 시각화 창으로 가져와야 합니다.
   
    사용자 지정 시각적 개체가 있는 보고서가 **다른 이름으로 저장** 옵션을 사용하여 저장될 때 사용자 지정 시각적 템플릿의 복사본이 새 보고서와 함께 저장됩니다.
   
    사용자 지정 시각적 템플릿을 가져오면 해당 특정 보고서의 시각화 창에서 제거할 수 없습니다. 시각화를 만든느 데 사용한 경우 시각화를 제거할 수 있지만 해당 아이콘은 시각화 창에 그대로 남아 있습니다.
7. 편집용 보기에서 사용자 지정 시각화 아이콘을 선택합니다.  워터 마크(템플릿)을 보고서 캔버스에 추가합니다.
   
    ![](media/power-bi-report-add-custom-visual/pbi_template.jpg)
8. 템플릿에 필드를 끌어 놓아서 시각화를 만듭니다. 필요에 따라 시각적 개체를 대시보드에 고정합니다. 이 예제에서는 테이블 Heatmap 사용자 지정 시각화를 보여줍니다.
   
    ![](media/power-bi-report-add-custom-visual/pbi_customvizadded.jpg)
9. Power BI의 다른(네이티브) 시각화와 마찬가지로 이 시각화를 계속 사용하고 탐색합니다.

## <a name="considerations-and-troubleshooting"></a>고려 사항 및 문제 해결
* 사용자 지정 시각적 개체를 PowerPoint로 내보내기에서 지원하거나 고객이 보고서 페이지를 구독할 때 수신되는 이메일에 표시하려면 Microsoft 사용자 지정 시각적 개체 인증 프로세스를 통과한 *인증된 사용자 지정 시각적 개체*여야 합니다.  *사용자 지정 시각적 개체 인증*의 목록을 보고 인증 프로세스에 대해 자세히 알아보려면 [인증된 사용자 지정 시각적 개체](power-bi-custom-visuals-certified.md)를 참조하세요.

## <a name="next-steps"></a>다음 단계
[Office 스토어에서 사용자 지정 시각적 개체 다운로드 및 사용](service-custom-visuals-office-store.md)  
[YouTube에서 Microsoft의 사용자 지정 시각적 재생 목록](https://www.youtube.com/playlist?list=PL1N57mwBHtN1vIjfvuBIzZllrmKo-Vz6x)  
[Power BI의 시각화](power-bi-report-visualizations.md)  
[Power BI의 사용자 지정 시각화](power-bi-custom-visuals.md)  
[Power BI Desktop에서 사용자 지정 시각화 사용](power-bi-custom-visuals-use.md)  
[보안 및 개인 정보에 대한 사용자 지정 시각적 개체 검토](service-custom-visuals-review-for-security-and-privacy.md)  
[사용자 지정 시각적 개체 개발자 도구 시작하기(미리 보기)](service-custom-visuals-getting-started-with-developer-tools.md)  
[사용자 지정 시각적 개체를 Office 스토어에 게시](developer/office-store.md)  
[비디오: Sachin Patney 및 Nico Cristache와 Power BI에 대한 사용자 지정 시각화 만들기](https://www.youtube.com/watch?v=kULc2VbwjCc)  

궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](http://community.powerbi.com/)

