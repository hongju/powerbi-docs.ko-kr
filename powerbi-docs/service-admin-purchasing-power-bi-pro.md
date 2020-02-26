---
title: Power BI Pro 라이선스 구매 및 할당
description: 사용자가 Power BI 서비스에서 콘텐츠에 액세스하고 다른 사용자와 공동 작업할 수 있도록 Power BI Pro 사용자 라이선스를 구매하고 사용자에게 할당하는 방법을 알아봅니다.
author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 01/16/2020
ms.author: kfollis
LocalizationGroup: Administration
ms.openlocfilehash: 138173d30b9c37c04047c61dbd04cbd3101696aa
ms.sourcegitcommit: 8e3d53cf971853c32eff4531d2d3cdb725a199af
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "76753194"
---
# <a name="purchase-and-assign-power-bi-pro-user-licenses"></a>Power BI Pro 사용자 라이선스 구매 및 할당

>[!IMPORTANT]
>Power BI Pro 라이선스로 업그레이드할 준비가 되셨습니까? [Power BI Pro 시작](https://go.microsoft.com/fwlink/?LinkId=2106428&clcid=0x409&cmpid=pbidocs-purchasing-power-bi-pro)으로 직접 이동하여 계정을 설정합니다.

Power BI Pro는 다른 사용자가 Power BI 서비스 게시한 보고서 및 대시보드를 읽고 상호 작용할 수 있도록 하는 개별 사용자 라이선스입니다. 이 라이선스 유형이 있는 사용자는 다른 Power BI Pro 사용자와 콘텐츠를 공유하고 공동 작업할 수 있습니다. 콘텐츠가 Power BI Premium 용량에 호스트되지 않은 한 Power BI Pro 사용자만 콘텐츠를 게시하거나 다른 사용자와 공유하거나 다른 사용자가 만든 콘텐츠를 사용할 수 있습니다. 자세한 내용은 [Power BI 가격](https://powerbi.microsoft.com/pricing/)의 _Power BI 기능 비교_ 섹션을 참조하세요.

## <a name="purchase-power-bi-pro-user-licenses"></a>Power BI Pro 사용자 라이선스 구매

이 문서에서는 Microsoft 365 관리 센터에서 Power BI Pro 사용자 라이선스를 구매하는 방법을 설명합니다. 라이선스를 구매한 후 Microsoft 365 관리 센터 또는 Azure Portal에서 사용자에게 라이선스를 할당할 수 있습니다.

> [!NOTE]
> 2020년 1월 14일부터 미국의 상용 클라우드 고객은 Power Platform 제품(Power BI, Power Apps, Power Automate)의 셀프 서비스 구매, 구독, 라이선스 관리 기능을 사용할 수 있습니다. 조직에서 셀프 서비스 구매를 사용 또는 사용하지 않도록 설정하는 단계를 비롯한 자세한 내용은 [셀프 서비스 구매 FAQ](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/self-service-purchase-faq)를 참조하세요.

### <a name="prerequisites"></a>필수 조건

Microsoft 365 관리 센터에서 라이선스를 구매하고 할당하려면 Microsoft 365에서 **[전역 관리자 또는 대금 청구 관리자](https://support.office.com/article/about-office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)** 역할의 구성원이어야 합니다.

Azure Portal에서 라이선스를 할당하려면 Power BI에서 Azure Active Directory 조회에 사용하는 Azure 구독의 소유자여야 합니다.

### <a name="purchase-licenses-in-microsoft-365"></a>Microsoft 365에서 라이선스 구매

Microsoft 365 관리 센터에서 Power BI Pro 라이선스를 구매하려면 다음 단계를 수행합니다.

1. [Microsoft 365 관리 센터](https://admin.microsoft.com)에 로그인합니다.

2. 탐색 메뉴에서 **청구** > **서비스 구매**를 선택합니다.

3. 구매할 구독을 검색하거나 스크롤해 찾습니다. 페이지 아래쪽의 **관심을 가질 만한 기타 범주**에서 **Power BI**를 찾을 수 있습니다. 조직에서 사용할 수 있는 Power BI 구독을 보려면 링크를 선택합니다.

4. **Power BI Pro**를 선택합니다.

5. **서비스 구매** 페이지에서 **구매**를 선택합니다.

6. 원하는 결제 방식에 따라 **월정액** 또는 **1년 결제**를 선택합니다.

7. **원하는 사용자 수**에 구매할 라이선스 수를 입력한 다음 **지금 체크 아웃**을 선택해 트랜잭션을 완료합니다.

8. 구매를 확인하려면 **청구** > **제품 및 서비스**로 이동해 **Power BI Pro**를 찾습니다.

9. 나중에 라이선스를 추가하려면 **제품 및 서비스** 페이지에서 **Power BI Pro**를 찾은 다음 **라이선스 추가/제거**를 선택합니다.

## <a name="assign-licenses-in-the-microsoft-365-admin-center"></a>Microsoft 365 관리 센터에서 라이선스 할당

Microsoft 365 관리 센터에서 라이선스를 할당하는 방법에 대한 자세한 내용은 [사용자에게 라이선스 할당](/office365/admin/manage/assign-licenses-to-users)을 참조하세요.

게스트 사용자의 경우 [라이선스 페이지에서 사용자에게 라이선스 할당](/office365/admin/manage/assign-licenses-to-users#assign-licenses-to-users-on-the-licenses-page)을 참조하세요. 게스트 사용자에게 Pro 라이선스를 할당하기 전에 Microsoft 계정 담당자에게 문의하여 Microsoft 계약 조건을 준수하고 있는지 확인합니다.

## <a name="assign-licenses-in-the-azure-portal"></a>Azure Portal에서 라이선스 할당

다음 단계를 수행하여 개별 사용자 계정에 Power BI Pro 라이선스를 할당합니다.

1. [Azure Portal](https://portal.azure.com/)에 로그인합니다.

2. **Azure Active Directory**를 검색하고 선택합니다.

3. **Azure Active Directory** 리소스 메뉴의 **관리**에서 **라이선스**를 선택합니다.

4. **라이선스 - 개요** 리소스 메뉴에서 **모든 제품**을 선택한 다음 **Power BI Pro**를 선택하여 허가된 사용자 목록을 표시합니다.

5. 명령 모음에서 **+할당**을 선택합니다. **라이선스 할당** 페이지에서 먼저 사용자를 선택한 다음 **할당 옵션**을 선택하여 선택된 사용자 계정에 대해 Power BI Pro 라이선스를 설정합니다.

## <a name="next-steps"></a>다음 단계

이제 라이선스를 할당했으므로 Power BI Pro에 대해 자세히 알아봅니다.

[조직의 Power BI 라이선스 부여](service-admin-licensing-organization.md)

[로그인한 Power BI 사용자 찾기](service-admin-access-usage.md)

궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](https://community.powerbi.com/)
