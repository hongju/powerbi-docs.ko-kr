---
title: Power BI에서 커넥터 확장성
description: 커넥터 확장성 기능, 특징, 보안 설정 및 인증된 커넥터
author: cpopell
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/22/2019
ms.author: gepopell
LocalizationGroup: Connect to data
ms.openlocfilehash: 7d5d743dda31d05df0beb528648c5a43ffc6b335
ms.sourcegitcommit: 32a44dd17a44ccfd4a2d86a0d235251c2fda1c5c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/01/2019
ms.locfileid: "68702097"
---
# <a name="connector-extensibility-in-power-bi"></a>Power BI에서 커넥터 확장성

Power BI에서 고객 및 개발자는 여러 가지 방법으로 연결하는 데이터 원본을 확장할 수 있습니다. 기존 커넥터 및 일반 데이터 원본(예: ODBC, OData, Oledb, Web, CSV, XML, JSON)을 사용합니다. 또는 개발자가 **사용자 지정 커넥터**라고 하는 데이터 확장 프로그램을 만들어 **인증된 커넥터**가 되게 합니다.

현재 시스템에서 실행하게 할 사용자 지정 코드 수준을 안전하게 제어할 수 있는 메뉴를 사용하여 **사용자 지정 커넥터**를 사용으로 설정합니다. **데이터 가져오기** 대화 상자에서 Microsoft가 인증하고 배포한 커넥터만 선택하거나 모든 사용자 지정 커넥터를 선택할 수 있습니다.

## <a name="custom-connectors"></a>사용자 지정 커넥터

**사용자 지정 커넥터**는 사용자의 비즈니스에 중요한 소규모 API부터 Microsoft에서 커넥터를 릴리스하지 않은 대규모 산업 특정 서비스까지 광범위한 가능성을 포함할 수 있습니다. 공급 업체에서 여러 커넥터를 배포합니다. 특정 데이터 커넥터가 필요한 경우 공급 업체에 문의해야 합니다.

**사용자 지정 커넥터**를 사용하려면 해당 커넥터를 *\[문서]\\Power BI Desktop\\사용자 지정 커넥터* 폴더에 넣은 후 다음 섹션에 설명된 대로 보안 설정을 조정합니다.

**인증된 커넥터**를 사용하도록 보안 설정을 조정하지 않아도 됩니다.

## <a name="data-extension-security"></a>데이터 확장 보안

데이터 확장 보안 설정을 변경하려면 **Power BI Desktop**에서 **파일 > 옵션 및 설정 > 옵션 > 보안**을 선택합니다.

![데이터 확장 보안 옵션을 사용하여 사용자 지정 커넥터를 로드할지 여부를 제어하세요.](media/desktop-connector-extensibility/data-extension-security-1.png)

**데이터 확장 프로그램**에서 두 가지 보안 수준을 선택할 수 있습니다.

* (권장) 인증된 확장 프로그램만 로드하도록 허용
* (권장하지 않음) 경고 없이 모든 확장 프로그램을 로드하도록 허용

**사용자 지정 커넥터** 또는 사용자나 타사가 개발한 커넥터를 사용하려는 경우 **“(권장하지 않음) 경고 없이 모든 확장 프로그램을 로드하도록 허용”** 을 선택해야 합니다. 사용자 지정 커넥터를 완전히 신뢰하는 경우가 아니면 이 보안 설정을 사용하지 않는 것이 좋습니다. 왜냐하면 HTTP를 통해 보내기를 비롯하여 여기에 있는 코드에서는 자격 증명을 처리할 수 있으므로 개인 정보 수준을 무시합니다.

**“(권장)”** 보안 설정에서, 시스템에 사용자 지정 커넥터가 있으면 “다음 커넥터가 인증되지 않았으므로 사용해도 안전한지 확인할 수 없습니다”라는 오류 다음에 안전하게 로드할 수 없는 커넥터 목록을 표시합니다.

![보안 설정으로 인해 로드할 수 없는 사용자 지정 커넥터를 설명하는 대화 상자(이 경우에는 TripPin)](media/desktop-connector-extensibility/data-extension-security-2.png)

보안을 변경하지 않고 오류를 해결하려면 '사용자 지정 커넥터' 폴더에서 서명되지 않은 커넥터를 제거합니다.

오류를 해결하고 해당 커넥터를 사용하려면 앞서 설명한 대로 보안 설정을 **“(권장하지 않음) 경고 없이 모든 확장 기능 로드 허용”** 설정을 변경합니다. **Power BI Desktop**을 다시 시작합니다.

## <a name="certified-connectors"></a>인증된 커넥터

제한된 데이터 하위 집합은 **인증**된 것으로 간주됩니다. **데이터 가져오기** 대화 상자에서 인증된 커넥터에 액세스합니다. 그러나 커넥터를 만든 타사 개발자는 유지 관리 및 지원을 담당합니다. Microsoft에서는 커넥터를 배포하지만, 성능 또는 지속적인 기능 유지에 대한 책임은 지지 않습니다.

사용자 지정 커넥터를 인증하려는 경우 해당 공급업체가 dataconnectors@microsoft.com에 연락하도록 하세요.
