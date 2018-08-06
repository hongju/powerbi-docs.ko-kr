---
title: Power BI에서 커넥터 확장성
description: 커넥터 확장성 기능, 특징, 보안 설정 및 인증된 커넥터
author: cpopell
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 07/25/2018
ms.author: gepopell
LocalizationGroup: Connect to data
ms.openlocfilehash: c63357df043ff6a646562d398a07d8042dd5a0ee
ms.sourcegitcommit: 7fb0b68203877ff01f29724f0d1761d023075445
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/26/2018
ms.locfileid: "39256568"
---
# <a name="connector-extensibility-in-power-bi"></a>Power BI에서 커넥터 확장성

Power BI에서 고객 및 개발자는 기존 커넥터 및 일반 데이터 원본(예:ODBC, OData, Oledb, Web, CSV, XML, JSON) 사용 등, 많은 방법으로 연결 가능한 데이터 원본을 확장할 수 있습니다. 이러한 데이터 원본뿐만 아니라, 개발자는 **사용자 지정 커넥터**라고 하는 데이터 확장 프로그램을 만들고 **인증된 커넥터**가 되도록 커넥터를 인증할 수 있습니다.

이전 버전의 Power BI에서 **사용자 지정 커넥터**는 기능 커넥터를 사용하여 사용 설정되었습니다. 이제는 시스템에서 실행을 허용하려는 사용자 지정 코드 수준을 안전하게 제어할 수 있는 메뉴가 있습니다(**데이터 가져오기** 대화 상자에서 모든 사용자 지정 커넥터, 또는 Microsoft에서 인증 및 배포한 커넥터만).

## <a name="custom-connectors"></a>사용자 지정 커넥터

**사용자 지정 커넥터**는 사용자의 비즈니스에 중요한 소규모 API에서 Microsoft에서 구현하지 않은 대규모 산업별 서비스까지 광범위한 가능성을 포함할 수 있습니다. 이러한 대부분의 커넥터는 공급업체에서 직접 배포하며 특정 데이터 커넥터가 필요할 경우 공급업체에 문의해야 합니다.

**사용자 지정 커넥터**를 사용하려면 해당 커넥터를 *\[문서]\\Power BI Desktop\\사용자 지정 커넥터* 폴더에 넣은 후 다음 섹션에 설명된 대로 보안 설정을 조정합니다.

**인증된 커넥터**를 사용할 경우 보안 설정을 조정하지 않아도 됩니다.

## <a name="data-extension-security"></a>데이터 확장 보안

데이터 확장 보안 설정을 변경하려면 **Power BI Desktop**에서 **파일 > 옵션 및 설정 > 옵션 > 보안**을 선택합니다.

![데이터 확장 보안 옵션을 사용하여 사용자 지정 커넥터를 로드할지 여부 제어](media/desktop-connector-extensibility/data-extension-security-1.png)

**데이터 확장 프로그램**에서 두 가지 보안 수준을 선택할 수 있습니다.

* (권장) 인증된 확장 프로그램만 로드하도록 허용
* (권장하지 않음) 경고 없이 모든 확장 프로그램을 로드하도록 허용

**사용자 지정 커넥터** 또는 사용자나 타사가 개발한 커넥터를 사용하고 배포하려는 경우, **(권장하지 않음) 경고 없이 모든 확장 프로그램을 로드하도록 허용**을 선택해야 합니다. **사용자 지정 커넥터**를 실행하려는 경우가 아니라면 이 보안 설정을 권장하지 않습니다.

**(권장)** 보안 설정에서 시스템에 사용자 지정 커넥터가 있는 경우 보안으로 인해 로드할 수 없는 커넥터를 설명하는 오류가 표시됩니다.

![보안 설정으로 인해 로드할 수 없는 사용자 지정 커넥터를 설명하는 대화 상자(이 경우에는 TripPin)](media/desktop-connector-extensibility/data-extension-security-2.png)

오류를 해결하고 해당 커넥터를 사용하려면 앞서 설명한 대로 보안 설정을 **(권장하지 않음)** 설정으로 변경하고 **Power BI Desktop**을 다시 시작해야 합니다.

## <a name="certified-connectors"></a>인증된 커넥터

일부 하위 집합의 데이터 확장 프로그램이 **인증된** 것으로 간주되며 이러한 인증된 커넥터는 **데이터 가져오기** 대화 상자를 사용하여 사용 가능하지만, 유지 보수 및 지원에 대한 책임은 여전히 해당 커넥터를 만든 타사 개발자에게 있습니다. Microsoft는 이러한 커넥터를 배포하지만, 성능 또는 지속적인 기능 유지에 대한 책임은 지지 않습니다.

사용자 지정 커넥터를 인증 받고 싶은 경우 해당 공급업체가 Microsoft에 연락하도록 하십시오.
