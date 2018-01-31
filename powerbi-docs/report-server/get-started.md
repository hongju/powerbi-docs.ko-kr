---
title: "Power BI Report Server 시작"
description: "Power BI Report Server를 설치하는 방법을 알아봅니다. "
services: powerbi
documentationcenter: 
author: markingmyname
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
ms.date: 11/01/2017
ms.author: maghan
ms.openlocfilehash: 61558613b0022f7585b31c3e3d674a64ea009d61
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/30/2018
---
# <a name="get-started-with-power-bi-report-server"></a>Power BI Report Server 시작
Power BI Report Server에서 제공하는 즉시 사용할 도구와 서비스의 범위에서 Power BI, 모바일 및 페이지가 매겨진 온-프레미스 보고서를 만들고, 배포하고 관리합니다.

## <a name="create-deploy-and-manage-reports"></a>보고서 만들기, 배포 및 관리
Power BI Report Server는 웹 브라우저, 해당 모바일 장치 또는 Windows 제공 이메일에서 볼 수 있는지 여부와 상관없이 고객이 보고서를 만들고 게시하고 관리한 다음 다른 방식으로 사용자에게 바로 전달하는 고유한 온-프레미스에 배포하는 솔루션입니다.

Power BI Report Server는 제품 모음을 제공합니다.

* 모든 최신 브라우저에서 볼 수 있는 최신 웹 포털입니다. 웹 포털에서 보고서 및 KPI를 구성하고 표시할 수 있습니다. 포털에 Excel 통합 문서를 저장할 수도 있습니다.
* Power BI Desktop을 사용하여 만든 Power BI 보고서는 웹 포털 및 고유한 환경에서 볼 수 있습니다.
* 페이지가 매겨진 보고서 및 해당 보고서를 만드는 도구를 사용하여 최신 보고서를 만들 수 있습니다.
* 반응형 레이아웃인 모바일 보고서는 보유한 다양한 장치 및 방법에 맞게 조정합니다.

각각에 대한 자세한 내용을 참고하세요.

### <a name="whats-new-in-power-bi-report-server"></a>Power BI Report Server의 새로운 기능
이러한 소스는 Power BI Report Server에서 새로운 기능을 최신 상태로 유지합니다.

* [Power BI Report Server의 새로운 기능](whats-new.md)
* [Microsoft Power BI 블로그](https://powerbi.microsoft.com/blog/)
* [SQL Server Reporting Services 팀 블로그](https://blogs.msdn.microsoft.com/sqlrsteamblog/)
* [큐브에서 Guy YouTube 채널](https://aka.ms/guyinacube)

## <a name="web-portal"></a>웹 포털
![](media/get-started/web-portal.png)

Power BI Report Server의 최종 사용자에게는 모든 최신 브라우저에서 볼 수 있는 최신 웹 포털입니다. 새 포털에서 모든 보고서 및 KPI에 액세스할 수 있습니다.

웹 포털에 사용자 고유의 사용자 지정 [브랜딩](https://docs.microsoft.com/sql/reporting-services/branding-the-web-portal)을 적용할 수 있습니다. 웹 포털에서 KPI를 만들 수 있습니다. KPI는 보고서를 열지 않고 브라우저에서 주요 비즈니스 메트릭을 한눈에 노출할 수 있습니다.

웹 포털의 콘텐츠는 Power BI 보고서, 모바일 보고서, 페이지가 매겨진 보고서와 KPI 및 Excel 통합 문서, 공유 데이터 집합 및 공유 데이터 소스 등의 형식으로 구성되어 보고서에 대한 문서 블록으로 사용합니다. 기존 폴더 계층 구조에서 안전하게 저장하고 관리할 수 있습니다. 즐겨찾기에 태그를 지정하고 해당 역할을 담당하는 경우 콘텐츠를 관리할 수 있습니다.

보고서 처리를 예약하고, 요청 시 보고서에 액세스하고, 새 웹 포털에서 게시된 보고서를 구독할 수 있습니다.

[웹 포털](https://docs.microsoft.com/sql/reporting-services/web-portal-ssrs-native-mode)에 대한 자세한 정보입니다.

## <a name="power-bi-reports"></a>Power BI 보고서
![](media/get-started/powerbi-reports.png)

Power BI 보고서는 데이터 집합의 다양한 결과 및 통찰력을 나타내는 시각화가 포함된 다각적인 데이터 뷰입니다.  보고서는 단일 시각화나 여러 페이지의 시각화를 포함할 수 있습니다. 작업 역할에 따라 보고서를 만들거나, 사용하거나 소비하는 사용자가 될 수 있습니다.

보고서는 단일 데이터 집합을 기반으로 합니다. 각 보고서의 시각화는 각기 정보 모음을 나타냅니다. 시각화 요소는 정적인 것이 아니므로 사용자가 데이터를 조사하여 정보와 답변을 찾아가는 과정에서 데이터를 추가 및 제거하고 시각화 유형을 변경하며 필터 및 슬라이서를 적용할 수 있습니다. 대시보드와 거의 유사하게 보고서도 대화형이며 자유롭게 사용자 지정이 가능하고 기본 데이터가 변경되면 시각화도 업데이트됩니다. 

## <a name="paginated-reports"></a>페이지가 매겨진 보고서
![](media/get-started/paginated-reports.png)

페이지가 매겨진 보고서는 데이터가 더 많고, 테이블에 행이 더 많고 보고서에 페이지가 더 많을수록 페이지가 매겨진 문서 스타일의 보고서가 됩니다. PDF 및 Word 파일과 같이 유용한 고정 레이아웃의 완벽한 픽셀 문서를 인쇄에 최적화하도록 만듭니다.

[SSDT(SQL Server Data Tools)](https://docs.microsoft.com/sql/reporting-services/tools/reporting-services-in-sql-server-data-tools-ssdt)에서 [보고서 작성기](https://docs.microsoft.com/sql/reporting-services/report-builder/report-builder-in-sql-server-2016) 또는 보고서 디자이너를 사용하여 최신 보고서를 만들 수 있습니다.

## <a name="report-server-programming-features"></a>Report Server 프로그래밍 기능
Power BI Report Server 프로그래밍 기능을 활용하여 API를 사용하는 보고 기능을 확장하고 사용자 지정하여 사용자 지정 응용 프로그램에서 데이터 및 보고서 처리를 통합하거나 확장할 수 있습니다.

더 많은 [Report Server 개발자 설명서](https://docs.microsoft.com/sql/reporting-services/reporting-services-developer-documentation)가 있습니다.

## <a name="next-steps"></a>다음 단계
[사용자 안내서](user-handbook-overview.md)  
[관리자 안내서](admin-handbook-overview.md)  
[빠른 시작: Power BI Report Server 설치](quickstart-install-report-server.md)  
[보고서 작성기 설치](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder)  
[SSDT(SQL Server Data Tools) 다운로드](http://go.microsoft.com/fwlink/?LinkID=616714)

궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](https://community.powerbi.com/)

