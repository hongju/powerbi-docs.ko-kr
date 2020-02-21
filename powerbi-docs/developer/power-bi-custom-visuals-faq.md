---
title: Power BI 시각적 개체에 대해 자주 묻는 질문
description: Power BI 시각적 개체에 대한 질문과 대답 목록을 살펴보세요.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.topic: conceptual
ms.subservice: powerbi-custom-visuals
ms.custom: ''
ms.date: 12/17/2018
ms.openlocfilehash: 01fe7056c844a9eed96356e478cc23d5593809bd
ms.sourcegitcommit: 8e3d53cf971853c32eff4531d2d3cdb725a199af
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "75759063"
---
# <a name="power-bi-visuals-faq"></a>Power BI 시각적 개체 FAQ

## <a name="organizational-power-bi-visuals"></a>조직의 Power BI 시각적 개체

관리 포털을 통해 조직의 Power BI 시각적 개체를 관리할 수 있습니다.

### <a name="how-can-the-admin-manage-organizational-power-bi-visuals"></a>관리자가 조직의 Power BI 시각적 개체를 관리하려면 어떻게 해야 하나요?

관리 포털의 *조직의 시각적 개체* 탭에서 관리자는 [엔터프라이즈의 모든 조직 Power BI 시각적 개체를 확인하고 관리](../service-admin-portal.md#organizational-visuals)할 수 있습니다. 여기에는 Power BI 시각적 개체 추가, 사용하도록 설정, 사용하지 않도록 설정 및 삭제가 포함됩니다.

조직의 사용자는 Power BI 시각적 개체를 쉽게 찾고 Power BI Desktop 또는 서비스에서 직접 보고서로 가져올 수 있습니다.

관리자가 새로운 버전의 조직 Power BI 시각적 개체를 업로드하면 조직의 모든 사용자가 동일한 업데이트된 버전을 가져옵니다. 업데이트된 Power BI 시각적 개체를 사용하는 모든 보고서는 자동으로 업데이트됩니다.

사용자는 기본 제공 Power BI Desktop 및 Power BI 서비스 조직 스토어의 *내 조직* 탭에서 조직의 Power BI 시각적 개체를 찾을 수 있습니다. 

### <a name="if-an-admin-uploads-a-power-bi-visual-from-the-public-marketplace-to-the-organization-store-is-it-automatically-updated-once-a-vendor-updates-the-visual-in-the-public-marketplace"></a>관리자가 Power BI 시각적 개체를 공용 마켓플레이스에서 조직 스토어로 업로드하는 경우 공급업체가 공용 마켓플레이스에서 시각적 개체를 업데이트하면 해당 시각적 개체가 자동으로 업데이트되나요?

아니요, 공용 마켓플레이스에서는 자동으로 업데이트되지 않습니다. 관리자가 조직의 Power BI 시각적 개체 버전을 업데이트해야 합니다.

### <a name="is-there-a-way-to-disable-the-organization-store"></a>조직 스토어를 사용하지 않도록 설정하는 방법이 있나요?

아니요. Power BI Desktop 및 Power BI 서비스에는 항상 *내 조직* 탭이 표시됩니다. 관리자가 관리 포털에서 조직의 모든 Power BI 시각적 개체를 사용하지 않도록 설정하거나 삭제하는 경우 조직 스토어가 비어 있게 됩니다.
  
### <a name="if-the-admin-disables-power-bi-visuals-from-the-admin-portal-tenant-settings-do-users-still-have-access-to-the-organizational-power-bi-visuals"></a>관리자가 관리 포털(테넌트 설정)에서 Power BI 시각적 개체를 사용하지 않도록 설정한 경우에도 사용자가 여전히 조직의 Power BI 시각적 개체에 액세스할 수 있나요?

예. 관리자가 관리 포털에서 Power BI 시각적 개체를 사용하지 않도록 설정해도 조직의 저장소에 영향을 주지 않습니다.

일부 조직은 Power BI 시각적 개체를 사용하지 않도록 설정하고 Power BI 관리자가 가져와 조직의 저장소에 업로드한 엄선한 시각적 개체만 사용하도록 설정합니다.

관리 포털에서 Power BI 시각적 개체를 사용하지 않도록 설정해도 Power BI Desktop에는 적용되지 않습니다. Power BI Desktop 사용자는 여전히 공용 마켓플레이스의 Power BI 시각적 개체를 자신의 보고서에 추가하고 사용할 수 있습니다. 그러나 이러한 공개 Power BI 시각적 개체는 Power BI 서비스에 게시되면 렌더링을 중지하고 적절한 오류를 표시합니다. 

관리 포털에서 Power BI 시각적 개체 설정이 적용되는 경우 Power BI 서비스의 사용자는 공용 마켓플레이스에서 Power BI 시각적 개체를 가져올 수 없습니다. 조직 스토어의 시각적 개체만 가져올 수 있습니다.

### <a name="what-are-the-advantages-of-power-bi-visuals-in-the-organizational-store"></a>조직 스토어의 Power BI 시각적 개체의 이점은 무엇인가요?

* 모든 사용자가 Power BI 관리자가 제어하는 동일한 시각적 개체 버전을 가져옵니다. 관리자가 관리 포털에서 시각적 개체 버전을 업데이트하면 조직의 모든 사용자가 업데이트된 버전을 자동으로 가져옵니다.

* 이메일 또는 공유 폴더를 통해 시각적 개체 파일을 공유할 필요가 없습니다. 조직 스토어 제품은 로그인한 모든 구성원에게 표시됩니다.

* 보안 및 지원 가능성이 제공됩니다. 조직의 Power BI 시각적 개체의 새로운 버전이 모든 보고서에서 자동으로 업데이트됩니다.

* 관리자는 조직 전체에서 사용할 수 있는 Power BI 시각적 개체를 제어할 수 있습니다.

* 관리자는 관리 포털에서 테스트하기 위해 시각적 개체를 사용하도록/사용하지 않도록 설정할 수 있습니다.

## <a name="certified-power-bi-visuals"></a>인증된 Power BI 시각적 개체

### <a name="what-are-certified-power-bi-visuals"></a>인증된 Power BI 시각적 개체란 무엇인가요?

인증된 Power BI 시각적 개체는 특정 [요구 사항](power-bi-custom-visuals-certified.md)을 충족하는 Power BI 시각적 개체이며 Microsoft에서 인증합니다.

[마켓플레이스](https://appsource.microsoft.com/marketplace/apps?page=1&product=power-bi-visuals)에서 인증된 Power BI 시각적 개체에는 인증되었음을 나타내는 노란색 배지가 있습니다.

Microsoft는 타사 Power BI 시각적 개체의 작성자가 아닙니다. 타사 시각적 개체의 기능을 확인하려면 고객이 작성자에게 직접 문의하는 것이 좋습니다.

### <a name="what-tests-are-done-during-the-certification-process"></a>인증 프로세스 중 수행되는 테스트는 무엇인가요?

인증 프로세스 테스트에는 다음이 포함되지만 이에 국한되지는 않습니다. 
* 코드 검토
* 정적 코드 분석
* 데이터 유출
* 데이터 퍼징
* 침투 테스트
* 액세스 XSS 테스트
* 악성 데이터 주입
* 입력 유효성 검사
* 기능 테스트
 
### <a name="are-certified-power-bi-visual-checked-again-with-every-new-submission-upgrade"></a>인증된 Power BI 시각적 개체는 모든 새로운 제출(업그레이드)에서 다시 인증되나요?

예. 인증된 시각적 개체의 새 버전이 마켓플레이스에 제출될 때마다 시각적 개체의 버전 업데이트는 동일한 인증 확인 하에 진행됩니다.

버전 업데이트 인증은 자동으로 이뤄집니다. 업데이트를 거부하는 위반이 발생하는 경우 해결해야 하는 사항을 설명하는 이메일이 개발자에게 발송됩니다.

### <a name="can-a-certified-power-bi-visual-stop-lose-its-certification-after-a-new-update"></a>새 업데이트 후 인증된 Power BI 시각적 개체가 인증을 상실할 수 있나요?

아니요, 이는 불가능합니다. 인증된 시각적 개체는 새 업데이트에서 인증을 상실할 수 없습니다. 업데이트가 거부되었습니다.
 
### <a name="do-i-need-to-share-my-code-in-a-public-repository-if-im-certifying-my-power-bi-visual"></a>내 Power BI 시각적 개체를 인증하는 경우 공용 리포지토리에서 코드를 공유해야 하나요?

아니요, 공개적으로 코드를 공유할 필요가 없습니다.

Power BI 시각적 코드를 확인할 수 있는 읽기 권한을 제공합니다. 예를 들어 GitHub에서 개인 리포지토리를 사용합니다.
 
### <a name="does-a-certified-power-bi-visual-have-to-be-in-the-marketplace"></a>인증된 Power BI 시각적 개체는 마켓플레이스에 있어야 하나요?

예. 비공개 시각적 개체는 인증되지 않습니다.
 
### <a name="how-long-does-it-take-to-certify-my-visual"></a>내 시각적 개체를 인증하는 데 얼마나 걸리나요?

새 Power BI 시각적 개체 인증(최초 인증)은 최대 4주까지 걸릴 수 있습니다. 

업데이트된 버전의 Power BI 시각적 개체를 인증하는 데는 최대 3주가 걸릴 수 있습니다. 

### <a name="does-the-certification-process-ensure-that-there-is-no-data-leakage"></a>인증 프로세스는 데이터 유출이 없음을 보장하나요?

수행된 테스트는 시각적 개체가 외부 서비스 또는 리소스에 액세스할 수 없는지 확인하기 위해 설계되었습니다. 

Microsoft는 타사 Power BI 시각적 개체의 작성자가 아닙니다. 타사 Power BI 시각적 개체의 기능을 확인하려면 고객이 작성자에게 직접 문의하는 것이 좋습니다.
 
### <a name="are-uncertified-power-bi-visuals-safe-to-use"></a>인증되지 않은 Power BI 시각적 개체는 사용하기에 안전한가요?

인증되지 않은 Power BI 시각적 개체가 반드시 안전하지 않은 시각적 개체를 의미하는 것은 아닙니다.

일부 시각적 개체는 [인증 요구 사항](https://docs.microsoft.com/power-bi/power-bi-custom-visuals-certified?#certification-requirements) 중 하나 이상을 준수하지 않았기 때문에 인증되지 않았습니다. 예를 들어 맵 시각적 개체와 같은 외부 서비스에 연결하거나 상용 라이브러리를 사용하여 시각적 개체에 연결할 수 있습니다.
 
## <a name="visuals-with-additional-purchases"></a>추가 구매 조건이 있는 시각적 개체

### <a name="what-is-a-visual-with-additional-purchases"></a>추가 구매 조건이 있는 시각적 개체란?

추가 구매 기능이 있는 시각적 개체는 IAP(앱 내 구매) 추가 기능과 유사합니다. 이러한 추가 기능에는 **추가 구매가 필요할 수도 있음** 가격 태그가 포함되어 있습니다.

IAP Power BI 시각적 개체는 무료로 다운로드할 수 있는 Power BI 시각적 개체입니다. 사용자는 마켓플레이스에서 이러한 Power BI 시각적 개체를 다운로드하는 데 비용을 지불하지 않습니다.

IAP 시각적 개체는 고급 기능에 대한 앱 내 구매 옵션을 제공합니다.  

### <a name="what-is-changing-in-the-submission-process"></a>제출 프로세스는 어떻게 변경되었나요?

마켓플레이스에 IAP Power BI 시각적 개체를 제출하는 프로세스는 무료 Power BI 시각적 개체와 동일합니다. [파트너 센터](https://docs.microsoft.com/partner-center/)를 사용하여 인증할 Power BI 시각적 개체를 제출할 수 있습니다.


Power BI 시각적 개체를 등록하는 경우 *제품 설정* 탭으로 이동하여 *내 제품에 서비스 구매가 필요합니다* 확인란을 선택합니다.

### <a name="what-should-i-do-beforesubmittingmy-iap-power-bi-visual"></a>내 IAP Power BI 시각적 개체를 제출하기 전에 무엇을 확인해야 하나요?

IAP Power BI 시각적 개체에서 작업하는 경우 해당 시각적 개체가 [지침](guidelines-powerbi-visuals.md)을 준수하는지 확인합니다.  

> [!NOTE]
> IAP 기능이 추가된 Power BI 무료 시각적 개체는 이전에 제공한 동일한 무료 기능을 유지해야 합니다. 이전의 무료 기능을 기반으로 선택적 고급 유료 기능을 추가할 수 있습니다. 고급 기능이 포함된 IAP Power BI 시각적 개체를 새 Power BI 시각적 개체로 제출하고 이전의 무료 시각적 개체를 업데이트하지 않는 것이 좋습니다.

### <a name="do-iap-power-bi-visuals-need-to-be-certified"></a>IAP Power BI 시각적 개체를 인증해야 하나요?

[인증](power-bi-custom-visuals-certified.md) 프로세스는 선택 사항입니다. 개발자가 IAP Power BI 시각적 개체를 인증할지 여부를 결정합니다.

### <a name="can-i-get-my-iap-power-bi-visual-certified"></a>내 IAP Power BI 시각적 개체를 인증받을 수 있나요?

예. IAP Power BI 시각적 개체가 AppSource 팀에서 승인된 후 [인증](power-bi-custom-visuals-certified.md)을 위해 Power BI 시각적 개체를 제출할 수 있습니다.

인증은 선택적 프로세스입니다. IAP 시각적 개체를 인증받을지 여부를 결정하는 것은 여러분에게 달려 있습니다.

## <a name="additional-questions"></a>추가 질문

### <a name="how-to-get-support"></a>지원을 받으려면 어떻게 하나요?

질문, 의견 또는 문제가 있으면 언제든지 Power BI 시각적 개체 지원 팀(pbicvsupport@microsoft.com)에 문의하세요.  

## <a name="next-steps"></a>다음 단계

자세한 내용은 [Power BI 시각적 개체 문제 해결](power-bi-custom-visuals-troubleshoot.md)을 참조하세요.
