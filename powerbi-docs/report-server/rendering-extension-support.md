---
title: ISO 14289-1을 준수하는 PDF 렌더링 확장 프로그램 - Power BI Report Server 및 SSRS
description: 이 문서에서는 Power BI Report Server 및 SQL Server Reporting Services PDF 렌더링 확장 프로그램의 ISO 14289-1(PDF/UA) 사양 준수에 대해 설명합니다.
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 11/04/2019
ms.author: maggies
ms.openlocfilehash: bfefcef18b8cd92a5c3b15c2dcbd4653a6c7c9cd
ms.sourcegitcommit: 0cc594ebb78a6d0e88784673ed09f8aefd10c7a7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76819517"
---
# <a name="pdf-rendering-extension-conformance-to-iso-14289-1---power-bi-report-server--ssrs"></a>ISO 14289-1을 준수하는 PDF 렌더링 확장 프로그램 - Power BI Report Server 및 SSRS

적용 대상: Power BI Report Server 및 SQL Reporting Services(SSRS)

이 문서에서는 Power BI Report Server 및 SQL Server Reporting Services PDF 렌더링 확장 프로그램의 [ISO 14289-1(PDF/UA)](https://www.pdfa.org/publication/pdfua-in-a-nutshell/) 사양 준수에 대해 설명합니다.

> [!NOTE]
> 이 백서는 브라우저에서 **인쇄**를 선택한 다음, **PDF로 저장**을 선택하여 저장하거나 인쇄할 수 있습니다.

## <a name="1--scope"></a>1.  범위

해당 사항 없음

## <a name="2--normative-references"></a>2.  표준 참조

해당 사항 없음

## <a name="3--terms-and-definitions"></a>3.  용어 및 정의

해당 사항 없음

## <a name="4--notation"></a>4.  표기법

해당 사항 없음

## <a name="5-version-identification"></a>5. 버전 확인

PDF 렌더링 확장 프로그램은 이 문서에서 설명한 대로 PDF/UA를 지원합니다. 아래에서 설명하는 일부 경우에는 사용자가 PDF/UA를 완전히 준수하는 PDF인지 확인하는 단계를 수행해야 합니다.  사용자가 이 프로세스의 마지막 단계로 적절한 PDF/UA 버전 및 적합성 식별자를 추가하여 PDF에서 PDF/UA를 완전히 준수하도록 하는 데 필요한 작업이 수행되었음을 나타내는 것이 좋습니다.

이 문서에 나와 있는 모든 항목은 디바이스 정보 설정인 AccessiblePdf가 `true`로 설정된 PDF 문서 렌더링을 기반으로 합니다. 경우에 따라 RDL(Report Definition Language)의 제한으로 인해 규정 준수 제한이 적용됩니다.

## <a name="6--conformance-requirements"></a>6.  적합성 요구 사항

|     기준     |     지원되는 기능     |     설명      |
|----|--------|--------|
|    6.1 일반    |                 지원됨    |    PDF 렌더링 확장 프로그램은 PDF 버전 1.7을 만듭니다.    |
|    6.2 파일 적합성    |                 지원됨(예외적인 경우는 제외)    |    섹션 7 – 파일 형식 요구 사항의 설명을 참조하세요.    |
|    6.3 판독기 적합성    |     해당 없음     |         |
|    6.4 보조 기술 적합성    |     해당 없음     |         |

## <a name="7--file-format-requirements"></a>7.  파일 형식 요구 사항

|     기준     |     지원되는 기능     |     설명      |
|-----|-------|------------------------|
|    7.1 일반    |                 지원됨(예외적인 경우는 제외)    |    모든 실제 콘텐츠에는 ISO 32000-1:2008, 14.8에서 정의한 대로 태그를 지정해야 합니다. 아티팩트(ISO 32000-1:2008, 14.8.2.2.2)의 구조 트리에는 태그를 지정할 수 없습니다. <li> PDF 렌더링 확장 프로그램은 개별 항목을 아티팩트로 명시적으로 표시할 수 있는 유연성을 제공하지 않으므로 이를 대신하여 ISO 32000-1:2008, 14.8.2.2.2의 기준에 매핑된 모든 항목을 아티팩트로 만듭니다.<br>콘텐츠는 논리적 읽기 순서에 따라 의미 있는 적절한 태그로 구조 트리에 표시해야 합니다. <br> **참고** 4 WCAG 2.0 지침 1.4에서는 내게 필요한 옵션에 대한 대비, 색 및 기타 서식 지정과 관련된 문제에 대해 설명합니다. <br><li> 사용자는 자신의 문서에 이러한 문제가 없도록 해야 합니다. <br>ISO 32000-1:2008, 14.8.4에 정의된 표준 태그는 다시 매핑할 수 없습니다. <li> PDF 렌더링 확장 프로그램은 표준 태그를 다시 매핑하지 않습니다. 문서는 Document 루트 요소로 시작합니다. <br>이 국제 표준의 준수를 주장하는 파일에는 false의 Suspects 값이 있어야 합니다(ISO 32000-1:2008, 표 321). <li> PDF 렌더링 확장 프로그램에는 Suspects 항목이 없습니다. 이 속성은 선택 사항입니다.    |
|    7.2 텍스트    |                 지원됨(예외적인 경우는 제외)    |    콘텐츠는 논리적 읽기 순서에 따라 태그를 지정해야 합니다. 문서 콘텐츠의 각 논리적 요소에 가장 의미 있는 적절한 태그를 사용해야 합니다. <br><li> PDF 렌더링 확장 프로그램은 가능한 한 논리적 읽기 순서에 따라 태그를 콘텐츠에 지정합니다.<br>문자 코드는 ISO 32000-1:2008, 14.8.2.4.2에서 설명한 대로 유니코드에 매핑해야 합니다. 유니코드 사양에 포함되지 않은 문자는 유니코드 전용 영역을 사용하거나 다른 문자 인코딩을 선언할 수 있습니다. <br>자연어는 ISO 32000-1:2008, 14.9.2 및/또는 ISO 32000-1:2008, 7.9.2에서 설명한 대로 선언해야 합니다. 자연어의 변경 내용이 선언됩니다. 텍스트 문자열(예: 내부 대체 설명) 내의 자연어 변경은 ISO 32000-1:2008, 14.9.2.2에 설명된 언어 식별자를 사용하여 선언해야 합니다. <br><li> PDF 렌더링 확장 프로그램은 문서 수준에서만 자연어를 선언합니다.    |
|    7.3 그래픽    |                 지원됨(예외적인 경우는 제외)    |    텍스트 개체 이외의 그래픽 개체에는 ISO 32000-1:2008, 14.8.4.5, 표 340에서 설명한 대로 Figure 태그를 지정해야 합니다. 다음 예외 중 하나에 해당하는 경우 그래픽에는 태그를 아티팩트로 지정해야 합니다. <br><li> 그래픽이 의미 있는 콘텐츠를 나타내지 않습니다. 또는 <li>  그래픽은 링크 주석에 대한 배경으로 표시됩니다. 이 경우 링크의 대체 텍스트는 그래픽과 링크를 모두 설명해야 합니다. <li> PDF 렌더링 확장 프로그램은 Figure 태그를 그래픽 개체에 지정합니다. <br>그림에 첨부되는 캡션에는 Caption 태그를 지정해야 합니다. <li> PDF 렌더링 확장 프로그램은 현재 Caption 태그가 있는 그림의 캡션에 태그를 지정하지 않습니다. <br>Figure 태그는 ISO 32000-1:2008, 14.7.2, 표 323에서 설명한 대로 Figure 태그로 표시된 콘텐츠를 나타내는 대체 표현 또는 대체 텍스트를 포함해야 합니다. <br>**참고** 1 WCAG 2.0, 지침 1.1도 참조하세요. <br>그래픽에 표시된 텍스트가 사람이 읽을 수 있는 자연어 텍스트가 아닌 경우 그래픽의 특성 또는 용도를 설명하는 대체 텍스트를 제공해야 합니다. <br>**참고** 2 언어에서 사용하는 형식 샘플 또는 쓰기 시스템의 샘플인 텍스트는 자연어 형식이 아닌 텍스트의 예입니다.   PDF 렌더링 확장 프로그램은 그림에서 대체 텍스트를 지원하지만, 이 대체 텍스트는 사용자가 추가해야 합니다. <br>BBox 특성에 대한 추가 참고 사항: <br><li> PDF 렌더링 확장 프로그램은 현재 BBox 특성을 작성하지 않습니다. <li> 이를 해결하려면 수동으로 새 Figure 또는 Artifact 태그를 그림에 다시 지정합니다.    |
|    7.4 제목    |                 해당 없음    |    RDL은 어떤 방식으로든 제목 표시를 지원하지 않습니다. 사용자가 태그를 적절하게 지정해야 합니다.    |
|    7.5 표    |                 지원됨(예외적인 경우는 제외)    |    표는 머리글을 포함해야 합니다. 표 머리글은 ISO 32000-1:2008, 표 337 및 표 349에 따라 태그를 지정해야 합니다. <br>**참고** 1 표는 열 머리글, 행 머리글 또는 둘 다를 포함할 수 있습니다. <br>**참고** 2 보조 기술을 사용하는 경우 표 구조에 대한 정보를 최대한 많이 제공해야 합니다. 머리글은 구조 정보를 제공하는 데 중요한 역할을 합니다. <br><li> 사용자가 머리글을 표에 포함시켜야 합니다. RDL 및 PDF 렌더링 확장 프로그램은 행 머리글을 지원합니다. <br>  TH 형식의 구조 요소에는 Scope 특성이 있어야 합니다.   <li> PDF 렌더링 확장 프로그램에서 열 및 행 멤버의 TH 요소에는 Scope 특성이 포함되지만 Corner 셀에는 포함되지 않습니다.<br>표 태그 지정 구조는 논리적 행 및/또는 열 관계 내에 표시되는 콘텐츠에 태그를 지정하는 데만 사용해야 합니다.   <li> 이는 사용자가 RDL에서 표를 사용하도록 선택하는 방식에 따라 달라집니다.    |
|    7.6 목록    |                 해당 없음    |    RDL은 목록 표시를 지원하지 않습니다. RDL에서 목록은 구조적으로 단일 표 셀이 있는 표입니다. <br>사용자가 태그를 적절하게 다시 지정해야 합니다.    |
|    7.7 수학 식    |                 지원됨(예외적인 경우는 제외)    |    모든 수학 식은 ISO 32000-1:2008, 14.8.4.5에서 자세히 설명한 대로 Formula 태그 내에 포함되고 Alt 특성을 포함해야 합니다. <br><li> PDF 렌더링 확장 프로그램은 현재 수학 식을 Formula 태그 내에 포함시키지 않습니다. <br>문자를 유니코드에 매핑하는 것과 관련된 요구 사항은 ISO 32000-1:2008, 9.10.2 및 14.8.2.4에 명시된 수학 식에 적용해야 합니다. <br><li> 이는 PDF 렌더링 확장 프로그램에서 지원합니다.    |
|    7.8 페이지 머리글 및 바닥글    |                 지원됨    |    실행되는 머리글 및 바닥글은 Pagination(페이지 매김) 아티팩트로 식별하고, ISO 32000-1:2008, 14.8.2.2.2, 표 330에 따라 Header 또는 Footer 하위 형식으로 분류해야 합니다. <br><li> Header 또는 Footer는 아티팩트로 처리하고 태그가 지정됩니다.    |
|    7.9 메모 및 참조    |                 해당 없음    |    PDF 렌더링 확장 프로그램은 메모 및 참조 표시를 지원하지 않습니다. <br>사용자가 태그를 적절하게 지정해야 합니다.    |
|    7.10 선택적 콘텐츠    |                 해당 없음    |         |
|    7.11 포함 파일    |                 해당 없음    |         |
|    7.12 아티클 스레드    |                 해당 없음    |         |
|    7.13 디지털 서명    |                 해당 없음    |         |
|    7.14 비대화형 양식    |                 해당 없음    |         |
|    7.15 XFA    |                 해당 없음    |         |
|    7.16 보안    |                 해당 없음    |         |
|    7.17 탐색    |                 지원됨    |    문서는 탐색 대상의 읽기 순서 및 수준(ISO 32000-1:2008, 12.3.3)과 일치하는 문서 개요를 포함해야 합니다. <br><li> RDL은 보고서 항목에 대한 책갈피를 지원하지만, 사용자가 이 옵션을 선택해야 합니다. 그러면 PDF 렌더링 확장 프로그램에서 이러한 책갈피를 문서 개요로 렌더링합니다. <br>있는 경우 PageLabels 번호 트리(ISO 32000-1:2008, 7.7.2, 표 28)의 항목은 의미상 적절해야 합니다. <br><li> PDF 렌더링 확장 프로그램에는 PageLabels 번호 트리가 포함되어 있지 않습니다.    |
|    7.18 주석    |                 해당 없음    |    RDL은 주석을 지원하지 않습니다.    |
|    7.21 글꼴    |                 지원됨    |         |
|    7.21.1 일반    |                 지원됨    |         |
|    7.21.2 글꼴 유형    |                 지원됨    |         |
|    7.21.3 합성 글꼴    |                 지원됨    |         |
|    7.21.3.1 일반    |                 지원됨    |         |
|    7.21 3.2 CIDFonts    |                 지원됨    |         |
|    7.21.3.3 CMaps    |                 지원됨    |         |
|    7.21.4 포함    |                 지원됨    |         |
|    7.21.4.1 일반    |                 지원됨    |         |
|    7.21.4.2 하위 세트 포함    |                 지원됨    |         |
|    7.21.5 글꼴 메트릭    |                 지원됨    |         |
|    7.21.6 문자 인코딩    |                 지원됨    |         |
|    7.21.7 유니코드 문자 맵    |                 지원됨    |         |
|    7.21.8 .notdef 문자 모양 사용    |                 지원됨    |         |

## <a name="8--conforming-reader-requirements"></a>8.  판독기 요구 사항 준수

해당 사항 없음

## <a name="9--at-requirements"></a>9.  AT 요구 사항

해당 사항 없음

## <a name="disclaimer"></a>Disclaimer

© 2017 Microsoft Corporation. All rights reserved. The names of actual companies and products mentioned herein may be the trademarks of their respective owners. The information contained in this document represents the current view of Microsoft Corporation on the issues discussed as of the date of publication. Microsoft cannot guarantee the accuracy of any information presented after the date of publication. Microsoft regularly updates its websites with new information about the accessibility of products as that information becomes available.

Customization of the product voids this conformance statement from Microsoft. Please consult with Assistive Technology (AT) vendors for compatibility specifications of specific AT products.

This document is for informational purposes only. MICROSOFT MAKES NO WARRANTIES, EXPRESS OR IMPLIED, IN THIS DOCUMENT.


## <a name="next-steps"></a>다음 단계
[관리자 개요](admin-handbook-overview.md)  

궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](https://community.powerbi.com/)

