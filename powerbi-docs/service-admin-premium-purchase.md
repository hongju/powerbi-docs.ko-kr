---
title: Power BI 프리미엄 구매 방법
description: Power BI Premium을 구매하고 전체 조직에 대한 콘텐츠에 대한 액세스를 활성화할 수 있는 방법을 알아봅니다.
author: minewiskan
ms.author: owend
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 02/26/2019
LocalizationGroup: Premium
ms.openlocfilehash: 8922bb329e4b598745fd259c67e74b063368b7be
ms.sourcegitcommit: 76772a361e6cd4dd88824b2e4b32af30656e69db
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/27/2019
ms.locfileid: "56892393"
---
# <a name="how-to-purchase-power-bi-premium"></a>Power BI 프리미엄 구매 방법

이 문서에서는 조직에 대한 Power BI 프리미엄 용량(P1-P3)을 구입하는 방법을 설명합니다. Office 365 관리 센터에서 Power BI Premium 용량을 구매하고 Power BI 관리 포털에서 [용량을 관리](service-admin-premium-manage.md)합니다. 최신 가격 책정 및 계획 정보는 [Power BI 가격 책정 페이지](https://powerbi.microsoft.com/pricing/) 및 [Power BI Premium 계산기](https://powerbi.microsoft.com/calculator/)를 참조하세요.

조직에서 Power BI Premium을 사용하더라도 콘텐츠 작성자는 여전히 Power BI Pro 라이선스가 필요합니다. 조직을 위한 Power BI Pro 라이선스를 하나 이상 구입하세요.

Premium 구독이 만료되면 30일 동안 용량에 대한 전체 액세스 권한을 가집니다. 그 후에는 콘텐츠가 공유 용량으로 전환됩니다. 1GB보다 큰 모델은 공유 용량에서 지원되지 않습니다.

## <a name="create-a-new-tenant-with-power-bi-premium-p1"></a>Power BI 프리미엄 P1로 새 테넌트 만들기

기존 테넌트가 없어 새로 하나를 만들려면 Power BI 프리미엄도 동시에 구입할 수 있습니다. 다음 링크를 통해 새 테넌트를 만드는 과정을 안내받고 Power BI Premium을 구매할 수 있습니다. [Power BI Premium P1 제품](https://signup.microsoft.com/Signup?OfferId=b3ec5615-cc11-48de-967d-8d79f7cb0af1). 테넌트를 만들면 자동으로 해당 테넌트에 대한 Office 365 글로벌 관리자 역할을 할당받게 됩니다.

## <a name="purchase-a-power-bi-premium-capacity-for-an-existing-organization"></a>기존 조직에 대한 Power BI 프리미엄 용량 구입

기존 조직(테넌트)이 있는 경우 Office 365 글로벌 관리자 역할 또는 청구 관리자 역할을 할당받아야 구독 및 라이선스를 구입할 수 있습니다. 자세한 내용은 [Office 365 관리자 역할 정보](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)를 참조하세요.

프리미엄 용량을 구입하려면 다음 단계를 따르세요.

1. Power BI 서비스 내에서 Office 365 앱 선택, **관리자**를 차례로 선택합니다.

    ![Office 365 앱 선택](media/service-admin-premium-purchase/o365-app-picker.png)

    또는 Office 365 관리 센터를 찾아볼 수 있습니다. https://portal.office.com으로 이동하여 **관리자**를 선택하면 도달할 수 있습니다.

1. **청구** > **서비스 구입**을 선택합니다.

1. **기타 계획** 아래에서 Power BI 프리미엄 제안을 찾습니다. P1~P3, EM3 및 P1(매월)로 나열됩니다.

1. 줄임표(**...**)를 마우스로 가리키고 **지금 구입**을 선택합니다.

    ![지금 구입](media/service-admin-premium-purchase/premium-purchase.png)

1. 단계에 따라 구입을 완료합니다.

구입을 완료하면 **서비스 구입** 페이지에 항목을 구입했고 활성 상태인 것으로 표시됩니다.

![구매한 Power BI 프리미엄](media/service-admin-premium-purchase/premium-purchased.png)

## <a name="purchase-additional-capacities"></a>추가 용량 구입

이제 용량을 구입했으므로 요구 사항 증가에 따라 더 많은 용량을 추가할 수 있습니다. 또한 조직 내에서 프리미엄 용량 SKU(P1~P3)의 임의 조합을 사용할 수 있습니다. SKU마다 다양한 리소스 기능을 제공합니다.

1. Office 365 관리 센터에서 **청구** > **서비스 구입**을 선택합니다.

1. **기타 계획** 아래에서 추가로 구입할 Power BI 프리미엄 항목을 찾습니다.

1. **줄임표(...)** 를 마우스로 가리키고 **라이선스 수량 변경**을 선택합니다.

    ![라이선스 수량 변경](media/service-admin-premium-purchase/premium-purchase-more.png)

1. 이 항목에 대해 포함할 인스턴스 수를 변경합니다. 그런 다음 완료했으면 **제출**을 선택합니다.

   > [!IMPORTANT]
   > **제출**을 선택하면 등록된 신용 카드에 요금이 부과됩니다.

**서비스 구입** 페이지에 보유하고 있는 인스턴스 수가 표시됩니다. Power BI 관리 포털 내의 **용량 설정** 아래에서 사용 가능한 V 코어는 구입한 새 용량을 반영합니다.

![Power BI Premium 용량에 대한 사용 가능한 V 코어](media/service-admin-premium-purchase/premium-capacities.png)

## <a name="cancel-your-subscription"></a>구독 취소

Office 365 관리 센터 내에서 구독을 취소할 수 있습니다. 프리미엄 구독을 취소하려면 다음을 수행합니다.

1. Office 365 관리 센터로 이동합니다.

1. **청구** > **구독**을 선택합니다.

1. 목록에서 Power BI 프리미엄 구독을 선택합니다.

1. **추가 작업** > **구독 취소**를 선택합니다.

1. **구독 취소** 페이지는 [조기 종료 요금](https://support.office.com/article/early-termination-fees-6487d4de-401a-466f-8bc3-c0beb5cc40d3)에 대한 책임 여부를 나타냅니다. 이 페이지는 구독에 대한 데이터가 삭제될 때도 이를 알려줍니다.

1. 정보를 자세히 읽고 계속하려면 **구독 취소**를 선택합니다.

## <a name="next-steps"></a>다음 단계

[Power BI 가격 책정 페이지](https://powerbi.microsoft.com/pricing/)
[Power BI Premium 계산기](https://powerbi.microsoft.com/calculator/)
[Power BI Premium이란?](service-premium.md)
[Power BI Premium FAQ](service-premium-faq.md)
[Microsoft Power BI Premium 백서](https://aka.ms/pbipremiumwhitepaper)
[Power BI Enterprise 배포 계획 백서](https://aka.ms/pbienterprisedeploy)

궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](http://community.powerbi.com/)