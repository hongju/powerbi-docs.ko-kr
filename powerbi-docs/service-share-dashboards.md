---
title: 동료 및 다른 사용자와 Power BI 대시보드 및 보고서 공유
description: 조직 내외부의 동료와 Power BI 대시보드 및 보고서를 공유하는 방법 및 공유에 대한 필수 고려 사항
author: maggiesMSFT
ms.reviewer: lukaszp
featuredvideoid: 0tUwn8DHo3s
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 11/26/2019
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: e6e66a4459abefbc66ec4e70b882cddc4771facf
ms.sourcegitcommit: a21f7f9de32203e3a4057292a24ef9b5ac6ce94b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/27/2019
ms.locfileid: "74565669"
---
# <a name="share-power-bi-dashboards-and-reports-with-coworkers-and-others"></a>동료 및 다른 사용자와 Power BI 대시보드 및 보고서 공유
다른 사람에게 대시보드 및 보고서에 대한 액세스 권한을 부여하려면 *공유*를 사용하는 것이 좋습니다. Power BI는 [대시보드 및 보고서를 공동 작업하고 배포하는 여러 가지 다른 방법](service-how-to-collaborate-distribute-dashboards-reports.md)도 제공합니다.

![대시보드 목록에서 공유 아이콘](media/service-share-dashboards/power-bi-share-new-look.png)

콘텐츠를 조직 내부와 공유하든 또는 외부와 공유하든, 공유하려면 [Power BI Pro 라이선스](service-features-license-type.md)가 필요합니다. 콘텐츠가 [프리미엄 용량](service-premium-what-is.md)에 있는 경우가 아니면 수신자도 Power BI Pro 라이선스가 필요합니다. 

즐겨찾기, 최근 항목, 공유한 항목(소유자가 허용한 경우), 내 작업 영역, 기타 작업 영역 등 Power BI 서비스의 대부분의 위치에서 대시보드와 보고서를 공유할 수 있습니다. 작업 영역에서 [관리자, 구성원 또는 참가자 역할](service-new-workspaces.md#roles-in-the-new-workspaces)을 하는 경우에도 다른 작업 영역에서 공유할 수 있습니다. 

대시보드 또는 보고서를 공유할 경우 공유받은 사람들은 대시보드 또는 보고서를 보고 조작할 수 있지만 편집할 수는 없습니다. [RLS(행 수준 보안)](service-admin-rls.md)를 적용하지 않는 한 다른 사용자는 사용자가 대시보드 또는 보고서에서 확인할 수 있는 동일한 데이터를 봅니다. 허용하는 경우 사용자와 항목을 공유하는 동료는 자신의 동료와도 공유할 수 있습니다. 조직 외부 사람들도 대시보드 또는 보고서를 보고 상호 작용할 수는 있지만, 공유할 수는 없습니다. 

Power BI Desktop에서 직접 *공유*할 수 없습니다. Power BI 서비스에 [Power BI Desktop의 보고서를 게시](desktop-upload-desktop-files.md)합니다. 하지만 [Power BI 모바일 앱에서 대시보드를 공유](consumer/mobile/mobile-share-dashboard-from-the-mobile-apps.md)할 수 있습니다.  

## <a name="video-share-a-dashboard"></a>비디오: 대시보드 공유
Amanda가 Amanda 회사 내부 및 외부의 동료와 대시보드를 공유하는 과정을 시청합니다. 그런 다음, 비디오 아래에 있는 단계별 지침을 따라서 직접 시도해 볼 수 있습니다.

<iframe width="560" height="315" src="https://www.youtube.com/embed/0tUwn8DHo3s?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

## <a name="share-a-dashboard-or-report"></a>대시보드 또는 보고서 공유

1. 대시보드 또는 보고서 목록이나 열린 대시보드 또는 보고서에서 **공유** 아이콘 ![공유 아이콘](media/service-share-dashboards/power-bi-share-icon.png)을 선택합니다.

2. 맨 위 상자에서 개인에 대한 전체 메일 주소, 메일 그룹 또는 보안 그룹을 입력합니다. 동적 메일 그룹과 공유할 수 없습니다. 
   
   주소가 조직 외부에 있는 사용자와 공유할 수 있지만 경고가 표시됩니다. 이 문서에서는 [조직 외부에서 공유](#share-a-dashboard-or-report-outside-your-organization)에 대해 자세히 알아보세요.
   
   ![외부에서 공유에 대한 경고](media/service-share-dashboards/power-bi-share-dialog-warning.png) 
 
   >[!NOTE]
   >입력 상자는 최대 100명의 개별 사용자 또는 그룹을 지원합니다. 더 많은 사람과 공유하는 방법에 대한 자세한 내용은 이 문서의 [100명 이상의 사용자와 공유](#share-with-more-than-100-separate-users)를 참조하세요.

3. 원하는 경우 메시지를 추가합니다. 선택 사항입니다.
4. 동료가 자신의 콘텐츠를 다른 사용자와 공유할 수 있게 하려면 **수신자가 대시보드(또는 보고서)를 공유하도록 허용**을 선택합니다.
   
   다른 사용자가 공유할 수 있도록 허용하는 작업을 *다시 공유*라고 합니다. 허용하는 경우 해당 사용자는 Power BI 서비스와 모바일 앱에서 다시 공유하거나 조직에서 다른 사용자에게 전자 메일 초대를 전달할 수 있습니다. 이 초대는 한 달 후에 만료됩니다. 조직 외부 사용자는 다시 공유할 수 없습니다. 콘텐츠 소유자는 다시 공유를 끄거나 개인별로 다시 공유를 해지할 수 있습니다. 이 문서에서 [공유 중지 또는 변경](#stop-or-change-sharing)을 참조하세요.

5. **기본 데이터 세트를 사용하여 사용자의 새 콘텐츠 빌드를 허용**을 선택하는 경우 이 대시보드의 데이터 세트를 기반으로 다른 작업 영역에서 사용자가 자체 보고서를 만들 수 있습니다. [다른 작업 영역의 데이터 세트를 기반으로 보고서 만들기](service-datasets-discover-across-workspaces.md)에 대해 자세히 알아보세요.

1. **공유**를 선택합니다.
   
   ![공유 단추 선택](media/service-share-dashboards/power-bi-share-dialog-share.png)  
   
   Power BI에서 공유 콘텐츠의 링크가 포함된 메일 초대를 그룹이 아닌 개인에게 보냅니다. **성공** 알림이 표시됩니다. 
   
   조직에서 받는 사람이 링크를 클릭하는 경우 Power BI에서 대시보드 또는 보고서를 해당 **공유한 항목** 목록 페이지에 추가합니다. 사용자의 이름을 선택하여 공유한 콘텐츠를 모두 볼 수 있습니다. 
   
   ![공유한 항목 목록 페이지](media/service-share-dashboards/power-bi-shared-with-me-new-look.png)
   
   조직 외부의 받는 사람이 링크를 클릭하면 대시보드 또는 보고서가 표지되지만 일반적인 Power BI 포털에는 표시되지 않습니다. 이 문서에서 [조직 외부 사용자와 공유](#share-a-dashboard-or-report-outside-your-organization)에 대해 자세히 알아보세요.

## <a name="see-who-has-access-to-a-dashboard-or-report"></a>대시보드 또는 보고서에 액세스할 사람 보기
경우에 따라 공유한 사용자를 확인하고 해당 사용자가 공유한 사람을 확인해야 합니다.

1. 대시보드 및 보고서 목록 또는 대시보드나 보고서 자체에서 **공유** 아이콘 ![공유 아이콘](media/service-share-dashboards/power-bi-share-icon.png)을 선택합니다. 
2. **대시보드 공유** 또는 **보고서 공유** 대화 상자에서 **액세스**를 선택합니다.
   
    ![대시보드 공유 대화 상자, 액세스 탭](media/service-share-dashboards/power-bi-share-dialog-access.png)

    조직 외부 사용자는 **게스트**로 표시됩니다.

    이 보기에서는, 이 문서의 [공유 권한을 중지하거나 변경](#stop-or-change-sharing)할 수 있습니다. 

## <a name="share-a-dashboard-or-report-outside-your-organization"></a>조직 외부에서 대시보드 또는 보고서 공유
조직 외부 사용자와 공유하는 경우, 해당 사용자가 공유 대시보드 또는 보고서에 대한 링크가 포함된 메일을 전송합니다. 공유한 항목을 확인하려면 Power BI에 로그인해야 합니다. Power BI Pro 라이선스가 없는 경우, 링크를 클릭하여 라이선스를 등록할 수 있습니다.

로그인하면 일반적인 Power BI 포털이 아닌 자체 브라우저 창에 공유 대시보드 또는 보고서가 표시됩니다. 나중에 이 대시보드 또는 보고서에 액세스하려면 링크를 책갈피에 추가해야 합니다.

이 대시보드 또는 보고서의 어떤 내용도 편집할 수 없습니다. 차트를 조작하고 필터 또는 슬라이서를 변경할 수 있지만, 변경 내용을 저장할 수는 없습니다. 

직접적인 수신자만 공유 대시보드 또는 보고서를 봅니다. 예를 들어, Vicki@contoso.com에게 메일을 보낸 경우 Vicki만 대시보드를 봅니다. Vicki가 링크를 전달하는 경우에도 다른 사용자는 대시보드를 볼 수 없습니다. Vicki는 동일한 메일 주소를 사용하여 대시보드에 액세스해야 합니다. Vicki가 다른 메일 주소로 로그인하는 경우 대시보드에 액세스할 수 없습니다.

역할 또는 행 수준 보안이 온-프레미스 Analysis Services 테이블 형식 모델에서 구현된 경우 조직 외부 사용자에게는 데이터가 전혀 표시되지 않습니다.

Power BI 모바일 앱에서 조직 외부의 사용자에게 링크를 보낼 경우, 링크를 클릭하면 Power BI 모바일 앱이 아닌 브라우저에서 대시보드가 열립니다.

### <a name="allow-external-users-to-edit-content"></a>외부 사용자가 콘텐츠를 편집할 수 있도록 허용

Power BI 관리자는 외부 게스트 사용자가 조직의 콘텐츠를 편집하고 관리할 수 있도록 허용할 수 있습니다. 그런 경우, 외부 사용자에게 소비 전용 환경이 제공되지 않습니다. 해당 사용자는 조직의 콘텐츠를 편집하고 관리할 수 있습니다. [Azure AD B2B를 사용하여 외부 게스트 사용자에게 Power BI 콘텐츠를 배포하는 방법](service-admin-azure-ad-b2b.md)에 대해 자세히 알아보세요.

## <a name="stop-or-change-sharing"></a>공유 중지 또는 변경
대시보드 또는 보고서 소유자만 다시 공유를 켜고 끌 수 있습니다.

### <a name="if-you-havent-sent-the-sharing-invitation-yet"></a>공유 초대를 아직 보내지 않은 경우
* 보내기 전에 초대장 맨 아래에 있는 **수신자가 대시보드(또는 보고서)를 공유하도록 허용** 확인란의 선택을 취소합니다.

### <a name="if-youve-already-shared-the-dashboard-or-report"></a>대시보드 또는 보고서를 이미 공유한 경우
1. 대시보드 및 보고서 목록 또는 대시보드나 보고서 자체에서 **공유** ![공유 아이콘](media/service-share-dashboards/power-bi-share-icon.png)을 선택합니다. 
2. **대시보드 공유** 또는 **보고서 공유** 대화 상자에서 **액세스**를 선택합니다.
   
    ![대시보드 공유 대화 상자, 액세스 탭](media/service-share-dashboards/power-bi-share-dialog-access.png)
3. **읽기 및 다시 공유** 옆에 있는 줄임표( **...** )를 선택하고 다음을 선택합니다.
   
   ![읽기 및 다시 공유 줄임표](media/service-share-dashboards/power-bi-change-access.png)
   
   * **읽기**는 해당 개인이 다른 사람과 공유하지 않도록 합니다.
   * **액세스 권한 제거**는 해당 사용자가 공유된 콘텐츠를 전혀 보지 못하도록 합니다.

4. **액세스 권한 제거** 대화 상자에서 보고서 및 데이터 세트와 같은 관련 콘텐츠에 대한 액세스도 제거할지 여부를 결정합니다. 경고 아이콘 ![Power BI 경고 아이콘](media/service-share-dashboards/power-bi-warning-icon.png)이 있는 항목을 제거할 경우 관련 콘텐츠도 함께 제거하는 것이 좋습니다. 그렇지 않으면 올바르게 표시되지 않습니다.

    ![Power BI 공유 경고 대화 상자](media/service-share-dashboards/power-bi-sharing-warning-dialog.png)

## <a name="limitations-and-considerations"></a>제한 사항 및 고려 사항
다음은 대시보드 및 보고서 공유에 관해 주의해야 할 점입니다.

* 일반적으로 사용자와 사용자의 동료는 대시보드 또는 보고서에서 동일한 데이터를 볼 수 있습니다. 따라서 사용자가 타인보다 더 많은 데이터를 볼 수 있는 권한을 가진 경우, 그들도 사용자의 대시보드 또는 보고서의 모든 데이터를 보게 됩니다. 그러나 [RLS(행 수준 보안)](service-admin-rls.md)가 대시보드 또는 보고서 바탕이 되는 데이터 세트에 적용된 경우 각 사용자의 자격 증명에 따라 해당 사용자가 액세스할 수 있는 데이터가 결정됩니다.
* 대시보드를 공유받은 모든 사용자는 대시보드를 보고 [읽기용 보기](consumer/end-user-reading-view.md#reading-view)에서 관련 보고서를 조작할 수 있습니다. 일반적으로, 보고서를 만들거나 기존 보고서에 변경 내용을 저장할 수는 없습니다. 그러나 **기본 데이터 세트를 사용하여 사용자의 새 콘텐츠 빌드를 허용**을 선택하는 경우 이 대시보드 또는 보고서의 데이터 세트를 기반으로 다른 작업 영역에서 사용자가 자체 보고서를 만들 수 있습니다.
* 누구도 데이터 세트를 다운로드하거나 볼 수는 없지만, Excel에서 분석 기능을 사용하여 데이터 세트에 직접 액세스할 수 있습니다. 관리자는 그룹의 모든 사용자에 대해 Excel에서 분석을 사용하는 기능을 제한할 수 있습니다. 이때 제한은 해당 그룹의 모든 사용자와 해당 그룹이 속한 모든 작업 영역에 적용됩니다.
* 모든 사용자는 수동으로 [데이터를 새로 고칠](refresh-data.md) 수 있습니다.
* Office 365를 메일에 사용하는 경우 메일 그룹과 연결된 메일 주소를 입력하여 메일 그룹의 멤버와 공유할 수 있습니다.
* 사용자의 메일 도메인을 공유하는 동료 및 도메인은 다르지만 동일한 테넌트에 등록된 동료는 다른 사용자와 대시보드를 공유할 수 있습니다. 예를 들어, contoso.com 및 contoso2.com 도메인이 동일한 테넌트에 등록되어 있고 메일 주소가 konrads@contoso.com이라고 가정합니다. ravali@contoso.com 및 gustav@contoso2.com에게 공유할 수 있는 권한을 부여한 경우, 해당 사용자가 사용자의 대시보드를 공유할 수 있습니다.
* 동료가 특정 대시보드 또는 보고서에 이미 액세스할 수 있고 사용자가 해당 대시보드 또는 보고서에 있는 경우 URL을 복사하여 직접 링크를 보낼 수 있습니다. 예: `https://powerbi.com/dashboards/g12466b5-a452-4e55-8634-xxxxxxxxxxxx`.
* 마찬가지로, 동료가 특정 대시보드에 대한 액세스 권한을 가진 경우 [기본 보고서의 직접 링크를 전송](service-share-reports.md)할 수 있습니다. 

### <a name="share-with-more-than-100-separate-users"></a>100명 이상의 개별 사용자와 공유

단일 공유 작업으로 최대 100명의 사용자 또는 그룹과 공유할 수 있습니다. 그러나 한 항목에 대한 액세스 권한을 500명이 넘는 사용자에게 부여할 수 있습니다. 다음은 몇 가지 제안 사항입니다.

- 사용자를 개별적으로 지정하여 여러 번 공유합니다.
- 모든 사용자를 포함하는 사용자 그룹과 공유합니다. 
- 작업 영역에서 보고서 또는 대시보드를 만든 다음, 작업 영역에서 앱을 만듭니다. 앱을 더 많은 사람들과 공유할 수 있습니다. [Power BI에서 앱을 게시하는 방법](service-create-distribute-apps.md)에 대해 자세히 알아보세요.

## <a name="troubleshoot-sharing"></a>공유 문제 해결

### <a name="my-dashboard-recipients-see-a-lock-icon-in-a-tile-or-a-permission-required-message"></a>내 대시보드를 받는 사람에게 타일 또는 “사용 권한 필요” 메시지에 잠금 아이콘이 표시됩니다.

공유받은 사람이 보고서를 보려고 할 때 대시보드의 잠긴 타일 또는 “사용 권한 필요” 메시지가 표시될 수 있습니다.

![Power BI 잠긴 타일](media/service-share-dashboards/power-bi-locked_tile_small.png)

이 경우 기본 데이터 세트에 대한 권한을 부여해야 합니다.

1. 콘텐츠 목록에 있는 **데이터 세트** 탭으로 이동합니다.

1. 데이터 세트 옆에 있는 줄임표( **...** )와 **사용 권한 관리**를 차례로 선택합니다.

    ![권한 관리](media/service-share-dashboards/power-bi-sharing-manage-permissions.png)

1. **사용자 추가**를 선택합니다.

    ![사용자 추가 선택](media/service-share-dashboards/power-bi-share-dataset-add-user.png)

1. 개인에 대한 전체 메일 주소, 메일 그룹 또는 보안 그룹을 입력합니다. 동적 메일 그룹과 공유할 수 없습니다.

    ![전자 메일 주소 추가](media/service-share-dashboards/power-bi-add-user-dataset.png)


1. **추가**를 선택합니다.

### <a name="i-cant-share-a-dashboard-or-report"></a>대시보드 또는 보고서를 공유할 수 없음

대시보드 또는 보고서를 공유하려면 기본 콘텐츠, 즉 모든 관련 보고서 및 데이터 세트를 다시 공유할 수 있는 권한이 있어야 합니다. 공유할 수 없다는 메시지가 표시되면 보고서 작성자에게 해당 보고서 및 데이터 세트에 대한 다시 공유 권한을 요청합니다.

!["공유할 수 없습니다." 메시지](media/service-share-dashboards/power-bi-sharing-unable-to-share.png)


## <a name="next-steps"></a>다음 단계

* [대시보드 및 보고서를 공동 작업 및 공유하는 방법](service-how-to-collaborate-distribute-dashboards-reports.md)
* [필터링된 Power BI 보고서 공유](service-share-reports.md)
* 궁금한 점이 더 있나요? [Power BI 커뮤니티를 이용하세요.](https://community.powerbi.com/)

