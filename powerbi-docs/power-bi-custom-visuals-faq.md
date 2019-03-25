---
title: Power BI 사용자 지정 시각적 개체에 대한 질문과 대답
description: Power BI 사용자 지정 시각적 개체에 대한 질문과 대답 목록을 찾아보세요.
author: sranins
ms.author: rasala
manager: kfile
ms.reviewer: maghan
ms.service: powerbi
ms.topic: conceptual
ms.subservice: powerbi-custom-visuals
ms.custom: ''
ms.date: 12/17/2018
ms.openlocfilehash: 9c5d2665f012881f951a186c3ec8c9fd94031a28
ms.sourcegitcommit: ac63b08a4085de35e1968fa90f2f49ea001b50c5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/18/2019
ms.locfileid: "57980361"
---
# <a name="frequently-asked-questions-about-power-bi-custom-visuals"></a>Power BI 사용자 지정 시각적 개체에 대한 질문과 대답

## <a name="organizational-custom-visuals"></a>조직의 사용자 지정 시각적 개체

### <a name="how-can-the-admin-manage-the-organizational-custom-visuals"></a>관리자가 조직의 사용자 지정 시각적 개체를 관리하려면 어떻게 하나요?

관리 포털에 있는 “조직의 사용자 지정 시각적 개체” 탭 아래에서 관리자는 [엔터프라이즈에 있는 조직의 사용자 지정 시각적 개체를 모두 보고 관리](service-admin-portal.md#organizational-visuals)(추가, 사용, 사용 안 함, 삭제)할 수 있습니다.
이러한 시각적 개체는 더 이상 이메일 또는 공유 폴더를 통해 공유할 필요가 없습니다. 조직의 리포지토리에 배포되면 조직의 사용자가 쉽게 찾을 수 있고 Power BI Desktop 또는 서비스에서 조직의 사용자 지정 시각적 개체를 자신의 보고서로 직접 가져올 수 있습니다. 조직의 사용자 지정 시각적 개체는 *내 조직* 탭 아래에 있는 Desktop 및 서비스의 기본 제공 상점에서 찾을 수 있습니다. 관리자가 새로운 조직의 사용자 지정 시각적 개체 버전을 업로드하면 조직의 모든 사용자가 동일한 업데이트된 버전을 가져옵니다. 이러한 시각적 개체를 사용하는 모든 보고서가 자동으로 업데이트되므로 보고서 작성자는 이러한 시각적 개체의 새 버전을 가져오기 위해 해당 보고서에서 시각적 개체를 삭제할 필요가 없습니다. 업데이트 메커니즘은 마켓플레이스 시각적 개체와 유사합니다.

### <a name="if-an-admin-uploads-a-custom-visual-from-the-public-marketplace-to-the-organization-store-is-it-automatically-updated-once-a-vendor-updates-the-visual-in-the-public-marketplace"></a>관리자가 사용자 지정 시각적 개체를 공용 마켓플레이스에서 조직 상점으로 업로드하는 경우 공급업체가 공용 마켓플레이스에서 시각적 개체를 업데이트하면 해당 시각적 개체가 자동으로 업데이트되나요?

아니요, 공용 마켓플레이스에서는 자동으로 업데이트되지 않습니다.
관리자가 조직의 사용자 지정 시각적 개체 버전을 업데이트해야 합니다.

### <a name="is-there-a-way-to-disable-the-organizational-store"></a>조직의 상점을 사용하지 않도록 설정하는 방법이 있나요?

아니요. Power BI Desktop 및 서비스에는 항상 “내 조직” 탭이 표시됩니다. 관리자는 관리 포털에서 모든 조직의 사용자 지정 시각적 개체를 사용하지 않도록 설정하거나 삭제할 수 있고 조직의 저장소는 비어 있습니다.
  
### <a name="if-the-administrator-disables-custom-visuals-from-the-admin-portal-tenant-settings-do-users-still-have-access-to-the-organizational-custom-visuals"></a>관리자가 관리 포털(테넌트 설정)에서 사용자 지정 시각적 개체를 사용하지 않도록 설정한 경우에도 사용자가 여전히 조직의 사용자 지정 시각적 개체에 액세스할 수 있나요?

예. 관리자가 관리 포털에서 사용자 지정 시각적 개체를 사용하지 않도록 설정해도 조직의 저장소에 영향을 주지 않습니다. 일부 조직은 사용자 지정 시각적 개체를 사용하지 않도록 설정하고 Power BI 관리자가 가져오고 조직의 저장소에 업로드한 엄선한 시각적 개체만 사용하도록 설정합니다. 관리 포털에서 사용자 지정 시각적 개체를 사용하지 않도록 설정해도 Power BI Desktop에는 적용되지 않습니다. Power BI Desktop 사용자는 여전히 공용 마켓플레이스의 사용자 지정 시각적 개체를 자신의 보고서에 추가하고 사용할 수 있습니다. 그러나 이러한 공개 사용자 지정 시각적 개체는 Power BI 서비스에 게시되면 렌더링을 중지하고 적절한 오류를 표시합니다. Power BI 서비스를 사용하는 경우 공용 마켓플레이스에서 사용자 지정 시각적 개체를 가져올 수 없습니다. 관리 포털의 사용자 지정 시각적 개체 설정이 Power BI 서비스에 적용되므로 조직의 저장소에 있는 시각적 개체만 가져올 수 있습니다.

### <a name="why-does-the-organizational-store-and-organizational-custom-visuals-make-a-great-enterprise-solution"></a>조직의 상점 및 조직의 사용자 지정 시각적 개체가 훌륭한 엔터프라이즈 솔루션을 만드는 이유는 무엇인가요?

* 모든 사용자가 Power BI 관리자가 제어하는 동일한 시각적 개체 버전을 가져옵니다. 관리자가 관리 포털에서 시각적 개체 버전을 업데이트하면 조직의 모든 사용자가 업데이트된 버전을 자동으로 가져옵니다.

* 더 이상 메일 또는 공유 폴더를 통해 시각적 개체 파일을 공유할 필요가 없습니다! 한 곳에서 로그인한 모든 멤버에게 표시됩니다.

* 보안 및 지원 가능성이 제공됩니다. 새로운 조직의 사용자 지정 시각적 개체 버전이 마켓플레이스 시각적 개체와 비슷하게 모든 보고서에서 자동으로 업데이트됩니다.

* 조직의 사용자 지정 시각적 개체를 사용하는 조직의 사용자는 조직의 보안 요소인 조직의 사용자 지정 시각적 개체를 보고 사용하려면 로그인해야 합니다.

* 관리자는 조직에서 사용할 수 있는 사용자 지정 시각적 개체를 제어할 수 있습니다.

* 관리자는 관리 포털에서 테스트하기 위해 시각적 개체를 사용하도록/사용하지 않도록 설정할 수 있습니다. 해당 시각적 개체는 조직의 멤버에게만 허용되므로 보안이 강화됩니다.

## <a name="certified-custom-visuals"></a>인증된 사용자 지정 시각적 개체

### <a name="what-are-certified-custom-visuals"></a>인증된 사용자 지정 시각적 개체란?

인증된 사용자 지정 시각적 개체는 특정 [지정된](power-bi-custom-visuals-certified.md) 코드 요구 사항 및 Power BI 팀의 테스트를 충족하는 [마켓플레이스](https://appsource.microsoft.com/marketplace/apps?page=1&product=power-bi-visuals)의 시각적 개체입니다. 수행된 테스트는 시각적 개체가 외부 서비스 또는 리소스에 액세스할 수 없는지 확인하기 위해 설계되었습니다. 그러나 Microsoft는 타사 사용자 지정 시각적 개체의 작성자가 아니며, 이러한 시각적 개체의 기능을 확인하기 위해서는 작성자에게 직접 연락하는 것이 좋습니다.

### <a name="what-tests-are-done-during-the-certification-process"></a>인증 프로세스 중 수행되는 테스트는 무엇인가요?

인증 프로세스 테스트에는 다음이 포함되지만 이에 국한되지는 않습니다. 코드 검토, 정적 코드 분석, 데이터 유출, 데이터 퍼징, 침투 테스트, 액세스 XSS 테스트, 악성 데이터 주입, 입력 유효성 검사 및 기능 테스트.
 
### <a name="do-you-certify-visuals-every-submission"></a>제출할 때마다 시각적 개체를 인증하나요?

예. 인증된 시각적 개체의 새 버전이 마켓플레이스에 제출될 때마다 시각적 개체의 버전 업데이트는 동일한 인증 확인 하에 진행됩니다.

개발자를 위한 참고: 인증된 시각적 개체의 버전 업데이트를 제출하는 경우 [첫 번째 인증 요청](https://docs.microsoft.com/power-bi/power-bi-custom-visuals-certified#process-for-submitting-a-custom-visual-for-certification)으로 별도의 이메일을 보낼 필요가 없습니다. 버전 업데이트의 인증은 자동으로 이루어지며 거부를 유발하는 모든 위반에는 수정해야 할 사항을 설명하는 이메일이 발송됩니다. 

### <a name="is-it-possible-that-a-certified-visual-stops-being-certified-with-a-new-update"></a>인증된 시각적 개체가 새 업데이트로 인증되지 않는 것이 가능한가요?

아니요, 이는 불가능합니다. 인증된 시각적 개체는 새 업데이트로 인증되지 않을 수 없습니다. 업데이트가 거부되었습니다.
 
### <a name="do-i-need-to-share-my-code-in-public-repository-if-i-am-submitting-to-the-certification-process"></a>인증 프로세스에 제출하려면 공용 리포지토리에서 내 코드를 공유해야 하나요?

아니요, 공개적으로 코드를 공유할 필요가 없습니다. 그러나 시각적 개체 코드를 확인하기 위한 읽기 권한을 제공해야 합니다. 예: GitHub의 개인 리포지토리.
 
### <a name="do-we-have-to-publishhttpsdocsmicrosoftcompower-bideveloperoffice-store-the-visual-in-the-marketplacehttpsappsourcemicrosoftcommarketplaceappspage1productpower-bi-visuals-to-certify-it"></a>[마켓플레이스](https://appsource.microsoft.com/marketplace/apps?page=1&product=power-bi-visuals)에 시각적 개체를 [게시](https://docs.microsoft.com/power-bi/developer/office-store)하여 인증해야 하나요?

예. 마켓플레이스에 시각적 개체를 먼저 게시하는 것은 인증을 위한 의무 요구 사항입니다.
사용자 지정 시각적 개체를 인증하려면 서버에 있어야 합니다. 개인 시각적 개체는 인증할 수 없습니다.
 
### <a name="how-long-does-it-take-to-certify-my-visual"></a>내 시각적 개체를 인증하는 데 얼마나 걸리나요?

업데이트된 버전의 경우 최대 2주가 걸릴 수 있습니다. 새로운 제출(첫 번째 인증)의 경우 최대 3주가 걸릴 수 있습니다. 

### <a name="does-the-certification-process-ensure-that-no-data-leakage-occurs"></a>인증 프로세스는 데이터 유출이 발생하지 않음을 보장하나요?

수행된 테스트는 시각적 개체가 외부 서비스 또는 리소스에 액세스할 수 없는지 확인하기 위해 설계되었습니다. 그러나 Microsoft는 타사 사용자 지정 시각적 개체의 작성자가 아니며, 이러한 시각적 개체의 기능을 확인하기 위해 작성자에게 직접 연락하는 것이 좋습니다.
 
### <a name="are-uncertified-custom-visuals-safe-to-use"></a>인증되지 않은 사용자 지정 시각적 개체는 사용하기에 안전한가요?

인증되지 않은 사용자 지정 시각적 개체는 반드시 안전하지 않은 시각적 개체를 의미하지는 않습니다.
일부 시각적 개체는 [인증 요구 사항](https://docs.microsoft.com/power-bi/power-bi-custom-visuals-certified?#certification-requirements) 중 하나 이상을 준수하지 않았기 때문에 인증되지 않았습니다. 예를 들어 맵 시각적 개체와 같은 외부 서비스에 연결하거나 상용 라이브러리를 사용하여 시각적 개체에 연결할 수 있습니다.
 
## <a name="visuals-with-additional-purchases"></a>추가 구매 조건이 있는 시각적 개체

### <a name="what-is-a-visual-with-additional-purchases"></a>추가 구매 조건이 있는 시각적 개체란?

추가 구매 조건이 있는 시각적 개체는 마켓플레이스의 IAP(앱 내 구매) 추가 기능과 비슷하며, 이러한 추가 구매에는 **추가 구매가 필요할 수도 있음**이라는 가격 태그가 있습니다.

IAP 사용자 지정 시각적 개체는 평가판으로 다운로드할 수 있는 사용자 지정 시각적 개체입니다. 마켓플레이스에서 사용자 지정 시각적 개체를 다운로드하는 경우 사용자는 아무 비용도 추가로 지불하지 않습니다. IAP 시각적 개체는 고급 기능에 대한 앱 내 구매 옵션을 제공합니다.  

### <a name="whats-the-benefit-to-developers"></a>개발자에게 어떤 혜택이 있나요?

AppSource의 IAP 사용자 지정 시각적 개체는 많은 일일 방문자가 검색할 수 있으며, 유용한 트래픽을 가져오고, 개발자의 IAP 사용자 지정 시각적 개체에 대한 인지도를 높여줍니다.

최근까지 웹사이트를 통해 이러한 시각적 개체를 관리했으면 이제 AppSource에 이를 제출할 수 있습니다. Power BI 커뮤니티 내에서 IAP 시각적 개체의 검색 가능성 및 가시성 수준을 높일 것입니다.

AppSource의 시각적 개체는 상점 내의 검토 및 등급 시스템을 통해 IAP 사용자 지정 시각적 개체를 사용하는 고객으로부터의 직접 피드백 채널을 이용할 수 있습니다.  

IAP 시각적 개체가 AppSource 유효성 검사 팀에서 승인되면 인증을 위해 해당 시각적 개체를 제출할 수도 있습니다. 이는 선택적 프로세스입니다.  

시각적 개체가 인증되면 IAP 사용자 지정 시각적 개체를 PowerPoint로 내보낼 수 있고 사용자가 보고서 페이지를 구독할 때 받은 이메일에 표시할 수 있습니다. 따라서 이제는 IAP 시각적 개체를 마켓플레이스에 제출하여 IAP 사용자 지정 시각적 개체를 인증하고 추가 기능 세트를 지원할 수도 있습니다.  

### <a name="do-iap-visuals-need-to-be-certified"></a>IAP 시각적 개체를 인증해야 하나요?

인증 프로세스는 선택 사항입니다. 개발자는 IAP 사용자 지정 시각적 개체를 인증할지, 아니면 평가판 시각적 개체와 동일한지 여부를 결정해야 합니다.

### <a name="what-is-changing-in-the-submission-process"></a>제출 프로세스는 어떻게 변경되었나요?

마켓플레이스에 대한 IAP 사용자 지정 시각적 개체 제출 프로세스는 평가판 시각적 개체와 동일합니다. 이 프로세스는 판매자 대시보드를 통해 수행됩니다.  제출 프로세스에서 유일하게 변경된 절차는 개발자가 판매자 대시보드의 개발자 참고 사항에 "앱 내 구매 조건이 있는 시각적 개체"를 명시해야 한다는 것입니다. 또한 유료/고급 기능의 유효성을 검사하는 데 필요한 경우 라이선스 키/토큰을 제공해야 합니다.  

판매자 대시보드에는 새 옵션이 없습니다. *앱 내 구매 조건이 있는 평가판*의 경우 IAP 시각적 개체를 *평가판*으로 제출해야 합니다.

또한 상점에서 평가판 기능과 작동하기 위해 추가 구매가 필요한 기능에 대해 자세히 설명하여 사용자가 기대하는 요구 사항을 알려줍니다.  

### <a name="what-should-i-do-beforesubmittingmy-iap-custom-visual"></a>내 IAP 사용자 지정 시각적 개체를 제출하려면 어떻게 해야 하나요?

IAP 사용자 지정 시각적 개체를 사용하고 있거나 이미 가지고 있는 경우 지침을 준수해야 합니다.  

사용자 지정 시각적 개체에 로고가 있으면 로고 지침(색, 위치, 크기 및 작업 트리거링)을 준수하는지 확인합니다.

또한 지침, 모범 사례 참고 사항을 찾을 수도 있습니다.  
> [!Note]
> 모든 무료 시각적 개체는 이전에 제공된 동일한 무료 기능을 유지해야 합니다. 이전 무료 기능을 기반으로 선택적 고급 유료 기능을 추가할 수 있습니다. 고급 기능을 갖춘 IAP 시각적 개체를 새 시각적 개체로 제출하고 이전 무료 버전을 업데이트하지 않는 것이 좋습니다.

### <a name="can-i-get-my-iap-custom-visual-certified"></a>내 IAP 사용자 지정 시각적 개체를 인증받을 수 있나요?

예, 평가판 시각적 개체와 동일합니다.  AppSource 팀에서 IAP 사용자 지정 시각적 개체를 승인하면 해당 시각적 개체를 인증 프로세스에 제출할 수 있습니다.

시각적 개체를 인증받으려면 인증 요구 사항을 준수해야 합니다. 예를 들어 시각적 개체는 라이선스 유효성 검사를 위해 외부 서비스에 액세스할 수 없습니다.

회수 인증은 선택적 프로세스입니다. IAP 시각적 개체를 인증받을지 여부를 결정하는 것은 여러분에게 달려 있습니다.

## <a name="additional-questions"></a>추가 질문

### <a name="how-to-get-support"></a>지원을 받으려면 어떻게 하나요?

질문, 의견 또는 문제가 있으면 언제든지 사용자 지정 시각적 개체 지원 팀 *pbicvsupport@microsoft.com* 에 문의하세요.  

## <a name="next-steps"></a>다음 단계

자세한 내용은 [Power BI 사용자 지정 시각적 개체 문제 해결](power-bi-custom-visuals-troubleshoot.md)을 참조하세요.
