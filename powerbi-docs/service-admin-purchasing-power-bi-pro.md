---
title: Power BI Pro 라이선스 구매 및 할당
description: 사용자가 Power BI 서비스에서 콘텐츠에 액세스하고 동료와 협업할 수 있도록 Power BI Pro 사용자 라이선스를 구매하고 할당하는 방법을 알아봅니다.
author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: quickstart
ms.date: 12/18/2019
ms.author: kfollis
LocalizationGroup: Administration
ms.openlocfilehash: 01eb30857b0b76f96e7e18115d92fb1d68dbef0c
ms.sourcegitcommit: 02b05932a119527f255e1eacc745a257044e392f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/19/2019
ms.locfileid: "75223819"
---
# <a name="purchase-and-assign-power-bi-pro-user-licenses"></a>Power BI Pro 사용자 라이선스 구매 및 할당

Power BI Pro는 Power BI 서비스에서 다른 사용자가 게시한 보고서와 대시보드를 사용자가 읽고 조작하는 것은 물론 다른 Power BI Pro 사용자와 콘텐츠를 공유하고 협업할 수 있게 해주는 개별 사용자 라이선스입니다. 콘텐츠가 Power BI Premium 용량에 호스트되지 않은 경우, Power BI Pro 사용자 라이선스가 있는 사용자만 콘텐츠를 게시하거나, 다른 사용자와 공유하거나, 다른 사용자가 만든 콘텐츠를 사용할 수 있습니다. 자세한 내용은 [Power BI 가격](https://powerbi.microsoft.com/pricing/)의 _Power BI 기능 비교_ 섹션을 참조하세요.

## <a name="purchase-and-assign-power-bi-pro-user-licenses"></a>Power BI Pro 사용자 라이선스 구매 및 할당

이 문서에서는 Microsoft 365 관리 센터에서 Power BI Pro 사용자 라이선스를 구매하는 방법과 관리자가 개별 사용자에게 해당 라이선스를 할당하는 데 사용할 수 있는 두 가지 옵션을 설명합니다. 즉, Microsoft 365 관리 센터 및 Azure Portal 옵션 중 하나를 선택할 수 있습니다.

### <a name="prerequisites"></a>필수 조건

Microsoft 365 관리 센터에서 라이선스를 구매하고 할당하려면 Microsoft 365에서 **[전역 관리자 또는 대금 청구 관리자](https://support.office.com/article/about-office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)** 역할의 구성원이어야 합니다.

Azure Portal에서 라이선스를 할당하려면 Power BI에서 Azure Active Directory 조회에 사용하는 Azure 구독의 소유자여야 합니다.

### <a name="purchase-licenses-in-microsoft-365"></a>Microsoft 365에서 라이선스 구매

Microsoft 365 관리 센터에서 Power BI Pro 라이선스를 구매하려면 다음 단계를 수행합니다.

1. [Microsoft 365 관리 센터](https://portal.office.com/adminportal/home#/homepage)를 엽니다.

2. 탐색 창에서 **청구**를 선택한 다음, **구독**을 선택합니다.

3. **구독** 페이지의 오른쪽 위 모서리에서 **구독 추가**를 선택합니다.

4. 원하는 구독 제안을 찾습니다.

    - **엔터프라이즈용 제품군**에서 **Office 365 Enterprise E5**를 선택합니다.

    - **다른 계획**에서 **Power BI Pro**를 선택합니다.

5. 원하는 구독에서 줄임표( **. . .** )를 마우스로 가리키고 **지금 구매**를 선택합니다.

6. 청구에서 원하는 대로 **매월 결제** 또는 **1년 결제**를 선택합니다.

7. **원하는 사용자 수**에서 원하는 라이선스 수를 입력한 다음, **지금 확인**을 선택하여 트랜잭션을 완료합니다.

8. 이제 구매한 구독이 **구독** 페이지에 나열되는지 확인합니다.

9. 최초 구매 후에 더 많은 라이선스를 추가하려면 **구독** 페이지에서 **Power BI Pro**를 선택한 다음, **라이선스 수량 변경**을 선택합니다.

### <a name="assign-licenses-in-the-microsoft-365-admin-center"></a>Microsoft 365 관리 센터에서 라이선스 할당

Microsoft 365 관리 센터에서 라이선스를 할당하는 방법에 대한 자세한 내용은 [사용자에게 라이선스 할당](/office365/admin/manage/assign-licenses-to-users)을 참조하세요.

게스트 사용자의 경우 [라이선스 페이지에서 사용자에게 라이선스 할당](/office365/admin/manage/assign-licenses-to-users#assign-licenses-to-users-on-the-licenses-page)을 참조하세요. 게스트 사용자에게 Pro 라이선스를 할당하기 전에 Microsoft 계정 담당자에게 문의하여 Microsoft 계약 조건을 준수하고 있는지 확인합니다.

### <a name="assign-licenses-in-the-azure-portal"></a>Azure Portal에서 라이선스 할당

다음 단계를 수행하여 개별 사용자 계정에 Power BI Pro 라이선스를 할당합니다.

1. [Azure Portal](https://portal.azure.com/)을 엽니다.

2. **Azure Active Directory**를 검색하고 선택합니다.

3. **Azure Active Directory** 아래에서 **라이선스**를 선택합니다.

4. **라이선스** 아래에서 **모든 제품**을 선택한 다음, **Power BI Pro**를 선택하여 사용이 허가된 사용자 목록을 표시합니다.

5. **할당**을 선택하여 사용자 계정에 Power BI Pro 라이선스를 추가합니다.

## <a name="next-steps"></a>다음 단계

이제 라이선스를 할당했으므로 Power BI Pro에 대해 자세히 알아봅니다.

[조직의 Power BI 라이선스 부여](service-admin-licensing-organization.md)

[로그인한 Power BI 사용자 찾기](service-admin-access-usage.md)

궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](https://community.powerbi.com/)
