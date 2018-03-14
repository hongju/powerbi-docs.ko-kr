---
title: "멋진 Power BI 대시보드를 디자인하기 위한 팁"
description: "멋진 Power BI 대시보드를 디자인하기 위한 팁"
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
ms.date: 03/02/2018
ms.author: mihart
LocalizationGroup: Dashboards
ms.openlocfilehash: 769d669f00c87e6139d8ff2cb8640739d09edf7a
ms.sourcegitcommit: 5e1f7d2673efe25c47b9b9f315011055bfe92c8f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2018
---
# <a name="tips-for-designing-a-great-power-bi-dashboard"></a>멋진 Power BI 대시보드를 디자인하기 위한 팁
이제 대시보드를 만들고 일부 타일을 추가했으므로 모양과 기능을 개선하는 방법을 살펴보겠습니다. 일반적으로 여기에는 가장 중요한 정보를 돋보이게 하고 깔끔하며 군더더기 없이 만드는 것이 포함됩니다.

다음은 몇 가지 팁입니다.

> [!TIP]
> 보고서에 대한 대부분의 디자인 원칙이 대시보드에도 적용됩니다.  백서 [보고서 및 시각화에 대한 최상의 디자인 원칙](power-bi-visualization-best-practices.md)을 읽어보세요.
> 
> 

### <a name="consider-your-audience"></a>대상 그룹을 고려
의사 결정에 도움이 될 주요 메트릭은 무엇인가요? 대시보드가 어떻게 사용될까요? 어떤 학습 내용 또는 문화적 가정이 디자인 선택에 영향을 줄 수 있을까요? 성공을 위해 대상 그룹은 어떤 정보를 필요로 할까요?

대시보드는 현재 데이터 상태를 한 곳에서 모니터링하는 개요임을 유념하세요. 대시보드는 기본 보고서 및 데이터 집합을 기반으로 하며 여러 세부 정보를 포함할 수 있습니다. 독자는 대시보드에서 보고서를 드릴인투할 수 있습니다. 따라서 독자가 모니터링해야 하는 내용이 아니라면 대시보드에 세부 정보를 넣지 마세요.

대시보드가 어디에 표시될 예정인가요? 큰 모니터에 표시될 예정이라면 대시보드에 더 많은 콘텐츠를 넣을 수 있습니다. 독자는 자신의 태블릿으로 대시보드를 확인하므로 타일 수가 적을수록 읽기 편합니다.

### <a name="tell-a-story-and-keep-it-to-one-screen"></a>스토리를 말하고 한 화면으로 유지
대시보드는 중요한 정보를 한 눈에 볼 수 있도록 하는 것이므로 모든 타일을 한 화면에 포함하는 것이 가장 좋습니다. 대시보드에서 스크롤 막대 사용을 피할 수 있나요?

대시보드가 너무 복잡한가요?  필수 정보를 쉽게 읽고 해석할 수 있도록 군더더기 제거

### <a name="make-use-of-full-screen-mode"></a>전체 화면 모드 사용
다른 항목 없이 [전체 화면](service-fullscreen-mode.md)에서 대시보드를 표시합니다.

### <a name="make-the-most-important-information-biggest"></a>가장 중요한 정보를 가장 비중있게
대시보드에서 시각화와 텍스트가 모두 동일한 크기인 경우 독자들은 가장 중요한 사항에 초점을 맞추기 어려워합니다. 예를 들어, 카드 시각화의 경우 중요한 번호를 눈에 띄게 표시하는 좋은 방법입니다.  
![카드 시각화](media/service-dashboards-design-tips/pbi_card.png)

하지만 컨텍스트를 제공해야 합니다.  

[번호로만 타일 만들기](power-bi-visualization-card.md)에 대해 알아보세요.

### <a name="put-the-most-important-information-in-the-upper-corner"></a>가장 중요한 정보를 상단 모서리에 놓기
대부분의 사람들이 위쪽에서 아래쪽으로 읽는 경향이 있으므로 가장 높은 수준의 세부 정보를 맨 위에 배치하고 대상 그룹이 읽어가는 방향(왼쪽-오른쪽, 오른쪽-왼쪽)으로 보다 자세한 정보를 표시합니다.

### <a name="use-the-right-visualization-for-the-data-and-format-it-for-easy-reading"></a>데이터에 적합한 시각화 사용 및 읽기 쉽게 서식 지정
다양성을 위해 여러 시각화를 사용하는 것을 피하세요.  시각화는 그림을 그리는 것이며 "읽고" 해석하기 쉬워야 합니다.  일부 데이터 및 시각화에서는 간단한 그래픽 시각화로도 충분합니다. 보다 복잡한 시각화를 호출할 수 있는 기타 데이터도 있지만 타일 및 레이블, 기타 사용자 지정 항목의 활용이 독자에게 도움이 되도록 해야 합니다.  

* [적절한 데이터 시각화를 선택합니다](http://blogs.msdn.com/b/microsoft_business_intelligence1/archive/2012/10/08/best-practices-in-data-visualization.aspx). 3차원 차트처럼 현실을 왜곡하는 차트를 사용할 때는 주의하세요. 인간의 뇌는 원형 모양을 해석하기 어렵다는 점을 유념하세요. 원형 차트, 도넛형 차트, 계기 및 기타 원형 차트 종류는 모양은 좋지만 데이터 시각화 모범 사례는 아닙니다.
* 차트 내에 있는 축의 차트 눈금, 차트 차원 순서 및 차원 값에 사용된 색이 일관되도록 하세요.
* 정량 데이터를 적절하게 인코딩하세요. 숫자를 표시할 때는 서너 개의 숫자를 초과하지 마세요. 소수점 왼쪽 및 수백 또는 수백만 자릿수를 한두 숫자로 표시하세요(예: 3,400,000가 아닌 3.4백만).
* 정밀도와 시간 수준을 섞어쓰지 마세요. 시간 프레임을 잘 이해하고 있어야 합니다.  해당 연도의 특정 월에서 필터링된 차트 옆에 지난 달에 대한 하나의 차트를 포함하지 마세요.
* 동일한 눈금에 큰 측정값과 작은 측정값을 함께 사용하지 마세요(예: 꺾은선형 차트 또는 가로 막대형 차트).  예를 들어 백만 단위인 측정값과 천 단위인 측정값이 있을 수 있습니다.  이러한 큰 단위에서는 천 단위인 측정값의 차이를 파악하기 어렵습니다.  함께 사용해야 하는 경우 보조 축의 사용을 허용하는 시각화를 선택합니다.
* 불필요한 데이터 레이블로 차트를 복잡하게 하지 마세요. 가로 막대형 차트의 값은 일반적으로 실제 숫자를 표시하지 않아도 잘 이해됩니다.
* [차트가 정렬](power-bi-report-change-sort.md)되는 방식에 주의하세요.  최상위 또는 최하위 숫자에 주목하도록 하려면 측정값을 기준으로 정렬합니다.  사람들이 여러 다른 범주 내에서 특정 범주를 신속하게 찾을 수 있도록 하려면 축을 기준으로 정렬합니다.  
* 원형 차트는 범주가 8개 미만일 경우 적합합니다. 값을 나란히 비교할 수 없으므로 원형 차트는 가로 막대형 및 세로 막대형 차트보다 값을 비교하기가 더 어렵습니다. 원형 차트는 부분을 비교하기보다는 부분에서 전체로의 관계를 파악하는 데 유용할 수 있습니다. 계기 차트는 목표의 컨텍스트에서 현재 상태를 표시하는 데 적합합니다.

시각화 관련 지침에 대한 자세한 내용은 [Power BI에서 시각화 유형](power-bi-visualization-types-for-reports-and-q-and-a.md)을 참조하세요.  

## <a name="learning-more-about-best-practice-dashboard-design"></a>모범 사례 대시보드 디자인에 대해 자세히 알아보기
뛰어난 대시보드 디자인 기법을 마스터하려면 시각적 인식 및 상황에 따라 조치 가능한 정보를 명확히 전달하는 방법에 대한 기본적인 게슈탈트(Gestalt) 이론을 학습하는 것이 좋습니다. 다행히 이에 대한 광범위한 리소스가 이미 제공되고 있으며 블로그에도 올라와 있습니다. 다음은 몇 가지 유용한 설명서입니다.

* *Information Dashboard Design* by Stephen Few  
* *Show Me the Numbers* by Stephen Few  
* *Now You See It* by Stephen Few  
* *Envisioning Information* by Edward Tufte  
* *Advanced Presentations* by Design by Andrew Abela   

## <a name="next-steps"></a>다음 단계
[Power BI의 대시보드](service-dashboards.md)  
[Power BI - 기본 개념](service-basic-concepts.md)  
궁금한 점이 더 있나요? [Power BI 커뮤니티를 이용하세요.](http://community.powerbi.com/)

