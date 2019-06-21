---
title: Power BI에 앱 게시
description: 기본 제공 탐색 기능이 있는 대시보드 및 보고서 컬렉션인 새 앱을 게시하는 방법에 대해 알아봅니다.
author: maggiesMSFT
manager: kfile
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/20/2019
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: eccda071b6c6abc92640024c3587bafa71038dee
ms.sourcegitcommit: c122c1a8c9f502a78ccecd32d2708ab2342409f0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/11/2019
ms.locfileid: "66826623"
---
# <a name="publish-an-app-in-power-bi"></a>Power BI에 앱 게시

Power BI에서 공식 패키지 콘텐츠를 만든 다음, *앱*을 통해 광범위한 잠재 고객에게 배포할 수 있습니다. *앱 작업 영역*에서 앱을 만듭니다. 여기서 동료와 Power BI 콘텐츠에 대해 공동 작업할 수 있습니다. 그런 다음, 조직의 대규모 사용자 그룹에 완성된 앱을 게시할 수 있습니다. 

![Power BI 앱](media/service-create-distribute-apps/power-bi-new-apps.png)

비즈니스 사용자는 비즈니스를 실행하기 위해 여러 Power BI 대시보드 및 보고서가 필요한 경우가 많습니다. Power BI 앱을 사용하면 대시보드 및 보고서의 컬렉션을 만들고 이러한 앱을 전체 조직 또는 특정 사람 또는 그룹에 게시할 수 있습니다. 보고서 작성자 또는 관리자인 경우 앱을 사용하면 이러한 컬렉션에 대한 사용 권한을 더 쉽게 관리할 수 있습니다.

비즈니스 사용자는 몇 가지 방법으로 앱을 가져옵니다.

- Microsoft AppSource에서 앱을 찾아 설치할 수 있습니다.
- 직접 링크를 보낼 수 있습니다.
- Power BI 관리자가 사용자에게 사용 권한을 부여한 경우 동료의 Power BI 계정에서 해당 앱을 자동으로 설치할 수 있습니다.

고유의 기본 제공 탐색 기능을 사용하여 앱을 만들 수 있으므로 사용자는 자신의 콘텐츠를 쉽게 찾을 수 있습니다. 앱의 콘텐츠를 수정할 수 없습니다. Power BI 서비스 또는 모바일 앱 중 하나인 데이터 필터링, 강조 표시 및 정렬에서 이 서비스와 상호 작용할 수 있습니다. 업데이트를 자동으로 가져오므로, 데이터 새로 고침 빈도를 조절할 수 있습니다. [비즈니스 사용자의 앱 환경](consumer/end-user-apps.md)에 대해 자세히 알아보기

## <a name="licenses-for-apps"></a>앱에 대한 라이선스
앱을 만들거나 업데이트하려면 Power BI Pro 라이선스가 필요합니다. 앱 *소비자*의 경우 두 가지 옵션이 있습니다.

* 옵션 1: 모든 비즈니스 사용자는 **Power BI Pro** 라이선스가 있어야 앱을 볼 수 있습니다. 
* 옵션 2: 앱 작업 영역이 Power BI Premium 용량에 있는 경우 조직의 무료 사용자가 앱 콘텐츠를 볼 수 있습니다. 자세한 내용은 [Power BI 프리미엄이란?](service-premium.md)을 참조하세요.

## <a name="publish-your-app"></a>앱 게시
작업 영역의 대시보드 및 보고서가 준비되면 게시하려는 대시보드 및 보고서를 선택한 다음, 앱으로 게시합니다. 

1. 작업 영역 목록 보기에서 **앱에 포함할** 대시보드와 보고서를 결정합니다.

     ![게시할 대시보드 선택](media/service-create-distribute-apps/power-bi-apps-incude-dashboard.png)

     관련 대시보드가 있는 보고서를 포함하지 않도록 선택하면 보고서 옆에 경고가 표시됩니다. 앱을 게시할 수는 있지만 관련 대시보드에는 해당 보고서의 타일이 없습니다.

     ![관련 대시보드에 대한 경고](media/service-create-distribute-apps/power-bi-apps-report-warning.png)

2. 오른쪽 위에서 **앱 게시** 단추를 선택하여 작업 영역에서 앱을 만들고 게시하는 프로세스를 시작합니다.
   
     ![앱 게시](media/service-create-distribute-apps/power-bi-apps-publish-button.png)

3. **설치**에서 사용자가 앱을 찾을 수 있도록 이름과 설명을 입력합니다. 테마 색을 설정하여 개인화할 수 있습니다. 지원 사이트에 링크를 추가할 수도 있습니다.
   
     ![앱 빌드](media/service-create-distribute-apps/power-bi-apps-build-your-apps.png)

4. **탐색**에서 앱의 일부로 게시할 콘텐츠를 선택합니다. 그런 다음, 앱 탐색을 추가하여 섹션에서 콘텐츠를 구성합니다. 자세한 내용은 이 문서의 [앱에 대한 탐색 환경 디자인](#design-the-navigation-experience-for-your-app)을 참조하세요.
   
     ![앱 탐색](media/service-create-distribute-apps/power-bi-apps-navigation.png)

5. **권한**에서 앱에 액세스할 수 있는 사용자와 수행할 수 있는 작업을 결정합니다. 
    - [클래식 작업 영역](service-create-workspaces.md): 조직의 모든 사용자, 특정 사용자 또는 AAD(Azure Active Directory) 보안 그룹.
    - [새 환경 작업 영역](service-create-the-new-workspaces.md): 특정 사용자, AAD 보안 그룹, 배포 목록 및 Office 365 그룹. 모든 작업 영역 사용자에게는 앱 작업 영역의 앱에 대한 액세스가 자동으로 부여됩니다.
    - 빌드 권한을 사용하여 앱 사용자가 앱의 기본 데이터 세트에 연결할 수 있도록 할 수 있습니다. 이러한 데이터 세트는 데이터 세트 검색 환경에 표시됩니다.
    - 앱 사용자가 이 앱의 보고서를 자신의 [내 작업 영역]에 복사할 수 있도록 허용할 수 있습니다. 
    
    >[!IMPORTANT]
    >앱이 다른 작업 영역 데이터 세트를 사용하는 경우 모든 앱 사용자가 기본 데이터 세트에 액세스할 수 있도록 해야 합니다.
> 
>     


6. Power BI 관리자가 Power BI 관리 포털에서 이 설정을 사용하도록 설정한 경우 수신인에게 앱을 자동으로 설치할 수 있습니다. 이 문서의 [앱을 자동으로 설치](#automatically-install-apps-for-end-users)하는 방법에 대해 자세히 알아봅니다.

     ![앱 사용 권한](media/service-create-distribute-apps/power-bi-apps-permissions.png)

7. **앱 게시**를 선택하면 게시할 준비가 되었음을 확인하는 메시지가 나타납니다. **이 앱 공유** 대화 상자에서 이 앱에 직접 연결되는 URL을 복사할 수 있습니다.
   
     ![앱 완료](media/service-create-distribute-apps/power-bi-apps-success.png)

공유한 사용자에게 직접 링크를 보내거나 **AppSource에서 더 많은 앱 다운로드 및 탐색**으로 이동하여 앱 탭에서 앱을 찾을 수 있습니다. [비즈니스 사용자의 앱 환경](consumer/end-user-apps.md)에 대해 자세히 알아보기

## <a name="change-your-published-app"></a>게시된 앱 변경
앱 게시 후, 변경하거나 업데이트하고 싶을 수 있습니다. 새 앱 작업 영역의 관리자 또는 구성원인 경우 업데이트하기 쉽습니다. 

1. 앱에 해당하는 앱 작업 영역을 엽니다. 
   
     ![작업 영역 열기](media/service-create-distribute-apps/power-bi-apps-open-workspace.png)

2. 대시보드 또는 보고서에 원하는 내용을 변경합니다.
 
     앱 작업 영역은 스테이징 영역이므로 다시 게시할 때까지 앱의 변경 내용은 반영되지 않습니다. 이를 통해 게시된 앱에 영향을 미치지 않고 변경 사항을 적용할 수 있습니다.  
 
    > [!IMPORTANT]
    > 보고서를 제거하고 앱을 업데이트하면 보고서를 다시 앱에 추가하더라도 앱 소비자는 책갈피, 주석 등 모든 사용자 지정을 잃게 됩니다.  
 
3. 콘텐츠의 앱 작업 영역 목록으로 돌아가서 오른쪽 상단 모서리에서 **앱 업데이트**를 선택합니다.
   
1. 필요한 경우 **설치**, **탐색** 및 **권한**을 업데이트한 다음, **앱 업데이트**를 선택합니다.
   
해당 앱을 게시한 사람들은 자동으로 업데이트된 버전의 앱을 보게 됩니다. 

## <a name="design-the-navigation-experience-for-your-app"></a>앱에 대한 탐색 환경 디자인
**새 탐색 작성기** 옵션을 사용하면 앱에 대한 사용자 지정 탐색을 빌드할 수 있습니다. 사용자 지정 탐색을 사용하면 사용자가 앱에서 콘텐츠를 쉽게 찾고 사용할 수 있습니다. 기존 앱은 이 옵션을 해제하고 새 앱은 기본적으로 실행 중인 옵션으로 설정됩니다.

옵션이 해제된 경우 **앱 방문 페이지**를 **특정 콘텐츠**(예: 대시보드 또는 보고서)로 선택하거나 **없음**을 선택하여 사용자에게 기본 콘텐츠 목록을 표시할 수 있습니다.

**새 탐색 작성기**를 켜면 사용자 지정 탐색을 디자인할 수 있습니다. 기본적으로 앱에 포함된 모든 보고서, 대시보드 및 Excel 통합 문서는 일반 목록으로 나열됩니다. 

![앱 탐색](media/service-create-distribute-apps/power-bi-apps-navigation.png)

다음을 통해 앱 탐색을 추가로 사용자 지정할 수 있습니다.
* 위쪽 / 아래쪽 화살표를 사용하여 항목을 재정렬합니다. 
* **보고서 세부 정보**, **대시보드 세부 정보** 및 **통합 문서 세부 정보**의 항목의 이름을 변경합니다.
* 탐색에서 특정 항목을 숨깁니다.
* **새로 만들기** 옵션을 사용하여 **섹션**을 추가하여 관련 콘텐츠를 그룹화합니다.
* **새로 만들기** 옵션을 사용하여 외부 리소스에 **링크**를 왼쪽 탐색에 추가합니다. 

**링크**를 추가할 때 **링크 세부 정보**에서 링크가 열리는 위치를 선택할 수 있습니다. 기본적으로 **현재 탭**에서 링크가 열리지만 **새 탭** 또는 **콘텐츠 영역**을 선택할 수 있습니다. 

### <a name="considerations-for-using-the-new-navigation-builder-option"></a>새 탐색 작성기 옵션 사용 시 고려 사항
새 탐색 작성기를 사용할 때 유의해야 할 일반적인 사항은 다음과 같습니다.
* 보고서 페이지는 앱 탐색 영역의 확장 가능한 섹션으로 표시됩니다.
* 새 탐색 작성기를 해제한 다음, 앱을 게시하거나 업데이트하면 만든 사용자 지정이 손실됩니다. 예를 들어 탐색 항목의 섹션, 정렬, 링크 및 사용자 지정 이름이 모두 손실됩니다.

앱 탐색에 링크를 추가하고 콘텐츠 영역 옵션을 선택하는 경우:
* 링크가 포함될 수 있는지 확인합니다. 일부 서비스는 Power BI와 같은 타사 사이트에서 해당 콘텐츠를 포함하는 것을 차단합니다.
* 보고서 또는 대시보드와 같은 Power BI 서비스 콘텐츠를 다른 작업 영역에 포함시키는 것은 지원되지 않습니다. 
* 온-프레미스 배포에서 기본 포함 URL 콘텐츠를 통해 Power BI Report Server 콘텐츠를 포함합니다. [Power BI Report Server URL 만들기](https://docs.microsoft.com/power-bi/report-server/quickstart-embed#creating-the-power-bi-report-server-report-url)의 단계를 수행하여 URL을 가져옵니다. 일반 인증 규칙이 적용되므로 콘텐츠를 보려면 온-프레미스 서버에 VPN 연결이 필요합니다. 
* 포함된 콘텐츠의 상단에 콘텐츠가 Power BI에 없지 않음을 나타내는 보안 경고가 표시됩니다.



## <a name="automatically-install-apps-for-end-users"></a>최종 사용자에 대해 자동으로 앱 설치
관리자가 권한을 부여하면 앱을 자동으로 설치하여 최종 사용자에게 *푸시*할 수 있습니다. 이 푸시 기능을 사용하면 적합한 앱을 올바른 사용자나 그룹에 더 쉽게 배포할 수 있습니다. 최종 사용자의 앱 콘텐츠 목록에서 앱이 자동으로 표시됩니다. Microsoft AppSource에서 찾거나 설치 링크를 따를 필요가 있습니다. Power BI 관리자 포털 문서에서 관리자가 [최종 사용자에게 앱을 푸시](service-admin-portal.md#push-apps-to-end-users)할 수 있는 방법을 참조하세요.

### <a name="how-to-push-an-app-automatically-to-end-users"></a>최종 사용자에게 앱을 자동으로 푸시하는 방법
관리자가 사용 권한을 할당하면 **앱을 자동으로 설치**하는 새로운 옵션이 표시됩니다. 상자를 확인하고 **앱 게시**(또는 **앱 업데이트**)을 선택하면 앱은 **액세스** 탭에 있는 앱의 **사용 권한** 섹션에서 정의된 모든 사용자 또는 그룹에 푸시됩니다.

![앱 푸시 설정](media/service-create-distribute-apps//power-bi-apps-access.png)

### <a name="how-users-get-the-apps-that-you-push-to-them"></a>사용자가 푸시된 앱을 가져오는 방법
앱을 푸시하면 앱 목록에 자동으로 표시됩니다. 이러한 방식으로 조직의 특정 사용자 또는 작업 역할이 필요로 하는 앱을 손쉽게 관리할 수 있습니다.

![앱 푸시 설정](media/service-create-distribute-apps/power-bi-apps-left-nav.png)

### <a name="considerations-for-automatically-installing-apps"></a>앱을 자동으로 설치하기 위한 고려 사항
앱을 최종 사용자에게 푸시할 때 유의할 사항은 다음과 같습니다.

* 사용자에게 앱을 자동으로 설치하는 데는 시간이 걸릴 수 있습니다. 대부분의 앱은 사용자를 위해 즉시 설치되지만 앱을 푸시하는 데는 시간이 걸릴 수 있습니다.  소요 시간은 앱에 있는 항목의 수 및 액세스 권한이 부여된 사용자의 수에 따라 다릅니다. 사용자가 필요로 하기 전에 업무 외 시간 동안 앱을 푸시하는 것이 좋습니다. 앱의 가용성에 대한 광범위 통신을 보내기 전에 몇몇 사용자를 통해 확인합니다.

* 브라우저를 새로 고칩니다. 앱 목록에서 푸시된 앱을 표시하기 전에 사용자를 새로 고치거나 해당 브라우저를 닫았다가 다시 열어야 합니다.

* 사용자가 앱 목록에서 앱을 즉시 확인하지 못하면, 브라우저를 새로 고침하거나 또는 닫고 다시 열어야 합니다.

* 사용자에게 과도한 부하가 걸리지 않도록 하세요. 사용자가 미리 설치된 앱이 유용함을 인식할 수 있도록 너무 많은 앱을 푸시하지 않도록 합니다. 타이밍을 조정하기 위해 최종 사용자에게 앱을 푸시할 수 있는 사용자를 제어하는 것이 좋습니다. 최종 사용자에게 푸시된 조직의 앱을 가져오기 위한 연락처를 설정합니다.

* 초대를 수락하지 않은 게스트 사용자에게는 자동으로 앱이 설치되지 않습니다.  

## <a name="allowing-users-to-connect-to-the-apps-underlying-datasets"></a>사용자가 앱의 기본 데이터 세트에 연결할 수 있도록 허용
모든 사용자가 앱의 기본 데이터 세트에 연결할 수 있도록 하는 옵션을 선택하면 앱 사용자가 기본 데이터 세트에 대한 빌드 권한을 받습니다. 이를 통해 사용자는 [작업 영역에서 앱 데이터 세트를 사용](service-datasets-across-workspaces.md)하여 Power BI Desktop에서 이러한 데이터 세트를 검색하고, 서비스에서 데이터 환경을 가져오고, 이러한 데이터 세트를 사용하여 보고서와 대시보드를 만들 수 있습니다. 

이 옵션을 선택 취소하면 앱에 추가하는 새 사용자에게 빌드 권한이 더 이상 제공되지 않습니다. 그러나 기본 데이터 세트의 기존 사용 권한은 변경되지 않습니다. 제공된 사용자 인터페이스를 사용하여 빌드 권한을 더 이상 보유하지 않아야 하는 앱 사용자로부터 수동으로 제거할 수 있습니다. [빌드 권한](service-datasets-build-permissions.md#build-permissions-for-shared-datasets)에 대해 자세히 알아봅니다.

## <a name="allowing-users-to-make-a-copy-of-the-reports-in-the-app"></a>사용자가 앱에서 보고서의 복사본을 만들 수 있도록 허용
**이 앱에서 사용자가 보고서의 복사본을 만들 수 있도록 허용**하는 옵션을 선택하면 사용자가 앱의 모든 보고서를 자신의 [내 작업 영역]에 저장할 수 있습니다. 그런 다음, 보고서의 고유한 요구에 맞게 보고서를 사용자 지정할 수 있습니다. 이 옵션을 사용하려면 **빌드 권한을 사용하여 앱 사용자가 앱의 기본 데이터 세트에 연결하도록 허용**해야 합니다. 이 기능은 새로운 [다른 작업 영역에서 보고서 복사](service-datasets-copy-reports.md) 기능처럼 작동합니다.

## <a name="unpublish-an-app"></a>앱 게시 취소
앱 작업 영역의 모든 멤버는 앱 게시를 취소할 수 있습니다.

>[!IMPORTANT]
>앱 게시를 취소하면 앱 사용자의 사용자 지정 정보가 손실됩니다. 모든 개인 책갈피, 의견 또는 앱의 콘텐츠를 사용하여 연결된 구독을 잃게 됩니다. 앱을 제거해야 할 경우에만 앱 게시를 취소합니다.
> 
> 

* 앱 작업 영역의 오른쪽 위 모서리 &gt; 줄임표( **...** )에서 **앱 게시 취소**를 선택합니다.
  
     ![앱 게시 취소](media/service-create-distribute-apps/power-bi-app-unpublish.png)

이 작업은 게시된 모든 사용자의 앱을 제거하고 더 이상 액세스 권한을 갖지 않습니다. 앱 작업 영역 또는 해당 내용을 삭제하지 않습니다.

## <a name="view-your-published-app"></a>게시된 앱 보기

앱 소비자가 앱을 열면, 표준 Power BI 왼쪽 탐색 창 대신 사용자가 만든 탐색이 표시됩니다. 앱 탐색에는 정의한 섹션에서 보고서와 대시보드가 나열됩니다. 또한 보고서 이름이 아니라 각 보고서의 개별 페이지가 나열됩니다.

![탐색이 있는 앱](media/service-create-distribute-apps/power-bi-new-apps-navigation.png)

## <a name="next-steps"></a>다음 단계
* [앱 작업 영역 만들기](service-create-workspaces.md)
* [Power BI에서 앱 설치 및 사용](consumer/end-user-apps.md)
* [외부 서비스용 Power BI 앱](service-connect-to-services.md)
* [Power BI 관리 포털](https://docs.microsoft.com/power-bi/service-admin-portal)
* 궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](http://community.powerbi.com/)
