---
title: 조직 내에서 감사 사용
description: Power BI를 통한 감사 기능을 사용하여 수행된 작업을 모니터링하고 조사하는 방법에 대해 알아보세요. 보안 및 규정 준수 센터를 사용하거나 PowerShell을 사용할 수 있습니다.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 04/10/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 294fb3a0142908ce0ab068e075ce39f950a0b124
ms.sourcegitcommit: d20f74d5300197a0930eeb7db586c6a90403aabc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2018
ms.locfileid: "50973353"
---
# <a name="using-auditing-within-your-organization"></a>조직 내에서 감사 사용

Power BI 테넌트의 어떤 항목에 누가 무슨 활동을 수행하는지를 아는 것은 조직에서 규정 준수 및 레코드 관리와 같은 요구 사항을 수행하도록 돕는 데 매우 중요합니다. Power BI 감사를 사용하여 “보고서 보기” 및 “대시보드 보기”와 같이 사용자가 수행한 작업을 감사할 수 있습니다. 감사를 사용하여 사용 권한을 감사할 수 없습니다.

Office 365 보안 및 준수 센터에서 감사하거나 PowerShell을 사용합니다. 이 문서에서는 둘 다 다룹니다. 감사 데이터는 날짜 범위, 사용자, 대시보드, 보고서, 데이터 집합 및 작업 유형에 따라 필터링할 수 있습니다. 활동을 CSV(쉼표로 구분된 값) 파일로 다운로드하여 오프라인에서 분석하도록 할 수도 있습니다.

## <a name="requirements"></a>요구 사항

감사 로그에 액세스하려면 이러한 요구 사항을 충족해야 합니다.

- Office 365 Security & Compliance Center의 감사 섹션에 액세스하려면 (Office 365 Enterprise E3 및 E5 구독에 포함된) Exchange Online 라이선스가 있어야 합니다.

- 전역 관리자이거나 감사 로그에 대한 액세스를 제공하는 Exchange 관리자 역할을 맡고 있어야 합니다. Exchange 관리자 역할은 Exchange 관리 센터를 통해 제어됩니다. 자세한 내용은 [Exchange Online에서의 사용 권한](/exchange/permissions-exo/permissions-exo/)을 참조하세요.

- 감사 로그에 대한 액세스 권한이 있지만 전역 관리자 또는 Power BI 서비스 관리자가 아닌 경우 Power BI 관리 포털에 대한 액세스 권한이 없습니다. 이 경우 [Office 365 보안 및 준수 센터](https://sip.protection.office.com/#/unifiedauditlog)의 직접 링크를 사용해야 합니다.

- 테넌트 내에서 Power BI에 대한 감사 로그를 보려면 테넌트 내에 하나 이상의 Exchange 사서함 라이선스가 필요합니다.

## <a name="accessing-your-audit-logs"></a>감사 로그에 액세스

로그에 액세스하려면 먼저 Power BI에서 로깅을 사용할 수 있는지 확인합니다. 자세한 내용은 관리 포털 설명서에서 [감사 로그](service-admin-portal.md#audit-logs)를 참조하세요. 감사를 설정하고 나서 감사 데이터를 확인할 때까지 최대 48시간이 지연될 수 있습니다. 데이터가 즉시 표시되지 않으면 나중에 감사 로그를 확인합니다. 감사 로그를 볼 수 있는 권한을 부여받고 나서 로그에 액세스할 때까지 유사하게 지연될 수 있습니다.

Power BI 감사 로그는 [Office 365 보안 및 준수 센터](https://sip.protection.office.com/#/unifiedauditlog)를 통해 직접 사용할 수 있습니다. Power BI 관리 포털의 링크도 있습니다.

1. Power BI에서 오른쪽 위의 **기어 아이콘**을 선택한 후 **관리 포털**을 선택합니다.

   ![관리 포털](media/service-admin-auditing/powerbi-admin.png)

1. **감사 로그**를 선택합니다.

1. **O365 관리 센터로 이동**을 선택합니다.

   ![O365 관리 센터로 이동](media/service-admin-auditing/audit-log-o365-admin-center.png)

관리자가 아닌 계정에 감사 로그에 대한 액세스 권한을 제공하려면 Exchange Online 관리 센터 내에서 사용 권한을 할당해야 합니다. 예를 들어, 조직 관리와 같은 기존 역할 그룹에 사용자를 할당하거나 감사 로그 역할을 가진 새 역할 그룹을 만들 수 있습니다. 자세한 내용은 [Exchange Online에서의 사용 권한](/exchange/permissions-exo/permissions-exo/)을 참조하세요.

## <a name="search-only-power-bi-activities"></a>Power BI 활동만 검색

다음 단계를 수행하여 결과를 Power BI 활동으로만 제한합니다. 활동 목록은 이 문서의 뒷부분에 나오는 [Power BI에서 감사되는 활동 목록](#list-of-activities-audited-by-power-bi)을 참조하세요.

1. **Audit log search**(감사 로그 검색) 페이지의 **검색** 아래에서 **활동**에 해당하는 드롭다운을 선택합니다.

2. **Power BI activities**(Power BI 활동)를 선택합니다.

   ![감사 로그 검색](media/service-admin-auditing/audit-log-search-filter-by-powerbi.png)

3. 선택 상자 밖의 아무 곳이나 선택하여 상자를 닫습니다.

이제 검색이 Power BI 활동으로만 필터링됩니다.

## <a name="search-the-audit-logs-by-date"></a>날짜별 감사 로그 검색

**시작 날짜**와 **종료 날짜** 필드를 사용하면 날짜 범위로 로그를 검색할 수 있습니다. 기본적으로 최근 7일이 선택됩니다. 날짜와 시간은 UTC(협정 세계시) 형식으로 표시됩니다. 지정할 수 있는 최대 날짜 범위는 90일입니다. 

선택한 날짜 범위가 90일을 초과하면 오류가 표시됩니다. 최대 날짜 범위인 90일을 사용하는 경우 **시작 날짜**에 현재 시간을 선택합니다. 그렇지 않으면 시작 날짜가 종료 날짜보다 빠르다는 오류가 표시됩니다. 90일이 지나기 전에 감사를 사용하도록 설정하는 경우, 날짜 범위가 감사를 켠 날짜 이전에 시작되도록 설정할 수 없습니다.

![](media/service-admin-auditing/search-audit-log-by-date.png)

## <a name="search-the-audit-logs-by-users"></a>사용자별 감사 로그 검색

특정 사용자가 수행한 활동에 대한 감사 로그 항목을 검색할 수 있습니다. 이를 수행하려면 **사용자** 필드에 사용자 이름을 하나 이상 입력합니다. 사용자 이름은 메일 주소와 유사하며 사용자가 Power BI에 로그인하는 계정입니다. 조직의 모든 사용자(및 서비스 계정)에 대한 항목을 반환하려면 이 상자를 비워둡니다.

![날짜별 검색](media/service-admin-auditing/search-audit-log-by-user.png)

## <a name="view-search-results"></a>검색 결과 보기

**검색**을 선택한 후 검색 결과가 로드되고 잠시 후에 **결과** 아래에 검색 결과가 표시됩니다. 검색이 완료되면 검색된 결과의 개수가 표시됩니다. 최대 1000개의 이벤트가 표시됩니다. 검색 조건을 충족하는 이벤트가 1000개를 넘으면, 최신 이벤트 1000개가 표시됩니다.

### <a name="view-the-main-results"></a>기본 결과 보기

**결과** 영역에는 검색을 통해 반환된 각 이벤트에 대한 다음과 같은 정보가 포함됩니다. 결과를 정렬하려면 **결과**에서 열 머리글을 선택합니다.

| **열** | **정의** |
| --- | --- |
| 날짜 |이벤트가 발생한 날짜와 시간(UTC 형식)입니다. |
| IP 주소 |활동이 기록될 때 사용된 장치의 IP 주소입니다. IP 주소는 IPv4 또는 IPv6 주소 형식으로 표시됩니다. |
| 사용자 |이벤트를 트리거한 작업을 수행한 사용자(또는 서비스 계정)입니다. |
| 활동 |사용자가 수행한 활동입니다. 이 값은 **활동** 드롭다운 목록에서 선택한 활동과 일치합니다. Exchange 관리자 감사 로그의 이벤트는 이 열의 값이 Exchange cmdlet입니다. |
| 항목 |해당하는 활동의 결과로 생성되거나 수정된 개체입니다. 예를 들면 보거나 수정한 파일 또는 업데이트된 사용자 계정입니다. 일부 활동은 이 열에 값이 없습니다. |
| 세부 정보 |활동에 대한 추가 세부 정보입니다. 마찬가지로, 일부 활동은 이 값이 없습니다. |

### <a name="view-the-details-for-an-event"></a>이벤트에 대한 세부 정보 보기

검색 결과 목록에서 이벤트 레코드를 클릭하면 이벤트에 대한 세부 정보를 볼 수 있습니다. 이벤트 레코드의 세부 속성을 포함하는 **세부 정보** 페이지가 표시됩니다. 표시되는 속성은 이벤트가 발생하는 Office 365 서비스에 따라 다릅니다. 

이러한 세부 정보를 표시하려면 **추가 정보**를 선택합니다. 모든 Power BI 항목에는 RecordType 속성에 대해 20이라는 값이 있습니다. 기타 속성에 대한 자세한 내용은 [감사 로그의 자세한 속성](/office365/securitycompliance/detailed-properties-in-the-office-365-audit-log/)을 참조하세요.

   ![감사 세부 정보](media/service-admin-auditing/audit-details.png)

## <a name="export-search-results"></a>검색 결과 내보내기

Power BI 감사 로그를 csv 파일로 내보내려면 다음 단계를 수행합니다.

1. **결과 내보내기**를 선택합니다.

1. **Save loaded results**(로드된 결과 저장) 또는 **Download all results**(모든 결과 다운로드)를 선택합니다.

    ![결과 내보내기](media/service-admin-auditing/export-auditing-results.png)

## <a name="use-powershell-to-search-audit-logs"></a>PowerShell을 사용하여 감사 로그 검색

사용자 로그인에 따른 감사 로그에 액세스하기 위해 PowerShell을 사용할 수도 있습니다. 다음 예제에서는 [Search-UnifiedAuditLog](/powershell/module/exchange/policy-and-compliance-audit/search-unifiedauditlog?view=exchange-ps/) 명령을 사용하여 Power BI 감사 로그 항목을 끌어오는 방법을 보여 줍니다.

[New-PSSession](/powershell/module/microsoft.powershell.core/new-pssession/) 명령을 사용하려면 계정에 할당된 Exchange Online 라이선스가 있어야 하고 테넌트의 감사 로그에 대한 액세스 권한이 필요합니다. Exchange Online에 연결하는 방법에 대한 자세한 내용은 [Exchange Online PowerShell에 연결](/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell/)을 참조하세요.

```powershell
Set-ExecutionPolicy RemoteSigned

$UserCredential = Get-Credential

$Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection

Import-PSSession $Session
Search-UnifiedAuditLog -StartDate 9/11/2018 -EndDate 9/15/2018 -RecordType PowerBI -ResultSize 1000 | Format-Table | More
```

감사 로그와 함께 PowerShell을 사용하는 또 다른 예는 [Using Power BI audit log and PowerShell to assign Power BI Pro licenses](https://powerbi.microsoft.com/blog/using-power-bi-audit-log-and-powershell-to-assign-power-bi-pro-licenses/)(Power BI 감사 로그 및 PowerShell을 사용하여 Power BI Pro 라이선스 할당)를 참조하세요.

## <a name="activities-audited-by-power-bi"></a>Power BI에서 감사하는 활동

Power BI에서 감사하는 활동은 다음과 같습니다.

* AddDatasourceToGateway
* AddGroupMembers
* AnalyzedByExternalApplication
* AnalyzeInExcel
* AttachDataflowStorageAccount
* BindToGateway
* ChangeCapacityState
* ChangeGatewayAdministrators
* ChangeGatewayDatasourceUsers
* CreateApp
* CreateDashboard
* CreateDataflow
* CreateDataset
* CreateEmailSubscription
* CreateFolder
* CreateGateway
* CreateGroup
* CreateOrgApp
* CreateReport
* DeleteComment
* DeleteDashboard
* DeleteDataflow
* DeleteDataset
* DeleteEmailSubscription
* DeleteFolder
* DeleteGateway
* DeleteGroup
* DeleteGroupMembers
* DeleteOrgApp
* DeleteReport
* DownloadReport
* EditDataset
* EditReport
* ExportDataflow
* ExportReport
* ExportTile
* GenerateDataflowSasToken
* GenerateEmbedToken
* GetDatasources
* 가져오기
* InstallApp
* MigrateWorkspaceIntoCapacity
* OptInForProTrial
* PostComment
* PrintDashboard
* PrintReport
* PublishToWebReport
* RefreshDataset
* RemoveDatasourceFromGateway
* RemoveWorkspacesFromCapacity
* RenameDashboard
* SetAllConnections
* SetScheduledRefresh
* SetScheduledRefreshOnDataflow
* ShareDashboard
* ShareReport
* TakeOverDataset
* TakeOverDatasource
* UnpublishApp
* UpdateApp
* UpdateCapacityAdmins
* UpdateCapacityDisplayName
* UpdateCapacityResourceGovernanceSettings
* UpdateCapacityUsersAssignment
* UpdatedAdminFeatureSwitch
* UpdateDataflow
* UpdateDatasetParameters
* UpdateDatasourceCredentials
* UpdateDatasources
* UpdateEmailSubscription
* UpdateFolder
* UpdateFolderAccess
* ViewDashboard
* ViewDataflow
* ViewReport
* ViewTile
* ViewUsageMetrics

## <a name="next-steps"></a>다음 단계

[Power BI 관리란?](service-admin-administering-power-bi-in-your-organization.md)  

[Power BI 관리 포털](service-admin-portal.md)  

궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](http://community.powerbi.com/)
