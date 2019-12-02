---
title: Power BI로 Zendesk에 연결
description: Power BI용 Zendesk
author: maggiesMSFT
manager: kfile
ms.reviewer: sarinas
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 04/26/2019
ms.author: maggies
LocalizationGroup: Connect to services
ms.openlocfilehash: 1edc4179b000191dfeff87387417009bc28e0ee5
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "64578801"
---
# <a name="connect-to-zendesk-with-power-bi"></a>Power BI로 Zendesk에 연결

이 문서에서는 Power BI 템플릿 앱을 사용 하 여 Zendesk 계정에서 데이터를 끌어오는 안내 합니다. Zendesk 앱에는 Power BI 대시보드 및 티켓 볼륨 및 에이전트 성능에 대 한 정보를 제공 하는 Power BI 보고서 집합을 제공 합니다. 하루에 한 번 자동으로 데이터가 새로 고쳐집니다. 

템플릿 앱을 설치한 후 대시보드 및 보고서를 가장 하는 방법에 대 한 중요 한 정보를 강조 표시를 사용자 지정할 수 있습니다. 그런 다음 조직의 동료에 게 앱으로 배포할 수 있습니다.

[Zendesk 콘텐츠 팩](https://app.powerbi.com/getdata/services/zendesk)에 연결하거나 Power BI와의 [Zendesk 통합](https://powerbi.microsoft.com/integrations/zendesk)에 대해 자세히 알아보세요.

템플릿 앱을 설치한 후에 대시보드 및 보고서를 변경할 수 있습니다. 그런 다음 조직의 동료에 게 앱으로 배포할 수 있습니다.

>[!NOTE]
>연결 하려면 Zendesk 관리자 계정이 필요 합니다. [요구 사항](#system-requirements)에 대한 자세한 내용은 아래에 나와 있습니다.

## <a name="how-to-connect"></a>연결 방법

[!INCLUDE [powerbi-service-apps-get-more-apps](./includes/powerbi-service-apps-get-more-apps.md)]

3. 선택 **Zendesk** \> **지금**합니다.
4. **Power BI 앱이 설치?** 선택 **설치**합니다.
4. 에 **앱** 창 합니다 **Zendesk** 타일입니다.

    ![Power BI Zendesk 앱 타일](media/service-connect-to-zendesk/power-bi-zendesk-tile.png)

6. **새 앱을 시작 하세요**를 선택 **데이터 연결**합니다.

    ![새 앱 시작](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-connect-data.png)

4. 계정과 연결된 URL을 제공합니다. 에 URL의 형식은 **https://company.zendesk.com** 합니다. 아래에서 [해당 매개 변수 찾기](#finding-parameters)에 대한 세부 정보를 참조하세요.
   
   ![Zendesk에 연결](media/service-connect-to-zendesk/pbi_zendeskconnect.png)

5. 메시지가 표시되면 Zendesk 자격 증명을 입력합니다.  **oAuth 2** 를 인증 메커니즘으로 선택하고 **로그인**을 클릭합니다. Zendesk 인증 흐름을 따릅니다. (이미 로그인 Zendesk에 브라우저를 하는 경우 있습니다 하지 묻는 자격 증명에 대 한.)
   
   > [!NOTE]
   > 이 콘텐츠 팩은 Zendesk 관리자 계정으로 연결 하는 필요 합니다. 
   > 
   
   ![OAuth2 사용 하 여 로그인](media/service-connect-to-zendesk/pbi_zendesksignin.png)
6. **허용**을 클릭하여 Power BI가 Zendesk 데이터에 액세스할 수 있도록 합니다.
   
   ![클릭 허용](media/service-connect-to-zendesk/zendesk2.jpg)
7. **연결**을 클릭하여 가져오기 프로세스를 시작합니다. 
8. Zendesk 앱에 대 한 콘텐츠 목록이 표시 Power BI가 데이터를 가져오면: 새 대시보드, 보고서 및 데이터 집합입니다.
9. 탐색 프로세스를 시작 하려면 대시보드를 선택 합니다.

    ![Zendesk 대시보드](media/service-connect-to-zendesk/power-bi-zendesk-dashboard.png)
   
## <a name="modify-and-distribute-your-app"></a>수정, 앱 배포

Zendesk 템플릿 앱을 설치 했습니다. 즉, Zendesk 앱 작업 영역도 만들었습니다. 작업 영역에서 보고서 및 대시보드를 다음으로 배포를 *앱* 조직의 동료에 게 합니다. 

1. 왼쪽된 탐색 모음에서 새 Zendesk 작업 영역의 모든 콘텐츠를 보려면 선택 **작업 영역** > **Zendesk**합니다. 

    ![왼쪽된 탐색 창에서 Zendesk 작업 영역](media/service-connect-to-zendesk/power-bi-zendesk-workspace-left-nav.png)

    이 보기에는 작업 영역 콘텐츠 목록입니다. 오른쪽 위 모서리에 표시 **앱 업데이트**합니다. 동료에 게 앱을 배포할 준비가 있는 경우 시작할 수 있습니다. 

    ![Zendesk 콘텐츠 목록](media/service-connect-to-zendesk/power-bi-zendesk-content-list.png)

2. 선택 **보고서** 하 고 **데이터 집합** 작업 영역에서 다른 요소를 확인 합니다.

    읽어보세요 [앱 배포](service-create-distribute-apps.md) 동료에 게 합니다.

## <a name="system-requirements"></a>시스템 요구 사항
Zendesk 콘텐츠 팩에 액세스하려면 Zendesk 관리자 계정이 필요합니다. 에이전트 또는 최종 사용자와 Zendesk 데이터를 보기에 관심이 있다면 제안 사항을 추가 하 고에서 Zendesk 커넥터를 검토 합니다 [Power BI Desktop](desktop-connect-to-data.md)합니다.

## <a name="finding-parameters"></a>매개 변수 찾기
Zendesk URL은 Zendesk 계정에 로그인하는 데 사용하는 URL과 동일합니다. Zendesk URL을 잘 모를 경우 Zendesk [로그인 도움말](https://www.zendesk.com/login/)을 사용할 수 있습니다.

## <a name="troubleshooting"></a>문제 해결
연결 하는 데 문제가 하는 경우 Zendesk URL을 확인 하 고 Zendesk 관리자 계정을 사용 하는 확인 합니다.

## <a name="next-steps"></a>다음 단계

* [Power BI에서 새 작업 영역 만들기](service-create-the-new-workspaces.md)
* [Power BI에서 앱 설치 및 사용](consumer/end-user-apps.md)
* [외부 서비스용 Power BI 앱에 연결](service-connect-to-services.md)
* 궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](http://community.powerbi.com/)

