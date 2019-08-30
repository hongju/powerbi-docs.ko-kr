---
title: 외부 게스트 사용자로 Power BI 콘텐츠 보기(Azure AD B2B)
description: Power BI Mobile 앱을 사용하여 외부 조직에서 자신과 공유된 콘텐츠를 볼 수 있습니다.
author: mshenhav
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: conceptual
ms.date: 03/27/2019
ms.author: mshenhav
ms.openlocfilehash: 900c7b57c2b6283c44e4a1923dd223d7dfd40ef7
ms.sourcegitcommit: d9755602235ba03594c348571b9102c9bf88d732
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69490363"
---
# <a name="view-power-bi-content-shared-with-you-from-an-external-organization"></a>외부 조직에서 자신과 공유된 Power BI 콘텐츠 보기

Power BI는 Azure AD B2B(Azure Active Directory Business-to-Business)와 통합되므로 조직 외부의 게스트 사용자에게 Power BI 콘텐츠를 안전하게 배포할 수 있습니다. 또한 외부 게스트 사용자가 Power BI Mobile 앱을 사용하여 자신과 공유된 Power BI 콘텐츠에 액세스할 수 있습니다. 


적용 대상:

| ![iPhone](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/iphone-logo-50-px.png) | ![iPad](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/ipad-logo-50-px.png) | ![Android 휴대폰](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/android-phone-logo-50-px.png) | ![Android 태블릿](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/android-tablet-logo-50-px.png) |
|:--- |:--- |:--- |:--- |
| iPhone |iPad |Android 휴대폰 |Android 태블릿 |

## <a name="accessing-shared-content"></a>공유 콘텐츠 액세스

**먼저 외부 조직의 누군가가 사용자와 항목을 공유해야 합니다.** 누군가가 동일한 조직이나 외부 조직에서 [항목을 공유](../../service-share-dashboards.md)하면, 해당 공유 항목의 링크가 포함된 메일을 받게 됩니다. 모바일 디바이스에서 해당 링크를 따르면 Power BI Mobile 앱이 열립니다. 외부 조직에서 항목이 공유된 것으로 인식하면, 앱은 사용자 ID를 사용하여 해당 조직에 다시 연결합니다. 그런 다음, 해당 조직에서 사용자와 공유된 모든 항목을 로드합니다.

![Power BI 메일에서 공유 항목 열기 ](./media/mobile-apps-b2b/mobile-b2b-open-item-email.png)

> [!NOTE]
> 외부 게스트 사용자로 자신과 공유된 첫 번째 항목인 경우 브라우저에서 초대를 클레임해야 합니다. Power BI 앱에서는 초대를 클레임할 수 없습니다.

외부 조직에 연결되어 있으면 앱에 검은색 헤더가 표시됩니다. 이 헤더는 홈 조직에 연결되어 있지 않음을 나타냅니다. 홈 조직에 다시 연결하려면 게스트 모드에서 종료합니다.

![Power BI 게스트 사용자 헤더](./media/mobile-apps-b2b/mobile-b2b-exit-home.png)

외부 조직에 연결하려면 Power BI 아티팩트 링크가 있어야 하지만, 앱이 전환되고 나면 메일에서 열린 항목뿐만 아니라 자신과 공유된 모든 항목에 액세스할 수 있습니다. 외부 조직에서 액세스할 수 있는 모든 항목을 보려면 앱 메뉴로 이동하여 **공유한 항목**을 선택합니다. **앱**에서도 사용할 수 있는 앱을 찾을 수 있습니다.

![Power BI 게스트 외부 사용자로 액세스한 앱 메뉴](./media/mobile-apps-b2b/mobile-b2b-menu.png)

## <a name="limitations"></a>제한 사항

- 사용자에게 활성 Power BI 계정과 홈 테넌트가 있어야 합니다.
- 사용자가 먼저 Power BI 홈 테넌트에 로그인해야 외부 테넌트에서 자신과 공유된 콘텐츠에 액세스할 수 있습니다.
- 조건부 액세스 및 기타 Intune 정책은 Azure AD B2B 및 Power BI Mobile에서 지원되지 않습니다. 즉, 앱에서 홈 조직의 정책만 적용합니다(있는 경우).
- 사용자가 외부 조직에 게스트로 연결된 경우에도 홈 조직 사이트의 푸시 알림이 수신됩니다. 알림을 열면 앱이 사용자의 홈 조직 사이트에 다시 연결됩니다.
- 사용자가 앱을 종료하면 앱이 다시 열릴 때 사용자의 홈 조직에 자동으로 연결됩니다.
- 외부 조직에 연결된 경우에는 즐겨찾기 항목, 데이터 경고, 주석 달기, 공유 등의 일부 작업을 사용할 수 없습니다.
- 외부 조직에 연결된 동안에는 오프라인 데이터를 사용할 수 없습니다.
- 디바이스에 회사 포털 앱이 설치되어 있으면 디바이스를 등록해야 합니다.
