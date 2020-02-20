---
title: Power BI 보고서 작성기
description: Power BI 보고서 작성기는 페이지를 매긴 보고서를 작성하기 위한 도구입니다.
ms.date: 11/27/2019
ms.service: powerbi
ms.subservice: report-builder
featuredvideoid: 78TZeiEhveY
ms.topic: conceptual
ms.assetid: 55bf4f9c-d037-412f-ae57-3fc39ce32fa5
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 5ef6068135e8adcbfd242ca4a6491396101d214e
ms.sourcegitcommit: df8bcc65f0df69bf1fc1d47eb06575742eac1622
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2020
ms.locfileid: "75953908"
---
# <a name="power-bi-report-builder"></a>Power BI 보고서 작성기

 Power BI 보고서 작성기는 페이지를 매긴 보고서를 작성하기 위한 도구입니다.  페이지를 매긴 보고서를 디자인할 때 검색할 데이터, 가져올 위치 및 표시 방법을 지정하는 보고서 정의를 만듭니다. 보고서를 실행하면 보고서 처리기는 지정된 보고서 정의를 가져와 데이터를 검색한 다음 보고서 레이아웃에 따라 정렬하여 보고서를 생성합니다. 보고서 작성기에서 보고서를 미리 봅니다. 그런 다음, Power BI 서비스에 보고서를 게시합니다.

[실습 랩: Microsoft Power BI 페이지를 매긴 보고서 만들기](https://www.microsoft.com/handsonlabs/selfpacedlabs/details/SQ00208)를 사용해보세요.

비디오에서 학습하는 것을 선호하십니까? YouTube에서 Power BI 수석 프로그램 관리자 Chris Finlan이 진행하는 Power BI 페이지를 매긴 보고서 비디오 시리즈를 확인하세요.

<iframe width="560" height="315" src="https://www.youtube.com/embed/78TZeiEhveY?list=PLx7LcKtN_gq-JVzM6L8xNNxX7kts-KflJ" frameborder="0" allowfullscreen></iframe>

다음의 페이지를 매긴 보고서에는 행과 열 그룹, 스파크라인, 표시기 및 모서리 셀의 요약 원형 차트가 포함된 행렬을 특징으로 하며, 색과 원 크기로 표시된 두 개의 지리적 데이터 세트가 포함된 맵이 있습니다.  

![Power BI 서비스의 페이지를 매긴 보고서](media/report-builder-power-bi/report-builder-get-started-paginated-report.png)

##  <a name="JumpStartReptCreation"></a> 빠른 보고서 만들기  
 
-   **테이블, 행렬 또는 차트 마법사를 사용하여 시작**합니다. 데이터 원본 연결을 만들고, 필드를 끌어서 놓아 데이터 세트 쿼리를 만들고, 레이아웃 및 스타일을 선택하고, 보고서를 사용자 지정합니다.  
  
-   **지도 마법사를 시작**하여 지리적 또는 기하학적 배경에 집계된 데이터를 표시하는 보고서를 만듭니다. 지도 데이터는 Transact-SQL 쿼리 또는 ESRI(Environmental Systems Research Institute, Inc.) 셰이프 파일의 공간 데이터일 수 있습니다. Microsoft Bing 지도 타일 배경을 추가할 수도 있습니다.  

##  <a name="DesignRept"></a> 보고서 디자인  
  
-   **테이블, 행렬, 차트 및 자유 형식 레이아웃을 사용하여 페이지를 매긴 보고서를 만듭니다.** 열 기반 데이터의 테이블 보고서, 요약된 데이터에 대한 행렬 보고서(예: 크로스탭 또는 피벗 테이블 보고서), 그래픽 데이터에 대한 차트 보고서 및 그 밖의 자유 형식 보고서를 만듭니다. 보고서에는 동적 웹 기반 애플리케이션의 목록, 그래픽 및 컨트롤과 함께 다른 보고서와 차트가 포함될 수 있습니다.  
  
-   **다양한 데이터 원본에서 보고합니다.** SQL Server 및 Analysis Services, Oracle, Power BI 데이터 세트 및 기타 데이터베이스의 관계형 및 다차원 데이터를 사용하는 보고서를 만들 수 있습니다.  
  
-   **기존 보고서를 수정합니다.** 보고서 작성기를 사용하면 SSDT(SQL Server Data Tools) 보고서 디자이너에서 생성된 보고서를 사용자 지정하고 업데이트할 수 있습니다.  
  
-   **데이터를 수정합니다**. 데이터를 필터링, 그룹화 및 정렬하거나 수식 또는 식을 추가합니다.  

-   **차트, 계기, 스파크라인 및 표시기를 추가합니다**. 데이터를 시각적 개체 형식으로 요약하고 집계된 대량의 정보를 한 눈에 볼 수 있습니다.  
  
-   문서 맵, 표시/숨기기 단추, 하위 보고서 및 드릴스루 보고서에 대한 드릴스루 링크와 같은 **대화형 기능을 추가합니다**. 매개 변수와 필터로 데이터를 필터링하여 사용자 지정 뷰를 만들 수 있습니다.  
  
-   **이미지 포함 또는 참조** 및 외부 콘텐츠를 포함한 리소스.  
  
##  <a name="ManageRpt"></a> 보고서 관리  
  
-   컴퓨터 또는 보고서에 **보고서의 정의를 저장**합니다. 여기서 관리하고 다른 사용자와 공유할 수 있습니다.  
  
-   보고서를 열거나 보고서를 연 후 **표시 형식을 선택합니다**. 웹 지향, 페이지 지향 및 데스크톱 애플리케이션 형식을 선택할 수 있습니다. 형식에는 MHTML, PDF, XML, CSV, Word 및 Excel이 포함됩니다.  
  
-   **구독을 설정합니다.** 보고서를 Power BI 서비스에 게시한 후 보고서를 특정 시간에 실행하고 이메일 구독으로 보내도록 구성할 수 있습니다.  

## <a name="next-steps"></a>다음 단계

- [Power BI Premium에서 페이지를 매긴 보고서란?](paginated-reports-report-builder-power-bi.md)
- [실습 랩: Microsoft Power BI 페이지를 매긴 보고서 만들기](https://www.microsoft.com/handsonlabs/selfpacedlabs/details/SQ00208)를 사용해보세요.
- YouTube에서 Power BI 수석 프로그램 관리자 Chris Finlan이 진행하는 [Power BI 페이지를 매긴 보고서 비디오 시리즈](https://www.youtube.com/watch?v=78TZeiEhveY&list=PLx7LcKtN_gq-JVzM6L8xNNxX7kts-KflJ) 시청