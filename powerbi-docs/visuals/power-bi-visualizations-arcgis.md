---
title: 사용자와 공유한 ArcGIS 지도와 상호 작용
description: 읽기용 보기에서 보고서 소비자로 ArcGIS Map for Power BI 시각적 개체 사용
author: mihart
ms.reviewer: willt, lukasz
featuredvideoid: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 11/18/2019
ms.author: mihart
ms.openlocfilehash: 1e141c56387e4bbde1741752e40e600c37088e87
ms.sourcegitcommit: 768e1e4b19fe8c7627010127c2420d63021cb542
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/20/2019
ms.locfileid: "74199465"
---
# <a name="interacting-with-arcgis-maps-in-power-bi"></a>Power BI에서 ArcGIS 지도와 상호 작용
이 토픽은 Power BI 서비스, 데스크톱 또는 모바일에서 ArcGIS 지도를 사용하는 사람의 관점에서 작성되었습니다. 디자이너가 ArcGIS map for Power BI 시각적 개체를 공유하면 여러 가지 방법으로 해당 시각적 개체와 상호 작용할 수 있습니다.  ArcGIS 지도를 작성하는 방법에 대한 자세한 내용은 [ArcGIS maps by Esri tutorial](../visuals/power-bi-visualization-arcgis.md)(Esri에서 제공하는 ArcGIS 지도 자습서)을 참조하세요.

ArcGIS 지도와 Power BI의 조합은 지도에서 요소의 표현을 넘어서 완전히 새로운 수준으로 매핑합니다. 보고서 디자이너는 지도를 시작하고 인구 통계 데이터 계층을 해당 지도에 연결합니다. 공간 분석과 지도의 위치 기반 데이터 계층(인구 조사 데이터 등)의 조합을 통해 시각화의 데이터를 자세히 이해할 수 있습니다.

> [!TIP]
> GIS는 Geographic Information System(지리적 정보 시스템)의 약자입니다.
> 

이 ArcGIS map for Power BI 시각적 개체는 지난해 도시별 판매액을 보여 주며 주소 기본 지도와 평균 가구 소득 참조 계층을 사용합니다. 지도에는 두 개의 핀(빨간색과 노란색)과 하나의 운행 시간 반경(자주색)이 포함되어 있습니다.

![거품, 핀 및 드라이브 시간과 함께 미국을 보여 주는 ArcGIS 지도](media/power-bi-visualizations-arcgis/power-bi-arcgis-esri.png)

> [!TIP]
> [Power BI의 Esri 페이지](https://www.esri.com/powerbi)를 방문하여 많은 예제를 참조하고 추천서를 봅니다. 그런 다음, Esri의 [ArcGIS Maps for Power BI 시작 페이지](https://doc.arcgis.com/en/maps-for-powerbi/get-started/about-maps-for-power-bi.htm)를 참조하세요.
> 
> 

## <a name="user-consent"></a>사용자 동의

동료가 처음으로 ArcGIS 지도를 공유하면 Power BI에 동의 프롬프트가 표시됩니다. ArcGIS Maps for Power BI는 Esri(https://www.esri.com) 에서 제공하며 ArcGIS Maps for Power BI 사용은 Esri의 사용 약관 및 개인정보처리방침에 따릅니다. Power BI용 ArcGIS Maps 시각적 개체를 사용할 Power BI 사용자는 승인 대화 상자를 수락해야 합니다.


## <a name="understand-the-layers"></a>계층 이해

ArcGIS Maps for Power BI 시각적 개체에는 여러 가지 유형의 인구 통계 위치 정보 계층이 있을 수 있습니다.

### <a name="base-maps"></a>기본 지도

각 ArcGIS Maps for Power BI 시각적 개체는 기본 지도에서 시작합니다. 기본 지도를 데이터의 캔버스라고 생각하면 됩니다. 기본 지도는 어둡거나 밝은 기본 캔버스이거나

![어두운 회색 기본 지도](media/power-bi-visualizations-arcgis/power-bi-basemap-dark.png) 

주소 및 교통 정보가 포함된 캔버스일 수 있습니다. 

![어두운 회색 기본 지도](media/power-bi-visualizations-arcgis/power-bi-streets-basemap.png)  

기본 지도는 캔버스 전체에 적용됩니다. 즉, 이동하고 확대/축소하면 지도가 업데이트됩니다. 확대하면 보다 자세한 주소 및 교통 정보가 표시되며, 대륙 간을 이동해도 정보 수준은 일정하게 유지됩니다. 여기서는 Porto에서 Beijing으로 이동했습니다.

![주소 기본 지도](media/power-bi-visualizations-arcgis/power-bi-basemap-pan.png)  

### <a name="reference-layers"></a>참조 계층

보고서 ‘디자이너’는 하나의 참조 계층을 추가할 수 있습니다.  참조 계층은 Esri에서 호스트되며 위치에 대한 인구 통계 정보의 추가 계층을 제공합니다. 아래 예제에는 인구 밀도에 대한 참조 계층이 있습니다. 더 어두운색은 더 높은 밀도를 나타냅니다.

![인구 밀도를 보여 주는 Orlando 영역 지도](media/power-bi-visualizations-arcgis/power-bi-reference.png)  

### <a name="infographics"></a>인포그래픽

보고서 ‘디자이너’는 여러 개의 인포그래픽 계층을 추가할 수 있습니다.  인포그래픽은 시각적 개체 캔버스의 오른쪽을 따라 표시되는 빠른 시각적 표시기입니다. 인포그래픽은 Esri에서 호스트되며 위치에 대한 인구 통계 정보의 추가 계층을 제공합니다. 아래 예제에는 세 가지 인포그래픽이 적용되어 있습니다. 지도 자체에는 표시되지 않지만 카드에는 표시됩니다. 인포그래픽 카드는 지도에서 영역을 확대/축소하고, 이동하고, 선택하면 업데이트됩니다.

![캔버스 오른쪽을 따라 인포그래픽이 표시되고 확대된 Orlando 영역 지도](media/power-bi-visualizations-arcgis/power-bi-infographics.png)  

### <a name="pins"></a>핀

핀은 도시나 주소 같은 정확한 위치를 나타냅니다. 경우에 따라 보고서 ‘디자이너’는 운행 시간 반경에 핀을 사용합니다.  이 예제에서는 North Carolina, Charlotte의 50마일 반경 내에 있는 매장을 보여 줍니다.


![NC, Charlotte 주변 운행 시간](media/power-bi-visualizations-arcgis/power-bi-drive-times.png) 


## <a name="interact-with-an-arcgis-maps-for-power-bi-visual"></a>ArcGIS Maps for Power BI 시각적 개체와 상호 작용
사용 가능한 기능은 보고서가 공유된 방법 및 Power BI 계정 유형에 따라 달라집니다. 질문 사항이 있으면 시스템 관리자에게 문의하세요. ArcGIS Maps for Power BI 시각적 개체는 보고서의 다른 시각적 개체와 매우 비슷하게 작동합니다. [시각화를 만드는 데 사용된 데이터를 표시](../consumer/end-user-show-data.md)하고, [포커스 모드 및 전체 화면 모드](../consumer/end-user-focus.md)로 지도를 표시하며, [주석을 추가](../consumer/end-user-comment.md)하고, 보고서 ‘디자이너’가 설정한 [필터와 상호 작용](../consumer/end-user-report-filter.md)하는 등의 기능을 사용할 수 있습니다.  ArcGIS 시각적 개체는 보고서 페이지의 다른 시각적 개체를 교차 필터링할 수 있으며 그 반대의 경우도 마찬가지입니다.

기본 지도 위치(예: 거품형)를 마우스로 가리켜 도구 설명을 표시합니다. 또한 ArcGIS 시각적 개체 선택 도구를 사용하여 추가 도구 설명을 표시하고 기본 지도 또는 참조 계층에서 특정 항목을 선택합니다.  

### <a name="selection-tools"></a>선택 도구

ArcGIS Maps for Power BI에서는 5가지 선택 모드를 사용할 수 있습니다. 최대 250개 데이터 요소를 한 번에 선택할 수 있습니다.

![3개의 선택 도구를 모두 보여 주는 스크린샷](media/power-bi-visualizations-arcgis/power-bi-esri-selection-tools.png)

#### <a name="the-single-select-tool"></a>단일 선택 도구

![단일 선택 도구를 보여 주는 스크린샷](media/power-bi-visualizations-arcgis/power-bi-esri-selection-single2.png) 

참조 계층에서 데이터 요소, 거품형, 핀 또는 개별 데이터 요소를 선택합니다. Power BI는 선택 항목에 대한 세부 정보와 함께 도구 설명을 표시합니다. 단일 선택에서는 선택 항목에 따라 보고서 페이지의 다른 시각적 개체를 교차 필터링하고 선택한 영역에 대한 인포그래픽 키드를 업데이트합니다. 

여기서는 기본 지도의 갈색 거품형 데이터 요소를 선택했습니다. Power BI는 다음을 수행합니다.
- 선택 항목을 강조 표시합니다.
- 해당 데이터 요소에 대한 도구 설명을 표시합니다. 
- 인포그래픽 카드를 업데이트하여 선택 항목에 대한 데이터만 표시합니다.
- 세로 막대형 차트를 교차 강조 표시합니다.

![갈색 거품형에 대한 도구 설명의 스크린샷](media/power-bi-visualizations-arcgis/power-bi-single-selects.png)

지도에 참조 계층이 있는 경우 위치를 선택하면 도구 설명에 세부 정보가 표시됩니다. 여기서는 Seneca County를 선택했으며 보고서 ‘디자이너’가 지도에 추가한 참조 계층(인구 밀드)의 데이터가 표시됩니다.  이 예제에서는 데이터 요소에 두 개의 다른 지방이 포함되어 도구 설명이 두 페이지입니다. 각 페이지에는 차트가 있습니다. 차트에서 막대를 선택하여 추가 세부 정보를 표시합니다. 

![Seneca County에 대한 도구 설명의 스크린샷](media/power-bi-visualizations-arcgis/power-bi-single-select-ref.png)

> [!TIP]
  > 경우에 따라 확대하여 특정 위치를 선택하면 도구 설명 페이지 수를 줄일 수 있습니다.  위치가 겹치는 경우 Power BI에서 한 번에 1개 이상의 도구 설명을 제공할 수 있습니다. 화살표를 선택하여 도구 설명 사이를 이동합니다.
  > 
  > ![세 페이지를 표시하는 도구 설명](media/power-bi-visualizations-arcgis/power-bi-3-screens.png)

#### <a name="the-multi-select-tool"></a>다중 선택 도구

![다중 선택 도구](media/power-bi-visualizations-arcgis/power-bi-esri-selection-marquee2.png) 

지도에 사각형을 그린 후 포함된 데이터 요소를 선택합니다. CTRL 키를 사용하여 둘 이상의 직사각형 영역을 선택합니다. 다중 선택에서는 선택한 영역에 대한 인포그래픽 카드를 업데이트하고 선택 항목에 따라 보고서 페이지의 다른 시각적 개체를 교차 강조 표시합니다.

![다중 선택 도구](media/power-bi-visualizations-arcgis/power-bi-multi-select.png) 

#### <a name="the-reference-layer-tool"></a>참조 계층 도구

![경계에 대한 세 번째 선택 도구](media/power-bi-visualizations-arcgis/power-bi-esri-selection-reference-layer2.png) 

사용할 참조 계층에 사용된 경계 또는 다각형을 통해 포함된 데이터 요소를 선택합니다. 잘 보이지는 않지만 참조 계층에는 노란색 윤곽선이 있습니다. 단일 선택 도구와 달리 도구 설명이 표시되지 않습니다. 대신 해당 윤곽선의 테두리 내에 포함된 데이터 요소에 대한 데이터를 가져옵니다. 이 예제의 선택 항목에는 데이터 요소가 포함되며 Winston Salem의 Lindseys 매장에 대한 것입니다.

![참조 선택 도구](media/power-bi-visualizations-arcgis/power-bi-ref-tool.png) 

#### <a name="the-buffer-tool"></a>버퍼 도구

![버퍼에 대한 네 번째 선택 도구](media/power-bi-visualizations-arcgis/power-bi-esri-selection-4.png) 

버퍼 계층을 사용하여 데이터 요소를 선택할 수 있습니다. 예를 들어 이 도구를 사용하여 운행 시간 반경을 선택하고 보고서의 나머지 부분과 계속 상호 작용할 수 있습니다. 운행 시간 반경은 활성 상태로 유지되고 인포그래픽 카드에는 운행 시간 반경이 계속 반영되지만 지도에서 다른 데이터 요소를 선택하면 보고서 페이지의 다른 시각적 개체를 교차 필터링합니다.

![버퍼 선택 도구](media/power-bi-visualizations-arcgis/power-bi-buffer.png) 

#### <a name="the-find-similar-tool"></a>유사 항목 찾기 도구

![유사성을 위한 다섯 번째 선택 도구](media/power-bi-visualizations-arcgis/power-bi-esri-selection-reference5.png) 

유사한 특성이 있는 위치를 찾을 수 있습니다. 먼저 하나 이상의 관심 요소나 참조 위치를 선택하고 분석에서 사용할 차원을 최대 5개까지 정의합니다. 그러면 유사 항목 찾기는 정의된 참조 위치와 가장 유사한 위치 10개를 지도에서 계산합니다. 그런 다음, 인포그래픽 카드를 사용하여 각 결과에 대한 인구 통계 정보를 자세히 알아보거나, 운행 시간 영역을 만들어 이러한 각 위치의 주행 거리 내에 있는 항목을 파악하거나, 유사 항목 찾기 도구 자체를 사용하여 보고서를 필터링하고 더 많은 인사이트를 얻을 수도 있습니다. 가장 중요한 점은 모든 계산이 머신에서 로컬로 수행되므로 기밀 데이터가 보호된 상태로 유지되도록 할 수 있습니다.


## <a name="considerations-and-limitations"></a>고려 사항 및 제한 사항
Power BI용 ArcGIS Maps는 다음과 같은 서비스 및 애플리케이션에서 사용할 수 있습니다.

|서비스/앱  |가용성  |
|---------|---------|
|Power BI Desktop     |     예    |
|Power BI 서비스(app.powerbi.com)     |    예     |
|Power BI 모바일 애플리케이션     |  예      |
|Power BI 웹에 게시     |  아니요       |
|Power BI Embedded     |     아니요    |
|Power BI 서비스 포함(PowerBI.com)  | 아니요 |


## <a name="how-do-arcgis-maps-for-power-bi-work-together"></a>ArcGIS Maps for Power BI가 함께 작동하는 방식
ArcGIS Maps for Power BI는 Esri(https://www.esri.com) 에서 제공합니다. ArcGIS Maps for Power BI의 사용은 Esri의 [사용 약관](https://go.microsoft.com/fwlink/?LinkID=8263222) 및 [개인정보처리방침](https://go.microsoft.com/fwlink/?LinkID=826323)에 따릅니다. Power BI용 ArcGIS Maps 시각적 개체를 사용할 Power BI 사용자는 승인 대화 상자를 수락해야 합니다(자세한 내용은 사용자 동의 참조).  Esri의 ArcGIS Maps for Power BI 사용은 승인 대화 상자에서도 연결되는 Esri의 사용 약관 및 개인정보처리방침에 따릅니다. 각 사용자는 처음으로 ArcGIS Maps for Power BI를 사용하기 전에 동의해야 합니다. 사용자가 동의하면 시각적 개체에 바인딩된 데이터는 지오코딩을 위해 Esri의 서비스로 전송됩니다. 즉, 위치 정보를 맵에 표시될 수 있는 위도 및 경도 정보로 변환하는 것입니다. 데이터 시각화에 바인딩된 모든 데이터를 Esri의 서비스에 보낼 수 있다고 가정해야 합니다. Esri에서는 기본 맵, 공간 분석, 지오코딩 등와 같은 서비스를 제공합니다. ArcGIS Maps for Power BI 시각적 개체는 Esri에서 제공되고 유지 관리되는 인증서에 의해 보호되는 SSL 연결을 사용하여 이러한 서비스와 상호 작용합니다. ArcGIS Maps for Power BI에 대한 추가 정보는 Esri의 [ArcGIS Maps for Power BI 제품 페이지](https://www.esri.com/powerbi)에서 가져올 수 있습니다.

### <a name="power-bi-plus"></a>Power BI Plus

![더하기 아이콘을 선택하여 등록 또는 로그인](media/power-bi-visualizations-arcgis/power-bi-plus.png)

ArcGIS Maps for Power BI를 통해 Esri에서 제공하는 Plus 구독에 등록한 사용자는 Esri와 직접적인 관계를 갖게 됩니다. Power BI는 Esri에 사용자에 대한 개인 정보를 전송하지 않습니다. 사용자가 고유한 AAD ID를 사용하여 Esri 제공 AAD 애플리케이션에 로그인하고 트러스트합니다. 이렇게 하면 사용자는 Esri와 개인 정보를 직접 공유하게 됩니다. 사용자가 ArcGIS Maps for Power BI 시각적 개체에 Plus 콘텐츠를 추가하면 해당 시각적 개체를 보거나 편집하려는 동료에게도 Esri의 Plus 구독이 필요합니다. 

Esri의 ArcGIS Maps for Power BI가 작동하는 방법에 대한 기술적인 세부 질문은 해당 지원 사이트를 통해 Esri에 문의하세요.

## <a name="considerations-and-troubleshooting"></a>고려 사항 및 문제 해결

**ArcGIS 지도가 표시되지 않는 경우**    
Power BI용 ArcGIS Maps를 사용할 수 없는 서비스 또는 애플리케이션에서 시각화는 빈 Power BI 로고와 함께 빈 시각적 개체로서 표시합니다.

**지도에 내 정보가 일부 표시되지 않는 경우**    
지도에 위도/경도를 지오코딩할 경우 최대 30,000개의 데이터 요소가 표시됩니다. 우편 번호 또는 거리 주소와 같은 데이터 요소를 지오코딩하면 처음 15,000개의 데이터 요소만 지오코딩됩니다. 지오코딩 장소 이름 또는 국가는 1500개 주소 제한에 적용되지 않습니다.

**Power BI용 ArcGIS Maps를 사용하는 경우 요금이 부과됩니까?**

Power BI용 ArcGIS Maps는 추가 비용 없이 모든 Power BI 사용자가 사용할 수 있습니다. **Esri**에서 제공하는 구성 요소이며, 이 문서의 앞 부분에서 설명했듯이 **Esri**의 사용 약관 및 개인정보처리방침에 따라 사용할 수 있습니다. ArcGIS **Plus**를 구독하면 비용이 청구됩니다.

**내 캐시가 가득 찼다는 오류 메시지가 나타나는 경우**

이 동작은 해결 중인 버그입니다.  오류 메시지에 나타나는 링크를 선택하여 Power BI 캐시 지우기에 대한 지침을 참조합니다.

**오프라인에서 ArcGIS 지도를 볼 수 있습니까?**

아니요, 지도를 표시하려면 Power BI는 네트워크 연결이 필요합니다.

## <a name="next-steps"></a>다음 단계
도움말 가져오기: **Esri**에서는 **Power BI용 ArcGIS Maps** 기능 모음에 대한 [종합적인 설명서](https://go.microsoft.com/fwlink/?LinkID=828772)를 제공하고 있습니다.

[**Power BI용 ArcGIS Maps**와 관련된 Power BI 커뮤니티](https://go.microsoft.com/fwlink/?LinkID=828771)에서 질문하고 최신 정보를 얻고 문제를 보고하고 대답을 찾을 수 있습니다.


[Power BI용 ArcGIS Maps 제품 페이지](https://www.esri.com/powerbi)
