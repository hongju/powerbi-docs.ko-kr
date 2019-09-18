---
title: 보고서에 차트 정렬 방식 변경
description: Power BI 보고서에서 차트 정렬 방식 변경
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 08/21/2019
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: 98a91b0651e7a357f0ba0462f6ba8734c64ab162
ms.sourcegitcommit: 52aa112ac9194f4bb62b0910c4a1be80e1bf1276
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/16/2019
ms.locfileid: "70302733"
---
# <a name="change-how-a-chart-is-sorted-in-a-power-bi-report"></a>Power BI 보고서에서 차트 정렬 방식 변경
Power BI 보고서에서는 차트의 범주 이름 또는 각 범주의 숫자 값을 기준으로 대부분의 시각화를 알파벳순으로 정렬할 수 있습니다. 예를 들어 이 차트는 범주 **매장 이름**을 기준으로 정렬되었습니다.

![X 축을 기준으로 사전순으로 정렬된 막대형 차트](media/end-user-change-sort/pbi_chartsortcategory.png)

정렬 기준을 범주(매장 이름)에서 값(평방 피트당 매출)으로 대신 변경하는 것은 쉽습니다.

1. 줄임표(...)를 선택하고 **정렬 기준 > 평방 미터당 매출**을 선택합니다.
2. 필요한 경우 줄임표를 다시 선택하고 **내림차순 정렬**을 선택합니다.

   ![정렬 방식 및 오름차순, 내림차순 선택을 보여주는 비디오](media/end-user-change-sort/sort.gif)

> [!NOTE]
> 일부 시각화는 정렬되지 않습니다. 예를 들어 트리맵, 지도, 등치 지역도, 분산형, 계기, 카드, 폭포 시각화는 정렬할 수 없습니다.

## <a name="saving-changes-you-make-to-sort-order"></a>정렬 순서에 적용한 변경 내용 저장
Power BI 보고서에서는 필터, 슬라이서, 정렬 및 기타 데이터 보기 변경 사항을 유지합니다. 따라서 보고서에서 다른 곳으로 이동하고 나중에 돌아오면 변경 내용이 저장됩니다.  변경 내용을 보고서 디자이너 설정으로 다시 되돌리려면 위쪽 메뉴 모음에서 **기본값으로 다시 설정**을 선택합니다. 

![영구 정렬](media/end-user-change-sort/power-bi-reset.png)

그러나 **기본값으로 다시 설정** 단추가 회색으로 표시되면 보고서 디자이너가 변경 내용을 저장하는 기능을 비활성화했다는 의미입니다.

<a name="other"></a>
## <a name="sorting-using-other-criteria"></a>다른 조건을 사용하여 정렬
경우에 따라 다른 필드 또는 기타 조건을 사용하여 시각적 개체를 정렬할 수 있습니다.  예를 들어 사전순이 아닌 월별로 정렬하려고 하거나 개별 숫자가 아닌 전체 숫자(예를 들어 0, 1, 20, 9가 아닌 0, 1, 9, 20 전체)별로 정렬하려고 할 수 있습니다.  

일부 경우에는 원하는 방식으로, 예를 들어 월별로 시각적 개체를 정렬할 수 있습니다.  하지만 그렇지 않은 경우 보고서에 사용된 데이터 세트를 조정해야 하기 때문일 수 있습니다. 보고서 디자이너에게 데이터 세트를 업데이트하도록 요청하세요.

## <a name="next-steps"></a>다음 단계
[Power BI 보고서의 시각화](end-user-visualizations.md)에 대해 자세히 알아보세요.

[Power BI - 기본 개념](end-user-basic-concepts.md)
