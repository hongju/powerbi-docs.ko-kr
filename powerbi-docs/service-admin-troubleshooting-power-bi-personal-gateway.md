---
title: Power BI Gateway - Personal 문제 해결
description: Power BI Gateway - Personal 문제 해결
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 5/06/2019
ms.author: mblythe
LocalizationGroup: Troubleshooting
ms.openlocfilehash: bc6eaccc2976266102dcca0d20df73df810fa5f3
ms.sourcegitcommit: bf535771c9ef495f9bb658569403fa5e3dd82e6a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/17/2019
ms.locfileid: "65853548"
---
# <a name="troubleshooting-power-bi-gateway---personal"></a>Power BI Gateway - Personal 문제 해결
다음 섹션에서는 Power BI Gateway-Personal 사용할 때 나올 수는 몇 가지 일반적인 문제를 진행 합니다.

> [!NOTE]
> 개인용 게이트웨이의 현재 버전은 **온-프레미스 데이터 게이트웨이(개인용)** 입니다. 이 버전을 사용하도록 설치를 업데이트하세요.
> 
> 

## <a name="update-to-the-latest-version"></a>최신 버전으로 업데이트
게이트웨이 버전이 만료 되 면 많은 문제가 발생할 수 있습니다.  것이 좋습니다는 일반 최신 버전에 있는지 확인 합니다. 한 달 이상 게이트웨이 업데이트 하지 않은 경우에 최신 버전의 게이트웨이 설치 하는 것이 좋습니다. 그런 다음 문제를 재현할 수 있는지를 참조 하세요.

## <a name="installation"></a>설치
**개인 게이트웨이 64 비트** -컴퓨터에 32 비트 이면 개인 게이트웨이 설치할 수 없습니다. 운영 체제는 64 비트 버전을 여야 합니다. Windows의 64 비트 버전을 설치 하거나 64 비트 컴퓨터에서 개인 게이트웨이 설치 합니다.

**개인 게이트웨이 설치에 실패 하는 서비스로 컴퓨터에 대 한 로컬 관리자 인 데도** -사용자가 컴퓨터의 로컬 관리자 그룹에 있지만 그룹 정책이 해당 사용자로 로그인 할를 허용 하지 않습니다 하는 경우 설치가 실패할 수 있습니다는 서비스입니다. 현재 그룹 정책 서비스에 로그인 한 사용자 수를 확인 합니다. 이 문제에 대한 수정 중입니다. [자세히 알아보기](https://technet.microsoft.com/library/cc739424.aspx)

**작업이 시간 초과** -이 메시지는 일반적인 개인 게이트웨이 설치 하는 컴퓨터 (물리적 컴퓨터 또는 VM)에 단일 코어 프로세서가 있는 경우. 애플리케이션을 닫고 필수가 아닌 모든 프로세스를 해제하고 다시 설치해 보세요.

**데이터 관리 게이트웨이 또는 Analysis Services Connector를 개인 게이트웨이와 동일한 컴퓨터에 설치할 수 없습니다.** -이미 Analysis Services Connector 또는 데이터 관리 게이트웨이 설치할 커넥터를 먼저 제거 해야 하는 경우 또는 게이트웨이입니다. 그런 다음 개인 게이트웨이 설치 해 보십시오.

> [!NOTE]
> 설치 하는 동안 문제가 발생 하면 설치 로그는 문제를 해결 하는 데 유용한 정보를 제공할 수 있습니다. 자세한 내용은 [설치 로그](#SetupLogs)합니다.
> 
> 

 **프록시 구성을** 환경에서 프록시를 사용 해야 하는 경우 개인 게이트웨이 구성 하는 문제가 발생할 수 있습니다. 프록시 정보를 구성하는 방법에 대해 자세히 알아보려면 [Power BI 게이트웨이에 프록시 설정 구성](service-gateway-proxy.md)을 참조하세요.

## <a name="schedule-refresh"></a>새로 고침 예약
**오류: 클라우드에 저장된 자격 증명이 누락되었습니다.**

에 대 한 설정에서이 오류가 발생할 수 있습니다 \<데이터 집합\> 새로 고침을 예약 하 고 제거 하 고 경우 개인 게이트웨이 다시 설치 합니다. 개인 게이트웨이 제거 하는 경우 새로 고침을 위해 구성 된 데이터 집합의 데이터 원본 자격 증명은 Power BI 서비스에서 제거 됩니다.

**해결 방법:** Power BI에서 데이터 세트의 새로 고침 설정으로 이동합니다. 데이터 소스 관리에서 오류가 발생 하 여 모든 데이터 원본 선택 **자격 증명 편집** 데이터 원본에 다시 로그인 합니다.

**오류: 데이터 세트에 대해 제공된 자격 증명이 유효하지 않습니다. 계속하려면 새로 고침을 통해 또는 데이터 소스 설정 대화 상자에서 자격 증명을 업데이트하세요.**

**해결 방법**: 자격 증명 메시지를 받는 경우 다음을 의미할 수 있습니다.

* 사용자 이름과 암호가 데이터 원본에 로그인 하는 것에 대 한 최신 상태 인지 확인 합니다. Power BI에서 데이터 세트에 대한 새로 고침 설정으로 이동합니다. 데이터 소스 관리에서 선택 **자격 증명 편집** 데이터 원본에 대 한 자격 증명을 업데이트 합니다.
* 클라우드 원본 서버와 단일 쿼리에서 온-프레미스 원본 간의 매시업 인증에 OAuth를 사용 하는 원본 중 하나 경우 개인 게이트웨이에서 새로 고침에 실패 합니다. 이 문제의 예로 CRM 온라인과 로컬 SQL Server 간의 매시업 있습니다. 매시업은 CRM Online OAuth를 필요로 하기 때문에 실패 합니다.
  
  이 오류는 알려진된 문제 및에서 찾고 됩니다. 문제를 해결 하려면 클라우드 원본과 온-프레미스 원본에 대 한 별도 쿼리가 있어야 합니다. 그런 다음, 병합을 사용 하거나 결합 하는 쿼리를 추가 합니다.

**오류: 지원되지 않는 데이터 원본입니다.**

**해결 방법:** 일정 새로 고침 설정에서 지원되지 않는 데이터 원본 메시지가 표시되면 다음을 의미할 수 있습니다. 

* 데이터 원본은 Power BI에서 새로 고침에 대 한 현재 지원 되지 않습니다. 
* Excel 통합 문서 데이터 모델, 워크시트 데이터만 포함 되어 있지 않습니다. 현재 Power BI는 업로드된 Excel 통합 문서에 데이터 모델이 포함된 경우 새로 고침만 지원합니다. Excel에서 Power Query를 사용하여 데이터를 가져올 때 데이터 모델로 데이터를 로드하는 옵션을 선택해야 합니다. 이 옵션을 사용 하면 데이터 모델에 데이터를 가져옵니다. 

**오류: [데이터를 결합할 수 없습니다.] &lt;쿼리 부분&gt;/&lt;... &gt; / &lt;... &gt; 함께 사용할 수 없는 개인 정보 수준의 데이터 원본에 액세스 합니다. 이 데이터 조합을 다시 작성합니다.**

**해결 방법**: 사용 중인 데이터 원본의 유형 및 개인 정보 수준 제한으로 인해이 오류가입니다.

**오류: 데이터 원본 오류: “\[테이블\]” 값을 테이블 형식으로 변환할 수 없습니다.**

**해결 방법**: 사용 중인 데이터 원본의 유형 및 개인 정보 수준 제한으로 인해이 오류가입니다.

**오류: 이 행에 필요한 공간이 부족합니다.**

크기가 4MB 보다 큰 단일 행이 있는 경우이 오류가 발생 합니다. 데이터 소스에서 행을 찾 및를 필터링 하거나 해당 행에 대 한 크기를 줄입니다.

## <a name="data-sources"></a>데이터 원본
**누락 된 데이터 공급자** – 개인 게이트웨이 64 비트 버전에만 해당 합니다. 64비트 버전의 데이터 공급자를 개인 게이트웨이가 설치한 컴퓨터에 설치해야 합니다. 예를 들어 데이터 세트의 데이터 원본이 Microsoft Access인 경우 개인 게이트웨이를 설치한 컴퓨터에 64비트 ACE 공급자를 설치해야 합니다.  

>[!NOTE]
>32 비트 버전 Excel을 사용 하는 경우 동일한 컴퓨터에 64 비트 ACE 공급자를 설치할 수 없습니다.

**액세스 데이터베이스에 대한 Windows 인증이 지원되지 않음** - 현재 Power BI는 액세스 데이터베이스에 대한 익명 인증만 지원합니다. Access 데이터베이스에 대 한 Windows 인증을 사용 하도록 설정 하면 진행 중입니다.

**데이터 원본에 대 한 자격 증명을 입력할 때 로그인 오류 발생** -개인 게이트웨이의 이전 버전에서 데이터 원본에 대 한 Windows 자격 증명을 입력할 때 이와 같은 오류를 받게 되 면 수 여전히 있습니다. [Power BI Gateway - Personal을 다운로드합니다](https://powerbi.microsoft.com/gateway/).

  ![](media/service-admin-troubleshooting-power-bi-personal-gateway/pbi_pg_credentialserror.jpg.png)

**오류: ACE OLEDB를 사용하여 데이터 원본에 대한 Windows 인증을 선택할 때 로그인 오류 발생** - ACE OLEDB 공급자를 사용하여 데이터 원본에 대한 데이터 원본 자격 증명을 입력할 때 다음 오류가 발생하는 경우:

![](media/service-admin-troubleshooting-power-bi-personal-gateway/aceoledberror.png)

현재 power BI ACE OLEDB 공급자를 사용 하 여 데이터 원본에 대해 Windows 인증을 지원 하지 않습니다.

**해결 방법:** 이 오류를 해결 하기 위해 선택할 수 있습니다 **익명 인증**합니다. 레거시 ACE OLEDB 공급자에 대 한 익명 자격 증명이 Windows 자격 증명와 같습니다.

## <a name="tile-refresh"></a>타일 새로 고침
대시보드 타일 새로 고침을 사용 하 여 오류를 수신 하는 경우 다음 문서를 참조 하십시오.

[타일 오류 문제 해결](refresh-troubleshooting-tile-errors.md)

## <a name="tools-for-troubleshooting"></a>문제 해결을 위한 도구
### <a name="refresh-history"></a>새로 고침 기록
**새로 고침 기록** 어떤 오류가 발생 했는지 확인할 수 있습니다 하 고 지원 요청을 만들어야 할 경우 유용한 데이터를 제공 합니다. 예약 및 주문형: 새로 고침을 볼 수 있습니다. 가져오는 방법은 다음과 같습니다 합니다 **새로 고침 기록**합니다.

1. Power BI 탐색 창의 **데이터 세트**에서 데이터 세트 &gt; 열기 메뉴 &gt;**새로 고침 예약**을 선택합니다.
   ![](media/service-admin-troubleshooting-power-bi-personal-gateway/scheduled-refresh.png)
1. **에 대 한 설정 하는 중...** 을 선택 **새로 고침 기록**합니다.  
   ![](media/service-admin-troubleshooting-power-bi-personal-gateway/scheduled-refresh-2.png)
   
   ![](media/service-admin-troubleshooting-power-bi-personal-gateway/refresh-history.png)

### <a name="event-logs"></a>이벤트 로그
여러 이벤트 로그 정보를 제공할 수 있습니다. 처음 두 **데이터 관리 게이트웨이** 및 **PowerBIGateway**, 컴퓨터의 관리자 인 경우에 표시 됩니다.  개인 게이트웨이 사용 하는 관리자가 아닌 경우를 보면에서 로그 항목의 **응용 프로그램** 로그 합니다.

**데이터 관리 게이트웨이** 및 **PowerBIGateway** 로그는 **애플리케이션 및 서비스 로그**아래에 표시됩니다.

![](media/service-admin-troubleshooting-power-bi-personal-gateway/event-logs.png)

### <a name="fiddler-trace"></a>Fiddler 추적
[Fiddler](http://www.telerik.com/fiddler)는 HTTP 트래픽을 모니터링하는 Telerik의 무료 도구입니다. 클라이언트 컴퓨터에서 Power BI 서비스와의 통신을 볼 수 있습니다. 이 통신 오류 및 기타 관련된 정보를 표시할 수 있습니다.

![](media/service-admin-troubleshooting-power-bi-personal-gateway/fiddler.png)

<a name="SetupLogs"></a>

### <a name="setup-logs"></a>설치 로그
경우는 **Personal Gateway**, 설치에 실패 하면 설치 로그를 표시 하는 링크가 표시 됩니다. 설치 로그는 오류에 대 한 세부 정보를 표시할 수 있습니다. 이러한 로그는 Windows 설치 로그를 MSI 로그 라고도 합니다. 상당히 복잡하고 읽기 어렵습니다. 일반적으로 결과 오류를 아래쪽에 이지만 간단 하지 않습니다 오류의 원인을 파악 합니다. 다른 로그에서의 오류나 로그의 위에서 발생한 오류로 인해 발생할 수 있습니다.

![](media/service-admin-troubleshooting-power-bi-personal-gateway/setup-log.png)

또는 이동할 수 있습니다 하 **Temp 폴더** (%temp%) 로 시작 하는 파일을 찾아볼 **전원\_BI\_** 합니다.

> [!NOTE]
> %temp%로 가면 임시 하위 폴더로 갈 수 있습니다. 합니다 **전원\_BI\_**  파일은 임시 디렉토리의 루트입니다.  하나 또는 두 수준 상위로 이동해야 합니다.
> 
> 

![](media/service-admin-troubleshooting-power-bi-personal-gateway/setup-logs2.png)

## <a name="next-steps"></a>다음 단계
[Power BI Gateway에 대한 프록시 설정 구성](service-gateway-proxy.md)  
[데이터 새로 고침](refresh-data.md)  
[Power BI 게이트웨이 - 개인](service-gateway-personal-mode.md)  
[타일 오류 문제 해결](refresh-troubleshooting-tile-errors.md)  
[온-프레미스 데이터 게이트웨이 문제 해결](service-gateway-onprem-tshoot.md)  
궁금한 점이 더 있나요? [Power BI 커뮤니티를 이용하세요.](http://community.powerbi.com/)

