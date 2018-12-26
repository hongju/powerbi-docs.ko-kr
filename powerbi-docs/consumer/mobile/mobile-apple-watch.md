---
title: Apple Watch에서 모바일 앱의 Power BI 데이터 탐색
description: Power BI Apple Watch 앱
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-mobile
ms.topic: conceptual
ms.date: 10/13/2017
ms.author: maggies
ms.openlocfilehash: bb5257b801ddb8ff2269a102e4f6c299b1291df4
ms.sourcegitcommit: 67336b077668ab332e04fa670b0e9afd0a0c6489
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2018
ms.locfileid: "44742796"
---
# <a name="explore-your-data-in-the-power-bi-mobile-app-on-your-apple-watch"></a>Apple Watch에서 Power BI 모바일 앱의 데이터 탐색
Power BI Apple Watch 앱을 사용하여 시계에 있는 Power BI 대시보드에서 KPI 및 타일 카드을 볼 수 있습니다. KPI 및 카드 타일은 작은 화면에서 하트비트 측정값을 제공하는 데 가장 적합합니다. iPhone이나 Watch 자체에서 대시보드를 새로 고칠 수 있습니다.

## <a name="install-the-apple-watch-app"></a>Apple Watch 앱 설치
Power BI Apple Watch 앱은 iOS 앱용 Power BI를 제공하므로 [iPhone에 Power BI 앱을 다운로드](http://go.microsoft.com/fwlink/?LinkId=522062 "iPhone 앱을 다운로드")할 경우 Apple 앱 스토어에서 하면 Power BI Watch 앱을 자동으로 다운로드 합니다. Apple 설명서에서는 [Apple Watch 애플리케이션을 설치](https://support.apple.com/en-us/HT204784)하는 방법을 설명합니다.

## <a name="use-the-power-bi-app-on-the-apple-watch"></a>Apple Watch에서 Power BI 앱 사용
시계의 Springboard에서 또는 시계 화면(구성된 경우)에서 직접 Power BI 위젯을 클릭하여 Power BI Apple Watch 앱으로 이동합니다.

![Apple Watch](./media/mobile-apple-watch/pbi_aplwatch_complicatn240arrow.png)

Power BI Apple Watch 앱은 두 부분으로 구성됩니다.

* **인덱스 화면**을 사용하면 대시보드에서 모든 KPI 및 카드 타일의 빠른 개요를 허용합니다.
  
  ![Apple Watch](./media/mobile-apple-watch/pbi_aplwatch_indexscreen240.png)
* **포커스 타일**: 특정 타일의 세부적인 보기에 대한 인덱스 화면에서 타일을 클릭합니다.
  
  ![Apple Watch](./media/mobile-apple-watch/pbi_aplwatch_kpi.png)

## <a name="refresh-a-dashboard-from-your-apple-watch"></a>Apple Watch에서 대시보드 새로 고침
Watch에서 직접 동기화된 대시보드를 새로 고칠 수 있습니다.

* Watch 앱의 대시보드 보기에서 화면을 오랫동안 누르고 **새로 고침**을 선택합니다.

이제 Watch 앱은 Power BI 서비스의 데이터와 대시보드를 동기화합니다.

> [!NOTE]
> Watch 앱은 iPhone의 Power BI 모바일 앱을 통해 Power BI와 통신합니다. 따라서 Power BI 앱을 iPhone에서(최소한 새로 고칠 Watch 앱의 대시보드에 대한 백그라운드에서에서) 실행해야 합니다.
> 
> 

## <a name="refresh-a-dashboard-on-your-apple-watch-from-your-iphone"></a>iPhone의 Apple Watch에서 대시보드 새로 고침
iPhone의 Apple Watch에서 대시보드를 새로 고칠 수도 있습니다.

1. iPhone의 Power BI에서 Apple Watch와 동기화하려는 대시보드를 엽니다. 
2. 줄임표 (...) > **시계와 동기화**를 선택합니다.

Power BI는 대시보드가 시계와 동기화되었다는 지표를 보여줍니다.

시계와 한 번에 하나의 대시보드만 동기화할 수 있습니다.

> [!TIP]
> 시계의 여러 대시보드에서 타일을 보려면 Power BI 서비스에 새 대시보드를 만들고 모든 관련 타일을 고정합니다.
> 
> 

## <a name="set-a-custom-power-bi-widget"></a>사용자 지정 Power BI 위젯 설정
또한 Apple Watch 화면에 직접 특정 Power BI 타일을 표시할 수 있으므로 항상 볼 수 있고 액세스할 수 있습니다.

Power BI Apple Watch 위젯은 데이터가 업데이트되는 시간에 업데이트되므로 필요한 정보를 항상 최신 상태로 유지합니다.

### <a name="add-a-power-bi-widget-to-your-watch-face"></a>시계 화면에 Power BI 위젯 추가
Apple 가이드에서 [Apple Watch 화면 사용자 지정](https://support.apple.com/en-us/HT205536)을 참조하세요.

### <a name="change-the-text-on-the-widget"></a>위젯의 텍스트 변경
Apple Watch 화면의 작은 공간에 맞게 Power BI Apple Watch 앱을 통해 작은 공간에 맞게 위젯의 제목을 변경할 수 있습니다.

* iPhone에서 Apple Watch 제어 앱으로 이동하고 Power BI를 선택하며 위젯 이름 필드로 이동하고 새 이름을 입력합니다.
  
  ![Apple Watch](./media/mobile-apple-watch/pbi_aplwatch_oniphone.png)

> [!NOTE]
> 이름을 변경하지 않으면 Power BI 위젯은 시계 화면의 작은 공간에 맞는 문자 수로 이름을 단축합니다. 
> 
> 

## <a name="next-steps"></a>다음 단계
사용자 의견은 나중에 구현할 사항을 결정하는 데 도움이 됩니다. 따라서 Power BI 모바일 앱에서 참조하고자 하는 다른 기능에 대해 꼭 투표해주세요. 

* [Power BI iPhone 모바일 앱](http://go.microsoft.com/fwlink/?LinkId=522062) 다운로드
* [@MSPowerBI Twitter](https://twitter.com/MSPowerBI)에서 팔로우
* [Power BI 커뮤니티](http://community.powerbi.com/)에서 대화에 참여

