---
title: "Power BI의 도넛형 차트(자습서)"
description: "자습서: Power BI의 도넛형 차트"
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
ms.date: 09/27/2017
ms.author: mihart
ms.openlocfilehash: 2f428095eb57c5358770f1d6d8572316d2b84c37
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2017
---
# <a name="doughnut-charts-in-power-bi-tutorial"></a>Power BI의 도넛형 차트(자습서)
도넛형 차트는 전체에 대한 부분의 관계를 표시한다는 점에서 원형 차트와 비슷합니다. 가운데가 비어 있고 레이블 또는 아이콘이 들어갈 공간이 있다는 점만 다릅니다.

## <a name="create-a-doughnut-chart"></a>도넛형 차트 만들기
이를 수행하려면 Power BI에 로그인하여 **데이터 가져오기**\>**샘플**\>**소매 분석 샘플**\>**연결**을 선택합니다. 

1. 대시보드에서 **총 매장** 타일을 선택하여 "소매 분석 샘플" 보고서를 엽니다.
2. **보고서 편집** 을 선택하여 편집 보기에서 보고서를 엽니다.
3. [새 보고서 페이지를 추가합니다](power-bi-report-add-page.md).
4. 올해의 판매액을 범주별로 표시하는 도넛형 차트를 만듭니다.
   
   * **필드** 창에서 **Sales**\>**Last Year Sales**를 선택합니다.
   * 도넛형 차트로 변환합니다. **값** 영역에 Last Year Sales가 없을 경우 끌어다 놓습니다.
     
       ![](media/power-bi-visualization-doughnut-charts/convertdonut.png)
   * **항목**\>**범주**를 선택하여 **범례** 영역에 추가합니다. 
     
       ![](media/power-bi-visualization-doughnut-charts/doughnuttutorial.png)

## <a name="considerations-and-troubleshooting"></a>고려 사항 및 문제 해결
* 도넛형 차트 값을 더한 총합은 100%를 넘지 않아야 합니다.
* 범주가 너무 많으면 읽고 해석하기 어렵습니다.
* 도넛형 차트는 개별 섹션을 서로 비교하는 것보다는 특정 섹션을 전체와 비교하는 데 사용하는 것이 가장 좋습니다. 

## <a name="next-steps"></a>다음 단계
[Power BI의 보고서](service-reports.md)

[Power BI의 시각화 유형](power-bi-visualization-types-for-reports-and-q-and-a.md)

[Power BI 보고서의 시각화](power-bi-report-visualizations.md)

[Power BI - 기본 개념](service-basic-concepts.md)

궁금한 점이 더 있나요? [Power BI 커뮤니티를 이용하세요.](http://community.powerbi.com/)

