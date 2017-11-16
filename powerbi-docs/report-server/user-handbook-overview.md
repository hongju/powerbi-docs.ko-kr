---
title: "Power BI Report Server에 대한 사용자 안내서 개요"
description: "Power BI, 모바일, 페이지가 매겨진 보고서 및 KPI를 보고, 저장하고 관리하는 온-프레미스 위치인 Power BI Report Server의 사용자 안내서를 시작합니다."
services: powerbi
documentationcenter: 
author: maggiesMSFT
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
ms.author: maggies
ms.openlocfilehash: 9b9fc6e9d93fb5e38eb8d0fb5606e4cef1d78940
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2017
---
# <a name="user-handbook-overview-for-power-bi-report-server"></a>Power BI Report Server에 대한 사용자 안내서 개요
Power BI, 모바일, 페이지가 매겨진 보고서 및 KPI를 보고, 저장하고 관리하는 온-프레미스 위치인 Power BI Report Server의 사용자 안내서를 시작합니다.

![](media/user-handbook-overview/web-portal.png)

또한 Power BI Report Server는 데이터를 활용하기 위해 사용하는 제품 및 환경을 설정합니다.

* 모든 최신 브라우저에서 볼 수 있는 [웹 포털](#web-portal)입니다. 웹 포털의 폴더에서 보고서 및 KPI를 구성하고 표시하며 즐겨찾기로 표시할 수 있습니다. 거기에 Excel 통합 문서를 저장할 수도 있습니다.
* Power BI Desktop을 사용하여 만든 [Power BI 보고서](#power-bi-reports)는 웹 포털 및 Power BI 모바일 앱 내에서 확인합니다.
* [페이지가 매겨진 보고서](#paginated-reports)는 최신 수준의 고정 레이아웃 문서로써 이를 만드는 도구를 포함하여 인쇄에 최적화되었습니다.

각각에 대한 자세한 내용을 참고하세요.

## <a name="web-portal"></a>웹 포털
![](media/user-handbook-overview/web-portal.png)

Power BI Report Server는 모든 최신 브라우저에서 볼 수 있는 최신 웹 포털 기능입니다. 새 포털에서 모든 보고서 및 KPI에 액세스할 수 있습니다.

웹 포털은 조직에서 사용자 지정 브랜딩의 기능을 담당하고 웹 포털에서 KPI를 표시할 수 있습니다. KPI는 보고서를 열 필요가 없도록 브라우저에서 주요 비즈니스 메트릭을 한눈에 노출할 수 있습니다.

웹 포털의 콘텐츠를 폴더 및 각 폴더 내에서 구성하고 Power BI 보고서, 모바일 보고서, 페이지가 매겨진 보고서와 KPI 및 Excel 통합 문서의 형식으로 구성됩니다. 즐겨찾는 보고서 및 KPI를 태그할 수 있습니다. 모두 즐겨찾기 폴더에 수집되어 있으므로 빠르게 찾을 수 있습니다.

## <a name="power-bi-reports"></a>Power BI 보고서
![](media/user-handbook-overview/powerbi-reports.png)

Power BI 보고서는 데이터 집합의 다양한 결과 및 통찰력을 나타내는 시각화가 포함된 다각적인 데이터 뷰입니다. 보고서는 단일 시각화나 여러 페이지의 시각화를 포함할 수 있습니다. 작업에 따라 사용자는 보고서를 만들고 보고서를 보거나 조작하는 사람이 될 수 있습니다.

보고서는 단일 데이터 집합을 기반으로 합니다. 각 보고서의 시각화는 각기 정보 모음을 나타냅니다. 그리고 시각화는 고정되지 않습니다. 대시보드와 거의 유사하게 보고서는 대화형이며 사용자 지정이 가능하고 기본 데이터가 변경되면 시각화도 업데이트됩니다.

* 사용자가 보고서 작성자라면 데이터를 추가하고 제거하거나 시각화를 추가하고 다시 정렬하거나 시각화 형식을 변경할 수 있습니다.
* 사용자가 보고서 뷰어라면 정보를 발견하고 답변을 찾기 위해 데이터를 자세히 알아보도록 필터 및 슬라이서를 정렬하고 적용할 수 있습니다.

특별한 버전의 Power BI Desktop을 사용하여 Power BI 보고서를 만듭니다. [Microsoft Power BI Desktop](https://go.microsoft.com/fwlink/?linkid=837581)을 다운로드합니다(Power BI Report Server에 최적화됨 - 2017년 10월 GA).

## <a name="paginated-reports"></a>페이지가 매겨진 보고서
![](media/user-handbook-overview/paginated-reports.png)

페이지가 매겨진 보고서는 데이터가 더 많고, 테이블에 행이 더 많고 보고서에 페이지가 더 많을수록 문서 스타일의 보고서가 됩니다. PDF 및 Word 파일과 같이 유용한 고정 레이아웃의 완벽한 픽셀 문서를 인쇄를 위해 최적화합니다.

[SSDT(SQL Server Data Tools)](https://docs.microsoft.com/sql/reporting-services/tools/reporting-services-in-sql-server-data-tools-ssdt)에서 [보고서 작성기](https://docs.microsoft.com/sql/reporting-services/report-builder/report-builder-in-sql-server-2016) 또는 보고서 디자이너를 사용하여 이러한 페이지가 매겨진 보고서를 만듭니다.

## <a name="next-steps"></a>다음 단계
[Power BI Report Server에 최적화된 Power BI Desktop 설치](install-powerbi-desktop.md)  
[빠른 시작: 페이지가 매겨진 보고서](quickstart-create-paginated-report.md)  
[빠른 시작: Power BI 보고서](quickstart-create-powerbi-report.md)

궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](https://community.powerbi.com/)

