---
title: Power BI 앱 구성 설정
description: MDM 도구를 사용하여 Power BI의 동작을 사용자 지정하는 방법
author: paulinbar
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: conceptual
ms.date: 11/07/2019
ms.author: painbar
ms.openlocfilehash: a517ee4edce6e18eadcbe2b1b6765684f8121b21
ms.sourcegitcommit: 768e1e4b19fe8c7627010127c2420d63021cb542
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/20/2019
ms.locfileid: "74199431"
---
# <a name="remotely-configure-power-bi-app-using-mobile-device-management-mdm-tool"></a>MDM(모바일 디바이스 관리) 도구를 사용하여 Power BI 앱을 원격으로 구성

iOS 및 Android용 Power BI 모바일 앱은 Office 365 및 MDM(모바일 디바이스 관리) 서비스(예: Intune)의 관리자가 앱의 동작을 사용자 지정할 수 있도록 앱 설정을 지원합니다.

Power BI 모바일 앱은 다음 구성 시나리오를 지원합니다.

- 보고서 서버 구성(iOS 및 Android)
- 데이터 보호 설정(iOS)

## <a name="report-server-configuration-ios-and-android"></a>보고서 서버 구성(iOS 및 Android)

관리자는 iOS 및 Android용 Power BI 앱을 사용하여 보고서 서버 구성을 등록된 장치에 원격으로 "푸시"할 수 있습니다.

| 키 | 형식 | 설명 |
|---|---|---|
| com.microsoft.powerbi.mobile.ServerURL | String | 보고서 서버 URL.<br><br>http/https로 시작해야 합니다.|
| com.microsoft.powerbi.mobile.ServerUsername | String | [선택 사항]<br><br>서버 연결에 사용할 사용자 이름입니다.<br><br>존재하지 않는 경우 앱은 연결의 사용자 이름을 입력하라는 메시지를 수신합니다.|
| com.microsoft.powerbi.mobile.ServerDisplayName | String | [선택 사항]<br><br>기본값은 "보고서 서버"입니다.<br><br>서버를 표시하기 위해 앱에서 사용되는 식별 이름입니다. |
| com.microsoft.powerbi.mobile.OverrideServerDetails | Boolean | [선택 사항]<br><br>기본값은 True입니다. True로 설정하면 모바일 디바이스에 이미 있는 모든 보고서 서버 정의를 재정의합니다. 이미 구성된 기존 서버는 삭제됩니다. 또한 True로 설정된 재정의는 사용자가 해당 구성을 제거하지 않도록 방지합니다.<br><br>기존 설정을 그대로 두고 False로 설정하여 푸시된 값을 추가합니다. 모바일 앱에 동일한 서버 URL이 이미 구성되어 있는 경우 앱 구성을 그대로 유지합니다. 앱은 사용자에게 동일한 서버에 대한 인증을 다시 요청하지 않습니다. |

## <a name="data-protection-settings-ios"></a>데이터 보호 설정(iOS)

iOS용 Power BI iOS 앱은 관리자에게 보안 및 개인 정보 설정에 대한 기본 구성을 사용자 지정할 수 있는 기능을 제공합니다. Power BI 앱에 액세스할 때 사용자에게 Face ID, Touch ID 또는 암호를 제공하도록 강제할 수 있습니다.

| 키 | 형식 | 설명 |
|---|---|---|
| com.microsoft.powerbi.mobile.ForceDeviceAuthentication | Boolean | 기본값은 False입니다. <br><br>사용자가 해당 디바이스에 액세스하기 위해서는 TouchID 또는 FaceID 등의 생체 인식이 필요할 수 있습니다. 필요한 경우 인증 외에 생체 인식도 사용됩니다.<br><br>앱 보호 정책을 사용하는 경우 Microsoft는 이중 액세스 프롬프트를 방지하기 위해 이 설정을 사용하지 않도록 설정하는 것을 권장합니다. |

## <a name="deploying-app-configuration-settings"></a>앱 구성 설정 배포

앱 구성 정책을 만드는 데 필요한 단계는 다음과 같습니다. 구성 정책을 만든 후에 사용자 그룹에 해당 설정을 할당할 수 있습니다.

1. MDM 도구를 연결합니다.
2. 새로운 앱 구성 정책을 만들고 이름을 지정합니다.
3. 이 앱 구성 정책을 배포할 사용자를 선택합니다.
4. 사용자에게 푸시할 설정에 대한 키-값 쌍을 만듭니다.

Intune 포털을 사용하면 관리자가 앱 구성 정책을 통해 Power BI 앱에 이러한 설정을 쉽게 배포할 수 있습니다. 그러나 모든 MDM 공급자가 지원됩니다. Intune을 사용하지 않는 경우 이러한 설정을 배포하는 방법은 MDM 설명서를 참조해야 합니다.

## <a name="next-steps"></a>다음 단계

* [앱 스토어](https://apps.apple.com/app/microsoft-power-bi/id929738808) 및 [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.powerbim&amp;amp;clcid=0x409)에서 Power BI 모바일 앱 가져오기
* [@MSPowerBI Twitter](https://twitter.com/MSPowerBI)에서 팔로우
* [Power BI 커뮤니티](https://community.powerbi.com/)에서 대화에 참여
