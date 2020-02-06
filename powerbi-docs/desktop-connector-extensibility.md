---
title: Power BI에서 커넥터 확장성
description: 커넥터 확장성 기능, 특징, 보안 설정 및 인증된 커넥터
author: cpopell
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/02/2020
ms.author: gepopell
LocalizationGroup: Connect to data
ms.openlocfilehash: b604ade56335e65b25501eb9fe3d3c2fd185a6f0
ms.sourcegitcommit: 97597ff7d9ac2c08c364ecf0c729eab5d59850ce
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2020
ms.locfileid: "75761403"
---
# <a name="connector-extensibility-in-power-bi"></a>Power BI에서 커넥터 확장성

Power BI는 ODBC, OData, OLE DB, Web, CSV, XML, JSON 등의 기존 커넥터와 일반 데이터 원본을 사용하여 데이터에 연결할 수 있습니다. 또는 개발자가 ‘사용자 지정 커넥터’라는 사용자 지정 데이터 확장 프로그램을 사용하여 새 데이터 원본을 사용하도록 설정할 수 있습니다.  일부 사용자 지정 커넥터는 Microsoft에서 인증하여 ‘인증된 커넥터’로 배포합니다. 

사용자 또는 타사에서 개발한 인증되지 않은 사용자 지정 커넥터를 사용하려면 Power BI Desktop 보안 설정을 조정하여 유효성 검사 또는 경고 없이 확장 프로그램을 로드하도록 허용해야 합니다. 이 코드는 HTTP를 통해 보내는 것을 포함하여 자격 증명을 처리하고 개인 정보 수준을 무시할 수 있으므로 사용자 지정 커넥터를 절대적으로 신뢰하는 경우에만 이 보안 설정을 사용해야 합니다.

개발자가 인증서를 사용하여 커넥터에 서명하고 보안 설정 변경 없이 커넥터 사용에 필요한 정보를 제공하는 또 다른 옵션도 있습니다. 자세한 내용은 [신뢰할 수 있는 타사 커넥터 정보](desktop-trusted-third-party-connectors.md)를 참조하세요.

## <a name="custom-connectors"></a>사용자 지정 커넥터

인증되지 않은 사용자 지정 커넥터는 소규모 중요 비즈니스용 API부터 Microsoft에서 커넥터를 릴리스하지 않은 대규모 산업 특정 서비스에 이르기까지 다양할 수 있습니다. 공급업체는 많은 커넥터를 배포합니다. 특정 데이터 커넥터가 필요한 경우 해당 공급업체에 문의하세요. 

인증되지 않은 사용자 지정 커넥터를 사용하려면 커넥터 *.pq*, *.pqx*, *.m* 또는 *.mez* 파일을 *\[문서]\\Power BI Desktop\\사용자 지정 커넥터* 폴더에 배치합니다. 이 폴더가 없으면 폴더를 만듭니다.

데이터 확장 프로그램 보안 설정을 다음과 같이 조정합니다.

Power BI Desktop에서 **파일** > **옵션 및 설정** > **옵션** > **보안**을 선택합니다.

**데이터 확장 프로그램**에서 **(권장하지 않음) 유효성 검사 또는 경고 없이 모든 확장 프로그램을 로드하도록 허용**을 선택합니다. **확인**을 선택하고 Power BI Desktop을 다시 시작합니다. 

![데이터 확장 프로그램의 인증되지 않은 사용자 지정 커넥터 허용 보안 옵션](media/desktop-connector-extensibility/data-extension-security-1.png)

기본 Power BI Desktop 데이터 확장 프로그램 보안 설정은 **(권장) Microsoft 인증 확장 프로그램 및 기타 신뢰할 수 있는 타사 확장 프로그램만 로드하도록 허용**입니다. 이 설정을 사용하면 시스템에 인증되지 않은 사용자 지정 커넥터가 있는 경우 Power BI Desktop을 시작할 때 안전하게 로드할 수 없는 커넥터가 나열된 **인증되지 않은 커넥터** 대화 상자가 표시됩니다.

![인증되지 않은 커넥터 대화 상자](media/desktop-connector-extensibility/data-extension-security-2.png)

이 오류가 해결되도록 **데이터 확장 프로그램** 보안 설정을 변경하거나 *사용자 지정 커넥터* 폴더에서 인증되지 않은 커넥터를 제거할 수 있습니다.

## <a name="certified-connectors"></a>인증된 커넥터

데이터 확장 프로그램 중 제한된 하위 집합의 확장 프로그램은 ‘인증’된 것으로 간주됩니다.  Microsoft에서는 커넥터를 배포하지만, 성능 또는 지속적인 기능 유지에 대한 책임은 지지 않습니다. 커넥터를 만든 타사 개발자는 유지 관리 및 지원에 대한 책임이 있습니다. 

Power BI Desktop에서 인증된 타사 커넥터는 **데이터 가져오기** 대화 상자의 목록에 일반 및 공통 커넥터와 함께 표시됩니다. 인증된 커넥터를 사용하기 위해 보안 설정을 조정할 필요가 없습니다.

사용자 지정 커넥터가 인증을 받게 하려면 해당 공급업체가 dataconnectors@microsoft.com으로 연락하도록 요청하세요.
