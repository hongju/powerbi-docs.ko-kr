---
title: SQL Server Reporting Services 보고서를 Power BI로 마이그레이션
description: SSRS(SQL Server Reporting Services) 보고서를 Power BI로 마이그레이션하기 위한 지침입니다.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 01/03/2020
ms.author: v-pemyer
ms.openlocfilehash: b1ce8644decb758775c0bbff87df7975a64692a2
ms.sourcegitcommit: 801d2baa944469a5b79cf591eb8afd18ca4e00b1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/11/2020
ms.locfileid: "75886116"
---
# <a name="migrate-sql-server-reporting-services-reports-to-power-bi"></a>SQL Server Reporting Services 보고서를 Power BI로 마이그레이션

이 문서는 SSRS(SQL Server Reporting Services) 보고서 작성자와 Power BI 관리자를 대상으로 작성되었습니다. 이 문서에서는 [RDL(Report Definition Language)](/sql/reporting-services/reports/report-definition-language-ssrs) 보고서를 Power BI로 마이그레이션하는 데 도움을 주는 지침을 제공합니다.

> [!NOTE]
> RDL 보고서만 마이그레이션이 가능합니다. Power BI에서는 RDL 보고서를 ‘페이지를 매긴 보고서’라고 합니다. 

지침은 4단계로 구분되어 제공됩니다. 먼저 문서 전체를 읽은 후에 보고서를 마이그레이션하는 것이 권장됩니다.

1. [시작하기 전 주의 사항](#before-you-start)
1. [마이그레이션 전 단계](#pre-migration-stage)
1. [마이그레이션 단계](#migration-stage)
1. [마이그레이션 후 단계](#post-migration-stage)

SSRS 서버의 가동을 중지하거나 보고서 사용자들의 작업을 방해하지 않으면서 마이그레이션을 진행할 수 있습니다. 어떤 데이터나 보고서도 제거할 필요가 없다는 사실을 이해하는 것이 중요합니다. 즉, 현재 환경을 중지시킬 준비가 될 때까지 전과 동일하게 유지할 수 있습니다.

## <a name="before-you-start"></a>시작하기 전에

마이그레이션을 시작하기 전에 먼저 환경이 특정 사전 요구 사항을 충족하는지 확인해야 합니다. 사전 요구 사항을 설명한 후에 유용한 마이그레이션 도구를 소개하겠습니다.

### <a name="preparing-for-migration"></a>마이그레이션 준비

보고서를 Power BI로 마이그레이션하기 위한 준비를 할 때 먼저 조직에 [Power BI Premium](../service-premium-what-is.md) 구독이 있는지 확인해야 합니다. 이 구독은 Power BI 페이지를 매긴 보고서를 호스트하고 실행하는 데 필요합니다.

### <a name="supported-versions"></a>지원되는 버전

온-프레미스에서 실행 중인 SSRS는 물론 Azure와 같은 클라우드 공급자가 호스트하는 가상 머신에 있는 SSRS도 마이그레이션할 수 있습니다. 

다음은 Power BI로의 마이그레이션이 지원되는 SQL Server 버전입니다.

> [!div class="checklist"]
> * SQL Server 2012
> * SQL Server 2014
> * SQL Server 2016
> * SQL Server 2017
> * SQL Server 2019

Power BI Report Server에서의 마이그레이션도 가능합니다.

### <a name="migration-tool"></a>마이그레이션 도구

보고서를 준비하고 마이그레이션할 때 [RDL 마이그레이션 도구](https://github.com/microsoft/RdlMigration)를 사용하는 것이 권장됩니다. 이 도구는 고객이 SSRS 서버에서 Power BI로 RDL 보고서를 마이그레이션하는 데 도움을 주기 위해 Microsoft에서 개발한 것입니다. 이 도구는 GitHub에서 받을 수 있으며, 마이그레이션 시나리오를 처음부터 끝까지 단계별로 안내합니다.

이 도구는 다음과 같은 작업을 자동화합니다.

* [지원되지 않는 데이터 원본](../paginated-reports-data-sources.md)과 [지원되지 않는 보고서 기능](../paginated-reports-faq.md#what-paginated-report-features-in-ssrs-arent-yet-supported-in-power-bi)이 있는지 확인
* ‘공유’ 리소스를 ‘임베디드’ 리소스로 변환:  
  * 공유 **데이터 원본**은 임베디드 데이터 원본이 됨
  * 공유 **데이터 세트**는 임베디드 데이터 세트가 됨
* (검사를 통과한) 보고서를 (프리미엄 용량에 있는) 지정된 Power BI 작업 영역으로 페이지를 매긴 보고서로 게시

기존 보고서가 수정 또는 제거되지는 않습니다. 작업이 완료되면 성공한 작업과 실패한 작업의 요약이 출력됩니다.

이 도구는 Microsoft가 지속적으로 개선할 수 있습니다. 도구를 개선하는 데 커뮤니티 여러분의 관심과 노력도 기울여 주시기 바랍니다.

## <a name="pre-migration-stage"></a>마이그레이션 전 단계

조직이 필수 사전 요건을 충족하는지 확인했으면 마이그레이션 전 단계를 시작할 준비가 된 것입니다.  이 단계는 3가지 하위 단계로 구성됩니다.

1. 검색
1. 평가
1. 준비

### <a name="discover"></a>검색

_검색_ 단계의 목표는 기존 SSRS 인스턴스를 식별하는 것입니다. 이 과정에서 네트워크를 검사하여 조직의 모든 SQL Server 인스턴스가 식별하는 작업이 이루어집니다.

[Microsoft Assessment and Planning Toolkit](https://www.microsoft.com/download/details.aspx?id=7826)을 사용할 수 있습니다. “MAP Toolkit”이라고도 하는 이 도구는 SQL Server 인스턴스, 버전 및 설치된 기능을 검색하고 보고합니다. 마이그레이션 계획 과정을 간소화해 주는 강력한 인벤토리, 평가 및 보고 도구입니다.

### <a name="assess"></a>평가

SSRS 인스턴스를 검색한 후에 이루어지는 _평가_ 단계의 목표는 마이그레이션할 수 없는 SSRS 보고서 또는 서버 항목을 파악하는 것입니다.

오직 RDL 보고서만 SSRS 서버에서 Power BI로 마이그레이션할 수 있습니다. 마이그레이션된 각 RDL 보고서는 Power BI 페이지를 매긴 보고서가 됩니다.

그러나 다음 SSRS 항목 유형은 Power BI로 마이그레이션할 수 없습니다.

* 공유 데이터 원본<sup>1</sup>
* 공유 데이터 세트<sup>1</sup>
* 리소스(예: 이미지 파일)
* KPI(SSRS 2016 이상-Enterprise Edition만 해당)
* 모바일 보고서(SSRS 2016 이상-Enterprise Edition만 해당)
* 보고서 모델(사용되지 않음)
* 보고서 파트(사용되지 않음)

<sup>1</sup> [RDL 마이그레이션 도구](https://github.com/microsoft/RdlMigration)는 지원되는 데이터 원본을 사용하는 공유 데이터 원본 및 공유 데이터 세트를 자동으로 변환합니다.

RDL 보고서가 [Power BI 페이지를 매긴 보고서에서 지원되지 않는 기능](../paginated-reports-faq.md#what-paginated-report-features-in-ssrs-arent-yet-supported-in-power-bi)을 사용할 경우, 보고서를 [Power BI 보고서](../consumer/end-user-reports.md)로 다시 만드는 방안을 고려할 수 있습니다. RDL 보고서가 마이그레이션되는 경우라 하더라도 가능한 경우 이를 Power BI 보고서로 새로 만드는 것이 권장됩니다.

일반적으로 Power BI 페이지를 매긴 보고서는 **인쇄** 또는 **PDF 생성**에 최적화되어 있습니다. Power BI 보고서는 **탐색 및 대화형 작업**에 최적화되어 있습니다. 자세한 내용은 [Power BI의 페이지를 매긴 보고서가 필요한 경우](report-paginated-or-power-bi.md)를 참조하세요.

### <a name="prepare"></a>준비

_준비_ 단계의 목표는 모든 것을 준비하는 것입니다. 이 단계에서는 Power BI 환경을 설정하고, 보고서를 보호하고 게시할 방법을 계획하고, 마이그레이션할 수 없는 SSRS 항목을 다시 만들 방안을 도출합니다.

1. Power BI 프리미엄 용량에서 [페이지를 매긴 보고서 워크로드](../service-admin-premium-workloads.md#paginated-reports)가 사용하도록 설정되어 있고 메모리가 충분한지 확인합니다.
1. 보고서 [데이터 원본](../paginated-reports-data-sources.md)에 대한 지원을 확인하고, 온-프레미스 데이터 원본과의 연결을 허용할 수 있도록 [Power BI 게이트웨이](../service-gateway-onprem.md)를 설정합니다.
1. Power BI 보안을 숙지하고, [Power BI 작업 영역 및 작업 영역 역할](../service-new-workspaces.md)을 사용하여 [SSRS 폴더 및 권한을 재현할 방법](/sql/reporting-services/security/secure-folders)을 계획합니다.
1. Power BI 공유를 숙지하고, [Power BI 앱](../service-create-distribute-apps.md)을 게시하여 콘텐츠를 배포할 방법을 계획합니다.
1. SSRS 공유 데이터 원본 대신 [공유 Power BI 데이터 세트](../service-datasets-build-permissions.md)를 사용하는 방안을 고려합니다.
1. [Power BI Desktop](../desktop-what-is-desktop.md)을 사용하여 모바일 최적화된 보고서를 개발합니다. 이때 SSRS 모바일 보고서 및 KPI 대신 [Power KPI 사용자 지정 시각적 개체](https://appsource.microsoft.com/product/power-bi-visuals/WA104381083?tab=Overview)를 사용하는 것이 좋습니다.
1. 보고서 작성자가 [Power BI 보고서 작성기](../report-builder-power-bi.md)를 설치해 두었고 조직에서 향후 릴리스를 간편하게 배포할 수 있는 환경이 구성되어 있는지 확인합니다.

## <a name="migration-stage"></a>마이그레이션 단계

Power BI 환경과 보고서를 준비했으면 _마이그레이션_ 단계를 진행할 준비가 된 것입니다.

마이그레이션에는 _수동_과 _자동_, 두 가지 옵션이 있습니다. 수동 마이그레이션은 적은 수의 보고서나 마이그레이션 전에 수정이 필요한 보고서에 적합합니다. 자동 마이그레이션은 많은 수의 보고서의 마이그레이션에 적합합니다.

### <a name="manual-migration"></a>수동 마이그레이션

SSRS 인스턴스 및 Power BI 작업 영역에 액세스할 권한이 있는 사용자는 모두 보고서를 Power BI로 수동 마이그레이션할 수 있습니다. 그 방법은 다음과 같습니다.

1. 마이그레이션하려는 보고서가 들어 있는 SSRS 포털을 엽니다.
1. 각 보고서 정의를 다운로드하고 .rdl 파일을 로컬에 저장합니다.
1. Power BI 보고서 작성기의 최신 버전을 열고 Azure AD 자격 증명을 사용하여 Power BI 서비스에 연결합니다. 
1. Power BI 보고서 작성기에서 각 보고서를 열고 다음을 수행합니다.
   1. 모든 데이터 원본과 데이터 세트가 보고서 정의에 임베디드되어 있고 [지원되는 데이터 원본](../paginated-reports-data-sources.md)인지 확인합니다.
   1. 미리 보기를 통해 보고서가 올바르게 렌더링되는지 확인합니다.
   1. _다른 이름으로 저장_ 옵션을 선택하고 _Power BI 서비스_를 선택합니다.
   1. 보고서를 포함하게 될 작업 영역을 선택합니다.
   1. 보고서가 저장되는지 확인합니다. 보고서 디자인에 포함된 특정 기능이 아직 지원되지 않을 경우 저장 작업이 실패하게 됩니다. 실패 이유도 제시됩니다. 이 경우 보고서 디자인을 수정한 후 저장을 다시 시도해야 합니다.

### <a name="automated-migration"></a>자동 마이그레이션

자동 마이그레이션에는 두 가지 옵션이 있습니다. 다음을 사용할 수 있습니다.

* RDL 마이그레이션 도구
* SSRS 및 Power BI용으로 공개된 API

[RDL 마이그레이션 도구](#migration-tool)는 이 문서에서 이미 설명한 바 있습니다.

공개된 SSRS 및 Power BI API를 사용하여 콘텐츠의 마이그레이션을 자동화할 수도 있습니다. RDL 마이그레이션 도구 역시 이 API를 사용하긴 하나, API를 직접 사용하면 정확한 요구 사항에 맞는 사용자 지정 도구를 개발할 수 있습니다.

API에 대한 자세한 내용은 다음을 참조하세요.

* [Power BI REST API 참조](../developer/rest-api-reference.md)
* [SQL Server Reporting Services REST API](/sql/reporting-services/developer/rest-api)

## <a name="post-migration-stage"></a>마이그레이션 후 단계

마이그레이션을 성공적으로 완료했으면 _마이그레이션 후_ 단계를 수행할 준비가 된 것입니다. 이 단계에는 일련의 마이그레이션 후 작업을 수행하여 모든 것이 효율적이고 올바르게 작동하는지 확인합니다.

### <a name="configure-data-sources"></a>데이터 원본 구성

보고서를 Power BI로 마이그레이션한 후에는 데이터 원본이 올바르게 설정되었는지 확인해야 합니다. 이 과정에는 게이트웨이 데이터 원본에 할당하고 [데이터 원본 자격 증명을 안전하게 저장](../paginated-reports-data-sources.md#azure-sql-database-authentication) 작업이 포함될 수 있습니다. 이러한 작업은 RDL 마이그레이션 도구에 의해 수행되지 않습니다.

### <a name="review-report-performance"></a>보고서 성능 검토

가능한 최상의 보고서 사용자 환경을 제공하기 위해 다음 작업을 완료하는 것이 권장됩니다.

1. [Power BI에서 지원하는 각 브라우저](../power-bi-browsers.md)에서 보고서를 테스트하여 보고서가 올바르게 렌더링되는지 확인합니다.
1. 테스트를 실행하여 SSRS 및 Power BI에서의 보고서 렌더링 시간을 비교합니다. Power BI 보고서가 적정 시간 안에 렌더링되는지 확인합니다.
1. 메모리가 부족하여 Power BI 보고서가 렌더링되지 않는 경우 [Power BI 프리미엄 용량에 추가 리소스를 할당](../service-admin-premium-workloads.md#paginated-reports)합니다.
1. 렌더링이 오래 걸리는 보고서의 경우 [보고서 첨부 파일이 포함된 메일 구독](../consumer/paginated-reports-subscriptions.md)으로 보고서 사용자에게 Power BI를 전달하는 방안을 고려합니다.
1. Power BI 데이터 세트를 기반으로 하는 Power BI 보고서의 경우 모델 디자인을 검토하여 완전히 최적화되었는지 확인합니다.

### <a name="reconcile-issues"></a>문제 대응

마이그레이션 후 단계는 모든 문제에 대응하고 성능 문제를 해결하는 데 중요합니다. 페이지를 매긴 보고서 워크로드를 용량에 추가하면 페이지를 매긴 보고서와 용량에 저장된 _그 밖의 콘텐츠_에서 성능 저하가 발생할 수 있습니다.

이러한 문제를 이해하고 문제에 대응하는 구체적인 방법을 포함하여 문제에 대해 자세히 알아보려면 다음 문서를 참조하세요.

* [Premium 용량 최적화](../service-premium-capacity-optimize.md)
* [앱 내에서 프리미엄 용량 모니터링](../service-admin-premium-monitor-capacity.md)

## <a name="next-steps"></a>다음 단계

이 문서에 대한 자세한 내용은 다음 리소스를 참조하세요.

* [Power BI Premium에서 페이지를 매긴 보고서란?](../paginated-reports-report-builder-power-bi.md)
* Guy in a cube 비디오: [Power BI의 페이지를 매긴 보고서 소개](https://www.youtube.com/watch?v=wfqn45XNK3M)
* [Power BI의 페이지를 매긴 보고서가 필요한 경우](report-paginated-or-power-bi.md)
* [Power BI의 페이지를 매긴 보고서: FAQ](../paginated-reports-faq.md)
* [Power BI 프리미엄 FAQ](../service-premium-faq.md)
* [RDL 마이그레이션 도구](https://github.com/microsoft/RdlMigration)
* 궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](https://community.powerbi.com/)
* 제안? [Power BI 개선을 위한 아이디어 제공](https://ideas.powerbi.com)

조직에서 마이그레이션 프로세스를 성공적으로 완료하는 데 도움을 줄 Power BI 파트너와 협력할 수 있습니다. Power BI 파트너와 협력하려면 [Power BI 파트너 포털](https://powerbi.microsoft.com/partners/)을 방문하세요.
