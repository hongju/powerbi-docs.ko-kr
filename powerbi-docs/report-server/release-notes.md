---
title: "Power BI Report Server 릴리스 정보"
description: "이 항목에서는 Power BI Report Server의 제한 사항 및 문제를 설명합니다."
services: powerbi
documentationcenter: 
author: markingmyname
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 11/01/2017
ms.author: maghan
ms.openlocfilehash: 7f59e3788b24344b5f86b146fb41e440eb0a2098
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/30/2018
---
# <a name="power-bi-report-server-release-notes"></a>Power BI Report Server 릴리스 정보
이 항목에서는 Power BI Report Server의 제한 사항 및 문제를 설명합니다.

Power BI Report Server 및 Report Server에 최적화된 Power BI Desktop을 다운로드하려면 [Power BI Report Server를 사용하여 온-프레미스 보고](https://powerbi.microsoft.com/report-server/)로 이동합니다.

## <a name="october-2017"></a>2017년 10월
* Power BI 보고서의 가져온 데이터에 대한 지원
* 웹 포털 내에서 Excel 통합 문서를 볼 수 있는 기능. 이는 Office Online Server를 구성하여 수행됩니다.
* 새 Power BI 테이블 및 행렬 시각적 개체에 대한 지원
* REST API 지원

## <a name="june-2017"></a>2017년 6월
* 2017년 6월에 대한 새 항목이 없습니다.

## <a name="may-2017"></a>2017년 5월
* Power BI Report Server를 사용하려면 Power BI Report Server에 최적화된 Power BI Desktop을 사용하여 Power BI 보고서를 만들어야 합니다. 이 페이지의 맨 위에 있는 다운로드 링크에서 Power BI Desktop을 다운로드할 수 있습니다.
* Power BI 보고서는 Analysis Services(테이블 형식 또는 다차원)에 대한 라이브 연결을 지원합니다.
* R 시각적 개체를 지원하지 않습니다.

**문제 및 고객 영향:** 동일한 컴퓨터에 SQL Server Reporting Services 및 Power BI Report Server가 모두 설치되어 있고 그 중 하나를 제거하는 경우 Report Server 구성 관리자를 사용하여 나머지 Report Server에 더 이상 연결할 수 없습니다.

**해결 방법** 이 문제를 해결하려면 서버 중 하나를 제거한 후에 다음 작업을 수행해야 합니다.

1. 관리자 모드에서 명령 프롬프트를 시작합니다.
2. 나머지 Report Server를 설치한 디렉터리로 이동합니다.
   
    *Power BI Report Server의 기본 위치: C:\Program Files\Microsoft Power BI Report Server*
   
    *SQL Server Reporting Service의 기본 위치: C:\Program Files\Microsoft SQL Server Reporting Services*
3. 다음 폴더로 이동합니다. 남아있는 프로그램에 따라 *SSRS* 또는 *PBIRS* 중 하나입니다.
4. WMI 폴더로 이동합니다.
5. 다음 명령을 실행합니다.
   
    ```
    regsvr32 /i ReportingServicesWMIProvider.dll
    ```
   
    다음 오류가 표시되는 경우 무시할 수 있습니다.
   
    ```
    The module "ReportingServicesWMIProvider.dll" was loaded but the entry-point DLLInstall was not found. Make sure that "ReportingServicesWMIProvider.dll" is a valid DLL or OCX file and then try again.
    ```

## <a name="next-steps"></a>다음 단계
[Power BI Report Server의 새로운 기능](whats-new.md)  
[사용자 안내서](user-handbook-overview.md)  
[관리자 안내서](admin-handbook-overview.md)  
[빠른 시작: Power BI Report Server 설치](quickstart-install-report-server.md)  
[보고서 작성기 설치](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder)  
[SSDT(SQL Server Data Tools) 다운로드](http://go.microsoft.com/fwlink/?LinkID=616714)

궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](https://community.powerbi.com/)

