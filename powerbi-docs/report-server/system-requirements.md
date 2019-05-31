---
title: Power BI Report Server를 설치하기 위한 하드웨어 및 소프트웨어 요구 사항
description: 이 문서에는 Power BI Report Server를 설치하고 실행하기 위한 최소 하드웨어 및 소프트웨어 요구 사항이 표시됩니다.
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 11/08/2018
ms.openlocfilehash: 063ab8083c3091a7a41ca30e9045ce3a791112d2
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "64770018"
---
# <a name="hardware-and-software-requirements-for-installing-power-bi-report-server"></a>Power BI Report Server를 설치하기 위한 하드웨어 및 소프트웨어 요구 사항

이 문서에는 Power BI Report Server를 설치하고 실행하기 위한 최소 하드웨어 및 소프트웨어 요구 사항이 표시됩니다.

## <a name="processor-memory-and-operating-system-requirements"></a>프로세서, 메모리 및 운영 체제 요구 사항

| 구성 요소 | 요구 사항 |
| --- | --- |
| .NET Framework |4.6<br><br>[Windows용 Microsoft .NET Framework 4.6(웹 설치 관리자)](http://support.microsoft.com/kb/3045560)에서 .NET Framework를 수동으로 설치할 수 있습니다.<br/><br/> .NET Framework 4.6에 대한 자세한 정보, 권장 사항 및 지침은 [개발자를 위한 .NET Framework 배포 가이드](http://msdn.microsoft.com/library/ee942965\(v=vs.110\).aspx)를 참조하세요.<br/><br/>.NET Framework 4.6을 설치하기 전에 Windows 8.1 및 Windows Server 2012 R2에는 [KB2919355](http://support.microsoft.com/kb/2919355)가 필요합니다. |
| 하드 디스크 |Power BI Report Server에는 최소 1GB의 하드 디스크 여유 공간이 필요합니다.<br><br>Report Server 데이터베이스를 호스팅하는 데이터베이스 서버에 추가 공간이 필요합니다. |
| 메모리 |**최소값:** 1GB<br/><br/> **권장:** 최소 4GB |
| 프로세서 속도 |**최소:** x64 프로세서: 1.4GHz<br/><br/> **권장:** 2.0GHz 이상 |
| 프로세서 형식 |x64 프로세서: AMD Opteron, AMD Athlon 64, Intel EM64T가 지원되는 Intel Xeon, EM64T가 지원되는 Intel Pentium IV |
| 운영 체제 |Windows Server 2019 Datacenter<br><br>Windows Server 2019 Standard<br><br>Windows Server 2016 Datacenter<br><br>Windows Server 2016 Standard<br><br>Windows Server 2012 R2 Datacenter<br><br>Windows Server 2012 R2 Standard<br><br>Windows Server 2012 R2 Essentials<br><br>Windows Server 2012 R2 Foundation<br><br>Windows Server 2012 Datacenter<br><br>Windows Server 2012 Standard<br><br>Windows Server 2012 Essentials<br><br>Windows Server 2012 Foundation<br><br>Windows 10 Home<br><br>Windows 10 Professional<br><br>Windows 10 Enterprise<br><br>Windows 8.1<br><br>Windows 8.1 Pro<br><br>Windows 8.1 Enterprise<br><br>Windows 8<br><br>Windows 8 Pro<br><br>Windows 8 Enterprise |

> [!NOTE]
> Power BI Report Server는 x64 설치는 프로세서에서만 지원됩니다.


## <a name="database-server-version-requirements"></a>데이터베이스 서버 버전 요구 사항

보고서 서버 데이터베이스를 호스팅하는 데 SQL Server를 사용합니다. SQL Server 데이터베이스 엔진 인스턴스는 로컬 또는 원격 인스턴스일 수 있습니다. 다음은 보고서 서버 데이터베이스를 호스팅하는 데 사용할 수 있는 지원되는 버전의 SQL Server 데이터베이스 엔진입니다.

* SQL Server 2017
* SQL Server 2016
* SQL Server 2014
* SQL Server 2012

원격 컴퓨터에서 보고서 서버 데이터베이스를 만들 때 네트워크 액세스 권한을 가진 도메인 사용자 계정 또는 서비스 계정을 사용하도록 연결을 구성해야 합니다. 원격 SQL Server 인스턴스를 사용하려는 경우 보고서 서버가 SQL Server 인스턴스에 연결하는 데 사용해야 하는 자격 증명을 신중하게 선택하는 것이 좋습니다. 자세한 내용은 [Report Server 데이터베이스 연결 구성](https://docs.microsoft.com/sql/reporting-services/install-windows/configure-a-report-server-database-connection-ssrs-configuration-manager)을 참조하세요.

## <a name="considerations"></a>고려 사항

Power BI Report Server는 Report Server를 작동하는 데 필요한 핵심 설정을 구성하는 기본값을 설치합니다. 다음 요구 사항을 포함합니다.

* 설치한 이후 및 Report Server 데이터베이스를 구성하기 전에 SQL Server 데이터베이스 엔진을 사용할 수 있어야 합니다. 데이터베이스 엔진 인스턴스는 Reporting Services 구성 관리자가 만들 Report Server 데이터베이스를 호스팅합니다. 데이터베이스 엔진은 실제 설치 환경에 필요하지 않습니다.
* [SQL Server 버전에서 지원되는 Reporting Services 기능](https://docs.microsoft.com/sql/reporting-services/reporting-services-features-supported-by-the-editions-of-sql-server-2016)에서는 SQL Server 버전 간의 차이점을 설명합니다.
* 설치 프로그램을 실행하는 사용자 계정은 로컬 관리자 그룹의 멤버여야 합니다.
* Reporting Services 구성 관리자를 실행하는 사용자 계정에는 보고서 서버 데이터베이스를 호스트하는 데이터베이스 엔진 인스턴스에 있는 데이터베이스에 액세스하고 해당 데이터베이스를 만들 권한이 있어야 합니다.
* 설치 마법사는 기본값을 사용하여 Report Server와 웹 포털에 대한 액세스를 제공하는 URL을 예약할 수 있어야 합니다. 기본값은 **ReportServer** 및 **보고서**에 있는 포트 80, 강력한 와일드 카드 및 가상 디렉터리 이름입니다.

## <a name="read-only-domain-controller-rodc"></a>RODC(읽기 전용 도메인 컨트롤러)

 RODC(읽기 전용 도메인 컨트롤러)가 있는 환경에 보고서 서버를 설치할 수 있습니다. 그러나 Reporting Services가 제대로 작동하려면 읽기/쓰기 도메인 컨트롤러에 대한 액세스가 필요합니다. Reporting Services가 RODC에 액세스할 수 있는 경우 서비스를 관리하려고 할 때 오류가 발생할 수 있습니다.

## <a name="power-bi-reports-and-analysis-services-live-connections"></a>Power BI 보고서 및 Analysis Services 라이브 연결

테이블 형식 또는 다차원 인스턴스에 대해 라이브 연결을 사용할 수 있습니다. Analysis Services 서버가 제대로 작동하려면 적절한 버전이어야 합니다.

| **서버 버전** | **필수 SKU** |
| --- | --- |
| 2012 SP1 CU4 이상 |비즈니스 인텔리전스 및 Enterprise SKU |
| 2014 |비즈니스 인텔리전스 및 Enterprise SKU |
| 2016 이상 |표준 SKU 이상 |

## <a name="next-steps"></a>다음 단계

[Power BI Report Server란?](get-started.md)  
[관리자 개요](admin-handbook-overview.md)  
[Power BI Report Server 설치](install-report-server.md)  
[보고서 작성기 다운로드](https://www.microsoft.com/download/details.aspx?id=53613)  
[SSDT(SQL Server Data Tools) 다운로드](http://go.microsoft.com/fwlink/?LinkID=616714)

궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](https://community.powerbi.com/)