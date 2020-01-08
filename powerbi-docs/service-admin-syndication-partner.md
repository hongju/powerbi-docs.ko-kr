---
title: O365 파트너에게 Power BI를 추가할 수 없음
description: Office 365 신디케이션 파트너에게 Power BI를 추가할 수 없습니다. 신디케이티드 모델은 Office 365에서 사용하는 구매 모델입니다.
author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 09/09/2019
ms.author: kfollis
LocalizationGroup: Administration
ms.openlocfilehash: cc85fb07f50a42952e9b293908a797b1cbac023f
ms.sourcegitcommit: 320d83ab392ded71bfda42c5491acab3d9d357b0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74958359"
---
# <a name="unable-to-add-power-bi-to-office-365-partner-subscription"></a>Office 365 파트너 구독에 Power BI를 추가할 수 없음

Office 365는 회사에서 Office 365를 자사의 솔루션에 통합하여 재판매함으로써 최종 고객에게 구매, 청구 및 지원을 위한 단일 접점을 제공할 수 있도록 합니다.

Office 365 구독과 함께 Power BI를 구매하려면 파트너에게 문의하는 것이 좋습니다. 파트너가 Power BI를 제공하지 않을 경우 사용할 다양한 옵션이 있습니다.

## <a name="work-with-your-partner-to-purchase-power-bi"></a>파트너와 협업하여 Power BI 구매

Power BI Pro 또는 Power BI Premium에 대한 구독을 구매하려면 파트너와 협업하여 어떤 옵션이 있는지 고려합니다.

* 파트너가 Power BI를 포트폴리오에 추가하는 데 동의하여 고객이 파트너에게서 구매할 수 있도록 합니다.

* 파트너는 Microsoft로부터 직접 또는 Power BI를 제공하는 다른 파트너로부터 Power BI를 구매할 수 있는 모델로 전환할 수 있습니다.

## <a name="purchase-from-microsoft-or-another-channel"></a>Microsoft 또는 다른 채널에서 구매

파트너와 관계에 따라 Microsoft 또는 다른 파트너로부터 직접 Power BI를 구매할 수 있습니다. Microsoft 365 관리 센터에서 Power BI 구독을 추가할 수 있는지 확인할 수 있습니다(전역 관리자 또는 청구 관리자 역할의 멤버 자격 필요).

1. [Microsoft 365 관리 센터](https://admin.microsoft.com/AdminPortal/Home#/homepage)로 이동합니다.

1. 왼쪽 메뉴에서 **청구**를 엽니다.

    * **구독**이 표시되면 Microsoft에서 직접 서비스를 구매하거나 Power BI를 제공하는 다른 파트너에게 문의할 수 있습니다.

        ![청구 - 구독 포함](media/service-admin-syndication-partner/billingsub.png)

    * **구독**이 표시되지 않으면 Microsoft에서 직접 또는 다른 파트너로부터 구매할 수 없습니다.

파트너가 Power BI를 제공하지 않고 Microsoft 또는 다른 파트너로부터 직접 구매할 수 없는 경우에는 무료 평가판에 가입하는 것이 좋습니다.

## <a name="sign-up-for-a-free-trial"></a>무료 평가판 가입

Power BI 무료 평가판에 가입할 수 있습니다. 평가판 기간이 끝날 때 Power BI Pro를 구매하지 않아도 Power BI의 많은 기능을 제공하는 무료 라이선스가 계속 유지됩니다. 자세한 내용은 [Power BI에 개인으로 가입](service-self-service-signup-for-power-bi.md)을 참조하세요.

### <a name="enable-ad-hoc-subscriptions"></a>임시 구독 사용

기본적으로 임시 구독이라고도 하는 개별 가입은 사용하지 않도록 설정됩니다. 이 경우 등록하려고 하면 *IT 부서에서 Microsoft Power BI 등록을 해제했습니다.* 라는 메시지가 표시됩니다.

![죄송합니다 이미지](media/service-admin-syndication-partner/sorry.png)

임시 구독을 사용하도록 설정하려면 파트너에게 연락하여 임시 구독을 설정해 달라고 요청할 수 있습니다. 테넌트 관리자이고 Azure Active Directory PowerShell 명령을 사용하는 방법을 알고 있는 경우 직접 임시 구독을 사용하도록 설정할 수 있습니다. [그래프용 Azure Active Directory PowerShell](/powershell/azure/active-directory/install-adv2/)

1. Office 365 자격 증명을 사용하여 Azure Active Directory에 로그인합니다. 아래 스크립트의 첫 번째 줄은 사용자 자격 증명을 입력하라는 메시지를 표시합니다. 두 번째 행은 Azure Active Directory에 연결합니다.

    ```powershell
    $msolcred = get-credential
    connect-msolservice -credential $msolcred
    ```

    ![자격 증명 입력](media/service-admin-syndication-partner/aad-signin.png)

1. 로그인한 후 다음 명령을 실행하여 `AllowAdHocSubscriptions`에 대한 현재 설정을 확인합니다.

    ```powershell
    Get-MsolCompanyInformation
    ```

1. 다음 명령을 실행하여 무료 가입을 사용하도록 설정합니다.

    ```powershell
    Set-MsolCompanySettings -AllowAdHocSubscriptions $true
    ```

## <a name="next-steps"></a>다음 단계

[조직의 Power BI 라이선스 부여](service-admin-licensing-organization.md)

궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](https://community.powerbi.com/)