---
title: 새 작업 영역-Power BI에서에서 작업 구성
description: 대시보드 및 조직에 대 한 주요 메트릭을 제공 하도록 제작 된 보고서의 컬렉션인 새 작업 영역에 알아봅니다.
author: maggiesMSFT
manager: kfile
ms.reviewer: lukaszp
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/18/2019
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: 9f5dfaa5a23ae46fef131a52355531b5fbde3051
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "65100683"
---
# <a name="organize-work-in-the-new-workspaces-in-power-bi"></a>Power BI에서 새 작업 영역에서 작업 구성

 *작업 영역* 대시보드, 보고서 및 페이지가 매겨진된 보고서의 컬렉션을 만들고 동료와 공동 작업 하는 위치입니다. 새 작업 영역 환경을 더 잘 콘텐츠에 대 한 액세스를 관리할 수 있습니다. 이 문서에서는 새 작업 영역 및 클래식 작업 영역에서 차이점을 설명 합니다.  클래식 작업 영역을 사용 하 여 여전히를 사용할 때를 만들고 앱을 배포 합니다. 방법에 대해 알아보세요 [새 작업 영역 환경을 만들](service-create-the-new-workspaces.md)합니다.

새 작업 영역 환경 일반 공급 (GA)에 도달 하 고는 이제 기본 작업 영역입니다. 만들기 및 사용을 계속할 수 있습니다 [클래식 작업 영역](service-create-workspaces.md) Office 365 그룹을 기반으로 합니다. 

> [!NOTE]
> 작업 영역에서 콘텐츠를 검색 하는 Power BI Pro 사용자에 대 한 행 수준 보안 (RLS)을 적용 하기 위해 계속 사용할 [클래식 작업 영역](service-create-workspaces.md)합니다. 선택 된 **멤버는 Power BI 콘텐츠를 볼 수만** 옵션입니다. 또는 해당 사용자에 게 Power BI 앱을 게시 하거나 공유 콘텐츠 배포를 사용 합니다. 곧 출시 예정인 뷰어 역할이 새 작업 영역 환경 작업 영역에서 나중에이 시나리오를 사용 하도록 설정 됩니다.

새 작업 영역을 사용 하 여 다음을 수행할 수 있습니다.

- 보안 그룹, 배포 목록, Office 365 그룹 및 개인과 같은 사용자 그룹에 작업 영역 역할을 할당합니다.
- Office 365 그룹을 만들지 않고 Power BI에서 작업 영역을 만듭니다.
- 작업 영역에서 더 유연한 사용 권한 관리에 대해 세분화된 작업 영역 역할을 사용합니다.

새 작업 영역 중 하나를 만들면 연결된 기본 Office 365 그룹을 만들지 않습니다. 모든 작업 영역 관리는 Office 365가 아닌 Power BI에 위치합니다. 새 작업 영역 환경에서 이제 Office 365 그룹을 통해 콘텐츠에 대 한 사용자 액세스 관리를 계속 하려면 작업 영역 액세스 목록에 Office 365 그룹을 추가할 수 있습니다.

## <a name="administering-new-workspace-experience-workspaces"></a>새 작업 영역 환경 작업 영역 관리
새 작업 영역 환경 작업 영역에 대 한 관리는 Power BI에서 Power BI 관리자는 다음과 같이 결정 됩니다. 이제 조직에서 누가 작업 영역을 만들 수 있습니다. 관리 하 고 복구 작업 영역 수 있습니다. 이렇게 하려면 Power BI 관리 포털 또는 PowerShell Cmdlet을 사용 해야 합니다. Office 365 그룹을 기반으로 기본 작업 영역에서 계속 관리 Office 365 관리 포털 및 Azure Active Directory에서 발생 합니다.

**작업 영역 설정을** 관리 포털에서 관리자 사용할 수 있습니다 조직의 모든 사용자 또는 아무도 수 있도록 설정 만들기 작업 영역 (새 작업 영역 환경) 새 작업 영역 환경 작업 영역을 만들어야 합니다. 특정 보안 그룹의 구성원으로만 만들기를 제한할 수도 있습니다.

> [!NOTE]
> 만들기 작업 영역 (새 작업 영역 환경) Power BI에서 새 작업 영역을 만들려면 Office 365 그룹을 만들 수 있는 사용자만 사용할 수 있도록 기본값을 설정 합니다. 적절 한 사용자가 새 작업 영역 환경 작업 영역을 만들 수 있도록 Power BI 관리 포털에서 값을 설정 해야 합니다.

![관리 포털에서 작업 영역 설정](media/service-new-workspaces/power-bi-workspace-admin-settings.png)

합니다 [작업 영역 목록은](service-admin-portal.md#workspaces) Power BI 관리 포털에서 합니다. 

![작업 영역 목록](media/service-admin-portal/workspaces-list.png)

## <a name="new-workspaces-side-by-side-with-classic-workspaces"></a>클래식 작업 영역을 사용 하 여 새 작업 영역 나란히

새, 업그레이드 된 작업 영역 및 기존 클래식 작업 영역 나란히 공존할 및 만들 수 있습니다. 새 작업 영역 환경에는 기본 작업 영역 형식입니다. Power BI 사용자가 기존 워크플로 변경 하지 않으려면 Power BI에서의 멤버인 모든 Office 365 그룹을 나열 하는 계속 됩니다. 새 작업 영역을 만드는 방법에 알아보려면 [새 작업 영역을 만들고](service-create-the-new-workspaces.md)합니다. 클래식 작업 영역을 만드는 방법에 알아보려면 [클래식 작업 영역을 만들고](service-create-workspaces.md)합니다.

## <a name="roles-in-the-new-workspaces"></a>새 작업 영역의 역할

새 작업 영역에 대 한 액세스에 권한을 부여 하려면 추가 사용자 그룹 또는 개인 작업 영역 역할 중 하나: 멤버, 참가자 또는 관리자입니다. 사용자 그룹의 모든 사용자는 정의된 역할을 가져옵니다. 개별 여러 사용자 그룹의 경우 가장 높은 수준의 할당 된 역할에서 제공 하는 권한 얻을 수 있습니다.

역할을 통해 팀이 공동 작업할 수 있도록 작업 영역에서 수행할 수 있는 작업 및 사용자를 관리할 수 있습니다. 새 작업 영역을 사용하면 개인 및 사용자 그룹(보안 그룹, Office 365 그룹 및 배포 목록)에 역할을 할당할 수 있습니다. 

사용자 그룹에 역할을 할당하면 그룹의 개인은 콘텐츠에 대한 액세스 권한을 갖습니다. 사용자 그룹을 중첩하는 경우 포함된 모든 사용자에게는 사용 권한이 있습니다. 다양한 역할을 가진 여러 사용자 그룹에 있는 사용자에게는 가장 높은 수준의 사용 권한이 부여됩니다. 

새 작업 영역은 세 가지 역할(제공 관리자, 구성원 및 참가자)을 제공합니다.

|기능   | 관리자  | 구성원  | Contributor  | 
|---|---|---|---|
| 작업 영역 업데이트 및 삭제  | X  |   |   |
| 다른 관리자를 비롯한 사람 추가/제거  | X  |   |   |
| 낮은 권한을 가진 구성원 또는 다른 사용자 추가  |  X | X  |   |
| 앱 게시 및 업데이트 |  X | X  |   |
| 항목 공유 또는 앱 공유 |  X | X  |   |
| 다른 사용자가 항목을 다시 공유하도록 허용 |  X | X  |   |
| 작업 영역에서 콘텐츠 만들기, 편집 및 삭제  |  X | X  | X  |
| 작업 영역에 보고서 게시, 콘텐츠 삭제 |  X | X  | X  |
 
 
## <a name="licensing"></a>라이선싱
작업 영역에 추가하는 모든 사용자는 Power BI Pro 라이선스가 필요합니다. 작업 영역에서 이러한 사용자는 물론, 더 광범위한 대상 그룹이나 조직 전체에 게시할 계획이 있는 대시보드, 보고서에 대해 공동 작업을 수행할 수 있습니다. 조직 내 다른 사용자에게 콘텐츠를 배포하려는 경우 해당 사용자에게 Power BI Pro 라이선스를 할당하거나 Power BI Premium 용량에 작업 영역을 배치할 수 있습니다.

> [!NOTE]
> 새 작업 영역 환경에 보고서 게시 라이선스 규칙 보다 엄격 하 게 적용 기존에 있습니다. "Power BI Pro 라이선스가 있는 사용자만이 작업 영역에 게시할 수 있습니다." 도구는 Pro 라이선스 없이 Power BI Desktop 또는 다른 클라이언트에서 게시 하려고 하는 사용자가 오류를 참조 하세요.

## <a name="how-are-the-new-workspaces-different-from-current-workspaces"></a>현재 작업 영역과 새 작업 영역의 차이점은?

새 작업 영역을 사용하여 몇 가지 기능을 다시 디자인하고 있습니다. 영구적으로 적용 될 변경 내용을 다음과 같습니다. 

* 이러한 작업 영역 만들기 클래식 작업 영역 등 Office 365 그룹을 만들 없습니다. 그러나 사용자가 액세스 하도록 작업 영역에는 역할을 할당 하 여 Office 365 그룹을 이제 사용할 수 있습니다. 
* 클래식 작업 영역에서 개인만 멤버 및 관리자 목록에 추가할 수 있습니다. 새 작업 영역에서 사용자 관리를 간소화하기 위해 이러한 목록에 여러 AD 보안 그룹, 배포 항목 또는 Office 365 그룹을 추가할 수 있습니다. 
- 클래식 작업 영역에서 조직 콘텐츠 팩을 만들 수 있습니다. 새 작업 영역에서 콘텐츠 팩을 만들 수 없습니다.
- 클래식 작업 영역에서 조직 콘텐츠 팩을 사용할 수 있습니다. 새 작업 영역에서 콘텐츠 팩을 사용할 수 없습니다.

## <a name="workspace-contact-list"></a>작업 영역 연락처 목록
새 **연락처 목록** 기능을 사용 하면 어떤 사용자 작업 영역에서 발생 한 문제에 대 한 알림을 받도록 지정할 수 있습니다. 기본적으로 모든 사용자 또는 그룹 작업 영역으로 관리자에 게 알림이 제공 지정 했지만 지정은 사용자 지정할 수 있습니다. 사용자 또는 연락처 목록에 나열 된 그룹 표시 됩니다 하는 데 사용자 인터페이스 (UI)에 사용자 작업 영역에 관련 된 도움말을 가져옵니다. 

에 대해 자세히 알아보세요 합니다 [작업 영역 연락처 목록 설정](service-create-the-new-workspaces.md#workspace-contact-list)합니다.

## <a name="workspace-onedrive"></a>작업 영역 OneDrive
작업 영역 OneDrive 기능을 사용 하면 해당 SharePoint 문서 라이브러리 file storage는 작업 영역 사용자에 게 제공 하는 Office 365 그룹을 구성할 수 있습니다. Power BI 외부에서 작성 해야 하는 그룹입니다. 

Power BI는 Office 365 그룹 멤버 자격을 사용 하 여 작업 영역 액세스를 갖도록 구성 되며 사용자 또는 그룹의 권한을 동기화 하지 않습니다. 이 설정에서 구성한 파일 저장소 동일한 Office 365 그룹을 통해 작업 영역 액세스를 관리 하는 것이 좋습니다. 

방법에 대해 알아보세요 [설정 하 고 작업 영역 OneDrive 액세스](service-create-the-new-workspaces.md#workspace-onedrive)합니다.  
   
## <a name="auditing"></a>감사
다음 작업은 새 작업 영역 환경 작업 영역에 대 한 Power BI에서 감사 됩니다.

| 식별 이름 |   작업 이름 |
|---|---|
| Power BI 폴더 만듦 | CreateFolder |
| Power BI 폴더 삭제됨 | DeleteFolder |
| Power BI 폴더 업데이트됨 | UpdateFolder |
| Power BI 폴더 액세스 권한 업데이트됨| UpdateFolderAccess |

에 대해 자세히 알아보세요 [Power BI 감사](service-admin-auditing.md#activities-audited-by-power-bi)합니다.

## <a name="limitations-and-considerations"></a>제한 사항 및 고려 사항

알아야 할 제한 사항:

- 작업 영역은 최대 1,000개 데이터 세트 또는 데이터 세트당 1,000개 보고서를 포함할 수 있습니다. 
- Power BI Pro 라이선스가 있는 사용자는 최대 1,000 영역의 멤버일 수 있습니다.
- Excel 용 power BI 게시자 지원 되지 않습니다.

## <a name="workspace-features-that-work-differently"></a>다르게 작동하는 작업 영역 기능

일부 기능은 새 작업 영역의 현재 작업 영역과 다르게 작동합니다. 이러한 차이점은 의도적인 고객에 게 서 받은 하 고 작업 영역과 공동 작업을 더 유연한 접근 방식을 사용 하는 피드백에 따라:

- 라이선스 적용 합니다. 새 작업 영역 환경에 보고서 게시는 Power BI 서비스에서 다른 사용자에 게 콘텐츠 공유 또는 작업 영역에서 공동 작업 사용자를 위한 Power BI Pro 라이선스를 필요로 하는 기존 라이선스 규칙을 적용 합니다. "Powre BI Pro 라이선스가 있는 사용자만이 작업 영역에 게시할 수 있습니다." Pro 라이선스가 없는 사용자가 오류를 참조 하세요.
- 멤버는 다시 공유할 수 있거나 없습니다. 기여자 역할에서 대체됩니다.
- 읽기 전용 작업 영역: 사용자에게 작업 영역에 대한 읽기 전용 액세스 권한을 부여하는 대신 곧 출시 예정인 뷰어 역할에 사용자를 할당합니다. 그러면 작업 영역의 콘텐츠에 유사한 읽기 전용 액세스 권한을 허용합니다.
- **작업 영역 나가기** 단추가 없습니다.

## <a name="frequently-asked-questions"></a>질문과 대답

**새 작업 영역에 영향을 받는 기존 콘텐츠에 대 한 링크도 환경을 GA는**

아니요. 클래식 작업 영역에서 기존 항목에 대 한 링크는 새 작업 영역 환경 영향을 받지 않습니다. 새 작업 영역 환경의 일반 공급 (GA) 변경 기본 작업 영역을 만들지만 기존 작업 영역을 변경 하지 않습니다. 

**기존 작업 영역 GA 사용 하 여 새 작업 영역 환경으로 업그레이드**

아니요. 새 작업 영역 환경을 GA는 새 작업 영역 환경으로 기본 작업 영역 유형에 변경 됩니다. Office 365 그룹을 기반으로 하는 기존 클래식 작업 영역 변경 되지 않습니다.

**작업 영역을 Office 365 그룹에 대해 계속 자동으로 만들는**

예. 두 가지 유형의 나란히 작업 영역을 지원 하므로 계속 모든 Office 365 그룹에 대 한 액세스 작업 영역 목록에 나열 됩니다.

## <a name="next-steps"></a>다음 단계
* [Power BI에서 새 작업 영역 만들기](service-create-the-new-workspaces.md)
* [클래식 작업 영역 만들기](service-create-workspaces.md)
* [Power BI에서 앱 설치 및 사용](service-create-distribute-apps.md)
* 궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](http://community.powerbi.com/)
