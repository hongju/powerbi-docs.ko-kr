---
title: 인증된 Power BI 시각적 개체
description: 인증을 위해 사용자 지정 시각적 개체를 제출하기 위한 요구 사항 및 프로세스와 인증된 Power BI 시각적 개체 목록.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.topic: conceptual
ms.subservice: powerbi-custom-visuals
ms.date: 01/12/2019
ms.openlocfilehash: 4ffab3913560498dd57103f0a25c39f7a03a42ec
ms.sourcegitcommit: 75300b3f53f438ed7d3bd4edc93b9eb5925bf3af
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2020
ms.locfileid: "77026672"
---
# <a name="get-a-power-bi-visual-certified"></a>Power BI 시각적 개체 인증받기

인증된 Power BI 시각적 개체란 Microsoft Power BI 팀 [코드 요구 사항](#certification-requirements)을 충족하는 [AppSource](https://appsource.microsoft.com/en-us/marketplace/apps?page=1&product=power-bi-visuals)의 Power BI 시각적 개체입니다. 이러한 시각적 개체는 외부 서비스 또는 리소스에 액세스 하지 않고 보안 코딩 패턴 및 지침을 따르는지 확인하는 테스트를 거쳤습니다.

인증된 Power BI 시각적 개체는 더 많은 기능을 제공합니다. 예를 들어 [PowerPoint로 내보내기](../consumer/end-user-powerpoint.md)가 가능하고 사용자가 [보고서 페이지를 구독](../consumer/end-user-subscribe.md)할 때 받은 이메일에 시각적 개체를 표시할 수 있습니다.

인증 프로세스는 선택 사항입니다. 인증되지 않은 Power BI 시각적 개체라고 해서 반드시 안전하지 않은 Power BI 시각적 개체인 것은 아닙니다. 일부 Power BI 시각적 개체는 [인증 요구 사항](https://docs.microsoft.com/power-bi/power-bi-custom-visuals-certified?#certification-requirements) 중 하나 이상을 준수하지 않았기 때문에 인증되지 않았습니다. 예를 들어 외부 서비스에 연결하는 맵 Power BI 시각적 개체 또는 상용 라이브러리를 사용하는 Power BI 시각적 개체가 그렇습니다.

> [!NOTE]
> Microsoft는 타사 Power BI 시각적 개체의 작성자가 아닙니다. 타사 시각적 개체의 기능을 확인하려면 시각적 개체의 작성자에게 직접 문의하세요.

## <a name="certification-requirements"></a>인증 요구 사항

Power BI 시각적 개체를 [인증](#get-a-power-bi-visual-certified)받으려면 Power BI 시각적 개체가 이 섹션에 나열된 요구 사항을 준수해야 합니다. 

### <a name="general-requirements"></a>일반 요구 사항

Power BI 시각적 개체가 판매자 대시보드 또는 파트너 센터에 의해 승인되어야 합니다. Power BI 시각적 개체가 이미 [AppSource](https://appsource.microsoft.com/marketplace/apps?page=1&product=power-bi-visuals)에 있는 것이 좋습니다. Power BI 시각적 개체를 AppSource에 게시하는 방법을 알아보려면 [파트너 센터에 Power BI 시각적 개체 게시](office-store.md)를 참조하세요.

인증을 받기 위해 Power BI 시각적 개체를 제출하기 전에 [Power BI 시각적 개체에 대한 지침](./guidelines-powerbi-visuals.md)을 준수하는지 확인합니다.

Power BI 시각적 개체를 제출할 때 컴파일된 패키지가 제출된 패키지와 정확히 일치하는지 확인합니다.

### <a name="code-repository-requirements"></a>코드 리포지토리 요구 사항

GitHub에서 공개적으로 코드를 공유할 필요는 없지만 Power BI 팀이 코드 리포지토리를 검토할 수 있어야 합니다. 이렇게 하는 가장 좋은 방법은 GitHub에서 소스 코드(JavaScript 또는 TypeScript)를 제공하는 것입니다.

리포지토리에는 Power BI 시각적 개체 하나의 코드만 포함되어야 합니다. 여러 Power BI 시각적 개체의 코드나 관계가 없는 코드는 포함할 수 없습니다.

리포지토리에는 **certification**(소문자 필요)이라는 분기가 포함되어야 합니다. 이 분기의 소스 코드는 제출된 패키지와 일치해야 합니다. 이 코드는 Power BI 시각적 개체를 다시 제출하는 경우, 다음 제출 프로세스 중에만 업데이트할 수 있습니다.

Power BI 시각적 개체가 비공개 npm 패키지 또는 git 하위 모듈을 사용하는 경우, 이 코드가 포함된 추가 리포지토리에 대한 액세스 권한을 제공해야 합니다.

### <a name="file-requirements"></a>파일 요구 사항

최신 버전의 API를 사용하여 Power BI 시각적 개체를 작성합니다.

리포지토리에는 다음 파일이 포함되어야 합니다.
* **.gitignore** - 이 파일에 `node_modules`를 추가합니다. 코드에는 *node_modules* 폴더가 포함될 수 없습니다.
* **capabilities.json** - 이 파일의 속성이 변경된 새 버전의 Power BI 시각적 개체를 제출하는 경우, 기존 사용자의 보고서를 중단하지 않는지 확인합니다.
* **pbiviz.json**
* **package.json**
* **package-lock.json**
* **tsconfig.json**

### <a name="command-requirements"></a>명령 요구 사항

다음 명령이 오류를 반환하지 않는지 확인합니다.

* `npm install`
* `pbiviz package`
* `npm audit` - 높음 또는 보통 수준의 경고를 반환하지 않아야 합니다.
* 구성 재정의 없는 [Microsoft의 TSlint](https://www.npmjs.com/package/tslint-microsoft-contrib). 이 명령이 lint 오류를 반환하지 않아야 합니다.

### <a name="compiling-requirements"></a>컴파일 요구 사항

최신 버전의 [powerbi-visuals-tools](https://www.npmjs.com/package/powerbi-visuals-tools)를 사용하여 Power BI 시각적 개체를 작성합니다.

`pbiviz package`를 사용하여 Power BI 시각적 개체를 컴파일해야 합니다. 자체 빌드 스크립트를 사용하는 경우, `npm run package` 사용자 지정 빌드 명령을 제공합니다.



### <a name="source-code-requirements"></a>소스 코드 요구 사항

[Power BI 시각적 개체 추가 인증](https://docs.microsoft.com/legal/marketplace/certification-policies#1200-power-bi-visuals-additional-certification) 정책 목록을 따르는지 확인합니다. 제출이 이러한 지침을 따르지 않는 경우, 파트너 센터의 거부 전자 메일에는 이 링크에 나열된 정책 번호가 포함됩니다.

코드가 Power BI 인증 정책에 맞도록 하려면 아래 나열된 코드 요구 사항에 따르세요.  

**필수**
* 공용 Javascript 또는 TypeScript 라이브러리와 같은 공개적으로 검토 가능한 OSS 구성 요소만 사용하세요.
* 코드는 [렌더링 이벤트 API](./visuals/event-service.md)를 지원해야 합니다.
* DOM을 안전하게 조작해야 합니다. DOM에 추가하기 전에 사용자 입력 또는 사용자 데이터에 대한 삭제를 사용합니다.
* [샘플 보고서](https://github.com/Microsoft/PowerBI-visuals/raw/gh-pages/assets/reports/large_data.pbix)를 테스트 데이터 세트로 사용합니다.

**허용되지 않음**
* 외부 서비스 또는 리소스에 액세스. 예를 들어 Power BI가 어떤 서비스에도 HTTP/S 또는 WebSocket 요청을 보낼 수 없어야 합니다.
* `innerHTML` 또는 `D3.html(user data or user input)` 사용.
* 브라우저 콘솔에서 입력 데이터에 대한 JavaScript 오류 또는 예외.
* `eval()`과 같은 임의 또는 동적 코드, `settimeout()`, `requestAnimationFrame()`, `setinterval(user input function)`, 사용자 입력 또는 사용자 데이터의 안전하지 않은 사용.
* 축소된 JavaScript 파일 또는 프로젝트.

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
* 자체 Power BI 시각적 개체를 만들어  [Microsoft AppSource](https://appsource.microsoft.com)에 추가하는 데 관심이 있는 웹 개발자라면  [Power BI 시각적 개체 개발](visuals/custom-visual-develop-tutorial.md) 자습서로 시작할 수 있습니다. 

궁금한 점이 더 있나요? [Power BI 커뮤니티를 이용하세요.](https://community.powerbi.com/)
