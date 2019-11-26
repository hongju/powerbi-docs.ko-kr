---
title: Power BI의 신뢰할 수 있는 타사 커넥터
description: Power BI에서 서명된 타사 커넥터를 신뢰하는 방법
author: cpopell
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 04/3/2019
ms.author: gepopell
LocalizationGroup: Connect to data
ms.openlocfilehash: ac3f795d6a80d5f143daf68436f41f5771b3c2bb
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2019
ms.locfileid: "73876153"
---
# <a name="trusting-third-party-connectors"></a>타사 커넥터 신뢰

## <a name="why-do-you-need-trusted-third-party-connectors"></a>신뢰할 수 있는 타사 커넥터가 필요한 이유는 무엇인가요?

Power BI에서는 대개 Microsoft에서 인증하지 않은 코드가 로드되지 않도록 '데이터 확장 프로그램 보안' 수준을 더 높은 수준으로 유지하는 것이 좋습니다. 그러나 직접 작성했거나 Microsoft 인증 경로 밖의 컨설턴트 또는 공급업체에서 제공하는 특정 커넥터를 로드하려는 경우가 많을 수 있습니다.

해당 커넥터의 개발자가 인증서를 사용하여 커넥터에 서명한 후 보안 설정을 낮추지 않고 안전하게 커넥터를 로드하는 데 필요한 정보를 제공할 수 있습니다.

보안 설정에 대한 자세한 내용을 보려면 [여기](https://docs.microsoft.com/power-bi/desktop-connector-extensibility)에서 확인하세요.

## <a name="using-the-registry-to-trust-third-party-connectors"></a>레지스트리를 사용하여 타사 커넥터 신뢰

Power BI에서 타사 커넥터 신뢰를 수행하려면 지정된 레지스트리 값에 신뢰하려는 인증서의 지문을 나열합니다. 이 지문이 로드하려는 커넥터의 인증서 지문과 일치하면 Power BI의 '권장' 보안 수준으로 커넥터를 로드할 수 있습니다. 

레지스트리 경로는 HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Power BI Desktop입니다. 해당 경로가 있는지 확인하거나 경로를 만듭니다. 이 위치는 주로 IT 정책에 의해 제어되며 편집하려면 로컬 컴퓨터 관리 액세스가 필요하기 때문에 선택되었습니다. 

![신뢰할 수 있는 타사 키가 설정되지 않은 Power BI Desktop 레지스트리](media/desktop-trusted-third-party-connectors/desktoptrustedthird1.png)

위에서 지정한 경로 아래에 새 값을 추가합니다. 형식은 “다중 문자열 값”(REG_MULTI_SZ)이고 이름은 “TrustedCertificateThumbprints”입니다. 

![신뢰할 수 있는 타사 커넥터에 대한 항목이 있지만 키가 없는 Power BI Desktop 레지스트리](media/desktop-trusted-third-party-connectors/desktoptrustedthird2.png)

신뢰 하려는 인증서의 지문을 추가합니다. “\0”을 구분 기호로 사용하여 여러 인증서를 추가하거나 레지스트리 편집기에서 마우스 오른쪽 단추를 클릭하고 새 줄에 각 지문을 넣을 수 있습니다. 예제 지문은 자체 서명된 인증서에서 가져온 것입니다. 

 ![신뢰할 수 있는 타사 키가 설정된 Power BI Desktop 레지스트리](media/desktop-trusted-third-party-connectors/desktoptrustedthird3.png)

지침을 제대로 따르고 개발자에게서 적절한 지문을 받으면 연결된 인증서로 서명된 커넥터를 안전하게 신뢰할 수 있습니다.

## <a name="how-to-sign-connectors"></a>커넥터에 서명하는 방법

사용자나 개발자가 서명해야 하는 커넥터가 있는 경우 [여기](https://docs.microsoft.com/power-query/handlingconnectorsigning)의 파워 쿼리 문서에서 이에 대해 알아볼 수 있습니다.
