---
title: "Power BI Desktop 파일에서 데이터 가져오기"
description: "Power BI Desktop에서 Power BI로 데이터 및 보고서를 가져오는 방법 알아보기"
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: complete
qualitydate: 03/30/2016
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/06/2017
ms.author: davidi
ms.openlocfilehash: d2d909f9f991f4abedeaee598820cac659bc9567
ms.sourcegitcommit: d91436de68a0e833ecff18d976de9d9431bc4121
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/06/2017
---
# <a name="get-data-from-power-bi-desktop-files"></a>Power BI Desktop 파일에서 데이터 가져오기
![](media/service-desktop-files/pbid_file_icon.png)

**Power BI Desktop**은 비즈니스 인텔리전스 및 보고서를 쉽게 만듭니다. 다양한 데이터 원본에 연결하든, 데이터를 쿼리하고 변환하든, 데이터를 모델링하든, 강력하고 동적인 보고서를 작성하든 관계없이 **Power BI Desktop**은 비즈니스 인텔리전스 작업을 직관적이고 신속하게 만듭니다. **Power BI Desktop**에 익숙하지 않은 경우 [Power BI Desktop 시작](desktop-getting-started.md)을 참조합니다.

일부 데이터를 **Power BI Desktop**으로 가져오고 몇 개의 보고서를 만들었다면 이제 저장된 파일을 **Power BI 서비스**로 가져올 순서입니다.

## <a name="where-your-file-is-saved-makes-a-difference"></a>파일 저장 위치는 중요합니다.
**로컬** - 파일을 사용자 컴퓨터의 로컬 드라이브 또는 조직의 다른 위치에 저장하는 경우 Power BI Desktop에서 파일을 *가져오거나* *게시*하여 데이터와 보고서를 Power BI로 가져올 수 있습니다. 파일은 사실 로컬 드라이브에 그대로 남아 있으므로, 전체 파일을 실제로 Power BI로 가져온 것은 아닙니다. 실제로는, 새 데이터 집합이 Power BI에서 만들어지고 Power BI Desktop 파일의 데이터와 데이터 모델이 데이터 집합으로 로드되는 것입니다. 파일에 보고서가 있을 경우 Power BI의 보고서에 나타납니다.

**OneDrive - 비즈니스** – 비즈니스용 OneDrive가 있고 Power BI에 로그인하는 같은 계정으로 로그인할 경우 Power BI Desktop의 작업과 Power BI의 데이터 집합, 보고서 그리고 대시보드의 동기화를 유지하는 가장 효율적인 방법입니다. Power BI와 OneDrive가 클라우드에 있으므로 Power BI는 매시간 OneDrive의 파일에 *연결*합니다. 변경 내용이 발견되면 데이터 집합, 보고서 및 대시보드가 Power BI에서 자동으로 업데이트됩니다.

**OneDrive - 개인** – 본인의 OneDrive 계정으로 파일을 저장할 경우 비즈니스용 OneDrive에 제공하는 것과 동일한 많은 혜택을 누릴 수 있습니다. 가장 큰 차이점은 파일에 처음 연결할 때(‘데이터 가져오기’ > ‘파일’ > ‘OneDrive - 개인’ 사용) Microsoft 계정으로 OneDrive에 로그인해야 한다는 점이 가장 큰 차이점이며, 일반적으로 Power BI에 로그인하기 위해 사용하는 것과는 다릅니다. Microsoft 계정으로 OneDrive에 로그인할 경우 로그인 유지 옵션을 선택해야 합니다. 이러한 방식으로 Power BI는 매시간 파일에 연결할 수 있으며 Power BI의 데이터 집합은 동기화를 유지하게 됩니다.

**SharePoint 팀 사이트** – Power BI Desktop 파일을 SharePoint 팀 사이트에 저장하는 것은 비즈니스용 OneDrive에 저장하는 것과 상당히 같습니다. 가장 큰 차이점은 Power BI에서 파일에 연결하는 방법입니다. URL을 지정하거나 루트 폴더에 연결할 수 있습니다.

## <a name="import-or-connect-to-a-power-bi-desktop-file-from-power-bi"></a>Power BI에서 Power BI Desktop 파일 가져오기 또는 연결
>[!IMPORTANT]
>Power BI로 가져올 수는 최대 파일 크기는 1GB입니다.

1. Power BI의 탐색 창에서 **데이터 가져오기**를 클릭합니다.
   
   ![](media/service-desktop-files/pbid_get_data_button.png)
2. **파일**에서 **가져오기**를 클릭합니다.
   
   ![](media/service-desktop-files/pbid_files_get.png)
3. 파일을 찾습니다. Power BI Desktop 파일의 확장명은 .PBIX입니다.
   
   ![](media/service-desktop-files/pbid_find_your_file.png)

## <a name="publish-a-file-from-power-bi-desktop-to-your-power-bi-site"></a>Power BI Desktop에서 Power BI 사이트로 파일 게시
Power BI Desktop에서 게시를 사용하는 것은 로컬 드라이브에서 파일을 가져오기 위해 Power BI에서 데이터 가져오기를 사용하거나 OneDrive에서 연결하는 것과 사실상 같습니다.  여기에 빠른 사용 방법이 나와 있지만 자세히 알아보려면 [Power BI Desktop에서 게시](desktop-upload-desktop-files.md)를 참조하세요.

1. Power BI Desktop에서 **파일** > **게시** > **Power BI에 게시** 또는 리본에서 **게시**를 클릭합니다.
   
   ![](media/service-desktop-files/pbid_publish.png)
2. Power BI에 로그인합니다. 이 작업은 처음에만 수행해야 합니다.
   
   완료되면 Power BI 사이트에서 보고서를 열기 위한 링크를 얻게 됩니다.
   
   ![](media/service-desktop-files/pbid_publishing.png)

## <a name="next-steps"></a>다음 단계
**데이터 탐색** - 파일에서 Power BI로 데이터 및 보고서를 가져오면 이제 살펴볼 차례입니다. 파일에 이미 보고서가 있다면 탐색 창의 **보고서**에 나타납니다. 파일에 데이터가 있다면 새 보고서를 만들 수 있습니다. 새 데이터 집합을 마우스 오른쪽 단추로 클릭한 다음 **탐색**을 클릭합니다.

**외부 데이터 원본 새로 고침** - Power BI Desktop 파일이 외부 데이터 원본에 연결할 경우 데이터 집합이 항상 최신 상태를 유지하도록 예약된 새로 고침을 설정할 수 있습니다. 대부분의 경우에 예약된 새로 고침을 설정하는 방법은 아주 쉽지만 이 문서에서는 자세히 다루지 않겠습니다. 자세한 내용은 [Power BI에서 데이터 새로 고침](refresh-data.md)을 참조하세요.

