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
ms.date: 12/21/2017
ms.author: mihart
ms.openlocfilehash: 7c0c09bd04eac31bac00e4562853c99befe9715f
ms.sourcegitcommit: 6ea8291cbfcb7847a8d7bc4e2b6abce7eddcd0ea
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="reading-view-and-editing-view-in-power-bi-service-reports"></a>Power BI 서비스 보고서의 읽기용 보기 및 편집용 보기
Power BI 서비스(Power BI Desktop 아님)에는 보고서를 보고 상호 작용할 수 있는 읽기용 보기 및 편집용 보기라는 두 가지 모드가 있습니다.  

읽기용 보기는 모든 사용자가 사용할 수 있지만 편집용 보기는 보고서 작성자와 소유자만 사용할 수 있습니다. 읽기용 보기는 *소비자*를 위해 설계되었습니다. 이들은 앱에서 보고서를 열거나 공유한 동료를 말합니다. 읽기용 보기는 특정 보고서의 모든 소비자가 동일한 필터가 적용된 동일한 보고서, 동일한 시각화를 보도록 합니다.  소비자는 보고서와 상호 작용할 수 있지만 변경 내용을 저장할 수는 없습니다.

>**참고**: 상황에 따라 행 수준 보안 및 데이터 권한으로 인해 보고서 소비자가 다른 데이터를 볼 수 있습니다. 

편집용 보기는 보고서를 만든 사람이나 앱 작업 영역의 구성원 또는 관리자로서 보고서를 공동 소유하는 사람만 사용할 수 있습니다.

## <a name="reading-view"></a>읽기용 보기

읽기용 보기는 데이터를 다루고 알아가는 데 있어서 재미있고 안전한 방법입니다. 읽기용 보기는 [편집용 보기](service-interact-with-a-report-in-editing-view.md)만큼 대화형은 아니지만 데이터를 조사하기 위한 여러 가지 옵션을 제공합니다. 읽기용 보기에서만 열 수 있는 [사용자와 공유된](service-share-dashboards.md) 보고서 등을 볼 때 유용합니다.

자세히 알아보려면 [Power BI 보고서의 읽기용 보기](service-interact-with-a-report-in-reading-view.md)를 참조하세요.

## <a name="editing-view"></a>편집용 보기
Power BI의 편집용 보기에서는 필드를 추가 및 제거하고 시각화 유형을 변경하며 새 시각화를 만들고 보고서에서 시각화 및 페이지를 추가 및 삭제하여 [읽기용 보기](service-interact-with-a-report-in-reading-view.md)에 비해 데이터에 대한 작업을 훨씬 자세히 수행할 수 있습니다.

자세히 알아보려면 [Power BI 보고서의 편집용 보기](service-interact-with-a-report-in-editing-view.md)를 참조하세요.

## <a name="navigating-between-editing-view-and-reading-view"></a>편집용 보기 및 읽기용 보기 간 이동
보고서 작성자와 소유자만 편집용 보기에서 보고서를 열 수 있다는 사실을 기억하세요.

1. 기본적으로 보고서는 보통 읽기용 보기에서 열립니다. **보고서 편집** 옵션이 보일 경우 읽기용 보기로 보고 있다는 의미입니다. **보고서 편집**이 회색으로 표시될 경우 편집용 보기에서 보고서를 열 권한이 없는 것입니다.

   ![](media/service-reading-view-and-editing-view/power-bi-edit-report-grey.png)

2. **보고서 편집**이 회색으로 표시되지 않을 경우 편집용 보기에서 보고서를 열도록 선택하세요. 
   
   ![](media/service-reading-view-and-editing-view/power-bi-edit-report.png)
   
   보고서가 편집용 보기 상태가 되며 읽기용 보기에서 마지막으로 사용한 것과 동일한 [표시 설정](power-bi-report-display-settings.md)을 사용합니다.

2. **읽기용 보기**로 돌아가려면 위쪽 탐색 모음에서 읽기용 보기를 선택합니다.
   
    ![](media/service-reading-view-and-editing-view/power-bi-reading-view.png)

읽기용 보기에서 보고서와 상호 작용하는 방법은 여러 가지가 있으며 데이터 분리 및 결합하여 통찰력을 얻고 질문에 대한 답변을 얻을 수 있습니다.  다음 항목인 [읽기용 보기에서 보고서와 상호 작용](service-interact-with-a-report-in-editing-view.md)에서 이에 대해 나열하고 보다 자세히 설명합니다.

### <a name="next-steps"></a>다음 단계
[읽기용 보기에서 보고서와 상호 작용](service-interact-with-a-report-in-editing-view.md)    
[Power BI의 보고서](service-reports.md)로 돌아가기    
궁금한 점이 더 있나요? [Power BI 커뮤니티를 이용하세요.](http://community.powerbi.com/) 

