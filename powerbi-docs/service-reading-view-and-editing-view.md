---
title: "Power BI 서비스의 보고서 읽기용 보기 및 편집용 보기"
description: "Power BI 서비스 보고서의 읽기용 보기 및 편집용 보기 간 차이점에 대한 대략적 개요"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/08/2018
ms.author: mihart
ms.openlocfilehash: 6948f0e333ba1136f6fda8fa0f62b146cefdd710
ms.sourcegitcommit: d803e85bb0569f6b357ba0586f5702c20d27dac4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="reading-view-and-editing-view-in-power-bi-service-reports"></a>Power BI 서비스 보고서의 읽기용 보기 및 편집용 보기
Power BI 서비스(Power BI Desktop 아님)에는 보고서를 보고 상호 작용할 수 있는 읽기용 보기 및 편집용 보기라는 두 가지 모드가 있습니다. 읽기용 보기는 모든 사용자가 사용할 수 있으며 특히 데이터 *소비자*를 위해 설계되었지만 편집용 보기는 보고서 *작성자*와 소유자만 사용할 수 있습니다. 

![](media/service-reading-view-and-editing-view/power-bi-creators-consumers.png)

## <a name="report-reading-view"></a>보고서 읽기용 보기

 읽기용 보기는 보고서를 탐색하고 상호 작용할 수 있는 방법으로, 재미있고 안전하게 데이터를 사용하면서 파악할 수 있습니다. 읽기용 보기는 *소비자*를 위해 설계되었습니다. 이들은 앱에서 보고서를 열거나 [공유한](service-share-dashboards.md) 사람들을 말합니다. 읽기용 보기는 특정 보고서의 모든 소비자가 동일한 필터가 적용된 동일한 보고서, 동일한 시각화를 보도록 합니다.  소비자는 보고서와 상호 작용할 수 있지만 변경 내용을 저장할 수는 없습니다.

>**참고**: 상황에 따라 행 수준 보안 및 데이터 권한으로 인해 보고서 소비자가 다른 데이터를 볼 수 있습니다. 

## <a name="report-editing-view"></a>보고서 편집용 보기

편집용 보기는 보고서를 만든 사람이나 [앱 작업 영역의 구성원 또는 관리자로서 보고서를 공동 소유하는 사람](service-create-distribute-apps.md)만 사용할 수 있습니다.

편집용 보기는 보고서 *작성자*를 위한 것입니다. 이 보기에서 작성자는 데이터 집합을 가져와서 데이터 집합에 연결하고, 데이터를 탐색하고, 보고서 및 대시보드를 작성합니다. 편집용 보기에서 *작성자*는 필드를 추가 및 제거하고 시각화 유형을 변경하며 새 시각화를 만들고 보고서에서 시각화 및 페이지를 추가 및 삭제하는 등 데이터에 대한 작업을 훨씬 자세히 수행할 수 있습니다. 그런 다음 동료들과 만든 보고서를 공유할 수 있습니다.

## <a name="reading-view-versus-editing-view"></a>읽기용 보기 및 편집용 보기 비교
이 차트에서는 Power BI 서비스의 모든 보고서 기능을 나열하지 않습니다! 여기에는 읽기용 보기와 편집용 보기 **모두**에서 사용할 수 없는 보고서 작업만 나열됩니다. 


|작업  | 읽기용 보기  | 편집용 보기 |
|-------------------------|-------|-------|
|**보고서, 전체**  |
||||
| [보고서 만들기 또는 편집](service-report-create-new.md) | 아니요  | 예 |
| [보고서 공유](service-share-reports.md)| 예 | 예, 다른 사용자에게 *소유자* 권한을 부여하는 등 권한을 관리할 수도 있습니다. |
| [필터 창에서 영구적인(영구) 시각적 개체 수준, 드릴스루, 페이지 수준 및 보고서 수준 필터 만들기](power-bi-report-add-filter.md) | 아니요  | 예 |
| [보고서 필터 창 사용](power-bi-how-to-report-filter.md) | 예, 기존 필터를 사용할 수 있지만 변경 사항은 보고서에 저장되지 않습니다. | 예 |
| [보고서 분석 창 사용](service-analytics-pane.md) | 아니요 | 예 |
| [보고서 **보기** 옵션](power-bi-report-display-settings.md) | 예, 몇 가지 예외가 있습니다. | 예, 눈금선, 맞추기, 잠금 등 모두 가능합니다. |
| [새로 고침 일정 만들기](refresh-data.md) | 아니요  | 예 |
| [보고서 구독](service-report-subscribe.md) | 예 | 아니요 |
| [질문 및 답변 - 보고서에서 질문하기](power-bi-q-and-a.md) | 아니요  | 예 |
| [사용 메트릭 보기](service-usage-metrics.md) | 예, 보고서 캔버스에서 볼 수 있습니다. | 예, 보고서 목록(콘텐츠 보기)에서 볼 수 있습니다. |
| [관련 항목 보기](service-related-content.md) | 예, 보고서 캔버스에서 볼 수 있습니다. | 예, 보고서 목록(콘텐츠 보기)에서 볼 수 있습니다. |
| [보고서 저장](service-report-save.md) | 예, 하지만 **다른 이름으로 저장**을 사용한 경우만 가능합니다. | 예 |
| [보고서 삭제](service-delete.md) | 아니요  | 예 |
|**보고서 페이지** |
||||
| [보고서 페이지 추가 또는 이름 바꾸기](power-bi-report-add-page.md)  | 아니요  | 예  |
| [보고서 페이지 복제](power-bi-report-copy-paste-page.md) | 아니요  | 예 |
| [보고서 페이지 삭제](service-delete.md) | 아니요 | 예 |
|**보고서 시각화 작업**|
||||
| [보고서에 시각화 추가](power-bi-report-add-visualizations-i.md) | 아니요  | 예 |
| [보고서에 텍스트 상자 및 셰이프 추가](power-bi-reports-add-text-and-shapes.md) | 아니요  | 예 |
| [보고서 서식 창 사용](service-the-report-editor-take-a-tour.md) | 아니요 | 예 |
| [시각적 개체 상호 작용 설정](service-reports-visual-interactions.md) | 아니요  | 예 |
| [시각화를 만드는 데 사용된 데이터 표시](service-reports-show-data.md) | 아니요  | 예 |
| [드릴링 구성](power-bi-visualization-drill-down.md) | 아니요  | 예 |
| [사용되는 시각화 변경](power-bi-report-change-visualization-type.md) | 아니요 | 예|
| [시각화, 텍스트 상자 또는 셰이프 삭제](service-delete.md)| 아니요 | 예 |


## <a name="navigating-between-editing-view-and-reading-view"></a>편집용 보기 및 읽기용 보기 간 이동
보고서 작성자와 소유자만 편집용 보기에서 보고서를 열 수 있다는 점을 기억하세요.

1. 기본적으로 보고서는 보통 읽기용 보기에서 열립니다. **보고서 편집** 옵션이 보일 경우 읽기용 보기로 보고 있다는 의미입니다. **보고서 편집**이 회색으로 표시될 경우 편집용 보기에서 보고서를 열 권한이 없는 것입니다.

   ![](media/service-reading-view-and-editing-view/power-bi-edit-report-grey.png)

2. **보고서 편집**이 회색으로 표시되지 않을 경우 편집용 보기에서 보고서를 열도록 선택하세요. 
   
   ![](media/service-reading-view-and-editing-view/power-bi-edit-report.png)
   
   보고서가 편집용 보기 상태가 되며 읽기용 보기에서 마지막으로 사용한 것과 동일한 [표시 설정](power-bi-report-display-settings.md)을 사용합니다.

2. **읽기용 보기**로 돌아가려면 위쪽 탐색 모음에서 읽기용 보기를 선택합니다.
   
    ![](media/service-reading-view-and-editing-view/power-bi-reading-view.png)



### <a name="next-steps"></a>다음 단계
읽기용 보기에서 보고서와 상호 작용하는 방법은 여러 가지가 있으며 데이터 분리 및 결합하여 통찰력을 얻고 질문에 대한 답변을 얻을 수 있습니다.  다음 항목인 [읽기용 보기에서 보고서와 상호 작용](service-interact-with-a-report-in-editing-view.md)에서 이에 대해 보다 자세히 설명합니다.    
[Power BI의 보고서](service-reports.md)로 돌아가기    
궁금한 점이 더 있나요? [Power BI 커뮤니티를 이용하세요.](http://community.powerbi.com/) 

