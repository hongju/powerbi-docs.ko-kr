---
title: Power BI Report Server 및 Power BI 서비스 비교
description: 이 문서에서는 Power BI Report Server와 Power BI 서비스의 기능을 비교합니다.
keywords: ''
author: maggiesMSFT
ms.author: maggies
ms.topic: overview
ms.service: powerbi
ms.subservice: powerbi-report-server
manager: kfile
ms.custom: mvc
ms.date: 05/22/2019
ms.openlocfilehash: c4254420ae949b1fae6a1407cd045589c23da3c8
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "66187693"
---
# <a name="comparing-power-bi-report-server-and-the-power-bi-service"></a>Power BI Report Server 및 Power BI 서비스 비교

Power BI Report Server 및 Power BI 서비스에는 많은 유사성과 일부 주요 차이점이 있습니다. 이 표에서 유사성과 차이점을 설명합니다.

## <a name="features-of-power-bi-report-server-and-the-power-bi-service"></a>Power BI Report Server 및 Power BI 서비스의 기능

| 기능 | Power BI Report Server | Power BI 서비스 | 참고 |
|---------|---------|---------|---------|
| 배포 | 온-프레미스 또는 호스트 클라우드 | 클라우드 | Power BI Premium을 통해 라이선스가 부여된 경우 Azure VM(호스트 클라우드)에 Power BI Report Server를 배포할 수 있습니다. |
| 원본 데이터 | 클라우드 및/또는 온-프레미스 | 클라우드 및/또는 온-프레미스 |  |
| 라이선스 | Power BI Premium 또는 SQL Server EE(SA 포함) | Power BI Pro 및/또는 Power BI Premium | |  
| 수명 주기 | 최신 수명 주기 정책 | 완전히 관리되는 서비스 |  |
| 릴리스 주기 | 4개월마다 한 번 | 1개월에 한 번 | 최신 기능 및 수정은 Power BI 서비스에 대해 먼저 제공됩니다. 대부분의 핵심 기능은 다음 몇 가지 릴리스에서 Power BI Report Server에 대해 제공되고, 일부 기능은 Power BI 서비스에만 적용됩니다. |
| Power BI Desktop에서 Power BI 보고서 만들기 | 예 | 예 |  |
| 브라우저에서 Power BI 보고서 만들기 | 아니요 | 예 |  |
| 게이트웨이 필요 | 아니요 | 온-프레미스 데이터 원본의 경우 예 |  |
| 실시간 스트리밍 | 아니요 | 예 | [Power BI에서 실시간 스트리밍](../service-real-time-streaming.md) |
| 대시보드 | 아니요 | 예 | [Power BI 서비스의 대시보드](../consumer/end-user-dashboards.md) |
| 앱을 사용하여 보고서 그룹 배포 | 아니요 | 예 | [대시보드 및 보고서로 앱 생성 및 게시](../service-create-distribute-apps.md) |
| 콘텐츠 팩 | 아니요 | 예 | [조직 콘텐츠 팩: 소개](../service-organizational-content-pack-introduction.md) |
| Salesforce와 같은 서비스에 연결 | 예 | 예 | Power BI 서비스의 콘텐츠 팩과 함께 [사용하는 서비스에 연결](../service-connect-to-services.md)합니다. Power BI Report Server에서 인증된 커넥터를 사용하여 서비스에 연결합니다. 자세한 내용은 [Power BI Report Server에서 Power BI 보고서 데이터 원본](data-sources.md)을 참조하세요. |
| 질문 및 답변 | 아니요 | 예 | [Power BI 서비스 및 Power BI Desktop의 질문 및 답변](../power-bi-tutorial-q-and-a.md) 
| 신속한 정보 활용 | 아니요 | 예 | [Power BI를 사용하여 데이터 인사이트를 자동으로 생성](../consumer/end-user-insights.md) |
| Excel에서 분석 | 아니요 | 예 | [Excel에서 분석](../service-analyze-in-excel.md) 
| 페이지를 매긴 보고서 | 예 | 예 | 프리미엄 용량에서 [Power BI 서비스에서 페이지를 매긴 보고서를 미리 보기로 사용할 수 있음](../paginated-reports-report-builder-power-bi.md) |
| Power BI 모바일 앱 | 예 | 예 | [Power BI 모바일 앱 개요](../consumer/mobile/mobile-apps-for-mobile-devices.md) |
| ARC GIS 지도 | 아니요 | 예 | [Power BI 서비스 및 Power BI Desktop에서 Esri로 ArcGIS 지도 만들기](../visuals/power-bi-visualization-arcgis.md) |
| Power BI 보고서에 대한 메일 구독 | 아니요 | 예 | Power BI 서비스의 보고서 또는 대시보드에 [자신이나 다른 사용자 구독](../service-report-subscribe.md) |
| 페이지를 매긴 보고서에 대한 메일 구독 | 예 | 아니요 | [Reporting Services의 메일 전송](https://docs.microsoft.com/sql/reporting-services/subscriptions/e-mail-delivery-in-reporting-services)  |
| 데이터 경고 | 아니요 | 예 | Power BI 서비스의 [데이터 경고](../service-set-data-alerts.md)
| 행 수준 보안(RLS) | 예 | 예 | DirectQuery(데이터 원본) 및 가져오기 모드에서 사용 가능 <br>[Power BI 서비스](../service-admin-rls.md)의 행 수준 보안 <br>[Power BI Report Server](row-level-security-report-server.md)의 행 수준 보안 |
| 전체 화면 모드 | 아니요 | 예 | Power BI 서비스의 [전체 화면 모드](../consumer/end-user-focus.md) |
| 고급 Office 365 협업 | 아니요 | 예 | Office 365를 사용하여 [앱 작업 영역에서 공동 작업](../service-collaborate-power-bi-workspace.md) |
| R 시각적 개체 | 아니요 | 예 | Power BI Desktop에서[R 시각적 개체를 만들고](../desktop-r-visuals.md) Power BI 서비스에 게시합니다. R 시각적 개체를 포함하는 Power BI 보고서는 Power BI Report Server에 저장할 수 없습니다.  |
| 미리 보기 기능 | 아니요 | 예 | [Power BI 서비스 미리 보기 기능 옵트인](../consumer/end-user-preview-features.md) |
| 사용자 지정 시각적 개체 | 예 | 예 | [Power BI의 사용자 지정 시각적 개체](../power-bi-custom-visuals.md) |
| Power BI Desktop | 보고서 서버에 최적화된 버전으로, 보고서 서버로 다운로드할 수 있음 | Power BI 서비스에 최적화된 버전으로, Windows 스토어에서 사용 가능 | [보고서 서버용 Power BI Desktop](https://powerbi.microsoft.com/report-server/) <br><br> [Power BI 서비스용 Power BI Desktop](http://aka.ms/pbidesktopstore) |

## <a name="next-steps"></a>다음 단계

[Power BI Report Server 설치](install-report-server.md)  