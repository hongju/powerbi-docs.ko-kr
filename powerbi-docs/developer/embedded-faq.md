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
ms.date: 05/22/2019
ms.openlocfilehash: 1bdc31d550573b926d45776307b8fcade95f0dc0
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "66222164"
---
# <a name="frequently-asked-questions-about-power-bi-embedded"></a>Power BI Embedded에 대한 질문과 대답

* 다른 질문이 있는 경우 [Power BI 커뮤니티에 질문합니다](http://community.powerbi.com/).
* 여전히 문제가 있나요? [Power BI 지원 페이지](https://powerbi.microsoft.com/support/)를 방문하세요.

## <a name="general"></a>일반

### <a name="what-is-power-bi-embedded"></a>Power BI Embedded는 무엇입니까?

[Microsoft Power BI Embedded (PBIE)](azure-pbie-what-is-power-bi-embedded.md) 응용 프로그램 개발자가 응용 프로그램에 자체 데이터 시각화 및 컨트롤부터에서 작성 하지 않고도 뛰어난 완전 한 대화형 보고서를 포함할 수 있습니다.

### <a name="who-is-the-target-audience-for-power-bi-embedded"></a>Power BI Embedded의 대상 그룹은 누구입니까?

개발자 및 소프트웨어 회사를 라고도 독립 소프트웨어 공급 업체 (Isv)가 응용 프로그램을 코딩 합니다.

### <a name="how-is-power-bi-embedded-different-from-power-bi-the-service"></a>Power BI Embedded는 Power BI 서비스와 어떤 차이가 있습니까?

Power BI는 조직의 가장 중요한 비즈니스 데이터의 단일 보기를 제공하는 SaaS(Software as a Service) 분석 솔루션입니다.

Microsoft는 고객이 분석 결정을 내릴 수 있도록 응용 프로그램에 시각적 개체를 포함 하려는 Isv를 위한 Power BI Embedded를 개발 했습니다. 이 자체는 자체 분석 솔루션을 구축 하는 것과 Isv를 덜어줍니다. [Embedded 분석](embedding.md) 비즈니스 데이터에 액세스 하 여 응용 프로그램 내에서 인 사이트 생성에 대 한 쿼리를 실행 하는 비즈니스 사용자를 사용 하도록 설정 합니다.


### <a name="what-is-the-difference-between-power-bi-premium-and-power-bi-embedded"></a>Power BI Premium과 Power BI Embedded의 차이점은 무엇인가요?

Power BI 프리미엄은 BI 솔루션을 조직, 파트너, 고객 및 공급 업체의 단일 보기를 제공 하려는 기업에 맞게 용량입니다. Power BI Premium은 조직의 의사 결정을 도와줍니다. Power BI 프리미엄은 Power BI 포털 또는 모바일 앱을 내부적으로 개발한 앱을 통해 콘텐츠를 사용할 수 있는 SaaS 제품입니다.

Power BI Embedded는 응용 프로그램에 시각적 개체를 포함 하려는 Isv입니다. Power BI Embedded는 고객의 의사 결정에 도움을 줍니다. 왜냐하면 Power BI Embedded는 애플리케이션 개발자를 위한 용량이며 해당 애플리케이션 고객은 조직 내부 또는 외부의 아무 사용자를 포함하여 Power BI Embedded 용량에 저장된 콘텐츠를 사용할 수 있기 때문입니다. Power BI Embedded를 공유할 수 없습니다 용량은 한 번의 클릭을 통해 웹에 게시 하거나 SharePoint에 게시 한 번 클릭 합니다.

### <a name="what-is-the-microsoft-recommendation-for-when-a-customer-should-buy-power-bi-premium-vs-power-bi-embedded"></a>고객이 Power BI Premium 또는 Power BI Embedded 중에 하나를 구매해야 하는 경우 Microsoft에서는 무엇을 추천하나요?

엔터프라이즈는 엔터프라이즈급, 셀프 서비스 클라우드 BI 솔루션인 Power BI 프리미엄을 구입 하는 것이 좋습니다. Isv는 클라우드 기반의 포함 된 분석 구성 요소에 대 한 Power BI Embedded 구입 하는 것이 좋습니다. 그러나 고객에 게는 제품 구입에 대 한 제한이 없습니다.

ISV (일반적으로 대규모)에서는 앱에 포함 하는 것 외에도 여기서 P SKU를 사용 하 여 조직 내에서 사전 패키지 Power BI 서비스의 추가 이점을 누릴 수 하려는 경우도 있을 수 있습니다. LOB(기간 업무) 애플리케이션을 빌드하고 분석 기능을 포함하는 데에만 관심이 있고 사전 패키지 Power BI 서비스에는 관심이 없는 일부 기업은 Azure에서 SKU를 사용할 수 있습니다.

### <a name="how-many-embed-tokens-can-i-create"></a>얼마나 많은 포함 토큰을 만들 수 있습니까?

포함 토큰 PRO 라이선스를 사용 하 여이 Power BI 마스터 계정 하므로 개발 테스트용은 또는 [서비스 주체](embed-service-principal.md) 에서만 제한 된 수의 토큰을 생성할 수 있습니다. 프로덕션 환경에 포함하려면 [용량을 구입](#technical)합니다. 얼마나 많은 용량을 구입할 때 생성할 수 있는 토큰을 포함 하려면 제한은 없습니다. [사용 가능한 기능](https://docs.microsoft.com/rest/api/power-bi/availablefeatures)으로 이동하여 현재 포함된 사용 현황을 백분율로 표시하는 사용 값을 확인합니다.

## <a name="technical"></a>기술

### <a name="what-is-the-difference-between-the-a-skus-in-azure-and-the-em-skus-in-office-365"></a>Azure의 A SKU와 Office 365의 EM SKU는 어떤 차이가 있나요?

PowerBI.com는 소셜 공동 작업, 전자 메일 구독 및 기타 기능 같은 다양 한 기능을 사용 하 여 서비스 (SaaS) 솔루션으로 엔터프라이즈 소프트웨어입니다. PowerBI.com는 Isv가 포함 된 분석 솔루션 콘텐츠를 관리 하 고 테 넌 트 수준 설정 하는 데 도움이 됩니다.

Power BI Embedded는 포함 된 분석 솔루션을 만드는 데 사용할 Api 개발자 설정 서비스 (PaaS) 플랫폼입니다.

부분 기능 차이점 목록은 다음과 같습니다.

| 특정 | Power BI Embedded | Power BI Premium 용량 | Power BI Premium 용량 |
|----------------------------------------------------------------------------------|-------------------|---------------------------|---------------------------|
|   | (A SKU) | (EM SKU) | (P SKU) |
| Power BI 앱 작업 영역의 아티팩트 포함 | Azure 용량 | Office 365 용량 | Office 365 용량 |
| Embedded 애플리케이션에서 Power BI 보고서 사용 | 예 | 예 | 예 |
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
|차별화 |탁월한 탄력성 - Azure Portal에서 또는 API를 통해 리소스를 강화/규모 축소, 일시 중지/다시 시작 가능  |SharePoint Online 및 Microsoft Teams (모바일 앱 제외)에서 콘텐츠를 포함 하는 데 사용할 수 있습니다. |애플리케이션에 포함 및 Power BI 서비스 사용을 동일한 용량에 결합 |

### <a name="what-are-the-prerequisites-to-create-a-pbie-capacity-in-azure"></a>Azure에서 PBIE 용량을 만드는 필수 구성 요소는 무엇입니까?

* 조직 디렉토리 (Microsoft 계정은 지원 되지 않습니다)에 로그인 합니다.
* 즉, 디렉터리에 하나 이상의 사용자에 등록 하 여 Power BI, Power BI 테 넌 트가 해야 합니다. 
* 조직 디렉토리에 Azure 구독이 있어야 합니다.

### <a name="how-can-i-monitor-power-bi-embedded-capacity-consumption"></a>Power BI Embedded 용량 소비를 모니터링하려면 어떻게 하나요?

* [Power BI 관리 포털](../service-admin-portal.md#power-bi-embedded) 사용

* Power BI에서 [메트릭 앱](https://review.docs.microsoft.com/power-bi/service-admin-premium-monitor-capacity) 다운로드

* [Azure 진단 로깅](azure-pbie-diag-logs.md) 사용

### <a name="can-my-capacity-scale-automatically-to-adjust-to-my-app-consumption"></a>내 앱 사용량에 맞게 용량이 자동으로 확장할 수 있습니까?

가 더 자동 이제 크기 조정 하는 동안 모든 Api는 언제 든 지 확장을 사용할 수 있습니다.

### <a name="why-creatingscalingresuming-a-capacity-results-in-putting-the-capacity-into-a-suspended-state"></a>용량을 만들기/크기 조정/다시 시작하면 용량을 일시 중단된 상태로 전환하는 이유는 무엇인가요?

용량 프로 비전 (확장/다시 시작/만들기) 실패할 수 있습니다. 용량을 ProvisioningState를 확인 하려면 세부 정보 가져오기 API를 사용할 수 있습니다. [용량 - 세부 정보 가져오기](https://docs.microsoft.com/rest/api/power-bi-embedded/capacities/getdetails).

### <a name="can-i-only-create-power-bi-embedded-capacities-in-a-specific-region"></a>특정 지역에서만 Power BI Embedded 용량을 만들 수 있나요?

[다중 지역 (미리 보기)](embedded-multi-geo.md) 기능을 사용하면 Power BI 홈 테넌트 위치가 아닌 다른 지역에서 [Power BI Embedded 용량](azure-pbie-create-capacity.md)을 구매할 수 있습니다.

### <a name="how-can-i-find-my-pbi-tenant-region"></a>내 PBI 테 넌 트 영역을 검색 하려면 어떻게 해야 합니까?

PBI 테 넌 트 지역을 찾으려면 PBI 포털을 사용할 수 있습니다.

[https://app.powerbi.com/](https://app.powerbi.com/) > ? > Power BI 정보

![Power BI 정보](media/embedded-faq/about-01.png)
![테넌트 지역](media/embedded-faq/tenant-location-01.png)

### <a name="what-does-the-cloud-solution-provider-csp-channel-support"></a>클라우드 솔루션 공급자 (CSP) 채널을 지원 하나요?

* 구독 형식 CSP를 사용하여 테넌트에 대한 PBIE를 만들 수 있습니다.
* 파트너 계정은 고객 테넌트에 로그인하고 고객 테넌트에 대한 PBIE를 구매하여 고객 테넌트 사용자를 Power BI 용량 관리자로 지정합니다.

### <a name="why-do-i-get-an-unsupported-account-message"></a>지원되지 않는 계정 메시지를 받은 이유는 무엇인가요?

Power BI에서는 조직 계정에 등록해야 합니다. Microsoft 계정을 사용 하 여 Power BI에 등록 하는 동안 지원 되지 않습니다.

### <a name="can-i-use-apis-to-create-and-manage-azure-capacities"></a>만들고 Azure 용량 관리 Api를 사용할 수 있나요?

예, Powershell cmdlet 및 Azure Resource Manager REST Api PBIE 리소스 만들기 및 관리를 사용할 수 있습니다.

* [Rest Api](https://docs.microsoft.com/rest/api/power-bi-embedded/)
* [Powershell cmdlet](https://docs.microsoft.com/powershell/module/azurerm.powerbiembedded/)

### <a name="what-is-the-pbi-embedded-dedicated-capacity-role-in-a-pbi-embedded-solution"></a>PBI Embedded 솔루션에 포함된 PBI Embedded 전용 용량 역할이란?

하 [프로덕션에 솔루션 승격](embed-sample-for-customers.md#move-to-production), Power BI Embedded (SKU) 용량에 응용 프로그램을 사용 하는 Power BI 콘텐츠 (앱 작업 영역)을 할당 해야 합니다.

### <a name="in-what-azure-regions-is-pbi-embedded-available"></a>어떤 Azure 지역에서 PBI Embedded는 사용할 수 있습니까?

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

### <a name="what-is-power-bi-embeddeds-authentication-model"></a>Power BI Embedded의 인증 모델은 무엇입니까?

Power BI Embedded 계속 또는 마스터 사용자 (지정 된 Power BI Pro 라이선스 사용자) 인증을 위해 Azure AD를 사용 하 여 [서비스 주체](embed-service-principal.md) Power BI 내에서 응용 프로그램을 인증 합니다.  

 ISV가 자신의 인증 및 응용 프로그램에 대 한 권한 부여를 구현할 수 있습니다.

Azure AD 테 넌 트를 이미 있는 경우 기존 디렉터리를 사용할 수 있습니다. 새로 만들 수도 있습니다에 포함 된 응용 프로그램 콘텐츠 보안을 위해 Azure AD 테 넌 트입니다.

AAD 토큰을 가져오려면 [Azure Active Directory 인증 라이브러리](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-libraries) 중 하나를 사용할 수 있습니다. 여러 플랫폼에서 사용할 수 있는 클라이언트 라이브러리가 있습니다.

### <a name="my-application-already-uses-aad-for-user-authentication-how-can-we-use-this-identity-when-authenticating-to-power-bi-in-a-user-owns-data-scenario"></a>내 애플리케이션은 사용자 인증에 이미 AAD를 사용합니다. "사용자 소유 데이터" 시나리오에서 Power BI에 인증할 때 이 ID를 사용하려면 어떻게 하나요?

표준 OAuth-대신-의 흐름 것 (<https://docs.microsoft.com/azure/active-directory/develop/web-api>). Power BI 서비스 (필요한 범위) 권한이 필요 하도록 응용 프로그램을 구성 해야 합니다. 사용자 액세스를 사용 하 여 ADAL API AcquireTokenAsync를 단순히 호출 앱으로 사용자 토큰을 만든 후 토큰 및 리소스 ID로 Power BI 리소스 URL을 지정 합니다.

```csharp
var context = new AD.AuthenticationContext(authorityUrl);
var userAssertion = new AD.UserAssertion(userAccessToken);
var clientAssertion = new AD.ClientAssertionCertificate(MyAppId, MyAppCertificate)
var authenticationResult = await context.AcquireTokenAsync(resourceId, clientAssertion, userAssertion);
```

### <a name="what-object-id-is-the-service-principal-object-id"></a>어떤 개체 ID가 서비스 주체 개체 ID가?

합니다 *개체 ID* 등록 된 앱의 주 화면에서 앱에 대 한 개체 ID입니다.

ID가 있는 개체를 *로컬 디렉터리에서 응용 프로그램 관리 > 속성* 섹션은 서비스 보안 주체 개체 ID를 사용 해야 합니다. 이 개체 ID는 작업에 대 한 서비스 주체를 참조 하거나 변경 하는 서비스 주체 개체 id입니다. 같은 관리자 작업 영역에 서비스 주체를 적용 합니다.

### <a name="how-is-power-bi-embedded-different-from-other-azure-services"></a>Power BI Embedded는 다른 Azure 서비스와 어떤 차이가 있나요?

Azure에서 Power BI Embedded를 구매 하기 전에 Power BI 계정이 있어야 합니다. 에 Power BI Embedded 배포 지역은 Power BI 계정을 결정합니다. Azure에서 Power BI Embedded 리소스를 관리하여 다음 작업을 수행할 수 있습니다.

* 강화/규모 축소
* 용량 관리자 추가
* 서비스 일시 중지/다시 시작

PowerBI.com을 사용하여 Power BI Embedded 용량에 작업 영역을 할당/할당 취소.

### <a name="what-are-the-supported-deploy-regions"></a>지역 배포는 지원 되는 무엇 인가요?

오스트레일리아 남동부, 브라질 남부, 캐나다 중부, 미국 동부 2, 인도 서부, 일본 동부, 미국 중북부, 북유럽, 미국 중남부, 동남 아시아, 영국 남부, 유럽 서부, 미국 서부 및 미국 서부 2입니다.

### <a name="what-content-pack-data-types-can-you-embed"></a>콘텐츠 팩 데이터 유형을 포함할 수 있습니까?

있습니다 *없습니다* 포함 **대시보드** 하 고 **타일** 콘텐츠 팩 데이터 집합에서 작성 합니다. 그러나 있습니다 *수 있습니다* 포함할 **보고서** 콘텐츠 팩 데이터 집합에서 작성 합니다.

### <a name="what-is-the-difference-between-using-row-level-security-rls-vs-javascript-filters"></a>새로운 행 수준 보안 (RLS) vs를 사용 하 여 간의 차이입니다. 무엇인가요?

종종 둘러싼 혼란 무엇을 제어 하는 방법에 대 한 한 가지 방법은 이므로 JavaScript 필터와 RLS를 사용 하는 특정 사용자가 볼 수, 하는 경우 이며 다른 하나는 사용자의 보기를 최적화 하는 방법에 대 한 합니다.

RLS의 경우 ISV 개발자는 모델 및 포함 토큰 생성의 일부로 데이터 필터링을 제어합니다. 최종 사용자는 ISV가 사용자에게 보도록 허용한 내용만 볼 수 있습니다. 이 경우 사용자는 필터링되는 것보다 적은 내용을 볼 수 있지만, RLS 구성을 무시하고 허용되는 것보다 더 많은 내용을 볼 수는 없습니다.

클라이언트 쪽 필터링 (JavaScript), ISV는 초기 보기의 최종 사용자가 결정할 수 있지만 최종 사용자가 뷰 자체에 적용 될 수 있습니다 변경 제어 수 없습니다. 사용자는 Javascript 클라이언트 코드가 백 엔드에서 필터링 하는 데이터를 트리거할 수 있습니다, 되므로 것 없습니다 수 안전한 것으로 간주 합니다.

자세한 내용은 [RLS 대 JavaScript 필터](embedded-row-level-security.md#using-rls-vs-javascript-filters)를 참조하세요.

### <a name="how-do-i-manage-permissions-for-service-principals-with-power-bi"></a>Power BI를 사용하여 서비스 주체에 대한 사용 권한을 관리하려면 어떻게 해야 하나요?

사용 하도록 설정 하면 [서비스 주체](embed-service-principal.md) Power BI를 사용 하려면 응용 프로그램의 AD 사용 권한 적용 되지 않습니다 더 이상. 응용 프로그램 사용 권한은 Power BI 관리 포털을 통해 관리됩니다.

서비스 주체는 해당 보안 그룹의 모든 Power BI 테넌트 설정에 대한 사용 권한을 상속받습니다. 권한을 제한 하려면 서비스 주체에 대 한 전용된 보안 그룹을 만들고에 추가 합니다 **특정 보안 그룹을 제외 하 고** 관련, 사용 가능한 Power BI 설정에 대 한 목록입니다.

이 경우는 서비스 주체를 **관리자**로 새 작업 영역에 추가할 때 중요합니다. 이 작업은 [API](https://docs.microsoft.com/rest/api/power-bi/groups/addgroupuser) 또는 Power BI 서비스를 통해 관리할 수 있습니다.

### <a name="when-to-use-an-application-id-vs-a-service-principal-object-id"></a>응용 프로그램 ID 및 서비스 주체 개체 ID를 사용하는 시기는?

**[응용 프로그램 ID](embed-sample-for-customers.md#application-id)** 는 인증을 위해 응용 프로그램 ID를 전달할 때 액세스 토큰을 만드는 데 사용됩니다.

작업을 위해 서비스 주체를 참조하거나 변경하려면 **[서비스 주체 개체 ID](embed-service-principal.md#how-to-get-the-service-principal-object-id)** 를 사용합니다(예: 서비스 주체를 작업 영역에 관리자로 적용).

### <a name="can-you-manage-an-on-premises-data-gateway-with-service-principal"></a>서비스 주체로 온-프레미스 데이터 게이트웨이를 관리할 수 있나요?

마스터 계정처럼 [서비스 주체](embed-service-principal.md)를 사용하여 온-프레미스 데이터 게이트웨이(데이터 게이트웨이)를 관리할 수 없습니다.

마스터 계정을 사용하여 게이트웨이를 설치하고, 사용자를 게이트웨이에 추가하고, 데이터 원본에 연결하고, 기타 관리 작업을 수행할 수 있습니다.

서비스 주체를 사용하면 SSAS(SQL Server Analysis Services) 온-프레미스 라이브 연결 데이터 원본을 통해 [RLS(행 수준 보안)](embedded-row-level-security.md#on-premises-data-gateway-with-service-principal-preview)를 구성할 수 있습니다. 이러한 방식으로 서비스 주체를 사용하여 **Power BI Embedded**와 통합할 때 SSAS에서 사용자와 데이터 액세스를 관리할 수 있습니다.

### <a name="can-you-sign-into-the-power-bi-service-with-service-principal"></a>서비스 주체를 사용하여 Power BI 서비스에 로그인할 수 있나요?

아니요 - 서비스 주체를 사용하여 Power BI에 로그인할 수 없습니다.

또한 포함 토큰을 생성할 때만 외부 애플리케이션(SaaS 포함)의 사용자로 콘텐츠를 사용할 수 없습니다.

### <a name="what-are-the-best-practices-to-improve-performance"></a>성능을 개선하기 위한 모범 사례는 무엇인가요?

[Power BI Embedded 성능](embedded-performance-best-practices.md)

## <a name="licensing"></a>라이선싱

### <a name="how-do-i-purchase-power-bi-embedded"></a>Power BI Embedded를 구매하려면 어떻게 하나요?

Power BI Embedded는 Azure를 통해 제공됩니다.

### <a name="what-happens-if-i-already-purchased-power-bi-premium-and-now-i-want-some-power-bi-embedded-in-azure-benefits"></a>이미 Power BI 프리미엄을 구입 했습니다 및 몇 가지 Power BI Embedded Azure 혜택에서 보려는 경우 어떻게 되나요?

고객은 자신의 현재 계약 기간이 끝날 때까지 모든 기존 Power BI 프리미엄 구매에 대 한 요금을 지불 계속 하 고 그런 다음이 시점에서 전환할 수는 Power BI 프리미엄 구매 필요에 따라 됩니다.

### <a name="do-i-still-have-to-buy-power-bi-premium-to-get-access-to-power-bi-embedded"></a>Power BI Embedded에 액세스하려면 Power BI Premium을 구매해야 하나요?

아니요, Power BI Embedded는 고객에게 솔루션을 배포해야 하는 Azure 기반 용량을 포함하고 있습니다.

### <a name="whats-the-purchase-commitment-for-power-bi-embedded"></a>Power BI Embedded의 구매 약정은 어떻게 되나요?

고객은 시간 단위로 사용량을 변경할 수 있습니다. Power BI Embedded 서비스에 대 한 월간 또는 연간 약정이 없습니다 있습니다.

### <a name="how-does-the-usage-of-power-bi-embedded-show-up-on-my-bill"></a>청구서에 Power BI Embedded 사용량이 어떻게 표시되나요?

Power BI Embedded는 배포된 노드 유형을 기반으로 예측 가능한 시간당 요금이 청구됩니다. 리소스는 사용 하지 않는 경우에 활성으로 청구 됩니다. 청구를 중지 하 게 리소스를 일시 중지 해야 합니다.

### <a name="who-needs-a-power-bi-pro-license-for-power-bi-embedded-and-why"></a>Power BI Embedded에 Power BI Pro 라이선스가 필요한 사람은 누구이고 그 이유는 무엇인가요?

Power BI Pro 라이선스가 필요 하거나 [서비스 주체](embed-service-principal.md) REST Api를 사용 하도록 합니다. 보고서는 Power BI 작업 영역에 추가할 분석가 필요한 Power BI Pro 라이선스 또는 서비스 주체. Power BI 테 넌 트 및 용량을 관리 하려면 관리자는 필요한 Power BI Pro 라이선스가 있어야 합니다.

Power BI Embedded 관리 및 포함 된 콘텐츠 유효성 검사에 대 한 Power BI 포털 사용을 허용 하기 때문에 Power BI Pro 라이선스는 올바른 리포지토리의 보고서에 대 한 액세스를 가져오려고 PowerBI.com 내에서 앱을 인증 해야 합니다.

그러나 애플리케이션 내의 [포함된 보고서 만들기/편집](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Create-Report-in-Embed-View)의 경우 최종 사용자가 Power BI 사용자일 필요가 없으므로 Pro 라이선스가 필요하지 않습니다.

### <a name="can-i-get-started-for-free"></a>무료로 시작할 수 있나요?

예, Power BI Embedded에 [Azure 크레딧](https://azure.microsoft.com/free/)을 사용할 수 있습니다.

### <a name="can-i-get-a-trial-experience-for-power-bi-embedded-in-azure"></a>Azure에서 Power BI Embedded 평가판을 받을 수 있나요?

이기 때문에 Power BI Embedded는 Azure의 일부를 사용 하 여 서비스를 사용 하 여 [Azure에 등록할 때 받은 $200 크레딧](https://azure.microsoft.com/free/)합니다.

### <a name="is-power-bi-embedded-available-for-national-clouds-us-government-germany-china"></a>내셔널 클라우드(미국 정부, 독일, 중국)에 Power BI Embedded를 사용할 수 있나요?

Power BI Embedded에 대 한 사용 가능한 이기도 [내셔널 클라우드](embed-sample-for-customers-national-clouds.md)합니다.

### <a name="is-power-bi-embedded-available-for-non-profits-and-educational"></a>교육 기관 및 비영리 단체도 Power BI Embedded를 사용할 수 있나요?

교육 기관 및 비영리 엔터티에 대 한 가격 책정 없는 특별 한 Azure 있습니다.

## <a name="power-bi-workspace-collection"></a>Power BI 작업 영역 컬렉션

### <a name="what-is-power-bi-workspace-collection"></a>Power BI 작업 영역 컬렉션이란?

**Power BI 작업 영역 컬렉션** (**Power BI Embedded** 버전 1) 솔루션을 기반으로 합니다 **Power BI 작업 영역 컬렉션** Azure 리소스입니다. 이 솔루션을 사용하면 애플리케이션을 Power BI에 대해 인증하는 데 **Power BI 작업 영역 컬렉션** 솔루션의 Power BI 콘텐츠, 전용 API 및 작업 영역 컬렉션 키를 사용하는 고객의 **Power BI Embedded** 애플리케이션을 만들 수 있습니다.

### <a name="can-i-migrate-from-power-bi-workspace-collection-to-power-bi-embedded"></a>Power BI 작업 영역 컬렉션에서 Power BI Embedded로 마이그레이션할 수 있나요?

1. 마이그레이션 도구를 사용하여 **Power BI 작업 영역 컬렉션** 콘텐츠를 Power BI - https://docs.microsoft.com/power-bi/developer/migrate-from-powerbi-embedded#content-migration에 복제할 수 있습니다.

2. Power BI 콘텐츠를 사용하는 **Power BI Embedded** 애플리케이션 POC를 시작합니다.

3. 프로덕션 준비가 되면 **Power BI Embedded** 전용 용량을 구매하고 해당 용량에 Power BI 콘텐츠(작업 영역)를 할당합니다.

    > [!Note]
    > **Power BI Embedded** 솔루션과 병렬로 빌드하는 동안 **Power BI 작업 영역 컬렉션**을 계속 사용할 수 있습니다. 준비가 되면 고객을 새 **Power BI Embedded** 솔루션으로 이동하고 **Power BI 작업 영역 컬렉션** 솔루션을 사용 중지할 수 있습니다.

자세한 내용은 [Power BI 작업 영역 컬렉션 콘텐츠를 Power BI Embedded로 마이그레이션하는 방법](https://docs.microsoft.com/power-bi/developer/migrate-from-powerbi-embedded)을 참조하세요.

### <a name="is-power-bi-workspace-collection-on-a-deprecation-path"></a>사용 중단 경로에서 Power BI 작업 영역 컬렉션은?

예, 하지만 이미 사용 하는 고객에 게는 **Power BI 작업 영역 컬렉션** 솔루션 계속 사용 중단 될 때까지 사용할 수 있습니다. 고객은 **Power BI 작업 영역 컬렉션** 솔루션을 사용하는 새 작업 영역 컬렉션 및 **Power BI Embedded** 애플리케이션을 만들 수도 있습니다.

그러나 즉, 새로운 기능에 추가할 수는 없습니다 **Power BI 작업 영역 컬렉션** 솔루션입니다. 새로 마이그레이션을 계획 하는 고객 것이 좋습니다 **Power BI Embedded** 솔루션입니다.

### <a name="when-is-power-bi-workspace-collection-support-discontinued"></a>Power BI 작업 영역 컬렉션 지원은 언제 중단되나요?

**Power BI 작업 영역 컬렉션** 솔루션을 이미 사용하고 있는 고객은 2018년 6월 말까지 또는 지원 계약이 종료될 때까지 계속 사용할 수 있습니다.

### <a name="in-what-regions-can-i-create-a-pbi-workspace-collection"></a>PBI 작업 영역 컬렉션을 어떤 지역에서 만들 수 있나요?

사용 가능한 지역은 오스트레일리아 남동부, 브라질 남부, 캐나다 중부, 미국 동부 2, 일본 동부, 미국 중북부, 북유럽, 미국 중남부, 동남 아시아, 영국 남부, 유럽 서부, 인도 서부 및 미국 서부입니다.

### <a name="why-should-i-migrate-from-pbi-workspace-collection-to-power-bi-embedded"></a>PBI 작업 영역 컬렉션에서 Power BI Embedded로 마이그레이션해야 하는 이유는 무엇인가요?

일부 새로 **Power BI Embedded** 솔루션 기능 및 기능을 수행할 수 없는 **Power BI 작업 영역 컬렉션**합니다.

일부 기능은 다음과 같습니다.
* 모든 PBI 데이터 원본이 지원 됩니다. 두 개의 **Power BI 작업 영역 컬렉션** 데이터 원본이 지원 됩니다. 
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

### <a name="how-can-i-edit-my-registered-application"></a>등록된 응용 프로그램을 편집할 수 있는 방법

Azure AD에 등록된 애플리케이션을 편집하는 방법을 알아보려면 [빠른 시작: Azure Active Directory에서 애플리케이션 업데이트](https://docs.microsoft.com/azure/active-directory/develop/quickstart-v1-update-azure-ad-app)를 참조하세요.

### <a name="how-can-i-edit-my-power-bi-user-profile-or-data"></a>내 Power BI 사용자 프로필 또는 데이터를 편집할 수 있는 방법

[여기](https://docs.microsoft.com/power-bi/service-basic-concepts)에서 Power BI 데이터를 편집하는 방법을 알아볼 수 있습니다.

자세한 내용은 [포함된 애플리케이션 문제 해결](embedded-troubleshoot.md)을 참조하세요.

궁금한 점이 더 있나요? [Power BI 커뮤니티를 이용하세요.](http://community.powerbi.com/)
