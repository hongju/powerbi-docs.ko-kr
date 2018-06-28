---
title: Power BI 모바일 앱의 특정 위치에 대한 링크 만들기
description: Power BI 모바일 앱에서 URI(Uniform Resource Identifier)를 사용하여 특정 대시보드, 타일 또는 보고서에 대한 딥 링크를 만드는 방법에 대해 알아봅니다.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-mobile
ms.topic: conceptual
ms.date: 10/13/2017
ms.author: maggies
ms.openlocfilehash: 3be6882219e23a2d22ee03e6805ce3a1e8e08b8f
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2018
ms.locfileid: "34297725"
---
# <a name="create-a-link-to-a-specific-location-in-the-power-bi-mobile-apps"></a>Power BI 모바일 앱의 특정 위치에 대한 링크 만들기
모든 모바일 플랫폼에서 Power BI 모바일 앱(예: iOS, Android 장치 및 Windows 10) 내에 특정 위치(*딥 링크*)에 연결하려면 URI(Uniform Resource Identifier)를 만들고 사용할 수 있습니다.

URI 링크는 대시보드, 타일 및 보고서를 직접 가리킬 수 있습니다.

딥 링크의 대상은 URI의 형식을 결정합니다. 다른 위치로 딥 링크를 만들려면 다음 단계를 수행합니다. 

## <a name="open-the-power-bi-mobile-app"></a>Power BI 모바일 앱 열기
이 URI를 사용하여 모든 장치에서 Power BI 모바일 앱 열기

    mspbi://app/


## <a name="open-to-a-specific-dashboard"></a>특정 대시보드 열기
이 URI는 특정 대시보드로 Power BI 모바일 앱을 엽니다.

    mspbi://app/OpenDashboard?DashboardObjectId=<36-character-dashboard-id>

36자의 대시보드 개체 ID를 찾으려면 Power BI 서비스 (https://powerbi.com) 의 특정 대시보드로 이동합니다. 예를 들어 이 URL의 강조 표시된 섹션을 참조합니다.

https://powerbi.com/groups/me/dashboards/**61b7e871-cb98-48ed-bddc-6572c921e270**

대시보드가 내 작업 영역 아닌 그룹에 있다면 대시보드 ID 앞이나 뒤에 `&GroupObjectId=<36-character-group-id>`을(를) 추가합니다. 예를 들어 

mspbi://app/OpenDashboard?DashboardObjectId=e684af3a-9e7f-44ee-b679-b9a1c59b5d60 **&GroupObjectId=8cc900cc-7339-467f-8900-fec82d748248**

두 가지 사이에 앰퍼샌드(&)를 참조하세요.

## <a name="open-to-a-specific-tile-in-focus"></a>포커스에서 특정 타일에 열기
이 URI는 Power BI 모바일 앱에서 포커스에 특정 타일을 엽니다.

    mspbi://app/OpenTile?DashboardObjectId=<36-character-dashboard-id>&TileObjectId=<36-character-tile-id>

36자의 대시보드 및 타일 개체 ID를 찾으려면 Power BI 서비스 (https://powerbi.com) 의 특정 대시보드로 이동하여 포커스 모드에서 타일을 엽니다. 예를 들어 다음 URL에서 강조 표시된 섹션을 참조하세요.

https://powerbi.com/groups/me/dashboards/**3784f99f-b460-4d5e-b86c-b6d8f7ec54b7**/tiles/**565f9740-5131-4648-87f2-f79c4cf9c5f5**/infocus

이 타일에 대한 URI은 다음과 같습니다.

    mspbi://app/OpenTile?DashboardObjectId=3784f99f-b460-4d5e-b86c-b6d8f7ec54b7&TileObjectId=565f9740-5131-4648-87f2-f79c4cf9c5f5

두 가지 사이에 앰퍼샌드(&)를 참조하세요.

대시보드가 내 작업 영역 아닌 그룹에 있는 경우 `&GroupObjectId=<36-character-group-id>`을(를) 추가하세요.

## <a name="open-to-a-specific-report"></a>특정 보고서에 열기
이 URI는 Power BI 모바일 앱에서 특정 보고서를 엽니다.

    mspbi://app/OpenReport?ReportObjectId=<36-character-report-id>

36자의 보고서 개체 ID를 찾으려면 Power BI 서비스 (https://powerbi.com) 의 특정 보고서로 이동합니다. 예를 들어 이 URL의 강조 표시된 섹션을 참조합니다.

https://powerbi.com/groups/me/reports/**df9f0e94-31df-450b-b97f-4461a7e4d300**

## <a name="open-to-a-specific-report-page"></a>특정 보고서 페이지에 열기
이 URI는 Power BI 모바일 앱에서 특정 보고서 페이지를 엽니다.

    mspbi://app/OpenReport?ReportObjectId=<36-character-report-id>&reportPage=ReportSection<number>

보고서 페이지는 "ReportSection"(뒤에 숫자가 따라옴)이라고 합니다. 다시 말해 Power BI 서비스 (https://powerbi.com) 의 보고서를 열고 특정 보고서 페이지로 이동합니다. 

예를 들어 이 URL의 강조 표시된 섹션을 참조합니다.

https://powerbi.com/groups/me/reports/df9f0e94-31df-450b-b97f-4461a7e4d300/**ReportSection11**

## <a name="open-in-full-screen-mode"></a>전체 화면 모드로 열기
굵게 표시된 매개 변수를 추가하여 전체 화면 모드로 특정 보고서를 엽니다.

    mspbi://app/OpenReport?ReportObjectId=<36-character-report-id>**&openFullScreen=true**

예: 

mspbi://app/OpenReport?ReportObjectId=500217de-50f0-4af1-b345-b81027224033&openFullScreen=true

## <a name="add-context-optional"></a>컨텍스트 추가(선택 사항)
문자열에 컨텍스트를 추가할 수도 있습니다. 그런 다음 문의해야 하는 경우 해당 컨텍스트를 사용하여 데이터를 앱으로 필터링할 수 있습니다. 링크에 `&context=<app-name>`을 추가합니다.

예를 들어 이 URL의 강조 표시된 섹션을 참조합니다. 

https://powerbi.com/groups/me/reports/df9f0e94-31df-450b-b97f-4461a7e4d300/**&context=SlackDeepLink**

## <a name="next-steps"></a>다음 단계
사용자 의견은 나중에 구현할 사항을 결정하는 데 도움이 됩니다. 따라서 Power BI 모바일 앱에서 참조하고자 하는 다른 기능에 대해 꼭 투표해주세요. 

* [모바일 장치용 Power BI 앱](mobile-apps-for-mobile-devices.md)
* Twitter에서 @MSPowerBI 팔로우
* [Power BI 커뮤니티](http://community.powerbi.com/)에서 대화에 참여
* [Power BI 시작](service-get-started.md)

