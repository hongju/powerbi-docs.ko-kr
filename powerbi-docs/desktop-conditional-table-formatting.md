---
title: Power BI Desktop에서 조건부 테이블 서식 지정
description: 테이블에 사용자 지정된 서식 지정을 적용합니다.
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 05/08/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 9599b40940c9d9cca254bb2ed2e87c161cce371f
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/17/2018
---
# <a name="conditional-formatting-in-tables"></a>테이블에서 조건부 서식 지정
테이블에 조건부 서식을 사용하면 셀 값을 기반으로 하거나 다른 값이나 필드를 기반으로 하여 사용자 지정된 셀 배경색을 지정할 수 있으며 그라데이션 색을 사용할 수 있습니다. 조건부 서식 지정에 액세스하려면 Power BI Desktop에서 **시각화** 창의 **필드**에서 서식을 지정하려는 **값**의 값 옆에 있는 아래쪽 화살표를 선택합니다(또는 필드를 마우스 오른쪽 단추로 클릭). 필드에 대한 조건부 서식은 **필드**의 **값** 영역에서만 관리할 수 있습니다.

![조건부 테이블 서식 지정](media/desktop-conditional-table-formatting/table-formatting_1.png)

대화 상자가 나타나면 색은 물론 ‘최소’ 및 ‘최대’ 값을 구성할 수 있습니다. **분기** 상자를 선택하면 선택적인 *가운데* 값도 구성할 수 있습니다.

![분기 색](media/desktop-conditional-table-formatting/table-formatting_2.png)

데이터 모델의 필드에 색 그라데이션을 기준으로 지정할 수도 있습니다. 또한 선택한 필드에 대해 집계 유형을 지정할 수 있습니다(선택한 필드는 **색 적용 대상** 필드에 지정하여 추적할 수 있음).

![필드에 색 기준 지정](media/desktop-conditional-table-formatting/table-formatting_2b.png)

테이블에 적용되는 경우 위에 설명된 단계 사용에 적용된 사용자 지정된 서식 지정은 조건에 따라 서식 지정된 셀에 적용된 모든 사용자 지정 테이블 스타일을 재정의합니다.

![테이블 서식 지정](media/desktop-conditional-table-formatting/table-formatting_3.png)

숫자 값을 서식 기준으로 선택하면 텍스트 및 날짜 필드에 조건부 서식을 적용할 수도 있습니다. 

시각화에서 조건부 서식 지정을 제거하려면 필드를 다시 마우스 오른쪽 단추로 클릭하고 **조건부 서식 지정 제거**를 선택합니다.

![테이블 서식 제거](media/desktop-conditional-table-formatting/table-formatting_4.png)

