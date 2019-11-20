---
title: 포함된 Power BI 콘텐츠에 앱 등록
description: Power BI 콘텐츠 포함에 사용하기 위해 Azure Active Directory 내에서 애플리케이션을 등록하는 방법에 대해 알아봅니다.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: nishalit
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 04/02/2019
ms.openlocfilehash: 8a2aa135bfa5720763485579b012c13c722637db
ms.sourcegitcommit: 0d7ad791a2d2bef45d5d60e38e0af4c9fc22187b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74009791"
---
# <a name="register-an-azure-ad-application-to-use-with-power-bi"></a>Power BI와 함께 사용할 Azure AD 애플리케이션 등록

Power BI 콘텐츠 포함에 사용하기 위해 Azure AD(Azure Active Directory) 내에서 애플리케이션을 등록하는 방법에 대해 알아봅니다.

Azure AD에 애플리케이션을 등록하면 애플리케이션에서 [Power BI REST API](https://docs.microsoft.com/rest/api/power-bi/)에 액세스할 수 있습니다. 애플리케이션을 등록하면 애플리케이션의 ID를 설정하고 Power BI REST 리소스에 대한 권한을 지정할 수 있습니다.

> [!IMPORTANT]
> Power BI 앱을 등록하려면 먼저 [Azure Active Directory 테넌트 및 조직 사용자](create-an-azure-active-directory-tenant.md)가 있어야 합니다. 테넌트의 사용자를 Power BI에 아직 등록하지 않은 경우 앱 등록이 성공적으로 완료되지 않습니다.

두 가지 방법으로 애플리케이션을 등록합니다. 즉, [Power BI 앱 등록 도구](https://dev.powerbi.com/apps/)를 사용하거나 Azure Portal 내에서 직접 수행하면 됩니다. Power BI 앱 등록 도구는 완료해야 할 필드가 몇 개뿐이므로 사용이 더 편리합니다. 앱을 변경하려는 경우 Azure Portal을 사용합니다.

## <a name="register-with-the-power-bi-application-registration-tool"></a>Power BI 애플리케이션 등록 도구를 사용하여 등록

애플리케이션을 **Azure Active Directory**에 등록하여 애플리케이션의 ID를 설정하고 Power BI REST 리소스에 대한 사용 권한을 지정하세요. 콘솔 앱 또는 웹 사이트와 같은 애플리케이션을 등록하는 경우 애플리케이션이 사용 권한을 요청한 사용자에게 자신을 식별하기 위해 사용하는 ID를 받습니다.

Power BI 앱 등록 도구를 사용하여 애플리케이션을 등록하는 방법은 다음과 같습니다.

1. [dev.powerbi.com/apps](https://dev.powerbi.com/apps)로 이동합니다.

2. 기존 계정으로 **로그인**을 선택한 후, **다음**을 선택합니다.

3. **애플리케이션 이름**을 제공합니다.

4. **애플리케이션 유형**을 제공합니다.

    애플리케이션에 유형에 대해 **네이티브**를 선택하는 이유와 **서버 쪽 웹 애플리케이션**을 선택하는 이유의 차이점은 다음과 같습니다.

    네이티브:
    * 인증을 위해 마스터 사용자 계정(Power BI에 로그인하는 데 사용되는 Power BI Pro 라이선스)을 사용하여 [고객용으로 디자인된](embed-sample-for-customers.md) 애플리케이션을 만들 계획입니다.

    서버 쪽 웹 애플리케이션:
    * [조직용으로 디자인된](embed-sample-for-your-organization.md) 애플리케이션을 만들 계획입니다.
    * 인증을 위해 서비스 주체를 사용하여 [고객용으로 디자인된](embed-sample-for-customers.md) 애플리케이션을 만들 계획입니다.
    * 웹앱 또는 웹 API를 만들 계획입니다.

    ![앱 유형](media/register-app/register-app-new-design-app-type.png)

5. 애플리케이션 유형으로 **서버 쪽 웹 애플리케이션**을 선택한 경우 **홈 페이지 URL** 및 **리디렉션 URL**에 대한 값을 계속 입력합니다. **리디렉션 URL**은 임의의 올바른 URL로 작동하며 사용자가 만든 애플리케이션과 일치해야 합니다. **네이티브**를 선택한 경우 6단계를 계속 진행합니다.

6. 애플리케이션에 필요한 Power BI API를 선택합니다. Power BI 액세스 권한에 대한 자세한 내용은 [Power BI 사용 권한](power-bi-permissions.md)을 참조하세요. 그런 다음, **등록**을 선택합니다.

    ![등록할 API 선택](media/register-app/register-app-new-app-registration-apis-register.png)

    > [!Important]
    > 서비스 주체를 Power BI와 함께 사용하도록 설정하면 Azure Active Directory 사용 권한이 더 이상 적용되지 않습니다. 사용 권한은 Power BI 관리 포털을 통해 관리됩니다.

7. 애플리케이션 유형으로 **네이티브**를 선택하면 **애플리케이션 ID**가 제공됩니다. 애플리케이션 유형으로 **서버 쪽 웹앱**을 선택하면 **애플리케이션 ID**와 **애플리케이션 암호**를 받게 됩니다.

    > [!Note]
    > **애플리케이션 ID**는 나중에 필요한 경우 Azure Portal에서 검색할 수 있습니다. **애플리케이션 암호**를 분실한 경우 Azure Portal 내에서 새로 만들어야 합니다.

| 네이티브 | 서버 쪽 웹 애플리케이션 |
|--------|-----------------------------|
| ![기본 성공](media/register-app/register-app-new-design-success-native.png) | ![서버 쪽 웹앱 성공](media/register-app/register-app-new-design-success-server-side-web-app.png) |

이제 등록된 애플리케이션을 사용자 지정 애플리케이션의 일부로 사용하여 Power BI 서비스 및 Power BI Embedded 애플리케이션과 상호 작용할 수 있습니다.

## <a name="register-with-the-azure-portal"></a>Azure Portal에 등록

애플리케이션을 등록하기 위한 다른 옵션은 Azure Portal에서 직접 수행하는 것입니다. 애플리케이션을 등록하려면 다음의 단계를 수행합니다.

1. [Microsoft Power BI API 약관](https://powerbi.microsoft.com/api-terms)에 동의합니다.

2. [Azure Portal](https://portal.azure.com)에 로그인합니다.

3. 페이지의 오른쪽 위에서 사용자 계정을 선택하여 Azure AD 테넌트를 선택합니다.

4. 왼쪽 탐색 창에서 **모든 서비스**로 이동하여 **앱 등록**을 선택한 다음, **새 등록**을 선택합니다.

5. 메시지에 따라 새 애플리케이션을 만듭니다.

   Azure Active Directory에 애플리케이션을 등록하는 방법에 대한 자세한 내용은 [Azure Active Directory에 앱 등록](https://docs.microsoft.com/azure/active-directory/develop/quickstart-v2-register-an-app)을 참조하세요.

## <a name="how-to-get-the-application-id"></a>애플리케이션 ID를 가져오는 방법

애플리케이션을 등록하면 [애플리케이션 ID](embed-sample-for-customers.md#application-id)를 받게 됩니다.  **애플리케이션 ID**는 애플리케이션이 사용자를 식별하도록 사용자에게 권한을 요청합니다.

## <a name="how-to-get-the-service-principal-object-id"></a>서비스 주체 개체 ID를 가져오는 방법

[Power BI API](https://docs.microsoft.com/rest/api/power-bi/)를 사용하는 경우 서비스 주체를 참조하기 위해 [서비스 주체 개체 ID](embed-service-principal.md#how-to-get-the-service-principal-object-id)를 사용하여 작업을 정의해야 합니다(예: 서비스 주체를 작업 영역에 관리자로 적용).

## <a name="apply-permissions-to-your-application-within-azure-ad"></a>Azure AD 에서 애플리케이션에 권한 적용

앱 등록 페이지에서 제공하는 권한 외에도 애플리케이션에 대한 추가 권한을 사용하도록 설정합니다. Azure AD 포털을 통해, 또는 프로그래밍 방식으로 이 작업을 수행할 수 있습니다.

포함에 사용된 ‘마스터’ 계정 또는 전역 관리자 계정 중 하나를 사용하여 로그인할 수 있습니다. 

### <a name="using-the-azure-ad-portal"></a>Azure AD 포털 사용

1. Azure Portal 내에서 [앱 등록](https://portal.azure.com/#blade/Microsoft_AAD_RegisteredApps/ApplicationsListBlade/quickStartType//sourceType/)으로 이동한 후 포함에 사용할 앱을 선택합니다.

2. **관리**에서 **API 권한**을 선택합니다.

3. **API 권한**에서 **권한 추가**를 선택하고 **Power BI 서비스**를 선택합니다.

    ![앱 사용 권한 03](media/register-app/powerbi-embedded-azuread-app-permissions03.png)

4. **위임된 권한**에서 필요한 특정 권한을 선택합니다. 선택 항목을 저장하려면 하나씩 선택합니다. 완료되면 **저장**을 선택합니다.

5. **동의 허용**을 선택합니다.

    Azure AD에서 동의하도록 요구하는 메시지가 표시되지 않게 하려면 *마스터 계정*에 **동의 허용** 작업이 필요합니다. 이 작업을 수행하는 계정이 전역 관리자인 경우, 조직 내 모든 사용자에게 이 애플리케이션에 대한 권한을 부여합니다. 이 작업을 수행하는 계정이 *마스터 계정*이고 글로벌 관리자가 아닌 경우, 이 애플리케이션의 *마스터 계정*에만 권한을 부여합니다.

### <a name="applying-permissions-programmatically"></a>프로그래밍 방식으로 권한 적용

1. 테넌트 내에서 기존 서비스 주체(사용자)를 가져와야 합니다. 이 작업을 수행하는 방법에 대한 자세한 내용은 [servicePrincipal](https://docs.microsoft.com/graph/api/resources/serviceprincipal?view=graph-rest-beta)을 참조하세요.

    {ID} 없이 *Get servicePrincipal* API를 호출하면 테넌트 내의 모든 서비스 주체를 가져옵니다.

2. **appId** 속성으로 앱 애플리케이션 ID가 있는 서비스 주체를 확인합니다.

3. 앱에서 누락된 경우 새 서비스 계획을 만듭니다.

    ```json
    Post https://graph.microsoft.com/beta/servicePrincipals
    Authorization: Bearer ey..qw
    Content-Type: application/json
    {
    "accountEnabled" : true,
    "appId" : "{App_Client_ID}",
    "displayName" : "{App_DisplayName}"
    }
    ```

4. Power BI API에 앱 권한 부여

   기존 테넌트를 사용하고 있고 모든 테넌트 사용자를 대신하여 권한을 부여하는 데 관심이 없는 경우 **contentType**의 값을 **Principal**로 바꾸면 특정 사용자에게 권한을 부여할 수 있습니다.

   **consentType**의 값은 **AllPrincipals** 또는 **Principal** 중 하나를 제공할 수 있습니다.

   * **AllPrincipals**는 테넌트 관리자가 테넌트의 모든 사용자를 대신하여 권한을 부여하는 데만 사용할 수 있습니다.
   * **Principal**은 특정 사용자를 대신하여 권한을 부여하는 데 사용됩니다. 이 경우 요청 본문에 추가 속성을 추가해야 합니다(*principalId = {User_ObjectId}* ).

     비대화형 로그인을 수행할 때 불가능한 Azure AD의 동의 요청을 피하기 위해 마스터 계정에 *사용 권한을 부여*해야 합니다.

     ```json
     Post https://graph.microsoft.com/beta/OAuth2PermissionGrants
     Authorization: Bearer ey..qw
     Content-Type: application/json
     {
     "clientId":"{Service_Plan_ID}",
     "consentType":"AllPrincipals",
     "resourceId":"c78a3685-1ce7-52cd-95f7-dc5aea8ec98e",
     "scope":"Dataset.ReadWrite.All Dashboard.Read.All Report.Read.All Group.Read Group.Read.All Content.Create Metadata.View_Any Dataset.Read.All Data.Alter_Any",
     "expiryTime":"2018-03-29T14:35:32.4943409+03:00",
     "startTime":"2017-03-29T14:35:32.4933413+03:00"
     }
     ```

    **resourceId** *c78a3685-1ce7-52cd-95f7-dc5aea8ec98e*는 범용이지 않지만 테넌트 종속입니다. 이 값은 AAD(Azure Active Directory) 테넌트에서 “Power BI Service” 애플리케이션의 objectId입니다.

    사용자는 Azure Portal에서 이 값을 신속하게 가져올 수 있습니다.
    1. https://portal.azure.com/#blade/Microsoft_AAD_IAM/StartboardApplicationsMenuBlade/AllApps

    2. 검색 상자에서 "Power BI 서비스" 검색

5. AAD(Azure Active Directory)에 앱 사용 권한 부여

   **consentType**의 값은 **AllPrincipals** 또는 **Principal** 중 하나를 제공할 수 있습니다.

   * **AllPrincipals**는 테넌트 관리자가 테넌트의 모든 사용자에게 권한을 부여하는 데만 사용할 수 있습니다.
   * **Principal**은 특정 사용자에게 권한을 부여하는 데 사용됩니다. 이 경우 요청 본문에 추가 속성을 추가해야 합니다(*principalId = {User_ObjectId}* ).

   비대화형 로그인을 수행할 때 불가능한 Azure AD의 동의 요청을 피하기 위해 마스터 계정에 *사용 권한을 부여*해야 합니다.

   ```json
   Post https://graph.microsoft.com/beta/OAuth2PermissionGrants
   Authorization: Bearer ey..qw
   Content-Type: application/json
   { 
   "clientId":"{Service_Plan_ID}",
   "consentType":"AllPrincipals",
   "resourceId":"61e57743-d5cf-41ba-bd1a-2b381390a3f1",
   "scope":"User.Read Directory.AccessAsUser.All",
   "expiryTime":"2018-03-29T14:35:32.4943409+03:00",
   "startTime":"2017-03-29T14:35:32.4933413+03:00"
   }
   ```

## <a name="next-steps"></a>다음 단계

이제 Azure AD에서 애플리케이션을 등록했으므로 애플리케이션 내에서 사용자를 인증해야 합니다. 자세한 내용은 [사용자 인증 및 Power BI 앱에 대한 Azure AD 액세스 토큰 가져오기](get-azuread-access-token.md)를 살펴보세요.

궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](https://community.powerbi.com/)