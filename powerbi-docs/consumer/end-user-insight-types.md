---
title: Power BI에서 지원되는 정보의 유형
description: Power BI를 사용한 신속한 정보 활용 및 정보 보기.
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 10/02/2019
ms.author: mihart
LocalizationGroup: Dashboards
ms.openlocfilehash: 7f754c1164448be88a3269cb8e3d129b63a6115f
ms.sourcegitcommit: 5410a17c6325406c9d9364585d7c26de4d9488ae
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72379906"
---
# <a name="types-of-insights-supported-by-power-bi"></a>Power BI에서 지원되는 정보의 유형

Power BI 서비스는 대시보드 또는 보고서에서 인사이트를 자동으로 찾을 수 있습니다.

## <a name="how-does-insights-work"></a>정보는 어떻게 작동하나요?
Power BI는 데이터 세트의 다른 하위 집합을 빠르게 검색합니다. 검색 시 Power BI는 정교한 알고리즘을 적용하여 관심을 가질 가능성이 높은 인사이트를 검색합니다. Power BI는 할당된 시간 내에 가능한 한 많은 데이터 세트를 검색합니다.

데이터 세트 또는 대시보드 타일에 대한 검색을 실행할 수 있습니다.   

## <a name="what-types-of-insights-can-we-find"></a>어떤 유형의 정보를 찾을 수 있나요?
다음은 사용되는 알고리즘 중 일부입니다.

## <a name="category-outliers-topbottom"></a>범주 이상값(상한/하한)
모델의 측정값에서 하나 또는 두 개의 차원 멤버가 차원의 다른 멤버보다 훨씬 더 큰 값을 가진 경우를 강조 표시합니다.  

![범주 이상값 예제](./media/end-user-insight-types/pbi_auto_insight_types_category_outliers.png)

## <a name="change-points-in-a-time-series"></a>시계열의 변경 지점
데이터의 시계열 추세에서 중요한 변경 내용이 있는 경우를 강조 표시합니다.

![시계열의 변경 지점 예제](./media/end-user-insight-types/pbi_auto_insight_types_changepoint.png)

## <a name="correlation"></a>상관 관계
데이터 세트의 한 차원에 대해 그릴 때 여러 측정값이 서로 간의 상관 관계를 표시하는 경우를 검색합니다.

![상관 관계 예제](./media/end-user-insight-types/pbi_auto_insight_types_correlation.png)

## <a name="low-variance"></a>하위 분산
데이터 요소가 평균에 크게 못 미치는 사례를 검색합니다.

![하위 분산 예제](./media/end-user-insight-types/power-bi-low-variance.png)

## <a name="majority-major-factors"></a>과반수(중요한 요인)
다른 차원을 기준으로 분석할 때 전체 값의 과반수가 단일 요인으로 인한 경우를 찾습니다.  

![주요 요소 예제](./media/end-user-insight-types/pbi_auto_insight_types_majority.png)

## <a name="overall-trends-in-time-series"></a>시계열의 전반적인 추세
시계열 데이터의 위쪽 또는 아래쪽 추세를 검색합니다.

![시계열의 전반적인 추세 예제](./media/end-user-insight-types/pbi_auto_insight_types_trend.png)

## <a name="seasonality-in-time-series"></a>시계열의 계절성
시계열 데이터에서 매주, 매월 또는 매년 계절성과 같은 주기적인 패턴을 찾습니다.

![계절성 예제](./media/end-user-insight-types/pbi_auto_insight_types_seasonality_new.png)

## <a name="steady-share"></a>안정적 지분
연속 변수에서 부모의 전체 값과 자식 값의 지분 간에 부모-자식 상관 관계가 있는 경우를 강조 표시합니다.

![안정적 지분 예제](./media/end-user-insight-types/pbi_auto_insight_types_steadyshare.png)

## <a name="time-series-outliers"></a>시계열 이상값
시계열 데이터에서 값이 다른 날짜/시간 값과 크게 다른 특정 날짜 또는 시간이 있는 경우를 검색합니다.

![시계열 이상값 예제](./media/end-user-insight-types/pbi_auto_insight_types_time_series_outliers.png)

## <a name="next-steps"></a>다음 단계
[Power BI 정보](end-user-insights.md)

궁금한 점이 더 있나요? [Power BI 커뮤니티를 이용하세요.](http://community.powerbi.com/)

