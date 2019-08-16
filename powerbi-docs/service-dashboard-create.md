---
title: 보고서에서 Power BI 대시보드 만들기
description: 보고서에서 Power BI 대시보드 만들기
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 07/17/2019
ms.author: maggies
ms.openlocfilehash: b50d247f54cfe2af4cefbd14b9528b1dfa263acf
ms.sourcegitcommit: bc688fab9288ab68eaa9f54b9b59cacfdf47aa2e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2019
ms.locfileid: "68624264"
---
# <a name="create-a-power-bi-dashboard-from-a-report"></a>보고서에서 Power BI 대시보드 만들기
지금까지 [Power BI의 대시보드 소개](service-dashboards.md)에 대해 살펴보았으며 이제 직접 만들려고 합니다. 다양한 방법으로 대시보드를 만들 수 있습니다. 예를 들어 보고서의 데이터 세트에서 처음부터 또는 기존 대시보드를 복제하여 대시보드를 만들 수 있습니다.  

처음 시작할 때에는 부담스러울 수 있으므로, 이미 빌드된 보고서에서 시각적 개체를 고정하는 쉽고 빠르게 대시보드를 만들어 시작합니다. 

이 빠른 시작을 완료한 후에는 다음을 이해하는 것이 좋습니다.
- 대시보드와 보고서 간의 관계
- 보고서 편집기에서 편집용 보기를 여는 방법
- 타일을 고정하는 방법 
- 대시보드와 보고서 간에 이동하는 방법 

## <a name="who-can-create-a-dashboard"></a>대시보드는 누가 만들 수 있나요?
대시보드를 만드는 기능은 *작성자* 기능으로 간주되며 보고서에 대한 편집 권한이 필요합니다. 편집 권한은 보고서 작성자와 작성자가 액세스 권한을 부여하는 동료들에게 제공됩니다. 예를 들어 David가 workspaceABC에서 보고서를 만들고 해당 작업 영역의 구성원으로 사용자를 추가하는 경우, David와 사용자는 둘 다 편집 권한이 있습니다. 반면, 보고서가 사용자와 직접 공유되거나 [Power BI 앱](service-create-distribute-apps.md)의 일부로서 공유되는 경우(사용자가 보고서를 *소비*하는 경우) 사용자는 대시보드에 타일을 고정할 수 없습니다.
 
![대시보드](media/service-dashboard-create/power-bi-completed-dashboard-small.png)

> [!NOTE] 
> 대시보드는 Power BI Desktop이 아닌 Power BI 서비스의 기능입니다. Power BI 모바일에서는 대시보드를 만들 수 없지만 [보고 공유](consumer/mobile/mobile-apps-view-dashboard.md)할 수는 있습니다.
>
> 

## <a name="video-create-a-dashboard-by-pinning-visuals-and-images-from-a-report"></a>비디오: 보고서에서 시각적 개체 및 이미지를 고정하여 대시보드를 만듭니다.
Amanda가 보고서에서 시각화를 핀 고정하여 새 대시보드를 만드는 과정을 시청합니다. 그런 다음 [보고서와 함께 데이터 세트 가져오기](#import-a-dataset-with-a-report)의 단계를 따라 조달 분석 샘플을 사용하여 직접 시도해 보세요.
    

<iframe width="560" height="315" src="https://www.youtube.com/embed/lJKgWnvl6bQ" frameborder="0" allowfullscreen></iframe>

## <a name="import-a-dataset-with-a-report"></a>보고서로 데이터 세트 가져오기
Power BI 샘플 데이터 세트 중 하나를 가져오고 이를 사용하여 새 대시보드를 만듭니다. 사용할 샘플은 두 개의 PowerView 시트가 있는 Excel 통합 문서입니다. Power BI에서 통합 문서를 가져오면 데이터 세트와 보고서를 작업 영역에 추가합니다. 보고서는 PowerView 시트에서 자동으로 생성됩니다.

1. 조달 분석 샘플 [Excel 파일](http://go.microsoft.com/fwlink/?LinkId=529784)을 다운로드합니다. 비즈니스용 OneDrive에 파일을 저장하는 것이 좋습니다.
2. 브라우저에서 Power BI 서비스(app.powerbi.com)를 엽니다.
3. 왼쪽 탐색 창에서 **내 작업 영역**을 선택하고 **데이터 가져오기**를 선택합니다.

    ![왼쪽 탐색 창](media/service-dashboard-create/power-bi-get-data3.png)
5. **파일**을 선택합니다.

   ![파일 가져오기](media/service-dashboard-create/power-bi-select-files.png)
6. 조달 분석 샘플 Excel 파일을 저장한 위치로 이동합니다. 이를 선택하고 **연결**을 선택합니다.

   ![파일에 연결](media/service-dashboard-create/power-bi-connectnew.png)
7. 이 연습에서는 **가져오기**를 선택합니다.

    ![비즈니스용 OneDrive 창](media/service-dashboard-create/power-bi-import.png)
8. 성공 메시지가 나타나면 **x**를 선택하여 해제합니다.

   ![성공 메시지](media/service-dashboard-create/power-bi-view-datasetnew.png)

### <a name="open-the-report-and-pin-tiles-to-your-dashboard"></a>보고서를 열고 타일을 대시보드에 고정
1. 동일한 작업 영역에서 **보고서** 탭을 선택한 다음 **조달 분석 샘플**을 선택하여 보고서를 엽니다.

    ![보고서 탭](media/service-dashboard-create/power-bi-reports.png) 보고서가 읽기용 보기에 열립니다. 아래쪽에 다음 두 탭이 있습니다. **할인 분석** 및 **지출 개요**. 각 탭은 보고서의 페이지를 나타냅니다.

2. **보고서 편집**을 선택하여 편집용 보기에서 보고서를 엽니다.

    ![읽기용 보기의 보고서](media/service-dashboard-create/power-bi-reading-view.png)
3. 시각화 위로 마우스를 가져 가면 사용할 수 있는 옵션이 표시됩니다. 시각적 개체를 대시보드에 추가하려면 고정 아이콘 선택 ![고정 아이콘](media/service-dashboard-create/power-bi-pin-icon.png)을 선택합니다.

    ![타일을 마우스로 가리키기](media/service-dashboard-create/power-bi-hover.png)
4. 새 대시보드를 만들고 있으므로 **새 대시보드**에 대한 옵션을 선택하고 이름을 지정합니다.

    ![대시보드에 고정 대화 상자](media/service-dashboard-create/power-bi-pin-tile.png)
5. **핀 고정**을 선택하면, Power BI에서 현재 작업 영역에 새 대시보드를 만듭니다. **대시보드에 고정됨** 메시지가 나타나면 **대시보드로 이동**을 선택합니다. 보고서를 저장할지 묻는 메시지가 표시되면 **저장**을 선택합니다.

    ![성공 메시지](media/service-dashboard-create/power-bi-pin-success.png)

    Power BI에서 새 대시보드를 엽니다. 여기에는 방금 고정한 시각적 개체인 타일이 하나 있습니다.

   ![하나의 타일이 포함된 대시보드](media/service-dashboard-create/power-bi-pinned.png)
7. 보고서로 돌아가려면 타일을 선택합니다. 새 대시보드에 몇 개 타일을 고정합니다. **대시보드에 고정** 창이 표시될 때 **기존 대시보드**를 선택합니다.  

   ![대시보드에 고정 대화 상자](media/service-dashboard-create/power-bi-existing-dashboard.png)

## <a name="pin-an-entire-report-page-to-the-dashboard"></a>전체 보고서 페이지를 대시보드에 고정
시각적 개체를 한 번에 하나씩 고정하는 대신, [전체 보고서 페이지를 ‘라이브 타일’로 고정할 수 있습니다](service-dashboard-pin-live-tile-from-report.md).  이를 수행해 보겠습니다.

1. 보고서 편집기에서 **지출 개요** 탭을 선택하여 보고서의 두 번째 페이지를 엽니다.

   ![보고서 탭](media/service-dashboard-create/power-bi-page-tab.png)

2. 대시보드에서 보고서의 모든 시각적 개체를 표시합니다. 메뉴 모음의 오른쪽 위 모서리에서 **라이브 고정 페이지**를 선택합니다. 대시보드에서 페이지를 새로 고칠 때마다 라이브 페이지 타일이 업데이트됩니다.

   ![보고서 편집기의 오른쪽 위](media/service-dashboard-create/power-bi-pin-live.png)

3. **대시보드에 고정** 창이 표시될 때 **기존 대시보드**를 선택합니다.

   ![대시보드에 고정 대화 상자](media/service-dashboard-create/power-bi-pin-live2.png)

4. [성공] 메시지가 나타나면 **대시보드로 이동**을 선택합니다. 보고서에서 고정한 타일이 표시됩니다. 아래 예에서는 보고서의 1페이지에서 타일을 2개 고정하고 보고서의 2페이지에 있는 라이브 타일을 하나 고정했습니다.

   ![대시보드](media/service-dashboard-create/power-bi-dashboard.png)

## <a name="next-steps"></a>다음 단계
축하합니다. 첫 번째 대시보드를 만들었습니다! 이제 대시보드가 있으며 훨씬 많은 작업을 수행할 수 있습니다. 아래 제안된 문서 중 하나를 수행하거나 직접 살펴봅니다. 

* [타일 크기 조정 및 이동](service-dashboard-edit-tile.md)
* [대시보드 타일에 대한 모든 정보](service-dashboard-tiles.md)
* [앱을 만들어 대시보드 공유](service-create-workspaces.md)
* [Power BI - 기본 개념](service-basic-concepts.md)
* [멋진 대시보드를 디자인하기 위한 팁](service-dashboards-design-tips.md)

궁금한 점이 더 있나요? [Power BI 커뮤니티를 이용](http://community.powerbi.com/)하세요.
