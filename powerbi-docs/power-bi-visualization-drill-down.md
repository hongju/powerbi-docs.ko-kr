---
title: Power BI에서 시각화 드릴다운
description: 이 문서에서는 Microsoft Power BI 서비스와 Power BI Desktop의 시각화에서 드릴다운하는 방법을 보여 줍니다.
author: mihart
manager: kfile
ms.reviewer: ''
featuredvideoid: MNAaHw4PxzE
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 02/26/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: d622e6b461668d1972a78f6844bd269fb6596061
ms.sourcegitcommit: dcde910817720c05880ffe24755034f916c9b890
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2018
---
# <a name="drill-down-in-a-visualization-in-power-bi"></a>Power BI에서 시각화 드릴다운
## <a name="drill-down-requires-a-hierarchy"></a>드릴다운 시 계층 구조 필요
시각적 계층 구조가 있는 경우 추가 세부 정보를 드릴다운할 수 있습니다. 예를 들어 스포츠, 규칙 및 이벤트로 구성된 계층별로 올림픽 메달 개수를 표시하는 시각화를 할 수 있습니다. 기본적으로 시각화는 체조, 스키, 수상 운동 등 스포츠별로 메달 수를 표시하게 됩니다. 하지만 계층 구조가 있기 때문에 시각적 요소 중 하나를 선택하면(예: 바, 라인 또는 버블) 점점 더 자세한 그림을 표시하게 됩니다. 수영, 다이빙, 수구에 대한 데이터를 보려면 **수상 운동** 요소를 선택합니다.  스프링보드, 플랫폼, 싱크로나이즈드 다이빙 이벤트에 대한 세부 정보를 보려면 **다이빙** 요소를 선택합니다.

사용자가 소유한 보고서에 계층 구조를 추가할 수 있지만 사용자와 공유한 보고서에는 계층 구조를 추가할 수 없습니다.
Power BI 시각화에 계층 구조가 포함되어 있는 것이 확실한가요?  시각화를 마우스로 가리키고 상단 모서리에서 이러한 드릴 컨트롤이 보이면 시각화에 계층이 있는 것입니다.

![](media/power-bi-visualization-drill-down/power-bi-drill-icon4.png)  ![](media/power-bi-visualization-drill-down/power-bi-drill-icon2.png)  ![](media/power-bi-visualization-drill-down/power-bi-drill-icon3.png)
![](media/power-bi-visualization-drill-down/power-bi-drill-icon5.png) ![](media/power-bi-visualization-drill-down/power-bi-drill-icon6.png)  

날짜는 계층 구조의 고유 형식입니다. 시각화에 날짜 필드를 추가한 경우 Power BI에서 년, 분기, 월 및 일을 포함하는 시간 계층 구조를 자동으로 추가합니다. 자세한 내용은 [시각적 계층 구조 및 드릴 다운 동작](guided-learning/visualizations.yml?tutorial-step=18)을 참조하거나 아래 비디오를 시청 하세요.


  <iframe width="560" height="315" src="https://www.youtube.com/embed/MNAaHw4PxzE?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

> [!NOTE]
> Power BI Desktop을 사용하여 계층을 만드는 방법에 자히 알아보려면 [계층 만들고 추가하는 방법](https://youtu.be/q8WDUAiTGeU) 비디오를 시청하세요.
> 
> 

## <a name="two-methods-to-drill-down"></a>두 가지 드릴다운 방법
시각화에서 두 가지 방식으로 드릴다운 및 드릴업할 수 있습니다.  둘 다 이 문서에 설명되어 있습니다. 두 방법이 모두 동일한 작업을 완료하므로 가장 즐길 수 있는 쪽을 사용합니다.

> [!NOTE]
> 과정을 따르려면 Power BI 서비스에서 [소매점 분석 샘플을 열고](sample-datasets.md) **지역**, **도시**, **우편번호** 및 **이름**(그룹)별로 **올해 총 단위**(값)를 보여주는 트리맵을 만듭니다.  
> 
> 

## <a name="method-one-for-drill-down"></a>드릴 다운의 경우 첫 번째 메서드
이 메서드는 자체 시각화의 위쪽 코너에 표시되는 드릴 아이콘을 사용합니다.

1. Power BI에서 [읽기용 보기 또는 편집용 보기](service-reading-view-and-editing-view.md)로 보고서를 엽니다. 드릴을 위해서는 계층 구조를 갖는 시각화가 필요합니다. 
   
   계층 구조는 아래 애니메이션에 표시됩니다.  시각화는 지역, 도시, 우편번호 및 도시 이름으로 구성된 계층 구조로 이루어집니다. 예를 들면 각 지역에 하나 이상의 도시가 있고 각 도시에 하나 이상의 우편 번호가 있습니다. 기본적으로 지역은 목록에서 첫 번째로 표시되기 때문에 시각화는 지역 데이터만 표시합니다.
   
   ![](media/power-bi-visualization-drill-down/power-bi-hierarcy-list.png)
2. 드릴다운을 사용하도록 설정하려면 시각화 오른쪽 위에 있는 화살표 아이콘을 선택합니다. 아이콘이 어두운 색이면 드릴이 활성화된 것입니다. 드릴을 사용하지 않는 경우 시각적 요소(예: 막대 또는 버블)를 선택하면 보고서 페이지의 다른 차트를 교차 필터링합니다.    
   
   ![](media/power-bi-visualization-drill-down/power-bi-drill-icon.png)
3. **한 번에 한 필드씩** 드릴다운하려면 시각화에서 요소 중 하나를 선택합니다. 즉, 가로 막대형 차트에서 가로 막대 중 하나를 클릭합니다. 즉, 트리 맵에서 **리프** 중 하나를 클릭합니다. 드릴다운하고 다시 백업할 때 제목이 바뀌는 것을 인식합니다. 이 애니메이션에서 제목은 "권역별 올해 총 단위"에서 "지역 및 도시별 올해 총 단위", "지역, 도시, 우편번호 별 올해 총 단위", "지역, 도시, 우편 번호, 이름별 올해 총 단위"로 변경됩니다. 다시 드릴업하려면 아래에 표시된 대로 시각화의 왼쪽 위 모서리에 있는 **드릴업** 아이콘 ![](media/power-bi-visualization-drill-down/power-bi-drill-icon5.png)을 선택합니다.
   
   ![](media/power-bi-visualization-drill-down/drill.gif)
4. ***한 번에 모든 필드***를 드릴다운하려면 시각화 왼쪽 위 모서리에 있는 양방향 화살표를 선택합니다.
   
   ![](media/power-bi-visualization-drill-down/pbi_drillall.png)
5. 다시 드릴업하려면 시각화 왼쪽 위에 있는 위쪽 화살표를 선택합니다.
   
   ![](media/power-bi-visualization-drill-down/pbi_drillup2.png)

## <a name="method-two-for-drill-down"></a>드릴 다운의 경우 두 번째 메서드
이 메서드는 상위 Power BI 메뉴 모음에서 **탐색**을 사용합니다.

1. Power BI에서 [읽기용 보기 또는 편집용 보기](service-reading-view-and-editing-view.md)로 보고서를 엽니다. 드릴을 위해서는 계층 구조를 갖는 시각화가 필요합니다. 
   
   계층 구조는 아래 이미지로 표시됩니다.  시각화는 지역, 도시, 우편번호 및 도시 이름으로 구성된 계층 구조로 이루어집니다. 예를 들면 각 지역에 하나 이상의 도시가 있고 각 도시에 하나 이상의 우편 번호가 있습니다. 기본적으로 지역은 목록에서 첫 번째로 표시되기 때문에 시각화는 지역 데이터만 표시합니다.
   
   ![](media/power-bi-visualization-drill-down/power-bi-hierarcy-list.png)
2. 드릴다운을 사용하려면 시각화를 선택하여 활성화하고 Power BI의 상위 메뉴 모음에서 **탐색** > **드릴다운**을 선택합니다. 시각화 오른쪽 위 모서리에 있는 드릴다운 아이콘이 검은색 배경으로 변경됩니다. ![](media/power-bi-visualization-drill-down/power-bi-drill-icon2.png)  
   
   ![](media/power-bi-visualization-drill-down/power-bi-explore2.png)
3. 활성화되면 트리맵 잎 중 하나를 선택하여 한 번에 하나의 필드를 드릴다운합니다. 이 예제에서는 도시별로 노스캐롤라이나의 올해 총 판매량을 보기 위해 **NC** 지역을 선택했습니다.
   
   ![](media/power-bi-visualization-drill-down/power-bi-drilldown-1.png)
4. 모든 필드를 한 번에 드릴다운하려면 **탐색** > **다음 수준 표시**를 선택합니다.
   
   ![](media/power-bi-visualization-drill-down/power-bi-show-next-level.png)
5. 드릴 백업하려면 **탐색** > **드릴업**을 선택합니다.
   
   ![](media/power-bi-visualization-drill-down/power-bi-drill-up2.png)

6. 시각적 개체를 만드는 데 사용된 데이터를 보려면 **데이터 참조**를 선택합니다. 데이터는 시각적 개체 아래 창에 표시됩니다. 시각적 개체를 계속 드릴하는 동시에 이 창이 계속 유지됩니다. 자세한 내용은 [시각적 개체를 만드는 데 사용할 데이터 표시](service-reports-show-data.md)를 참조하세요.

## <a name="understanding-the-hierarchy-axis-and-hierarchy-group"></a>계층 구조 축 및 계층 구조 그룹 이해
계층 구조 축 및 계층 구조 그룹을 보려는 데이터의 세분성을 늘리거나 줄이는 데 사용할 수 있는 메커니즘으로 생각할 수 있습니다. 범주 및 하위 범주로 구성할 수 있는 데이터는 계층 구조를 가진 것으로 한정합니다. 물론 여기에 날짜와 시간이 포함됩니다.

**값** 웰에서 데이터 필드로 검사하려는 데이터와 함께 **축** 웰 또는 **그룹** 웰 중 하나에 추가할 하나 이상의 데이터 필드를 선택하여 계층 구조를 포함하도록 Power BI에서 시각화를 만들 수 있습니다. 드릴 모드 아이콘이 시각화의 왼쪽 및 오른쪽 모서리에 표시되는 경우 데이터가 계층적인지 알 수 있습니다. 

기본적으로 두 가지 형식의 계층적 데이터를 고려하는 것이 좋습니다.
- 날짜 및 시간 데이터 - 날짜/시간 데이터 형식을 포함한 데이터 필드가 있으면 계층적 데이터입니다. Power BI는 [DateTime](https://msdn.microsoft.com/library/system.datetime.aspx) 구조로 값을 구문 분석할 수 있는 데이터 필드에 자동으로 계층 구조를 만듭니다. **축** 또는 **그룹**에 날짜/시간 필드를 하나 추가하기만 하면 됩니다.
- 범주 데이터 - 데이터가 하위 컬렉션을 포함하는 컬렉션에서 파생된 경우입니다. 또는 그렇지 않은 경우 공통 값을 공유하는 데이터 행이면 계층적 데이터입니다.

Power BI를 사용하면 하나 또는 모든 하위 집합을 확장할 수 있습니다. 데이터를 다운드릴하여 각 수준에서 단일 하위 집합을 보거나 동시에 각 수준에서 모든 하위 집합을 볼 수 있습니다. 예를 들어 계층 구조를 따라서 특정 연도에 대해 드릴다운하거나 각 연도 대한 모든 결과를 확인할 수 있습니다. 반대로 동일한 방식으로 드릴업할 수 있습니다.

다음 섹션에서는 가장 높은 보기, 중간 보기 및 가장 낮은 보기에서 드릴다운을 설명합니다.

### <a name="hierarchical-data-and-time-data"></a>계층적 데이터 및 시간 데이터
예를 들어 [소매 분석 샘플](sample-datasets.md)을 따라 **TotalSales**(값) 별로 **월**(축)을 보는 세로 막대형 누적 차트 시각화를 만듭니다.  

축 데이터 필드가 **월**인 경우라도 **축**에서 **연도** 범주를 생성합니다. Power BI가 읽어 온 모든 값에 대한 전체 날짜/시간 구조를 제공하기 때문입니다. 계층 구조의 상단에서는 연도에 대한 데이터를 표시합니다.

![](media\power-bi-visualization-drill-down/power-bi-hierarchical-axis-datetime-1.png)

드릴다운 모드에서 차트에서 막대를 클릭하여 계층 구조의 한 수준 아래로 이동합니다. 분기의 데이터에 세 개의 막대 차트가 사용할 수 있다고 표시됩니다. 그런 다음, 왼쪽 상단 아이콘에서 **계층 구조의 한 수준 아래로 모두 확장**을 선택합니다. 다시 이 작업을 수행하여 계층 구조의 가장 낮은 수준으로 이동하면 각 월에 대한 결과를 보여줍니다.

![](media\power-bi-visualization-drill-down/power-bi-hierarchical-axis-datetime-2.png)

시각화 외에도 각 보고서에 대해 렌더링된 데이터에 반영되는 계층 구조를 볼 수 있습니다. 다음 표에서는 단일 월 또는 모든 월에서 드릴다운한 보고서에 있는 **데이터 표시** 결과를 보여줍니다. 

데이터가 분기 및 연도 보고서에 대해 동일하지만 **값**에 지정된 수준으로 드릴다운한 후에 단일 보고서를 보다 구체적으로 만드는 방법 및 "모든 월" 보고서에 추가 데이터를 포함하는 방법을 확인할 수 있습니다.


|확장 모드|연도|분기|월|일|
| ---|:---:|:---:|:---:|---|
|단일|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-year.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-quarter.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-one-month.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-one-day.png)|
|모두|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-year.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-quarter.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-all-month.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-all-day.png)|


### <a name="hierarchical-category-data"></a>계층적 범주 데이터
컬렉션 및 하위 컬렉션에서 모델링된 데이터는 계층적입니다. 위치 데이터가 좋은 예입니다. 열이 국가, 주, 도시 및 우편 번호인 데이터 원본에 있는 테이블을 가정합니다. 동일한 국가, 주 및 도시를 공유하는 데이터는 계층적입니다.

예를 들어 [소매 분석 샘플](sample-datasets.md)을 따릅니다. **권역**, **도시**, **우편 번호** 및 **이름**(그룹)별 **올해 총 단위**(값)을 확인하는 세로 막대형 누적 차트 시각화를 만듭니다.  

![](media\power-bi-visualization-drill-down/power-bi-hierarchical-axis-category-1.png)

드릴 다운 모드로 왼쪽 상단 아이콘에서 세 번 **계층 구조의 한 수준 아래로 모두 확장**을 선택합니다.
권역, 도시 및 우편 번호에 대한 결과를 보여주는 계층 구조의 최하위 수준에 있어야 합니다.

![](media\power-bi-visualization-drill-down/power-bi-hierarchical-axis-category-2.png)

시각화 외에도 각 보고서에 대해 렌더링된 데이터에 반영되는 계층 구조를 볼 수 있습니다. 다음 표에서는 단일 지역 또는 모든 지역에 대해 드릴다운한 보고서에서 **데이터 표시** 결과를 보여줍니다. 드릴다운하면 단일 보고서를 보다 구체적으로 만드는 방법 및 "모든 지역" 보고서에 추가 데이터를 포함하는 방법을 확인할 수 있습니다.


| 확장 모드|지역|시|우편 번호|이름|
| ---|:---:|:---:|:---:|---|
|단일|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-territory.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-one-territory-city.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-one-territory-city-postal.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-one-territory-city-postal-name.png)|
|모두|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-territory.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-all-territory-city.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-all-territory-city-postal.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-all-territory-city-postal-name.png)|


## <a name="considerations-and-limitations"></a>고려 사항 및 제한 사항
* 시각화에 날짜 필드를 추가하여 계층을 만들지 않는 경우 "날짜" 필드는 실제로 날짜로 저장되지 않을 수 있습니다. 데이터 집합을 소유하는 경우 Power BI Desktop에서 *데이터* 보기에서 열고, 날짜를 포함하는 열을 선택하고 모델링 탭에서 **데이터 형식**을 **날짜** 또는 **날짜/시간**으로 변경합니다. 보고서를 사용자와 공유하는 경우 변경을 요청하려면 소유자에 게 문의합니다.  
  
  ![](media/power-bi-visualization-drill-down/power-bi-change-data-type2.png)

## <a name="next-steps"></a>다음 단계
[Power BI 보고서의 시각화](power-bi-report-visualizations.md)

[Power BI 보고서](service-reports.md)

[Power BI - 기본 개념](service-basic-concepts.md)

궁금한 점이 더 있나요? [Power BI 커뮤니티를 이용하세요.](http://community.powerbi.com/)

