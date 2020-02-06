---
title: Power BI 서비스에서 인쇄
description: Power BI 서비스에서 대시보드, 타일 또는 보고서 페이지를 인쇄합니다.
author: mihart
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 12/12/2019
ms.author: mihart
LocalizationGroup: Common tasks
ms.openlocfilehash: 5ad3e1f18e6b18116a070d9013bf7cd64d7e1c0f
ms.sourcegitcommit: 6272c4a0f267708ca7d38a45774f3bedd680f2d6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/06/2020
ms.locfileid: "75218032"
---
# <a name="printing-from-the-power-bi-service"></a>Power BI 서비스에서 인쇄

## <a name="what-can-be-printed"></a>인쇄할 수 있는 내용
[!INCLUDE [power-bi-service-new-look-include](../includes/power-bi-service-new-look-include.md)]

Power BI 서비스에서 전체 대시보드, 대시보드 타일, 보고서 페이지 또는 보고서 시각적 개체를 인쇄합니다. 보고서가 여러 페이지로 이루어진 경우 각 페이지를 개별적으로 인쇄해야 합니다. 

## <a name="printing-considerations"></a>인쇄 고려 사항

대부분의 Power BI 대시보드 및 보고서는 보고서 ‘디자이너’가 온라인에서 사용되고 다양한 디바이스에서 멋지게 표시되도록 생성한 것입니다.  보고서를 인쇄할 때 해당 콘텐츠가 용지에 표시되는 모양은 브라우저를 통해 제어합니다. 

브라우저 설정을 사용하여 인쇄물을 조정할 수 있지만, 여전히 원하는 결과를 얻지 못할 수 있습니다. 먼저 [PDF로 내보낸](end-user-pdf.md) 다음, PDF를 인쇄하는 것이 좋습니다. 

## <a name="adjust-your-browser-print-settings"></a>브라우저 인쇄 설정 조정
Power BI에서 인쇄하는 경우 브라우저에서 인쇄 창이 열립니다. 각 브라우저의 인쇄 창은 서로 다릅니다. 하지만 모든 브라우저에 인쇄물의 모양을 제어하는 데 사용할 수 있는 유사한 옵션이 있습니다. 

다음은 인쇄물의 서식 지정에 사용할 수 있는 몇 가지 간단한 팁입니다.

   > 
1. 대시보드, 보고서 또는 시각적 개체가 가로로 긴 경우에는 **가로** 레이아웃을 사용하는 것이 좋습니다. 

   ![가로 레이아웃이 표시된 인쇄 대화 상자](./media/end-user-print/power-bi-landscape-layout.png)

2. 인쇄된 페이지에 더 많은 내용을 넣으려면 여백, 배율 등의 설정을 조정합니다. 

    ![기타 설정이 표시된 인쇄 대화 상자](./media/end-user-print/power-bi-margins.png)

원하는 모양이 될 때까지 특정 브라우저의 설정을 시험해 보세요. 일부 브라우저에는 배경 그래픽을 인쇄하는 옵션도 있습니다. 

## <a name="print-a-dashboard"></a>대시보드 인쇄
1. 인쇄하려는 대시보드를 엽니다.
2. 왼쪽 위 모서리에서 [내보내기]를 선택하고 **이 페이지 인쇄**를 선택합니다.
   
    ![대시보드 인쇄 옵션](./media/end-user-print/power-bi-dashboard-print.png)

3. 브라우저의 인쇄 창이 열립니다. 설정을 선택합니다. 예를 들어 대시보드가 가로로 긴 경우에는 레이아웃을 **가로**로 변경하는 것이 좋습니다. **인쇄**를 선택합니다.
   
    ![인쇄 대화 상자](./media/end-user-print/power-bi-print-dash.png)

## <a name="print-a-dashboard-tile"></a>대시보드 타일 인쇄
1. 상단 메뉴 모음에서 전체 화면 아이콘 ![전체 화면 아이콘](./media/end-user-print/power-bi-full-screen.png)을 선택하여 [전체 화면 모드](end-user-focus.md)에서 대시보드를 엽니다.

3. 마우스로 가리켜 **추가 옵션**(...)을 표시한 다음 **포커스 모드에서 열기** 또는 포커스 아이콘 ![포커스 아이콘](./media/end-user-print/power-bi-focus-icon.png)을 선택하여 [포커스 모드에서 타일을 엽니다](end-user-focus.md).
   
    ![줄임표 메뉴](./media/end-user-print/power-bi-menu-options.png)

4. 타일을 마우스로 가리켜서 옵션 메뉴 표시
   
    ![전체 화면 옵션 메뉴](./media/end-user-print/menu-options-new.png)

4. 인쇄 아이콘을 선택합니다. ![인쇄 아이콘](./media/end-user-print/print-icon.png)을 탭합니다.     

5. 브라우저의 인쇄 창이 열립니다. 설정을 선택합니다. 예를 들어 타일이 페이지에 맞지 않는 경우 배율을 75%로 변경할 수 있습니다. **인쇄**를 선택합니다.

    ![인쇄 창](./media/end-user-print/power-bi-scale.png) 

> [!TIP]
> 이러한 단계를 모두 수행했는데도 타일이 원하는 방식으로 표시되지 않는 경우 다음을 시도해 보세요.
> 1. 인쇄 창을 열고 최상의 인쇄물을 생성할 것 같은 인쇄 설정으로 변경합니다. 예를 들어 레이아웃, 여백, 배율을 변경합니다. 
> 2. 그러나 인쇄하는 대신 **취소**를 선택합니다. 
> 3. 1~5단계를 다시 수행합니다. 타일이 새 인쇄 창 설정으로 조정되고 인쇄 준비가 됩니다.

## <a name="print-a-report-page"></a>보고서 페이지 인쇄
한 번에 한 페이지의 보고서를 인쇄할 수 있습니다.

1. 보고서를 열고 **내보내기** > **인쇄**를 선택하여 현재 보고서 페이지를 인쇄합니다.
   
    ![Power BI 파일 메뉴](./media/end-user-print/power-bi-report-print.png)
2. 브라우저의 인쇄 창이 열립니다.

3. 위 **대시보드 인쇄**의 인쇄 단계를 수행합니다.
   


## <a name="print-a-report-visual"></a>보고서 시각적 개체 인쇄
1. 타일 위로 마우스를 가져가고 오른쪽 위 모서리에서 포커스 아이콘 ![포커스 아이콘](./media/end-user-print/power-bi-focus-icon.png)을 선택하여 [시각적 개체를 포커스 모드에서 엽니다](end-user-focus.md).

2. 왼쪽 위 모서리에서 **내보내기** > **인쇄**를 선택하여 시각적 개체를 인쇄합니다.

    ![Power BI 파일 메뉴](./media/end-user-print/power-bi-report-print.png)


3. 위 **대시보드 인쇄**의 인쇄 단계를 수행합니다.

## <a name="considerations-and-troubleshooting"></a>고려 사항 및 문제 해결

* Q: 한 번에 모든 보고서 페이지를 인쇄할 수 없습니다.    
* A: 정상 동작입니다. 보고서 페이지는 한 번에 한 페이지만 인쇄할 수 있습니다.
* Q: PDF로 인쇄할 수 없습니다.    
* A: 이 옵션은 브라우저에서 PDF 드라이버를 구성한 경우에만 나타납니다.    
* Q: **인쇄**를 선택하면 표시되는 내용이 여기에 표시된 내용과 같지 않습니다.    
* A: 인쇄 화면은 브라우저 및 소프트웨어 버전에 따라 다릅니다.
* Q: 인쇄물의 크기가 올바르게 조정되지 않습니다.  내 대시보드가 페이지에 맞지 않습니다. 기타 크기 조정 및 방향 질문입니다.    
* A: 인쇄된 복사본이 Power BI 서비스에 표시되는 것과 정확히 동일하게 표시된다고 보장할 수는 없습니다. 크기 조정, 여백, 시각적 개체 세부 정보, 방향 및 크기와 같은 항목은 Power BI에서 제어되지 않습니다. 브라우저의 인쇄 설정을 조정해 보세요. 위에서 제안된 몇 가지 사항은 용지 방향(세로 또는 가로), 여백 크기, 배율입니다. 이 제안이 도움이 되지 않는 경우 해당 브라우저의 설명서를 참조하세요.      
* Q: 전체 화면 모드에서 인쇄하는 경우 시각적 개체를 마우스로 가리킬 때 인쇄 옵션이 표시되지 않습니다.   
* A: 기본 보기의 대시보드 또는 보고서로 돌아가서 시각적 개체를 포커스 모드, 전체 화면 모드로 차례로 다시 엽니다. 

## <a name="next-steps"></a>다음 단계
[동료 및 다른 사용자와 대시보드 및 보고서 공유](../service-share-dashboards.md)

궁금한 점이 더 있나요? [Power BI 커뮤니티를 이용하세요.](https://community.powerbi.com/)

