---
title: "조직에서 Power BI 관리"
description: "조직에서 Power BI 관리"
services: powerbi
documentationcenter: 
author: guyinacube
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 09/05/2017
ms.author: asaxton
ms.openlocfilehash: 3ee74e9a7f2f174b37e582089e0d9a1d6c433831
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2017
---
# <a name="administering-power-bi-in-your-organization"></a>조직에서 Power BI 관리
Microsoft Power BI를 사용하면 사용자가 데이터를 시각화, 검색 공유 및 직관적인 새로운 방법으로 공동 작업할 수 있습니다. 더 자세히 알아보려면 [Power BI 시작하기](service-get-started.md)를 참조하세요.

Power BI의 관리는 여러 위치에서 수행할 수 있습니다. 다음은 두 가지 일반적인 위치입니다.

> [!NOTE]
> Power BI 관리 포털에 대한 액세스 권한을 얻으려면 계정이 Office 365 또는 Azure Active Directory 내에서 **전역 관리자**로 표시되거나 Power BI 서비스 관리자 역할이 할당되어야 합니다. Power BI 서비스 관리자 역할에 대한 자세한 내용은 [Power BI 관리자 역할 이해](service-admin-role.md)를 참조하세요.
> 
> 

* [Power BI 관리 포털](https://app.powerbi.com/admin-portal)
* [Office 365 관리 센터](https://portal.office.com/adminportal/home)

Power BI 서비스 관리자 역할에 대한 자세한 내용은 [Power BI 관리자 역할 이해](service-admin-role.md)를 참조하세요.

## <a name="whats-in-this-article"></a>이 문서의 내용
**Power BI에 등록**

* [사용자가 Power BI에 등록하려면 어떻게 합니까?](#how-do-users-sign-up-for-power-bi)
* [개별 사용자가 조직에 등록하려면 어떻게 합니까?](#how-do-individual-users-in-my-organization-sign-up)
* [사용자가 내 기존 Office 365 테넌트에 가입하지 못하게 하려면 어떻게 합니까?](#how-can-i-prevent-users-from-joining-my-existing-office-365-tenant)
* [사용자가 내 기존 Office 365 테넌트에 가입하도록 허용하려면 어떻게 합니까?](#how-can-i-allow-users-to-join-my-existing-office-365-tenant)
* [내가 테넌트에 블록을 가지고 있는지 여부를 확인하려면 어떻게 합니까?](#how-do-i-verify-if-i-have-the-block-on-in-the-tenant)
* [기존 사용자가 Power BI 사용을 시작하지 못하게 하려면 어떻게 합니까?](#how-can-i-prevent-my-existing-users-from-starting-to-use-power-bi)
* [기존 사용자가 Power BI에 등록하도록 허용하려면 어떻게 합니까?](#how-can-i-allow-my-existing-users-to-sign-up-for-power-bi)

**Power BI 관리**

* [현재 조직의 사용자에 대한 ID를 관리하는 방법이 어떻게 달라집니까?](#how-will-this-change-the-way-i-manage-identities-for-users-in-my-organization-today)
* [Power BI를 어떻게 관리합니까?](#how-do-we-manage-power-bi)
* [Microsoft에서 내 사용자를 위해 만든 테넌트를 관리하는 프로세스는 무엇입니까?](#what-is-the-process-to-manage-a-tenant-created-by-Microsoft-for-my-users)
* [여러 도메인이 있는 경우 사용자가 추가되는 Office 365 테넌트를 제어할 수 있습니까?](#if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-are-added-to)
* [이미 등록된 사용자에 대한 Power BI를 삭제하려면 어떻게 합니까?](#how-do-i-remove-power-bi-for-users-that-already-signed-up)
* [새 사용자가 내 테넌트에 가입한 경우 어떻게 알 수 있습니까?](#how-do-i-know-when-new-users-have-joined-my-tenant)
* [추가로 준비할 사항이 있습니까?](#are-there-any-additional-things-i-should-be-prepared-for)
* [이는 무료입니까? 이 라이선스에 대해 수수료를 지불합니까?](#is-this-free-will-i-be-charged-for-these-licenses)
* [내 Power BI 테넌트는 어디에 있습니까?](#where-is-my-power-bi-tenant-located)

**Power BI의 보안**

* [Power BI는 국가, 지역 및 업계별 규정 준수 요구 사항을 충족합니까?](#does-power-bi-meet-national-regional-and-industry-specific-compliance-requirements)
* [Power BI에서 보안은 어떻게 작동합니까?](#how-does-security-work-in-power-bi?)

## <a name="sign-up-for-power-bi"></a>Power BI에 등록
### <a name="how-do-users-sign-up-for-power-bi"></a>사용자가 Power BI에 등록하려면 어떻게 합니까?
[Power BI 웹 사이트](https://powerbi.microsoft.com)를 통해 Power BI에 등록할 수 있습니다. 또한 Office 365 관리 센터의 구매 서비스 페이지를 통해 등록할 수도 있습니다. 관리자가 Power BI에 등록할 때 액세스 권한이 있어야 하는 사용자에게 사용자 라이선스를 할당할 수 있습니다.

또한 조직의 개별 사용자는 [Power BI 웹 사이트](https://powerbi.microsoft.com)를 통해 Power BI에 등록할 수 있습니다. 조직의 사용자가 Power BI에 등록할 때 해당 사용자에게 Power BI 라이선스가 자동으로 할당됩니다. [자세히 알아보기](service-self-service-signup-for-power-bi.md)

### <a name="how-do-individual-users-in-my-organization-sign-up"></a>개별 사용자가 조직에 등록하려면 어떻게 합니까?
조직의 사용자에게 적용될 수 있는 세 가지 시나리오가 있습니다.

시나리오 1: 조직에 기존 Office 365 환경이 이미 있고 Power BI에 등록하는 사용자가 Office 365 계정을 이미 가지고 있습니다.
이 시나리오에서 사용자가 테넌트(예: contoso.com)에 회사 또는 학교 계정을 이미 가지고 있지만 Power BI가 아직 없는 경우, Microsoft가 해당 계정에 대한 계획을 활성화해 주며 사용자에게 Power BI 서비스 사용 방법을 자동으로 알립니다.

시나리오 2: 조직에 기존 Office 365 환경이 이미 있는데 Power BI에 등록하는 사용자가 Office 365 계정을 가지고 있지 않습니다.
이 시나리오에서 사용자는 조직의 도메인(예: contoso.com)에 전자 메일 주소가 있지만 Office 365 계정이 아직 없습니다. 이 경우 사용자는 Power BI에 등록할 수 있으며 자동으로 계정을 받습니다. 이렇게 해서 사용자가 Power BI 서비스에 액세스할 수 있습니다. 예를 들어 Nancy라는 직원이 자신의 회사 전자 메일 주소(예: Nancy@contoso.com)를 사용하여 등록하면 Microsoft는 자동으로 Nancy를 Contoso의 Office 365 환경에 사용자로 추가하고 해당 계정에 대해 Power BI를 활성화합니다.

시나리오 3: 조직에 전자 메일 도메인에 연결된 Office 365 환경이 없습니다.
조직이 Power BI를 이용하기 위해 실행해야 하는 관리 작업은 없습니다. 사용자는 새 클라우드 전용 사용자 디렉터리에 추가되며, 이때 테넌트 관리자로 인수하여 사용자를 관리하도록 선택하는 옵션이 있습니다.

> [!IMPORTANT]
> 조직에 여러 전자 메일 도메인이 있고 모든 전자 메일 주소 확장을 같은 테넌트에 두려는 경우, 사용자가 등록하기 전에 모든 전자 메일 주소 도메인을 Azure Active Directory 테넌트에 추가합니다. 사용자가 생성된 후 테넌트 간에 사용자를 이동하는 자동화된 메커니즘은 없습니다. 이 프로세스에 대한 자세한 내용은 이 문서 뒷부분의 [여러 도메인이 있는 경우 사용자가 추가되는 Office 365 테넌트를 제어할 수 있습니까?](#if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-are-added-to) 및 온라인에서 [Office 365에 도메인 추가](https://support.office.com/article/Add-your-users-and-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)를 참조하세요.
> 
> 

### <a name="how-can-i-prevent-users-from-joining-my-existing-office-365-tenant"></a>사용자가 내 기존 Office 365 테넌트에 가입하지 못하게 하려면 어떻게 합니까?
관리자로서 사용자가 기존 Office 365 테넌트에 가입하지 못하게 하기 위해 실행할 수 있는 단계가 있습니다. 이렇게 차단하면 사용자의 등록 시도가 실패하며 사용자는 자기 조직의 관리자에게 문의하도록 디렉션됩니다. 자동 라이선스 배포(예: 학생, 교수 및 교직원을 위한 교육용 Office 365)를 이미 사용하지 않도록 설정한 경우 프로세스를 반복할 필요가 없습니다.

다음 단계를 수행하려면 Windows PowerShell을 사용해야 합니다. Windows PowerShell을 시작하려면 [PowerShell 시작 가이드](http://go.microsoft.com/fwlink/p/?LinkID=286814)를 참조하세요.

다음 단계를 수행하려면 최신 64비트 버전의 [Windows PowerShell용 Microsoft Azure Active Directory 모듈](http://go.microsoft.com/fwlink/p/?LinkID=236297)을 설치해야 합니다.

링크를 선택한 후 **실행**을 선택하여 설치 관리자 패키지를 실행합니다.

**자동 테넌트 가입 사용 안 함**: 이 Windows PowerShell 명령을 사용하여 새 사용자를 관리되는 테넌트에 가입하지 못하게 합니다.

* 새 사용자에 대해 자동 테넌트 가입을 사용하지 않으려면:
  
    $msolcred = get-credential   connect-msolservice -credential $msolcred
  
    Set-MsolCompanySettings -AllowEmailVerifiedUsers $false
* 새 사용자에 대해 자동 테넌트 가입을 사용하려면:
  
    $msolcred = get-credential   connect-msolservice -credential $msolcred
  
    Set-MsolCompanySettings -AllowEmailVerifiedUsers $true

> [!NOTE]
> 이 차단은 조직의 새 사용자가 Power BI에 등록하지 못하게 합니다. 조직에 대해 새 등록을 사용하지 않도록 설정하기 전에 Power BI에 등록하는 사용자는 라이선스를 여전히 유지합니다. 서비스에 대해 이전에 등록한 사용자에 대한 Power BI 액세스 권한을 제거할 수 있는 방법에 대한 지침은 [라이선스를 제거하려면 어떻게 해야 합니까?] 섹션을 참조하세요.
> 
> 

### <a name="how-can-i-allow-users-to-join-my-existing-office-365-tenant"></a>사용자가 내 기존 Office 365 테넌트에 가입하도록 허용하려면 어떻게 합니까?
사용자가 테넌트에 가입하도록 허용하려면 위의 질문에서 설명한 대로 반대 명령을 실행합니다.

다음 단계를 수행하려면 최신 64비트 버전의 [Windows PowerShell용 Microsoft Azure Active Directory 모듈](http://go.microsoft.com/fwlink/p/?LinkID=236297)을 설치해야 합니다.

    $msolcred = get-credential
    connect-msolservice -credential $msolcred

    Set-MsolCompanySettings -AllowEmailVerifiedUsers $true

### <a name="how-do-i-verify-if-i-have-the-block-on-in-the-tenant"></a>내가 테넌트에 블록을 가지고 있는지 여부를 확인하려면 어떻게 합니까?
다음 PowerShell 스크립트를 사용합니다.

다음 단계를 수행하려면 최신 64비트 버전의 [Windows PowerShell용 Microsoft Azure Active Directory 모듈](http://go.microsoft.com/fwlink/p/?LinkID=236297)을 설치해야 합니다.

    $msolcred = get-credential
    connect-msolservice -credential $msolcred

    Get-MsolCompanyInformation | fl allow*

### <a name="how-can-i-prevent-my-existing-users-from-starting-to-use-power-bi"></a>기존 사용자가 Power BI 사용을 시작하지 못하게 하려면 어떻게 합니까?
관리자로서 사용자가 Power BI에 등록하지 못하게 하기 위해 실행할 수 있는 단계가 있습니다. 이렇게 차단하면 사용자의 등록 시도가 실패하며 사용자는 자기 조직의 관리자에게 문의하도록 디렉션됩니다. 자동 라이선스 배포(예: 학생, 교수 및 교직원을 위한 교육용 Office 365)를 이미 사용하지 않도록 설정한 경우 프로세스를 반복할 필요가 없습니다. [자세히 알아보기](service-admin-service-free-in-your-organization.md#enable-or-disable-individual-user-sign-up-in-azure-active-directory)

이를 제어하는 AAD 설정은 **AllowAdHocSubscriptions**입니다. 대부분의 테넌트에서는 이 설정을 true로 설정되어 사용합니다. 파트너를 통해 Power BI를 구입한 경우 기본적으로 false로 설정되어 사용하지 않습니다.

다음 단계를 수행하려면 최신 64비트 버전의 [Windows PowerShell용 Microsoft Azure Active Directory 모듈](http://go.microsoft.com/fwlink/p/?LinkID=236297)을 설치해야 합니다.

1. 먼저 Office 365 자격 증명을 사용하여 Azure Active Directory에 로그인해야 합니다. 첫 번째 행에서 자격 증명을 확인합니다. 두 번째 행은 Azure Active Directory에 연결합니다.
   
     $msolcred = get-credential   connect-msolservice -credential $msolcred
2. 로그인하면 테넌트가 현재 구성된 항목을 참조하도록 다음 명령을 시작할 수 있습니다.
   
     Get-MsolCompanyInformation | fl AllowAdHocSubscriptions
3. AllowAdHocSubscriptions을 사용하거나($true) 사용하지 않도록($false) 이 명령을 사용할 수 있습니다.
   
     Set-MsolCompanySettings -AllowAdHocSubscriptions $true

> [!NOTE]
> AllowAdHocSubscriptions 플래그는 사용자가 Azure 권한 관리 서비스에 등록하는 기능을 비롯하여 조직의 여러 사용자 기능을 제어하기 위해 사용됩니다. 이 플래그 변경은 이러한 모든 기능에 적용됩니다.
> 
> 

### <a name="how-can-i-allow-my-existing-users-to-sign-up-for-power-bi"></a>기존 사용자가 Power BI에 등록하도록 허용하려면 어떻게 합니까?
기존 사용자가 Power BI에 등록하도록 허용하려면 위의 질문에 대해 나열된 명령을 실행하되, False 대신 True를 전달합니다.

다음 단계를 수행하려면 최신 64비트 버전의 [Windows PowerShell용 Microsoft Azure Active Directory 모듈](http://go.microsoft.com/fwlink/p/?LinkID=236297)을 설치해야 합니다.

1. 먼저 Office 365 자격 증명을 사용하여 Azure Active Directory에 로그인해야 합니다. 첫 번째 행에서 자격 증명을 확인합니다. 두 번째 행은 Azure Active Directory에 연결합니다.
   
     $msolcred = get-credential   connect-msolservice -credential $msolcred
2. 로그인하면 테넌트가 현재 구성된 항목을 참조하도록 다음 명령을 시작할 수 있습니다.
   
     Get-MsolCompanyInformation | fl AllowAdHocSubscriptions
3. AllowAdHocSubscriptions을 사용하거나($true) 사용하지 않도록($false) 이 명령을 사용할 수 있습니다.
   
     Set-MsolCompanySettings -AllowAdHocSubscriptions $true

> [!NOTE]
> AllowAdHocSubscriptions 플래그는 사용자가 Azure 권한 관리 서비스에 등록하는 기능을 비롯하여 조직의 여러 사용자 기능을 제어하기 위해 사용됩니다. 이 플래그 변경은 이러한 모든 기능에 적용됩니다.
> 
> 

## <a name="administration-of-power-bi"></a>Power BI 관리
### <a name="how-will-this-change-the-way-i-manage-identities-for-users-in-my-organization-today"></a>현재 조직의 사용자에 대한 ID를 관리하는 방법이 어떻게 달라집니까?
조직에 기존 Office 365 환경이 이미 있고 조직의 모든 사용자가 Office 365 계정을 가지고 있는 경우 ID 관리는 변하지 않습니다.

조직에 기존 Office 365 환경이 있지만 조직의 일부 사용자가 Office 365 계정을 가지고 있지 않은 경우 테넌트에서 사용자를 생성하고 사용자의 회사 또는 학교 전자 메일 주소를 기반으로 라이선스를 할당합니다. 즉, 특정 시간에 관리하는 사용자 수는 조직의 사용자가 서비스에 등록함에 따라 증가합니다.

온-프레미스로 디렉터리를 관리하고 AD FS(Active Directory Federation Services)를 사용하는 경우 Microsoft는 테넌트에 사용자를 추가하지 않으며 테넌트에 가입을 시도하는 사용자는 조직의 관리자에게 문의하라는 메시지를 받게 됩니다.

조직에 전자 메일 도메인에 연결된 Office 365 환경이 없는 경우 ID를 관리하는 방법이 변경되지 않습니다. 사용자는 새 클라우드 전용 사용자 디렉터리에 추가되며, 이때 테넌트 관리자로 인수하여 사용자를 관리하도록 선택하는 옵션이 있습니다.

### <a name="how-do-we-manage-power-bi"></a>Power BI를 어떻게 관리합니까?
Power BI는 사용 통계를 볼 수 있는 관리 포털, 사용자 및 그룹을 관리하는 Office 365 관리 센터에 대한 링크, 그리고 테넌트 전체 설정을 제어하는 기능을 제공합니다. 

> [!NOTE]
> Power BI 관리 포털에 대한 액세스 권한을 얻으려면 Office 365 또는 Azure Active Directory 내에서 계정을 **전역 관리자**로 표시해야 합니다.
> 
> 

자세한 내용은 [Power BI 관리 포털](service-admin-portal.md)을 참조하세요.

### <a name="what-is-the-process-to-manage-a-tenant-created-by-microsoft-for-my-users"></a>Microsoft에서 내 사용자를 위해 만든 테넌트를 관리하는 프로세스는 무엇입니까?
테넌트를 Microsoft가 만든 경우 다음 단계를 따라 테넌트를 청구 및 관리할 수 있습니다.

1. 관리할 테넌트 도메인과 일치하는 전자 메일 주소 도메인을 사용해 Power BI에 등록하여 테넌트에 가입합니다. 예를 들어 Microsoft가 contoso.com 테넌트를 만든 경우 @contoso.com으로 끝나는 전자 메일 주소를 사용하여 테넌트에 가입해야 합니다.
2. 도메인 소유권을 확인하여 관리자 제어 청구: 테넌트 내에서 도메인 소유권을 확인하여 *전역 관리자* 역할을 승격할 수 있습니다. 이 작업을 수행하려면 다음 단계를 따릅니다.
   
   1. [https://portal.office.com](https://portal.office.com)으로 이동합니다.
   2. 왼쪽 위에서 앱 시작 관리자 아이콘을 선택하고 **관리자**를 선택합니다.
   3. **관리자 되기** 페이지의 지침을 읽은 다음 **예, 관리자가 되려고 합니다**를 선택합니다.
      
      > [!NOTE]
      > 이 옵션이 표시되지 않으면 Office 365 관리자가 이미 있는 것입니다.
      > 
      > 

### <a name="if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-are-added-to"></a>여러 도메인이 있는 경우 사용자가 추가되는 Office 365 테넌트를 제어할 수 있습니까?
아무 일도 하지 않은 경우 각 사용자 전자 메일 도메인 및 하위 도메인에 대해 테넌트가 생성됩니다.

모든 사용자가 자신의 전자 메일 주소 확장명에 관계 없이 동일한 테넌트에 포함되도록 하려면:

* 대상 테넌트를 미리 만들거나 기존 테넌트를 사용하고 해당 테넌트 내에 통합할 모든 기존 도메인 및 하위 도메인을 추가합니다. 그러면 해당 도메인 및 하위 도메인으로 끝나는 전자 메일 주소를 가진 모든 사용자가 등록할 때 대상 테넌트에 자동으로 가입됩니다.

> [!IMPORTANT]
> 사용자가 생성된 후 테넌트 간에 사용자를 이동하는 자동화된 메커니즘은 없습니다. 단일 Office 365 테넌트에 도메인 추가에 대해 알아보려면 [Office 365에 사용자 및 도메인 추가](https://support.office.com/article/Add-your-users-and-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)를 참조하세요.
> 
> 

### <a name="how-do-i-remove-power-bi-for-users-that-already-signed-up"></a>이미 등록된 사용자에 대한 Power BI를 삭제하려면 어떻게 합니까?
사용자가 Power BI에 등록했지만 Power BI에 더 이상 액세스하지 않으려는 경우 해당 사용자에 대한 Power BI 라이선스를 제거할 수 있습니다.

1. Office 365 관리 센터로 이동합니다.
2. 왼쪽 탐색 모음에서 **사용자** > **활성 사용자**를 선택합니다.
3. 라이선스를 제거할 사용자를 찾은 다음 사용자 이름 > **편집**을 선택합니다.
4. 사용자 세부 정보 페이지의 왼쪽 탐색 모음에서 **라이선스**를 선택합니다.
5. 계정에 어떤 라이선스가 적용되는지에 따라 **Power BI(무료)** 또는 **Power BI Pro**를 선택 취소합니다.
6. **저장**을 선택합니다.

> [!NOTE]
> 사용자에 대해 대량 라이선스 관리를 수행할 수도 있습니다. 이렇게 하려면 여러 사용자를 선택하고 **편집**을 선택합니다.
> 
> 

### <a name="how-do-i-know-when-new-users-have-joined-my-tenant"></a>새 사용자가 내 테넌트에 가입한 경우 어떻게 알 수 있습니까?
이 프로그램의 일부로 테넌트에 가입한 사용자에 대해서는 관리 대시보드의 활성 사용자 창에서 필터링할 수 있는 고유한 라이선스가 할당됩니다.

새 보기를 생성하려면 Office 365 관리 센터에서 **사용자** > **활성 사용자**로 이동하고 **보기 선택** 메뉴에서 **새 보기**를 선택합니다. 새 보기 이름을 지정하고 **할당된 라이선스** 아래에서 **Power BI(무료)** 또는 **Power BI Pro**를 선택합니다. 보기당 라이선스 한 개만 선택할 수 있습니다. 조직에서 **Power BI(무료)** 및 **Power BI Pro** 라이선스를 모두 가지고 있는 경우 두 보기를 생성해야 합니다. 새 보기가 생성된 후 이 프로그램에서 등록한 테넌트의 모든 사용자를 확인할 수 있습니다.

### <a name="are-there-any-additional-things-i-should-be-prepared-for"></a>추가로 준비할 사항이 있습니까?
암호 재설정 요청의 증가를 경험할 수 있습니다. 이 프로세스에 대한 자세한 내용은 [사용자의 암호 재설정](https://support.office.com/article/Reset-a-users-password-7a5d073b-7fae-4aa5-8f96-9ecd041aba9c)을 참조하세요.

Office 365 관리 센터에서 표준 프로세스를 통해 테넌트에서 사용자를 제거할 수 있습니다. 그러나 사용자가 조직에 활성 전자 메일 주소를 여전히 가지고 있는 경우 관리자가 모든 사용자를 가입하지 못하게 차단하지 않은 한 해당 사용자가 다시 가입할 수 있습니다.

### <a name="is-this-free-will-i-be-charged-for-these-licenses"></a>이는 무료입니까? 이 라이선스에 대해 수수료를 지불합니까?
**Power BI(무료)** 라이선스는 Power BI의 무료 버전에 대한 것입니다. 추가 기능에 관심이 있는 경우 [Power BI Pro 버전](service-premium.md)을 참조하세요.

### <a name="where-is-my-power-bi-tenant-located"></a>내 Power BI 테넌트는 어디에 있습니까?
데이터 영역이라고도 알려진 Power BI 테넌트의 위치를 찾는 방법은 [내 Power BI 테넌트는 어디에 있습니까?](service-admin-where-is-my-tenant-located.md)를 참조하세요.

## <a name="security-in-power-bi"></a>Power BI의 보안
### <a name="does-power-bi-meet-national-regional-and-industry-specific-compliance-requirements"></a>Power BI는 국가, 지역 및 업계별 규정 준수 요구 사항을 충족합니까?
Power BI 준수에 대해 자세히 알아보려면 [Microsoft 보안 센터](http://go.microsoft.com/fwlink/?LinkId=785324)를 참조하세요.

### <a name="how-does-security-work-in-power-bi"></a>Power BI에서 보안은 어떻게 작동합니까?
Power BI는 Azure Active Directory와 같은 Azure 서비스를 기초로 하는 Office 365를 기반으로 합니다. Power BI 아키텍처 개요는 [Power BI 보안](service-admin-power-bi-security.md)을 참조하세요. 

## <a name="next-steps"></a>다음 단계
[Power BI 관리 포털](service-admin-portal.md)  
[Power BI 관리자 역할 이해](service-admin-role.md)  
[Power BI에 대한 셀프 서비스 등록](service-self-service-signup-for-power-bi.md)  
[조직의 Power BI(무료)](service-admin-service-free-in-your-organization.md)  
[Power BI Pro 구매](service-admin-purchasing-power-bi-pro.md)  
[Power BI 프리미엄이란?](service-premium.md)  
[Power BI 프리미엄 구매 방법](service-admin-premium-purchase.md)  
[Office 365 사용자 계정 관리](https://technet.microsoft.com/library/office-365-user-account-management.aspx)  
[Office 365 그룹 관리](https://support.office.com/Article/Find-help-about-Groups-in-Office-365-7a9b321f-b76a-4d53-b98b-a2b0b7946de1)  
[Power BI 및 Office 365에서 그룹 관리](service-manage-app-workspace-in-power-bi-and-office-365.md)  
[Power BI 프리미엄 백서](https://aka.ms/pbipremiumwhitepaper)  

궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](http://community.powerbi.com/)

