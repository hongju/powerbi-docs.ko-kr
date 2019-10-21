---
title: Power BI Gateway 문제 해결(개인 모드)
description: Power BI Gateway 문제 해결(개인 모드)
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: troubleshooting
ms.date: 5/06/2019
ms.author: mblythe
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 8916d92eef86be601ceb21112209ab7daa736c11
ms.sourcegitcommit: e5cf19e16112c7dad1591c3b38d232267ffb3ae1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "72543533"
---
# <a name="troubleshooting-power-bi-gateway-personal-mode"></a>Power BI Gateway 문제 해결(개인 모드)

[!INCLUDE [gateway-rewrite](includes/gateway-rewrite.md)]

다음 섹션에서는 Power BI 온-프레미스 데이터 게이트웨이(개인 모드)를 사용할 때 발생할 수 있는 몇 가지 일반적인 문제를 설명합니다.

## <a name="update-to-the-latest-version"></a>최신 버전으로 업데이트

개인용 게이트웨이의 현재 버전은 온-프레미스 데이터 게이트웨이(개인 모드)입니다. 이 버전을 사용하려면 설치를 업데이트하세요.

게이트웨이 버전이 만료되면 많은 문제가 발생할 수 있습니다. 최신 버전을 사용하고 있는지 확인하는 것이 좋습니다. 한 달 이상 게이트웨이를 업데이트하지 않은 경우에는 최신 버전 게이트웨이를 설치하는 것이 좋습니다. 그런 다음 문제를 재현할 수 있는지 확인합니다.

## <a name="installation"></a>설치
**게이트웨이(개인 모드)는 64비트 버전에서 작동합니다.** 머신이 32비트 버전인 경우 게이트웨이(개인 모드)를 설치할 수 없습니다. 운영 체제가 64비트 버전이어야 합니다. Windows 64비트 버전을 설치하거나 64비트 머신에 개인 게이트웨이(개인 모드)를 설치해야 합니다.

**컴퓨터의 로컬 관리자이지만 게이트웨이(개인 모드)가 서비스로 설치되지 않습니다.** 사용자가 컴퓨터의 로컬 관리자 그룹에 속하더라도 그룹 정책에서 사용 사용자 이름의 서비스 로그인을 허용하지 않는 경우 설치에 실패할 수 있습니다. 그룹 정책에서 사용자의 서비스 로그인을 허용하는지 확인하세요. 이 문제에 대한 수정 중입니다. 자세한 내용은 [계정에 서비스로 로그온 권한 추가](https://technet.microsoft.com/library/cc739424.aspx)를 참조하세요.

**작업 시간이 초과됨:** 이 메시지는 일반적으로 게이트웨이(개인 모드)를 설치하는 컴퓨터(물리적 컴퓨터 또는 VM)에 단일 코어 프로세서가 있는 경우에 흔히 나타납니다. 애플리케이션을 닫고 필수가 아닌 모든 프로세스를 해제하고 다시 설치해 보세요.

**데이터 관리 게이트웨이 또는 Analysis Services 커넥터를 게이트웨이(개인 모드)와 동일한 컴퓨터에 설치할 수 없음:** Analysis Services 커넥터 또는 데이터 관리 게이트웨이를 이미 설치한 경우 먼저 커넥터 또는 게이트웨이를 제거해야 합니다. 그런 다음 게이트웨이(개인 모드)를 설치해 보세요.

> [!NOTE]
> 설치하는 동안 오류가 발생하는 경우 설치 로그에서 문제를 해결하는 데 유용한 정보를 제공할 수 있습니다. 자세한 내용은 [설치 로그](#SetupLogs)를 참조하세요.
> 
> 

 **프록시 구성:** 환경에서 프록시를 사용해야 하는 경우 게이트웨이(개인 모드)를 구성하는 데 문제가 발생할 수 있습니다. 프록시 정보를 구성하는 방법에 대해 자세히 알아보려면 [온-프레미스 데이터 게이트웨이에 대한 프록시 설정 구성](/data-integration/gateway/service-gateway-proxy)을 참조하세요.

## <a name="schedule-refresh"></a>새로 고침 예약
**오류: 클라우드에 저장된 자격 증명이 누락되었습니다.**

새로 고침을 예약한 후 게이트웨이(개인 모드)를 제거하고 다시 설치한 경우 \<데이터 세트\>에 대한 설정에 이 오류가 나타날 수 있습니다. 게이트웨이(개인 모드)를 제거하는 경우 새로 고침에 대해 데이터 세트의 데이터 원본 자격 증명이 Power BI 서비스에서 제거됩니다.

**해결 방법:** Power BI에서 데이터 세트의 새로 고침 설정으로 이동합니다. **데이터 원본 관리**에서 오류가 있는 모든 데이터 원본에 대해 **자격 증명 편집**을 선택합니다. 그런 다음 데이터 원본에 다시 로그인합니다.

**오류: 데이터 세트에 대해 제공된 자격 증명이 유효하지 않습니다. 계속하려면 새로 고침을 통해 또는 데이터 소스 설정 대화 상자에서 자격 증명을 업데이트하세요.**

**해결 방법:** 자격 증명 메시지를 받는 경우 다음을 의미할 수 있습니다.

* 데이터 원본에 로그인하는 데 사용된 사용자 이름과 암호가 최신이 아닌지 확인합니다. Power BI에서 데이터 세트에 대한 새로 고침 설정으로 이동합니다. **데이터 원본 관리**에서 **자격 증명 편집**을 선택하여 데이터 원본의 자격 증명을 업데이트합니다.
* 원본 중 하나가 인증에 OAuth를 사용하는 경우 단일 쿼리에서 클라우드 원본과 온-프레미스 원본 간의 매시업이 게이트웨이(개인 모드)에서 새로 고침을 수행하지 못합니다. CRM 온라인과 로컬 SQL Server 인스턴스 간의 매시업이 이 문제에 대한 예입니다. 이 매시업은 CRM 온라인에서 OAuth가 필요하기 때문에 실패합니다.
  
  이 오류는 알려진 문제이며 검토 중입니다. 문제를 해결하려면 클라우드 원본 및 온-프레미스 원본에 대해 별도의 쿼리를 포함합니다. 그런 다음, 병합 또는 추가 쿼리를 사용하여 결합합니다.

**오류: 지원되지 않는 데이터 원본입니다.**

**해결 방법:** **일정 새로 고침** 설정에서 지원되지 않는 데이터 원본 메시지가 표시되면 다음을 의미할 수 있습니다. 

* Power BI에서 현재 데이터 원본 새로 고침이 지원되지 않습니다. 
* Excel 통합 문서에는 데이터 모델이 포함되어 있지 않고, 워크시트 데이터만 포함되어 있습니다. 현재 Power BI는 업로드된 Excel 통합 문서에 데이터 모델이 포함된 경우 새로 고침만 지원합니다. Excel에서 파워 쿼리를 사용하여 데이터를 가져올 때 데이터 모델로 데이터를 로드하는 **로드** 옵션을 선택합니다. 이 옵션을 사용하면 데이터를 데이터 모델로 가져옵니다. 

**오류: [데이터를 결합할 수 없습니다.] &lt;쿼리 부분&gt;/&lt;…&gt;/&lt;…&gt;이 함께 사용할 수 없는 프라이버시 수준의 데이터 원본에 액세스합니다. 이 데이터 조합을 다시 작성합니다.**

**해결 방법:** 이 오류는 현재 사용 중인 데이터 원본의 유형 및 개인 정보 수준 제한으로 인해 발생합니다.

**오류: 데이터 원본 오류: “\[테이블\]” 값을 테이블 형식으로 변환할 수 없습니다.**

**해결 방법:** 이 오류는 현재 사용 중인 데이터 원본의 유형 및 개인 정보 수준 제한으로 인해 발생합니다.

**오류: 이 행에 필요한 공간이 부족합니다.**

**해결 방법:** 단일 행의 크기가 4MB를 초과할 경우 이 오류가 발생합니다. 데이터 원본에서 행을 찾고 해당 행을 필터링하거나 해당 행의 크기를 줄입니다.

## <a name="data-sources"></a>데이터 원본
**데이터 공급자 누락:** 게이트웨이(개인 모드)는 64비트 버전에서만 작동합니다. 64비트 버전의 데이터 공급자를 게이트웨이(개인 모드)가 설치된 컴퓨터에 설치해야 합니다. 예를 들어 데이터 세트의 데이터 원본이 Microsoft Access인 경우 게이트웨이(개인 모드)를 설치한 컴퓨터에 64비트 ACE 공급자를 설치해야 합니다. 

>[!NOTE]
>32비트 버전 Excel을 사용하는 경우 동일한 컴퓨터에 64비트 버전 ACE 공급자를 설치할 수 없습니다.

**Access 데이터베이스에서는 Windows 인증이 지원되지 않습니다.** 현재 Power BI는 Access 데이터베이스에 대해 익명 인증만 지원합니다.

**오류: 데이터 원본에 대한 자격 증명을 입력할 때 로그인 오류가 발생합니다.** 데이터 원본에 대해 Windows 자격 증명을 입력할 때 이러한 오류가 발생하는 경우: 

  ![Windows 자격 증명 오류 메시지](media/service-admin-troubleshooting-power-bi-personal-gateway/pbi_pg_credentialserror.jpg.png)

이전 버전의 게이트웨이(개인 모드)를 사용 중일 수 있습니다. 

**해결 방법:** 자세한 내용은 [Power BI Gateway(개인 모드) 최신 버전 설치](https://powerbi.microsoft.com/gateway/)를 참조하세요.

**오류: ACE OLEDB를 사용하여 데이터 원본에 대한 Windows 인증을 선택할 때 로그인 오류가 발생합니다.** ACE OLEDB 공급자를 사용하여 데이터 원본에 대한 데이터 원본 자격 증명을 입력할 때 다음과 같은 오류가 발생하는 경우:

![데이터 원본 자격 증명 오류 메시지](media/service-admin-troubleshooting-power-bi-personal-gateway/aceoledberror.png)

Power BI는 현재 ACE OLEDB 공급자를 사용하여 데이터 원본에 대한 Windows 인증을 지원하지 않습니다.

**해결 방법:** 이 오류를 해결하려면 **익명 인증**을 선택합니다. 레거시 ACE OLEDB 공급자에 대한 익명 자격 증명은 Windows 자격 증명과 동일합니다.

## <a name="tile-refresh"></a>타일 새로 고침
대시보드 타일을 새로 고칠 때 오류가 표시되는 경우 [타일 오류 문제 해결](refresh-troubleshooting-tile-errors.md)을 참조하세요.

## <a name="tools-for-troubleshooting"></a>문제 해결을 위한 도구
### <a name="refresh-history"></a>새로 고침 기록
**새로 고침 기록**을 사용하면 어떤 오류가 발생했는지 확인하고 지원 요청을 만들어야 할 경우 유용한 데이터를 찾을 수 있습니다. 예약된 새로 고침 및 요청 시 새로 고침을 둘 다 볼 수 있습니다. **새로 고침 기록**을 가져오는 방법은 다음과 같습니다.

1. Power BI 탐색 창의 **데이터 세트**에서 데이터 세트를 선택합니다. 메뉴를 열고 **새로 고침 예약**을 선택합니다.

   ![새로 고침 예약 선택](media/service-admin-troubleshooting-power-bi-personal-gateway/scheduled-refresh.png)
1. **다음 설정...** 에서 **새로 고침 기록**을 선택합니다. 

   ![새로 고침 기록 선택](media/service-admin-troubleshooting-power-bi-personal-gateway/scheduled-refresh-2.png)
   
   ![새로 고침 기록 정보](media/service-admin-troubleshooting-power-bi-personal-gateway/refresh-history.png)

### <a name="event-logs"></a>이벤트 로그
여러 이벤트 로그가 정보를 제공할 수 있습니다. 처음 두 가지인 **데이터 관리 게이트웨이** 및 **PowerBIGateway**는 머신 관리자인 경우에 제공됩니다. 관리자가 아니고 데이터 게이트웨이(개인 모드)를 사용하는 경우는 **애플리케이션** 로그에서 로그 항목을 볼 수 있습니다.

**데이터 관리 게이트웨이** 및 **PowerBIGateway** 로그는 **애플리케이션 및 서비스 로그**아래에 표시됩니다.

![데이터 관리 게이트웨이 및 PowerBIGateway 로그](media/service-admin-troubleshooting-power-bi-personal-gateway/event-logs.png)

### <a name="fiddler-trace"></a>Fiddler 추적
[Fiddler](http://www.telerik.com/fiddler)는 HTTP 트래픽을 모니터링하는 Telerik의 무료 도구입니다. 클라이언트 머신에서 Power BI 서비스에 대한 통신을 볼 수 있습니다. 이 통신에서 오류 및 다른 관련 정보를 표시할 수 있습니다.

![Fiddler 추적](media/service-admin-troubleshooting-power-bi-personal-gateway/fiddler.png)

<a name="SetupLogs"></a>

### <a name="setup-logs"></a>설치 로그
게이트웨이(개인 모드) 설치에 실패하면 설치 로그를 볼 수 있는 링크가 표시됩니다. 설치 로그에서는 오류에 대한 자세한 정보를 볼 수 있습니다. 이 로그는 MSI 로그로도 알려진 Windows 설치 로그입니다. 상당히 복잡하고 읽기 어렵습니다. 일반적으로 결과 오류는 기저에 있지만, 오류의 원인을 파악하기란 쉽지 않습니다. 오류의 결과를 다른 로그에서 확인할 수 있습니다. 오류의 결과를 로그의 상위 수준에서 확인할 수도 있습니다.

![설치 로그에 연결](media/service-admin-troubleshooting-power-bi-personal-gateway/setup-log.png)

또는 임시 폴더(%temp%)로 가서 *Power\_BI\_* 로 시작하는 파일을 찾아볼 수 있습니다.

> [!NOTE]
> %temp%로 가면 임시 하위 폴더로 갈 수 있습니다. *Power\_BI\_* 파일은 임시 디렉터리의 루트에 있습니다. 하나 또는 두 수준 상위로 이동해야 할 수 있습니다.
> 
> 

![임시 폴더](media/service-admin-troubleshooting-power-bi-personal-gateway/setup-logs2.png)

## <a name="next-steps"></a>다음 단계
- [온-프레미스 데이터 게이트웨이에 대한 프록시 설정 구성](/data-integration/gateway/service-gateway-proxy)- [데이터 새로 고침](refresh-data.md)  
- [Power BI 게이트웨이 - 개인](service-gateway-personal-mode.md)  
- [타일 오류 문제 해결](refresh-troubleshooting-tile-errors.md)  
- [온-프레미스 데이터 게이트웨이 문제 해결](service-gateway-onprem-tshoot.md) 
 
궁금한 점이 더 있나요? [Power BI 커뮤니티](http://community.powerbi.com/)에 질문합니다.

