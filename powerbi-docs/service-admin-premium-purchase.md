---
title: Power BI 프리미엄 구매 방법
description: Power BI Premium을 구매하고 전체 조직에 대한 콘텐츠에 대한 액세스를 활성화할 수 있는 방법을 알아봅니다.
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 12/10/2019
LocalizationGroup: Premium
ms.openlocfilehash: 8a97f30f75b8bf720d735944589e671392c47237
ms.sourcegitcommit: 6272c4a0f267708ca7d38a45774f3bedd680f2d6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/06/2020
ms.locfileid: "75224079"
---
# <a name="how-to-purchase-power-bi-premium"></a>Power BI 프리미엄 구매 방법

이 문서에서는 조직에 대한 Power BI 프리미엄 용량을 구입하는 방법을 설명합니다. 이 문서에서는 다음 두 가지 시나리오를 설명합니다.

- 일반적인 프로덕션 시나리오에 P SKU 사용. P SKU는 월간 또는 연간 약정이 필요하며 매달 요금이 청구됩니다. P SKU는 [Microsoft 365 관리 센터](https://admmin.microsoft.com)에서 구매합니다.

- 테스트 시나리오와 P SKU를 구매하는 데 필요한 권한(Microsoft 365 전역 관리자 역할 또는 대금 청구 관리자 역할)이 없는 경우에 A SKU 사용. A SKU는 시간 약정이 필요하지 않으며 시간 단위로 요금이 청구됩니다. A SKU는 [Azure Portal](https://portal.azure.com)에서 구매합니다.

Power BI Premium에 대한 자세한 내용은 [Power BI Premium이란?](service-premium-what-is.md)을 참조하세요. 최신 가격 책정 및 계획 정보는 [Power BI 가격 책정 페이지](https://powerbi.microsoft.com/pricing/) 및 [Power BI Premium 계산기](https://powerbi.microsoft.com/calculator/)를 참조하세요. 조직에서 Power BI Premium을 사용하더라도 콘텐츠 작성자는 여전히 [Power BI Pro 라이선스](service-admin-purchasing-power-bi-pro.md)가 필요합니다. 조직을 위한 Power BI Pro 라이선스를 하나 이상 구매하세요. A SKU를 사용하는 경우 콘텐츠를 사용하는 ‘모든 사용자’도 Pro 라이선스가 필요합니다. 

> [!NOTE]
> Premium 구독이 만료되면 30일 동안 용량에 대한 전체 액세스 권한을 가집니다. 그 후에는 콘텐츠가 공유 용량으로 전환됩니다. 1GB보다 큰 모델은 공유 용량에서 지원되지 않습니다.

## <a name="purchase-p-skus-for-typical-production-scenarios"></a>일반적인 프로덕션 시나리오를 위해 P SKU 구매

Power BI Premium P1 SKU가 구성된 새 테넌트를 만들거나, 기존 조직을 위해 Power BI Premium 용량을 구매할 수 있습니다. 두 경우 모두, 필요에 따라 용량을 추가할 수 있습니다.

### <a name="create-a-new-tenant-with-power-bi-premium-p1"></a>Power BI 프리미엄 P1로 새 테넌트 만들기

기존 테넌트가 없어 새로 하나를 만들려면 Power BI 프리미엄도 동시에 구매할 수 있습니다. 다음 링크를 통해 새 테넌트를 만드는 과정을 안내받고 Power BI Premium을 구매할 수 있습니다: [Power BI Premium P1 제품](https://signup.microsoft.com/Signup?OfferId=b3ec5615-cc11-48de-967d-8d79f7cb0af1). 테넌트를 만들면 자동으로 해당 테넌트의 Microsoft 365 전역 관리자 역할에 할당됩니다.

용량을 구매한 후 [용량을 관리](service-admin-premium-manage.md#manage-capacity)하고 용량에 [작업 영역을 할당](service-admin-premium-manage.md#assign-a-workspace-to-a-capacity)하는 방법을 알아봅니다.

### <a name="purchase-a-power-bi-premium-capacity-for-an-existing-organization"></a>기존 조직에 대한 Power BI 프리미엄 용량 구매

기존 조직(테넌트)이 있는 경우 Microsoft 365 전역 관리자 역할 또는 대금 청구 관리자 역할에 할당되어아야 구독 및 라이선스를 구매할 수 있습니다. 자세한 내용은 [Microsoft 365 관리자 역할 정보](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)를 참조하세요.

프리미엄 용량을 구매하려면 다음 단계를 따르세요.

1. Power BI 서비스 내에서 Microsoft 365 앱 선택기, **관리자**를 차례로 선택합니다.

    ![Microsoft 365 앱 선택기](media/service-admin-premium-purchase/o365-app-picker.png)

    또는 Microsoft 365 관리 센터로 이동할 수 있습니다.

1. **청구** > **서비스 구매**를 선택합니다.

1. **기타 계획** 아래에서 Power BI 프리미엄 제안을 찾습니다. P1~P3, EM3 및 P1(매월)로 나열됩니다.

1. 줄임표( **...** )를 마우스로 가리키고 **지금 구매**를 선택합니다.

    ![지금 구입](media/service-admin-premium-purchase/premium-purchase.png)

1. 단계에 따라 구매를 완료합니다.

구매를 완료하면 **서비스 구입** 페이지에 항목을 구매했고 활성 상태인 것으로 표시됩니다.

![구매한 Power BI 프리미엄](media/service-admin-premium-purchase/premium-purchased.png)

용량을 구매한 후 [용량을 관리](service-admin-premium-manage.md#manage-capacity)하고 용량에 [작업 영역을 할당](service-admin-premium-manage.md#assign-a-workspace-to-a-capacity)하는 방법을 알아봅니다.

### <a name="purchase-additional-capacities"></a>추가 용량 구매

이제 용량을 구매했으므로 요구 사항 증가에 따라 더 많은 용량을 추가할 수 있습니다. 또한 조직 내에서 프리미엄 용량 SKU(P1~P3)의 임의 조합을 사용할 수 있습니다. SKU마다 다양한 리소스 기능을 제공합니다.

1. Microsoft 365 관리 센터에서 **청구** > **서비스 구매**를 선택합니다.

1. **기타 계획** 아래에서 추가로 구매할 Power BI 프리미엄 항목을 찾습니다.

1. **추가 옵션**(...)을 마우스로 가리키고 **라이선스 수량 변경**을 선택합니다.

    ![라이선스 수량 변경](media/service-admin-premium-purchase/premium-purchase-more.png)

1. 이 항목에 대해 포함할 인스턴스 수를 변경합니다. 그런 다음 완료했으면 **제출**을 선택합니다.

   > [!IMPORTANT]
   > **제출**을 선택하면 등록된 신용 카드에 요금이 부과됩니다.

**서비스 구매** 페이지에 보유하고 있는 인스턴스 수가 표시됩니다. Power BI 관리 포털 내의 **용량 설정** 아래에서 사용 가능한 V 코어는 구매한 새 용량을 반영합니다.

![Power BI Premium 용량에 대한 사용 가능한 V 코어](media/service-admin-premium-purchase/premium-capacities.png)

### <a name="cancel-your-subscription"></a>구독 취소

Microsoft 365 관리 센터 내에서 구독을 취소할 수 있습니다. 프리미엄 구독을 취소하려면 다음을 수행합니다.

1. Microsoft 365 관리 센터로 이동합니다.

1. **청구** > **구독**을 선택합니다.

1. 목록에서 Power BI 프리미엄 구독을 선택합니다.

1. **추가 작업** > **구독 취소**를 선택합니다.

1. **구독 취소** 페이지는 [조기 종료 요금](https://support.office.com/article/early-termination-fees-6487d4de-401a-466f-8bc3-c0beb5cc40d3)에 대한 책임 여부를 나타냅니다. 이 페이지는 구독에 대한 데이터가 삭제될 때도 이를 알려줍니다.

1. 정보를 자세히 읽고 계속하려면 **구독 취소**를 선택합니다.

#### <a name="when-canceling-or-your-license-expires"></a>구독을 취소하거나 라이선스가 만료되는 경우

프리미엄 구독을 취소하거나 용량 라이선스가 만료되는 경우 구독 취소 또는 라이선스 만료 날짜로부터 30일 동안 프리미엄 용량에 계속 액세스할 수 있습니다. 30일 후에는 프리미엄 용량 또는 해당 작업 영역에 더 이상 액세스할 수 없습니다.

## <a name="purchase-a-skus-for-testing-and-other-scenarios"></a>테스트 및 기타 시나리오를 위해 A SKU 구매

A SKU는 Azure Power BI Embedded 서비스를 통해 제공됩니다. A SKU는 다음과 같은 방법으로 사용할 수 있습니다.

- 타사 애플리케이션에서 Power BI 포함을 사용하도록 설정합니다. 자세한 내용은 [Power BI Embedded](developer/azure-pbie-what-is-power-bi-embedded.md)를 참조하세요.

- P SKU를 구입하기 전에 Premium 기능을 테스트합니다.

- P SKU를 사용하는 프로덕션 환경과 함께 개발 및 테스트 환경을 만듭니다.

- Microsoft 365 전역 관리자 역할 또는 대금 청구 관리자 역할이 아니더라도 Power BI Premium을 구매합니다.

> [!NOTE]
> A4 이상 SKU를 구매하면 무제한 콘텐츠 공유를 제외한 모든 Premium 기능을 이용할 수 있습니다. A SKU를 사용하는 경우 콘텐츠를 사용하는 ‘모든 사용자’에게 Pro 라이선스가 필요합니다. 

Azure Portal에서 A SKU를 구매하려면 다음 단계를 수행합니다.

1. Power BI에서 최소한 용량 관리자 권한이 있는 계정으로 [Azure Portal](https://portal.azure.com)에 로그인합니다.

1. _Power BI Embedded_ 를 검색하고 검색 결과에서 서비스를 선택합니다.

    ![Azure Portal 검색](media/service-admin-premium-purchase/azure-portal-search.png)

1. **Power BI Embedded 만들기**를 선택합니다.

    ![Power BI Embedded 만들기](media/service-admin-premium-purchase/create-power-bi-embedded.png)

1. **Power BI Embedded** 만들기 화면에서 다음 정보를 지정합니다.

    - Power BI Embedded 서비스를 만들려는 **구독**

    - 서비스를 포함하는 리소스 그룹을 만들려는 물리적 **위치**. 성능 향상을 위해 이 위치는 Power BI의 Azure Active Directory 테넌트 위치에 가까워야 합니다.

    - 사용할 기존 **리소스 그룹**. 또는 예제와 같이 새 리소스 그룹을 만듭니다.

    - **Power BI 용량 관리자**. 용량 관리자는 Azure AD 테넌트의 서비스 주체 또는 멤버 사용자여야 합니다.

    ![구독 및 리소스 그룹](media/service-admin-premium-purchase/subscription-resource-group.png)

1. 무제한 공유를 제외한 Power BI Premium의 모든 기능을 사용하려면 최소한 A4 SKU가 필요합니다. **크기 변경**을 선택합니다.

    ![용량 크기 변경](media/service-admin-premium-purchase/change-capacity-size.png)

1. P1, P2, P3에 해당하는 A4, A5 또는 A6 용량 크기를 선택합니다.

    ![A3 용량 선택](media/service-admin-premium-purchase/select-a3-capacity.png)

1. **검토 + 만들기**를 선택하고 선택한 옵션을 검토한 다음, **만들기**를 선택합니다.

    ![리소스 만들기](media/service-admin-premium-purchase/create-resource.png)

1. 배포가 완료될 때까지 몇 분 정도 걸릴 수 있습니다. 준비되면 **리소스로 이동**을 선택합니다.

    ![배포 완료](media/service-admin-premium-purchase/deployment-complete.png)

1. 관리 화면에서 사용하지 않을 때 서비스 일시 중지를 포함하여 사용 가능한 서비스 관리 옵션을 검토합니다.

    ![용량 관리](media/service-admin-premium-purchase/manage-capacity.png)

용량을 구매한 후 [용량을 관리](service-admin-premium-manage.md#manage-capacity)하고 용량에 [작업 영역을 할당](service-admin-premium-manage.md#assign-a-workspace-to-a-capacity)하는 방법을 알아봅니다.

## <a name="next-steps"></a>다음 단계

[Power BI Premium에서 용량 구성 및 관리](service-admin-premium-manage.md)\
[Power BI 가격 책정 페이지](https://powerbi.microsoft.com/pricing/)\
[Power BI Premium 계산기](https://powerbi.microsoft.com/calculator/)\
[Power BI Premium FAQ](service-premium-faq.md)\
[Power BI 엔터프라이즈 배포 계획 백서](https://aka.ms/pbienterprisedeploy)

궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](https://community.powerbi.com/)
