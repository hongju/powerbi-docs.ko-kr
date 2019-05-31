---
title: Power BI에서 타사 커넥터를 신뢰할 수 있는
description: Power BI에서 서명 된 타사 커넥터를 신뢰 하는 방법
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
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "65607780"
---
# <a name="trusting-third-party-connectors"></a>타사 커넥터를 신뢰합니다.

## <a name="why-do-you-need-trusted-third-party-connectors"></a>신뢰할 수 있는 타사 커넥터는 왜 필요 한가요?

Power BI에서 일반적으로 권장 '데이터 확장 프로그램 '보안 수준 되지 Microsoft에서 인증 코드의 로드를 방지 하는 더 높은 수준으로 유지 합니다. 그러나 특정 커넥터-작성, 또는 컨설턴트 또는 Microsoft 인증 경로 외부 공급 업체에서 제공 하는 것을 로드 하려는 많은 경우가 있을 수 있습니다.

지정 된 커넥터의 개발자는 인증서를 사용 하 여 로그인 하 고 보안 설정을 낮춰 없이 안전 하 게 로드 하는 데 필요한 정보를 사용 하 여 제공 수 있습니다.

보안 설정에 대 한 자세한 정보를 알아야 하는 경우에 대 한 읽을 수 있습니다 [여기](https://docs.microsoft.com/power-bi/desktop-connector-extensibility)합니다.

## <a name="using-the-registry-to-trust-third-party-connectors"></a>타사 커넥터를 신뢰 하도록 레지스트리를 사용 하 여

Power BI에서 타사 커넥터 신뢰는 지정 된 레지스트리 값에서 신뢰 하려면 인증서의 지문을 나열 하 여 수행 됩니다. 이 지문을 로드 하려는 커넥터에 인증서의 지문과 일치 하는 경우 Power BI에서 '권장' 보안 수준의 로드 수 있습니다. 

레지스트리 경로 HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Power BI 데스크톱입니다. 경로가 존재 하는지 확인 하거나 만들어야 합니다. 편집 하려면 로컬 컴퓨터 관리 액세스가 필요한 뿐만 아니라 IT 정책에서 기본적으로 제어 하 고이 인해이 위치를 선택 했습니다. 

![신뢰할 수 있는 제 3 자 키를 사용 하 여 power BI 데스크톱 레지스트리 설정](media/desktop-trusted-third-party-connectors/desktoptrustedthird1.png)

위에 지정 된 경로에서 새 값을 추가 합니다. 형식에는 "다중 문자열 값" (REG_MULTI_SZ) 이어야 하며 "TrustedCertificateThumbprints" 호출 되어야 합니다. 

![신뢰할 수 있는 타사 커넥터는 하지만 키에 대 한 진입점을 사용 하 여 power BI Desktop 레지스트리](media/desktop-trusted-third-party-connectors/desktoptrustedthird2.png)

신뢰 하려면 인증서의 지문이 추가 합니다. 구분 기호를 사용 하거나 레지스트리 편집기에서 오른쪽 클릭-> "\0"를 사용 하 여 여러 인증서 수정 하 고 새 줄에 각 지 문은 배치를 추가할 수 있습니다. 예제에서는 지문에서 자체 서명 된 인증서를 가져옵니다. 

 ![신뢰할 수 있는 제 3 자 키를 사용 하 여 power BI 데스크톱 레지스트리 설정](media/desktop-trusted-third-party-connectors/desktoptrustedthird3.png)

지침을 올바르게 수행 했다면 하 여 개발자가 올바른 지문을 지정 된 경우 안전 하 게 연결 된 인증서로 서명 하는 신뢰 커넥터 있어야 이제 합니다.

## <a name="how-to-sign-connectors"></a>커넥터를 서명 하는 방법

파워 쿼리 문서에에 대 한 읽을 수 있습니다 로그온 해야 하는 개발자 또는 커넥터를 만든 경우 [여기](https://docs.microsoft.com/power-query/handlingconnectorsigning)합니다.
