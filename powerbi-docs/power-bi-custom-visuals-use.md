---
title: "보고서에 사용자 지정 시각적 개체 추가(데스크톱)"
description: "데스크톱의 보고서에 사용자 지정 시각적 개체 추가"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: complete
qualitydate: 03/15/2016
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 09/27/2017
ms.author: mihart
ms.openlocfilehash: b3a3e34fac546ee57cd66924e72a2c93aa647850
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2017
---
# <a name="add-a-custom-visual-to-a-report-desktop"></a>보고서에 사용자 지정 시각적 개체 추가(데스크톱)
[사용자 지정 시각적 템플릿를 다운로드](service-custom-visuals-office-store.md)하여 컴퓨터 또는 다른 위치에 저장했습니다.  다음 단계는 시각화 창에 옵션으로 추가할 수 있게 사용자 지정 시각적 템플릿을 보고서로 가져오는 것입니다.

![](media/power-bi-custom-visuals-use/pbi-custom-viz-icon.png)

사용자 지정 시각적 템플릿은 가져올 때 특정 보고서에 추가됩니다. 다른 보고서에서 시각적 템플릿을 사용하려는 경우 또한 해당 보고서로 가져와야 합니다. 사용자 지정 시각적 개체가 있는 보고서가 **다른 이름으로 저장** 옵션을 사용하여 저장될 때 사용자 지정 시각적 템플릿의 복사본이 새 보고서와 함께 저장됩니다.

1. Power BI Desktop을 열고 사용자 지정 시각화를 추가하려는 보고서를 선택합니다.   
2. 사용자 지정 시각적 템플릿은 **파일** 메뉴 또는 **시각화** 창에서 가져올 수 있습니다.
   
    **데스크톱 파일 메뉴에서**
   
    보고서 **파일** 메뉴에서 **가져오기** &gt; **Power BI 사용자 지정 시각적 개체**를 선택합니다. 편집용 보기에 있어야 합니다.    
   
      ![](media/power-bi-custom-visuals-use/power-bi-import.png)
   
    **시각화 창에서**
   
    **시각화** 창에서 **삽입(...)**을 선택합니다.    
   
      ![](media/power-bi-custom-visuals-use/insertpane.png)
   
    **사용자 지정 시각적 개체 가져오기**를 선택합니다.  
   
      ![](media/power-bi-custom-visuals-use/insertpane.png)
3. **경고를 검토**합니다.
   
    사용자 지정 시각적 개체는 보고서의 데이터에 액세스할 수 있으며 사용자 지정 시각적 개체를 포함하는 보고서를 공유하는 경우 동료는 동일한 데이터에 액세스할 수 있습니다. 사용자 지정 시각적 개체를 검토하려면 신뢰할 수 있는 원본에서 가져와야 합니다. Office 온라인 스토어, 전자 메일 또는 다른 원본을 통해 가져온 특정 사용자 지정 시각적 개체를 사용할지 확실하지 않은 경우 Microsoft는 IT 부서와 작업하는 것을 추천합니다.
   
    ![](media/power-bi-custom-visuals-use/caution.png)
4. 사용자 지정 시각적 개체 .pbiviz 파일을 저장한 위치로 이동하여 엽니다.
5. 아이콘( *템플릿* 이라고도 함)이 **시각화** 창에 추가됩니다.
   
    ![](media/power-bi-custom-visuals-use/visualuse.png)
6. 시각화 창에서 다른 템플릿 중 하나와 함께 보고서에 추가할 사용자 지정 시각적 개체 템플릿을 선택합니다. 필드와 필터를 추가하고 시각적 개체를 작성합니다.
7. 다른 시각적 개체와 마찬가지로 사용자 지정 시각적 개체의 서식을 지정합니다.  **시각화** 창에서 페인트 롤러 아이콘을 선택합니다. 사용할 수 있는 서식 옵션은 시각적 개체 유형에 따라 달라집니다.

## <a name="considerations-and-troubleshooting"></a>고려 사항 및 문제 해결
* 사용자 지정 시각적 개체를 [PowerPoint로 내보내기](service-publish-to-powerpoint.md)에서 지원하거나 [고객이 보고서 페이지를 구독할 때 수신되는 이메일에 표시](service-report-subscribe.md)하려면 Microsoft 사용자 지정 시각적 개체 인증 프로세스를 통과한 *인증된 사용자 지정 시각적 개체*여야 합니다.  *사용자 지정 시각적 개체 인증*의 목록을 보고 인증 프로세스에 대해 자세히 알아보려면 [인증된 사용자 지정 시각적 개체](power-bi-custom-visuals-certified.md)를 참조하세요.

## <a name="next-steps"></a>다음 단계
[Office 스토어에서 사용자 지정 시각적 개체 다운로드 및 사용](service-custom-visuals-office-store.md)  
[Power BI Service의 보고서에 사용자 지정 시각적 개체 추가](power-bi-report-add-custom-visual.md)  
[사용자 지정 시각적 개체를 Office 스토어에 게시](developer/office-store.md)  
[Power BI의 사용자 지정 시각화](power-bi-custom-visuals.md)  
궁금한 점이 더 있나요? [Power BI 커뮤니티를 이용하세요.](http://community.powerbi.com/)

