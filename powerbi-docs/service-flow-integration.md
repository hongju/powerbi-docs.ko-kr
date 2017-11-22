---
title: "자습서: Power BI를 Microsoft Flow와 통합하기"
description: "Power BI 데이터 경고에 의해 트리거되는 Flow를 만드는 방법에 대해 알아봅니다."
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: YhmNstC39Mw
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/30/2017
ms.author: mihart
ms.openlocfilehash: efab2e6be1d376a0da70c13bb66144ba34afa58c
ms.sourcegitcommit: f2b38777ca74c28f81b25e2f739e4835a0ffa75d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2017
---
# <a name="microsoft-flow-and-power-bi"></a>Microsoft Flow 및 Power BI

[Microsoft Flow](https://flow.microsoft.com/en-us/documentation/getting-started)는 비즈니스 사용자가 사용하는 응용 프로그램 및 SaaS 서비스가 증가함에 따라 워크플로 자동화를 위해 제공되는 SaaS입니다. Flow를 사용하면 즐겨 찾는 앱과 서비스(Power BI 포함)를 통합하여 작업을 자동화함으로써 알림 가져오기, 파일 동기화, 데이터 수집 등을 수행할 수 있습니다. 워크플로 자동화를 사용하면 반복 작업이 쉬워집니다.

[이제 Flow를 사용하여 시작합니다.](https://flow.microsoft.com/documentation/getting-started)

Sirui에서 Power BI 경고가 트리거될 때 동료에게 자세한 전자 메일을 전송 하는 흐름을 만드는 것을 감시합니다. 그런 다음 비디오 아래에 있는 단계별 지침을 따라서 직접 시도해 볼 수 있습니다.

<iframe width="560" height="315" src="https://www.youtube.com/embed/YhmNstC39Mw" frameborder="0" allowfullscreen></iframe>

## <a name="create-a-flow-that-is-triggered-by-a-power-bi-data-alert"></a>Power BI 데이터 경고로 트리거하는 흐름 만들기
이 자습서에서는 흐름을 만드는 두 가지 방법, 즉 템플릿을 이용하는 방법과 처음부터 새로 만드는 방법을 보여줍니다. 과정을 따르려면 [Power BI에서 데이터 경고를 만들고](service-set-data-alerts.md) [Microsoft Flow에 등록합니다](https://flow.microsoft.com/en-us/#home-signup)(무료).

## <a name="create-a-flow-that-uses-power-bi---from-a-template"></a>Power BI를 사용하여 템플릿을 기반으로 하는 흐름 만들기
이 작업에서는 Power BI 데이터 경고(알림)에 의해 트리거되는 간단한 흐름을 만드는 템플릿을 사용합니다.

1. Microsoft Flow(flow.microsoft.com)에 로그인합니다.
2. **내 흐름**을 선택합니다.
   
   ![](media/service-flow-integration/power-bi-my-flows.png)
3. **템플릿에서 만들기**를 선택합니다.
   
    ![](media/service-flow-integration/power-bi-template.png)
4. Search 상자를 사용하여 Power BI 템플릿을 찾고 **Power BI 데이터 경고가 트리거될 때 Slack 채널에 메시지 게시**를 선택합니다.
   
    ![](media/service-flow-integration/power-bi-template2.png)
5. **이 템플릿 사용**을 선택합니다.
   
   ![](media/service-flow-integration/power-bi-use-template.png)
6. 메시지가 표시되면 **로그인**을 선택하여 Slack과 Power BI에 연결한 다음 지시를 따르십시오. 녹색 확인 표시는 로그인되어 있음을 알려줍니다.  사용자 연결을 확인한 후 **계속**을 선택합니다.
   
   ![](media/service-flow-integration/power-bi-flow-signin.png)

### <a name="build-the-flow"></a>흐름 작성
이 템플릿에는 트리거 1개(아일랜드의 새 올림픽 메달에 대한 Power BI 데이터 경고)와 작업 1개(Slack에 메시지 게시)가 있습니다. 필드를 선택하면 Flow는 포함시킬 수 있는 동적 콘텐츠를 표시합니다.  이 예에서 타일 값 및 타일 URL이 메시지 본문에 포함되어 있습니다.

![](media/service-flow-integration/power-bi-flow-template.png)

1. 트리거 드롭다운 목록에서 Power BI 데이터 경고를 선택합니다. **아일랜드의 새 메달**을 선택합니다. 경고를 만드는 방법을 알아보려면 [Power BI에서 데이터 경고](service-set-data-alerts.md)를 참조하세요.
   
   ![](media/service-flow-integration/power-bi-trigger-flow.png)
2. Slack에 게시하려면 채널 이름 및 메시지 텍스트를 입력합니다(흐름에서 만드는 기본 메시지를 선택할 수도 있음). 메시지 텍스트 필드에 포함된 동적 콘텐츠를 확인합니다.
   
   > [!NOTE]
   > 채널 이름의 시작 부분에 “@”를 포함합니다.  예를 들어, Slack 채널의 이름이 "channelA"인 경우 흐름에 “@channelA”를 입력합니다.
   > 
   > 
   
   ![](media/service-flow-integration/power-bi-flow-slacker.png)
3. 완료되면 **흐름 만들기** 또는 **흐름 저장**을 선택합니다.  흐름이 생성되고 평가가 이루어집니다.  Flow에서 오류를 발견하면 알려줍니다.
4. 오류가 발견되면 **흐름 편집**을 선택하여 오류를 해결하고 그렇지 않으면 **완료**를 선택하여 새 흐름을 실행합니다.
   
   ![](media/service-flow-integration/power-bi-flow-running.png)
5. Slack 계정을 열어 메시지를 봅니다.  
   
   ![](media/service-flow-integration/power-bi-slack-message.png)

## <a name="create-a-flow-that-uses-power-bi---from-scratch-blank"></a>Power BI를 사용하는 흐름(빈 값)을 새로 만들기
이 작업에서는 Power BI 데이터 경고(알림)에 의해 트리거되는 간단한 흐름을 처음부터 새로 만듭니다.

1. Microsoft Flow에 로그인합니다.
2. **내 흐름** > **빈 페이지에서 만들기**를 선택합니다.
   
   ![](media/service-flow-integration/power-bi-my-flows.png)
3. 검색 상자를 사용하여 Power BI 트리거를 찾고 **Power BI 데이터 기반 경고로 흐름 트리거**를 선택합니다.

### <a name="build-your-flow"></a>흐름 작성
1. 드롭다운 목록에서 경고의 이름을 선택합니다.  경고를 만드는 방법을 알아보려면 [Power BI에서 데이터 경고](service-set-data-alerts.md)를 참조하세요.
   
    ![](media/service-flow-integration/power-bi-totalstores.png)
2. **새 단계** > **작업 추가**를 선택합니다.
   
   ![](media/service-flow-integration/power-bi-new-step.png)
3. **Outlook**을 검색하고 **이벤트 만들기**를 선택합니다.
   
   ![](media/service-flow-integration/power-bi-create-event.png)
4. 이벤트 필드를 입력합니다. 필드를 선택하면 Flow는 포함시킬 수 있는 동적 콘텐츠를 표시합니다.
   
   ![](media/service-flow-integration/power-bi-flow-event.png)
5. 완료되면 **흐름 만들기**를 선택합니다.  Flow는 흐름을 저장하고 평가합니다. 오류가 없는 경우 이 흐름을 실행하려면 **완료**를 선택합니다.  새 흐름이 **내 흐름** 페이지에 추가됩니다.
   
   ![](media/service-flow-integration/power-bi-flow-running.png)
6. 흐름이 Power BI 데이터 경고에 의해 트리거되면 이와 유사한 Outlook 이벤트 알림을 받게 됩니다.
   
    ![](media/service-flow-integration/power-bi-flow-notice.png)

## <a name="next-steps"></a>다음 단계
* [Microsoft Flow 시작](https://flow.microsoft.com/en-us/documentation/getting-started/)
* [Power BI 서비스에서 데이터 경고 설정](service-set-data-alerts.md)
* [iPhone에서 데이터 경고 설정](mobile-set-data-alerts-in-the-mobile-apps.md)
* [Windows 10용 Power BI 모바일 앱의 데이터 경고 설정](mobile-set-data-alerts-in-the-mobile-apps.md)
* 궁금한 점이 더 있나요? [Power BI 커뮤니티를 이용하세요.](http://community.powerbi.com/)

