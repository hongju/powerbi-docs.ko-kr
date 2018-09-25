---
title: Power BI 보고서에서 차트 정렬 방식 변경
description: Power BI 보고서에서 차트 정렬 방식 변경
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 05/20/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: dd8eeda3ba2bbc8da49a06199fa00dc3d731faaa
ms.sourcegitcommit: 70192daf070ede3382ac13f6001e0c8b5fb8d934
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2018
ms.locfileid: "46565892"
---
# <a name="change-how-a-chart-is-sorted-in-a-power-bi-report"></a>Power BI 보고서에서 차트 정렬 방식 변경
Power BI 보고서에서는 차트의 범주 이름 또는 각 범주의 숫자 값을 기준으로 대부분의 시각화를 알파벳순으로 정렬할 수 있습니다. 예를 들어 이 차트는 매장 이름을 기준으로 정렬되었습니다.

![](media/end-user-change-sort/pbi_chartsortcategory.png)

정렬 기준을 범주(매장 이름)에서 값(평방 피트당 매출)으로 대신 변경하는 것은 쉽습니다.

1. 줄임표(...)를 선택하고 **정렬 기준 평방 미터당 매출**을 선택합니다.
2. 필요할 경우 정렬 아이콘 ![](media/end-user-change-sort/sorticon.png)을 선택하여 **내림차순**으로 변경합니다.

   ![](media/end-user-change-sort/sortby.gif)

   **참고**: 일부 시각화는 정렬되지 않습니다.  예를 들어 트리맵, 맵, 등치 지역도, 분산형, Guage, 카드, Multi Row Card, 폭포 시각화는 정렬할 수 없습니다.

## <a name="saving-changes-you-make-to-sort-order"></a>정렬 순서에 적용한 변경 내용 저장
Power BI 보고서에서는 필터, 슬라이서, 정렬 및 기타 데이터 보기 변경 사항을 유지합니다. 따라서 보고서에서 다른 곳으로 이동하고 나중에 돌아오면 변경 내용이 저장됩니다.  보고서 작성자 설정에 대한 변경 내용을 다시 되돌리려면 위의 메뉴 모음에서 **기본값으로 다시 설정**을 선택합니다. 

![영구 정렬](./media/end-user-change-sort/power-bi-reset-to-default.png)

그러나 **기본값으로 다시 설정** 단추가 회색으로 표시되면 보고서 작성자가 변경 내용을 저장하는 기능을 비활성화했다는 의미입니다.

<a name="other"></a>
## <a name="sorting-using-other-criteria"></a>다른 조건을 사용하여 정렬
경우에 따라 다른 필드 또는 기타 조건을 사용하여 시각적 개체를 정렬할 수 있습니다.  예를 들어 사전순이 아닌 월별로 정렬하려고 하거나 개별 숫자가 아닌 전체 숫자(예를 들어 0, 1, 20, 9가 아닌 0, 1, 9, 20 전체)별로 정렬하려고 할 수 있습니다.  

일부 경우에는 원하는 방식으로, 예를 들어 월별로 시각적 개체를 정렬할 수 있습니다.  하지만 그렇지 않은 경우 보고서에 사용된 데이터 집합을 조정해야 하기 때문일 수 있습니다. 다음은 몇 가지 해결 방법입니다.

* Power BI Desktop에서 [데이터 도구 모델링 탭을 사용하여 다른 열별로 정렬](../desktop-sort-by-column.md)합니다.
* Excel에서 자체 데이터 집합이 있는 경우 월 이름 및 번호를 연결하는 새 열을 추가합니다. 그런 다음 데이터 집합을 새로 고치거나 다시 가져와 필드 영역에 새 열을 표시합니다.
* Excel에서 숫자 열에 "텍스트"가 아닌 "정수" 또는 "십진수"로 태그를 지정합니다.

## <a name="next-steps"></a>다음 단계
[Power BI 보고서의 시각화](../visuals/power-bi-report-visualizations.md)에 대해 자세히 알아보세요.

[Power BI - 기본 개념](end-user-basic-concepts.md)

궁금한 점이 더 있나요? [Power BI 커뮤니티를 이용하세요.](http://community.powerbi.com/)
