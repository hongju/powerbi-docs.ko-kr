---
title: Power BI-새 작업 영역 만들기
description: 새 작업 영역에서 대시보드, 보고서 및 조직에 대 한 주요 메트릭을 제공 하도록 제작 된 페이지 매긴된 보고서의 컬렉션을 만드는 방법에 알아봅니다.
author: maggiesMSFT
manager: kfile
ms.reviewer: lukaszp
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/18/2019
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: d0c0781ea5d3864f1cf3627cd42d53cca632102d
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "61142074"
---
# <a name="create-the-new-workspaces-in-power-bi"></a>Power BI에서 새 작업 영역 만들기

Power BI는 새로운 작업 영역 환경을 소개 합니다. 작업 영역은 여전히 대시보드, 보고서 및 페이지가 매겨진된 보고서의 컬렉션을 만들고 동료와 공동 작업 하는 위치입니다. 해당 컬렉션에 번들로 다음을 *앱* 을 전체 조직 또는 특정 사용자 또는 그룹에 배포 합니다. 

다른 점은 다음과 같습니다. 새 작업 영역에서 다음을 수행할 수 있습니다.

- 보안 그룹, 배포 목록, Office 365 그룹 및 개인과 같은 사용자 그룹에 작업 영역 역할을 할당합니다.
- Office 365 그룹을 만들지 않고 Power BI에서 작업 영역을 만듭니다.
- 작업 영역에서 더 유연한 사용 권한 관리에 대해 세분화된 작업 영역 역할을 사용합니다.

> [!NOTE]
> 작업 영역에서 콘텐츠를 검색 하는 Power BI Pro 사용자에 대 한 행 수준 보안 (RLS)을 적용 하기 위해 계속 사용할 [클래식 작업 영역](service-create-workspaces.md)합니다. 선택 된 **멤버는 Power BI 콘텐츠를 볼 수만** 옵션입니다. 또는 해당 사용자에 게 Power BI 앱을 게시 하거나 공유 콘텐츠 배포를 사용 합니다. 곧 출시 예정인 뷰어 역할이 새 작업 영역 환경 작업 영역에서 나중에이 시나리오를 사용 하도록 설정 됩니다.

자세한 배경 정보를 참조 하세요. 합니다 [새 작업 영역](service-new-workspaces.md) 문서.

## <a name="create-one-of-the-new-app-workspaces"></a>새로운 앱 작업 영역 중 하나 만들기

1. 웹 작업 영역을 만들어 시작합니다. **작업 영역** > **앱 작업 영역 만들기**를 선택합니다.
   
     ![앱 작업 영역 만들기](media/service-create-the-new-workspaces/power-bi-create-app-workspace.png)

2. 자동으로 만들 업그레이드 된 작업 영역을 선택 하지 않는 한 **classic로 되돌릴**합니다.
   
     ![새 작업 영역 환경](media/service-create-the-new-workspaces/power-bi-new-workspace.png)
     
     선택 하는 경우 **classic로 되돌릴**, Office 365 그룹에 따라 작업 영역을 만듭니다. 필요한 경우이 옵션을 사용 합니다 **멤버는 Power BI 콘텐츠를 볼 수만** 작업 영역 구성원에 대 한 행 수준 보안 (RLS)를 적용 하는 옵션.

2. 작업 영역에 이름을 지정합니다. 이름을 사용할 수 없으면 고유 이름으로 표시 되도록 편집 합니다.
   
     작업 영역에 대 한 앱 작업 영역으로 동일한 이름 및 아이콘 해야 합니다.
   
1. 다음은 몇 가지 선택 항목에 작업 영역에 대해 설정할 수 있습니다.

    업로드를 **작업 영역 이미지**합니다. 파일은.png 또는.jpg 형식 수 있습니다. 파일 크기는 45KB 보다 작은 수입니다.
    
    [추가 된 **연락처 목록**](#workspace-contact-list)합니다. 기본적으로 작업 영역 관리자 연락처는 합니다. 
    
    [지정 된 **작업 영역 OneDrive** ](#workspace-onedrive) URL이 아닌는 기존 Office 365 그룹의 이름을 입력 하 여 합니다. 이제이 작업 영역 해당 Office 365 그룹의 파일 저장소 위치를 사용할 수 있습니다. 

    ![OneDrive 위치를 지정 합니다.](media/service-create-the-new-workspaces/power-bi-new-workspace-onedrive.png)

    작업 영역을 할당 하는 **전용 용량**의 **Premium** 탭을 선택 **전용 용량**합니다.
     
    ![전용 용량](media/service-create-the-new-workspaces/power-bi-workspace-premium.png)

1. **저장**을 선택합니다.

    Power BI는 작업 영역을 만들고 엽니다. 구성원으로 속해 있는 작업 영역 목록에서 볼 수 있습니다. 

## <a name="workspace-contact-list"></a>작업 영역 연락처 목록

새 작업 영역 연락처 목록을 사용 하는 사용자 작업 영역에서 발생 한 문제에 대 한 알림을 받도록 지정할 수 있습니다. 기본적으로 모든 사용자 또는 그룹 작업 영역으로 관리자에 게 알림이 제공 지정 했지만 지정은 사용자 지정할 수 있습니다. 사용자 또는 연락처 목록에 나열 된 그룹 표시 됩니다 하는 데 사용자 인터페이스 (UI)에 사용자 작업 영역에 관련 된 도움말을 가져옵니다.

1. 새 액세스 **연락처 목록** 두 가지 방법 중 하나로 설정 합니다.

    에 **작업 영역 만들기** 창을 처음 만들 때.

    왼쪽된 탐색 창에서 화살표를 선택 옆 **작업 영역**, 작업 영역 이름 옆의 줄임표 (...) > **작업 영역 설정을**합니다. 합니다 **설정을** 창이 열립니다.

    ![작업 영역 설정](media/service-create-the-new-workspaces/power-bi-workspace-settings.png)

2. 아래 **고급** > **연락처 목록**, 기본값을 적용 **작업 영역 관리자**, 또는 사용자가 목록에 추가 **특정 사용자 또는 그룹과**. 
3. **저장**을 선택합니다.

## <a name="workspace-onedrive"></a>작업 영역 OneDrive

작업 영역 OneDrive 기능을 사용 하면 해당 SharePoint 문서 라이브러리 file storage는 작업 영역 사용자에 게 제공 하는 Office 365 그룹을 구성할 수 있습니다. Power BI 외부에서 그룹을 먼저 만듭니다. 

Power BI는 Office 365 그룹 멤버 자격을 사용 하 여 작업 영역 액세스를 갖도록 구성 되며 사용자 또는 그룹의 권한을 동기화 하지 않습니다. 모범 사례는 동일한 Office 365 그룹에이 설정은 Office 365 그룹의 구성 파일 저장소를 제공 [작업 영역에 대 한 액세스](#give-access-to-your-workspace)합니다. 그런 다음 Office 365 그룹의 멤버 자격을 관리 하 여 작업 영역 액세스를 관리 합니다. 

1. 새 액세스 **작업 영역 OneDrive** 두 가지 방법 중 하나로 설정 합니다.

    에 **작업 영역 만들기** 창을 처음 만들 때.

    왼쪽된 탐색 창에서 화살표를 선택 옆 **작업 영역**, 작업 영역 이름 옆의 줄임표 (...) > **작업 영역 설정을**합니다. 합니다 **설정을** 창이 열립니다.

    ![작업 영역 설정](media/service-create-the-new-workspaces/power-bi-workspace-settings.png)

2. 아래 **고급** > **작업 영역 OneDrive**, 이전에 만든 Office 365 그룹의 이름을 입력 합니다. Power BI의 그룹에 대 한 OneDrive 자동으로 선택합니다.

    ![OneDrive 위치를 지정 합니다.](media/service-create-the-new-workspaces/power-bi-new-workspace-onedrive.png)

3. **저장**을 선택합니다.

### <a name="access-the-workspace-onedrive-location"></a>작업 영역 OneDrive 위치에 액세스

OneDrive 위치를 구성한 후에 작업 영역에서 몇 가지 서로 다른 위치에서를 가져올 수 있습니다.

- 선택 **작업 영역** > *작업 영역 이름* > 줄임표 ( **...** ) 메뉴 > **파일**합니다. 

    ![작업 영역 파일 위치](media/service-new-workspaces/power-bi-new-workspace-files.png)

- 줄임표를 선택 ( **...** ) 작업 영역의 오른쪽 위 모서리에 있는 메뉴 > **파일**합니다.

    ![작업 영역 파일 위치](media/service-new-workspaces/power-bi-new-workspace-files-2.png)
    
- 에 **데이터 가져오기** > **파일** 발생 합니다. 합니다 **OneDrive-비즈니스** 항목은 비즈니스용 OneDrive. 두 번째 OneDrive 추가한 것입니다.

    ![작업 영역 파일 위치-데이터 가져오기](media/service-new-workspaces/power-bi-new-workspace-get-data-onedrive.png)

## <a name="add-content-to-your-app-workspace"></a>앱 작업 영역에 콘텐츠 추가

새 작업 영역 환경 작업 영역을 만든 후에 콘텐츠를 추가할 차례입니다. 클래식 및 새 작업 영역에서 콘텐츠를 추가 비슷합니다. 만들기 단추를 사용 하거나 사용 하 여 작업 영역에 콘텐츠를 추가 합니다.

1. 에 **시작** 화면에 새 작업 영역에 대 한 콘텐츠를 추가할 수 있습니다. 

    ![새 작업 영역 시작 화면](media/service-create-the-new-workspaces/power-bi-workspace-welcome-screen.png)

1. 예를 들어 **샘플** > **고객 수익성 샘플**을 선택합니다.

> [!NOTE]
> 새 작업 영역에서 조직 콘텐츠 팩 또는 타사 콘텐츠 팩을 사용할 수 없습니다. 모든 타사 콘텐츠 팩에 대 한 앱은 사용할 수 있는 이전에 사용 합니다. 콘텐츠 팩을 사용 하 여 계속 해야 할 경우 클래식 작업 영역을 사용 합니다. 콘텐츠 팩 사용 되지 않으므로 앱을 대신 사용 하는 것이 좋습니다.

앱 작업 영역에서 콘텐츠 목록의 콘텐츠를 볼 때 앱 작업 영역의 이름이 소유자로 나열됩니다.

### <a name="connecting-to-third-party-services-in-new-workspaces"></a>새 작업 영역에서 타사 서비스에 연결

새 작업 영역 환경에서 *앱*에 집중하도록 변경이 진행 중입니다. 타사 서비스의 앱을 통해 사용자가 Microsoft Dynamics CRM, Salesforce 또는 Google Analytics와 같은 사용할 서비스에서 데이터를 쉽게 가져올 수 있습니다.

새 작업 영역 환경에서 만들기 하거나 조직 콘텐츠 팩을 사용할 수 없습니다. 대신 타사 서비스에 연결하기 위해 제공된 앱을 사용하거나 내부 팀이 현재 사용하는 콘텐츠 팩의 앱을 제공하도록 요청할 수 있습니다. 

## <a name="give-access-to-your-workspace"></a>작업 영역에 액세스할 수 있도록

1. 작업 영역 콘텐츠 목록에서 관리자 이므로 표시 새 작업을 **액세스**합니다.

    ![작업 영역 콘텐츠 목록](media/service-create-the-new-workspaces/power-bi-workspace-content-list.png)

1. **액세스**를 선택합니다.

1. 보안 그룹, 배포 목록, Office 365 그룹 또는 개인을 이러한 작업 영역에 구성원, 참가자 또는 관리자로 추가합니다. 다양한 역할에 대한 설명은 [새 작업 영역의 역할](service-new-workspaces.md#roles-in-the-new-workspaces)을 참조하세요.

    ![작업 영역 추가 멤버, 관리자, 기여자](media/service-create-the-new-workspaces/power-bi-access-add-members.png)

9. **추가** > **닫기**를 선택합니다.


## <a name="distribute-an-app"></a>앱 배포

조직 내에서 대규모 대상에 게 공식 콘텐츠를 배포 하려는 경우에 작업 영역에서 앱을 게시할 수 있습니다.  대시보드 및 보고서를 게시 하려면를 선택 하 고 다음으로 게시 하 콘텐츠가 준비 되 면 프로그램 *앱*합니다. 각 작업 영역에서 하나의 앱을 만들 수 있습니다.

에 대 한 읽기 [새 작업 영역에서 앱 게시](service-create-distribute-apps.md)

## <a name="next-steps"></a>다음 단계
* 에 대 한 읽기 [Power BI에서 새 작업 영역 환경에서 작업 구성](service-new-workspaces.md)
* [클래식 작업 영역 만들기](service-create-workspaces.md)
* [Power BI에서 새 작업 영역에서 앱 게시](service-create-distribute-apps.md)
* 궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](http://community.powerbi.com/)
