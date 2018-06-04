---
title: Power BI 서비스의 대시보드 타일
description: Power BI의 대시보드 타일에 대한 모든 정보. SSRS(SQL Server Reporting Services)에서 만들어진 타일을 포함합니다.
author: mihart
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 03/02/2018
ms.author: mihart
LocalizationGroup: Dashboards
ms.openlocfilehash: e53945e0a112d9498dc6798e2441dd3d925a64c1
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34249071"
---
# <a name="dashboard-tiles-in-power-bi"></a>Power BI의 대시보드 타일
대시보드 및 대시보드 타일은 Power BI Desktop이 아닌 Power BI 서비스의 기능입니다. Power BI 모바일에서는 대시보드 타일을 만들거나 고정할 수 없지만 [보고 공유](mobile-tiles-in-the-mobile-apps.md)할 수는 있습니다. 또한 Power BI 모바일에서는 [iPhone 앱으로 대시보드에 그림을 추가](mobile-iphone-app-get-started.md)할 수 있습니다.

## <a name="dashboard-tiles"></a>대시보드 타일
![Power BI 대시보드](media/service-dashboard-tiles/power-bi-dashboard.png)

타일은 대시보드에 고정된 데이터에 대한 스냅숏입니다. 타일은 보고서, 데이터 집합, 대시보드, 질문 및 답변 상자, Excel 및 SSRS(SQL Server Reporting Services) 등에서 만들 수 있습니다.  이 스크린샷은 대시보드에 고정된 여러 타일을 보여 줍니다.

고정 외에도 [타일 추가](service-dashboard-add-widget.md)를 사용하여 대시보드에서 독립 실행형 타일을 직접 만들 수 있습니다. 독립 실행형 타일에는 텍스트 상자, 이미지, 동영상, 스트리밍 데이터 및 웹 콘텐츠가 포함됩니다.

Power BI의 구성 요소를 이해하는 데 도움이 필요한 경우  [Power BI - 기본 개념](service-basic-concepts.md)을 참조하세요.

> [!NOTE]
> 원래 시각화를 사용하여 타일을 변경한 경우 타일이 변경되지 않습니다.  예를 들어 보고서에서 꺾은선형 차트를 고정한 다음 꺾은선형 차트를 막대형 차트로 변경하면 대시보드 타일에 꺾은선형 차트가 계속 표시됩니다. 데이터는 새로 고쳐지지만 시각화 유형은 새로 고쳐지지 않습니다.
> 
> 

## <a name="pin-a-tile-from"></a>다음에서 타일 고정...
다양한 방법으로 대시보드에 타일을 추가(고정)할 수 있습니다. 다음에서 타일을 고정할 수 있습니다.

* [Power BI 질문 및 답변](service-dashboard-pin-tile-from-q-and-a.md)
* [보고서](service-dashboard-pin-tile-from-report.md)
* [다른 대시보드](service-pin-tile-to-another-dashboard.md)
* [비즈니스용 OneDrive의 Excel 통합 문서](service-dashboard-pin-tile-from-excel.md)
* [Power BI Publisher for Excel](publisher-for-excel.md)
* [신속한 정보 활용](service-insights.md)
* [SSRS](https://msdn.microsoft.com/library/mt604784.aspx)

[타일 추가](service-dashboard-add-widget.md)를 사용하여 대시보드에서 이미지, 텍스트 상자, 동영상, 스트리밍 데이터 및 웹 콘텐츠에 대한 독립 실행형 타일을 직접 만들 수 있습니다.

  ![타일 추가 아이콘](media/service-dashboard-tiles/add_widgetnew.png)

## <a name="interacting-with-tiles-on-a-dashboard"></a>대시보드에서 타일 조작
### <a name="move-and-resize-a-tile"></a>타일 이동 및 크기 조정
타일을 선택하고 [대시보드 내에서 이동](service-dashboard-edit-tile.md)합니다. 핸들 ![핸들](media/service-dashboard-tiles/resize-handle.jpg)을 가리키고 선택하여 타일 크기를 조정합니다.

### <a name="hover-over-a-tile-to-change-the-appearance-and-behavior"></a>타일을 가리켜서 모양 및 동작을 변경합니다.
1. 타일을 가리켜서 줄임표을 표시합니다.
   
    ![타일 줄임표](media/service-dashboard-tiles/ellipses_new.png)
2. 줄임표를 선택하여 타일 동작 메뉴를 엽니다.
   
    ![줄임표 아이콘](media/service-dashboard-tiles/power-bi-tile-menu.png)
   
    여기에서 다음과 같은 작업을 할 수 있습니다.
   
   * [이 타일을 만드는 데 사용된 보고서 열기](service-reports.md) ![보고서 아이콘](media/service-dashboard-tiles/chart-icon.jpg)  
   
   * [이 타일을 만드는 데 사용된 워크시트 열기](service-reports.md) ![워크시트 아이콘](media/service-dashboard-tiles/power-bi-open-worksheet.png)  
     
     * [포커스 모드로 보기](service-focus-mode.md) ![포커스 아이콘](media/service-dashboard-tiles/fullscreen-icon.jpg)  
     * [타일에 사용된 데이터 내보내기](power-bi-visualization-export-data.md) ![데이터 내보내기 아이콘](media/service-dashboard-tiles/export-icon.png)
     * [제목 및 부제목 편집, 하이퍼링크 추가 및 마지막 새로 고침 시간 표시](service-dashboard-edit-tile.md) ![편집 아이콘](media/service-dashboard-tiles/pencil-icon.jpg)
     * [정보 실행](service-insights.md) ![정보 아이콘](media/service-dashboard-tiles/power-bi-insights.png)
     * [타일을 다른 대시보드에 고정](service-pin-tile-to-another-dashboard.md)
       ![고정 아이콘](media/service-dashboard-tiles/pin-icon.jpg)
     * [타일 제거](service-dashboard-edit-tile.md)
     ![삭제 아이콘](media/service-dashboard-tiles/trash-icon.png)
3. 동작 메뉴를 닫으려면 캔버스의 빈 영역을 선택합니다.

### <a name="select-click-a-tile"></a>타일 선택(클릭)
타일을 선택하는 경우 다음 작업은 타일을 만든 방법 및 타일에 [사용자 지정 링크](service-dashboard-edit-tile.md)가 있는지 여부에 따라 달라집니다. 사용자 지정 링크가 있는 경우 타일을 선택하면 해당 링크로 이동합니다. 링크가 없는 경우 타일을 선택하면 타일을 만드는 데 사용되는 보고서, Excel Online 통합 문서, 온-프레미스인 SSRS 보고서 또는 질문 및 답변의 질문으로 이동됩니다.

> [!NOTE]
> 이 동작의 예외는 **타일 추가**를 사용하여 대시보드에 직접 만든 동영상 타일입니다. 이러한 방식으로 만든 동영상 타일을 선택하면 동영상이 대시보드에서 바로 재생됩니다.   
> 
> 

## <a name="considerations-and-troubleshooting"></a>고려 사항 및 문제 해결
* 시각화를 만드는 데 사용된 보고서를 저장하지 않은 경우 타일을 선택해도 어떤 동작도 수행되지 않습니다.
* 타일이 Excel Online의 통합 문서에서 만들어졌으며 해당 통합 문서에 대한 권한이 읽기 권한보다 낮은 경우 타일을 선택해도 Excel Online에서 통합 문서가 열리지 않습니다.
* **타일 추가**를 사용하여 대시보드에서 직접 만든 파일에서는, 사용자 지정 하이퍼링크가 설정된 경우 제목, 부제목 및/또는 타일을 선택하면 해당 URL이 열립니다.  그렇지 않은 경우 이미지, 웹 코드 또는 텍스트 상자에 대한 대시보드에서 직접 만든 다음 타일 중 하나를 선택하면 기본적으로 동작을 생성하지 않습니다.
* SSRS 내의 보고서에 대한 권한이 없는 경우 SSRS에서 만든 타일을 선택하면 액세스가 없음을 나타내는 페이지를 생성합니다(rsAccessDenied).
* SSRS 서버가 있는 네트워크에 대한 액세스가 없는 경우 SSRS에서 만든 타일을 선택하면 서버를 찾을 수 없음을 나타내는 페이지를 만듭니다(HTTP 404). 장치에서 보고서를 보려면 보고서 서버에 대한 네트워크 액세스가 있어야 합니다.
* 원래 시각화를 사용하여 타일을 변경한 경우 타일이 변경되지 않습니다.  예를 들어 보고서에서 꺾은선형 차트를 고정한 다음 꺾은선형 차트를 막대형 차트로 변경하면 대시보드 타일에 꺾은선형 차트가 계속 표시됩니다. 데이터는 새로 고쳐지지만 시각화 유형은 새로 고쳐지지 않습니다.

## <a name="next-steps"></a>다음 단계
[대시보드에 대한 카드(큰 숫자 타일) 만들기](power-bi-visualization-card.md)

[Power BI의 대시보드](service-dashboards.md)  

[데이터 새로 고침](refresh-data.md)

[Power BI - 기본 개념](service-basic-concepts.md)

[Power Point로 타일 내보내기](http://blogs.msdn.com/b/powerbidev/archive/2015/09/28/integrating-power-bi-tiles-into-office-documents.aspx)

[Power BI 대시보드에에 Reporting Services 항목 고정](https://msdn.microsoft.com/library/mt604784.aspx)

궁금한 점이 더 있나요? [Power BI 커뮤니티를 이용하세요.](http://community.powerbi.com/)

