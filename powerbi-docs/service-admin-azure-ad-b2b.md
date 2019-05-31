---
title: Azure AD B2B에서 외부 게스트 사용자에게 콘텐츠 배포
description: Power BI는 Azure AD B2B(Azure Active Directory Business-to-business)를 통합하므로 조직 외부의 게스트 사용자에게 Power BI 콘텐츠를 안전하게 배포할 수 있습니다.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 04/25/2019
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 2d1e9e32fcec67647bb75ac14ed872e6c51fef96
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "65101670"
---
# <a name="distribute-power-bi-content-to-external-guest-users-with-azure-ad-b2b"></a>Azure AD B2B에서 외부 게스트 사용자에게 Power BI 콘텐츠 배포

Power BI는 Azure AD B2B(Azure Active Directory Business-to-business)를 통합하므로 조직 외부의 게스트 사용자에게 Power BI 콘텐츠를 안전하게 배포하고 내부 데이터에 대한 제어를 유지 관리할 수 있습니다.  

또한 조직의 외부 게스트 사용자가 조직의 콘텐츠를 편집하고 관리할 수 있도록 허용할 수 있습니다.

## <a name="enable-access"></a>액세스 사용

사용 하도록 설정 해야 합니다 [외부 사용자와 콘텐츠 공유](service-admin-portal.md#export-and-sharing-settings) 게스트 사용자를 초대 하기 전에 Power BI 관리 포털의 기능입니다.

사용할 수도 있습니다는 [외부 게스트 사용자를 편집 및 관리를 조직에 콘텐츠 허용](service-admin-portal.md#allow-external-guest-users-to-edit-and-manage-content-in-the-organization) 기능입니다. 사용 하면 선택 게스트 사용자는 보고 작업 영역에서는 조직의 Power BI 탐색을 포함 하 여 콘텐츠를 만들 수 있습니다.

## <a name="who-can-you-invite"></a>누구를 초대할 수 있나요?

Gmail.com, outlook.com, hotmail.com 등 개인 계정을 포함 한 모든 전자 메일 주소를 사용 하 여 게스트 사용자를 초대할 수 있습니다. 이러한 주소를 호출 하는 azure AD B2B *소셜 id*합니다.

## <a name="invite-guest-users"></a>게스트 사용자 초대

게스트 사용자는만 초대 조직에 초대 합니다. 처음으로 필요 합니다. 두 가지 방법으로 사용자를 초대 하기: 계획 된 초대 및 임시 초대 합니다.

### <a name="planned-invites"></a>계획 초대

초대할 사용자를 알고 있는 경우 계획 초대를 사용합니다. Azure Portal 또는 PowerShell을 사용하여 초대를 보낼 수 있습니다. 사람을 초대하려면 테넌트 관리자여야 합니다.

Azure Portal에서 초대를 보내려면 다음 단계를 수행합니다.

1. [Azure Portal](https://portal.azure.com)에서 **Azure Active Directory**를 선택합니다.

1. 아래 **관리**를 선택 **사용자** > **들은** > **새 게스트 사용자**.

    ![새 게스트 사용자 옵션을 사용 하 여 Azure portal의 스크린샷 호출 합니다.](media/service-admin-azure-ad-b2b/azure-ad-portal-new-guest-user.png)

1. **메일 주소** 및 **개인 메시지**를 입력합니다.

    ![Azure AD 포털 새 게스트 사용자 대화 상자의 스크린샷.](media/service-admin-azure-ad-b2b/azure-ad-portal-invite-message.png)

1. **초대**를 선택합니다.

여러 명의 게스트 사용자를 초대하려면 PowerShell을 사용합니다. 자세한 내용은 [Azure AD B2B 협업 코드 및 PowerShell 샘플](/azure/active-directory/b2b/code-samples/)을 참조하세요.

게스트 사용자는 받은 이메일 초대에서 **시작**을 선택해야 합니다. 그러면 게스트 사용자가 테넌트에 추가됩니다.

![스크린 샷의 게스트 사용자 이메일 초대 합니다.](media/service-admin-azure-ad-b2b/guest-user-invite-email.png)

### <a name="ad-hoc-invites"></a>임시 초대

언제 든 지 외부 사용자를 초대 하려면 대시보드 또는 보고서 공유 UI 통해 또는 액세스 페이지를 통해 앱을 추가 합니다. 다음은 앱을 사용할 외부 사용자를 초대할 때 수행할 작업의 예입니다.

![스크린 샷의 외부 사용자를 Power BI에서 앱 액세스 목록에 추가 합니다.](media/service-admin-azure-ad-b2b/power-bi-app-access.png)

게스트 사용자는 사람과 앱 공유 되었음을 나타내는 이메일을 받게 됩니다.

![게스트 사용자와 공유한 앱에 대 한 메일의 스크린샷](media/service-admin-azure-ad-b2b/guest-user-invite-email-2.png)

게스트 사용자가 해당 조직 이메일 주소로 로그인해야 합니다. 로그인 후 초대를 수락할 프롬프트를 받게 됩니다. 로그인 후 게스트 사용자에 대 한 앱이 열립니다. 앱으로 돌아가려면 링크를 책갈피로 표시하거나, 메일을 저장합니다.

## <a name="licensing"></a>라이선싱

게스트 사용자는 적합 한 라이선싱이 공유한 콘텐츠를 볼 수 있어야 합니다. 사용자에 적절 한 라이선스가 있는지 확인 하는 방법은 세 가지가 있습니다: Power BI 프리미엄을 사용 하 여, Power BI Pro 라이선스를 할당 또는 게스트의 Power BI Pro 라이선스를 사용 합니다.

[외부 게스트 사용자가 조직의 콘텐츠를 편집 및 관리하도록 허용](service-admin-portal.md#allow-external-guest-users-to-edit-and-manage-content-in-the-organization) 기능을 사용하는 경우, 작업 영역에 컨텐츠를 제공하거나 다른 사람들과 컨텐츠를 공유하는 게스트 사용자는 Power BI Pro 라이선스가 필요합니다.

### <a name="use-power-bi-premium"></a>Power BI Premium 사용

앱 작업 영역을 할당 [Power BI 프리미엄 용량](service-premium-what-is.md) 게스트 사용자가 Power BI Pro 라이선스가 필요 없이 앱을 사용할 수 있습니다. Power BI 프리미엄 앱을 새로 고침 비율 증대, 전용된 용량, 대규모 모델 크기와 같은 다른 기능은 활용할 수 있습니다.

![Power BI 프리미엄을 사용 하 여 게스트 사용자 환경의 다이어그램입니다.](media/service-admin-azure-ad-b2b/license-approach-1.png)

### <a name="assign-a-power-bi-pro-license-to-guest-user"></a>게스트 사용자에게 Power BI Pro 라이선스 할당

테 넌 트 안에서 게스트 사용자에 게 Power BI Pro 라이선스 할당을 사용 하면 테 넌 트에서 게스트 사용자 보기 콘텐츠가 있습니다.

![테 넌 트에서 Pro 할당할 라이선스를 사용 하 여 게스트 사용자 환경의 다이어그램입니다.](media/service-admin-azure-ad-b2b/license-approach-2.png)

### <a name="guest-user-brings-their-own-power-bi-pro-license"></a>게스트 사용자가 자신의 Power BI Pro 라이선스 사용

게스트 사용자에게 이미 테넌트 안에 할당된 Power BI Pro 라이선스가 있습니다.

![자신의 라이선스를 제공 하는 경우 게스트 사용자 환경의 다이어그램입니다.](media/service-admin-azure-ad-b2b/license-approach-3.png)

## <a name="guest-users-who-can-edit-and-manage-content"></a>콘텐츠를 편집하고 관리할 수 있는 게스트 사용자 

사용 하는 경우는 [외부 게스트 사용자를 편집 및 관리를 조직에 콘텐츠 허용](service-admin-portal.md#allow-external-guest-users-to-edit-and-manage-content-in-the-organization) 기능을 지정 된 게스트 사용자 조직의 Power BI에 대 한 액세스를 가져옵니다. 권한이 할 내용을 볼 수 있습니다. 액세스 홈, 작업 영역을 찾아보기, 앱을 설치, 액세스 목록에는 참조 하 고 작업 영역에 콘텐츠를 제공할 합니다. 또 새로운 작업 영역 환경을 사용하는 작업 영역의 관리자를 만들거나 관리자가 될 수 있습니다. 몇 가지 제한 사항이 적용 됩니다. 고려 사항 및 제한 사항 섹션에는 이러한 제한 나열 합니다.
 
Power BI에 로그인 하는 이러한 사용자를 위해 테 넌 트 URL을 제공 합니다. 테넌트 URL을 찾으려면 이 단계를 수행합니다.

1. Power BI 서비스의 맨 위 메뉴에서 도움말( **?** )을 선택한 후 **Power BI 정보**를 선택합니다.

2. **테넌트 URL** 옆에 있는 값을 찾습니다. 값은 테 넌 트 URL에 게스트 사용자와 공유할 수 있습니다.

    ![게스트 사용자 테 넌 트 url 호출을 사용 하 여 스크린 샷에 대 한 Power BI 대화 상자입니다.](media/service-admin-azure-ad-b2b/power-bi-about-dialog.png)

## <a name="considerations-and-limitations"></a>고려 사항 및 제한 사항

* 기본적으로 외부 Azure AD B2B 게스트에만 콘텐츠의 소비를 제한합니다. 외부 Azure AD B2B 게스트는 앱, 대시보드, 보고서를 볼 수 데이터를 내보내고 대시보드 및 보고서에 대 한 전자 메일 구독을 만듭니다. 작업 영역에 액세스하거나 자신의 콘텐츠를 게시할 수는 없습니다. 하지만 이러한 제한을 통해 액세스할 수 있는 게스트 사용자에 게 적용 되지 않습니다 합니다 [외부 게스트 사용자를 편집 및 관리를 조직에 콘텐츠 허용](service-admin-portal.md#allow-external-guest-users-to-edit-and-manage-content-in-the-organization) 기능입니다.

* 통해 사용할 수 있는 게스트 사용자에 대 한 합니다 [외부 게스트 사용자를 편집 및 관리를 조직에 콘텐츠 허용](service-admin-portal.md#allow-external-guest-users-to-edit-and-manage-content-in-the-organization) 기능을 일부 환경에 사용할 수 없습니다. 보고서를 업데이트하거나 게시하려면 데이터 가져오기 등의 Power BI 서비스 웹 UI를 사용하여 Power BI Desktop 파일을 업로드해야 합니다.  다음과 같은 환경은 지원 되지 않습니다.
    * Power BI Desktop에서 Power BI 서비스에 직접 게시
    * 게스트 사용자에 게 Power BI desktop를 사용 하 여 Power BI 서비스에서 서비스 데이터 집합에 연결할 수 없습니다.
    * Office 365 그룹에 연결된 클래식 작업 영역:
        * 게스트 사용자를 만들거나 이러한 작업 영역 관리자 수 없습니다.
        * 게스트 사용자 구성원 수 있습니다.
    * 작업 영역 액세스 목록에 지원 되지 않습니다 임시 초대 보내기
    * Power BI Publisher for Excel은 게스트 사용자에 대해 지원 되지 않습니다.
    * 게스트 사용자 수 없습니다. Power BI Gateway 설치 하 고 조직에 연결
    * 게스트 사용자가 설치할 수 없습니다. 전체 조직에 앱 게시
    * 게스트 사용자에 게 없습니다 사용, 만들기, 업데이트 또는 조직 콘텐츠 팩을 설치
    * 게스트 사용자는 Excel에서 분석을 사용할 수 없습니다.
    * 게스트 사용자 일 수 없습니다 @mentioned 에 주석 달기
    * 게스트 사용자에 게 구독을 사용할 수 없습니다.
    * 이 기능을 사용하는 게스트 사용자는 회사 또는 학교 계정이 있어야 합니다. 개인 계정을 사용 하 여 게스트 사용자 제한에 로그인으로 인해 더 많은 제한이 발생 합니다.

* 이 기능은 현재 Power BI SharePoint Online 보고서 웹 파트를 사용 하 여 사용할 수 없습니다.

* Active Directory 설정 하는 외부 게스트 사용자가 전체 조직 내에서 수행할 수 있는 작업을 제한할 수 있습니다. Power BI 환경에도 적용 됩니다. 다음 설명서에는 설정에 대해 설명되어 있습니다.
    * [외부 협업 설정 관리](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations#control-who-can-invite)
    * [특정 조직의 B2B 사용자 초대 허용 또는 차단](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)  

## <a name="next-steps"></a>다음 단계

행 수준 보안 작동을 비롯 한 자세한 내용은 백서 확인해 보세요. [Azure AD B2B를 사용하여 외부 게스트 사용자에게 Power BI 콘텐츠 배포](https://aka.ms/powerbi-b2b-whitepaper).

Azure AD B2B에 대 한 정보를 참조 하세요 [Azure AD B2B 공동 작업 이란?](/azure/active-directory/active-directory-b2b-what-is-azure-ad-b2b/)합니다.
