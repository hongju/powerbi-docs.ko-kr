---
title: Power BI 관리 - 질문과 대답(FAQ)
description: Power BI 등록, 테넌트 관리 및 기타 관리 작업에 대해 자주 묻는 질문에 대한 답변을 알아봅니다.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 11/16/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 2e51017333a940bd9d7838e6a903c1a66ce2e342
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "65100765"
---
# <a name="administering-power-bi---frequently-asked-questions-faq"></a>Power BI 관리 - 질문과 대답(FAQ)

이 문서에서는 Power BI 관리에 대한 질문과 대답을 다룹니다. Power BI 관리에 대한 개요는 [Power BI 관리란?](service-admin-administering-power-bi-in-your-organization.md)을 참조하세요.

## <a name="whats-in-this-article"></a>이 문서의 내용

### <a name="sign-up-for-power-bi-section"></a>Power BI 등록 섹션

* [PowerShell 사용](#using-powershell)
* [사용자가 Power BI에 등록하려면 어떻게 합니까?](#how-do-users-sign-up-for-power-bi)
* [개별 사용자가 조직에 등록하려면 어떻게 합니까?](#how-do-individual-users-in-my-organization-sign-up)
* [사용자가 내 기존 Office 365 테넌트에 가입하지 못하게 하려면 어떻게 합니까?](#how-can-i-prevent-users-from-joining-my-existing-office-365-tenant)
* [사용자가 내 기존 Office 365 테넌트에 가입하도록 허용하려면 어떻게 합니까?](#how-can-i-allow-users-to-join-my-existing-office-365-tenant)
* [테넌트에 가입이 차단되어 있는지 확인하려면 어떻게 해야 하나요?](#how-do-i-check-if-i-have-the-block-on-in-the-tenant)
* [기존 사용자가 Power BI 사용을 시작하지 못하게 하려면 어떻게 합니까?](#how-can-i-prevent-my-existing-users-from-starting-to-use-power-bi)
* [기존 사용자가 Power BI에 등록하도록 허용하려면 어떻게 합니까?](#how-can-i-allow-my-existing-users-to-sign-up-for-power-bi)

### <a name="administration-of-power-bi-section"></a>Power BI 관리 섹션

* [현재 조직의 사용자에 대한 ID를 관리하는 방법이 어떻게 달라집니까?](#how-will-this-change-the-way-i-manage-identities-for-users-in-my-organization-today)
* [Power BI를 어떻게 관리합니까?](#how-do-we-manage-power-bi)
* [Microsoft에서 사용자를 위해 만든 테넌트를 관리하는 프로세스는 무엇입니까?](#what-is-the-process-to-manage-a-tenant-created-by-microsoft-for-my-users)
* [여러 도메인이 있는 경우, 사용자가 추가되는 Office 365 테넌트를 제어할 수 있습니까?](#if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-get-added-to)
* [이미 등록된 사용자의 Power BI를 제거하려면 어떻게 하나요?](#how-do-i-remove-power-bi-for-users-that-already-signed-up)
* [새 사용자가 내 테넌트에 가입한 경우 어떻게 알 수 있습니까?](#how-do-i-know-when-new-users-have-joined-my-tenant)
* [추가로 준비 해야 할 것이 있나요?](#are-there-any-additional-things-i-should-prepare-for)
* [내 Power BI 테넌트는 어디에 있습니까?](#where-is-my-power-bi-tenant-located)
* [Power BI Service Level Agreement(서비스 수준 약정)란?](#what-is-the-power-bi-sla)
* [Power BI는 고가용성 및 장애 조치(failover)를 어떻게 처리하나요?](#how-does-power-bi-handle-high-availability-and-failover)

### <a name="security-in-power-bi-section"></a>Power BI의 보안 섹션

* [Power BI는 국가, 지역 및 업계별 규정 준수 요구 사항을 충족합니까?](#does-power-bi-meet-national-regional-and-industry-specific-compliance-requirements)
* [Power BI에서 보안은 어떻게 작동합니까?](#how-does-security-work-in-power-bi)

## <a name="sign-up-for-power-bi"></a>Power BI에 등록

### <a name="using-powershell"></a>PowerShell 사용

이 섹션의 일부 절차에는 Windows PowerShell 스크립트가 필요합니다. PowerShell에 익숙하지 않은 경우 [PowerShell 시작 가이드](http://go.microsoft.com/fwlink/p/?LinkID=286814)를 사용하는 것이 좋습니다. 스크립트를 실행하려면 먼저 [그래프용 Azure Active Directory PowerShell](/powershell/azure/active-directory/)의 최신 64비트 버전을 설치합니다.

### <a name="how-do-users-sign-up-for-power-bi"></a>사용자가 Power BI에 등록하려면 어떻게 합니까?

관리자로서, [Power BI 웹 사이트](https://powerbi.microsoft.com) 또는 Microsoft 365 관리 센터의 [서비스 구입](https://admin.microsoft.com/AdminPortal/Home#/catalog) 페이지를 통해 Power BI에 등록할 수 있습니다. 관리자가 Power BI에 등록할 때, 액세스 해야 하는 사용자에게 사용자 라이선스를 할당할 수 있습니다.

또한, 조직의 개별 사용자는 [Power BI 웹 사이트](https://powerbi.microsoft.com)를 통해 Power BI에 등록할 수 있습니다. 조직에서 사용자가 Power BI에 등록할 때 서비스는 자동으로 Power BI 라이선스를 사용자에게 할당 합니다. 자세한 내용은 [개별로 Power BI에 등록](service-self-service-signup-for-power-bi.md)과 [조직에서 Power BI 라이선스](service-admin-licensing-organization.md)를 참조 하세요.

### <a name="how-do-individual-users-in-my-organization-sign-up"></a>개별 사용자가 조직에 등록하려면 어떻게 합니까?

조직의 사용자에게 적용될 수 있는 세 가지 시나리오가 있습니다.

* **시나리오 1**: 조직에 기존 Office 365 환경이 이미 있고 Power BI에 가입하는 사용자가 Office 365 계정을 이미 가지고 있습니다.
    이 시나리오에서는 사용자가 테넌트에서 이미 회사 또는 학교 계정(예: contoso.com)을 가지고 있지만 아직 Power BI 없는 경우, Microsoft는 간단히 해당 계정에 대한 계획을 활성화 합니다. 사용자에게 Power BI 서비스를 사용 하는 방법에 대한 정보를 자동으로 알립니다.

* **시나리오 2**: 조직에 기존 Office 365 환경이 있지만, Power BI에 가입하는 사용자가 Office 365 계정을 가지고 있지 않습니다.
    이 시나리오에서는 사용자는 조직의 도메인(예: contoso.com)에 전자 메일 주소가 있지만 Office 365 계정이 아직 없습니다. 이 경우 사용자는 Power BI에 가입할 수 있으며 자동으로 계정을 받습니다. 이 작업을 통해 사용자는 Power BI 서비스에 액세스할 수 있습니다. 예를 들어, Nancy 라는 직원이 등록하기 위해 자신의 회사 전자 메일 주소(nancy@contoso.com 같은)를 사용하는 경우, Microsoft는 자동으로 Nancy를 Contoso의 Office 365 환경에 사용자로 추가하고 해당 계정에 대한 Power BI를 활성화 합니다.

* **시나리오 3**: 조직은 전자 메일 도메인에 연결된 Office 365 환경이 없습니다.
    Power BI를 활용하여 조직에 필요한 관리 작업이 없습니다. 서비스는 새 클라우드 전용 사용자 디렉터리에 사용자를 추가합니다. 테넌트 관리자로 인수 하여 관리할 수도 있습니다.

> [!IMPORTANT]
> 조직에 여러 전자 메일 도메인이 있고 모든 전자 메일 주소 확장을 같은 테넌트에 두려는 경우, 사용자가 등록하기 전에 모든 전자 메일 주소 도메인을 Azure Active Directory 테넌트에 추가합니다. 사용자를 만든 후, 테넌트에서 사용자를 이동하는 자동화된 메커니즘이 없습니다. 이 프로세스에 대한 자세한 내용은 이 문서의 뒷부분에 나오는 [여러 도메인이 있는 경우, 사용자가 추가하는 Office 365 테넌트를 제어할 수 있습니까?](#if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-get-added-to) 및 [Office 365에 도메인 추가](/office365/admin/setup/add-domain/)를 참조 하세요.

### <a name="how-can-i-prevent-users-from-joining-my-existing-office-365-tenant"></a>사용자가 내 기존 Office 365 테넌트에 가입하지 못하게 하려면 어떻게 합니까?

관리자로서 사용자가 기존 Office 365 테넌트에 가입하지 못하게 하기 위해 실행할 수 있는 단계가 있습니다. 액세스를 차단하는 경우, 사용자의 가입 시도가 실패하고, 조직의 관리자에게 문의하라는 메시지가 나타납니다. 자동 라이선스 배포를 사용하지 않도록 이미 설정한 경우(예를 들어 학생, 교수진 및 교직원을 위한 교육용 Office 365) 이 프로세스를 반복 하지 않아도 됩니다.

다음 PowerShell 스크립트를 사용하여 새 사용자가 관리형 테넌트에 가입하지 못하도록 합니다. [PowerShell에 대해 자세히 알아보세요][1].

```powershell
$msolcred = get-credential
connect-msolservice -credential $msolcred

Set-MsolCompanySettings -AllowEmailVerifiedUsers $false
```

> [!NOTE]
> 액세스 차단은 조직의 새 사용자가 Power BI에 가입하지 못하게 합니다. 조직의 새 가입을 사용하지 않도록 설정하기 전에 Power BI에 가입하는 사용자는 라이선스를 여전히 유지합니다. 사용자를 제거하려면 이 문서의 뒷부분의 [이미 등록된 사용자의 Power BI를 제거하려면 어떻게 하나요?](#how-do-i-remove-power-bi-for-users-that-already-signed-up)를 참조하세요.

### <a name="how-can-i-allow-users-to-join-my-existing-office-365-tenant"></a>사용자가 내 기존 Office 365 테넌트에 가입하도록 허용하려면 어떻게 합니까?

다음 PowerShell 스크립트를 사용하여 새 사용자가 관리되는 테넌트에 가입할 수 있도록 합니다. [PowerShell에 대해 자세히 알아보세요][1].

```powershell
$msolcred = get-credential
connect-msolservice -credential $msolcred

Set-MsolCompanySettings -AllowEmailVerifiedUsers $true
```

### <a name="how-do-i-check-if-i-have-the-block-on-in-the-tenant"></a>테넌트에 가입이 차단되어 있는지 확인하려면 어떻게 해야 하나요?

다음 PowerShell 스크립트를 사용하여 설정을 확인 합니다. *AllowEmailVerifiedUsers*는 false여야 합니다. [PowerShell에 대해 자세히 알아보세요][1].

```powershell
$msolcred = get-credential
connect-msolservice -credential $msolcred

Get-MsolCompanyInformation | fl allow*
```

### <a name="how-can-i-prevent-my-existing-users-from-starting-to-use-power-bi"></a>기존 사용자가 Power BI 사용을 시작하지 못하게 하려면 어떻게 합니까?

이를 제어하는 Azure AD 설정은 **AllowAdHocSubscriptions**입니다. 대부분의 테 넌 트가 사용 하는 것을 의미 하는 true로 설정 합니다. 파트너를 통해 Power BI를 구입한 경우이 비활성화 되어 즉 false로 설정할 수 있습니다.

다음 PowerShell 스크립트를 사용하여 임시 구독을 사용하지 않도록 설정합니다. [PowerShell에 대해 자세히 알아보세요][1].

1. Office 365 자격 증명을 사용하여 Azure Active Directory에 로그인합니다. 다음 PowerShell 스크립트의 첫 번째 행은 사용자 자격 증명을 입력하라는 메시지를 표시합니다. 두 번째 행은 Azure Active Directory에 연결합니다.

    ```powershell
     $msolcred = get-credential
     connect-msolservice -credential $msolcred
    ```

   ![PowerShell 통해 로그인 Azure Active Directory 스크린샷](media/service-admin-licensing-organization/azure-ad-sign-in.png)

1. 한 번에 로그인 할 테 넌 트 현재 설정 방법을 보려면 다음 명령을 실행 합니다.

    ```powershell
     Get-MsolCompanyInformation | fl AllowAdHocSubscriptions
    ```

1. 사용 하도록 설정 하려면 다음 명령을 실행 (`$true`) 하거나 사용 하지 않도록 (`$false`) **AllowAdHocSubscriptions**합니다.

    ```powershell
     Set-MsolCompanySettings -AllowAdHocSubscriptions $false
    ```

> [!NOTE]
> 사용 된 **AllowAdHocSubscriptions** Azure Rights Management 서비스에 등록 하려면 사용자가 기능을 포함 하 여 조직의 여러 사용자 기능을 제어 하는 플래그입니다. 이 플래그를 변경하면 이러한 모든 기능에 영향을 줍니다.

### <a name="how-can-i-allow-my-existing-users-to-sign-up-for-power-bi"></a>기존 사용자가 Power BI에 등록하도록 허용하려면 어떻게 합니까?

이전 질문에 대해 나열 된 명령을 실행 하는 Power BI에 등록 하려면 기존 사용자를 허용 하지만 전달 `$true` 대신 `$false` 마지막 단계에서 합니다.

## <a name="administration-of-power-bi"></a>Power BI 관리

### <a name="how-will-this-change-the-way-i-manage-identities-for-users-in-my-organization-today"></a>현재 조직의 사용자에 대한 ID를 관리하는 방법이 어떻게 달라집니까?

조직의 사용자에게 적용될 수 있는 세 가지 시나리오가 있습니다.

* **시나리오 1**: 조직에 기존 Office 365 환경에 있는 경우 Office 365 계정이 조직의 모든 사용자가 id를 관리 하는 방법에서 변하지가 않습니다.

* **시나리오 2**: 조직에 이미 기존 Office 365 환경이 있지만 조직의 일부 사용자가 Office 365 계정이, 하는 경우 테 넌 트에서 사용자를 만들기 하 고 사용자의 회사 또는 학교 전자 메일 주소에 따라 라이선스를 할당 합니다.

    결과적으로, 특정 시점에 관리 하는 사용자 수가 증가 함에 따라 조직의 사용자가 서비스에 등록.

* **시나리오 3**: 조직에 전자 메일 도메인에 연결 된 Office 365 환경에 없는 경우 id를 관리 하는 방법에서 변하지가 않습니다.

    서비스는 새 클라우드 전용 사용자 디렉터리에 사용자를 추가합니다. 또한 테 넌 트 관리자로 인수 하 여 관리할 수 있습니다.

### <a name="how-do-we-manage-power-bi"></a>Power BI를 어떻게 관리합니까?

Power BI는 사용 통계를 볼 수 있는 관리 포털을 사용자 및 그룹을 관리 하려면 Microsoft 365 관리 센터에 대 한 링크를 제공 하 고 테 넌 트 전체 설정을 제어 하는 기능을 제공을 제공 합니다.

Power BI 관리 포털을 사용 하려면 계정으로 표시 해야 합니다는 **전역 관리자** 내에서 Office 365 또는 Azure Active Directory 또는 다른 사용자를 할당 해야 합니다 Power BI 서비스 관리자 역할에 사용자 계정입니다. 자세한 내용은 참조 하세요. [Power BI 관리자 역할 이해](service-admin-role.md) 하 고 [Power BI 관리 포털](service-admin-portal.md)합니다.

### <a name="what-is-the-process-to-manage-a-tenant-created-by-microsoft-for-my-users"></a>Microsoft에서 내 사용자를 위해 만든 테넌트를 관리하는 프로세스는 무엇입니까?

셀프 서비스 사용자가 Azure AD를 사용 하는 클라우드 서비스에 등록할 때 서비스에 추가 관리 되지 않는 Azure AD directory 해당 메일 도메인에 기반 합니다. 클레임 및 사용자가 만든 이라는 프로세스를 사용 하 여 테 넌 트를 관리할 수는 *관리자 인수*합니다. 형식의 할 인수에 따라 달라 집니다 있는지 여부를 기존 도메인에 연결 된 테 넌 트를 관리 합니다.

* ‘내부 인수’를 사용하여 도메인에 대한 새 관리 테넌트를 만듭니다. 

* ‘외부 인수’를 사용하여 도메인을 기존 관리 테넌트로 이동합니다. 

자세한 내용은 참조 하세요. [Azure Active Directory에서 관리자 권한으로 관리 되지 않는 디렉터리 인수](/azure/active-directory/users-groups-roles/domains-admin-takeover)합니다.

외부 인수를 수행할 때 서비스 배치 Power BI에서 인수 전에 생성 된 콘텐츠를 [Power BI 보관 작업 영역](service-admin-power-bi-archived-workspace.md)합니다. 새 테넌트에서 사용할 콘텐츠를 수동으로 마이그레이션해야 합니다.

### <a name="if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-get-added-to"></a>여러 도메인이 있는 경우 사용자를 추가 하는 Office 365 테 넌 트 제어할 수 있습니다.?

아무 일도 하지 하는 경우 서비스는 각 사용자 전자 메일 도메인 및 하위 도메인에 대 한 테 넌 트를 만듭니다. 모든 사용자가 자신의 전자 메일 주소 확장명에 관계 없이 동일한 테넌트에 포함되도록 하려면: 미리 대상 테 넌 트 만들거나 기존 테 넌 트를 사용 합니다. 그런 다음 모든 기존 도메인 및 해당 테 넌 트 내에 통합 하는 것이 원하는 하위 도메인을 추가 합니다. 해당 도메인 및 하위 도메인을 자동으로 끝나는 전자 메일 주소를 사용 하 여 모든 사용자는 등록할 때 대상 테 넌 트를 조인 합니다.

> [!IMPORTANT]
> 사용자를 만든 후 테 넌 트에서 사용자를 이동 하는 지원 되는 자동화 된 메커니즘이 있습니다. 단일 Office 365 테넌트에 도메인 추가에 대해 알아보려면 [Office 365에 사용자 및 도메인 추가](/office365/admin/setup/add-domain/)를 참조하세요.

### <a name="how-do-i-remove-power-bi-for-users-that-already-signed-up"></a>이미 등록된 사용자에 대한 Power BI를 삭제하려면 어떻게 합니까?

사용자가 Power BI에 가입했지만 Power BI에 더 이상 액세스하지 않으려는 경우 해당 사용자에 대한 Power BI 라이선스를 제거할 수 있습니다.

1. [Microsoft 365 관리 센터](https://admin.microsoft.com/AdminPortal/Home#/homepage)로 이동합니다.

1. 왼쪽 탐색 모음에서 **사용자** > **활성 사용자**를 선택합니다.

1. 라이선스를 제거할 사용자를 찾은 후 사용자 이름을 선택합니다.

    사용자에 대해 대량 라이선스 관리를 수행할 수도 있습니다. 이렇게 하려면 여러 사용자를 선택하고 **제품 라이선스 편집**을 선택합니다.

1. 사용자 세부 정보 페이지의 **제품 라이선스** 옆에 있는 **편집**을 선택합니다.

1. 해당 계정에 적용 하면 새로운 라이선스에 따라 설정 합니다 **Power BI (무료)** 또는 **Power BI Pro** 하 **해제**합니다.

1. **저장**을 선택합니다.

### <a name="how-do-i-know-when-new-users-have-joined-my-tenant"></a>새 사용자가 내 테넌트에 가입한 경우 어떻게 알 수 있습니까?

이 프로그램의 일부로 테 넌 트에 가입한 사용자 관리 대시보드의 활성 사용자 창 내에서 필터링 할 수 있는 고유 라이선스를 할당 합니다. 이 새 보기를 만들려면 다음 단계를 수행합니다.

1. [Microsoft 365 관리 센터](https://admin.microsoft.com/AdminPortal/Home#/homepage)로 이동합니다.

1. 왼쪽 탐색 모음에서 **사용자** > **활성 사용자**를 선택합니다.

1. **보기** 메뉴에서 **사용자 지정 보기 추가**를 선택합니다.

1. 새 보기 이름을 지정하고 **할당된 제품 라이선스** 아래에서 **Power BI(무료)** 또는 **Power BI Pro**를 선택합니다.

    보기당 라이선스 한 개만 선택할 수 있습니다. 조직에서 **Power BI(무료)** 및 **Power BI Pro** 라이선스를 모두 가지고 있는 경우 두 보기를 만들 수 있습니다.

1. 원하는 다른 조건을 입력한 후 **추가**를 선택합니다.

1. 제공 되며 새 보기를 만든 후 합니다 **뷰** 메뉴.

### <a name="are-there-any-additional-things-i-should-prepare-for"></a>사항이 추가 대 한 준비 해야 하나요?

암호 재설정 요청의 증가를 경험할 수 있습니다. 이 프로세스에 대 한 자세한 내용은 참조 하십시오 [사용자의 암호를 재설정](/office365/admin/add-users/reset-passwords)합니다.

Microsoft 365 관리 센터에서 표준 프로세스를 통해 테넌트에서 사용자를 제거할 수 있습니다. 그러나 사용자가 조직에 활성 메일 주소를 여전히 가지고 있는 경우 관리자가 모든 사용자가 가입하지 못하게 차단하지 않는 한 해당 사용자가 다시 가입할 수 있습니다.

### <a name="where-is-my-power-bi-tenant-located"></a>내 Power BI 테넌트는 어디에 있습니까?

Power BI 테 넌 트에는 데이터 영역에 대 한 자세한 내용은 참조 하십시오 [내 Power BI 테 넌 트는 어디?](service-admin-where-is-my-tenant-located.md)합니다.

### <a name="what-is-the-power-bi-sla"></a>Power BI Service Level Agreement(서비스 수준 약정)란?

Power BI SLA (서비스 수준 계약)에 대 한 정보를 참조 하세요. 합니다 [조건 및 설명서](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=37) 에서 문서를 **라이선스** Microsoft 라이선스 웹 사이트의 섹션입니다.

### <a name="how-does-power-bi-handle-high-availability-and-failover"></a>Power BI는 고가용성 및 장애 조치(failover)를 어떻게 처리하나요?

고가용성 및 장애 조치 하는 방법에 대 한 정보를 참조 하세요 [Power BI 높은 가용성, 장애 조치 및 재해 복구 FAQ](service-admin-failover.md)합니다.

## <a name="security-in-power-bi"></a>Power BI의 보안

### <a name="does-power-bi-meet-national-regional-and-industry-specific-compliance-requirements"></a>Power BI는 국가, 지역 및 업계별 규정 준수 요구 사항을 충족합니까?

Power BI 준수에 대해 자세히 알아보려면 [Microsoft 보안 센터](https://www.microsoft.com/TrustCenter/CloudServices/business-application-platform/default.aspx)를 참조하세요.

### <a name="how-does-security-work-in-power-bi"></a>Power BI에서 보안은 어떻게 작동합니까?

Microsoft은 Power BI에서 Azure Active Directory와 같은 Azure 서비스에서 빌드되는 Office 365의 기초가 기반으로 합니다. Power BI 아키텍처 개요는 [Power BI 보안](service-admin-power-bi-security.md)을 참조하세요.

## <a name="next-steps"></a>다음 단계

[Power BI 관리 포털](service-admin-portal.md)  
[Power BI 관리자 역할 이해](service-admin-role.md)  
[Power BI에 대한 셀프 서비스 등록](service-self-service-signup-for-power-bi.md)  
[Power BI Pro 구매](service-admin-purchasing-power-bi-pro.md)  
[Power BI 프리미엄이란?](service-premium-what-is.md)  
[Power BI 프리미엄을 구입 하는 방법](service-admin-premium-purchase.md)  
[Power BI 프리미엄 백서](https://aka.ms/pbipremiumwhitepaper)  
[Power BI 및 Office 365에서 그룹 관리](service-manage-app-workspace-in-power-bi-and-office-365.md)  
[Office 365 사용자 계정 관리](/office365/servicedescriptions/office-365-platform-service-description/user-account-management/)  
[Office 365 그룹 관리](/office365/admin/email/create-edit-or-delete-a-security-group/)  

궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](http://community.powerbi.com/)

[1]: https://docs.microsoft.com/powershell/scripting/overview
