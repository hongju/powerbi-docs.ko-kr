---
title: Power BI에서 신뢰하는 타사 커넥터
description: Power BI에서 서명된 타사 커넥터를 신뢰하는 방법
author: cpopell
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 04/3/2019
ms.author: gepopell
LocalizationGroup: Connect to data
ms.openlocfilehash: 30b7457c6149320c43f24b967a842382821b01b1
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "65607780"
---
# <a name="trusting-third-party-connectors"></a>타사 커넥터 신뢰

## <a name="why-do-you-need-trusted-third-party-connectors"></a>신뢰할 수 있는 타사 커넥터가 필요한 이유

Power BI에서는 일반적으로 Microsoft에서 인증하지 않은 코드의 로드를 방지하는 '데이터 확장 보안' 수준을 더 높은 수준으로 유지할 것을 권장합니다. 그러나 사용자가 작성한 커넥터 또는 Microsoft 인증 경로 외부에 있는 컨설턴트 또는 공급업체에서 제공하는 커넥터를 로드하려는 많은 경우가 있을 수 있습니다.

지정된 커넥터의 개발자는 인증서로 서명하고 보안 설정을 낮추지 않고 안전하게 로드하는 데 필요한 정보를 제공할 수 있습니다.

보안 설정에 대한 자세한 정보를 알아야 하는 경우 [여기](https://docs.microsoft.com/power-bi/desktop-connector-extensibility)를 참고합니다.

## <a name="using-the-registry-to-trust-third-party-connectors"></a>타사 커넥터를 신뢰하도록 레지스트리 사용

Power BI에서 타사 커넥터 신뢰는 신뢰하고자 하는 인증서의 지문을 지정된 레지스트리 값에 나열하여 수행됩니다. 이 지문이 로드하려는 커넥터의 인증서의 지문과 일치하는 경우 Power BI의 '권장' 보안 수준에서 로드할 수 있습니다. 

레지스트리 경로는 HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Power BI Desktop입니다. 경로가 존재하는지 확인하거나 만들어야 합니다. 편집하려면 로컬 컴퓨터 관리 액세스가 필요할 뿐만 아니라 IT 정책에서 기본적으로 제어하므로 이 위치를 선택했습니다. 

![신뢰할 수 있는 제 3 자 키를 사용 하 여 power BI 데스크톱 레지스트리 설정](media/desktop-trusted-third-party-connectors/desktoptrustedthird1.png)

위에 지정된 경로 아래에 새 값을 추가합니다. 형식은 "다중 문자열 값"(REG_MULTI_SZ)이어야 하며 "TrustedCertificateThumbprints"가 되어야 합니다. 

![신뢰할 수 있는 타사 커넥터는 하지만 키에 대 한 진입점을 사용 하 여 power BI Desktop 레지스트리](media/desktop-trusted-third-party-connectors/desktoptrustedthird2.png)

신뢰하고자 하는 인증서의 지문을 추가합니다. 구분 기호로 "\0"를 사용하거나 레지스트리 편집기에서 오른쪽 클릭-> 수정에서 새 줄에 각 지문은 추가하여 여러 인증서를 추가할 수 있습니다. 예제에서는 지문을 자체 서명된 인증서에서 가져옵니다. 

 ![신뢰할 수 있는 제 3 자 키를 사용 하 여 power BI 데스크톱 레지스트리 설정](media/desktop-trusted-third-party-connectors/desktoptrustedthird3.png)

지침을 올바르게 수행하고 개발자로부터 올바른 지문을 받은 경우, 이제 관련 인증서로 서명된 커넥터를 안전하게 신뢰할 수 있습니다.

## <a name="how-to-sign-connectors"></a>커넥터를 서명 하는 방법

서명해야 하는 커넥터가 있는 경우 또는 개발자가 서명해야 하는 경우, [여기](https://docs.microsoft.com/power-query/handlingconnectorsigning)서 파워 쿼리 문서에 대해 읽을 수 있습니다.
