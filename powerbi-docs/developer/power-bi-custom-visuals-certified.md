---
title: 인증된 Power BI 시각적 개체
description: 인증을 위해 사용자 지정 시각적 개체를 제출하기 위한 요구 사항 및 프로세스. 인증된 Power BI 시각적 개체 목록
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.topic: conceptual
ms.subservice: powerbi-custom-visuals
ms.date: 12/02/2019
ms.openlocfilehash: c39b96122016746905ea09c0983adf50356f0c77
ms.sourcegitcommit: 6272c4a0f267708ca7d38a45774f3bedd680f2d6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/06/2020
ms.locfileid: "75221968"
---
# <a name="get-a-power-bi-visual-certified"></a>Power BI 시각적 개체 인증받기

인증된 Power BI 시각적 개체는 *Microsoft Power BI 팀*이 테스트하고 승인한 특정 *지정 코드* 요구 사항을 충족하는 *Marketplace*의 시각적 개체입니다. 테스트는 시각적 개체가 외부 서비스 또는 리소스에 액세스하지 않는지 확인하도록 설계되었습니다.

인증된 Power BI 시각적 개체와 [표준 Power BI 시각적 개체](power-bi-custom-visuals.md)가 동일한 방식으로 사용됩니다. 이들은 [Power BI Desktop](../desktop-what-is-desktop.md) 및 [Power BI 서비스](../power-bi-service-overview.md)에 추가하고 [Power BI 모바일](../consumer/mobile/mobile-apps-for-mobile-devices.md) 및 [Power BI Embedded](embedding.md)를 사용하여 볼 수 있습니다.

인증 프로세스는 선택적 프로세스입니다. 개발자는 Marketplace에서 Power BI 시각적 개체를 인증받을지 여부를 결정할 수 있습니다. 인증된 Power BI 시각적 개체는 더 많은 기능을 제공합니다. 예를 들어 [PowerPoint로 내보내기](../consumer/end-user-powerpoint.md)가 가능하고 사용자가 [보고서 페이지를 구독](../consumer/end-user-subscribe.md)할 때 받은 이메일에 시각적 개체를 표시할 수 있습니다.

인증되지 않은 Power BI 시각적 개체가 반드시 안전하지 않은 시각적 개체를 의미하는 것은 아닙니다. 일부 시각적 개체는 [인증 요구 사항](https://docs.microsoft.com/power-bi/power-bi-custom-visuals-certified?#certification-requirements) 중 하나 이상을 준수하지 않았기 때문에 인증되지 않았습니다. 예를 들어 맵 시각적 개체와 같은 외부 서비스에 연결하거나 상용 라이브러리를 사용하여 시각적 개체에 연결할 수 있습니다.

자체 Power BI 시각적 개체를 만들어  [Microsoft AppSource](https://appsource.microsoft.com)에 추가하는 데 관심이 있는 웹 개발자라면  [Power BI 시각적 개체 개발](visuals/custom-visual-develop-tutorial.md) 자습서로 시작할 수 있습니다.

> [!NOTE]
> **Microsoft**는 타사 Power BI 시각적 개체의 작성자가 *아닙니다*. 타사 시각적 개체의 기능을 확인하려면 고객이 작성자에게 직접 문의하는 것이 좋습니다.

> [!IMPORTANT]
> Microsoft는 자체 판단에 따라 [인증된 Power BI 시각적 개체](#certified-power-bi-visuals) 목록에서 Power BI 시각적 개체를 제거할 수 있습니다.

## <a name="certification-requirements"></a>인증 요구 사항

Power BI 시각적 개체를 [인증](#get-a-power-bi-visual-certified)받으려면 Power BI 시각적 개체가 이 섹션에 나열된 요구 사항을 준수해야 합니다. 

> [!TIP]
> 코드를 제출하기 전에 미리 유효성을 검사하려면 기본 보안 규칙 집합을 포함하는 EsLint를 사용하는 것이 좋습니다.

* Microsoft 판매자 대시보드 또는 파트너 센터에서 승인해야 합니다. Power BI 시각적 개체가 [Marketplace](https://appsource.microsoft.com/marketplace/apps?page=1&product=power-bi-visuals)에 있어야 합니다.
* Power BI 시각적 개체가 *API v2.5* 이상으로 작성되어야 합니다.
* Power BI 팀에서 코드 리포지토리를 검토할 수 있어야 합니다. 예를 들어 소스 코드(JavaScript 또는 TypeScript)의 읽기 가능한 형식을 GitHub를 통해 사용할 수 있어야 합니다.

    >[!NOTE]
    > Github에서 코드를 공용으로 공유할 필요는 없습니다.

* 코드 리포지토리 요구 사항:
  * 다음 파일을 포함해야 합니다.
    * .gitignore
    * capabilities.json
    * pbiviz.json
    * package.json
    * package-lock.json
    * tsconfig.json
  * *node_modules* 폴더를 포함하지 않아야 합니다(.gitingore* 파일에 *node_modules* 추가).
  * *npm install* 명령이 오류를 반환하지 않아야 합니다.
  * *npm audit* 명령이 높음 또는 보통 수준의 경고를 반환하지 않아야 합니다.
  * *pbiviz package* 명령이 오류를 반환하지 않아야 합니다.
  * 구성 재정의 없이 [Microsoft의 TSlint](https://www.npmjs.com/package/tslint-microsoft-contrib)를 포함해야 합니다. 이 명령이 lint 오류를 반환하지 않아야 합니다.
   * Power BI 시각적 개체의 컴파일된 패키지가 제출된 패키지와 일치해야 합니다.
* 소스 코드 요구 사항:
   * Power BI 시각적 개체가 [렌더링 이벤트 API](./visuals/event-service.md)를 지원해야 합니다.
   * 임의/동적 코드가 실행되지 않아야 합니다(불량: eval(), 안전하지 않은 사용: settimeout(), requestAnimationFrame(), setinterval(사용자 입력이 있는 일부 함수), 사용자 입력/데이터 실행).
   * DOM이 안전하게 조작되었는지 확인해야 합니다(불량: innerHTML, D3.html(<일부 사용자/데이터 입력>), DOM에 추가하기 전에 사용자 입력/데이터에 대한 삭제를 사용).
   * 브라우저 콘솔에 입력 데이터에 대한 javascript 오류 또는 예외가 없어야 합니다. 사용자가 Power BI 시각적 개체를 예기치 않은 다른 데이터 범위와 함께 사용할 수 있으므로 시각적 개체가 실패하지 않아야 합니다. 이 [샘플 보고서](https://github.com/Microsoft/PowerBI-visuals/raw/gh-pages/assets/reports/large_data.pbix)를 테스트 데이터 집합으로 사용할 수 있습니다.

* *capabilities.json* 파일에서 속성을 변경한 경우 이로 인해 기존 사용자의 보고서가 손상되지 않아야 합니다.

* Power BI 시각적 개체가 [Power BI 시각적 개체에 대한 지침](./guidelines-powerbi-visuals.md)을 준수해야 합니다.
    
* 코드는 공용 Javascript 또는 TypeScript 라이브러리와 같은 공용 검토 가능한 OSS 구성 요소만 사용할 수 있습니다. 소스 코드는 검토할 수 있어야 하고 알려진 취약점이 없어야 합니다. 상용 구성 요소를 사용하여 사용자 지정 시각적 개체를 확인할 수 없습니다.

* Power BI 시각적 개체가 외부 서비스 또는 리소스에 액세스해서는 안 됩니다. 예를 들어 Power BI가 어떤 서비스에도 HTTP/S 또는 WebSocket 요청을 보낼 수 없어야 합니다. 

## <a name="submitting-a-power-bi-visual-for-certification"></a>인증을 위한 Power BI 시각적 개체 제출

파트너 센터를 통해 Power BI 팀에 Power BI 시각적 개체를 인증하도록 요청할 수 있습니다.

>[!TIP]
>Power BI 인증 프로세스는 시간이 걸릴 수 있습니다. 새 Power BI 시각적 개체를 만드는 경우 Power BI 인증을 요청하기 전에 파트너 센터를 통해 Power BI 시각적 개체를 게시하는 것이 좋습니다. 이렇게 하면 시각적 개체의 게시가 지연되지 않습니다.

Power BI 인증을 요청하려면

1. 파트너 센터에 로그인합니다.
2. **개요 페이지**에서 Power BI 시각적 개체를 선택하고 **제품 설정** 페이지로 이동합니다.
3. **Power BI 인증 요청** 확인란을 선택합니다.
4. **검토 및 게시** 페이지의 **인증에 대한 참고 사항** 텍스트 상자에 소스 코드 및 액세스 자격 증명에 대한 링크를 제공합니다.

>[!NOTE]
> Power BI 시각적 개체 제출 프로세스를 진행하는 도중이고 [판매자 대시보드](https://docs.microsoft.com/office/dev/store/use-the-seller-dashboard-to-submit-to-the-office-store)(이전 관리 도구)를 사용해야 하는 경우 [판매자 대시보드 인증 제출 프로세스](seller-dashboard.md#seller-dashboard-certification-submission-process) 지침을 검토하세요.

## <a name="certified-power-bi-visuals"></a>인증된 Power BI 시각적 개체

인증된 Power BI 시각적 개체는 아래에 나와 있습니다. 링크를 클릭하여 AppSource에서 Power BI 시각적 개체를 엽니다. 동영상를 사용할 수 있는 경우 동영상 링크를 클릭하여 동영상를 볼 수 있습니다.

* [3AG Systems - Bar Chart With Absolute Variance](https://appsource.microsoft.com/product/power-bi-visuals/WA104381802)(3AG Systems - 절대적 차이 포함 가로 막대형 차트)
*  [3AG Systems - Bar Chart With Relative Variance](https://appsource.microsoft.com/product/power-bi-visuals/WA104381912)(3AG 시스템 - 상대적 차이가 있는 막대형 차트)
*  [3AG Systems - Column Chart With Relative Variance](https://appsource.microsoft.com/product/power-bi-visuals/WA104381803)(3AG 시스템 - 상대적 차이가 있는 세로 막대형 차트)
*  [3AG Systems - Column Chart with Variance](https://appsource.microsoft.com/product/power-bi-visuals/WA104381724)(3AG Systems - 차이 포함 세로 막대형 차트)
* [Advanced Donut Visual (Full Edition)](https://appsource.microsoft.com/product/power-bi-visuals/WA104381941)(고급 도넛형 시각적 개체(정식 버전))
*  [Advanced Donut Visual (Light Edition)](https://appsource.microsoft.com/product/power-bi-visuals/WA104380858)(고급 도넛형 시각적 개체(경량 버전))
*  [Advanced Graph Visual](https://appsource.microsoft.com/product/power-bi-visuals/WA104382086)(고급 그래프 시각적 개체)
*  [Advanced Network Visualization](https://appsource.microsoft.com/product/power-bi-visuals/WA104381942)(고급 네트워크 시각화)
*  [Advanced TimeSeries Visual](https://appsource.microsoft.com/product/power-bi-visuals/WA104381943)(고급 시계열 시각적 개체(정식 버전))
*  [Aster Plot](https://appsource.microsoft.com/product/power-bi-visuals/WA104380759)(별표 그림)
*  [Beyondsoft Calendar](https://appsource.microsoft.com/product/power-bi-visuals/WA104381096)(Beyondsoft 달력)
*  [MAQ Software의 보타이 차트](https://appsource.microsoft.com/product/power-bi-visuals/WA104380838)
*  [Box and Whisker chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104380831)(상자 수염 차트)
* [Box and Whisker chart by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104381351)(MAQ Software의 상자 수염 차트)
*  [Brick Chart by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380836)(MAQ Software의 브릭 차트)
*  [Bubble Chart by Akvelon](https://appsource.microsoft.com/product/power-bi-visuals/WA104381340)(Akvelon의 버블 차트)
*  [Bullet Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104380755)(글머리 기호 차트), **[동영상 링크](https://youtu.be/AOlsFYkfkcw)**
* [Bullet Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104380755)(글머리 기호 차트)
*  [Bullet Chart by OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380953)(OKViz 글머리 기호 차트), **[동영상 링크](https://youtu.be/mtvUNl9bMjA)**
* [Calendar by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104381844)(MAQ Software 달력)
*  [Calendar by Tallan](https://appsource.microsoft.com/product/power-bi-visuals/WA104381146)(Tallan 달력)
*  [Candlestick by OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380952)(OKViz 원통형), **[동영상 링크](https://youtu.be/nT_18gyRxPo)**
*  [Card with States by OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380967)(OKViz에 의한 상태 포함 카드)
*  [Chiclet Slicer](https://appsource.microsoft.com/product/power-bi-visuals/WA104380756)(치클릿 슬라이서)
*  [Chord](https://appsource.microsoft.com/product/power-bi-visuals/WA104380761)(현), **[동영상 링크](https://youtu.be/AQvd2FhRyCI)**
*  [Circular Gauge by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380837)(MAQ Software의 원형 계기)
*  [Cluster Map](https://appsource.microsoft.com/product/power-bi-visuals/WA104380806)(클러스터 맵)
* [Custom Calendar by Akvelon](https://appsource.microsoft.com/product/power-bi-visuals/WA104381179)(Akvelon 사용자 지정 달력)
* [Cylindrical Gauge by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380874)(MAQ Software의 원통형 계기)
*  [Dial Gauge](https://appsource.microsoft.com/product/power-bi-visuals/WA104381184)(다이얼 계기)
[점 그림](https://appsource.microsoft.com/product/power-bi-visuals/WA104380760)
*  [Dot Plot by OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380949)(OKViz 점 그림), **[동영상 링크](https://youtu.be/By16pX9KT40)**
*  [Drilldown Cartogram](https://appsource.microsoft.com/product/power-bi-visuals/WA104381045)(드릴다운 Cartogram)
*  [Drilldown Choropleth](https://appsource.microsoft.com/product/power-bi-visuals/WA104381044)(드릴다운 Choropleth)
*  [Drill-down column chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104380857)(드릴다운 세로 막대형 차트), **[동영상 링크](https://youtu.be/lBy2gQQ5YsQ)**
*  [Drill-down column chart for time based data](https://appsource.microsoft.com/product/power-bi-visuals/WA104380881)(시간 기반 데이터의 드릴다운 세로 막대형 차트), **[동영상 링크](https://youtu.be/T_mRou18vx0)**
*  [Drill-down donut chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104380858)(드릴다운 도넛형 차트), **[동영상 링크](https://youtu.be/AUVFrSHmPeo)**
*  [Dual KPI](https://appsource.microsoft.com/product/power-bi-visuals/WA104380774)(이중 KPI)
*  [Dynamic Tooltip by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380983)(MAQ 소프트웨어의 동적 도구 설명)
*  [Enhanced Scatter](https://appsource.microsoft.com/product/power-bi-visuals/WA104380762)(향상된 분산형), **[동영상 링크](https://youtu.be/xCfM0cjM4do)**
*  [Enlighten Aquarium](https://appsource.microsoft.com/product/power-bi-visuals/WA104381112)(Enlighten 아쿠아리움)
*  [Enlighten Slicer](https://appsource.microsoft.com/product/power-bi-visuals/WA104380960)(Enlighten 슬라이서)
*  [Enlighten Stack Shuffle](https://appsource.microsoft.com/product/power-bi-visuals/WA104380849)(Enlighten 스택 셔플)
*  [Enlighten Waffle Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104380850)(Enlighten 와플 차트)
*  [Filter by List by Devscope](https://appsource.microsoft.com/product/power-bi-visuals/WA104381413)(Devscope 목록으로 필터링), **[동영상 링크](https://youtu.be/RetEWGwBu0I)**
*  [Force-Directed Graph](https://appsource.microsoft.com/product/power-bi-visuals/WA104380764)(Force-Directed 그래프), **[동영상 링크](https://youtu.be/YsTa7uyJ4sg)**
*  [Funnel with Source by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104381334)(MAQ Software의 원본이 포함된 깔때기)
*  [Gantt](https://appsource.microsoft.com/product/power-bi-visuals/WA104380765), **[동영상 링크](https://youtu.be/qJ7s_KrGiUU)**
* [Gantt Chart by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104381364)(MAQ Software의 Gantt 차트)
*  [Globe Data Bars](https://appsource.microsoft.com/product/power-bi-visuals/WA104381344)(지구본 데이터 막대)
*  [Grid by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380825)(MAQ Software의 그리드)
*  [Hierarchy Chart by Akvelon](https://appsource.microsoft.com/product/power-bi-visuals/WA104381333)(Akvelon 계층 구조 차트), **[동영상 링크](https://youtu.be/0ZGzJaq_KT4)**
*  [Histogram Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104380776)(히스토그램 차트)
*  [Histogram with points by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104381032)(MAQ Software의 포인트가 있는 히스토그램)
* [Horizontal bar chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104381230)(가로 막대형 차트)
*  [Horizontal Funnel by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380846)(MAQ Software의 가로 깔때기)
*  [CloudScope의 이미지](https://appsource.microsoft.com/product/power-bi-visuals/WA104381297)
*  [Image Grid](https://appsource.microsoft.com/product/power-bi-visuals/WA104381355)(이미지 격자)
*  [Infographic Designer](https://appsource.microsoft.com/product/power-bi-visuals/WA104380898)(인포그래픽 디자이너)
*  [KPI Chart by Akvelon](https://appsource.microsoft.com/product/power-bi-visuals/WA104381432)(Akvelon의 KPI 차트)
*  [KPI Column by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380996)(MAQ 소프트웨어의 KPI 열)
*  [KPI Grid by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380947)(MAQ Software의 KPI 그리드)
*  [KPI Indicator](https://appsource.microsoft.com/product/power-bi-visuals/WA104380832)(KPI 지표)
*  [KPI Ticker by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380946)(MAQ 소프트웨어의 KPI 티커)
* [Linear Gauge by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380821)(MAQ Software의 선형 계기)
*  [LineDot Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104380766)(LineDot 차트)
*  [Mekko Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104380785)(Mekko 차트), **[동영상 링크](https://youtu.be/90FLCKpgicA)**
*  [Multi KPI](https://appsource.microsoft.com/product/power-bi-visuals/WA104381763)(다중 KPI)
*  [Overview by CloudScope](https://appsource.microsoft.com/product/power-bi-visuals/WA104381477)(CloudScope의 개요)
*  [Play Axis (Dynamic Slicer)](https://appsource.microsoft.com/product/power-bi-visuals/WA104380981)(재생 축(동적 슬라이서))
*  [Power KPI](https://appsource.microsoft.com/product/power-bi-visuals/WA104381083), [동영상 링크](https://youtu.be/IvfIP3E6-1Q)
*  [Power KPI Matrix](https://appsource.microsoft.com/product/power-bi-visuals/WA104381299)(Power KPI 행렬), **[동영상 링크](https://youtu.be/1enze8pcGzY)**
*  [Pulse Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104381006)(펄스 차트), **[동영상 링크](https://youtu.be/DQWdcQtjDVw)**
*  [Quadrant Chart by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104381011)(MAQ Software에 의한 사분면 차트)
*  [Radar Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104380771)(방사형 차트)
*  [MAQ Software의 링 차트](https://appsource.microsoft.com/product/power-bi-visuals/WA104380824)
*  [Rotating Chart by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104381007)(MAQ Software의 회전 차트)
*  [Sankey Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104380777)(Sankey 차트), **[동영상 링크](https://youtu.be/WWP9wVUHGaA)**
*  [Scatter Chart by Akvelon](https://appsource.microsoft.com/product/power-bi-visuals/WA104381703)(Akvelon의 분산형 차트)
*  [Scroller](https://appsource.microsoft.com/product/power-bi-visuals/WA104381018)(스크롤러)
*  [Smart Filter by OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380859)(OKViz 스마트 필터), **[동영상 링크](https://youtu.be/gcJsDDRQq28)**
*  [Sparkline by OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380910)(OKViz 스파크라인), **[동영상 링크](https://youtu.be/0m3Vnvso9tY)**
*  [Stream Graph](https://appsource.microsoft.com/product/power-bi-visuals/WA104380772)(스트림 그래프)
*  [Sunburst](https://appsource.microsoft.com/product/power-bi-visuals/WA104380767)
*  [Synoptic Panel by OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380873)(OKViz의 시놉틱 패널)
*  [Table Heatmap](https://appsource.microsoft.com/product/power-bi-visuals/WA104380818)(테이블 Heatmap)
*  [Tachometer](https://appsource.microsoft.com/product/power-bi-visuals/WA104380937)(회전속도계), **[동영상 링크](https://youtu.be/C3OXdETbS9o)**
*  [Text Filter](https://appsource.microsoft.com/product/power-bi-visuals/WA104381309)(텍스트 필터)
*  [Text Wrapper by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380826)(MAQ Software의 텍스트 래퍼)
*  [Thermometer by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380847)(MAQ Software의 Thermometer)
*  [Time Brush Slicer](https://appsource.microsoft.com/product/power-bi-visuals/WA104380798)(시간 브러시 슬라이서)
*  [Timeline Slicer](https://appsource.microsoft.com/product/power-bi-visuals/WA104380786)(타임라인 슬라이서), **[동영상 링크](https://youtu.be/ozMtZ4_NZ10)**
*  [Timeline by CloudScope](https://appsource.microsoft.com/product/power-bi-visuals/WA104381427)(CloudScope 타임라인), [동영상 링크](https://youtu.be/szNi9YgXFJc)
*  [Tornado chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104380768)(토네이도 차트), **[동영상 링크](https://www.youtube.com/watch?v=AQvd2FhRyCI)**
*  [Trading Chart by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380823)(MAQ Software의 거래 차트)
* [Ultimate KPI Card](https://appsource.microsoft.com/product/power-bi-visuals/WA104381977)(Ultimate KPI 카드)
*  [Ultimate Variance](https://appsource.microsoft.com/product/power-bi-visuals/WA104381140)(Ultimate 차이), **[동영상 링크](https://youtu.be/pDYF8iZxERs)**
*  [Ultimate Waterfall](https://appsource.microsoft.com/product/power-bi-visuals/WA104380956)(Ultimate 폭포), **[동영상 링크](https://youtu.be/0BZsVCQdEkc)**
*  [User List by CloudScope](https://appsource.microsoft.com/product/power-bi-visuals/WA104381426)(CloudScope의 사용자 목록)
*  [MAQ 소프트웨어의 벤 다이어그램](https://appsource.microsoft.com/product/power-bi-visuals/WA104381231)
*  [Violin Plot](https://appsource.microsoft.com/product/power-bi-visuals/WA104381947)(바이올린 그림)
*  [Visio Visual](https://appsource.microsoft.com/product/power-bi-visuals/WA104381132)(Visio 시각적 개체)
*  [Waffle Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104381049)(와플 차트), **[동영상 링크](https://youtu.be/1vRqYUsm3Vk)**
*  [Word Cloud](https://appsource.microsoft.com/product/power-bi-visuals/WA104380752)(워드 클라우드), **[동영상 링크](https://youtu.be/AblTenl9fqo)**

## <a name="faq"></a>FAQ

시각적 개체에 대한 자세한 내용은 [인증된 시각적 개체에 관한 자주 묻는 질문](power-bi-custom-visuals-faq.md#certified-power-bi-visuals)을 참조하세요.

## <a name="next-steps"></a>다음 단계

* [Power BI 사용자 지정 시각적 개체 개발](../developer/custom-visual-develop-tutorial.md)
* [Microsoft의 사용자 지정 시각적 개체 YouTube 재생 목록](https://www.youtube.com/playlist?list=PL1N57mwBHtN1vIjfvuBIzZllrmKo-Vz6x)  
* [Power BI의 시각화](../visuals/power-bi-report-visualizations.md)  
* [Power BI의 사용자 지정 시각화](power-bi-custom-visuals.md)  
* [Microsoft AppSource에 Power BI 시각적 개체 게시하기](../developer/office-store.md)  

궁금한 점이 더 있나요? [Power BI 커뮤니티를 이용하세요.](https://community.powerbi.com/)
