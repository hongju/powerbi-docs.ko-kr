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
ms.date: 02/13/2018
ms.author: mihart
ms.openlocfilehash: 94a01f1d302d455dbcfe52ce39f5cb0b1ac4aa29
ms.sourcegitcommit: 05018ef2fe8439a9e8f599c696b8c3cee67e3958
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2018
---
# <a name="getting-a-custom-visual-certified"></a>사용자 지정 시각적 개체 *인증*하기
## <a name="what-is-meant-by-certified"></a>*인증*이란?
A *인증된 사용자 지정 시각적 개체*는 일련의 코드 요구 사항을 충족하고 엄격한 보안 테스트를 통과한 시각적 개체입니다.  사용자 지정 시각적 개체가 인증되면 [PowerPoint로 내보낼](service-publish-to-powerpoint.md) 수 있으며 사용자가 [페이지를 보고하도록 구독](service-report-subscribe.md)하면 수신된 전자 메일에 표시됩니다. 물론, [표준 사용자 지정 시각적 개체](power-bi-custom-visuals.md)처럼 사용하여 Power BI 서비스 및 Power BI Desktop 보고서에 추가하고 Power BI 모바일에서 보고 내장시킬 수 있습니다.

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
   * 코드 및 보안 검토 전달    2. Microsoft의 사용자 지정 시각적 개체 팀은 사용자 지정 시각적 개체를 인증하고 인증된 목록(아래)에 추가하거나 수정해야 하는 문제에 대한 보고서와 함께 거부하는 경우 사용자에게 알립니다. 개발자는 Microsoft와의 통신을 열어 두고 필요한 경우 인증된 시각적 개체를 업데이트하는 것을 담당합니다.

## <a name="removal-of-power-bi-certified-custom-visuals"></a>Power BI 인증된 사용자 지정 시각적 개체 제거
Microsoft에서는 판단에 따라 인증된 목록에서 시각적 개체를 제거할 수 있습니다.  

## <a name="list-of-custom-visuals-that-have-been-certified"></a>인증된 사용자 지정 시각적 개체의 목록
| AppSource에 연결 | 비디오에 연결 |
| --- | --- |
| [연결 규칙](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380815) | |
| [별표 그림](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380759) | |
| [Beyondsoft 달력](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381096) | |
| [MAQ Software의 보타이 차트](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380838) | [비디오](https://youtu.be/So5xKMSpVJI) |
| [상자 수염 차트](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380831) | |
| [Box and Whisker chart by MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381351)(MAQ Software의 상자 수염 차트) | [비디오](https://youtu.be/JoHaFLfhXdo) |
| [MAQ Software의 브릭 차트](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380836) | [비디오](https://youtu.be/hA3DOsvn2xY) |
| [Akvelon의 버블 차트](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381340) | |
| [글머리 기호 차트](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380755) | [비디오](https://youtu.be/AOlsFYkfkcw) |
| [OKViz에 의한 글머리 기호 차트](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380953) | [비디오](https://youtu.be/mtvUNl9bMjA) |
| [Tallan로 달력](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381146) | |
| [OKViz의 원통형](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380952) | [비디오](https://youtu.be/nT_18gyRxPo) |
| [OKViz에 의한 상태 포함 카드](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380967) | |
| [치클릿 슬라이서](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380756) | |
| [현](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380761) | [비디오](https://youtu.be/AQvd2FhRyCI) |
| [MAQ Software의 원형 계기](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380837) | [비디오](https://youtu.be/9NHXALkBXuY) |
| [클러스터 맵](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380806) | |
| [클러스터링](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380861) | |
| [이상값이 있는 클러스터링](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380889) | |
| [상관 관계 그림](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380814) | |
| [MAQ Software의 원통형 계기](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380874) | [비디오](https://youtu.be/DgdoWi7Gcxo) |
| [의사 결정 트리 차트](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380817) | |
| [다이얼 계기](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381184) | |
| [점 그림](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380760) | |
| [OKViz로 점 그림](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380949) | [비디오](https://youtu.be/By16pX9KT40) |
| [드릴다운 Cartogram](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381045) | |
| [드릴다운 Choropleth](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381044) | |
| [드릴다운 세로 막대형 차트](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380857) | [비디오](https://youtu.be/lBy2gQQ5YsQ) |
| [시간 기반 데이터에 대한 드릴다운 세로 막대형 차트](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380881) | [비디오](https://youtu.be/T_mRou18vx0) |
| [드릴다운 도넛 차트](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380858) | [비디오](https://youtu.be/AUVFrSHmPeo) |
| [이중 KPI](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380774) | |
| [향상된 분산형](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380762) | [비디오](https://youtu.be/xCfM0cjM4do) |
| [Aquarium 지원](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381112) | |
| [슬라이서 지원](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380960) | |
| [Stack Shuffle 지원](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380849) | |
| [Enlighten 와플 차트](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380850) | |
| [Force-Directed Graph](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380764)(Force-Directed 그래프) | [비디오](https://youtu.be/YsTa7uyJ4sg) |
| [TBATS 예측](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381326) | |
| [ARIMA를 사용한 예측](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380888) | |
| [MAQ Software의 원본이 포함된 깔때기](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381334) | [비디오](https://youtu.be/R_EcimsLI8U) |
| [Gantt](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380765) | [비디오](https://youtu.be/qJ7s_KrGiUU) |
| [MAQ Software의 원본이 Gantt 차트](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381364) | [비디오](https://youtu.be/vJLV9JRCpI8) |
| [지구본 데이터 막대](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381344) | |
| [Akvelon의 계층 구조 차트](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381333) | [비디오](https://youtu.be/0ZGzJaq_KT4) |
| [히스토그램 차트](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380776) | |
| [Histogram with points by MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381032)(MAQ Software의 포인트가 있는 히스토그램) | [비디오](https://youtu.be/-ILF--wExrw) |
| [MAQ Software의 가로 깔때기](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380846) | [비디오](https://youtu.be/SudZei68PPo) |
| [CloudScope의 이미지](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381297) | |
| [이미지 격자](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381355) | |
| [인포그래픽 디자이너](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380898) | |
| [KPI Chart by Akvelon](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381432)(Akvelon의 KPI 차트) | |
| [KPI 지표](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380832) | |
| [MAQ 소프트웨어의 KPI 티커](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380946) | [비디오](https://youtu.be/cudG4gsZ2V8) |
| [MAQ Software의 선형 계기](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380821) | [비디오](https://youtu.be/7_jFaM30dkc) |
| [LineDot 차트](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380766) | |
| [Mekko 차트](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380785) | [비디오](https://youtu.be/90FLCKpgicA) |
| [재생 축(동적 슬라이서)](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380981) | |
| [Power KPI](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381083) | [비디오](https://youtu.be/IvfIP3E6-1Q) |
| [Power KPI 행렬](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381299) | [비디오](https://youtu.be/1enze8pcGzY) |
| [방사형 차트](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380771) | |
| [MAQ Software의 링 차트](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380824) | [비디오](https://youtu.be/pDToHDFHnq8) |
| [MAQ Software의 회전 차트](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381007) | [비디오](https://youtu.be/d5xBCMmb3hU) |
| [Sankey 차트](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380777) | [비디오](https://youtu.be/WWP9wVUHGaA) |
| [스크롤러](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381018) | |
| [OKViz에 의한 스마트 필터](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380859) | [비디오](https://youtu.be/gcJsDDRQq28) |
| [OKViz로 스파크라인](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380910) | [비디오](https://youtu.be/0m3Vnvso9tY) |
| [스플라인 차트](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380860) | |
| [스트림 그래프](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380772) | |
| [Sunburst](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380767) | |
| [테이블 Heatmap](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380818) | |
| [속도계](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380937) | [비디오](https://youtu.be/C3OXdETbS9o) |
| [MAQ Software의 텍스트 래퍼](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380826) | |
| [온도계](https://appsource.microsoft.com/en-us/product/office/WA104379807) | |
| [시계열 분해 차트](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380897) | |
| [시계열 예측 차트](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380816) | |
| [타임라인 슬라이서](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380786) | [비디오](https://youtu.be/ozMtZ4_NZ10) |
| [토네이도 차트](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380768) | [비디오](https://www.youtube.com/watch?v=AQvd2FhRyCI) |
| [MAQ Software의 거래 차트](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380823) | [비디오](https://youtu.be/xhTR6y6J9Ko) |
| [최종 차이](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381140) | [비디오](https://youtu.be/pDYF8iZxERs) |
| [최고의 폭포 차트](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380956) | [비디오](https://youtu.be/0BZsVCQdEkc) |
| [CloudScope의 사용자 목록](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381426) | |
| [와플 차트](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381049) | [비디오](https://youtu.be/1vRqYUsm3Vk) |
| [워드 클라우드](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380752) | [비디오](https://youtu.be/AblTenl9fqo) |

## <a name="next-steps"></a>다음 단계
[사용자 지정 시각적 개체 개발자 도구 시작하기(미리 보기)](service-custom-visuals-getting-started-with-developer-tools.md)      
[YouTube에서 Microsoft의 사용자 지정 시각적 재생 목록](https://www.youtube.com/playlist?list=PL1N57mwBHtN1vIjfvuBIzZllrmKo-Vz6x)  
[Power BI의 시각화](power-bi-report-visualizations.md)  
[Power BI의 사용자 지정 시각화](power-bi-custom-visuals.md)  
[Microsoft AppSource에 사용자 지정 시각적 개체 게시](developer/office-store.md)  
궁금한 점이 더 있나요? [Power BI 커뮤니티를 이용하세요.](http://community.powerbi.com/)

