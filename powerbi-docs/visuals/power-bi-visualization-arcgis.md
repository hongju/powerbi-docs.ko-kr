---
title: Power BI에서 ESRI로 ArcGIS 지도 만들기
description: 'Power BI에서 ESRI로 ArcGIS 지도 만들기 '
author: mihart
manager: kvivek
ms.reviewer: lukaszp
featuredvideoid: EKVvOZmxg9s
ms.service: powerbi
ms.subservice: powerbi-visuals
ms.topic: conceptual
ms.date: 02/10/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 6b3f1c3780b60efc2ade444960a92234afecc71e
ms.sourcegitcommit: 88ac51106ec7d0ead8c2a1550a11afae0d502bb9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56086589"
---
# <a name="arcgis-maps-in-power-bi-service-and-power-bi-desktop-by-esri"></a>Power BI 서비스 및 Power BI 데스크톱에서 Esri로 ArcGIS 지도 만들기
이 자습서는 ArcGIS 지도를 만드는 사용자의 관점에서 작성되었습니다. 작성자가 동료와 ArcGIS 지도를 공유하면 해당 동료는 지도를 보고 상호 작용할 수 있지만 변경 내용을 저장할 수 없습니다. ArcGIS 지도 보기에 대해 자세히 알아보려면 [ArcGIS 지도와 상호 작용](power-bi-visualizations-arcgis.md)을 참조하세요.

ArcGIS 지도와 Power BI의 조합은 지도에서 요소의 표현을 넘어서 완전히 새로운 수준으로 매핑합니다. 기본 지도, 위치 유형, 테마, 기호 스타일 및 참조 계층에서 선택하여 멋진 정보 제공용 지도 시각화를 만듭니다. 공간 분석과 지도의 신뢰할 수 있는 데이터 계층의 조합은 시각화에서 데이터의 심도 깊은 이해를 제공합니다.

 모바일 디바이스에서 ArcGIS 지도를 만들 수 없는 경우에도 지도를 보고 상호 작용할 수 있습니다. [ArcGIS 지도와 상호 작용](power-bi-visualizations-arcgis.md)을 참조하세요.

> [!TIP]
> GIS는 Geographic Information Systems(지리적 정보 시스템)의 약자입니다.


아래 예제에서는 2016 평균 가처분 소득의 인구 통계 계층에 대해 heatmap으로 지역 판매를 표시하는 데 진한 회색 캔버스를 사용합니다. 살펴봄으로써 알 수 있듯이 ArcGIS 지도를 사용하면 최상의 스토리를 알릴 수 있도록 거의 제한이 없는 향상된 매핑 기능, 인구 통계 데이터 및 눈을 뗄 수 없는 지도 시각화를 제공합니다.

![](media/power-bi-visualization-arcgis/power-bi-intro-arcgis.png)

> [!TIP]
> [Power BI의 esri 페이지](https://www.esri.com/powerbi)를 방문하여 많은 예제를 참조하고 추천서를 봅니다. 그런 다음 esri의 [Power BI용 ArcGIS 지도 시작 페이지](https://doc.arcgis.com/en/maps-for-powerbi/get-started/about-maps-for-power-bi.htm)를 참조하세요.

## <a name="user-consent"></a>사용자 동의
ArcGIS Maps for Power BI는 Esri(www.esri.com)에서 제공합니다. Power BI용 ArcGIS Maps의 사용은 Esri의 사용 약관 및 개인 정보 보호 정책에 따릅니다. Power BI용 ArcGIS Maps 시각적 개체를 사용할 Power BI 사용자는 승인 대화 상자를 수락해야 합니다.

**리소스**

[용어](https://go.microsoft.com/fwlink/?LinkID=826322)

[개인 정보 보호 정책](https://go.microsoft.com/fwlink/?LinkID=826323)

[Power BI용 ArcGIS Maps 제품 페이지](https://www.esri.com/powerbi)

<br/>

## <a name="enable-arcgis-map"></a>ArcGIS 지도 사용
ArcGIS 지도는 현재 Power BI 서비스, Power BI Desktop 및 Power BI 모바일에서 사용할 수 있습니다. 이 문서는 서비스 및 Desktop에 대한 지침을 제공합니다.

### <a name="enable-the-arcgis-map-in-power-bi-service-apppowerbicom"></a>***Power BI 서비스에서(app.powerbi.com)*** ArcGIS 지도 사용
이 자습서는 [소매점 분석 샘플](../sample-retail-analysis.md)을 사용합니다. **Power BI용 ArcGIS Maps**를 사용하려면:

1. 메뉴 모음의 오른쪽 윗부분에서 톱니 아이콘을 선택하고 **설정**을 엽니다.
   
    ![](media/power-bi-visualization-arcgis/power-bi-settings.png)
2. **Power BI용 ArcGIS Maps** 확인란을 선택합니다. 선택한 후에는 Power BI를 다시 시작해야 합니다.
   
    ![](media/power-bi-visualization-arcgis/power-bi-use-arcgis-new.png)
3. [편집용 보기](../consumer/end-user-reading-view.md)에서 보고서를 열고 시각화 창에서 Power BI용 ArcGIS Maps 아이콘을 선택합니다.
   
    ![](media/power-bi-visualization-arcgis/power-bi-viz-pane2.png)
4. Power BI에서 빈 ArcGIS 지도 템플릿을 보고서 캔버스에 추가합니다.
   
   ![](media/power-bi-visualization-arcgis/power-bi-esri-placeholder2new.png)

<br/>

## <a name="create-an-arcgis-map-visual"></a>ArcGIS 지도 시각적 개체 만들기
Will이 몇 가지 다른 ArcGIS 지도 시각화를 만드는 것을 지켜본 다음 아래 단계를 사용하여 [소매점 분석 샘플](../sample-datasets.md)로 직접 시도해 보십시오.

<iframe width="560" height="315" src="https://www.youtube.com/embed/EKVvOZmxg9s" frameborder="0" allowfullscreen></iframe>

1. **필드** 창에서 데이터 필드를 **위치** 또는 **위도** 및/또는 **경도** 버킷으로 끌어갑니다. 이 예에서는 **Store > City**를 사용합니다.
   
   > [!NOTE]
   > Power BI용 ArcGIS 맵은 선택한 필드가 지도 상에서 도형이나 점으로 가장 적절하게 표시되는지를 자동으로 감지합니다. 설정에서 기본값을 조정할 수 있습니다(아래 참조).
   > 
   > 
   
    ![](media/power-bi-visualization-arcgis/power-bi-fields-pane3new.png)
2. 시각화 창 ![](media/power-bi-visualization-arcgis/power-bi-arcgis-template.png)에서 템플릿을 선택하여 시각화를 ArcGIS 맵으로 변환합니다.
3. **필드** 창에서 측정값을 **크기** 버킷으로 끌어 데이터가 표시되는 모양을 조정합니다. 이 예에서는 **Sales > Last Year Sales**를 사용합니다.
   
    ![](media/power-bi-visualization-arcgis/power-bi-esri-point-map-size2new.png)

## <a name="settings-and-formatting-for-arcgis-maps"></a>ArcGIS 지도의 설정 및 서식 지정
**Power BI용 ArcGIS Maps** 서식 지정 기능에 액세스하려면 다음과 같이 수행합니다.

1. 시각화의 오른쪽 위 모서리에서 줄임표를 선택하고 **편집**을 선택하여 추가 기능에 액세스합니다.
   
   ![](media/power-bi-visualization-arcgis/power-bi-edit2.png)
   
   사용 가능한 기능이 시각화의 위쪽에 표시됩니다. 선택한 기능마다 자세한 옵션을 제공하는 작업 창이 열립니다.<br/>
   
   ![](media/power-bi-visualization-arcgis/power-bi-esri-features-new.png)
   
   > [!NOTE]
   > 설정 및 기능에 대한 자세한 내용은 아래의 **상세 설명**을 참조하세요.
   > 
   > 
2. 보고서로 돌아가려면 보고서 캔버스의 왼쪽 위 모서리에 있는 **보고서로 돌아가기**를 선택합니다.

<br/>

## <a name="detailed-documentation"></a>상세 설명
**Esri**에서는 **Power BI용 ArcGIS Maps** 기능 모음에 대한 [종합적인 설명서](https://go.microsoft.com/fwlink/?LinkID=828772)를 제공하고 있습니다.

## <a name="features-overview"></a>기능 개요
### <a name="base-maps"></a>기본 지도
4개의 기본 지도, 즉 진한 회색 캔버스, 연한 회색 캔버스, OpenStreetMap 및 도로 지도가 제공됩니다.  도로는 ArcGIS의 표준 기본 지도입니다.

기본 지도를 적용하려면 작업 창에서 선택합니다.

![](media/power-bi-visualization-arcgis/power-bi-esri-base-maps-new.png)

### <a name="location-type"></a>위치 유형
Power BI용 ArgGIS Maps는 자동으로 가장 적절한 방법을 감지하여 지도에 데이터를 표시합니다. 데이터를 표시하려면 포인트 또는 경계에서 선택합니다. 위치 유형 옵션을 사용하면 이러한 선택을 자세히 조정할 수 있습니다.

![](media/power-bi-visualization-arcgis/power-bi-esri-location-types-new.png)

**경계**는 표준 지리적 값이 데이터에 포함된 경우에만 작동됩니다. Esri는 지도에 표시할 도형을 자동으로 해석합니다. 표준 지리적 값에는 국가, 지방, 우편 번호 등이 포함됩니다. 하지만 지오코딩과 마찬가지로 Power BI에서도 기본적으로 경계인 필드인지 또는 데이터에 적합한 경계를 가지고 있는지를 자동으로 감지할 수 없습니다.  

### <a name="map-theme"></a>지도 테마
4 개 지도 테마가 제공됩니다. 위치에 바인딩한 필드에 기반하여 위치 전용 및 크기 테마가 자동으로 선택되고 Power BI 필드 창에서 **크기** 버킷에 추가됩니다. 여기서는 **열 지도(히트 맵)** 로 변경하기 위해 **크기**를 사용하겠습니다.  

![](media/power-bi-visualization-arcgis/power-bi-esri-map-theme-new.png)

<table>
<tr><th>테마</th><th>설명</th>
<tr>
<td>위치 전용</td>
<td>위치 유형 설정에 기반한 데이터 요소 또는 채워진 경계를 지도에 그립니다.</td>
</tr>
<tr>
<td>열 지도</td>
<td>지도에 데이터의 강도 도표를 그립니다.</td>
</tr>
<tr>
<td>크기</td>
<td>필드 창의 크기 버킷에 있는 값에 기반하여 크기가 조정된 데이터 요소를 지도에 그립니다.</td>
</tr>
<tr>
<td>클러스터링</td>
<td>지역에 속한 데이터 요소의 개수를 지도에 그립니다. </td>
</tr>
</table>


### <a name="symbol-style"></a>기호 스타일
기호 스타일을 사용하면 데이터가 지도에 표시되는 모양을 자세히 조정할 수 있습니다. 기호 스타일은 선택한 위치 유형과 지도 테마에 기반한 상황에 맞춰집니다. 아래 예제는 **크기**에 설정된 위치 유형과 몇 가지 투명도, 스타일 및 크기 조정을 보여줍니다.

![](media/power-bi-visualization-arcgis/power-bi-esri-symbol-style-new.png)

### <a name="pins"></a>핀
핀을 추가하여 지도의 지점에 주의를 환기시킵니다.  

1. **핀** 탭을 선택합니다.
2. 검색 상자에 키워드(예: 주소, 장소 및 관심 지점)를 입력하고 드롭다운에서 선택합니다. 지도에 기호가 나타나고 지도는 위치에 자동으로 확대합니다. 검색 결과는 핀 창에 위치 카드로서 저장됩니다. 최대 10개의 위치 카드를 저장할 수 있습니다.
   
   ![](media/power-bi-visualization-arcgis/power-bi-pin-arcgis-newer.png)
3. Power BI는 해당 위치에 핀을 추가하고 사용자는 핀의 색을 변경할 수 있습니다.
   
   ![](media/power-bi-visualization-arcgis/power-bi-pin-color-new.png)
4. 핀을 추가하고 삭제합니다.
   
   ![](media/power-bi-visualization-arcgis/power-bi-pin3.png)

### <a name="drive-time"></a>운행 시간
운행 시간 창에서는 위치를 선택한 다음 지정된 반경 또는 운행 시간 내에서 어떤 지도 기능이 있는지 확인할 수 있습니다.  
    ![](media/power-bi-visualization-arcgis/power-bi-esri-drive-time.png)

1. **운행 시간** 탭을 선택하고 단일 또는 다중 선택 도구를 선택합니다. 워싱턴 D.C.에 대한 핀을 선택한 단일 도구

   ![](media/power-bi-visualization-arcgis/power-bi-esri-single-select.png)
   
   > [!TIP]
   > 지도에서 확대하면 위치를 선택하기가 쉬워집니다(+ 아이콘 사용).
   > 
   > 
2. 몇 일 동안 워싱턴 D.C. 로 가서 적당한 운행 거리 내에 어떤 가계가 있는지 알아본다고 가정해보겠습니다. 검색 영역을 **반경**으로, 거리를 **50** 마일로 변경하고 확인을 선택합니다.    
   
    ![](media/power-bi-visualization-arcgis/power-bi-esri-drive-time-radius.png)
3. 반경은 자주색으로 표시됩니다. 위치를 선택하여 세부 정보를 표시합니다. 아니면 색 및 외곽선을 변경하여 변경 형식을 지정합니다.
   
    ![](media/power-bi-visualization-arcgis/power-bi-esri-drive-time.png)

### <a name="reference-layer"></a>참조 계층
#### <a name="reference-layer---demographics"></a>참조 계층 - 인구 통계
Power BI용 ArcGIS Maps에는 Power BI에서 상황에 맞게 데이터를 조정하는 데 유용한 인구 통계 계층이 제공됩니다.

1. **참조 계층** 탭, **인구 통계**를 차례로 선택합니다.
2. 나열되는 계층마다 확인란이 있습니다. 확인 표시를 추가하여 해당 계층을 지도에 추가합니다.  이 예에서는 평균 가구 소득을 추가했습니다.<br/>
   
    ![](media/power-bi-visualization-arcgis/power-bi-esri-reference-layer-demographic.png)
3. 각 계층 또한 대화형 계층입니다. 거품 위를 마우스로 가리키면 자세한 정보를 볼 수 있듯이 지도 상에서 음영 처리된 영역을 클릭하면 자세한 정보를 볼 수 있습니다.<br/>
   
    ![](media/power-bi-visualization-arcgis/power-bi-esri-reference-layer-details.png)

#### <a name="reference-layer---arcgis"></a>참조 계층 - ArcGIS
ArcGIS Online에서는 공용 웹 지도를 게시하는 조직을 위한 기능을 제공하고 있습니다. 또한 Esri에서는 Living Atlas를 통해 처리되는 웹 지도 모음도 제공하고 있습니다. ArcGIS 탭에서 모든 공용 웹 지도 또는 Living Atlas 지도를 검색하여 지도에 참조 계층으로 추가할 수 있습니다.

1. **참조 계층** 탭, **ArcGIS**를 차례로 선택합니다.
2. 검색 용어를 입력한 후 지도 계층을 선택합니다. 이 예에서는 미국 하원의원 선거구를 선택했습니다.
   
    ![](media/power-bi-visualization-arcgis/power-bi-esri-demographics-esri2-new.png)
3. 자세한 정보를 보려면 음영 처리된 영역을 선택하여 ‘참조 계층에서 선택’을 엽니다. 참조 계층 선택 도구를 사용하여 참조 계층에 있는 경계 또는 개체를 선택합니다.

<br/>

## <a name="selecting-data-points"></a>데이터 요소 선택
Power BI용 ArcGIS Maps에서는 세 가지 선택 모드를 사용할 수 있습니다.

다음과 같은 스위치를 사용하여 선택 모드를 변경합니다.

![](media/power-bi-visualization-arcgis/power-bi-esri-selection-tools2.png)

![](media/power-bi-visualization-arcgis/power-bi-esri-selection-single2.png) 개별 데이터 요소를 선택합니다.

![](media/power-bi-visualization-arcgis/power-bi-esri-selection-marquee2.png) 지도에 사각형을 그린 후 포함된 데이터 요소를 선택합니다.

![](media/power-bi-visualization-arcgis/power-bi-esri-selection-reference-layer2.png) 사용할 참조 계층에 사용된 경계 또는 다각형을 통해 포함된 데이터 요소를 선택합니다.

> [!NOTE]
> 최대 250개 데이터 요소를 한 번에 선택할 수 있습니다.
> 
> 

<br/>

## <a name="getting-help"></a>도움말 가져오기
**Esri**에서는 **Power BI용 ArcGIS Maps** 기능 모음에 대한 [종합적인 설명서](https://go.microsoft.com/fwlink/?LinkID=828772)를 제공하고 있습니다.

[**Power BI용 ArcGIS Maps**와 관련된 Power BI 커뮤니티](https://go.microsoft.com/fwlink/?LinkID=828771)에서 질문하고 최신 정보를 얻고 문제를 보고하고 대답을 찾을 수 있습니다.

개선을 위해 제안할 사항이 있으면 [Power BI 아이디어 목록](https://ideas.powerbi.com)에 제출해 주십시오.

<br/>

## <a name="managing-use-of-arcgis-maps-for-power-bi-within-your-organization"></a>조직 내 Power BI용 ArcGIS Maps 사용 관리
Power BI에는 Power BI용 ArcGIS Maps를 사용할지 여부를 관리하기 위해 사용자, 테넌트 관리자 및 IT 관리자에게 제공되는 기능이 있습니다.

**사용자 옵션** Power BI Desktop에서 사용자가 **옵션**의 보안 탭을 통해 Power BI용 ArcGIS Maps 사용을 중지할 수 있습니다. 기본적으로 ArcGIS Maps는 사용할 수 없게 되는 경우 로드되지 않습니다.

![](media/power-bi-visualization-arcgis/power-bi-desktop-security-dialog2.png)

Power BI 서비스에서 사용자가 사용자 설정의 Power BI용 ArcGIS Maps 탭을 통해 Power BI용 ArcGIS Maps 사용을 중지할 수 있습니다. 기본적으로 ArcGIS Maps는 사용할 수 없게 되는 경우 로드되지 않습니다.

![](media/power-bi-visualization-arcgis/power-bi-use-arcgis-new.png)

**테넌트 관리자 옵션** 모든 테넌트 사용자가 Power BI용 ArcGIS Maps를 사용할 수 없도록 PowerBI.com에서 테넌트 관리자가 설정할 수 있습니다. 이러한 경우 Power BI의 시각화 창에서 Power BI용 ArcGIS Maps 아이콘을 더 이상 표시하지 않습니다.

![](media/power-bi-visualization-arcgis/power-bi-arcgis-admin-portal2.png)

**IT 관리자 옵션** Power BI Desktop에서 **그룹 정책**을 사용하여 조직에 배포된 컴퓨터 전체에 걸쳐 Power BI용 ArcGIS Maps를 사용하지 않도록 설정합니다.

<table>
<tr><th>특성</th><th>값</th>
</tr>
<tr>
<td>key</td>
<td>Software\Policies\Microsoft\Power BI Desktop&lt;/td&gt;
</tr>
<tr>
<td>valueName</td>
<td>EnableArcGISMaps</td>
</tr>
</table>

1(10진수) 값이면 Power BI용 ArcGIS Maps를 사용할 수 있습니다.

0(10진수) 값이면 Power BI용 ArcGIS Maps를 사용할 수 없습니다.

## <a name="considerations-and-limitations"></a>고려 사항 및 제한 사항
Power BI용 ArcGIS Maps는 다음과 같은 서비스 및 애플리케이션에서 사용할 수 있습니다.

<table>
<tr><th>서비스/앱</th><th>가용성</th></tr>
<tr>
<td>Power BI Desktop</td>
<td>예</td>
</tr>
<tr>
<td>Power BI 서비스(PowerBI.com)</td>
<td>예</td>
</tr>
<tr>
<td>Power BI 모바일 애플리케이션</td>
<td>예</td>
</tr>
<tr>
<td>Power BI 웹에 게시</td>
<td>아니요</td>
</tr>
<tr>
<td>Power BI Embedded</td>
<td>아니요</td>
</tr>
<tr>
<td>Power BI 서비스 포함(PowerBI.com)</td>
<td>아니요</td>
</tr>
</table>

Power BI용 ArcGIS Maps를 사용할 수 없는 서비스 또는 애플리케이션에서 시각화는 빈 Power BI 로고와 함께 빈 시각적 개체로서 표시합니다.

주소를 지오코딩한 경우 첫 1500개 주소만 지오코딩됩니다. 지오코딩 장소 이름 또는 국가는 1500개 주소 제한에 적용되지 않습니다.

<br/>

**ArcGIS Maps for Power BI를 함께 작동하는 방법**
ArcGIS Maps for Power BI는 Esri(www.esri.com)에서 제공합니다. ArcGIS Maps for Power BI의 사용은 Esri의 [사용 약관](https://go.microsoft.com/fwlink/?LinkID=8263222) 및 [개인 정보 보호 정책](https://go.microsoft.com/fwlink/?LinkID=826323)에 따릅니다. Power BI용 ArcGIS Maps 시각적 개체를 사용할 Power BI 사용자는 승인 대화 상자를 수락해야 합니다(자세한 내용은 사용자 동의 참조).  Esri의 ArcGIS Maps for Power BI를 사용하는 작업은 승인 대화 상자에 연결되어 있는 Esri의 사용 약관 및 개인 정보 보호 정책에 따릅니다. 각 사용자는 처음으로 ArcGIS Maps for Power BI를 사용하기 전에 동의해야 합니다. 사용자가 동의하면 시각적 개체에 바인딩된 데이터는 지오코딩을 위해 Esri의 서비스로 전송됩니다. 즉, 위치 정보를 맵에 표시될 수 있는 위도 및 경도 정보로 변환하는 것입니다. 데이터 시각화에 바인딩된 모든 데이터를 Esri의 서비스에 보낼 수 있다고 가정해야 합니다. Esri에서는 기본 맵, 공간 분석, 지오코딩 등와 같은 서비스를 제공합니다. ArcGIS Maps for Power BI 시각적 개체는 Esri에서 제공되고 유지 관리되는 인증서에 의해 보호되는 SSL 연결을 사용하여 이러한 서비스와 상호 작용합니다. ArcGIS Maps for Power BI에 대한 추가 정보는 Esri의 [ArcGIS Maps for Power BI 제품 페이지](https://www.esri.com/powerbi)에서 가져올 수 있습니다.

사용자가 ArcGIS Maps for Power BI를 통해 Esri에서 제공된 추가 구독에 등록하는 경우 Esri와 직접 관계로 전환됩니다. Power BI는 Esri에 사용자에 대한 개인 정보를 전송하지 않습니다. 사용자가 고유한 AAD ID를 사용하여 Esri 제공 AAD 애플리케이션에 로그인하고 트러스트합니다. 이렇게 하면 사용자는 Esri와 개인 정보를 직접 공유하게 됩니다. 사용자가 ArcGIS Maps for Power BI 시각적 개체에 추가 콘텐츠를 추가하면 다른 Power BI 사용자도 해당 콘텐츠를 보거나 편집하기 위해 Esri의 추가 구독이 필요합니다. 

Esri의 ArcGIS Maps for Power BI가 작동하는 방법에 대한 기술적인 세부 질문은 해당 지원 사이트를 통해 Esri에 문의하세요.


**Power BI용 ArcGIS Maps를 사용하는 경우 요금이 부과됩니까?**

Power BI용 ArcGIS Maps는 추가 비용 없이 모든 Power BI 사용자가 사용할 수 있습니다. **Esri**에서 제공하는 구성 요소이며, 이 문서의 앞 부분에서 설명했듯이 **Esri**의 사용 약관 및 개인 정보 보호 정책에 따라 사용할 수 있습니다.

**Power BI Desktop에서 내 캐시가 가득 찼다는 오류 메시지가 나타나는 경우**

이는 해결 중인 버그입니다.  캐시를 지우려면 C:\Users\\AppData\Local\Microsoft\Power BI Desktop\CEF 위치에서 파일을 삭제한 후 Power BI를 다시 시작해 봅니다.

**Power BI용 ArcGIS Maps에서 Esri Shapefiles를 지원합니까?**

Power BI용 ArcGIS Maps는 국가/지역, 시/도 및 우편 번호와 같은 표준 경계를 자동으로 감지합니다. [Power BI Desktop용 도형 지도(미리 보기)](desktop-shape-map.md)를 사용하면 사용자 자신의 도형을 직접 제공할 수 있습니다.

**오프라인에서 ArcGIS 지도를 볼 수 있습니까?**

아니요, 지도를 표시하려면 Power BI는 네트워크 연결이 필요합니다.

**Power BI에서 내 ArcGIS Online 계정을 연결할 수 있습니까?**

아직은 연결할 수 없습니다. [이 아이디어에 투표](https://ideas.powerbi.com/forums/265200-power-bi-ideas/suggestions/9154765-arcgis-geodatabases)를 이용해 주십시오. 그리고 이 연결 기능에 대한 서비스를 시작하게 되면 귀하에게 전자 메일을 보내겠습니다.  

## <a name="next-steps"></a>다음 단계
[사용자와 공유한 ArcGIS 지도와 상호 작용](power-bi-visualizations-arcgis.md)

[Power BI용 ArcGIS 지도의 가용성을 발표하는 블로그 게시물](https://powerbi.microsoft.com/blog/announcing-arcgis-maps-for-power-bi-by-esri-preview/)

궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](http://community.powerbi.com/)

