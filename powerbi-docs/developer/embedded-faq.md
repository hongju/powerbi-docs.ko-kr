---
title: Power BI Embedded에 대한 질문과 대답
description: Power BI Embedded에 대한 질문과 대답 목록을 찾아보세요.
author: rkarlin
ms.author: rkarlin
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 05/27/2019
ms.openlocfilehash: 81eb5de3294430c3960502700bb6255aea43f91a
ms.sourcegitcommit: 8cc2b7510aae76c0334df6f495752e143a5851c4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/01/2019
ms.locfileid: "73429282"
---
# <a name="frequently-asked-questions-about-power-bi-embedded"></a>Power BI Embedded에 대한 질문과 대답

* 다른 질문이 있는 경우 [Power BI 커뮤니티에 질문합니다](http://community.powerbi.com/).
* 여전히 문제가 있나요? [Power BI 지원 페이지](https://powerbi.microsoft.com/support/)를 방문하세요.

## <a name="general"></a>일반

### <a name="what-is-power-bi-embedded"></a>Power BI Embedded는 무엇입니까?

[Microsoft PBIE(Power BI Embedded)](azure-pbie-what-is-power-bi-embedded.md)를 사용하면 애플리케이션 개발자가 데이터 시각화를 직접 만들고 컨트롤을 처음부터 새로 빌드하지 않고도 멋진 대화형 보고서를 애플리케이션에 포함할 수 있습니다.

### <a name="who-is-the-target-audience-for-power-bi-embedded"></a>Power BI Embedded의 대상 그룹은 누구입니까?

애플리케이션을 코딩하는, ISV(독립 소프트웨어 공급업체)라고도 하는 소프트웨어 회사 및 개발자입니다.

### <a name="how-is-power-bi-embedded-different-from-power-bi-the-service"></a>Power BI Embedded는 Power BI 서비스와 어떤 차이가 있습니까?

Power BI는 조직의 가장 중요한 비즈니스 데이터의 단일 보기를 제공하는 SaaS(Software as a Service) 분석 솔루션입니다.

Microsoft는 고객이 분석적 의사 결정을 내리는 데 참고할 수 있는 시각적 개체를 애플리케이션에 포함시킬 수 있도록 ISV용 Power BI Embedded를 개발했습니다. 따라서, ISV가 자체 분석 솔루션을 직접 빌드하지 않아도 됩니다. 비즈니스 사용자는 [임베디드 분석](embedding.md)을 사용하여 비즈니스 데이터에 액세스하고 그에 대한 쿼리를 실행하여 애플리케이션 내에서 인사이트를 생성할 수 있습니다.


### <a name="what-is-the-difference-between-power-bi-premium-and-power-bi-embedded"></a>Power BI Premium과 Power BI Embedded의 차이점은 무엇인가요?

Power BI Premium은 조직, 파트너, 고객 및 공급업체에 대한 단일 보기를 제공하는 완전한 BI 솔루션을 원하는 기업 고객을 위한 용량입니다. Power BI Premium은 조직의 의사 결정을 도와줍니다. Power BI Premium은 사용자가 모바일 앱, 내부 개발 앱 또는 Power BI 포털을 통해 콘텐츠를 사용할 수 있는 SaaS 제품입니다.

Power BI Embedded는 애플리케이션에 시각적 개체를 포함하려는 ISV를 위한 제품입니다. Power BI Embedded는 고객의 의사 결정에 도움을 줍니다. 왜냐하면 Power BI Embedded는 애플리케이션 개발자를 위한 용량이며 해당 애플리케이션 고객은 조직 내부 또는 외부의 아무 사용자를 포함하여 Power BI Embedded 용량에 저장된 콘텐츠를 사용할 수 있기 때문입니다. Power BI Embedded 용량 콘텐츠는 한 번 클릭으로 웹에 게시하거나 한 번 클릭으로 SharePoint에 게시할 수 없습니다.

### <a name="what-is-the-microsoft-recommendation-for-when-a-customer-should-buy-power-bi-premium-vs-power-bi-embedded"></a>고객이 Power BI Premium 또는 Power BI Embedded 중에 하나를 구매해야 하는 경우 Microsoft에서는 무엇을 추천하나요?

기업은 엔터프라이즈급 셀프 서비스 클라우드 BI 솔루션인 Power BI Premium을 구입하는 것이 좋습니다. ISV는 클라우드 기반 임베디드 분석 구성 요소를 위한 Power BI Embedded를 구입하는 것이 좋습니다. 하지만 고객이 구매할 수 있는 제품에는 제한이 없습니다.

앱 포함 외에도, ISV(일반적으로 대규모)가 P SKU를 사용하여 조직 내에서 사전 패키지 Power BI 서비스의 추가 이점을 누리려는 경우가 있습니다. LOB(기간 업무) 애플리케이션을 빌드하고 분석 기능을 포함하는 데에만 관심이 있고 사전 패키지 Power BI 서비스에는 관심이 없는 일부 기업은 Azure에서 SKU를 사용할 수 있습니다.

### <a name="how-many-embed-tokens-can-i-create"></a>얼마나 많은 포함 토큰을 만들 수 있습니까?

PRO 라이선스가 있는 포함 토큰은 개발 테스트용이므로 Power BI 마스터 계정 또는 [서비스 주체](embed-service-principal.md)는 제한된 수의 토큰만 생성할 수 있습니다. 프로덕션 환경에 포함하려면 [용량을 구입](#technical)합니다. 용량 구입 시 생성할 수 있는 포함 토큰 수에는 제한이 없습니다. [사용 가능한 기능](https://docs.microsoft.com/rest/api/power-bi/availablefeatures)으로 이동하여 현재 포함된 사용 현황을 백분율로 표시하는 사용 값을 확인합니다.

## <a name="technical"></a>기술

### <a name="what-is-the-difference-between-the-a-skus-in-azure-and-the-em-skus-in-office-365"></a>Azure의 A SKU와 Office 365의 EM SKU는 어떤 차이가 있나요?

PowerBI.com은 소셜 협업, 이메일 구독 및 기타 기능과 같은 다양한 기능을 갖춘 엔터프라이즈 SaaS(Software as a Service) 솔루션입니다. PowerBI.com을 사용하여 ISV는 임베디드 분석 솔루션 콘텐츠 및 테넌트 수준 설정을 관리할 수 있습니다.

Power BI Embedded는 개발자가 임베디드 분석 솔루션을 만드는 데 사용할 수 있는 PaaS(Platform as a Service) API 세트입니다.

다음은 기능 차이에 대한 일부 목록입니다.

| 특정 | Power BI Embedded | Power BI Premium 용량 | Power BI Premium 용량 |
|----------------------------------------------------------------------------------|-------------------|---------------------------|---------------------------|
|   | A SKU-Azure 용량 | EM SKU-O365 용량 | P SKU-O365 용량 |
| Power BI 작업 영역의 아티팩트 포함 | 예 | 예 | 예 |
| 포함된 애플리케이션에서 Power BI 보고서 사용 - SaaS | 아니요 | 예 | 예 |
| 포함된 애플리케이션에서 Power BI 보고서 사용 - PaaS | 예 | 예 | 예 |
| SharePoint에서 Power BI 보고서 사용 | 아니요 | 예 | 예 |
| Dynamics에서 Power BI 보고서 사용 | 아니요 | 예 | 예 |
| Teams에서 Power BI 보고서 사용(모바일 앱 제외) | 아니요 | 예 | 예 |
| Powerbi.com 및 Power BI 모바일에서 무료 Power BI 라이선스를 사용하여 콘텐츠 액세스 | 아니요 | 아니요 | 예 |
| MS Office 앱에 포함된 무료 Power BI 라이선스를 사용하여 콘텐츠에 액세스 | 아니요 | 예 | 예 |

### <a name="power-bi-now-offers-three-skus-for-embedding-a-skus-em-skus-and-p-skus-which-one-should-i-purchase-for-my-scenario"></a>Power BI는 이제 다음 세 가지 SKU를 포함할 수 있습니다. SKU, EM SKU 및 P SKU. 제 시나리오에는 어떤 용량을 구매해야 하나요?

|  |A SKU(Power BI Embedded)  |EM SKU(Power BI Premium)  |P SKU(Power BI Premium)  |
|---------|---------|---------|---------|
|구입  |Azure Portal |Office |Office |
|사용 사례 | 자체 애플리케이션에 콘텐츠 포함 | <li> 자체 애플리케이션에 콘텐츠 포함 <br><br><br> <li> MS Office 애플리케이션에 콘텐츠 포함: <br> - [SharePoint](https://powerbi.microsoft.com/blog/integrate-power-bi-reports-in-sharepoint-online/) <br> - [Teams(모바일 앱 제외)](https://powerbi.microsoft.com/blog/power-bi-teams-up-with-microsoft-teams/) <br> - [Dynamics 365](https://docs.microsoft.com/dynamics365/customer-engagement/basics/add-edit-power-bi-visualizations-dashboard) | <li> 자체 애플리케이션에 콘텐츠 포함 <br><br><br> <li> MS Office 애플리케이션에 콘텐츠 포함: <br> - [SharePoint](https://powerbi.microsoft.com/blog/integrate-power-bi-reports-in-sharepoint-online/) <br> - [Teams(모바일 앱 제외)](https://powerbi.microsoft.com/blog/power-bi-teams-up-with-microsoft-teams/) <br> - [Dynamics 365](https://docs.microsoft.com/dynamics365/customer-engagement/basics/add-edit-power-bi-visualizations-dashboard) <br><br><br> <li> [Power BI 서비스](https://powerbi.microsoft.com/)를 통해 Power BI 사용자와 콘텐츠 공유  |
|청구 |시간별 |매월 |매월 |
|약정  |약정 없음 |매년  |매월/매년 |
|차별화 |탁월한 탄력성 - Azure Portal에서 또는 API를 통해 리소스를 강화/규모 축소, 일시 중지/다시 시작 가능  |SharePoint Online 및 Microsoft Teams(모바일 앱 제외)에 콘텐츠를 포함하는 데 사용할 수 있습니다. |애플리케이션에 포함 및 Power BI 서비스 사용을 동일한 용량에 결합 |

### <a name="what-are-the-prerequisites-to-create-a-pbie-capacity-in-azure"></a>Azure에서 PBIE 용량을 만드는 필수 구성 요소는 무엇입니까?

* 조직 디렉터리에 로그인합니다(Microsoft 계정은 지원되지 않음).
* Power BI 테넌트가 있어야 합니다. 즉, 디렉터리에 있는 한 명 이상의 사용자가 Power BI에 가입되어 있어야 합니다. 
* 조직 디렉토리에 Azure 구독이 있어야 합니다.

### <a name="how-can-i-monitor-power-bi-embedded-capacity-consumption"></a>Power BI Embedded 용량 소비를 모니터링하려면 어떻게 하나요?

* [Power BI 관리 포털](../service-admin-portal.md#power-bi-embedded) 사용

* Power BI에서 [메트릭 앱](https://docs.microsoft.com/power-bi/service-admin-premium-monitor-capacity) 다운로드

* [Azure 진단 로깅](azure-pbie-diag-logs.md) 사용

### <a name="can-my-capacity-scale-automatically-to-adjust-to-my-app-consumption"></a>내 앱 소비량에 맞게 용량이 자동으로 조정될 수 있나요?

아직은 자동 크기 조정 기능이 없지만, 언제든지 조정할 수 있도록 모든 API가 제공됩니다.

### <a name="why-creatingscalingresuming-a-capacity-results-in-putting-the-capacity-into-a-suspended-state"></a>용량을 만들기/크기 조정/다시 시작하면 용량을 일시 중단된 상태로 전환하는 이유는 무엇인가요?

용량 프로비저닝(확장/다시 시작/만들기)에 실패할 수 있습니다. Get Details API를 사용하여 용량의 ProvisioningState를 확인할 수 있습니다. [용량 - 세부 정보 가져오기](https://docs.microsoft.com/rest/api/power-bi-embedded/capacities/getdetails).

### <a name="can-i-only-create-power-bi-embedded-capacities-in-a-specific-region"></a>특정 지역에서만 Power BI Embedded 용량을 만들 수 있나요?

[다중 지역 (미리 보기)](embedded-multi-geo.md) 기능을 사용하면 Power BI 홈 테넌트 위치가 아닌 다른 지역에서 [Power BI Embedded 용량](azure-pbie-create-capacity.md)을 구매할 수 있습니다.

### <a name="why-cant-i-see-a-workspace-although-i-have-permissions"></a>권한이 있는데 작업 영역을 볼 수 없는 이유는 무엇인가요?

작업 영역, 앱 또는 아티팩트에 대한 권한이 사용자에게 부여되더라도 API 호출을 통해 즉시 사용하지 못할 수도 있습니다.
결과는 'GET' API 응답에서 아티팩트가 누락되거나 아티팩트를 사용하려고 할 때 오류가 발생할 수 있습니다.
사용자는 [refreshUserPermissions API](https://docs.microsoft.com/rest/api/power-bi/users/refreshuserpermissions)를 호출하여 이 문제를 해결할 수 있습니다. 이 API는 사용자 권한을 업데이트합니다.


### <a name="how-can-i-find-my-pbi-tenant-region"></a>내 PBI 테넌트 지역을 어떻게 찾을 수 있나요?

PBI 포털을 사용하여 PBI 테넌트 지역을 찾을 수 있습니다.

[https://app.powerbi.com/](https://app.powerbi.com/) > ? > Power BI 정보

![Power BI 정보](media/embedded-faq/about-01.png)
![테넌트 지역](media/embedded-faq/tenant-location-01.png)

### <a name="what-does-the-cloud-solution-provider-csp-channel-support"></a>CSP(클라우드 솔루션 공급자) 채널은 무엇을 지원하나요?

* 구독 형식 CSP를 사용하여 테넌트에 대한 PBIE를 만들 수 있습니다.
* 파트너 계정은 고객 테넌트에 로그인하고 고객 테넌트에 대한 PBIE를 구매하여 고객 테넌트 사용자를 Power BI 용량 관리자로 지정합니다.

### <a name="why-do-i-get-an-unsupported-account-message"></a>지원되지 않는 계정 메시지를 받은 이유는 무엇인가요?

Power BI에서는 조직 계정에 등록해야 합니다. Microsoft 계정을 사용하여 Power BI에 등록하는 기능은 지원되지 않습니다.

### <a name="can-i-use-apis-to-create-and-manage-azure-capacities"></a>API를 사용하여 Azure 용량을 만들고 관리할 수 있나요?

예, PBIE 리소스를 만들고 관리하는 데 사용할 수 있는 PowerShell cmdlet 및 Azure Resource Manager REST API가 있습니다.

* [Rest API](https://docs.microsoft.com/rest/api/power-bi-embedded/) 
* [Powershell cmdlet](https://docs.microsoft.com/powershell/module/azurerm.powerbiembedded/)

### <a name="what-is-the-pbi-embedded-dedicated-capacity-role-in-a-pbi-embedded-solution"></a>PBI Embedded 솔루션에 포함된 PBI Embedded 전용 용량 역할이란?

[솔루션 수준을 프로덕션으로 올리려면](embed-sample-for-customers.md#move-to-production) 애플리케이션에서 사용되는 Power BI 콘텐츠(작업 영역)를 Power BI Embedded(SKU) 용량에 할당해야 합니다.

### <a name="in-what-azure-regions-is-pbi-embedded-available"></a>PBI Embedded는 어떤 Azure 지역에서 사용할 수 있나요?

[PAM](https://ecosystemmanager.azurewebsites.net/home)(EcoManager) - 제품 가용성 관리자를 참조하세요.

사용 가능한 지역(Power BI와 동일한 16개 지역)

* 미국(6) - 미국 동부, 미국 동부 2, 미국 중북부, 미국 중남부, 미국 서부, 미국 서부 2
* 유럽(2) - 유럽 북부, 유럽 서부
* 아시아 태평양(2) - 동남 아시아, 동아시아
* 브라질(1) - 브라질 남부
* 일본(1) - 일본 동부
* 오스트레일리아(1) - 오스트레일리아 남동부
* 인도(1) - 인도 서부
* 캐나다(1) - 캐나다 중부
* 영국(1) - 영국 남부

### <a name="what-is-power-bi-embeddeds-authentication-model"></a>Power BI Embedded의 인증 모델은 무엇인가요?

Power BI Embedded는 마스터 사용자 인증(지정된 Power BI Pro 라이선스 사용자)을 위해 Azure AD를 계속 사용하거나 Power BI 내에서 애플리케이션을 인증하기 위해 [서비스 주체](embed-service-principal.md)와 함께 사용합니다.  

 ISV는 자체 애플리케이션에 대한 자체 인증 및 권한 부여를 구현할 수 있습니다.

Azure AD 테넌트가 이미 있는 경우 기존 디렉터리를 사용할 수 있습니다. 포함된 애플리케이션 콘텐츠 보안을 위해 새로운 Azure AD 테넌트를 만들 수도 있습니다.

AAD 토큰을 가져오려면 [Azure Active Directory 인증 라이브러리](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-libraries) 중 하나를 사용할 수 있습니다. 여러 플랫폼에서 사용할 수 있는 클라이언트 라이브러리가 있습니다.

### <a name="my-application-already-uses-aad-for-user-authentication-how-can-we-use-this-identity-when-authenticating-to-power-bi-in-a-user-owns-data-scenario"></a>내 애플리케이션은 사용자 인증에 이미 AAD를 사용합니다. "사용자 소유 데이터" 시나리오에서 Power BI에 인증할 때 이 ID를 사용하려면 어떻게 하나요?

표준 OAuth On-Behalf-Of 흐름입니다(<https://docs.microsoft.com/azure/active-directory/develop/web-api>). Power BI 서비스(필요한 범위 포함) 사용 권한이 필요하도록 애플리케이션을 구성해야 합니다. 앱에 대한 사용자 토큰이 있으면 간단히 사용자 액세스 토큰을 사용하여 ADAL API AcquireTokenAsync를 호출하고 Power BI 리소스 URL을 리소스 ID로 지정합니다.

```csharp
var context = new AD.AuthenticationContext(authorityUrl);
var userAssertion = new AD.UserAssertion(userAccessToken);
var clientAssertion = new AD.ClientAssertionCertificate(MyAppId, MyAppCertificate)
var authenticationResult = await context.AcquireTokenAsync(resourceId, clientAssertion, userAssertion);
```

### <a name="what-object-id-is-the-service-principal-object-id"></a>어떤 개체 ID가 서비스 주체 개체 ID인가요?

등록된 앱의 주 화면에 있는 *개체 ID*는 앱에 대한 개체 ID입니다.

*로컬 디렉터리의 관리형 애플리케이션 > 속성* 섹션에 있는 개체 ID가 사용해야 하는 서비스 주체 개체 ID입니다. 이 개체 ID는 작업에 대한 서비스 주체를 참조하거나 서비스 주체 개체 ID를 변경하는 데 사용됩니다. 예를 들면 서비스 주체를 작업 영역에 관리자로 적용하는 경우입니다.

### <a name="how-is-power-bi-embedded-different-from-other-azure-services"></a>Power BI Embedded는 다른 Azure 서비스와 어떤 차이가 있나요?

Azure에서 Power BI Embedded를 구매하려면 그 전에 Power BI 계정이 있어야 합니다. Power BI Embedded 배포 지역에 따라 Power BI 계정이 결정됩니다. Azure에서 Power BI Embedded 리소스를 관리하여 다음 작업을 수행할 수 있습니다.

* 강화/규모 축소
* 용량 관리자 추가
* 서비스 일시 중지/다시 시작

PowerBI.com을 사용하여 Power BI Embedded 용량에 작업 영역을 할당/할당 취소.

### <a name="what-content-pack-data-types-can-you-embed"></a>어떤 콘텐츠 팩 데이터 형식을 포함할 수 있나요?

콘텐츠 팩 데이터 세트에서 만든 **대시보드** 및 **타일**은 포함할 수 없습니다. 단, 콘텐츠 팩 데이터 세트에서 만든 **보고서**는 포함할 수 있습니다.

### <a name="what-is-the-difference-between-using-row-level-security-rls-vs-javascript-filters"></a>RLS(행 수준 보안)를 사용하는 것과 JavaScript 필터를 사용하는 차이는 무엇인가요?

RLS와 JavaScript 필터를 사용할 때 혼란이 있는 경우가 종종 있습니다. 한 가지 방법은 특정 사용자가 볼 수 있는 것을 제어하는 것이고 다른 방법은 사용자의보기를 최적화하는 것입니다.

RLS의 경우 ISV 개발자는 모델 및 포함 토큰 생성의 일부로 데이터 필터링을 제어합니다. 최종 사용자는 ISV가 사용자에게 보도록 허용한 내용만 볼 수 있습니다. 이 경우 사용자는 필터링되는 것보다 적은 내용을 볼 수 있지만, RLS 구성을 무시하고 허용되는 것보다 더 많은 내용을 볼 수는 없습니다.

클라이언트 쪽 필터링(JavaScript)의 경우 최종 사용자에게 초기 보기에 표시되는 내용을 ISV가 결정할 수 있지만, 최종 사용자가 보기 자체에 적용할 수 있는 변경 사항은 제어할 수 없습니다. 사용자 Javascript 클라이언트 코드가 백 엔드에서 데이터 필터링을 트리거할 수 있기 때문에 안전하다고 간주할 수 없습니다.

자세한 내용은 [RLS 대 JavaScript 필터](embedded-row-level-security.md#using-rls-vs-javascript-filters)를 참조하세요.

### <a name="how-do-i-manage-permissions-for-service-principals-with-power-bi"></a>Power BI를 사용하여 서비스 주체에 대한 사용 권한을 관리하려면 어떻게 해야 하나요?

[서비스 주체](embed-service-principal.md)가 Power BI를 사용하도록 설정하면 애플리케이션의 AD 사용 권한이 더 이상 적용되지 않습니다. 애플리케이션 사용 권한은 Power BI 관리 포털을 통해 관리됩니다.

서비스 주체는 해당 보안 그룹의 모든 Power BI 테넌트 설정에 대한 사용 권한을 상속받습니다. 사용 권한을 제한하려면 서비스 주체에 대한 전용 보안 그룹을 만들어서, 활성화된 해당 Power BI 설정에 대한 **특정 보안 그룹 제외** 목록에 추가합니다.

이 경우는 서비스 주체를 **관리자**로 새 작업 영역에 추가할 때 중요합니다. 이 작업은 [API](https://docs.microsoft.com/rest/api/power-bi/groups/addgroupuser) 또는 Power BI 서비스를 통해 관리할 수 있습니다.

### <a name="when-to-use-an-application-id-vs-a-service-principal-object-id"></a>애플리케이션 ID 및 서비스 주체 개체 ID를 사용하는 시기는?

**[애플리케이션 ID](embed-sample-for-customers.md#application-id)** 는 인증을 위해 애플리케이션 ID를 전달할 때 액세스 토큰을 만드는 데 사용됩니다.

작업을 위해 서비스 주체를 참조하거나 변경하려면 **[서비스 주체 개체 ID](embed-service-principal.md#how-to-get-the-service-principal-object-id)** 를 사용합니다(예: 서비스 주체를 작업 영역에 관리자로 적용).

### <a name="can-you-manage-an-on-premises-data-gateway-with-service-principal"></a>서비스 주체로 온-프레미스 데이터 게이트웨이를 관리할 수 있나요?

마스터 계정처럼 [서비스 주체](embed-service-principal.md)를 사용하여 온-프레미스 데이터 게이트웨이(데이터 게이트웨이)를 관리할 수 없습니다.

마스터 계정을 사용하여 게이트웨이를 설치하고, 사용자를 게이트웨이에 추가하고, 데이터 원본에 연결하고, 기타 관리 작업을 수행할 수 있습니다.

서비스 주체를 사용하면 SSAS(SQL Server Analysis Services) 온-프레미스 라이브 연결 데이터 원본을 통해 [RLS(행 수준 보안)](embedded-row-level-security.md#on-premises-data-gateway-with-service-principal)를 구성할 수 있습니다. 이러한 방식으로 서비스 주체를 사용하여 **Power BI Embedded**와 통합할 때 SSAS에서 사용자와 데이터 액세스를 관리할 수 있습니다.

### <a name="can-you-sign-into-the-power-bi-service-with-service-principal"></a>서비스 주체를 사용하여 Power BI 서비스에 로그인할 수 있나요?

아니요 - 서비스 주체를 사용하여 Power BI에 로그인할 수 없습니다.

또한 포함 토큰을 생성할 때만 외부 애플리케이션(SaaS 포함)의 사용자로 콘텐츠를 사용할 수 없습니다.

### <a name="what-are-the-best-practices-to-improve-performance"></a>성능을 개선하기 위한 모범 사례는 무엇인가요?

[Power BI Embedded 성능](embedded-performance-best-practices.md)

## <a name="licensing"></a>라이선싱

### <a name="how-do-i-purchase-power-bi-embedded"></a>Power BI Embedded를 구매하려면 어떻게 하나요?

Power BI Embedded는 Azure를 통해 제공됩니다.

### <a name="what-happens-if-i-already-purchased-power-bi-premium-and-now-i-want-some-power-bi-embedded-in-azure-benefits"></a>Power BI Premium을 이미 구입했는데 Azure 혜택으로 일부 Power BI Embedded를 사용하려면 어떻게 해야 하나요?

고객은 현재 계약 기간이 종료될 때까지는 기존에 구매한 Power BI Premium 요금을 계속 지불한 다음, 그 시점에, 필요에 따라 Power BI Premium 구매를 전환할 수 있습니다.

### <a name="do-i-still-have-to-buy-power-bi-premium-to-get-access-to-power-bi-embedded"></a>Power BI Embedded에 액세스하려면 Power BI Premium을 구매해야 하나요?

아니요, Power BI Embedded는 고객에게 솔루션을 배포해야 하는 Azure 기반 용량을 포함하고 있습니다.

### <a name="whats-the-purchase-commitment-for-power-bi-embedded"></a>Power BI Embedded의 구매 약정은 어떻게 되나요?

고객은 시간 단위로 사용량을 변경할 수 있습니다. Power BI Embedded 서비스는 월별 또는 연간 약정이 없습니다.

### <a name="how-does-the-usage-of-power-bi-embedded-show-up-on-my-bill"></a>청구서에 Power BI Embedded 사용량이 어떻게 표시되나요?

Power BI Embedded는 배포된 노드 유형을 기반으로 예측 가능한 시간당 요금이 청구됩니다. 사용량 없더라도 리소스가 활성화되어 있는 한 요금이 청구됩니다. 청구를 중지하려면 리소스를 일시 중지해야 합니다.

### <a name="who-needs-a-power-bi-pro-license-for-power-bi-embedded-and-why"></a>Power BI Embedded에 Power BI Pro 라이선스가 필요한 사람은 누구이고 그 이유는 무엇인가요?

REST API를 사용하려면 Power BI Pro 라이선스나 [서비스 주체](embed-service-principal.md)가 필요합니다. Power BI 작업 영역에 보고서를 추가하려면, 분석가에게 Power BI Pro 라이선스나 서비스 주체가 필요합니다. Power BI 테넌트 및 용량을 관리하려면 관리자에게 Power BI Pro 라이선스가 있어야 합니다.

Power BI Embedded는 Power BI 포털을 사용하여 포함된 콘텐츠를 관리하고 유효성을 검증할 수 있으므로, 올바른 리포지토리의 보고서에 액세스할 수 있도록 PowerBI.com 내에서 앱을 인증하려면 Power BI Pro 라이선스가 필요 합니다.

그러나 애플리케이션 내의 [포함된 보고서 만들기/편집](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Create-Report-in-Embed-View)의 경우 최종 사용자가 Power BI 사용자일 필요가 없으므로 Pro 라이선스가 필요하지 않습니다.

### <a name="can-i-get-started-for-free"></a>무료로 시작할 수 있나요?

예, Power BI Embedded에 [Azure 크레딧](https://azure.microsoft.com/free/)을 사용할 수 있습니다.

### <a name="can-i-get-a-trial-experience-for-power-bi-embedded-in-azure"></a>Azure에서 Power BI Embedded 평가판을 받을 수 있나요?

Power BI Embedded는 Azure의 일부이기 때문에 [Azure에 등록할 때 받은 $200 크레딧](https://azure.microsoft.com/free/)으로 서비스를 사용할 수 있습니다.

### <a name="is-power-bi-embedded-available-for-national-clouds-us-government-germany-china"></a>내셔널 클라우드(미국 정부, 독일, 중국)에 Power BI Embedded를 사용할 수 있나요?

Power BI Embedded는 [내셔널 클라우드](embed-sample-for-customers-national-clouds.md)에서도 사용할 수 있습니다.

### <a name="is-power-bi-embedded-available-for-non-profits-and-educational"></a>교육 기관 및 비영리 단체도 Power BI Embedded를 사용할 수 있나요?

교육 기관 및 비영리 단체를 위한 특별한 Azure 가격 책정은 없습니다.

## <a name="power-bi-workspace-collection"></a>Power BI 작업 영역 컬렉션

### <a name="what-is-power-bi-workspace-collection"></a>Power BI 작업 영역 컬렉션이란?

**Power BI 작업 영역 컬렉션**(** Power BI Embedded** 버전 1)은 **Power BI 작업 영역 컬렉션** Azure 리소스에 기반한 솔루션입니다. 이 솔루션을 사용하면 애플리케이션을 Power BI에 대해 인증하는 데 **Power BI 작업 영역 컬렉션** 솔루션의 Power BI 콘텐츠, 전용 API 및 작업 영역 컬렉션 키를 사용하는 고객의 **Power BI Embedded** 애플리케이션을 만들 수 있습니다.

### <a name="can-i-migrate-from-power-bi-workspace-collection-to-power-bi-embedded"></a>Power BI 작업 영역 컬렉션에서 Power BI Embedded로 마이그레이션할 수 있나요?

1. 마이그레이션 도구를 사용하여 **Power BI 작업 영역 컬렉션** 콘텐츠를 Power BI - https://docs.microsoft.com/power-bi/developer/migrate-from-powerbi-embedded#content-migration에 복제할 수 있습니다.

2. Power BI 콘텐츠를 사용하는 **Power BI Embedded** 애플리케이션 POC를 시작합니다.

3. 프로덕션 준비가 되면 **Power BI Embedded** 전용 용량을 구매하고 해당 용량에 Power BI 콘텐츠(작업 영역)를 할당합니다.

    > [!Note]
    > **Power BI Embedded** 솔루션과 병렬로 빌드하는 동안 **Power BI 작업 영역 컬렉션**을 계속 사용할 수 있습니다. 준비가 되면 고객을 새 **Power BI Embedded** 솔루션으로 이동하고 **Power BI 작업 영역 컬렉션** 솔루션을 사용 중지할 수 있습니다.

자세한 내용은 [Power BI 작업 영역 컬렉션 콘텐츠를 Power BI Embedded로 마이그레이션하는 방법](https://docs.microsoft.com/power-bi/developer/migrate-from-powerbi-embedded)을 참조하세요.

### <a name="is-power-bi-workspace-collection-on-a-deprecation-path"></a>Power BI 작업 영역 컬렉션이 사용 중단 경로에 있나요?

예. 단, **Power BI 작업 영역 컬렉션** 솔루션을 이미 사용하고 있는 고객은 사용 중단될 때까지 계속 사용할 수 있습니다. 고객은 **Power BI 작업 영역 컬렉션** 솔루션을 사용하는 새 작업 영역 컬렉션 및 **Power BI Embedded** 애플리케이션을 만들 수도 있습니다.

하지만 **Power BI 작업 영역 컬렉션** 솔루션에 새로운 기능이 추가되지 않는다는 의미이기도 합니다. 새로운 **Power BI Embedded** 솔루션으로 마이그레이션을 계획하는 것이 좋습니다.

### <a name="when-is-power-bi-workspace-collection-support-discontinued"></a>Power BI 작업 영역 컬렉션 지원은 언제 중단되나요?

**Power BI 작업 영역 컬렉션** 솔루션을 이미 사용하고 있는 고객은 2018년 6월 말까지 또는 지원 계약이 종료될 때까지 계속 사용할 수 있습니다.

### <a name="in-what-regions-can-i-create-a-pbi-workspace-collection"></a>PBI 작업 영역 컬렉션은 어떤 지역에 만들 수 있나요?

사용 가능한 지역은 오스트레일리아 남동부, 브라질 남부, 캐나다 중부, 미국 동부 2, 일본 동부, 미국 중북부, 북유럽, 미국 중남부, 동남 아시아, 영국 남부, 유럽 서부, 인도 서부 및 미국 서부입니다.

### <a name="why-should-i-migrate-from-pbi-workspace-collection-to-power-bi-embedded"></a>PBI 작업 영역 컬렉션에서 Power BI Embedded로 마이그레이션해야 하는 이유는 무엇인가요?

일부 새로운 **Power BI Embedded** 솔루션 기능과 역량은 **Power BI 작업 영역 컬렉션**에서 수행할 수 없습니다.

일부 기능은 다음과 같습니다.
* PBI 데이터 원본은 모두 지원됩니다. **Power BI 작업 영역 컬렉션** 데이터 원본은 두 가지만 지원됩니다. 
* 질문 및 답변, 새로 고침, 책갈피, 대시보드 및 타일 포함, 사용자 지정 메뉴 등의 새로운 기능은 **Power BI Embedded** 솔루션에서만 지원됩니다.
* 용량 청구 모델입니다.

## <a name="embedding-setup-tool"></a>포함 설정 도구

### <a name="what-is-the-embedding-setup-tool"></a>포함 설정 도구란 무엇인가요?

[포함 설정 도구](https://aka.ms/embedsetup)를 사용하면 샘플 애플리케이션을 신속하게 시작하고 다운로드하여 Power BI에서 포함을 시작할 수 있습니다.

### <a name="which-solution-should-i-choose"></a>어떤 솔루션은 선택해야 하나요?

* [고객에 대한 콘텐츠를 포함하면](embedding.md#embedding-for-your-customers) Power BI에 대한 계정이 없는 사용자에게 대시보드 및 보고서를 포함하는 기능을 제공합니다. [고객에 대한 콘텐츠 포함](https://aka.ms/embedsetup/AppOwnsData) 솔루션을 실행합니다.
* [조직에 대한 콘텐츠를 포함하면](embedding.md#embedding-for-your-organization) Power BI 서비스를 확장할 수 있습니다. [조직에 대한 콘텐츠 포함](https://aka.ms/embedsetup/UserOwnsData) 솔루션을 실행합니다.

### <a name="ive-downloaded-the-sample-app-which-solution-do-i-choose"></a>샘플 앱을 다운로드했다면 어떤 솔루션을 선택해야 하나요?

**고객에 대한 콘텐츠 포함** 환경을 사용하는 경우 *PowerBI-Developer-Samples.zip* 파일을 저장하고 압축을 풉니다. 그런 다음, *PowerBI-Developer-Samples-master\App Owns Data* 폴더를 열고 *PowerBIEmbedded_AppOwnsData.sln* 파일을 실행합니다.

**조직에 대한 콘텐츠 포함** 환경을 사용하는 경우 *PowerBI-Developer-Samples.zip* 파일을 저장하고 압축을 풉니다. 그런 다음, *PowerBI-Developer-Samples-master\User Owns Data\integrate-report-web-app* 폴더를 열고, *pbi-saas-embed-report.sln* 파일을 실행합니다.

### <a name="how-can-i-edit-my-registered-application"></a>등록된 애플리케이션을 편집할 수 있는 방법

Azure AD에 등록된 애플리케이션을 편집하는 방법을 알아보려면 [빠른 시작: Azure Active Directory에서 애플리케이션 업데이트](https://docs.microsoft.com/azure/active-directory/develop/quickstart-v1-update-azure-ad-app)를 참조하세요.

### <a name="how-can-i-edit-my-power-bi-user-profile-or-data"></a>내 Power BI 사용자 프로필 또는 데이터를 편집할 수 있는 방법

[여기](https://docs.microsoft.com/power-bi/service-basic-concepts)에서 Power BI 데이터를 편집하는 방법을 알아볼 수 있습니다.

자세한 내용은 [포함된 애플리케이션 문제 해결](embedded-troubleshoot.md)을 참조하세요.

궁금한 점이 더 있나요? [Power BI 커뮤니티를 이용하세요.](http://community.powerbi.com/)
