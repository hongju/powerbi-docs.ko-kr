---
title: "Power BI 서비스에서 인쇄"
description: "Power BI에서 대시보드, 타일 또는 보고서 페이지를 인쇄합니다."
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: 
qualityfocus: 
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/06/2017
ms.author: mihart
ms.openlocfilehash: d8dc99fec9851dc6f5d3786d2fc1d615e4ee22b4
ms.sourcegitcommit: 54da95f184dd0f7bb59bb0bc8775a1d93129b195
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/08/2017
---
# <a name="printing-from-power-bi-service"></a>Power BI 서비스에서 인쇄
Power BI 서비스에서 전체 대시보드, 대시보드 타일, 보고서 페이지 또는 보고서 시각적 개체를 인쇄합니다. 보고서는 한 번에 한 페이지만 인쇄할 수 있습니다. 전체 보고서를 한 번에 인쇄할 수는 없습니다.

> [!NOTE]
> 인쇄는 Power BI Desktop이 아닌 Power BI 서비스에서만 사용할 수 있습니다.
> 
> 

Amanda가 대시보드 및 보고서에서 인쇄하는 모습을 시청합니다. 그런 다음 비디오 아래에 있는 단계별 지침을 따라서 직접 시도해 볼 수 있습니다.

<iframe width="560" height="315" src="https://www.youtube.com/embed/jtlLGRKBvXY" frameborder="0" allowfullscreen></iframe>

## <a name="print-a-dashboard"></a>대시보드 인쇄
1. 인쇄하려는 대시보드를 엽니다.
2. 오른쪽 위의 모서리에서 줄임표(...)를 선택하고 **대시보드 인쇄**를 선택합니다.
   
    ![](media/service-print/pbi_print_dash_ellipses.png)
3. 브라우저의 인쇄 창이 열립니다. 설정 및 인쇄 대상을 선택하고 **인쇄**를 선택합니다.
   
   > [!NOTE]
   > 표시된 인쇄 대화 상자는 사용 중인 브라우저에 따라 달라집니다.
   > 
   > 
   
    ![](media/service-print/pbi_print_dash_new2.png)

## <a name="print-a-dashboard-tile"></a>대시보드 타일 인쇄
1. 줄임표를 선택하고 포커스 아이콘 ![](media/service-print/power-bi-focus-icon.png)을 선택하여 [포커스 모드에서 타일을 엽니다](service-focus-mode.md).
   
    ![](media/service-print/menu-options.png)
2. 이제 맨 위 탐색 모음에서 전체 화면 아이콘![](media/service-print/power-bi-full-screen-icon.png)을 선택하여 [전체 화면 모드](service-fullscreen-mode.md)에서 타일을 봅니다.
3. 타일을 마우스로 가리켜서 옵션 메뉴 표시
   
    ![](media/service-print/menu-options-new.png)
4. 인쇄 아이콘 ![](media/service-print/print-icon.png)을 선택합니다.     
   
   > [!NOTE]
   > 표시된 인쇄 대화 상자는 사용 중인 브라우저에 따라 달라집니다.
   > 
   > 

## <a name="print-a-report-page"></a>보고서 페이지 인쇄
한 번에 한 페이지의 보고서를 인쇄할 수 있습니다.

1. 읽기용 보기 또는 편집용 보기에서 보고서를 엽니다.
2. **파일** > **인쇄**를 선택하여 현재 보고서 페이지를 인쇄합니다.
   
    ![](media/service-print/power-bi-print.png)
3. 브라우저의 인쇄 창이 열립니다.
   
   > [!NOTE]
   > 표시된 인쇄 대화 상자는 사용 중인 브라우저에 따라 달라집니다.
   > 
   > 

## <a name="print-a-report-visual"></a>보고서 시각적 개체 인쇄
1. 타일 위로 마우스를 가져가고 오른쪽 위 모서리에서 포커스 아이콘 ![](media/service-print/power-bi-focus-icon.png)을 선택하여 [시각적 개체를 포커스 모드에서 엽니다](service-focus-mode.md). 
2. 위의 *보고서 페이지 인쇄*의 2-3단계를 진행합니다.

## <a name="considerations-and-troubleshooting"></a>고려 사항 및 문제 해결
* Q: **인쇄** 단추를 찾을 수 없습니다.    
* A: Power BI Desktop을 사용하는 경우 인쇄는 지원되지 않습니다.  인쇄는 Power BI 서비스에서만 작동합니다.
* Q: 한 번에 모든 보고서 페이지를 인쇄할 수 없습니다.    
* A: 그렇습니다. 보고서 페이지는 한 번에 한 페이지만 인쇄할 수 있습니다.
* Q: PDF로 인쇄할 수 없습니다.    
* A: 브라우저에서 PDF 드라이버를 이미 구성한 경우에만 옵션이 나타납니다.    
* Q: **인쇄**를 선택한 경우 표시 내용이 여기에 표시된 내용과 일치하지 않습니다.    
* A: 인쇄 화면은 브라우저 및 소프트웨어 버전에 따라 다릅니다.
* Q: 내 인쇄물이 제대로 조정되지 않습니다.  내 대시보드가 페이지에 맞지 않습니다. 기타 크기 조정 및 방향 질문입니다.    
* A: 인쇄된 복사본이 Power BI 서비스와 정확히 동일하게 나타난다고는 보장할 수 없습니다. 크기 조정, 여백, 시각적 개체 세부 정보, 방향 및 크기와 같은 항목은 Power BI에서 제어되지 않습니다. 다음과 같은 문제에 대한 도움말은 특정 브라우저에 대한 설명서를 참조하세요.      

## <a name="next-steps"></a>다음 단계
[동료 및 다른 사용자와 대시보드 및 보고서 공유](service-share-dashboards.md)

궁금한 점이 더 있나요? [Power BI 커뮤니티를 이용하세요.](http://community.powerbi.com/)

