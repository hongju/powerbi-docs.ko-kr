---
title: Power BI Desktop에서 게시
description: Power BI Desktop에서 게시
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: f67f73dd66da7f1d3e8d84a3373a15d20f81645e
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "65513814"
---
# <a name="publish-from-power-bi-desktop"></a>Power BI Desktop에서 게시
**Power BI Desktop** 파일을 **Power BI 서비스**에 게시하면 모델의 데이터 및 **보고서** 보기에서 만든 보고서가 Power BI 작업 영역에 게시됩니다. 작업 영역 탐색기에서 동일한 이름의 새 데이터 세트와 모든 보고서를 볼 수 있습니다.

**Power BI Desktop**에서 게시하는 것은 Power BI의 **데이터 가져오기**를 사용하여 연결하고 **Power BI Desktop** 파일을 업로드하는 것과 동일한 효과를 가집니다.

> [!NOTE]
> Power BI의 보고서에서 수행한 변경 내용(예: 보고서의 시각화 추가, 삭제 또는 변경)은 원래 **Power BI Desktop** 파일에 다시 저장되지 않습니다.
> 
> 

## <a name="to-publish-a-power-bi-desktop-dataset-and-reports"></a>Power BI Desktop 데이터 세트 및 보고서를 게시하려면
1. Power BI Desktop에서 **파일** \> **게시** \> **Power BI에 게시** 누르거나 **게시** 에 리본입니다.  

   ![게시 단추](media/desktop-upload-desktop-files/pbid_publish_publishbutton.png)

2. Power BI에 로그인합니다.
3. 대상을 선택합니다.

   ![게시 대상 선택](media/desktop-upload-desktop-files/pbid_publish_select_destination.png)

작업이 완료되면 보고서에 대한 링크를 수신합니다. 링크를 클릭하여 Power BI 사이트에서 보고서를 엽니다.

![게시 성공 대화 상자](media/desktop-upload-desktop-files/pbid_publish_success.png)

## <a name="re-publish-or-replace-a-dataset-published-from-power-bi-desktop"></a>Power BI Desktop에서 게시된 데이터 세트의 다시 게시 또는 대체
**Power BI Desktop** 파일을 게시할 때는 **Power BI Desktop**에서 만든 데이터 세트 및 모든 보고서가 Power BI 사이트에 업로드됩니다. **Power BI Desktop** 파일을 다시 게시할 때는 Power BI 사이트의 데이터 세트가 **Power BI Desktop** 파일에서 업데이트된 데이터 세트로 대체됩니다.

이 작업은 모두 간단 하지만 몇 가지 알아야 할:

* 이미 Power BI에 **Power BI Desktop** 파일과 동일한 이름의 데이터 세트가 두 개 이상 있을 경우, 게시에 실패할 수 있습니다. Power BI에 동일한 이름의 데이터 세트가 하나뿐인지 확인하세요. 파일의 이름을 변경하고 파일과 동일한 이름의 새 데이터 세트를 게시, 생성할 수도 있습니다.
* 열 또는 측정값의 이름을 변경하거나 삭제하는 경우, Power BI에서 해당 필드에 갖고 있던 모든 시각화가 손상될 수 있습니다. 
* Power BI는 기존 열 형식의 일부 변경을 무시합니다. 예를 들어, 열 형식을 0.25에서 25%로 변경한 경우입니다.
* Power BI의 기존 데이터 세트에 대해 구성된 새로 고침 일정이 있고 파일에 새로운 데이터 원본을 추가한 다음, 다시 게시한 경우에는 다음 일정 새로고침에 앞서 *데이터 원본 관리*에 로그인해야 합니다.

