---
title: "인증된 Power BI 사용자 지정 시각화"
description: "인증을 위해 사용자 지정 시각적 개체를 제출하기 위한 요구 사항 및 프로세스. 이미 인증된 사용자 지정 시각적 개체 목록."
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 11/20/2017
ms.author: mihart
ms.openlocfilehash: 3d51475b300fadc55f33960b03c3adc0031a39b8
ms.sourcegitcommit: 12236d08c27c7ee3fabb7ef9d767e9dee693f8aa
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="getting-a-custom-visual-certified"></a>사용자 지정 시각적 개체 *인증*하기
## <a name="what-is-meant-by-certified"></a>*인증*이란?
A *인증된 사용자 지정 시각적 개체*는 일련의 코드 요구 사항을 충족하고 엄격한 보안 테스트를 통과한 시각적 개체입니다.  사용자 지정 시각적 개체가 인증되면 [PowerPoint로 내보낼](service-publish-to-powerpoint.md) 수 있으며 사용자가 [페이지를 보고하도록 구독](service-report-subscribe.md)하면 수신된 전자 메일에 표시됩니다.

웹 개발자로서 고유한 시각화를 만들고 [Microsoft AppSource](https://appsource.microsoft.com)에 추가하는 데 관심이 있나요? 방법을 알아보려면 [개발자 도구 시작하기](service-custom-visuals-getting-started-with-developer-tools.md)를 참조하세요.


## <a name="certification-requirements"></a>인증 요구 사항
* Microsoft AppSource 승인    
* 사용자 지정 시각적 개체는 API 1.2 이상 버전으로 작성됩니다.    
* 검토에 사용 가능한 코드 리포지토리(예: GitHub을 통해 사용할 수 있는 시각적 개체 코드)    
* 공용 검토 가능한 OSS 구성 요소만 사용    
* 외부 서비스 또는 리소스에 액세스하지 않습니다.    

> **팁**: 코드를 제출하기 전에 미리 유효성을 검사하려면 기본 보안 규칙 집합을 포함하는 EsLint를 사용하는 것이 좋습니다.
> 
> 

## <a name="process-for-submitting-a-custom-visual-for-certification"></a>인증을 위해 사용자 지정 시각적 개체를 전송하는 프로세스
인증을 위해 사용자 지정 시각적 개체를 제출하려면:

1. Power BI 사용자 지정 시각적 개체 지원에 전자 메일을 보냅니다(pbicvsupport@microsoft.com). 전자 메일에는 다음 정보를 포함합니다.    
   
   * 제목: 시각적 인증 요청    
   * 시각적 소스 코드를 호스팅하는 GitHub 리포지토리에 연결    
   * 요구 사항 준수(위 참조)    
   * 코드 및 보안 검토 전달    
2. Microsoft의 사용자 지정 시각적 개체 팀은 사용자 지정 시각적 개체를 인증하고 인증된 목록(아래)에 추가하거나 수정해야 하는 문제에 대한 보고서와 함께 거부하는 경우 사용자에게 알립니다. 개발자는 Microsoft와의 통신을 열어 두고 필요한 경우 인증된 시각적 개체를 업데이트하는 것을 담당합니다.

## <a name="removal-of-power-bi-certified-custom-visuals"></a>Power BI 인증된 사용자 지정 시각적 개체 제거
Microsoft에서는 판단에 따라 인증된 목록에서 시각적 개체를 제거할 수 있습니다.  

## <a name="list-of-custom-visuals-that-have-been-certified"></a>인증된 사용자 지정 시각적 개체의 목록
| AppSource에 연결 | 비디오에 연결 |
| --- | --- |
| [별표 그림](https://appsource.microsoft.com/product/power-bi-visuals/WA104380759?src=office&tab=Overview) | |
| [MAQ 소프트웨어로 보타이 차트](https://appsource.microsoft.com/product/power-bi-visuals/WA104380838?src=office&tab=Overview) |[비디오](https://youtu.be/So5xKMSpVJI) |
| [BciCalendar(Beyondsoft 달력)](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381096?src=office&tab=Overview)  | |
| [상자 수염](https://appsource.microsoft.com/product/power-bi-visuals/WA104380831?src=office&tab=Overview) | |
| [글머리 기호 차트](https://store.office.com/app.aspx?assetid=WA104380755) |[비디오1](https://youtu.be/AOlsFYkfkcw)   [비디오2](https://youtu.be/AQvd2FhRyCI) |
| [OKViz에 의한 글머리 기호 차트](https://store.office.com/bullet-chart-by-okviz-WA104380953.aspx) |[비디오](https://youtu.be/mtvUNl9bMjA) |
| [Tallan로 달력](https://appsource.microsoft.com/product/power-bi-visuals/WA104381146?src=office&tab=Overview) | |
| [치클릿 슬라이서](https://store.office.com/chiclet-slicer-WA104380756.aspx) |[비디오](https://youtu.be/iYOkJ1APueY) |
| [화음 차트](https://appsource.microsoft.com/product/power-bi-visuals/WA104380761?src=office&tab=Overview) |[비디오](https://youtu.be/AQvd2FhRyCI) |
| [MAQ 소프트웨어로 순환 계기](https://appsource.microsoft.com/product/power-bi-visuals/WA104380837?tab=Overview) | |
| [원통형 계기](https://appsource.microsoft.com/product/power-bi-visuals/WA104380874) | |
| [전화 계기](https://appsource.microsoft.com/product/power-bi-visuals/WA104381184) |[비디오](https://youtu.be/AOlsFYkfkcw) |
| [MAQ 소프트웨어로 도넛 차트(링 차트)](https://appsource.microsoft.com/product/power-bi-visuals/WA104380824?tab=Overview) |[비디오](https://youtu.be/pDToHDFHnq8) |
| [OKViz로 점 그림](https://appsource.microsoft.com/product/power-bi-visuals/WA104381101?src=office&tab=Overview) |[비디오](https://youtu.be/4lskRgcpFJY) |
| [ZoomCharts로 도넛 차트 드릴다운](https://appsource.microsoft.com/product/power-bi-visuals/WA104380858) | |
| [이중 KPI](https://store.office.com/dual-kpi-WA104380774.aspx) |[비디오](https://youtu.be/821o0-eVBXo?list=PL1N57mwBHtN1vIjfvuBIzZllrmKo-Vz6x) |
| [Aquarium 지원](https://appsource.microsoft.com/product/power-bi-visuals/WA104381112?src=office&tab=Overview) | |
| World Flags 지원 - 서비스 예정 | |
| Stack Shuffle 지원 - 서비스 예정 | |
| [Gantt](https://store.office.com/gantt-WA104380765.aspx) |[비디오](https://youtu.be/qJ7s_KrGiUU) |
| [히스토그램](https://store.office.com/histogram-chart-WA104380776.aspx) | |
| [수평 깔때기](https://appsource.microsoft.com/product/power-bi-visuals/WA104380846) |[비디오](https://youtu.be/SudZei68PPo) |
| [KPI 지표](https://store.office.com/kpi-indicator-WA104380832.aspx) | |
| [MAQ 소프트웨어로 선형 계기](https://appsource.microsoft.com/product/power-bi-visuals/WA104380821?src=office&tab=Overview) |[비디오](https://youtu.be/AOlsFYkfkcw) |
| [Mekko 차트](https://appsource.microsoft.com/product/power-bi-visuals/WA104380785?src=office&tab=Overview)  | [비디오](https://youtu.be/90FLCKpgicA)|
| [재생 축(동적 슬라이서)](https://store.office.com/play-axis-dynamic-slicer-WA104380981.aspx) | |
| [Power KPI](https://appsource.microsoft.com/product/power-bi-visuals/WA104381083) |[비디오](https://youtu.be/IvfIP3E6-1Q) |
| [방사형 차트](https://store.office.com/radar-chart-WA104380771.aspx) | |
| [MAQ 소프트웨어로 링 차트(도넛 차트)](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380824?src=office&tab=Overview) | [비디오](https://youtu.be/pDToHDFHnq8)|
| [Sankey 차트](https://store.office.com/app.aspx?assetid=WA104380777.aspx) |[비디오](https://youtu.be/WWP9wVUHGaA) |
| [스크롤러](https://store.office.com/scroller-WA104381018.aspx) |[비디오](https://youtu.be/uhRFQF2cGSY) |
| [SQLBI로 스마트 필터](https://store.office.com/smart-filter-by-okviz-WA104380859.aspx) |[비디오](https://youtu.be/gcJsDDRQq28) |
| [OKViz로 스파크라인](https://appsource.microsoft.com/product/power-bi-visuals/WA104380910?src=office&tab=Overview) |[비디오](https://youtu.be/0m3Vnvso9tY) |
| [Sunburst](https://appsource.microsoft.com/product/power-bi-visuals/WA104380767?src=office&tab=Overview) | |
| [속도계](https://store.office.com/tachometer-WA104380937.aspx?) |[비디오](https://www.youtube.com/watch?v=C3OXdETbS9o) |
| [온도계](https://appsource.microsoft.com/product/power-bi-visuals/WA104380847?src=office&tab=Overview) | [비디오](https://youtu.be/SPX9mgrAdBc)|
| [시간 시계열 분해](https://appsource.microsoft.com/product/power-bi-visuals/WA104380897) | |
| [테이블 Heatmap](https://store.office.com/table-heatmap-WA104380818.aspx) | |
| [텍스트 래퍼](https://appsource.microsoft.com/product/power-bi-visuals/WA104380826) | |
| [타임라인 슬라이서](https://store.office.com/timeline-slicer-WA104380786.aspx) |[비디오](https://youtu.be/ozMtZ4_NZ10) |
| [토네이도 차트](https://store.office.com/tornado-chart-WA104380768.aspx) |[비디오](https://youtu.be/AQvd2FhRyCI) |
| [Waffle 차트](https://appsource.microsoft.com/product/power-bi-visuals/WA104381049?src=office&tab=Overview) |[비디오](https://youtu.be/1vRqYUsm3Vk) |
| [워드 클라우드](https://store.office.com/word-cloud-WA104380752.aspx?) |[비디오](https://www.youtube.com/watch?v=AblTenl9fqo) |

## <a name="next-steps"></a>다음 단계
[사용자 지정 시각적 개체 개발자 도구 시작하기(미리 보기)](service-custom-visuals-getting-started-with-developer-tools.md)      
[YouTube에서 Microsoft의 사용자 지정 시각적 재생 목록](https://www.youtube.com/playlist?list=PL1N57mwBHtN1vIjfvuBIzZllrmKo-Vz6x)  
[Power BI의 시각화](power-bi-report-visualizations.md)  
[Power BI의 사용자 지정 시각화](power-bi-custom-visuals.md)  
[Microsoft AppSource에 사용자 지정 시각적 개체 게시](developer/office-store.md)  
궁금한 점이 더 있나요? [Power BI 커뮤니티를 이용하세요.](http://community.powerbi.com/)

