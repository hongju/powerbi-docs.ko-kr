---
title: 큰 데이터 세트, 데이터 요소 제한 및 데이터 전략
description: 시각적 개체 및 데이터 감소 전략에 대한 데이터 제한
author: mihart
ms.reviewer: justyna
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/10/2020
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 320e8a25206a069c43800295ab64a7ab87afbcf0
ms.sourcegitcommit: 801d2baa944469a5b79cf591eb8afd18ca4e00b1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/11/2020
ms.locfileid: "75885243"
---
# <a name="apply-data-point-limits-and-strategies-by-visual-type"></a>시각적 개체 유형별 데이터 요소 제한 및 전략 적용

Power BI에서 시각적 개체를 렌더링할 경우 시각화가 빠르고 정확해야 합니다. 이를 위해 각 시각적 개체 유형의 기본 알고리즘을 구성해야 합니다. Power BI의 시각적 개체는 다양한 규모의 데이터 세트를 처리할 수 있을 정도의 유연성이 있어야 합니다. 일부 데이터 세트에는 몇 개의 데이터 요소만 있는 반면, 다른 데이터 세트에는 페타바이트 단위의 데이터 요소가 있습니다. 이 문서에서는 Power BI에서 시각화를 렌더링하는 데 사용하는 전략을 설명합니다.

## <a name="data-reduction-strategies"></a>데이터 감소 전략
모든 시각적 개체는 분석되는 대규모일 수 있는 데이터를 처리하기 위해 하나 이상의 ‘데이터 감소 전략’을 사용합니다.  간단한 테이블에서도 클라이언트에 전체 데이터 세트를 로드하지 않기 위한 전략을 사용합니다.  사용되는 감소 전략은 시각적 개체 유형에 따라 다릅니다. 각 시각적 개체는 서버에 전송된 데이터 요청을 생성하는 과정 중에 지원되는 ‘데이터 감소 전략’ 중에서 선택합니다.  

각 시각적 개체는 전체 데이터 양에 영향을 주는 이러한 전략의 매개 변수를 제어합니다.   

## <a name="strategies"></a>전략
각 전략에는 시각화되는 데이터의 셰이프 및 형식을 기반으로 하는 기본값이 있습니다. 그러나 Power BI 서식 지정 창에서 기본값을 재정의하여 적합한 사용자 환경을 제공할 수 있습니다. 

* **데이터 창**(구분): 사용자가 전체 데이터 세트의 조각을 점진적으로 로드하여 시각적 개체에서 데이터를 스크롤할 수 있도록 합니다.
* **TopN**: 처음 N개 항목만 표시합니다.
* **간단한 샘플**: 사이에 있는 처음, 마지막 및 N개 균등 분산 항목을 표시합니다.
* **BottomN**: 마지막 N개 항목만 표시합니다.  자주 업데이트되는 데이터를 모니터링하는 데 유용합니다.
* **고밀도 샘플링** - 이상값 및/또는 곡선 셰이프를 더욱 잘 준수하는 향상된 샘플링 알고리즘입니다.
    * **범주화된 선 샘플링** - 축에서 Bin의 이상값을 기반으로 하는 샘플 데이터 요소입니다.
    * **겹치는 요소 샘플링** - 이상값을 보존하기 위해 겹치는 값을 기반으로 하는 샘플 데이터 요소입니다.

## <a name="statistics"></a>통계
특정 모델은 특정 열의 값 수에 대한 통계를 제공할 수 있습니다. 해당 정보가 있으면 해당 정보를 이용하여 시각적 개체가 전략의 값 수를 명시적으로 재정의하지 않는 경우 여러 계층 구조에서 향상된 분산을 제공합니다.

자세한 내용은 [Analysis Services의 새로운 기능](https://docs.microsoft.com/sql/analysis-services/what-s-new-in-analysis-services?view=sql-server-2017)을 참조하세요.

## <a name="dynamic-limits"></a>동적 제한
위의 전략 외에도 그룹화 열의 2개 계층 구조(축과 범례 또는 범주와 계열)가 있는 시각적 개체는 ‘동적 제한’이라는 하나의 추가 전략을 사용합니다.   동적 제한은 데이터 요소를 더 잘 분산하도록 설계되었습니다. 

동적 제한은 정적 제한보다 스파스 데이터 요소에 더 효과적인 선택입니다. 예를 들어 시각적 개체는 총 1000개 요소가 포함된 100개 범주 및 10개 계열을 선택하도록 구성될 수 있습니다. 그러나 실제 데이터에는 50개 범주 및 20개 계열이 포함됩니다.  쿼리 런타임에 동적 제한은 모든 20개 계열을 선택하여 요청된 1000개 요소를 채웁니다.

동적 제한은 다음 설명과 같이 서버가 가능할 때 자동으로 적용됩니다.

* [서버의 SuperDax 기능을 활용](https://blogs.msdn.microsoft.com/analysisservices/2015/09/02/whats-new-in-microsoft-sql-server-analysis-services-tabular-models-in-sql-server-2016-ctp-2-3/)하는 온-프레미스 SSAS 버전 2016 이상의 Power BI Desktop에서

* 가져온 모델, 직접 쿼리 서비스 실시간 연결 또는 AS PaaS 실시간 연결을 사용할 경우 데스크톱 및 Power BI 서비스에서. 

* Power BI 서비스에서 온-프레미스 SSAS에 온-프레미스 게이트웨이를 통해 연결할 경우에는 동적 제한을 사용할 수 없습니다. 온-프레미스 게이트웨이는 온-프레미스 SSAS와 다른 결과 세트 구조를 반환하는 동적 제한 전략을 완전히 지원하지 않습니다.  

## <a name="strategies-and-data-point-limits-by-visual-type"></a>시각적 개체 유형별 전략 및 데이터 요소 제한

### <a name="area-chart"></a>영역형 차트
[선 샘플링 작동 방식](../desktop-high-density-sampling.md#how-the-new-line-sampling-algorithm-works) 참조

### <a name="barcolumn-chart"></a>가로 막대형/세로 막대형 차트
- 범주별 모드인 경우
    - 범주: 한 번에 500개 행의 창을 사용하여 가상화
    - 계열: 상위 60
    - 스칼라 모드인 경우(동적 제한을 사용할 수 있음)
        - 최대 요소: 10,000
        - 범주: 500개 값 샘플
        - 계열: 상위 20개 값

### <a name="card-multirow"></a>카드(다중 행) 
- 값: 한 번에 200개 행의 창을 사용하여 가상화

### <a name="combo-chart"></a>콤보 차트
 세로 막대형 차트와 동일한 전략을 사용합니다. **콤보 차트**의 선은 **꺾은선형 차트**에서 사용하는 고밀도 알고리즘을 사용하지 않습니다.

### <a name="custom-visuals"></a>사용자 지정 시각적 개체
최대 30,000개를 가져올 수 있지만 어떤 전략을 사용할지는 시각적 개체 작성자의 마음입니다. 기본 제한은 1,000개이지만 시각적 개체 생성자가 이를 최대 30,000개까지로 변경할 수 있습니다.

### <a name="doughnut"></a>도넛형
- 최대 요소: 3,500
- 그룹: 상위 500
- 세부 정보: 상위 20

### <a name="filled-map-choropleth"></a>등치 지역도 단계구분도 
등치 지역도에는 통계 또는 동적 제한을 사용할 수 있습니다. Power BI는 동적 제한, 통계 및 마지막 구성의 순서로 감소를 사용하려고 시도합니다. 
- 최대 요소: 10000
- 범주: 상위 500
- 계열(X 및 Y가 둘 다 있는 경우): 상위 20

### <a name="funnel"></a>깔때기형
- 최대 요소: 3,500
- 범주: 상위 3,500

### <a name="kpi"></a>KPI
- 추세 축
- 하위 3,500

### <a name="line-chart"></a>꺾은선형 차트
[선 샘플링 작동 방식](../desktop-high-density-sampling.md#how-the-new-line-sampling-algorithm-works) 참조

### <a name="line-chart-high-density"></a>꺽은선형 차트, 고밀도
[고밀도 샘플링](../desktop-high-density-sampling.md) 참조

### <a name="map"></a>맵 
- 최대 요소: 3,500

구성에 따라 지도에 다음을 포함할 수 있습니다.
- 위치: 상위 3,500
- 위치, 크기: 상위 3,500
- 위치, 위도 및 경도 집계(+/-Size): 상위 3,500
- 위도, 경도: [고밀도 분산형](desktop-high-density-scatter-charts.md) 참조
- 위도, 경도, 크기: 상위 3,500
- 범례, 위도, 경도: [고밀도 분산형](desktop-high-density-scatter-charts.md) 참조
- 범례, 위도, 경도, 크기: 상위 233개 범례, 상위 15개 위도 및 경고(통계 또는 동적 제한을 사용할 수 있음)
- 위치, 범례, 위도 및 경도를 집계로(+/-Size): 상위 233개 위치, 상위 15개 범례(통계 또는 동적 제한을 사용할 수 있음)

### <a name="matrix"></a>행렬
- 행: 한 번에 500개 행의 창을 사용하여 가상화
- 열: 상위 100개 그룹화 열 
- 값: 여러 값이 데이터 감소 계산에 포함되지 않음

### <a name="powerapps-visual"></a>PowerApps 시각적 개체
최대 30,000개를 가져올 수 있지만 어떤 전략을 사용할지는 시각적 개체 작성자의 마음입니다. 기본 제한은 1,000개이지만 시각적 개체 생성자가 이를 최대 30,000개까지로 변경할 수 있습니다.

### <a name="radial-gauge"></a>방사형 계기
감소 전략 없음

### <a name="slicer"></a>슬라이서
- 값: 한 번에 200개 행의 창을 사용하여 가상화

### <a name="scatter-chart-high-density"></a>분산형 차트(고밀도)
[고밀도 분산형](https://docs.microsoft.com/power-bi/visuals/desktop-high-density-scatter-charts) 참조

### <a name="pie"></a>원형
- 최대 요소: 3,500
- 그룹: 상위 500
- 세부 정보: 상위 20

### <a name="r--python-visuals"></a>R 및 Python 시각적 개체
150,000개 행으로 제한됨. 150,000개 이상의 행이 선택되면 상위 150,000개 행만 사용됨

### <a name="ribbon-chart"></a>리본 차트
- 범주별 모드인 경우
    - 범주: 한 번에 500개 행의 창을 사용하여 가상화(데이터 창)
    - 계열: 상위 60
    - 스칼라 모드인 경우(동적 제한을 사용할 수 있음)
        - 최대 요소: 10,000
        - 범주: 500개 값 샘플
        - 계열: 상위 20개 값

### <a name="shape-map-preview"></a>도형 맵(미리 보기)
도형 맵에는 통계 또는 동적 제한을 사용할 수 있습니다. 
- 최대 요소: 1,500
- 범주: 상위 500

### <a name="table"></a>테이블
- 값: 한 번에 500개 행의 창을 사용하여 가상화(데이터 창)

### <a name="tree-map-could-use-statistics-or-dynamic-limits"></a>트리 맵(통계 또는 동적 제한을 사용할 수 있음)
- 최대 요소: 3,500
- 그룹: 상위 500
- 세부 정보: 상위 20

### <a name="waterfall-chart"></a>폭포 차트
- 범주 버킷만 있는 경우
    - 최대 요소: 3,500
    - 범주 전용 - 상위 3,500
- 범주 및 분류가 둘 다 있는 경우
    - 범주: 한 번에 30개 행의 창을 사용하여 가상화(데이터 창)
    - 분석 결과 - 상위 200개 값


## <a name="next-steps"></a>다음 단계
[시각화 형식](power-bi-report-visualizations.md)
