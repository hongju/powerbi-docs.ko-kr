---
title: 미국 정부 기관 고객용 Power BI - 개요
description: 미국 정부 고객은 Office 365 정부 플랜에 Power BI Pro 구독을 추가할 수 있습니다. 이 서비스 설명에서 가입 방법을 알아보고 기능 가용성을 검토하세요.
author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 01/13/2020
ms.author: kfollis
LocalizationGroup: Get started
ms.openlocfilehash: 26dabde3846ec33e2f5910de75fb8165cce6513a
ms.sourcegitcommit: 3d6b27e3936e451339d8c11e9af1a72c725a5668
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2020
ms.locfileid: "76160768"
---
# <a name="power-bi-for-us-government-customers"></a>미국 정부 기관 고객용 Power BI
이 문서는 Office 365 정부 플랜의 일부로 Power BI를 배포하는 정부 기관 고객을 위한 것입니다. 정부 플랜은 미국 규정 준수 및 보안 표준을 충족해야 하는 조직의 고유한 요구 사항을 위해 설계되었습니다. 미국 정부 기관 고객을 위해 고안된 Power BI 서비스는 상용 Power BI 서비스 버전과 다릅니다. 이러한 기능 차이는 다음 섹션에 설명되어 있습니다.

## <a name="add-power-bi-to-your-office-365-government-plan"></a>Office 365 정부 플랜에 Power BI 추가

Power BI 미국 정부 구독을 획득하고 사용자에게 라이선스를 할당하려면 먼저 Office 365 정부 플랜에 등록해야 합니다. 조직에 이미 Office 365 정부 플랜이 있는 경우 [Power BI Pro 정부 구독 구매](#purchase-a-power-bi-pro-government-subscription)로 건너뜁니다.

### <a name="enroll-in-office-365-government-plan"></a>Office 365 정부 플랜에 등록

신규 고객은 정부 플랜에 등록하기 전에 조직의 자격 유효성을 검사해야 합니다.  먼저 [정부 기관용 Office 365 자격 유효성 검사 양식](https://www.microsoft.com/microsoft-365/government/eligibility-validation)을 작성합니다. 조직에 적합한 플랜을 선택하려면 [Office 365 미국 정부 서비스 설명](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government)을 참조하세요.

> [!NOTE]
> 이미 상용 환경에 Power BI를 배포했고 미국 정부 클라우드로 마이그레이션하려는 경우, Office 365 정부 플랜에 새로운 Power BI Pro 구독을 추가해야 합니다. 다음으로 상용 데이터를 미국 정부 기관용 Power BI 서비스에 복제하고 사용자 계정에서 상용 라이선스 할당을 제거한 다음 사용자 계정에 Power BI Pro 정부 기관 라이선스를 할당합니다.
>
>

### <a name="government-cloud-instances"></a>정부 클라우드 인스턴스
Office 365는 다양한 규정 준수 요구 사항을 충족하기 위해 다양한 정부 기관용 환경을 제공합니다. 각 환경에서 제공하는 기능에 대한 자세한 내용은 연결된 서비스 설명을 참조하세요.

* [Office 365 GCC(정부 커뮤니티 클라우드)](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc)는 연방, 주, 지방 정부를 위해 설계되었습니다.

* [Office 365 GCC High(정부 커뮤니티 클라우드-높음)](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc-high-and-dod)은 연방 기관, 방위 산업, 항공 우주 산업 및 제어되는 미분류 정보를 보유하는 기타 조직을 위해 설계되었습니다. 이 환경은 국가 안보 조직 및 ITAR(국제 무기 거래 규정) 또는 DFARS(국방 연방 획득 규칙 부록) 요구 사항이 있는 회사에 적합합니다.

* [Office 365 DoD 환경](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc-high-and-dod)은 미국 국방부만을 위해 설계되었습니다. 

### <a name="purchase-a-power-bi-pro-government-subscription"></a>Power BI Pro 정부 구독 구매

Power BI 구독은 Office 365를 배포한 후 추가할 수 있습니다. [미국 정부 기관 등록](service-govus-signup.md#existing-office-government-cloud-customers)의 단계별 지침에 따라 Power BI Pro 정부 서비스를 구매합니다. Power BI를 사용해야 하는 모든 사용자에게 충분한 라이선스를 구입한 다음 개별 사용자 계정에 할당합니다.

> [!IMPORTANT]
> Power BI 미국 정부는 무료 라이선스로 제공되지 않습니다. 각 사용자는 Pro 라이선스가 할당되어야 정부 커뮤니티 클라우드에 액세스할 수 있습니다. 무료 라이선스가 할당된 사용자 계정은 상용 클라우드에만 액세스할 권한이 있으며, 인증 및 액세스 문제가 발생합니다. 라이선스 유형의 차이점을 검토하려면 [라이선스 유형별 Power BI 서비스 기능](service-features-license-type.md)을 참조하세요.
>
>

## <a name="connect-to-power-bi-for-us-government"></a>미국 정부 기관용 Power BI에 연결

미국 정부용 Power BI에 연결하려면 상용 사용자와는 다른 URL을 사용해야 합니다. Power BI에 로그인하려면 다음 URL을 사용하세요.

| 상용 버전 URL | 미국 정부 버전 URL | GCC High를 위한 미국 정부 URL |
| --- | --- | --- |
| https://app.powerbi.com/ |[https://app.powerbigov.us](https://app.powerbigov.us) | [https://app.high.powerbigov.us](https://app.high.powerbigov.us) |

계정이 둘 이상의 클라우드로 프로비전될 수 있습니다. 이 경우, Power BI Desktop을 사용할 때 로그인 시 연결할 클라우드를 선택할 수 있습니다.

## <a name="connectivity-between-government-and-global-azure-cloud-services"></a>정부와 글로벌 Azure 클라우드 서비스 간의 연결

Azure는 여러 클라우드에 분산되어 있습니다. 기본적으로 클라우드별 인스턴스와의 연결을 열도록 방화벽 규칙을 사용할 수 있지만 클라우드 간 네트워킹은 다릅니다.  퍼블릭 클라우드의 서비스와 정부 커뮤니티 클라우드의 서비스가 통신하려면 특정 방화벽 규칙을 구성해야 합니다. 예를 들어 Power BI 정부 클라우드 배포에서 SQL의 퍼블릭 클라우드 인스턴스에 액세스하려면 SQL에서 방화벽 규칙이 필요합니다. 다음 데이터 센터의 Azure Government 클라우드와의 연결을 허용하도록 SQL에서 특정 방화벽 규칙을 구성합니다.

* USGov 아이오와
* USGov 버지니아
* USGov 텍사스
* USGov 애리조나

퍼블릭 클라우드에서는 IP 범위를 사용할 수 있습니다. 미국 정부 클라우드 IP 범위를 얻으려면 [Azure IP 범위 및 서비스 태그 - 미국 정부 클라우드](https://www.microsoft.com/download/details.aspx?id=57063) 파일을 다운로드합니다. 

SQL에서 방화벽을 설정하려면 단계에 따라 [IP 방화벽 규칙을 만들고 관리](https://docs.microsoft.com/azure/sql-database/sql-database-firewall-configure#create-and-manage-ip-firewall-rules)합니다.

## <a name="power-bi-feature-availability"></a>Power BI 기능 가용성

정부 클라우드 고객의 요구 사항을 수용하기 위해 정부 플랜과 상용 플랜에는 몇 가지 차이점이 있습니다. 각 정부 환경에서 사용할 수 있는 기능을 확인하려면 다음 표를 참조하세요.

|기능 |   |GCC |GCC-High |DoD|
|------|------|------|------|------|
|관리|무료 라이선스|사용할 수 없음|사용할 수 없음|사용할 수 없음|
|  |데이터 스토리지 제한 설정|사용 가능|사용 가능|사용 가능|
|  |공유 및 액세스 제어에 Active Directory 그룹 사용|사용 가능|사용 가능|사용 가능|
|  |Office 365 보안 및 준수 관리 센터를 통한 감사|사용 가능|사용 가능|사용 가능|
|  |외부 사용자 공유|사용 가능|사용 가능|사용 가능|
|  |보고서 및 대시보드의 사용량 메트릭|사용할 수 없음|사용할 수 없음|사용할 수 없음|
|  |GCC와 상용 클라우드 간 Azure B2B|사용할 수 없음|사용할 수 없음|사용할 수 없음|
|보고서 작성|대시보드 및 보고서 만들기 및 보기|사용 가능|사용 가능|사용 가능|
|  |예약된 데이터 새로 고침|사용 가능|사용 가능|사용 가능|
|  |새로 고칠 수 있는 팀 대시보드|사용 가능|사용 가능|사용 가능|
|  |페이지를 매긴 보고서|USGov 텍사스 및 USGov 버지니아에서만 사용 가능 |사용 가능|로드맵|
|  |템플릿 앱|사용할 수 없음|사용할 수 없음|사용할 수 없음|
|데이터에 연결|Excel에서 데이터 및 보고서 가져오기|사용 가능|사용 가능|사용 가능|
|  |CSV 파일에서 데이터 가져오기|사용 가능|사용 가능|사용 가능|
|  |Power BI Desktop 파일에서 데이터 가져오기|사용 가능|사용 가능|사용 가능|
|  |CDS 연결|사용할 수 없음|사용할 수 없음|사용할 수 없음|
|  |Azure Data Lake Storage Gen2 커넥터|사용할 수 없음|사용할 수 없음|사용할 수 없음|
|데이터 관리|데이터 관리 게이트웨이|사용 가능|사용 가능|사용 가능|
|  |Azure SQL에서 데이터 암호화|사용 가능|사용 가능|사용 가능|
|  |Power BI용 Blob Storage에서 데이터 암호화|사용 가능|사용 가능|사용 가능|
|제품 간 통합|Power BI 웹 파트를 사용하여 SharePoint Online에 포함|사용할 수 없음|사용할 수 없음|사용할 수 없음|
|  |Embed 웹 파트를 사용하여 SharePoint Online에 포함|사용 가능|사용 가능|사용 가능|
|  |데이터 흐름 및 AI 함수|사용할 수 없음|사용할 수 없음|사용할 수 없음|
|  |데이터 기반 경고를 위한 Power Automate 연결|사용할 수 없음|사용할 수 없음|사용할 수 없음|
|  |Teams의 Power BI 탭|사용할 수 없음|사용할 수 없음|사용할 수 없음|
|  |자동화된 Machine Learning|사용할 수 없음|사용할 수 없음|사용할 수 없음|
|  |Cognitive Services|사용할 수 없음|사용할 수 없음|사용할 수 없음|
|  |Azure 기계 학습|사용할 수 없음|사용할 수 없음|사용할 수 없음|

## <a name="next-steps"></a>다음 단계

* [미국 정부 기관용 Power BI 등록](service-govus-signup.md)
* <a href="https://channel9.msdn.com/Blogs/Azure/Cognitive-Services-HDInsight-and-Power-BI-on-Azure-Government">Power BI 미국 정부 데모</a>
* [Power BI 서비스 시작](service-get-started.md)
* [Power BI Desktop이란?](desktop-what-is-desktop.md)

