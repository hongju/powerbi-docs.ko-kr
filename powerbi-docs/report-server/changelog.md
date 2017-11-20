---
title: "Power BI 보고서 서버에 대한 변경 로그"
description: "Power BI 보고서 서버에 대한 이 변경 로그는 각 릴리스 빌드에 대한 버그 픽스와 새 항목을 나열합니다."
services: powerbi
documentationcenter: 
author: jtarquino
manager: jonhp
backup: asaxton
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 09/19/2017
ms.author: jaimeta
ms.openlocfilehash: 9fdc757fca252c5c35d308dcd0b326098683b159
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2017
---
# <a name="changelog-for-power-bi-report-server"></a>Power BI 보고서 서버에 대한 변경 로그
Power BI 보고서 서버에 대한 이 변경 로그는 각 릴리스 빌드에 대한 버그 픽스와 새 항목을 나열합니다.

새로운 기능에 대한 자세한 내용은 [Power BI 보고서 서버의 새로운 기능](whats-new.md)을 참조하세요.

## <a name="october-2017"></a>2017년 10월
* **Power BI Report Server**
  * *버전 1.1.6514.9163빌드 14.0.600.434), 릴리스 날짜: 2017년 11월 1일*
    * 버그 픽스
      * 500MB 초과 PBIX 보고서의 업로드 안정성 문제 해결
      * 1GB 초과 PBIX 보고서의 데이터 로드 문제 해결
  * *버전 1.1.6513.3500(빌드 14.0.600.433), 릴리스 날짜: 2017년 10월 31일*
    * 기능
      * 포함된 데이터 모델 지원
      * Excel 통합 문서 보기(Office Online Server 통합 사용)
      * 예약된 데이터 새로 고침(PBIX)
      * 직접 쿼리 지원
      * 큰 파일 지원(최대 2GB)
      * 공용 REST API
        * Power BI Desktop에서 공유 데이터 집합 지원(oData를 통해)
      * PBIX 파일에 대한 URL 매개 변수 지원
      * 내게 필요한 옵션 기능 향
* **Power BI Desktop(Power BI Report Server에 최적화됨)**
  * *버전: 2.51.4885.1041(2017년 10월), 릴리스 날짜: 2017년 10월 31일*
    * Power BI Report Server로 연결에 필요한 변경 내용 포함(2017년 10월)

## <a name="june-2017"></a>2017년 6월
* **Power BI Report Server**
  
  * *빌드 14.0.600.305, 릴리스 날짜: 2017년 9월 19일*  
    
    * 버그 픽스
      * 최신 [Bing Maps 웹 컨트롤](https://msdn.microsoft.com/library/mt712542.aspx)로 업데이트
  * *빌드 14.0.600.301, 릴리스 날짜: 2017년 7월 11일*
    
    * 버그 픽스
      * {{UserId}} 태그가 Power BI 보고서에서 보고서를 실행한 사용자 대신 저장된 자격 증명으로 확인됩니다.
      * Power BI Server 보고서에서 일부 이미지가 렌더링되지 않습니다.
      * Power BI 보고서 서버에서 Power BI 보고서의 이름을 변경할 수 없습니다.
      * Power BI 모바일 응용 프로그램에서 사용자 지정 시각적 개체를 로드할 수 없습니다(로컬 캐시 정리를 위해 모바일 앱을 다시 설치해야 함).
  * *빌드 14.0.600.271, 릴리스 날짜: 2017년 6월 12일*
    
    * Power BI Report Server 초기 릴리스

## <a name="next-steps"></a>다음 단계
[사용자 안내서](user-handbook-overview.md)  
[관리자 안내서](admin-handbook-overview.md)  
[빠른 시작: Power BI Report Server 설치](quickstart-install-report-server.md)  
[보고서 작성기 설치](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder)  
[SSDT(SQL Server Data Tools) 다운로드](http://go.microsoft.com/fwlink/?LinkID=616714)

궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](https://community.powerbi.com/)

