---
title: Power BI Desktop을 시작할 때 발생하는 문제 해결
description: Power BI Desktop을 시작할 때 발생하는 문제 해결
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/14/2020
ms.author: davidi
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 67c83f2cc0eb81e90f447961ed178a04e97e050e
ms.sourcegitcommit: 3d6b27e3936e451339d8c11e9af1a72c725a5668
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2020
ms.locfileid: "76160906"
---
# <a name="troubleshoot-opening-power-bi-desktop"></a>Power BI Desktop 열기 문제 해결

Power BI Desktop에서 이전 버전의 *Power BI 온-프레미스 데이터 게이트웨이*를 설치하고 실행하는 사용자는 Power BI 온-프레미스 게이트웨이가 로컬 컴퓨터의 명명된 파이프에 설정하는 관리 정책 제한 때문에 Power BI Desktop을 열지 못할 수 있습니다.

## <a name="resolve-issues-with-the-on-premises-data-gateway-and-power-bi-desktop"></a>온-프레미스 데이터 게이트웨이 및 Power BI Desktop 문제 해결

온-프레미스 데이터 게이트웨이와 관련된 문제를 해결하고 Power BI Desktop을 열 수 있는 세 가지 방법이 있습니다.

### <a name="resolution-1-install-the-latest-version-of-power-bi-on-premises-data-gateway"></a>해결 방법 1: 최신 버전의 Power BI 온-프레미스 데이터 게이트웨이 설치

최신 버전의 Power BI 온-프레미스 데이터 게이트웨이는 로컬 컴퓨터에 명명된 파이프 제한을 설정하지 않으며 Power BI Desktop이 제대로 열립니다. Power BI 온-프레미스 데이터 게이트웨이를 계속 사용해야 하는 경우 업데이트하는 방법이 권장됩니다. [최신 버전의 Power BI 온-프레미스 데이터 게이트웨이](https://go.microsoft.com/fwlink/?LinkId=698863)를 다운로드할 수 있습니다. 이 링크는 설치 실행 파일 직접 다운로드 링크입니다.

### <a name="resolution-2-uninstall-or-stop-the-power-bi-on-premises-data-gateway-microsoft-service"></a>해결 방법 2: Power BI 온-프레미스 데이터 게이트웨이 Microsoft 서비스 제거 또는 중지

더 이상 필요하지 않은 경우 Power BI 온-프레미스 데이터 게이트웨이를 제거할 수 있습니다. 또는 Power BI 온-프레미스 데이터 게이트웨이 Microsoft 서비스를 중지하여 정책 제한을 제거하고 Power BI Desktop을 열 수 있습니다.

### <a name="resolution-3-run-power-bi-desktop-with-administrator-privilege"></a>해결 방법 3: 관리자 권한으로 Power BI Desktop 실행

또는 관리자 권한으로 Power BI Desktop을 시작할 수도 있습니다. 이 경우에도 Power BI Desktop이 성공적으로 열립니다. 앞에서 설명한 대로 최신 버전의 Power BI 온-프레미스 데이터 게이트웨이를 설치하는 것이 좋습니다.

Power BI Desktop은 멀티 프로세스 아키텍처로 설계되었으며, 이러한 여러 프로세스는 Windows 명명된 파이프를 사용하여 통신합니다. 해당 명명된 파이프를 방해하는 다른 프로세스가 있을 수 있습니다. 바이러스 백신 소프트웨어 또는 방화벽이 파이프를 차단하거나 트래픽을 특정 포트로 리디렉션할 수 있는 상황을 포함하여 이러한 방해의 가장 일반적인 이유는 보안입니다. 관리자 권한으로 Power BI Desktop을 열면 해당 문제가 해결될 수 있습니다. 관리자 권한으로도 열 수 없는 경우 관리자에게 문의하여 명명된 파이프가 제대로 통신하지 못하도록 하는 보안 규칙을 확인합니다. 그런 다음 Power BI Desktop 및 해당 하위 프로세스를 허용 목록에 포함합니다.

## <a name="resolve-issues-when-connecting-to-sql-server"></a>SQL Server 연결 시 문제 해결

SQL Server 데이터베이스에 연결하려고 할 때 다음 텍스트와 유사한 오류 메시지가 표시될 수 있습니다.

`"An error happened while reading data from the provider:`\
`'Could not load file or assembly 'System.EnterpriseServices, Version=4.0.0.0, Culture=neutral, PublicKeyToken=xxxxxxxxxxxxx' or one of its dependencies.`\
`Either a required impersonation level was not provided, or the provided impersonation level is invalid. (Exception from HRESULT: 0x80070542)'"`

SQL Server 연결 전에 관리자 권한으로 Power BI Desktop을 열면 문제를 해결할 수 있는 경우가 많습니다.

관리자 권한으로 Power BI Desktop을 열고 연결을 설정하면 필수 DLL이 제대로 등록됩니다. 이후에는 관리자 권한으로 Power BI Desktop을 열 필요가 없습니다.

## <a name="get-help-with-other-launch-issues"></a>다른 시작 문제에 대한 도움말 보기

Power BI Desktop에서 발생하는 문제를 최대한 처리하려고 노력하고 있습니다. 당사는 많은 고객에 영향을 줄 수 있는 문제를 정기적으로 살펴보고 문서에 포함시키고 있습니다.

Power BI Desktop 열기 관련 문제가 온-프레미스 데이터 게이트웨이와 관련이 없거나 앞의 해결 방법이 효과가 없는 경우 *Power BI 지원팀*(<https://support.powerbi.com>)에 인시던트를 제출하여 문제를 식별하고 해결할 수 있습니다.

향후 Power BI Desktop와 관련된 다른 문제가 발생할 경우에 대비하여 추적을 설정하고 로그 파일을 수집하는 것이 좋습니다. 로그 파일은 문제를 격리하고 식별하는 데 도움이 됩니다. 추적을 설정하려면 **파일** > **옵션 및 설정** > **옵션**을 선택하고 **진단**을 선택한 다음 **추적 사용**을 선택합니다. 이 옵션을 설정하려면 Power BI Desktop이 실행 중이어야 하지만 Power BI Desktop 열기와 관련된 이후 문제에 유용합니다.
