---
title: Power BI 서비스의 매개 변수 설정 편집
description: 쿼리 매개 변수는 Power BI Desktop에서 만들지만 Power BI 서비스에서 검토되고 업데이트될 수 있습니다.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 11/21/2018
ms.author: maggies
LocalizationGroup: Create reports
ms.openlocfilehash: eefb863b4dde9fb6e368e244fa9d55c0af7c6001
ms.sourcegitcommit: e17fc3816d6ae403414cf5357afbf6a492822ab8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/04/2018
ms.locfileid: "52829599"
---
# <a name="edit-parameter-settings-in-the-power-bi-service"></a>Power BI 서비스의 매개 변수 설정 편집
보고서 작성자는 Power BI Desktop의 보고서에 쿼리 매개 변수를 추가합니다. 매개 변수를 사용하면 보고서의 일부가 하나 이상의 매개 변수 *값*을 사용하도록 할 수 있습니다. 예를 들어 보고서 작성자는 단일 국가/지역으로 데이터를 제한하는 매개 변수 또는 날짜, 시간 및 텍스트와 같은 필드에 적합한 형식을 정의하는 매개 변수를 만들 수 있습니다.

![데스크톱에서 매개 변수 관리 옵션을 보여주는 홈 탭](media/service-parameters/power-bi-manage-parameters.png)

## <a name="review-and-edit-parameters-in-power-bi-service"></a>Power BI 서비스에서 매개 변수 검토 및 편집

보고서 작성자는 데스크톱에서 매개 변수를 정의합니다. [Power BI 서비스에 해당 보고서를 게시](desktop-upload-desktop-files.md)하면 매개 변수 설정 및 선택 항목이 함께 이동합니다. 사용 가능한 데이터를 제한하는 매개 변수가 아니라 허용되는 값을 정의하고 설명하는 매개 변수인 Power BI 서비스의 일부 매개 변수 설정을 검토하고 편집할 수 있습니다.

1. Power BI 서비스에서 톱니바퀴 아이콘 ![톱니바퀴 아이콘](media/service-parameters/power-bi-cog.png)을 선택하여 **설정**을 엽니다.

2. **데이터 집합**에 대한 탭을 선택하고 목록에서 데이터 집합을 강조 표시합니다. 
    
    ![데이터 집합 탭이 선택된 설정 창](media/service-parameters/power-bi-select-dataset2.png)

3. **매개 변수**를 확장합니다.  선택한 데이터 집합에 매개 변수가 없는 경우 쿼리 매개 변수의 자세한 내용에 대한 링크가 포함된 메시지가 표시됩니다. 하지만 데이터 집합에 매개 변수가 있는 경우 **매개 변수** 머리글을 확장하면 이러한 매개 변수를 표시합니다. 

    ![매개 변수를 확장한 설정 창](media/service-parameters/power-bi-settings.png)

    매개 변수 설정을 검토하고 필요한 경우 변경합니다. 회색 필드는 편집할 수 없습니다. 


## <a name="next-steps"></a>다음 단계
간단한 매개 변수를 추가하는 임시 방법은 [URL을 수정](service-url-filters.md)하는 것입니다.