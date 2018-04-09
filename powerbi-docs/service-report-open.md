---
title: Power BI 서비스에서 읽기용 보기 또는 편집용 보기로 보고서 열기
description: 읽기용 보기 또는 편집용 보기로 Power BI 보고서 열기
services: powerbi
documentationcenter: ''
author: mihart
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 03/01/2018
ms.author: mihart
ms.openlocfilehash: 17921d1fe28a1b4c0640748123efe4b70982b18d
ms.sourcegitcommit: afa10c016433cf72d6d366c024b862187a8692fd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/04/2018
---
# <a name="open-a-report-in-power-bi-service-apppowerbicom"></a>Power BI 서비스에서 보고서 열기(app.powerbi.com)
보고서는 Power BI 서비스, Power BI Desktop, Power BI 모바일 및 Power BI Embedded에서도 사용할 수 있습니다. 이 문서는 ***Power BI 서비스***의 보고서를 여는 데 적용됩니다.

Power BI 서비스에는 보고서를 보고 상호 작용할 수 있는 [읽기용 보기 및 편집용 보기](service-reading-view-and-editing-view.md)라는 두 가지 모드가 있습니다. 읽기용 보기는 모든 사용자가 사용할 수 있으며 특히 보고서 *소비자*를 위해 설계되었지만 편집용 보기는 보고서 *작성자*와 소유자만 사용할 수 있습니다. 

## <a name="open-a-report-from-a-workspace-via-the-reports-content-view-list"></a>**보고서** 콘텐츠 보기 목록을 통해 작업 영역에서 보고서 열기

1. 작업 영역에서 시작하고 **보고서** 탭을 선택하여 해당 작업 영역에 모든 보고서를 표시합니다.  
   
   ![작업 영역의 보고서 탭](media/service-report-open/power-bi-open-report.png)
2. 보고서 이름을 선택하여 읽기용 보기에서 엽니다.  
   
    ![읽기용 보기의 보고서](media/service-report-open/power-bi-reading-view.png)
3. [읽기용 보기에서는 수많은 작업을 수행할 수 있습니다](service-reading-view-and-editing-view.md).  이 샘플 보고서에는 여러 페이지에 있기 때문에 보고서 캔버스의 맨 아래에 각 탭을 선택하여 탐색을 시작합니다. 

## <a name="open-a-report-from-a-dashboard"></a>대시보드에서 보고서 열기
대시보드에서 시작하고 보고서에서 생성된 타일을 선택하는 등, 여러 다양한 방법으로 보고서를 열 수 있습니다.  타일을 선택하면 보고서가 읽기용 보기에서 열립니다. 이를 수행하려면 [영업 및 마케팅 샘플 대시보드를 여세요](sample-datasets.md).

1. 대시보드를 열고 타일을 선택합니다.

   [질문 및 답변으로 작성한](service-dashboard-pin-tile-from-q-and-a.md) 타일을 선택하면 질문 및 답변 화면이 열립니다. [대시보드 **타일 추가** 위젯을 사용하여 만든](service-dashboard-add-widget.md) 타일을 선택하면 마법사를 열어 해당 위젯을 편집하게 됩니다.  

2.  이 예에서는 "총 단위 YTD..." 열 차트 타일을 선택했습니다.

    ![타일을 선택한 대시보드](media/service-report-open/power-bi-dashboard.png)

3.  연결된 보고서는 읽기용 보기로 열립니다. "YTD 범주" 페이지에 있는지 확인합니다. 이는 대시보드에서 선택한 열 차트가 포함된 보고서 페이지입니다.

    ![읽기용 보기로 보고서 열기](media/service-report-open/power-bi-report.png)

4. 읽기용 보기를 유지하거나 **보고서 편집**을 선택하여 편집용 보기에서 보고서를 엽니다. 해당 보고서에 대한 편집 권한이 있는 사용자만 편집용 보기에서 열 수 있습니다.

    ![보고서 편집 아이콘을 보여주는 보고서 편집기](media/service-report-open/power-bi-edit-report.png)

## <a name="create-a-brand-new-report-from-a-dataset"></a>데이터 집합에서 새 보고서 만들기
보고서를 여는 또 하나의 방법은 데이터 집합에서 여는 것입니다. 데이터 집합에서 시작하면 보고서 캔버스가 비어 있기 때문에, 이 메서드는 자신이 소유한 데이터 집합을 기반으로 새 보고서를 만드는 데 관심이 있는 보고서 *작성자*에게 권장됩니다. 위의 예와 같이 수행하려면 [영업 및 마케팅 샘플 앱](sample-datasets.md)을 다운로드하세요.

1. 보고서의 기초로 사용할 데이터 집합이 포함된 작업 영역에서 시작합니다.

   ![앱 작업 영역을 표시하는 왼쪽 탐색 창](media/service-report-open/power-bi-workspace.png)

2. 해당 작업 공간의 모든 데이터 집합 목록을 표시하려면 **데이터 집합** 탭을 선택합니다. 이를 **데이터 집합** 콘텐츠 뷰 목록이라고 합니다.
   
   ![데이터 집합 목록](media/service-report-open/power-bi-dataset.png)

1. 데이터 집합을 찾아 **보고서 만들기** 아이콘을 선택하여 편집용 보기에서 데이터 집합을 엽니다. 데이터 집합에 대한 편집 권한이 없는 경우 데이터 세트를 열 수 없습니다. 
   
    ![보고서 만들기 아이콘이 포함된 데이터 집합](media/service-report-open/power-bi-create-report.png)

3. 데이터 집합은 보고서 편집기에서 열립니다. 오른쪽에서 데이터 필드가 표시된 것을 볼 수 있으며, 시각화 탐색 및 만들기가 시작될 때까지 기다립니다. 

   ![보고서 캔버스](media/service-report-open/power-bi-blank-canvas.png)

##  <a name="still-more-ways-to-open-a-report"></a>보고서를 열 수 있는 기타 방법
Power BI 서비스를 보다 편리하게 탐색할 수 있기 때문에 자신에게 가장 적합한 워크플로를 찾을 수 있습니다. 보고서에 액세스하는 몇 가지 다른 방법:
- 왼쪽 탐색 창에서 **즐겨찾기**, **최근**, **앱** 및 **공유한 항목** 사용 
- [관련 항목 보기](service-related-content.md) 사용
- 누군가가 [사용자와 공유](service-share-reports.md)하거나 [경고를 설정](service-set-data-alerts.md)할 때 전자 메일을 통해    
- [알림 센터](service-notification-center.md)를 통해    
- 기타

## <a name="next-steps"></a>다음 단계
[Power BI의 보고서](service-reports.md)에 대해 자세히 알아보기

궁금한 점이 더 있나요? [Power BI 커뮤니티를 이용하세요.](http://community.powerbi.com/)  

