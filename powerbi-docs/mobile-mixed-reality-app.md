---
title: 혼합 현실용 Power BI 앱(미리 보기)
description: 가상 환경 또는 사용자 환경 컨텍스트에서 사용하는 동안 혼합 현실용 Power BI 앱(미리 보기)에서 대시보드 및 보고서를 봅니다.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-mobile
ms.topic: conceptual
ms.date: 06/05/2018
ms.author: maggies
ms.openlocfilehash: 15c59d25814a50ce09b5b52accd0f88d74871a34
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2018
ms.locfileid: "34799329"
---
# <a name="power-bi-for-mixed-reality-app-preview"></a>혼합 현실용 Power BI 앱(미리 보기)
가상 환경을 사용하는 동안 혼합 현실용 Power BI 앱(미리 보기)에서 대시보드 및 보고서를 확인하거나 사용자 환경 컨텍스트의 특정 위치에 배치합니다. 

Windows 스토어에서 [혼합 현실용 Power BI 앱 다운로드](https://www.microsoft.com/p/power-bi-mobile/9nblgggzlxn1?activetab=pivot%3aoverviewtab): Windows 스토어에서는 "Power BI 모바일"이라고 합니다. 가상 환경에서 대시보드 및 보고서와 상호 작용한 다음, 배치하려는 항목을 선택합니다. 

## <a name="two-views-windows-classic-and-holographic"></a>두 가지 보기: Windows 클래식 및 홀로그램

혼합 현실용 Power BI는 혼합된 현실에 고유한 추가 기능이 포함된 Windows Power BI 모바일 앱을 기반으로 합니다. 혼합 현실용 Power BI를 시작하면 Power BI의 "클래식" Windows 보기가 표시됩니다. 이 보기에서 액세스할 수 있는 대시보드 및 보고서를 탐색할 수 있습니다. 원하는 항목을 찾으면 클래식 Windows 보기에서 홀로그램 환경으로 전환할 수 있습니다. 


## <a name="windows-classic-view-basics"></a>Windows 클래식 보기 기본 사항

혼합 현실 환경에 익숙하지 않다면 이 섹션을 참조하세요. 혼합 현실 앱으로 상호 작용하는 작업은 컴퓨터 또는 태블릿이나 휴대폰으로 상호 작용하는 작업과 다릅니다. Windows 클래식 보기에서 혼합 현실 앱은 기존의 마우스와 키보드 또는 전화 탭을 대체하는 제스처 및 음성 명령 집합에 대응합니다. 

**에어 탭**

에어 탭은 대부분의 혼합 현실 앱과 상호 작용하기 위해 알아야 하는 가장 기본적인 제스처입니다. 마우스 클릭이나 전화 탭과 유사하게 손을 세워서 엄지 및 집게 손가락을 함께 누릅니다.  

![혼합 현실 에어 탭 제스처](media/mobile-mixed-reality-app/power-bi-hololens-airtap.png)

Power BI에서는 마우스 클릭을 사용하려는 Windows 클래식 앱에서 에어 탭을 사용합니다. 에어 탭을 사용하여 작업 영역에서 대시보드 또는 보고서를 열거나 시각적 개체의 일부에서 에어 탭을 사용하여 다른 시각적 개체를 필터링하거나 교차 강조 표시할 수 있습니다.

![Power BI에서 에어 탭 사용](media/mobile-mixed-reality-app/power-bi-hololens-airtap-hand.png) 

[혼합 현실에서 Microsoft 손 제스처](https://developer.microsoft.com/windows/mixed-reality/gestures)에 대해 자세히 알아보세요.

**항목 고정** 

**고정** 아이콘 ![고정 아이콘](media/mobile-mixed-reality-app/power-bi-hololens-pin.png)에서 에어 탭을 사용하여 Windows 클래식 보기에서 홀로그램 보기로 대시보드 또는 보고서를 고정합니다. 홀로그램 보기로 여러 항목을 고정할 수 있습니다. 

**홀로그램 보기로 전환**

Windows 클래식 보기에서 항목을 고정한 후에 **전체 화면** 아이콘 ![전체 화면 아이콘](media/mobile-mixed-reality-app/power-bi-hololens-fullscreen.png)에서 에어 탭을 사용하여 홀로그램 보기로 전환합니다. 


## <a name="holographic-view-basics"></a>홀로그램 보기 기본 사항

이제 홀로그램 보기를 사용하므로 고정한 모든 아티팩트가 도킹 벨트에 있습니다. 물리적 공간의 특정 위치에 이러한 고정된 항목을 배치할 수 있습니다(예: 항목에서 설명하는 장비 옆에). 홀로그램 보기에서 음성 명령은 손 제스처를 보완합니다. 몇 가지 일반적인 음성 명령은 다음과 같습니다.

**"팔로우 미"** 

기본 가시 영역에서 유지되고 어딘가에 배치될 때까지 게이즈를 따르도록 Power BI 아티팩트를 선택합니다.

**"도킹"** 

쉽게 액세스하기 위해 기본 가시 영역의 외부에서 사용자를 따르도록 "도킹" 명령을 사용하여 Power BI 도킹 벨트에 아티팩트를 배치합니다.

**"여기 배치"**

이 명령은 개체나 벽이나 개체에 대시보드 또는 보고서를 배치하거나 공간을 마우스로 가리킵니다.

![공간에 대시보드 배치](media/mobile-mixed-reality-app/power-bi-hololens-place-visuals.png)

**"홈으로 이동"**

Power BI 클래식 Windows 보기로 돌아가려면 "Go home"이라고 말합니다. 

**"제거"**

이 명령을 사용하여 홀로그램 보기에서 아티팩트를 제거합니다.

**"모두 제거"** 

이 명령을 사용하여 홀로그램 보기에서 모든 아티팩트를 제거합니다.


## <a name="scan-a-report-qr-code-in-holographic-view"></a>홀로그램 보기에서 보고서 QR 코드 스캔

iPhone 및 Android용 [Power BI 모바일 앱을 사용하여 QR 코드를 스캔](mobile-apps-qr-code.md)하는 경우와 마찬가지로 홀로그램 보기에서 보고서의 QR 코드를 스캔할 수 있습니다.

- 홀로그램 보기에서 QR 코드를 응시합니다. Power BI는 해당 QR 코드와 연결된 보고서를 엽니다.

## <a name="limitations-and-considerations"></a>제한 사항 및 고려 사항

홀로그램 보기에 대한 몇 가지 제한 사항과 고려 사항은 다음과 같습니다.

- 교차 필터링 또는 강조 표시가 표시되지 않는 경우 Windows 클래식 보기에서 설정할 수 있습니다.
- 고정된 대시보드 및 보고서 보기는 비공개입니다. 현재 공유 환경을 지원하지 않습니다.
- 대시보드 및 보고서는 데이터가 변경될 때 45초마다 새로 고칩니다.


## <a name="next-steps"></a>다음 단계

- [Power BI 모바일 앱으로 실제 환경에서 데이터 가져오기](mobile-apps-data-in-real-world-context.md)

 



