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
ms.date: 10/27/2017
ms.author: mihart
ms.openlocfilehash: 27af387a6d789b00837e6bbf8c6be9aa219c7198
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2017
---
# <a name="getting-a-custom-visual-certified"></a>사용자 지정 시각적 개체 *인증*하기
## <a name="what-is-meant-by-certified"></a>*인증*이란?
A *인증된 사용자 지정 시각적 개체*는 일련의 코드 요구 사항을 충족하고 엄격한 보안 테스트를 통과한 시각적 개체입니다.  사용자 지정 시각적 개체가 인증되면 [PowerPoint로 내보낼](service-publish-to-powerpoint.md) 수 있으며 사용자가 [페이지를 보고하도록 구독](service-report-subscribe.md)하면 수신된 전자 메일에 표시됩니다.

* 웹 개발자로서 고유한 시각화를 만들고 스토어에 추가하는 데 관심이 있나요? 방법을 알아보려면 [개발자 도구 시작하기](service-custom-visuals-getting-started-with-developer-tools.md)를 참조하고 [Office 스토어](service-custom-visuals-office-store.md)를 방문하세요.
* 정기적으로 사용하는 Office 스토어 시각적 개체가 있나요? 시각적 개체 개발자에게 시각적 개체의 Microsoft 인증을 요청하세요.  개발자의 연락처 정보가 시각적 개체 **자세한 정보** 페이지에 **공급자**로 나열됩니다.

## <a name="certification-requirements"></a>인증 요구 사항
* Office 스토어 승인    
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
| Office 스토어에 연결 | 비디오에 연결 |
| --- | --- |
| [연결 규칙](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380815) | |
| [별표 그림](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380759?src=office&tab=Overview) | |
| [BciCalendar] 제공 예정 | |
| [상자 수염](https://appsource.microsoft.com/product/power-bi-visuals/WA104380831?src=office&tab=Overview) | |
| [글머리 기호 차트](https://store.office.com/en-us/app.aspx?assetid=WA104380755) |[비디오1](https://youtu.be/AOlsFYkfkcw)   [비디오2](https://youtu.be/AQvd2FhRyCI) |
| [OKViz에 의한 글머리 기호 차트](https://store.office.com/bullet-chart-by-okviz-WA104380953.aspx) |[비디오](https://youtu.be/mtvUNl9bMjA) |
| [OKViz에 의한 상태 포함 카드](https://store.office.com/card-with-states-by-okviz-WA104380967.aspx) |[비디오 1](https://youtu.be/myiX0BmZd8U) [비디오 2](https://youtu.be/AOlsFYkfkcw) |
| [치클릿 슬라이서](https://store.office.com/chiclet-slicer-WA104380756.aspx) |[비디오](https://youtu.be/iYOkJ1APueY) |
| [MAQ 소프트웨어로 순환 계기](https://appsource.microsoft.com/product/power-bi-visuals/WA104380837?tab=Overview) | |
| [원통형 계기](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380874) | |
| [전화 계기](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381184) |[비디오](https://youtu.be/AOlsFYkfkcw) |
| [MAQ 소프트웨어로 도넛 차트(링 차트)](https://appsource.microsoft.com/product/power-bi-visuals/WA104380824?tab=Overview) |[비디오](https://youtu.be/pDToHDFHnq8) |
| [드릴다운 도넛 차트](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380858) | |
| [이중 KPI](https://store.office.com/dual-kpi-WA104380774.aspx) |[비디오](https://youtu.be/821o0-eVBXo?list=PL1N57mwBHtN1vIjfvuBIzZllrmKo-Vz6x) |
| Fly Wheel - 제공 예정 | |
| [Gantt](https://store.office.com/gantt-WA104380765.aspx) |[비디오](https://youtu.be/qJ7s_KrGiUU) |
| [히스토그램](https://store.office.com/histogram-chart-WA104380776.aspx) | |
| [수평 깔때기](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380846) |[비디오](https://youtu.be/SudZei68PPo) |
| [이미지 타임라인](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381254) | |
| [KPI 지표](https://store.office.com/kpi-indicator-WA104380832.aspx) | |
| Liquid Fill Gauge - 서비스 예정 |[비디오](https://youtu.be/wQ51TTqIZc4) |
| [MAQ 소프트웨어로 선형 계기](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380821?src=office&tab=Overview) |[비디오](https://youtu.be/AOlsFYkfkcw) |
| 긴 텍스트 뷰어 - 제공 예정 | |
| [재생 축(동적 슬라이서)](https://store.office.com/play-axis-dynamic-slicer-WA104380981.aspx) | |
| [Power KPI](https://appsource.microsoft.com/product/power-bi-visuals/WA104381083) |[비디오](https://youtu.be/IvfIP3E6-1Q) |
| [펄스 차트](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381006?src=office&tab=Overview) |[비디오](https://www.youtube.com/watch?v=DQWdcQtjDVw) |
| [방사형 차트](https://store.office.com/radar-chart-WA104380771.aspx) | |
| [Sankey 차트](https://store.office.com/app.aspx?assetid=WA104380777.aspx) |[비디오](https://youtu.be/WWP9wVUHGaA) |
| [MAQ 소프트웨어로 링 차트](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380824) |[비디오](https://youtu.be/pDToHDFHnq8) |
| [스크롤러](https://store.office.com/scroller-WA104381018.aspx) |[비디오](https://youtu.be/uhRFQF2cGSY) |
| [OKViz에 의한 스마트 필터](https://store.office.com/smart-filter-by-okviz-WA104380859.aspx) |[비디오](https://youtu.be/gcJsDDRQq28) |
| [OKViz로 스파크라인](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380910?src=office&tab=Overview) |[비디오](https://youtu.be/0m3Vnvso9tY) |
| [Sunburst](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380767?src=office&tab=Overview) | |
| [속도계](https://store.office.com/tachometer-WA104380937.aspx?) |[비디오](https://www.youtube.com/watch?v=C3OXdETbS9o) |
| [시간 시계열 분해](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380897) | |
| [테이블 Heatmap](https://store.office.com/table-heatmap-WA104380818.aspx) | |
| [텍스트 래퍼](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380826) | |
| [타임라인 슬라이서](https://store.office.com/timeline-slicer-WA104380786.aspx) |[비디오](https://youtu.be/ozMtZ4_NZ10) |
| [토네이도 차트](https://store.office.com/tornado-chart-WA104380768.aspx) |[비디오](https://youtu.be/AQvd2FhRyCI) |
| [Visio 시각적 개체 미리 보기](https://store.office.com/visio-visual-preview-WA104381132.aspx) |[비디오](https://www.youtube.com/watch?v=dCcd7rftjZA&list=PL1N57mwBHtN1vIjfvuBIzZllrmKo-Vz6x&index=2) |
| [Waffle 차트](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381049?src=office&tab=Overview) |[비디오](https://youtu.be/1vRqYUsm3Vk) |
| [워드 클라우드](https://store.office.com/word-cloud-WA104380752.aspx?) |[비디오](https://www.youtube.com/watch?v=AblTenl9fqo) |

## <a name="next-steps"></a>다음 단계
[Office 스토어에서 사용자 지정 시각적 개체 다운로드 및 사용](service-custom-visuals-office-store.md)  
[사용자 지정 시각적 개체 개발자 도구 시작하기(미리 보기)](service-custom-visuals-getting-started-with-developer-tools.md)      
[YouTube에서 Microsoft의 사용자 지정 시각적 재생 목록](https://www.youtube.com/playlist?list=PL1N57mwBHtN1vIjfvuBIzZllrmKo-Vz6x)  
[Power BI의 시각화](power-bi-report-visualizations.md)  
[Power BI의 사용자 지정 시각화](power-bi-custom-visuals.md)  
[Power BI Desktop에서 사용자 지정 시각화 사용](power-bi-custom-visuals-use.md)  
[사용자 지정 시각적 개체를 Office 스토어에 게시](developer/office-store.md)  
궁금한 점이 더 있나요? [Power BI 커뮤니티를 이용하세요.](http://community.powerbi.com/)

