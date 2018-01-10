---
title: "빠른 시작: Power BI Report Server 설치"
description: "Power BI Report Server 자체를 신속하게 설치할 수 있습니다. 몇 분 이내에 다운로드, 설치 및 구성하도록 실행합니다."
services: powerbi
documentationcenter: 
author: guyinacube
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 06/28/2017
ms.author: maghan
ms.openlocfilehash: 934b4d3f2da44a161cd76d14c9f042aaf697f26d
ms.sourcegitcommit: eec6b47970bf69ed30638d1a20051f961ba792f2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/06/2018
---
# <a name="quickstart-install-power-bi-report-server"></a>빠른 시작: Power BI Report Server 설치
Power BI Report Server 자체를 신속하게 설치할 수 있습니다. 몇 분 이내에 다운로드, 설치 및 구성하도록 실행합니다.

새 서버에서 실행하려면 여기에서 Report Server를 설치하는 방법을 간략히 알아봅니다. Report Server를 설치하는 방법에 자세한 정보는 [Power BI Report Server 설치](install-report-server.md)를 참조하세요.

 **다운로드** ![다운로드](media/quickstart-install-report-server/download.png "다운로드")

Power BI Report Server를 다운로드하려면 [Power BI Report Server를 사용하여 온-프레미스 보고](https://powerbi.microsoft.com/report-server/)로 이동합니다. Power BI Report Server에 최적화된 Power BI Desktop을 다운로드하려면 [Microsoft 다운로드 센터](https://go.microsoft.com/fwlink/?linkid=837581)로 이동합니다.

![팁](media/quickstart-install-report-server/fyi-tip.png "팁") 현재 릴리스 정보는 [Power BI Report Server - 릴리스 정보](release-notes.md)를 참조하세요.

<iframe width="640" height="360" src="https://www.youtube.com/embed/zacaEb9A4F0?showinfo=0" frameborder="0" allowfullscreen></iframe>

## <a name="before-you-begin"></a>시작하기 전에
Power BI Report Server를 설치하기 전에 [Power BI Report Server를 설치하기 위한 하드웨어 및 소프트웨어 요구 사항](system-requirements.md)을 검토하는 것이 좋습니다.

## <a name="step-1-download"></a>1단계: 다운로드
Power BI Report Server에 대한 설치 파일을 로컬로 다운로드합니다. Power BI Report Server를 다운로드하려면 [Microsoft 다운로드 센터](https://go.microsoft.com/fwlink/?linkid=839351)로 이동합니다.

![Power BI Report Server 다운로드](media/quickstart-install-report-server/download-pbireportserver.png)

## <a name="step-2-run-installer"></a>2단계: 설치 관리자 실행
다운로드한 PowerBIReportServer.exe 파일 및 설치 화면을 통한 단계를 실행합니다. 설치 경로뿐만 아니라 설치하려는 버전도 같이 선택할 기회가 있습니다. 180일 이내에 만료되는 개발자 버전을 사용할지 아니면 제품 키를 제공할지를 선택할 수 있습니다.

![Power BI Report Server 설치](media/quickstart-install-report-server/pbireportserver-install.png)

## <a name="step-3-configure-the-server"></a>3단계: 서버 구성
설치를 완료한 후에 서버 설정을 완료하기 위해 구성 관리자를 실행합니다. ReportServer 카탈로그 데이터베이스를 만들 뿐만 아니라 웹 포털 및 웹 서비스 URL을 확인해야 합니다.

![Power BI Report Server 구성](media/quickstart-install-report-server/pbireportserver-configure.png)

## <a name="step-4-browse-to-web-portal"></a>4단계: 웹 포털로 이동
이제 구성했으므로 서버의 웹 포털로 브라우저를 열 수 있습니다. 기본적으로 `http://localhost/reports`입니다. 또한 방화벽의 형식에 의해 차단되지 않는다고 가정하면 기본적으로 localhost를 사용하는 대신 컴퓨터 이름을 사용하여 탐색할 수 있습니다.

![Power BI Report Server 웹 포털](media/quickstart-install-report-server/web-portal.png)

## <a name="next-steps"></a>다음 단계
[관리자 안내서](admin-handbook-overview.md)  
[보고서 서버 제품 키를 확인하는 방법](find-product-key.md)  
[Power BI Report Server 설치](install-report-server.md)  
[Power BI Report Server에 최적화된 Power BI Desktop 설치](install-powerbi-desktop.md)  
[Power BI Report Server에 대한 브라우저 지원](browser-support.md)

궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](https://community.powerbi.com/)

