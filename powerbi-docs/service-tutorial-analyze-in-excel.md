---
title: '자습서:  Excel에서 분석 사용'
description: 이 자습서에서는 Power BI 데이터 세트 페이지를 사용하여 데이터 세트를 Excel로 가져옵니다.
author: tejaskulkarni
ms.reviewer: davidiseminger
ms.service: powerbi
ms.subservice: powerbi-service
ms.custom: connect-to-services
ms.topic: tutorial
ms.date: 01/27/2020
ms.author: tekulkar
LocalizationGroup: Connect to services
ms.openlocfilehash: a68adccec019e64e554d199d23d7dddd782f56a2
ms.sourcegitcommit: 53c2b5ea4ee1fe2659804d5ccc8e4bb445a8bcad
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/01/2020
ms.locfileid: "76921488"
---
# <a name="tutorial-use-analyze-in-excel"></a>자습서:  Excel에서 분석 사용

조직에서 Power BI를 사용하여 데이터에 대한 액세스를 공유합니다. Excel에서 분석 기능을 사용하여 피벗 테이블 및 피벗 차트를 만들어 분석에 추가 컨텍스트를 가져오거나 관련 데이터 세트를 찾고 가져오는 데 걸리는 시간을 줄일 수 있습니다.

데이터 세트 선택을 시작하려면 'Excel에서 분석'을 선택합니다. 데이터를 사용하는 피벗 테이블을 만드는 방법이 안내됩니다.  

데이터 세트 페이지로 돌아가면 조직에서 공유하는 추가 데이터 세트를 찾을 수 있습니다.

어느 지점에서든 문제가 발생하는 경우 아래 흐름의 해당 단계에서 아니요를 선택하고 연결된 양식에 피드백을 제공합니다.  

이 자습서에서는 다음 작업을 수행하는 방법을 알아봅니다.

> [!div class="checklist"]
> * Power BI 데이터 세트 페이지에서 ODC 파일을 다운로드합니다.
> * Excel에서 데이터 세트에 액세스할 수 있도록 설정합니다.
> * 데이터 세트를 사용하여 피벗 테이블, 차트 및 워크시트를 만들기 시작합니다.

## <a name="prerequisites"></a>필수 조건

이 자습서를 완료하려면 다음이 필요합니다.

* Power BI 계정. 아직 Power BI에 등록하지 않은 경우 시작하기 전에 [평가판에 등록합니다](https://app.powerbi.com/signupredirect?pbi_source=web).

* [Power BI 서비스 시작하기](https://docs.microsoft.com/power-bi/service-get-started) 자습서에 나열된 모든 단계를 잘 알고 있어야 합니다.

* Power BI Premium 데이터 세트 및 Power BI Pro 라이선스가 필요합니다. 자세한 내용은 [Power BI Premium이란?](https://docs.microsoft.com/power-bi/service-premium-what-is)을 참조하세요.

* 전체 필수 구성 요소 목록은 [Excel에서 분석](https://docs.microsoft.com/power-bi/service-analyze-in-excel#requirements) 문서에서 찾을 수 있습니다.

* 활성 [Microsoft Office E5 구독](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab)

## <a name="get-started"></a>시작

Excel에서 시작하여, Power BI 공유 데이터를 사용하여 피벗 테이블을 만드는 옵션을 선택하고 Power BI 데이터 세트 페이지로 이동합니다.

![데이터 세트 페이지](media/service-tutorial-analyze-in-excel/tutorial-analyze-in-excel-01.png)

Excel에서 분석 워크플로를 사용하는 동안 안내 메시지가 여러 번 표시됩니다. 각 단계를 완료하여 다음 단계로 진행할 수 있는지 여부를 표시합니다. 어느 단계에서든 문제가 발생하는 경우 **아니요**를 선택하고 해당 양식에 대한 피드백을 제공합니다.

![워크플로 지침](media/service-tutorial-analyze-in-excel/tutorial-analyze-in-excel-02.png)

## <a name="download-and-open-the-odc-file"></a>ODC 파일 다운로드 및 열기

해당 목록 및 연결된 작업 영역에서 데이터 세트를 선택한 다음 Excel에서 분석을 클릭합니다. Power BI가 ODC 파일을 만들고 브라우저에서 컴퓨터로 다운로드합니다.

![데이터 세트 선택](media/service-tutorial-analyze-in-excel/tutorial-analyze-in-excel-03.png)

Excel에서 그 파일을 열면, Power BI 데이터 세트의 테이블, 필드 및 측정값과 함께 빈 피벗 테이블 및 필드 목록이 표시됩니다. Excel에서 로컬 데이터 세트로 작업하는 것처럼 피벗 테이블, 차트를 만들고 데이터 세트를 분석할 수 있습니다.

## <a name="enable-data-connections"></a>데이터 연결 사용

Excel에서 Power BI 데이터를 분석하기 위해 연결을 신뢰하라는 메시지가 표시될 수 있습니다. 관리자는 Power BI 관리 포털에서 Analysis Services 데이터베이스의 온-프레미스 데이터 세트에 Excel에서 분석을 사용하지 않도록 설정할 수 있습니다.

![연결 사용](media/service-tutorial-analyze-in-excel/tutorial-analyze-in-excel-04.png)

## <a name="install-updates-and-authenticate"></a>업데이트 설치 및 인증

새 ODC 파일을 처음 열 때 Power BI 계정으로 인증해야 할 수도 있습니다.  문제가 있는 경우 [Excel에서 분석](https://docs.microsoft.com/power-bi/service-analyze-in-excel#sign-in-to-power-bi ) 문서에서 자세한 내용을 참조하거나 워크플로 도중 아니요를 클릭합니다.

![연결 사용](media/service-tutorial-analyze-in-excel/tutorial-analyze-in-excel-05.png)

## <a name="analyze-away"></a>분석

다른 로컬 통합 문서와 마찬가지로 Excel에서 분석을 사용하면 피벗 테이블과 차트를 만들고, 데이터를 추가하고, 데이터에 대한 보기를 사용하여 다른 워크시트를 만들 수 있습니다. Excel에서 분석에서는 데이터 세트에 대한 권한이 있는 사용자에게 모든 세부 수준 데이터가 노출됩니다. 이 통합 문서를 저장할 수 있지만, 다시 Power BI로 게시 또는 가져오거나 조직의 다른 사용자와 공유할 수는 없습니다. 자세한 내용 및 기타 사용 사례는 [Excel에서 분석](https://docs.microsoft.com/power-bi/service-analyze-in-excel#analyze-away)을 참조하세요.

## <a name="clean-up-resources"></a>리소스 정리

Power BI 서비스 및 데이터 세트 페이지와의 상호 작용은 ODC 파일을 다운로드하고 워크플로를 클릭하는 것으로 제한되어야 합니다. 이러한 단계를 수행하는 데 문제가 있는 경우에는 해당 단계에서 **아니요**를 표시하고 연결된 양식에 피드백을 제공합니다. 이 양식에는 문제에 대한 자세한 정보로 연결되는 링크가 포함되어 있습니다. 데이터 세트 페이지를 다시 방문하여 프로세스를 다시 시도하거나 다른 데이터 세트를 선택합니다.

## <a name="next-steps"></a>다음 단계

다음 문서에도 관심이 있을 수 있습니다.

* [Power BI Desktop에서 교차 보고서 드릴스루 사용](https://docs.microsoft.com/power-bi/desktop-cross-report-drill-through)

* [Power BI Desktop에서 슬라이서 사용](https://docs.microsoft.com/power-bi/visuals/power-bi-visualization-slicers)
