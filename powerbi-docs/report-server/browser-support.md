---
title: Power BI Report Server에 대한 브라우저 지원
description: Power BI Report Server 및 Report Viewer Controls을 관리하고 보기 위해 지원되는 브라우저 버전에 대해 알아봅니다.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 10/24/2018
ms.author: maggies
ms.openlocfilehash: 5a2ca653a06efbde161899602536b05c8f6ab666
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "64769757"
---
# <a name="browser-support-for-power-bi-report-server"></a>Power BI Report Server에 대한 브라우저 지원
Power BI Report Server 및 Report Viewer Controls을 관리하고 보기 위해 지원되는 브라우저 버전에 대해 알아봅니다.

## <a name="browser-requirements-for-the-web-portal"></a>웹 포털에 대한 브라우저 요구 사항
다음은 웹 포털에 지원되는 브라우저의 현재 목록입니다.

**Microsoft Windows**  
*Windows 7, 8.1, 10; Windows Server 2008 R2, 2012, 2012 R2*

* Microsoft Edge(+)
* Microsoft Internet Explorer 11
* Google Chrome(+)
* Mozilla Firefox(+)

**Apple OS X**  
*OS X 10.9~10.11*

* Apple Safari(+)
* Google Chrome(+)
* Mozilla Firefox(+)

**Apple iOS**  
‘iOS 10 버전의 iPhone 및 iPad’ 

* Apple Safari(+)

**Google Android**  
*Android 4.4(KitKat) 이상 버전의 휴대폰 및 태블릿*

* Google Chrome(+)
  
  **(+)** 최신 공개 릴리스 버전

## <a name="browser-requirements-for-the-report-viewer-web-control-2015"></a>Report Viewer 웹 컨트롤(2015)에 대한 브라우저 요구 사항
다음은 Report Viewer 웹 컨트롤에 지원되는 브라우저의 현재 목록입니다. Report Viewer는 웹 포털에서 보고서 보기를 지원합니다.

**Microsoft Windows**  
*Windows 7, 8.1, 10; Windows Server 2008 R2, 2012, 2012 R2*

* Microsoft Edge(+)
* Microsoft Internet Explorer 11
* Google Chrome(+)
* Mozilla Firefox(+)

**Apple OS X**  
*OS X 10.9~10.11*

* Apple Safari(+)
  
  **(+)** 최신 공개 릴리스 버전

### <a name="authentication-requirements"></a>인증 요구 사항
브라우저는 클라이언트 요청이 성공하기 위해 Report Server에서 처리되어야 하는 특정 인증 체계를 지원합니다. 다음 표에서는 Windows 운영 체제에서 실행 중인 각 브라우저에서 지원하는 기본 인증 유형을 식별합니다.

| **브라우저 형식** | **지원** | **브라우저 기본값** | **서버 기본값** |
| --- | --- | --- | --- |
| **Microsoft Edge**(+) |Negotiate, Kerberos, NTLM, 기본 |협상 |예. 기본 인증 설정은 Edge를 사용합니다. |
| **Microsoft Internet Explorer** |Negotiate, Kerberos, NTLM, 기본 |협상 |예. 기본 인증 설정은 Internet Explorer를 사용합니다. |
| **Google Chrome**(+) |협상, NTLM, 기본 |협상 |예. 기본 인증 설정은 Chrome을 사용합니다. |
| **Mozilla Firefox**(+) |NTLM, 기본 |NTLM |예. 기본 인증 설정은 Firefox를 사용합니다. |
| **Apple Safari**(+) |NTLM, 기본 |기본 |예. 기본 인증 설정은 Safari를 사용합니다. |

 **(+)** 최신 공개 릴리스 버전

### <a name="script-requirements-for-viewing-reports"></a>보고서를 보기 위한 스크립트 요구 사항
보고서 뷰어를 사용하려면 브라우저를 구성하여 스크립트를 실행합니다.

스크립팅을 사용하지 않는 경우 보고서를 열 때 다음과 비슷한 오류 메시지가 나타납니다.

```
Your browser does not support scripts or has been configured to not allow scripts to run. Click here to view this report without scripts
```

 스크립트 지원 없이 보고서를 보려고 선택한 경우 보고서는 보고서 도구 모음과 문서 맵와 같은 보고서 뷰어 기능 없이 HTML로 렌더링됩니다.

> [!NOTE]
> 보고서 도구 모음은 HTML 뷰어 구성의 일부입니다. 기본적으로 도구 모음은 브라우저 창에서 렌더링되는 모든 보고서의 맨 위에 나타납니다. 보고서 뷰어는 정보에 대한 보고서를 검색하고, 특정 페이지로 스크롤하며 보기 편하게 페이지 크기를 조정하는 기능을 제공합니다. 보고서 도구 모음 또는 HTML 뷰어에 대한 자세한 내용은 [HTML 뷰어 및 보고서 도구 모음](https://docs.microsoft.com/sql/reporting-services/html-viewer-and-the-report-toolbar)을 참조하세요.
> 
> 

## <a name="browser-support-for-report-viewer-web-server-controls-in-visual-studio"></a>Visual Studio에서 Report Viewer 웹 서버 컨트롤에 대한 브라우저 지원
Report Viewer 웹 서버 컨트롤은 ASP.NET 웹 애플리케이션에서 보고서 기능을 포함하는 데 사용됩니다. Report Viewer 컨트롤을 가져오는 방법에 대한 자세한 내용은 [Report Viewer 컨트롤을 사용하여 Reporting Services 통합 - 시작](https://docs.microsoft.com/sql/reporting-services/application-integration/integrating-reporting-services-using-reportviewer-controls-get-started)을 참조하세요.

스크립트 지원을 사용하는 브라우저를 사용합니다. 브라우저에서 스크립트를 실행할 수 없는 경우 보고서를 볼 수 없습니다.

**Microsoft Windows**  
*Windows 7, 8.1, 10; Windows Server 2008 R2, 2012, 2012 R2*

* Microsoft Edge(+)
* Microsoft Internet Explorer 11
* Google Chrome(+)
* Mozilla Firefox(+)
  
  **(+)** 최신 공개 릴리스 버전

## <a name="next-steps"></a>다음 단계
[관리자 개요](admin-handbook-overview.md)  
[Power BI Report Server 설치](install-report-server.md)  
[보고서 작성기 다운로드](https://www.microsoft.com/download/details.aspx?id=53613)  
[SSDT(SQL Server Data Tools) 다운로드](http://go.microsoft.com/fwlink/?LinkID=616714)

궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](https://community.powerbi.com/)

