---
title: Power BI 외부 게스트 사용자 (Azure AD B2B)로 콘텐츠 보기
description: Power BI 모바일 앱을 사용 하 여 외부 조직의 사용자와 공유 하는 콘텐츠를 볼 수 있습니다.
author: mshenhav
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: conceptual
ms.date: 03/27/2019
ms.author: mshenhav
ms.openlocfilehash: a15da4349ce97e34c8321909abc862e424b2839c
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "61338773"
---
# <a name="view-power-bi-content-shared-with-you-from-an-external-organization"></a>외부 조직의 사용자와 공유 하는 Power BI 콘텐츠 보기

Power BI는 Azure Active Directory-비즈니스 조직 외부 게스트 사용자에 게 Power BI 콘텐츠를 안전 하 게 배포할 수 있도록 (Azure AD B2B)와 통합 됩니다. 및 외부 게스트 사용자 동료와 공유 하는 Power BI 콘텐츠에 액세스 하기 위한 Power BI 모바일 앱을 사용할 수 있습니다. 


적용 대상:

| ![iPhone](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/iphone-logo-50-px.png) | ![iPad](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/ipad-logo-50-px.png) | ![Android 휴대폰](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/android-phone-logo-50-px.png) | ![Android 태블릿](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/android-tablet-logo-50-px.png) |
|:--- |:--- |:--- |:--- |
| iPhone |iPad |Android 휴대폰 |Android 태블릿 |

## <a name="accessing-shared-content"></a>공유 콘텐츠 액세스

**첫째, 공유한 항목을 외부 조직의 사용자가 필요 합니다.** 사람이 들어오면 [된 항목 공유](../../service-share-dashboards.md), 항목 공유에 대 한 링크를 사용 하 여 메일을 받게 같은 조직 또는 외부 조직의 합니다. 모바일 장치에서 해당 링크를 따라 Power BI 모바일 앱을 엽니다. 앱 항목 외부 조직에서 공유 된 있음을 인식 하는 경우 앱 id 사용 하 여 해당 조직에 다시 연결 합니다. 앱에서 해당 조직의 사용자와 공유 된 모든 항목을 로드 합니다.

![Power BI는 전자 메일에서 공유 항목 열기 ](./media/mobile-apps-b2b/mobile-b2b-open-item-email.png)

> [!NOTE]
> 외부 게스트 사용자로 사용자와 공유 하는 첫 번째 항목의 경우 브라우저에서 초대를 클레임 해야 합니다. Power BI 앱에 초대를 요청할 수 없습니다 수 있습니다.

외부 조직에 연결할으로 검은색 헤더를 앱에 표시 됩니다. 이 헤더 홈 조직에 연결 되지 않은 것을 나타냅니다. 홈 조직에 다시 연결 하려면 게스트 모드를 종료 합니다.

![Power BI 게스트 사용자 헤더](./media/mobile-apps-b2b/mobile-b2b-exit-home.png)

Power BI 아티팩트 링크 앱 전환 되 면 외부 조직에 연결 해야 하는 경우에 있습니다 (뿐만 아니라 전자 메일에서 열린 항목)를 사용 하 여 공유 되는 모든 항목을 액세스할 수 있습니다. 외부 조직에서 모든 항목에 액세스할 수 있습니다를 보려면 앱 메뉴로 이동 하 고 선택 **공유한**합니다. 아래 **앱** 도 사용할 수 있는 앱을 찾습니다.

![외부 게스트 사용자로 power BI 앱 메뉴](./media/mobile-apps-b2b/mobile-b2b-menu.png)

## <a name="limitations"></a>제한 사항

- Power BI mobile에서 Azure AD B2B에 대 한 조건부 액세스 및 기타 Intune 정책을 지원 되지 않습니다. 즉, 있는 경우 앱 홈 조직의 정책만 적용 하 합니다.
- 홈 조직을 통해서만 사이트에서 푸시 알림을 받은 (도 경우 사용자가 연결 된 외부 조직에 게 게스트로). 알림을 열고 앱 사용자의 홈 조직 사이트로 다시 연결 합니다.
- 사용자가 앱을 종료 하는 경우 때 다시 사용자의 홈 조직에 앱이 자동으로 연결 하는 열입니다.
- 외부 조직에 연결 하는 경우 일부 동작이 해제: 즐겨찾기 항목, 데이터 경고에 주석 달기 및 공유 합니다.
- 오프 라인 데이터를 외부 조직에 연결 되어 있는 동안에 사용할 수 없는 경우
- 회사 포털 앱이 장치에서 설치에 있는 경우 장치가 등록 되어야 합니다.
