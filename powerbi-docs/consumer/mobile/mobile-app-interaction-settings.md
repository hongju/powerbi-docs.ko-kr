---
title: 보고서 상호 작용 설정 구성
description: 보고서의 기본 상호 작용 설정을 재정의하는 방법에 대해 알아봅니다.
author: paulinbar
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: conceptual
ms.date: 01/21/2020
ms.author: painbar
ms.openlocfilehash: fee89c65328b70e1f312b39fbad75d7148bd92f2
ms.sourcegitcommit: 02342150eeab52b13a37b7725900eaf84de912bc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2020
ms.locfileid: "76542292"
---
# <a name="configure-report-interaction-settings"></a>보고서 상호 작용 설정 구성

## <a name="overview"></a>개요

Power BI 모바일 앱에는 사용자가 데이터를 조작하는 방법을 제어하고 Power BI 모바일 앱의 일부 요소가 작동하는 방식을 정의할 수 있는 여러 가지 구성 가능한 “상호 작용” 설정이 있습니다. 현재 다음에 대한 설정이 있습니다.
* [보고서 시각적 개체에서 한 번 대 두 번 탭 상호 작용](#single-tap)
* [도킹 및 동적 보고서 바닥글](#docked-report-footer-android-phones)(Android)
* [단추로 시작되는 보고서 새로 고침과 당겨서 새로 고침](#report-refresh-android-phones)(Android)

상호 작용 설정에 대한 자세한 내용을 보려면 프로필 사진을 탭하여 [사이드 패널](./mobile-apps-home-page.md#header)을 열고 **설정**을 선택한 다음 **상호 작용** 섹션을 찾습니다.

![상호 작용 설정](./media/mobile-app-interaction-settings/powerbi-mobile-app-interactions-section.png)

>[!NOTE]
>새로 고침 단추 및 보고서 바닥글 고정에 대한 상호 작용 설정은 현재 보고서 서버 보고서에 영향을 주지 않습니다. 2020년 1월 보고서 서버 릴리스와 함께 변경됩니다.

## <a name="interaction-settings"></a>상호 작용 설정

### <a name="single-tap"></a>한 번 탭하기
Power BI 모바일 앱을 다운로드하면 단일 탭 상호 작용이 설정됩니다. 즉, 시각적 개체를 탭하여 슬라이서 항목 선택, 상호 강조 표시, 링크 또는 단추 클릭 등의 작업을 수행하는 경우 두 탭 모두 시각적 개체를 선택하고 원하는 작업을 수행합니다.

원하는 경우 단일 탭 상호 작용을 해제할 수 있습니다. 그런 다음 두 번 탭하여 상호 작용합니다. 두 번 탭 상호 작용을 사용하면 먼저 시각적 개체를 탭하여 선택한 다음 시각적 개체에서 다시 탭하여 원하는 작업을 수행합니다.

### <a name="docked-report-footer-android-phones"></a>고정된 보고서 바닥글(Android 휴대폰)

고정된 보고서의 바닥글 설정은 보고서의 아래쪽에 보고서 바닥글을 고정(예: 고정 및 항상 표시)할지 아니면 스크롤 등 보고서에서 수행하는 작업에 따라 숨기거나 다시 표시할지 방법을 결정합니다.

Android 휴대폰에서 고정된 보고서 바닥글 설정은 기본적으로 **켜짐**으로 설정됩니다. 즉, 보고서 바닥글은 보고서의 아래쪽에 고정되고 항상 표시됩니다. 보고서의 작업에 따라 동적 보고서 바닥글을 표시하고 사라지게 하려는 경우 설정을 **해제**로 전환하세요.

### <a name="report-refresh-android-phones"></a>보고서 새로 고침(Android 휴대폰)

보고서 새로 고침 설정은 보고서 새로 고침을 시작하는 방법을 정의합니다. 모든 보고서 헤더에 새로 고침 단추를 갖거나 보고서 페이지에서 당겨서 새로 고침 작업(위에서 아래로 약간 당기기)을 사용하여 보고서를 새로 고침합니다. 아래 그림에서는 두 가지 방법을 보여줍니다. 

![새로 고침 단추 및 당겨서 새로 고침](./media/mobile-app-interaction-settings/powerbi-mobile-app-interactions-refresh-button-versus-pull.png)

Android 휴대폰에서 새로 고침 단추는 기본적으로 추가됩니다.

보고서 새로 고침 설정을 변경하려면 상호 작용 설정에서 보고서 새로 고침 항목으로 이동합니다. 현재 설정이 표시됩니다. 값을 탭하여 새 값을 선택할 수 있는 팝업을 엽니다.

![새로 고침 설정](./media/mobile-app-interaction-settings/powerbi-mobile-app-interactions-set-refresh.png)

## <a name="remote-configuration"></a>원격 구성

관리자는 앱 구성 파일과 함께 MDM 도구를 사용하여 원격으로 상호 작용을 구성할 수도 있습니다. 이러한 방식으로 조직 전체 또는 조직의 특정 사용자 그룹에 대한 보고서 상호 작용 환경을 표준화할 수 있습니다. 자세한 내용은 [모바일 디바이스 관리를 사용하여 상호 작용 구성](./mobile-app-configuration.md)을 참조하세요.


## <a name="next-steps"></a>다음 단계
* [보고서 조작](./mobile-reports-in-the-mobile-apps.md#interact-with-reports)
* [모바일 디바이스 관리를 사용하여 상호 작용 구성](./mobile-app-configuration.md)
