---
title: Power BI 시각화를 생성하는 데 사용된 데이터 표시
description: 이 문서에서는 Power BI에서 시각적 개체를 만드는 데 사용되는 데이터를 보는 방법 및 해당 데이터를 .csv 파일로 내보내는 방법을 설명합니다.
author: mihart
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 11/4/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: f1598aabee45359b312d39f836cede8ca4198bb2
ms.sourcegitcommit: 97597ff7d9ac2c08c364ecf0c729eab5d59850ce
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2020
ms.locfileid: "75758626"
---
# <a name="display-a-visualizations-underlying-data"></a>시각화의 기본 데이터 표시

## <a name="show-data"></a>데이터 표시
Power BI 시각화는 데이터 세트에서 데이터를 사용하여 구성됩니다. 숨은 기능에 관심이 있는 경우 Power BI를 사용하면 시각적 개체를 만드는 데 사용되는 데이터를 *표시*할 수 있습니다. **데이터 표시**를 선택하면 Power BI는 시각화 아래(또는 옆)에 데이터를 표시합니다.

시각화를 만드는 데 사용되는 데이터를 .xlsx 또는 .csv 파일로 내보내고 Excel에서 볼 수도 있습니다. 자세한 내용은 [Power BI 시각화에서 데이터 내보내기](power-bi-visualization-export-data.md)를 참조하세요.

> [!NOTE]
> *데이터 표시* 및 *데이터 내보내기*는 모두 Power BI 서비스 및 Power BI Desktop에서 사용할 수 있습니다. Power BI Desktop은 하나의 추가 세부 정보 계층을 제공합니다. [*레코드 표시*는 데이터 세트에서 실제 행을 표시합니다](../desktop-see-data-see-records.md).
> 
> 

## <a name="using-show-data"></a>*데이터 표시* 사용 
1. Power BI Desktop에서 시각화를 선택하여 활성화합니다.

2. **기타 작업**(...)을 선택하고 **데이터 표시**를 선택합니다. 
    ![데이터 표시의 표시 옵션](media/service-reports-show-data/power-bi-more-action.png)


3. 기본적으로 데이터는 시각적 개체 아래에 표시됩니다.
   
   ![시각적 개체 및 데이터 세로 표시](media/service-reports-show-data/power-bi-show-data-below.png)

4. 방향을 변경하려면 시각화의 오른쪽 위에서 세로 레이아웃 ![세로 레이아웃으로 변경하는 데 사용되는 아이콘의 작은 스크린샷](media/service-reports-show-data/power-bi-vertical-icon-new.png) 을 선택합니다.
   
   ![시각적 개체 및 데이터 가로 표시](media/service-reports-show-data/power-bi-show-data-side.png)
5. 데이터를 .csv 파일로 내보내려면 줄임표를 선택하고 **데이터 내보내기**를 선택합니다.
   
    ![데이터 내보내기 선택](media/service-reports-show-data/power-bi-export-data-new.png)
   
    데이터를 Excel로 내보내기에 대한 자세한 내용은 [Power BI 시각화에서 데이터 내보내기](power-bi-visualization-export-data.md)를 참조하세요.
6. 데이터를 숨기려면 **탐색** > **데이터 표시**를 선택 취소합니다.

## <a name="using-show-records"></a>레코드 표시 사용
시각화에서 하나의 데이터 레코드에 포커스를 맞추고 그 뒤의 데이터로 드릴할 수도 있습니다. 

1. **레코드 표시**를 사용하려면 시각화를 선택하여 활성화합니다. 

2. 데스크톱 리본에서 **시각적 도구** > **데이터/드릴** > **레코드 표시**를 선택합니다. 

    ![레코드 표시가 선택된 스크린샷.](media/service-reports-show-data/power-bi-see-record.png)

3. 시각화에서 데이터 요소나 행을 선택합니다. 이 예제에서는 왼쪽에서 네 번째 열을 선택했습니다. Power BI에서 이 데이터 요소에 대한 데이터 세트 레코드를 표시합니다.

    ![데이터 세트의 단일 레코드 스크린샷.](media/service-reports-show-data/power-bi-row.png)

4. **보고서로 돌아가기**를 선택하여 Desktop 보고서 캔버스로 돌아갑니다. 

## <a name="considerations-and-troubleshooting"></a>고려 사항 및 문제 해결

- 리본의 **레코드 표시** 단추가 사용하지 않도록 설정되어 회색으로 표시되면 선택된 시각화가 레코드 표시를 지원하지 않는 것입니다.
- 레코드 표시 보기에서 데이터를 변경하고 다시 보고서에 저장할 수 없습니다.
- 시각적 개체에서 계산된 측정값을 사용할 때는 레코드 표시를 사용할 수 없습니다.
- 라이브 MD(다차원) 모델에 연결된 경우 레코드 표시를 사용할 수 없습니다.  

## <a name="next-steps"></a>다음 단계
[Power BI 시각화에서 데이터 내보내기](power-bi-visualization-export-data.md)    

궁금한 점이 더 있나요? [Power BI 커뮤니티를 이용하세요.](https://community.powerbi.com/)

