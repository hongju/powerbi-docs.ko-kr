---
title: 'Power BI의 페이지를 매긴 보고서: FAQ'
description: 이 문서에서는 페이지를 매긴 보고서에 대한 질문과 대답을 제공합니다. 이러한 보고서는 인쇄 또는 PDF 생성에 최적화되어 있고 정교하게 형식 지정된 완벽한 픽셀 출력입니다.
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: report-builder
ms.topic: overview
ms.date: 06/18/2019
ms.openlocfilehash: 10ac6ed9f49241103d03f2667ccc8db5d619db6c
ms.sourcegitcommit: a42c6758aa255c21ece6366a3257b0dd82f3606b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2019
ms.locfileid: "67345521"
---
# <a name="paginated-reports-in-power-bi-faq"></a>Power BI의 페이지를 매긴 보고서: FAQ 

이 문서에서는 페이지를 매긴 보고서에 대한 질문과 대답을 제공합니다. 이러한 보고서는 인쇄 또는 PDF 생성에 최적화되어 있고 정교하게 형식 지정된 완벽한 픽셀 출력입니다. 이러한 보고서가 “페이지를 매긴” 보고서로 불리는 이유는 여러 페이지에 적합하게 형식 지정되어 있기 때문입니다. 페이지를 매긴 보고서는 SQL Server Reporting Services의 RDL 보고서 기술을 기반으로 합니다. 

이 문서에서는 Power BI Premium의 페이지를 매긴 보고서와 페이지를 매긴 보고서를 제작하는 데 사용되는 독립 실행형 도구인 보고서 작성기에 대해 가지고 있는 여러 가지 일반적인 질문에 대한 답변을 제공합니다. 서비스에 보고서를 게시하려면 Power BI Pro 라이선스가 필요합니다. 작업 영역이 Power BI Premium 용량에 포함된 경우 내 작업 영역 또는 앱 작업 영역에서 페이지를 매긴 보고서를 게시하고 공유할 수 있습니다. 

## <a name="administration"></a>관리

### <a name="what-size-premium-capacity-do-i-need-for-paginated-reports"></a>페이지를 매긴 보고서에 필요한 크기의 프리미엄 용량은 무엇인가요?

페이지를 매긴 보고서 워크로드는 P1 - P3 SKU에서 사용할 수 있습니다.  A4 - A6 SKU에서 SaaS 포함 시나리오에도 사용할 수 있습니다.

### <a name="what-is-the-maximum-memory-threshold-i-can-put-for-paginated-reports-in-my-capacity"></a>내 용량의 페이지를 매긴 보고서에 지정할 수 있는 최대 메모리 임계값은 얼마인가요?

2019년 6월 말까지 이 워크로드에 대해 최대 100% 메모리를 사용할 수 있습니다. 

### <a name="how-does-user-access-work-for-paginated-reports"></a>페이지를 매긴 보고서에 대한 사용자 액세스는 어떻게 이루어지나요?

페이지를 매긴 보고서에 대한 사용자 액세스는 Power BI 서비스의 다른 모든 콘텐츠에 대한 사용자 액세스와 동일합니다. 

### <a name="how-do-i-turn-onoff-my-paginated-reports-workload"></a>페이지를 매긴 보고서 워크로드를 켜는/끄는 방법은 무엇인가요?

용량 관리자는 용량 관리자 포털 페이지에서 페이지를 매긴 보고서 워크로드를 사용하거나 사용하지 않도록 설정할 수 있습니다.  기본적으로 워크로드는 사용자가 만드는 새 용량에 대해 켜집니다.  

### <a name="how-can-i-monitor-usage-of-paginated-reports-in-my-tenant"></a>내 테넌트에서 페이지를 매긴 보고서의 사용량을 모니터링할 수 있는 방법은 무엇인가요?

Office 365 감사 로그의 다음 이벤트 아래에 이 보고서 종류의 사용량이 자세히 나와 있습니다. 

- Power BI 보고서 보기
- Power BI 보고서 삭제
- Power BI 보고서 만들기
- 다운로드한 Power BI 보고서

ReportType 필드에는 Power BI 보고서가 아닌 페이지를 매긴 보고서를 식별하는 “PaginatedReport” 값이 있습니다.

감사 로그는 페이지를 매긴 보고서에 대한 다음 이벤트도 제공합니다.

- 게이트웨이에 바인딩된 Power BI 데이터 세트
- Power BI 데이터 원본 검색
- TakeOverDatasource

### <a name="can-i-monitor-this-workload-through-the-premium-capacity-monitoring-app"></a>프리미엄 용량 모니터링 앱을 통해 이 워크로드를 모니터링할 수 있나요?

예, 모니터링은 Power BI 데이터 세트에 대한 동일한 관련 세부 정보가 포함된 새 탭으로 사용할 수 있습니다.

### <a name="do-i-need-a-pro-license-to-create-and-publish-paginated-reports"></a>페이지를 매긴 보고서를 만들고 게시하려면 Pro 라이선스가 필요한가요?

작업 영역이 프리미엄 용량에 포함된 경우 Pro 라이선스 없이 내 작업 영역에 페이지를 매긴 보고서를 업로드할 수 있습니다.  다른 작업 영역의 경우 콘텐츠를 작성하고 게시하려면 Pro 라이선스가 있어야 합니다. Pro 라이선스가 없어도 Power BI 보고서 작성기를 다운로드하여 사용하는 것이 좋지만, 해당 라이선스 없이 만드는 페이지를 보고서는 게시할 수 없습니다. 

### <a name="what-if-i-have-a-paginated-report-in-a-workspace-and-the-paginated-report-workload-is-turned-off"></a>작업 영역에 페이지를 매긴 보고서가 있는데 페이지를 매긴 보고서 워크로드가 꺼져 있는 경우 어떻게 하나요?

오류 메시지가 수신되지만 워크로드가 다시 켜질 때까지 보고서를 볼 수 없습니다. 작업 영역에서 보고서를 삭제할 수는 있습니다.

### <a name="what-is-the-default-memory-for-each-of-the-premium-skus-supported-for-paginated-reports"></a>페이지를 매긴 보고서에 대해 지원되는 각 Premium SKU의 기본 메모리는 얼마인가요?

페이지를 매긴 보고서에 대한 각 Premium SKU의 기본 메모리는 다음과 같습니다.

- **P1/A4**: 기본값 20%, 최솟값 10%
- **P2/A5**: 기본값 20%, 최솟값 5%
- **P3/A6**: 기본값 20%, 최솟값 2.5%

## <a name="general"></a>일반

### <a name="when-should-i-use-a-paginated-report-vs-a-power-bi-report"></a>페이지를 매긴 보고서와 Power BI 보고서를 사용해야 하는 경우를 비교하면 각각 언제인가요?

페이지를 매긴 보고서는 인쇄 또는 PDF 생성에 최적화된 정교한 서식의 완벽한 픽셀 출력이 요구되는 시나리오에 가장 적합합니다.  손익 계산서가 페이지를 매긴 보고서로 만들 보고서 종류의 좋은 예입니다.  

Power BI 보고서는 탐색 및 대화형 작업에 최적화되어 있습니다.  여러 영업 사원이 특정 지역/산업/고객에 대해 동일한 보고서의 데이터를 분할하여 수치가 어떻게 변경되는지 확인하려는 영업 보고서로는 Power BI 보고서가 가장 적합합니다.

### <a name="the-documentation-says-power-bi-report-builder-is-the-preferred-authoring-tool-can-i-create-paginated-reports-in-sql-server-data-tools-for-power-bi"></a>설명서에 따르면 Power BI 보고서 작성기가 기본 제작 도구입니다. SQL Server Data Tools에서 Power BI용 페이지를 매긴 보고서를 만들 수 있나요?

예. 하지만 Power BI 서비스에서는 한 번에 하나의 항목만 업로드할 수 있으므로 작성자가 SSDT(SQL Server Data Tools)와 함께 사용하는 시나리오 중 다수는 아직 지원되지 않습니다. 이 FAQ 뒷부분에 제공된 [지원되지 않는 기능의 전체 목록](#what-paginated-report-features-in-ssrs-arent-yet-supported-in-power-bi)을 참조하세요.  

### <a name="what-versions-of-report-builder-do-you-support"></a>지원되는 보고서 작성기 버전은 무엇인가요?

최근에 Power BI 서비스의 페이지를 매긴 보고서용 기본 제작 도구로 Power BI 보고서 작성기를 릴리스했습니다. [Microsoft 다운로드 센터에서 Power BI 보고서 작성기](https://go.microsoft.com/fwlink/?linkid=2086513)를 설치합니다.

### <a name="how-do-i-move-existing-reports-i-have-saved-in-sql-server-reporting-services-to-power-bi"></a>SQL Server Reporting Services에 저장한 기존 보고서를 Power BI로 이동하려면 어떻게 해야 하나요?

서버에서 보고서를 다운로드한 후 포털을 통해 Power BI로 업로드해야 합니다.  현재는 사용할 수 있는 마이그레이션 도구가 없으나 공개 미리 보기를 완료하고 적합한 수준의 제품 간 기능 패리티를 확보한 후 마이그레이션 도구를 만들려고 검토하고 있습니다.

### <a name="can-i-open-reports-and-publish-directly-to-the-service"></a>보고서를 열어서 서비스에 직접 게시할 수 있나요?

예. 최근에 보고서를 열어서 Power BI 보고서 작성기에서 서비스에 직접 게시할 수 있도록 지원을 추가했습니다.

### <a name="what-paginated-report-features-in-ssrs-arent-yet-supported-in-power-bi"></a>Power BI에서 아직 지원되지 않는 SSRS의 페이지를 매긴 보고서 기능은 무엇인가요?

현재 페이지를 매긴 보고서에서는 다음 항목을 지원하지 않습니다.

- 공유 데이터 원본
- 공유 데이터 세트
- 하위 보고서
- 다른 보고서로 드릴스루 및 클릭 광고
- 연결된 보고서
- Bing 지도 계층
- 사용자 지정 글꼴

토글/정렬을 제외하고 Power BI 서비스에서 지원되지 않는 기능이 있는 파일을 업로드하려고 하면 오류 메시지를 받게 됩니다.

### <a name="what-data-sources-do-you-support-currently-for-paginated-reports"></a>페이지를 매긴 보고서에 대해 현재 지원되는 데이터 원본은 무엇인가요?

다음 데이터 원본을 지원합니다. 

- Power BI Premium 데이터 세트
- Azure Analysis Services(SSO(Single Sign-On) 및 oAuth를 통해)
- Azure SQL Data Warehouse
- Azure SQL Database(사용자 이름/암호 및 oAuth)
- SQL Server*
- SSAS(SQL Server Analysis Services) 테이블 형식(DAX) 및 다차원(MDX) 모델* 
- Oracle* 
- Teradata* 

* 온-프레미스 게이트웨이가 필요합니다.

게이트웨이를 통해 SSAS에 액세스하는 경우 해당 자격 증명이 저장된 사용자가 SSAS에서 게이트웨이를 통해 작업하려면 상승된 권한이 있어야 합니다.

### <a name="what-authentication-methods-do-you-support"></a>지원되는 인증 방법은 무엇인가요?

Azure Analysis Services와 Power BI Premium 데이터 원본에 대한 SSO를 지원하며 Azure SQL Database에 대한 oAuth 및 SSO를 지원합니다.  기타 데이터 원본의 경우 현재는 포털 또는 게이트웨이에 사용자 이름 및 암호를 데이터 원본과 함께 저장해야 합니다.  

### <a name="can-i-use-a-power-bi-dataset-as-a-data-source-for-my-paginated-report"></a>내 페이지를 매긴 보고서의 데이터 원본으로 Power BI 데이터 세트를 사용할 수 있나요?

예. 페이지를 매긴 보고서의 데이터 원본으로 Power BI Premium 데이터 세트를 지원합니다.

### <a name="can-i-use-stored-procedures-through-the-gateway"></a>게이트웨이를 통해 저장 프로시저를 사용할 수 있나요?

게이트웨이를 통해 저장 프로시저를 사용할 수 있지만, 저장 프로시저에 매개 변수가 있는 경우 특정 시나리오에서 문제가 표시될 수 있습니다.

### <a name="what-export-formats-are-available-for-my-report-in-the-power-bi-service"></a>Power BI 서비스에서 내 보고서에 사용할 수 있는 내보내기 형식은 무엇인가요?

Microsoft Excel, Microsoft Word, Microsoft PowerPoint, PDF, .CSV, XML 및 MHTML로 내보낼 수 있습니다.

### <a name="can-i-print-paginated-reports"></a>페이지를 매긴 보고서를 인쇄할 수 있나요?

예. 인쇄는 새롭고 향상된 인쇄 미리 보기 환경을 포함하여 페이지를 매긴 보고서에 사용할 수 있습니다. 

### <a name="are-e-mail-subscriptions-available-yet-for-paginated-reports"></a>페이지를 매긴 보고서에 대해 메일 구독을 사용할 수 있나요?

예. 메일 구독은 페이지를 매긴 보고서에서 완전 지원되며 6가지 파일 형식 및 매개 변수 값을 지원합니다.

### <a name="can-i-run-custom-code-in-my-report"></a>내 보고서에서 사용자 지정 코드를 실행할 수 있나요?

예, SSRS에서처럼 보고서에서 코드를 실행하는 기능을 지원합니다.

### <a name="can-i-use-power-bi-embedded-to-embed-my-paginated-reports-into-an-app-im-hosting"></a>Power BI Embedded를 사용하여 호스트하는 앱에 페이지를 매긴 보고서를 포함할 수 있나요?

SaaS 포함은 6월 한 달간 지원됩니다.  Microsoft는 기존 Power BI API를 사용하여 PaaS 포함을 지원할 계획이지만, 이 시나리오를 구현할 시기를 아직 정하지 않았습니다.

### <a name="can-i-drill-through-from-a-power-bi-report-to-a-paginated-report"></a>Power BI 보고서에서 페이지를 매긴 보고서로 드릴스루할 수 있나요?

아직 드릴스루할 수 없으나 이 시나리오는 당연히 지원할 계획입니다.

### <a name="can-i-share-my-paginated-report-content-through-a-power-bi-app"></a>Power BI 앱을 통해 내 페이지를 매긴 보고서 콘텐츠를 공유할 수 있나요?

예. 페이지 번호를 매긴 보고서는 v1 및 v2 작업 영역에서 앱과 함께 배포되도록 지원됩니다. 

### <a name="will-other-report-specific-features-in-power-bi-like-pinning-to-report-tiles-to-dashboards-work-with-paginated-reports"></a>보고서 타일을 대시보드에 고정하는 기능과 같이, Power BI의 다른 보고서 관련 기능이 페이지를 매긴 보고서에서도 작동하나요?

가능한 한 보고서가 서비스의 동일한 주요 시나리오를 지원하도록 할 계획입니다.  보고서를 작성하는 도구가 달라도 소비자 관점에서는 포털의 목록에 있는 또 다른 보고서인 경우가 이상적입니다. 필요한 작업을 달성할 수 있으면 어떻게 만들어졌는지는 중요시하지 않습니다.  이 기능 패리티의 좋은 예가 계획된 주석 지원입니다. 기능 자체는 보고서 종류마다 약간 다르게 작동할 수 있으나 보고서 종료 둘 다에 대해 주석을 사용할 수 있습니다.

### <a name="is-a-migration-tool-planned-so-ssrs-customers-can-move-their-existing-reports-and-assets-to-power-bi"></a>SSRS 고객이 기존 보고서 및 자산을 Power BI로 이동할 수 있도록 마이그레이션 도구가 계획되어 있나요?

현재 콘텐츠를 자동으로 Power BI로 이동할 수 있는 옵션을 평가하고 있지만, GA 상태가 될 때까지 이 옵션은 사용할 수 없습니다.

### <a name="will-i-ever-be-able-to-create-both-paginated-reports-and-power-bi-reports-in-a-single-authoring-tool"></a>페이지를 매긴 보고서와 Power BI 보고서를 단일 제작 도구로 둘 다 만들 수 있나요?

이 시나리오를 사용하도록 설정하는 방법을 살펴보았지만 지금은 플랜에 이 시나리오가 포함되지 않습니다.

### <a name="is-there-a-report-viewer-control-for-paginated-reports-in-the-power-bi-service"></a>Power BI 서비스의 페이지를 매긴 보고서에 대한 보고서 뷰어 컨트롤이 있나요?

아니요. 현재 보고서 뷰어 컨트롤은 제공되지 않습니다.

### <a name="can-you-search-for-paginated-reports-from-the-new-home-experience-in-the-power-bi-service"></a>Power BI 서비스의 새 홈 환경에서 페이지를 매긴 보고서를 검색할 수 있나요?

예. 이제 홈에서 페이지를 매긴 보고서를 검색할 수 있습니다.  또한 새 홈 환경의 다른 부분에 보고서가 표시됩니다.

## <a name="next-steps"></a>다음 단계

- [Microsoft 다운로드 센터에서 Power BI 보고서 작성기 설치](https://go.microsoft.com/fwlink/?linkid=2086513)
- [자습서: 페이지를 매긴 보고서 만들기](paginated-reports-quickstart-aw.md)
