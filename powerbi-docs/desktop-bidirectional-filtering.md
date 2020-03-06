---
title: Power BI Desktop의 양방향 교차 필터링
description: Power BI Desktop에서 DirectQuery를 사용하여 교차 필터링 사용
author: davidiseminger
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/15/2020
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 141dabdce7816d21c49d8c7f98d1438c2fc20e8d
ms.sourcegitcommit: a1409030a1616027b138128695b80f6843258168
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76709842"
---
# <a name="enable-bidirectional-cross-filtering-for-directquery-in-power-bi-desktop"></a>Power BI Desktop에서 DirectQuery에 대해 양방향 교차 필터링 사용

테이블을 필터링하여 적절한 데이터 보기를 만드는 경우 보고서 작성자 및 데이터 모델러는 보고서에 필터를 적용하는 방법을 정하는 데 어려움을 겪습니다. 이전에는 테이블의 필터 컨텍스트가 관계의 한쪽에 있었지만 다른 쪽에는 없었습니다. 이러한 정렬에서는 원하는 결과를 얻기 위해 복잡한 DAX 수식이 필요한 경우가 많았습니다.

양방향 교차 필터링을 사용하면 보고서 작성자와 데이터 모델러는 이제 관련 테이블과 작업할 때 필터를 적용할 수 있는 방법을 더욱 효율적으로 제어할 수 있습니다. 양방향 교차 필터링을 사용하면 테이블 관계의 ‘양쪽’에 필터를 적용할 수 있습니다. 테이블 관계의 다른 쪽에 있는 두 번째 관련 테이블에 필터 컨텍스트를 전파하여 필터를 적용할 수 있습니다.

## <a name="enable-bidirectional-cross-filtering-for-directquery"></a>DirectQuery에 대해 양방향 교차 필터링 사용

**관계 편집** 대화 상자에서 교차 필터링을 사용하도록 설정할 수 있습니다. 관계에 교차 필터링을 사용하려면 다음 옵션을 구성해야 합니다.

* **교차 필터 방향**을 **모두**로 설정합니다.
* **양방향으로 보안 필터 적용**을 선택합니다.

교차 필터링을 활성화하려면 관계에 대한 **관계 편집** 대화 상자에서 다음을 선택해야 합니다.

* **교차 필터 방향**은 **모두**로 설정되어야 합니다.
* **보안 필터 양방향으로 적용**도 선택해야 합니다.

  ![](media/desktop-bidirectional-filtering/bidirectional-filtering_2.png)


> [!NOTE]
> Power BI Desktop에서 교차 필터링 DAX 수식을 만들 때 *UserPrincipalName*을 사용합니다. 이 필드는 사용자의 로그인과 동일한 경우가 많습니다. 예를 들어 *UserName* 대신 <em>joe@contoso.com</em>입니다. 따라서 *UserName* 또는 *EmployeeID*를 *UserPrincipalName*에 매핑하는 관련 테이블을 만들어야 할 수 있습니다.

양방향 교차 필터링의 작동 방식에 대한 자세한 내용 및 예제는 [Power BI Desktop 백서에 대한 양방향 교차 필터링](https://download.microsoft.com/download/2/7/8/2782DF95-3E0D-40CD-BFC8-749A2882E109/Bidirectional%20cross-filtering%20in%20Analysis%20Services%202016%20and%20Power%20BI.docx)을 확인하세요.

