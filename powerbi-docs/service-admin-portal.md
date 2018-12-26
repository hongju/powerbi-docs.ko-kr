---
title: Power BI 관리 포털
description: 관리 포털을 통해 조직에서 Power BI의 테넌트 관리를 사용할 수 있습니다. 사용 메트릭, Office 365 관리 센터 액세스 및 설정 등과 같은 항목을 포함하고 있습니다.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 10/30/2018
ms.custom: seodec18
LocalizationGroup: Administration
ms.openlocfilehash: 5f377f60935f23b62b90731c5d7bc16c8119ab83
ms.sourcegitcommit: 72c9d9ec26e17e94fccb9c5a24301028cebcdeb5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/07/2018
ms.locfileid: "53026710"
---
# <a name="administering-power-bi-in-the-admin-portal"></a>관리 포털에서 Power BI 관리

관리 포털을 통해 조직의 Power BI ‘테넌트’를 관리할 수 있습니다. 포털에는 사용 메트릭, Office 365 관리 센터 액세스 및 설정 등과 같은 항목이 포함되어 있습니다.

전체 관리 포털은 Office 365의 전역 관리자이거나 Power BI 서비스 관리자 역할에 할당된 모든 사용자가 액세스할 수 있습니다. 이러한 역할 중 하나를 할당받지 않은 경우에는 포털에 **용량 설정**만 표시됩니다. Power BI 서비스 관리자 역할에 대한 자세한 내용은 [Power BI 관리자 역할 이해](service-admin-role.md)를 참조하세요.

## <a name="how-to-get-to-the-admin-portal"></a>관리 포털에 도달하는 방법

Power BI 관리 포털에 대한 액세스 권한을 얻으려면 계정이 Office 365 또는 Azure Active Directory 내에서 **전역 관리자**로 표시되거나 Power BI 서비스 관리자 역할이 할당되어야 합니다. Power BI 서비스 관리자 역할에 대한 자세한 내용은 [Power BI 관리자 역할 이해](service-admin-role.md)를 참조하세요. Power BI 관리 포털에 도달하려면 다음을 수행합니다.

1. Power BI 서비스의 오른쪽 위에서 설정 기어를 선택합니다.

1. **관리 포털**을 선택합니다.

    ![관리 포털에 대한 설정](media/service-admin-portal/powerbi-admin-settings.png)

포털에는 7개의 탭이 있습니다. 이 문서의 나머지 부분에서는 이러한 각 탭에 대한 정보를 제공합니다.

![관리 포털 탐색](media/service-admin-portal/powerbi-admin-landing-page.png)

* [사용 메트릭](#usage-metrics)
* [사용자](#users)
* [감사 로그](#audit-logs)
* [테넌트 설정](#tenant-settings)
* [프리미엄 설정](#premium-settings)
* [embed 태그](#embed-codes)
* [조직의 시각적 개체](#organization-visuals)

## <a name="usage-metrics"></a>사용 메트릭

**사용 메트릭**을 통해 조직의 Power BI 사용을 모니터링할 수 있습니다. 또한 조직을 위한 Power BI 내에서 가장 활발한 사용자 및 그룹이 누구인지 확인하는 기능을 제공합니다.

> [!NOTE]
> 대시보드에 처음 액세스할 때 또는 대시보드를 오랫동안 보지 않았다가 다시 방문한 후 대시보드를 로드하는 동안 로드 중 화면이 표시될 수 있습니다.

대시보드가 로드된 후 타일 섹션 두 개가 표시됩니다. 첫 번째 섹션은 개별 사용자에 대한 사용량 데이터를 포함하고 있으며 두 번째 섹션은 조직의 그룹에 대해 유사한 정보를 포함하고 있습니다.

다음은 각 타일에 표시되는 내용에 대한 요약입니다.

* 사용자 작업 영역의 모든 대시보드, 보고서 및 데이터 집합에 대한 고유한 개수입니다.
  
    ![대시보드, 보고서, 데이터 집합에 대한 고유한 개수](media/service-admin-portal/powerbi-admin-usage-metrics-number-tiles.png)

* 액세스할 수 있는 사용자 수별로 가장 많이 사용한 대시보드입니다. 예를 들어 사용자 3명과 공유하는 대시보드가 있는데 서로 다른 두 사용자가 연결한 콘텐츠 팩에 이를 추가하면 개수는 6(1+3+2)개가 됩니다.
  
    ![가장 많이 사용한 대시보드](media/service-admin-portal/powerbi-admin-usage-metrics-top-dashboards.png)

* 사용자가 연결한 가장 인기 있는 콘텐츠입니다. 사용자가 데이터 가져오기 프로세스를 통해 도달할 수 있는 모든 것, 다시 말해서 SaaS 콘텐츠 팩, 조직 콘텐츠 팩, 파일 또는 데이터베이스가 이에 해당합니다.
  
    ![가장 많이 사용한 패키지](media/service-admin-portal/powerbi-admin-usage-metrics-top-connections.png)

* 직접 만든 대시보드 및 공유하는 대시보드를 모두 포함하여 가지고 있는 대시보드 수를 기반으로 하는 최상위 사용자의 뷰입니다.
  
    ![최상위 사용자 - 대시보드](media/service-admin-portal/powerbi-admin-usage-metrics-top-users-dashboards.png)

* 가지고 있는 보고서 수를 기반으로 하는 최상위 사용자의 뷰입니다.
  
    ![최상위 사용자 - 보고서](media/service-admin-portal/powerbi-admin-usage-metrics-top-users-reports.png)

두 번째 섹션은 동일한 유형의 정보를 보여 주지만 그룹을 기반으로 합니다. 여기에서는 조직에서 가장 활발한 그룹 및 해당 그룹이 사용 중인 콘텐츠의 종류를 확인할 수 있습니다.

이 정보를 사용하여 조직의 사용자가 Power BI를 사용하는 방법을 실제로 파악할 수 있으며 조직에서 매우 활발한 사용자 및 그룹을 인식할 수 있습니다.

## <a name="users"></a>사용자

Office 365 관리 센터에서 Power BI 사용자, 그룹 및 관리자를 관리합니다. **사용자** 탭은 테넌트의 관리 센터에 대한 링크를 제공합니다.

![O365 관리 센터로 이동](media/service-admin-portal/powerbi-admin-manage-users.png)

## <a name="audit-logs"></a>감사 로그

Office 365 Security & Compliance 센터에서 Power BI 감사 로그를 관리합니다. **감사 로그** 탭은 테넌트의 Security & Compliance 센터에 대한 링크를 제공합니다. [자세히 알아보기](service-admin-auditing.md)

감사 로그를 사용하려면 [**내부 활동 감사 및 규정 준수를 위해 감사 로그 만들기**](#create-audit-logs-for-internal-activity-auditing-and-compliance) 설정이 사용하도록 설정되어 있는지 확인합니다.

## <a name="tenant-settings"></a>테넌트 설정

**테넌트 설정** 탭에서는 조직에서 사용할 수 있는 기능에 대한 세분화된 제어를 제공합니다. 중요한 데이터에 대한 우려가 있는 경우 일부 기능은 사용자의 조직에 적합하지 않을 수 있거나 특정 기능을 특정 그룹만 사용할 수 있도록 할 수 있습니다.

다음 이미지는 **테넌트 설정** 탭의 처음 두 섹션을 보여 줍니다.

![테넌트 설정](media/service-admin-portal/powerbi-admin-tenant-settings.png)

> [!NOTE]
> 설정 변경 내용이 테넌트의 모든 사용자에게 적용되려면 최대 10분까지 걸릴 수 있습니다.

설정에는 다음과 같은 세 가지 상태가 포함될 수 있습니다.

* **전체 조직에서 사용하지 않도록 설정됨**: 조직의 누구도 이 기능을 사용할 수 없습니다.

    ![모두 사용 안 함 설정](media/service-admin-portal/powerbi-admin-tenant-settings-disabled.png)

* **전체 조직에서 사용하도록 설정됨**: 조직의 모든 사용자가 이 기능을 사용할 수 있습니다.

    ![모두 사용 설정](media/service-admin-portal/powerbi-admin-tenant-settings-enabled.png)

* **조직 일부에서 사용하도록 설정됨**: 조직에서 사용자 또는 그룹의 특정 하위 세트만 이 기능을 사용할 수 있습니다.

    특정 사용자 그룹을 제외하고 전체 조직에서 기능을 사용하도록 설정할 수 있습니다.

    ![하위 집합 사용 설정](media/service-admin-portal/powerbi-admin-tenant-settings-enabled-except.png)

    또한 특정 사용자 그룹에만 기능을 사용하도록 설정하고 사용자 그룹에 대해 사용하지 않도록 설정할 수도 있습니다. 이 경우 특정 사용자가 허용되는 그룹에 있더라도 해당 기능에 액세스할 수 없게 됩니다.

    ![제외 사용 설정](media/service-admin-portal/powerbi-admin-tenant-settings-enabled-except2.png)

다음 몇몇 섹션에서는 다양한 형식의 테넌트 설정 개요를 제공합니다.

## <a name="workspace-settings"></a>작업 영역 설정

### <a name="create-workspaces-preview"></a>작업 영역 만들기(미리 보기)

조직의 사용자는 앱 작업 영역을 만들어 대시보드, 보고서 및 기타 콘텐츠에서 공동 작업할 수 있습니다. [자세히 알아보기](service-create-the-new-workspaces.md)

## <a name="export-and-sharing-settings"></a>내보내기 및 공유 설정

### <a name="share-content-to-external-users"></a>외부 사용자에게 콘텐츠 공유

조직의 사용자는 조직 외부의 사용자와 대시보드를 공유할 수 있습니다. [자세히 알아보기](service-share-dashboards.md#share-a-dashboard-or-report-with-people-outside-your-organization)

![외부 사용자 설정](media/service-admin-portal/powerbi-admin-sharing-external-02.png)

다음 이미지는 외부 사용자와 공유할 때 표시되는 메시지를 보여 줍니다.

![외부 사용자와 공유](media/service-admin-portal/powerbi-admin-sharing-external.png)

### <a name="publish-to-web"></a>웹에 게시

조직의 사용자는 웹에 보고서를 게시할 수 있습니다. [자세히 알아보기](service-publish-to-web.md)

다음 이미지는 **웹에 게시** 설정을 사용하도록 설정한 경우 보고서의 **파일** 메뉴를 보여 줍니다.

![웹에 게시 설정](media/service-admin-portal/powerbi-admin-publish-to-web.png)

**웹에 게시** 설정에 따라 UI에 다른 옵션이 표시됩니다.

|특정 |전체 조직에 대해 사용 |전체 조직에 대해 사용 안 함 |특정 보안 그룹   |
|---------|---------|---------|---------|
|보고서의 **파일** 메뉴 아래에 있는 **웹 게시**.|모든 사용자에 대해 사용|모든 사용자에게 표시 안 함|권한 있는 사용자 또는 그룹에만 표시.|
|**설정** 아래의 **embed 태그 관리**|모든 사용자에 대해 사용|모든 사용자에 대해 사용|모든 사용자에 대해 사용<br><br>권한 있는 사용자 또는 그룹에만 * **삭제** 옵션 제공.<br>모든 사용자에 대해 * **코드 가져오기** 사용.|
|관리자 포털 내의 **embed 태그**|상태는 다음 중 하나를 반영합니다.<br>* 활성<br>* 지원되지 않음<br>* 차단됨|상태에 **사용 안 함**이 표시됨|상태는 다음 중 하나를 반영합니다.<br>* 활성<br>* 지원되지 않음<br>* 차단됨<br><br>테넌트 설정에 따라 사용자에게 권한이 없으면 상태가 **침해됨**으로 표시됩니다.|
|게시된 기존 보고서|모두 사용|모두 사용 안 함|보고서가 모든 사용자에 대해 계속 렌더링합니다.|

### <a name="export-data"></a>데이터 내보내기

조직의 사용자는 타일 또는 시각화에서 데이터를 내보낼 수 있습니다. [자세히 알아보기](visuals/power-bi-visualization-export-data.md)

다음 이미지는 타일에서 데이터를 내보내는 옵션을 보여 줍니다.

![타일에서 데이터 내보내기](media/service-admin-portal/powerbi-admin-export-data.png)

> [!NOTE]
> **데이터 내보내기**를 사용하지 않도록 설정하면 사용자는 Power BI 서비스 라이브 연결과 함께 **Excel에서 분석** 기능을 사용할 수 없습니다.

### <a name="export-reports-as-powerpoint-presentations"></a>보고서를 PowerPoint 프레젠테이션으로 내보내기

조직의 사용자는 PowerPoint 파일로 Power BI 보고서를 내보낼 수 있습니다. [자세히 알아보기](consumer/end-user-powerpoint.md)

다음 이미지는 **보고서를 PowerPoint 프레젠테이션으로 내보내기** 설정을 사용하도록 설정한 경우 보고서의 **파일** 메뉴를 보여 줍니다.

![보고서를 PowerPoint 프레젠테이션으로 내보내기](media/service-admin-portal/powerbi-admin-powerpoint.png)

### <a name="print-dashboards-and-reports"></a>대시보드 및 보고서 인쇄

조직의 사용자는 대시보드 및 보고서를 인쇄할 수 있습니다. [자세히 알아보기](consumer/end-user-print.md)

다음 이미지는 대시보드를 인쇄하는 옵션을 보여 줍니다.

![대시보드 인쇄](media/service-admin-portal/powerbi-admin-print-dashboard.png)

다음 이미지는 **대시보드 및 보고서 인쇄** 설정을 사용할 수 있을 때 보고서의 **파일** 메뉴를 보여 줍니다.

![보고서 인쇄](media/service-admin-portal/powerbi-admin-print-report.png)

## <a name="content-pack-and-app-settings"></a>콘텐츠 팩 및 앱 설정

### <a name="publish-content-packs-and-apps-to-the-entire-organization"></a>콘텐츠 팩과 앱을 전체 조직에 게시

조직의 사용자는 콘텐츠 팩과 앱을 특정 그룹이 아닌 전체 조직에 게시할 수 있습니다. [자세히 알아보기](service-organizational-content-pack-manage-update-delete.md)

다음 이미지는 콘텐츠 팩을 만들 때 **내 전체 조직** 옵션을 보여 줍니다.

![조직에 콘텐츠 팩 게시](media/service-admin-portal/powerbi-admin-publish-entire-org.png)

### <a name="create-template-organizational-content-packs-and-apps"></a>템플릿 조직 콘텐츠 팩 및 앱 만들기

조직의 사용자는 Power BI Desktop에서 빌드된 데이터 집합을 사용하는 템플릿 콘텐츠 팩을 만들 수 있습니다. [자세히 알아보기](template-content-pack-authoring.md)

### <a name="push-apps-to-end-users"></a>최종 사용자에게 앱 푸시

사용자는 AppSource에서 설치하지 않고 최종 사용자와 직접 앱을 공유할 수 있습니다. [자세히 알아보기](service-create-distribute-apps.md)

## <a name="integration-settings"></a>통합 설정

### <a name="ask-questions-about-data-using-cortana"></a>Cortana를 사용하여 데이터에 대한 질문

조직의 사용자는 Cortana를 사용하여 데이터에 대한 질문을 할 수 있습니다. [자세히 알아보기](service-cortana-enable.md)

> [!NOTE]
> 이 설정은 전체 조직에 적용되며 특정 그룹에 제한될 수 없습니다.

### <a name="use-analyze-in-excel-with-on-premises-datasets"></a>온-프레미스 데이터 집합을 통해 Excel에서 분석 사용

조직의 사용자는 Excel을 사용하여 온-프레미스 Power BI 데이터 집합을 보고 상호 작용할 수 있습니다. [자세히 알아보기](service-analyze-in-excel.md)

> [!NOTE]
> **데이터 내보내기**를 사용하지 않도록 설정하면 사용자는 **Excel에서 분석** 기능을 사용할 수 없습니다.

### <a name="use-arcgis-maps-for-power-bi"></a>ArcGIS Maps for Power BI 사용

조직의 사용자는 Esri에서 제공하는 ArcGIS Maps for Power BI 시각화를 사용할 수 있습니다. [자세히 알아보기](power-bi-visualization-arcgis.md)

### <a name="use-global-search-for-power-bi-preview"></a>Power BI(미리 보기)용 전역 검색 사용

조직의 사용자는 Azure Search에 의존하는 외부 검색 기능을 사용할 수 있습니다. 예를 들어 사용자는 Cortana를 사용하여 Power BI 대시보드 및 보고서에서 주요 정보를 직접 검색할 수 있습니다. [자세히 알아보기](service-cortana-intro.md)

## <a name="custom-visuals-settings"></a>사용자 지정 시각적 개체 설정

### <a name="enable-custom-visuals-for-the-entire-organization"></a>전체 조직에 대해 사용자 지정 시각적 개체 사용

조직의 사용자는 사용자 지정 시각적 개체를 조작하고 공유할 수 있습니다. [자세히 알아보기](power-bi-custom-visuals.md)

> [!NOTE]
> 이 설정은 전체 조직에 적용되며 특정 그룹에 제한될 수 없습니다.

## <a name="r-visuals-settings"></a>R 시각적 개체 설정

### <a name="interact-with-and-share-r-visuals"></a>R 시각적 개체와 상호 작용 및 공유

조직의 사용자는 R 스크립트를 사용하여 만든 시각적 개체와 상호 작용하고 공유할 수 있습니다. [자세히 알아보기](visuals/service-r-visuals.md)

> [!NOTE]
> 이 설정은 전체 조직에 적용되며 특정 그룹에 제한될 수 없습니다.

## <a name="audit-and-usage-settings"></a>감사 및 사용 설정

### <a name="create-audit-logs-for-internal-activity-auditing-and-compliance"></a>내부 활동 감사 및 규정 준수를 위해 감사 로그 만들기

조직의 사용자는 감사를 사용하여 조직의 다른 사용자가 Power BI에서 수행한 작업을 모니터링할 수 있습니다. [자세히 알아보기](service-admin-auditing.md)

감사 로그 항목을 기록하려면 이 설정이 사용하도록 설정되어야 합니다. 감사를 설정하고 나서 감사 데이터를 확인할 때까지 최대 48시간이 지연될 수 있습니다. 데이터가 즉시 표시되지 않으면 나중에 감사 로그를 확인합니다. 감사 로그를 볼 수 있는 권한을 부여받고 나서 로그에 액세스할 때까지 유사하게 지연될 수 있습니다.

> [!NOTE]
> 이 설정은 전체 조직에 적용되며 특정 그룹에 제한될 수 없습니다.

### <a name="usage-metrics-for-content-creators"></a>콘텐츠 작성자용 사용 메트릭

조직의 사용자가 자신이 만든 보고서 및 대시보드에 대한 사용 메트릭을 확인할 수 있습니다. [자세히 알아보기](service-usage-metrics.md)

### <a name="per-user-data-in-usage-metrics-for-content-creators"></a>콘텐츠 작성자에 대한 사용 메트릭의 사용자별 데이터

콘텐츠 사용자에 대한 사용 메트릭에는 콘텐츠에 액세스하는 사용자의 표시 이름 및 이메일 주소가 노출됩니다. [자세히 알아보기](service-usage-metrics.md)

사용자별 데이터는 기본적으로 사용 메트릭에 사용되도록 설정되고, 콘텐츠 생성자 계정 정보는 메트릭 보고서에 포함됩니다. 일부 또는 모든 사용자에게 이 정보를 포함하지 않으려는 경우 지정된 보안 그룹 또는 전체 조직에 기능을 사용하지 않도록 설정합니다. 그러면 계정 정보는 *이름 없음*으로 보고서에 표시됩니다.

## <a name="dashboard-settings"></a>대시보드 설정

### <a name="data-classification-for-dashboards"></a>대시보드에 대한 데이터 분류

조직의 사용자는 대시보드 보안 수준을 나타내는 분류로 대시보드를 태그할 수 있습니다. [자세히 알아보기](service-data-classification.md)

> [!NOTE]
> 이 설정은 전체 조직에 적용되며 특정 그룹에 제한될 수 없습니다.

## <a name="developer-settings"></a>개발자 설정

### <a name="embed-content-in-apps"></a>앱에 콘텐츠 포함

조직 내 사용자는 Power BI 대시보드 및 보고서를 SaaS(Software as a Service) 애플리케이션에 포함할 수 있습니다. 이 설정을 사용하지 않도록 설정하면 사용자는 REST API를 사용하여 Power BI 콘텐츠를 해당 애플리케이션에 포함할 수 없게 됩니다. [자세히 알아보기](developer/embedding.md)

## <a name="workspaces-and-import-settings"></a>작업 영역 및 가져오기 설정

### <a name="author-content-in-workspaces"></a>작업 영역에서 콘텐츠 작성

조직의 사용자는 작업 영역에 액세스하여 데이터에 연결하고 콘텐츠를 작성할 수 있습니다. [자세히 알아보기](service-create-the-new-workspaces.md)

### <a name="import-data-into-power-bi"></a>Power BI로 데이터 가져오기

조직의 사용자는 Power BI Desktop에서 보고서를 게시하고, Power BI 보고서 파일을 업로드하고, 서비스에서 바로 데이터에 연결하는 등 데이터를 서비스로 가져올 수 있습니다. [자세히 알아보기](desktop-upload-desktop-files.md)

## <a name="dataflow-settings-preview"></a>데이터 흐름 설정(미리 보기)

### <a name="create-and-use-dataflows-preview"></a>데이터 흐름 만들기 및 사용(미리 보기)

조직의 사용자가 데이터 흐름을 만들고 사용할 수 있습니다. 데이터 흐름 개요는 [Power BI의 셀프 서비스 데이터 준비(미리 보기)](service-dataflows-overview.md)를 참조하세요. 프리미엄 용량에 대한 데이터 흐름을 사용하려면 [워크로드 구성](service-admin-premium-manage.md#configure-workloads)을 참조하세요.

> [!NOTE]
> 이 설정은 전체 조직에 적용되며 특정 그룹에 제한될 수 없습니다.

## <a name="capacity-settings"></a>용량 설정

### <a name="power-bi-premium"></a>Power BI Premium

**Power BI Premium** 탭에서는 조직용으로 구매한 Power BI Premium 용량(EM 또는 P SKU)을 관리할 수 있습니다. 조직 내 모든 사용자가 **Power BI Premium** 탭을 볼 수 있으나, ‘용량 관리자’ 또는 할당 권한이 있는 사용자로 할당된 경우에만 탭 내 콘텐츠를 볼 수 있습니다. 사용자에게 권한이 없으면 다음과 같은 메시지가 나타납니다.

![Premium 설정 액세스 권한 없음](media/service-admin-portal/premium-settings-no-access.png)

프리미엄 설정 관리에 관한 자세한 내용은 [Power BI Premium 관리](service-admin-premium-manage.md)를 참조하세요.

### <a name="power-bi-embedded"></a>Power BI Embedded

**Power BI Embedded** 탭에서는 고객용으로 구매한 Power BI Embedded(A SKU) 용량을 확인할 수 있습니다. Azure에서만 A SKU를 구매할 수 있으므로 **Azure Portal**에서 [Azure의 포함된 용량을 관리](developer/azure-pbie-create-capacity.md)할 수 있습니다.

Power BI Embedded(A SKU) 설정을 관리하는 방법은 [Azure의 Power BI Embedded란?](developer/azure-pbie-what-is-power-bi-embedded.md)을 참조하세요.

## <a name="embed-codes"></a>embed 태그

관리자는 테넌트에 대해 생성된 embed 태그를 볼 수 있습니다. 코드를 취소하거나 삭제할 수도 있습니다. [자세히 알아보기](service-publish-to-web.md)

![Power BI 관리 포털 내의 embed 태그](media/service-admin-portal/embed-codes.png)

## <a name="organization-visuals"></a>조직의 시각적 개체

**조직 시각적 개체** 탭에서는 조직 내부에서 사용자 지정 시각적 개체를 배포 및 관리할 수 있습니다. 조직 시각적 개체를 사용하면 조직에서 소유 시각적 개체를 쉽게 배포할 수 있으므로 이후 보고서 작성자가 Power BI Desktop에서 이를 검색하고 보고서로 가져올 수 있습니다. [자세히 알아보기](power-bi-custom-visuals-organization.md)

> [!WARNING]
> 사용자 지정 시각적 개체에는 보안 또는 개인 정보 관련 위험이 있는 코드가 포함될 수 있습니다. 조직의 리포지토리로 배포하기 전에 사용자 지정 시각적 개체의 작성자와 원본을 신뢰할 수 있는지 확인해야 합니다.

다음 이미지는 조직의 리포지토리에 현재 배포된 모든 사용자 지정 시각적 개체를 보여 줍니다.

![조직 관리의 시각적 개체](media/service-admin-portal/power-bi-custom-visuals-organizational-admin-01.png)

### <a name="add-a-new-custom-visual"></a>새 사용자 지정 시각적 개체 추가

목록에 새 사용자 지정 시각적 개체를 추가하려면 다음 단계를 수행합니다. 

1. 오른쪽 창에서 **사용자 지정 시각적 개체 추가**를 선택합니다.

    ![사용자 지정 시각적 개체 양식](media/service-admin-portal/power-bi-custom-visuals-organizational-admin-02.png)

1. **사용자 지정 시각적 개체 추가** 양식을 채웁니다.

    * **.pbiviz 파일 선택**(필수): 업로드할 사용자 지정 시각적 개체 파일을 선택합니다. 버전이 있는 API 사용자 지정 시각적 개체만 지원됩니다(여기 참조).

    사용자 지정 시각적 개체를 업로드하기 전에 보안 및 개인 정보에 대해 사용자 지정 시각적 개체를 검토하여 조직의 표준에 적합한지 확인해야 합니다.

    * **사용자 지정 시각적 개체 이름 지정**(필수): Power BI Desktop 사용자가 쉽게 이해할 수 있도록 시각적 개체에 간단한 제목을 지정합니다.

    * **아이콘**: Power BI Desktop UI에 표시되는 아이콘 파일입니다.

    * **설명**: 사용자에게 더 많은 컨텍스트와 교육을 제공하기 위한 시각적 개체에 대한 간단한 설명입니다.

1. **적용**을 선택하여 업로드 요청을 시작합니다. 성공하면 목록에 새 항목이 표시됩니다. 실패하면 해당 오류 메시지가 표시됩니다.

### <a name="delete-a-custom-visual-from-the-list"></a>목록에서 사용자 지정 시각적 개체 삭제

시각적 개체를 영구적으로 삭제하려면 리포지토리에서 시각적 개체의 휴지통 아이콘을 선택합니다.

> [!IMPORTANT]
> 삭제는 되돌릴 수 없습니다. 삭제되면 시각적 개체는 기존 보고서에서 렌더링을 즉시 중지합니다. 동일한 시각적 개체를 다시 업로드하더라도 삭제된 이전 시각적 개체를 대체하지 않습니다. 그러나 사용자는 새 시각적 개체를 다시 가져오고 해당 보고서에 있는 인스턴스를 대체할 수 있습니다.

### <a name="disable-a-custom-visual-in-the-list"></a>목록에서 사용자 지정 시각적 개체 사용 안 함

조직의 저장소에서 시각적 개체를 사용하지 않으려면 기어 아이콘을 선택합니다. **액세스** 섹션에서 사용자 지정 시각적 개체를 사용 안 함으로 설정합니다.

시각적 개체를 사용하지 않도록 설정하면 시각적 개체가 기존 보고서에 렌더링되지 않고 아래와 같은 오류 메시지가 표시됩니다.

이 사용자 지정 시각적 개체는 더 이상 사용할 수 없습니다. 자세한 내용은 관리자에게 문의하세요.

그러나 책갈피로 지정된 시각적 개체는 여전히 작동합니다.

업데이트 후 또는 관리자가 변경한 후 Power BI Desktop 사용자는 애플리케이션을 다시 시작하거나 Power BI 서비스에서 브라우저를 새로 고쳐 업데이트를 확인해야 합니다.

### <a name="update-a-visual"></a>시각적 개체 업데이트

조직 저장소에서 시각적 개체를 업데이트하려면 기어 아이콘을 선택합니다. 시각적 개체의 새 버전을 찾아보고 업로드합니다.

시각적 개체 ID가 변경되지 않았는지 확인합니다. 새 파일은 조직 전체의 모든 보고서에 대해 이전 파일을 대체합니다. 그러나 시각적 개체의 새 버전이 시각적 개체의 이전 버전에 대한 사용이나 데이터 구조를 중단하는 경우에는 이전 버전을 바꾸지 마세요. 대신에 시각적 개체의 새 버전에 대한 새 목록을 만들어야 합니다. 예를 들어 새 버전 번호(버전 X.X)를 새 나열된 시각적 개체의 제목에 추가합니다. 이렇게 하면 업데이트된 버전 번호를 가진 동일한 시각적 개체가 되므로 기존 보고서가 해당 기능을 중단하지 않습니다. 다시 한번 시각적 개체 ID가 변경되지 않았는지 확인합니다. 그러면 다음에 사용자가 Power BI Desktop에서 조직의 리포지토리에 들어갈 때 새 버전을 가져올 수 있으며, 보고서에 있는 현재 버전을 바꾸라는 메시지가 표시됩니다.

## <a name="next-steps"></a>다음 단계

[조직의 Power BI 관리](service-admin-administering-power-bi-in-your-organization.md)  [Power BI 관리 역할 이해](service-admin-role.md)  
[조직에서 Power BI 감사](service-admin-auditing.md)  
[Power BI 프리미엄 관리](service-admin-premium-manage.md)  

궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](http://community.powerbi.com/)
