---
title: Power BI 고가용성, 장애 조치(failover) 및 재해 복구 FAQ
description: Power BI 서비스가 고가용성을 제공하고 비즈니스 연속성 및 재해 복구를 사용자에게 제공하는 방법을 이해합니다.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 09/09/2019
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: b8f98541b70c3573d9f31b5e59196cd37d322bb3
ms.sourcegitcommit: a97c0c34f888e44abf4c9aa657ec9463a32be06f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2019
ms.locfileid: "71075228"
---
# <a name="power-bi-high-availability-failover-and-disaster-recovery-faq"></a>Power BI 고가용성, 장애 조치(failover) 및 재해 복구 FAQ

이 문서에서는 Power BI 서비스가 고가용성을 제공하고 비즈니스 연속성 및 재해 복구를 사용자에게 제공하는 방법을 설명합니다. 이 문서를 읽은 후에는 고가용성이 실현되는 방법, Power BI 장애 조치(failover)를 수행하는 상황과 장애 조치(failover) 시 서비스에서 예상되는 사항에 대해 더 잘 이해해야 합니다.

## <a name="what-does-high-availability-mean-for-power-bi"></a>Power BI에 대해 "고가용성"이 의미하는 것은 무엇인가요?

Power BI는 SaaS(Software as a Service)로 완전 관리형 소프트웨어입니다.  Microsoft는 사용자가 항상 자신의 보고서에 액세스할 수 있도록 인프라 오류에 탄력적으로 대처하도록 설계하고 운영합니다.  서비스는 [99.9% SLA](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=37)에서 지원됩니다.

## <a name="what-is-a-power-bi-failover"></a>Power BI 장애 조치(failover)란?

Power BI는 비즈니스 연속성을 보장하기 위해 Azure 데이터 센터(지역이라고도 함)의 각 구성 요소의 여러 인스턴스를 유지 관리합니다. 가동 중단 또는 Power BI가 한 지역에서 액세스할 수 없거나 제대로 작동할 수 없는 문제가 있는 경우, Power BI는 해당 지역의 모든 구성 요소를 백업 인스턴스로 가져오지 못합니다. 장애 조치(failover)는 새 지역에서 Power BI 서비스 인스턴스에 대한 가용성과 작동성을 복원합니다(일반적으로 [Microsoft 보안 센터](https://www.microsoft.com/TrustCenter/CloudServices/business-application-platform/data-location)에 명시된 것과 동일한 지리적 위치 내에 있음).

장애 조치(failover) Power BI 서비스 인스턴스는 _읽기 작업_만 지원합니다. 즉, 장애 조치(failover) 중에는 새로 고침, 보고서 게시 작업, 대시보드 또는 보고서 수정 및 Power BI 메타데이터 변경(예: 보고서에 주석 삽입)이 필요한 기타 작업이 지원되지 않습니다.  대시보드 표시 및 보고서 표시와 같은 작업(온-프레미스 데이터 원본에 대한 DirectQuery 또는 Live Connect를 기반으로 하지 않음)은 계속 정상적으로 작동합니다.

## <a name="how-are-backup-instances-kept-in-sync-with-my-data"></a>백업 인스턴스를 데이터와 동기화하는 방법은?

모든 Power BI 서비스 구성 요소는 정기적으로 해당 백업 인스턴스를 동기화합니다. Power BI에서 업로드하거나 변경한 모든 콘텐츠에 대해 15분 지정 시간 동기화가 목표입니다. 장애 조치(failover) 이벤트에서 Power BI는 [Azure 스토리지 지역 중복 복제](/azure/storage/common/storage-redundancy-grs) 및 [Azure SQL 지역 중복 복제](/azure/sql-database/sql-database-active-geo-replication)를 사용하여 백업 인스턴스가 다른 지역에 존재하고 장애 조치(failover) 시 사용할 수 있도록 보장합니다.

## <a name="where-are-the-failover-clusters-located"></a>장애 조치(failover) 클러스터는 어디에 있나요?

백업 인스턴스는 [Microsoft 보안 센터](https://www.microsoft.com/TrustCenter/CloudServices/business-application-platform/data-location)에 표시된 경우를 제외하고 조직에서 Power BI에 등록할 때 선택한 동일한 지리적 위치(지역) 내에 있습니다. 한 지역은 여러 지역을 포함할 수 있으며 Microsoft는 모든 데이터 복원력을 위해 지정된 지역 내의 모든 지역에 데이터를 복제할 수 있습니다. Microsoft는 고객 데이터를 지역 외부에서 복제하거나 이동하지 않습니다. Power BI가 제공하는 지역 및 지역 내의 매핑은 [Microsoft 보안 센터](https://www.microsoft.com/TrustCenter/CloudServices/business-application-platform/data-location)를 참조하세요.

## <a name="how-does-microsoft-decide-to-failover"></a>Microsoft가 장애 조치(failover)를 결정하는 방법은?

장애 조치(failover)가 필요한 시기를 나타내는 두 가지 시스템이 있습니다.

- 외부 및 내부 모니터링 프로브는 가용성이 부족하거나 제대로 작동하지 못함을 나타냅니다. 이러한 표시는 Power BI 구성 요소에서 감지된 중단이나 Power BI가 지역에서 사용하는 하나 이상의 서비스에 기반할 수 있습니다.
- Microsoft Azure의 중앙 운영 팀은 지역의 중요한 중단을 알려줍니다.

두 경우 모두 Power BI 실행 팀 멤버가 장애 조치(failover)를 결정합니다. 결정 자체는 자동화되지 않습니다. 결정이 내려지면 장애 조치(failover) 프로세스가 자동으로 수행됩니다.

## <a name="how-do-i-know-power-bi-is-now-in-failover-mode"></a>Power BI가 현재 장애 조치(failover) 모드에 있는지 확인하는 방법은?

Power BI 지원 페이지에 알림이 게시됩니다([https://powerbi.microsoft.com/en-us/support/](https://powerbi.microsoft.com/en-us/support/)). 알림에는 게시, 새로 고침, 대시보드 만들기, 대시보드 복제 및 권한 변경을 포함하여 장애 조치(failover) 중에는 사용할 수 없는 주요 작업이 포함됩니다.

## <a name="how-long-does-it-take-power-bi-to-fail-over"></a>Power BI를 장애 조치(failover)하는 데 얼마나 걸리나요?

장애 조치(failover) 결정이 내려지면 장애 조치(failover) 인스턴스를 사용할 수 있기까지 최대 60분이 걸릴 수 있습니다.

## <a name="when-does-my-power-bi-instance-return-to-the-original-region"></a>내 Power BI 인스턴스가 원래 영역으로 돌아가는 시기는?

장애 조치(failover)를 초래한 문제가 해결되면 power BI 서비스 인스턴스가 원래 영역으로 돌아갑니다. Power BI 지원 페이지 확인: 문제가 해결되면 Power BI 팀은 장애 조치(failover)를 설명하는 알림을 제거합니다. 이 시점에서 작업은 정상으로 돌아와야 합니다.

## <a name="am-i-responsible-for-the-availability-of-my-power-bi-solution"></a>내 Power BI 솔루션의 가용성에 대한 책임이 있나요?

조직에서 사용하는 Power BI 솔루션에 다음 요소 중 하나가 포함되어 있는 경우, 솔루션의 고가용성 유지를 보장하기 위해 몇 가지 작업을 수행해야 합니다.

- 조직에서 Power BI Premium을 사용하는 경우 프리미엄 용량이 배포의 로드 요구 사항을 충족시킬 수 있는 크기인지 확인해야 합니다.  [Power BI Premium 계획 및 배포 백서](https://aka.ms/Premium-Capacity-Planning-Deployment) 및 [Power BI Premium 용량 메트릭 앱](service-admin-premium-monitor-capacity.md)을 통해 이 요구 사항을 계획하고 충족할 수 있습니다. 정기적으로 새로운 기능을 메트릭 앱과 Power BI의 관리 포털에 추가하여 도움을 줍니다.
- 조직에서 온-프레미스 데이터 게이트웨이를 사용하여 온-프레미스 데이터 원본에 액세스하는 경우, 고가용성을 지원하려면 [이 문서에 설명된 대로](/data-integration/gateway/service-gateway-high-availability-clusters) 게이트웨이를 설정해야 합니다. 가져오기 모드에서 보고서를 새로 고치거나 DirectQuery 또는 Live Connect를 사용하여 데이터 또는 데이터 모델에 액세스하는 경우 이 지침을 따릅니다.

## <a name="will-gateways-function-when-in-failover-mode"></a>장애 조치(failover) 모드에 있을 때 게이트웨이가 작동하나요?

아니요. 온-프레미스 데이터 원본(직접 쿼리 및 Live Connect를 기반으로 하는 모든 보고서 및 대시보드)에서 필요한 데이터는 장애 조치(failover) 중에는 작동하지 않습니다. 게이트웨이 구성은 변경되지 않습니다. Power BI 인스턴스가 원래 상태로 돌아오면 게이트웨이는 일반 함수로 돌아갑니다.
