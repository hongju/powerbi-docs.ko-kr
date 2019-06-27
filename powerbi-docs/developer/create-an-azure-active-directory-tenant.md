---
title: Power BI에서 사용할 Azure Active Directory 테넌트 만들기
description: Power BI REST API를 호출하는 사용자 지정 애플리케이션에 대한 새 Azure AD(Azure Active Directory) 테넌트를 만드는 방법을 알아봅니다.
author: rkarlin
ms.author: rkarlin
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 05/28/2019
ms.openlocfilehash: 73dddd00b6f811cd29c76c97b04136358d6e6b7a
ms.sourcegitcommit: aef57ff94a5d452d6b54a90598bd6a0dd1299a46
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/07/2019
ms.locfileid: "66809233"
---
# <a name="create-an-azure-active-directory-tenant-to-use-with-power-bi"></a>Power BI에서 사용할 Azure Active Directory 테넌트 만들기

[Power BI REST API](rest-api-reference.md)를 호출하는 사용자 지정 애플리케이션에 대한 새 Azure AD(Azure Active Directory) 테넌트를 만드는 방법을 알아봅니다.

테넌트는 Azure Active Directory에 조직을 표시합니다. 이것은 조직이 Azure, Microsoft Intune 또는 Office 365와 같은 Microsoft 클라우드 서비스에 가입할 때 수신하고 소유하는 전용 Azure AD 서비스 인스턴스입니다. 각 Azure AD 테넌트는 고유하며 다른 Azure AD 테넌트와 별개입니다.

Azure AD 테넌트가 있다면 애플리케이션을 정의하고 [Power BI REST API](rest-api-reference.md)를 호출할 수 있도록 사용 권한을 할당할 수 있습니다.

조직에는 애플리케이션에 사용할 수 있는 Azure AD 테넌트가 이미 있을 수 있습니다. 또한 애플리케이션 전용 새 테넌트를 만들 수도 있습니다. 이 문서에서는 새 테넌트를 만드는 방법을 설명합니다.

## <a name="create-an-azure-active-directory-tenant"></a>Azure Active Directory 테넌트 만들기

Power BI를 사용자 지정 애플리케이션에 통합하려면 Azure AD 내에서 애플리케이션을 정의해야 하며, Azure AD 디렉터리가 필요합니다. 이 디렉터리는 사용자 *테넌트*입니다. 조직에서 Power BI 또는 Office 365를 사용하지 않아서 아직 테넌트가 없는 경우 [개발 환경을 설정해야 합니다](https://docs.microsoft.com/azure/active-directory/develop/active-directory-howto-tenant). 애플리케이션을 조직의 테넌트와 혼합하여 사용하지 않으려는 경우에도 테넌트를 만들어 격리된 상태로 유지할 수 있어야 합니다. 또는 테스트 용도로 테넌트를 만들려고 할 수 있습니다.

새 Azure AD 테넌트를 만들려면 다음을 수행합니다.

1. [Azure Portal](https://portal.azure.com)로 이동하여 Azure 구독이 있는 계정으로 로그인합니다.

2. **더하기 아이콘(+)** 을 선택하고 **Azure Active Directory**를 검색합니다.

    ![더하기 아이콘(+)](media/create-an-azure-active-directory-tenant/new-directory.png)

3. 검색 결과에서 **Azure Active Directory**를 선택합니다.

    ![AAD 검색](media/create-an-azure-active-directory-tenant/new-directory2.png)

4. **만들기**를 선택합니다.

5. **조직 이름** 및 **초기 도메인 이름**을 제공합니다. 그런 다음 **만들기**를 선택합니다. 디렉터리가 만들어집니다.

    ![조직 및 도메인](media/create-an-azure-active-directory-tenant/organization-and-domain.png)

   > [!NOTE]
   > 초기 도메인은 onmicrosoft.com의 일부입니다. 나중에 다른 도메인 이름을 추가할 수 있습니다. 테넌트 디렉터리에는 여러 도메인이 할당될 수 있습니다.

6. 디렉터리 만들기를 완료한 후 새 디렉터리를 관리하는 정보 상자를 선택합니다.

다음으로 테넌트 사용자를 추가합니다.

## <a name="create-azure-active-directory-tenant-users"></a>Azure Active Directory 테넌트 사용자 만들기

이제 디렉터리가 있으며 두 명 이상의 사용자를 만들어 보겠습니다. 하나는 테넌트 글로벌 관리자이며 다른 하나는 포함을 위한 마스터 사용자입니다. 후자를 서비스 계정으로 생각할 수 있습니다.

1. Azure Portal에서 Azure Active Directory를 사용하고 있는지 확인합니다.

    ![](media/create-an-azure-active-directory-tenant/aad-flyout.png)

    그렇지 않은 경우 왼쪽 서비스 탐색에서 Azure Active Directory 아이콘을 선택합니다.

    ![](media/create-an-azure-active-directory-tenant/aad-service.png)

2. **관리** 아래에서 **사용자**를 선택합니다.

    ![](media/create-an-azure-active-directory-tenant/users-and-groups.png)

3. **모든 사용자**를 선택한 후 **+ 새 사용자**를 선택합니다.

4. 테넌트 글로벌 관리자에 대한 **이름** 및 **사용자 이름**을 제공합니다. **디렉터리 역할**을 **글로벌 관리자**로 변경합니다. 임시 암호를 표시할 수도 있습니다. 완료되면 **만들기**를 선택합니다.

    ![](media/create-an-azure-active-directory-tenant/global-admin.png)

5. 일반 테넌트 사용자에 대해 동일한 작업을 수행합니다. 마스터 포함 계정에 대해 이 계정을 사용할 수 있습니다. 현재는 **디렉터리 역할**에 대해 **사용자**로 남겨 둡니다. 암호를 적어 둔 다음, **만들기**를 선택합니다.

    ![](media/create-an-azure-active-directory-tenant/pbiembed-user.png)

6. 5단계에서 만든 사용자 계정으로 Power BI에 가입합니다. [powerbi.com](https://powerbi.microsoft.com/get-started/)으로 이동하고 **Power BI - Cloud 협업 및 공유** 아래에서 **평가판 사용해 보기**를 선택합니다.

    ![](media/create-an-azure-active-directory-tenant/try-powerbi-free.png)

    가입하면 Power BI Pro를 60일 동안 무료로 사용해보라는 메시지가 표시됩니다. [임베디드 솔루션 개발 시작](embedding-content.md)에 대한 옵션을 제공하는 Pro 사용자가 되도록 가입할 수 있습니다.

   > [!NOTE]
   > 사용자 계정의 이메일 주소로 가입해야 합니다.

## <a name="next-steps"></a>다음 단계

이제 Azure AD 테넌트가 있으므로 이 테넌트를 사용하여 Power BI 내에서 항목을 테스트할 수 있습니다. 또한 애플리케이션에서 Power BI 대시보드 및 보고서를 포함할 수도 있습니다. 자세한 내용은 [Power BI 대시보드, 보고서 및 타일을 포함하는 방법](embedding-content.md)을 참조하세요.

[Azure Active Directory란?](https://docs.microsoft.com/azure/active-directory/active-directory-whatis) 
 
[빠른 시작: 개발 환경 설정](https://docs.microsoft.com/azure/active-directory/develop/active-directory-howto-tenant)  

궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](http://community.powerbi.com/)
