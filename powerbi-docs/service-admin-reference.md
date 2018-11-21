---
title: 관리자용 PowerShell cmdlet, REST API 및 .NET SDK
description: 스크립트 및 프로그래밍 API를 통해 Power BI를 관리할 수 있는 방법에 대해 알아봅니다.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: overview
ms.date: 06/25/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 1ed4298e4ed4cddcdf965bd427c654cab6adf1e6
ms.sourcegitcommit: 46f1ba3f972f6e64bce05ad0fd527b27c49aedd6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52157014"
---
# <a name="powershell-cmdlets-rest-apis-and-net-sdk-for-power-bi-administration"></a>Power BI 관리를 위한 PowerShell cmdlet, REST API 및 .NET SDK
Power BI를 사용하면 관리자가 PowerShell cmdlet을 사용하여 일반적인 작업을 스크립팅할 수 있습니다. 또한 REST API를 노출하고 관리 솔루션을 개발하기 위해 .NET SDK를 제공합니다. 이 항목에서는 해당하는 SDK 메서드 및 REST API 엔드포인트의 cmdlet 목록을 보여줍니다. 자세한 내용은 다음을 참조하세요.

- PowerShell [다운로드](https://www.powershellgallery.com/packages/MicrosoftPowerBIMgmt/) 및 [설명서](https://docs.microsoft.com/powershell/power-bi/overview?view=powerbi-ps)
- REST API [설명서](https://docs.microsoft.com/rest/api/power-bi/admin)
- .NET SDK [다운로드](https://www.nuget.org/packages/Microsoft.PowerBI.Api/)

| **Cmdlet 이름** | **별칭** | **SDK 메서드** | **REST API 엔드포인트** | **설명** |
| --- | --- | --- | --- | --- |
| **Get-PowerBIDatasource** | 해당 없음 | 데이터 집합\_GetDataSourcesAsAdmin | /v1.0/myorg/admin/datasets/{datasetkey}/datasources | 지정된 데이터 집합에 데이터 원본을 가져옵니다. |
| **Get-PowerBIDataset** | 해당 없음 | 데이터 집합\_GetDatasetsAsAdmin | /v1.0/myorg/admin/datasets | Power BI 테넌트에서 데이터 집합의 전체 목록을 가져옵니다. |
| **Get-PowerBIWorkspace** | **Get-PowerBIGroup** | 그룹\_GetGroupsAsAdmin | /v1.0/myorg/admin/groups | Power BI 테넌트에서 작업 영역의 전체 목록을 가져옵니다. |
| **Add-PowerBIWorkspaceUser** | **Add-PowerBIGroupUser** |그룹\_AddUserAsAdmin | /v1.0/myorg/admin/groups/{groupId}/users | 지정된 작업 영역에 구성원으로 사용자를 추가합니다. |
| **Remove-PowerBIWorkspaceUser** | **Remove-PowerBIGroupUser** | 그룹\_DeleteUserAsAdmin | /v1.0/myorg/admin/groups/{groupId}/users/{user} | 지정된 작업 영역 구성원 목록에서 사용자를 제거합니다. |
| **Restore-PowerBIWorkspace** |**Restore-PowerBIGroup** | 그룹\_RestoreDeletedGroupAsAdmin | /v1.0/myorg/admin/groups/{groupId}/restore | 삭제된 작업 영역을 복원합니다. |
| **Set-PowerBIWorkspace** |**Set-PowerBIGroup** | 그룹\_UpdateGroupAsAdmin | /v1.0/myorg/admin/groups/{groupId} | 지정된 작업 영역의 속성을 업데이트합니다. |
| **Get-PowerBIDataset -WorkspaceId** | 해당 없음 | 그룹\_GetDatasetsAsAdmin | /v1.0/myorg/admin/groups/{group\_id}/datasets | 지정된 작업 영역 내에서 데이터 집합을 가져옵니다. |
| **Export-PowerBIReport** | 해당 없음 | 보고서\_ExportReportAsAdmin | 해당 없음 | 로컬 파일에 보고서를 내보냅니다. |
| **Get-PowerBIReport** | 해당 없음 | 보고서\_GetReportsAsAdmin | /v1.0/myorg/admin/reports | Power BI 테넌트에서 보고서의 전체 목록을 가져옵니다. |
| **Get-PowerBIDashboard** | 해당 없음 | 대시보드\_GetDashboardsAsAdmin | /v1.0/myorg/admin/dashboards | Power BI 테넌트에서 대시보드의 전체 목록을 가져옵니다. |
| **Get-PowerBIDashboard** | 해당 없음 | 그룹\_GetDashboardsAsAdmin | /v1.0/myorg/admin/groups/{group\_id}/dashboards | 지정된 작업 영역 내에서 대시보드를 가져옵니다. |
| **Get-PowerBITile** | **Get-PowerBIDashboardTile** | 대시보드\_GetTilesAsAdmin | /v1.0/myorg/admin/dashboards/{dashboard\_id}/tiles | 지정된 대시보드 타일을 가져옵니다. |
| **Get-PowerBIReport** | 해당 없음 | 그룹\_GetReportsAsAdmin | /v1.0/myorg/admin/groups/{group\_id}/reports | 지정된 보고서 내에서 데이터 집합을 가져옵니다. |
| **Get-PowerBIImport** | 해당 없음 | 가져오기\_GetImportsAsAdmin | /v1.0/myorg/admin/imports | Power BI 테넌트에서 가져오기의 전체 목록을 가져옵니다. |
| **Connect-PowerBIServiceAccount** | **Login-PowerBI** &  **Login-PowerBIServiceAccount** | 해당 없음 | 해당 없음 | Power BI에 로그인하고 세션을 시작합니다. |
| **Disconnect-PowerBIServiceAccount** | **Logout-PowerBI** & **Logout-PowerBIServiceAccount** | 해당 없음 | 해당 없음 | Power BI의 로그아웃 및 기존 세션을 닫습니다. |
| **Invoke-PowerBIRestMethod**| 해당 없음 | 해당 없음 | 해당 없음 | Power BI에 대한 임의의 REST API 호출을 보냅니다. |
| **Get-PowerBIAccessToken**| 해당 없음 | 해당 없음 | 해당 없음 | 세션에서 Power BI 액세스 토큰을 가져옵니다. |
| **Resolve-PowerBIError**| 해당 없음 | 해당 없음 | 해당 없음 | 실패한 cmdlet 호출에 대한 자세한 오류 정보를 가져옵니다. |