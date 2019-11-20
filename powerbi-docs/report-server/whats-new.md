---
title: Power BI Report Server의 새로운 기능
description: Power BI Report Server의 새로운 기능에 대해 알아봅니다. 주요 기능 영역을 설명하고 새 항목이 출시될 때 업데이트됩니다.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 09/26/2019
ms.openlocfilehash: 526a971817c50599bf77ae085f3d5ff07294b25b
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2019
ms.locfileid: "73858755"
---
# <a name="whats-new-in-power-bi-report-server"></a>Power BI Report Server의 새로운 기능

Power BI Report Server와 Power BI Report Server에 최적화된 Power BI Desktop의 새로운 기능을 알아봅니다. 이 문서에서는 주요 기능 영역을 설명합니다. 이 문서는 신규 릴리스가 공개될 때마다 업데이트됩니다.

관련 Power BI “새로운 기능” 정보는 다음을 참조하세요.

* [Power BI 서비스의 새로운 기능](../service-whats-new.md)
* [Power BI Desktop의 새로운 기능](../desktop-latest-update.md)
* [Power BI용 모바일 앱의 새로운 기능](../consumer/mobile/mobile-whats-new-in-the-mobile-apps.md)

## <a name="september-2019"></a>2019년 9월

모든 새로운 기능에 대한 자세한 내용은 [Power BI Report Server 2019년 9월](https://powerbi.microsoft.com/blog/power-bi-report-server-september-2019-feature-summary/) 블로그 게시물을 참조하세요.

Power BI Report Server 2019년 9월 업데이트에는 다양한 Power BI 보고서 기능이 포함되어 있습니다. 다음은 몇 가지 주요 기능입니다.

- **슬라이서를 위한 시각적 수준 필터** 슬라이서에 시각적 수준 필터를 추가할 수 있습니다. 슬라이서를 위한 시각적 수준 필터는 여타 시각적 수준 필터와 동일하게 작동하되 다른 시각적 개체가 아닌 슬라이서 자체만 필터링합니다. 이 필터는 공백을 필터링할 때나 측정 필터를 사용할 때 유용합니다.
- **테이블과 행렬을 위한 아이콘 집합** KPI 아이콘을 사용하여 Excel의 아이콘 집합과 마찬가지로 테이블과 행렬에서 다양한 아이콘 집합을 표시하는 규칙을 설정할 수 있습니다.
- **시각적 개체 그룹화** 시각적 개체, 도형, 텍스트 상자, 이미지 및 단추를 PowerPoint에서와 마찬가지로 보고서 페이지에서 하나로 그룹화할 수 있습니다. 개체를 하나로 그룹화한 후에는 한꺼번에 이동하고 크기를 조정할 수 있습니다. 그룹화를 사용하면 각 페이지에 여러 개의 개체가 있는 보고서를 훨씬 더 쉽게 작업할 수 있습니다.
- **새로운 기본 테마** 새로운 테마의 JSON 옵션에 어울리도록 보고서에서 사용 가능한 테마가 업데이트되고 새로운 보고서의 기본 테마가 변경되었습니다. 새로운 기본 테마는 Microsoft의 디자인 원칙에 더욱 잘 부합하며 시각적 개체를 위한 디자인 모범 사례를 따릅니다. 
- **업데이트된 창 디자인** 인터페이스의 많은 부분이 새로 단장되었습니다. 모든 창, 바닥글, 보기 전환기에 더 밝은색이 적용되었고, 간격이 업데이트되었으며, 새로운 아이콘이 도입되었습니다. 이번 새로운 디자인은 전체 인터페이스 새 단장을 위한 첫걸음입니다.

다음은 전체 기능 목록입니다. 

### <a name="reporting"></a>보고

- 업데이트된 창 디자인
- 슬라이서를 위한 시각적 수준 필터
- 성능 분석기 창의 정렬
- 시각적 개체 머리글 도구 설명
- 테이블과 행렬 총 레이블 사용자 지정
- 계층 슬라이서를 위한 동기화 슬라이서 지원
- 시각적 개체 간에 일관된 글꼴 크기
- 테이블과 행렬의 아이콘 집합
- 규칙을 통한 조건부 서식의 백분율 지원
- 이제 새 필터 창이 일반 공급됨
- 분산형 차트에서 재생 축을 사용할 때 데이터 색 지원
- 상대 날짜와 드롭다운 슬라이서를 사용할 때 성능 개선
- 시각적 개체 그룹화
- 테마의 색 및 텍스트 클래스
- 새로운 기본 테마

### <a name="analytics"></a>분석

- 사용자 지정 형식 문자열
- 서식 지정 옵션을 위한 조건부 서식 업데이트

    - 시각적 개체 배경 및 제목 색
    - 카드 색
    - 계기 채우기 및 색
    - 대체 텍스트
    - 테두리 색

- 조건부 서식 지정 경고
- 드릴스루 검색 기능 개선
- 새로운 DAX 식: REMOVEFILTERS 및 CONVERT
- 새로운 DAX 비교 연산자: ==

### <a name="data-preparation"></a>데이터 준비

- M Intellisense의 향상된 기능
- 새로운 변환: 위치를 기준으로 열 분할
- 데이터 프로파일링에서 클립보드로 복사


## <a name="may-2019-power-bi-desktop-for-power-bi-report-server"></a>2019년 5월 Power BI Report Server를 위한 Power BI Desktop

모든 새로운 기능에 대한 자세한 내용은 [Power BI Report Server 2019년 5월](https://powerbi.microsoft.com/blog/power-bi-report-server-update-may-2019/) 블로그 게시물을 참조하세요.

다음은 이번 릴리스의 몇 가지 주요 기능입니다.

### <a name="performance-analyzer"></a>성능 분석기 

보고서가 예상보다 느리게 실행된다면 Power BI Desktop에서 성능 분석기를 사용해 보세요. 성능 분석기를 시작하면 사용자가 보고서에서 수행하는 모든 동작에 대한 정보가 담긴 로그 파일이 생성됩니다. [성능 분석기](../desktop-performance-analyzer.md)에 대해 자세히 알아보세요.

### <a name="new-modeling-view"></a>새로운 모델링 보기

Power BI Desktop의 새로운 모델링 보기에서는 테이블이 여러 개 포함된 복잡한 데이터 세트를 보고 작업할 수 있습니다. 여러 다이어그램 레이아웃과 열, 측정값, 테이블의 대량 편집 등의 기능이 추가되었습니다. [모델링 보기](../desktop-modeling-view.md)에 대해 자세히 알아보세요.

### <a name="accessible-visual-interaction"></a>액세스 가능 시각적 개체 조작

이제 키보드 탐색을 사용하여 여러 기본 제공 시각적 개체에서 데이터 요소에 액세스할 수 있습니다. [Power BI 보고서의 액세스 가능 기능](../desktop-accessibility.md)에 대해 자세히 알아보세요.

### <a name="conditional-formatting-titles-and-web-url-actions"></a>조건부 서식 제목 및 웹 URL 동작

Power BI 보고서는 대화형입니다. 보고서의 타일이 보고서의 현재 상태를 반영하여 동적으로 변경될 것을 기대할 수 있습니다. 동일한 표현식 바인딩 서식 지정을 사용하여 단추, 도형 및 이미지의 URL을 동적으로 만들 수 있습니다. [표현식 기반 제목](../desktop-conditional-format-visual-titles.md)에 대해 자세히 알아보세요.

### <a name="cross-highlight-by-axis-labels"></a>축 레이블별 교차 강조 표시

시각적 개체에서 데이터 요소를 선택하는 것과 마찬가지로 시각적 개체에서 축 범주 레이블을 선택하여 페이지에 있는 다른 요소를 교차 강조 표시합니다. [교차 강조 표시](../power-bi-reports-filters-and-highlighting.md#ad-hoc-highlighting)에 대해 자세히 알아보세요.

### <a name="all-the-new-features"></a>모든 새로운 기능

다음은 모든 새로운 기능 목록입니다.

### <a name="reporting"></a>보고

- 꺾은선형 차트의 단일 점에서 교차 강조 표시 
- 제목에서 자동 줄 바꿈 
- 기본 시각적 개체 조작을 교차 필터로 업데이트
- 시각적 개체 테두리의 둥근 모서리 
- 단일 선택 슬라이서  
- Bing 지도를 위한 열 지도 지원  
- 축 레이블별 교차 강조 표시  
- 기본 도구 설명 서식 지정  
- 단추, 도형 및 이미지를 위한 정적 웹 URL 지원  
- 페이지 맞춤 옵션   
- 선택 창의 향상된 기능  
- 액세스 가능 시각적 개체 조작  
- 시각적 개체 제목을 위한 조건부 서식 지정  
- 단추, 도형 및 이미지의 웹 URL 동작을 위한 조건부 서식 지정
- 성능 분석기 창
- 테이블 및 행렬 키보드 탐색
- 선 데이터 레이블 위치 컨트롤
- KPI 시각적 개체 표시기 텍스트 크기 컨트롤

### <a name="analytics"></a>분석

- 계층 구조로 날짜 표시가 이제 일반 공급됨  

### <a name="modeling"></a>모델링

- 새로운 모델링 보기가 이제 일반 공급됨
- 새로운 DAX 함수
- ALLSELECTED DAX 함수 업데이트
- 새 보고서에서 자동 날짜 테이블 사용 안 함

## <a name="may-2019-power-bi-report-server"></a>2019년 5월 Power BI Report Server

### <a name="support-for-trusted-visuals"></a>신뢰할 수 있는 시각적 개체에 대한 지원

Power BI Report Server에 신뢰할 수 있는 시각적 개체에 대한 지원이 추가되었습니다. 현재 Mapbox 및 PowerOn 시각적 개체가 지원됩니다. ESRI, Visio 및 PowerApps는 이 릴리스에서 지원되지 않습니다.)

### <a name="improved-security-features"></a>향상된 보안 기능

**RestrictedResourceMimeTypeForUpload**. 관리자가 금지된 MIME 형식(예: text/html)의 쉼표로 구분된 목록을 지정하는 데 사용할 수 있습니다.

## <a name="january-2019"></a>2019년 1월

Power BI 보고서에서 다음 기능 지원:

[**행 수준 보안**](row-level-security-report-server.md) Power BI Report Server를 사용하는 RLS(행 수준 보안)를 설정하면 지정된 사용자의 데이터 액세스를 제한할 수 있습니다. 필터는 행 수준에서 데이터 액세스를 제한하고 역할 내에서 필터를 정의할 수 있습니다.

[**행렬 행 머리글의 확장 및 축소**](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2018-feature-summary/#expandCollapse) 가장 많이 요청된 시각적 개체 기능 중 하나인 개별 행 머리글을 확장 및 축소하는 기능을 추가했습니다.

[ **.pbix 파일 간에 복사 및 붙여넣기**](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2018-feature-summary/#copyPaste) 시각적 개체의 컨텍스트 메뉴에서 또는 표준 Ctrl+C 바로 가기 키를 사용하여 .pbix 파일 간에 시각적 개체를 복사하고 Ctrl+V를 사용하여 다른 보고서에 붙여넣을 수 있습니다.

[**스마트 맞춤 가이드**](https://powerbi.microsoft.com/blog/power-bi-desktop-december-2018-feature-summary/#smartGuides) PowerPoint에서 볼 수 있는 것처럼 보고서 페이지에서 개체를 이동할 때 페이지의 모든 항목을 정렬하는 데 도움이 되는 스마트 맞춤 가이드가 표시됩니다. 페이지의 있는 항목을 드래그하거나 크기를 조정할 때마다 스마트 가이드를 볼 수 있습니다. 다른 개체 근처에서 개체를 이동하면 다른 개체와 정렬된 위치로 스냅됩니다.

**내게 필요한 옵션 기능** 목록에 내게 필요한 옵션 기능이 너무 많습니다(예: [필드 목록 창 내게 필요한 옵션 지원](https://powerbi.microsoft.com/blog/power-bi-desktop-december-2018-feature-summary/#fieldList)). 필드 목록 창에 완전히 액세스할 수 있습니다. 키보드 및 화면 reader만 사용하여 창 주위를 탐색하고 컨텍스트 메뉴를 사용하여 보고서 페이지에 필드를 추가할 수 있습니다.

#### <a name="custom-visuals"></a>사용자 지정 시각적 개체

- 이 릴리스에서 제공된 API 버전은 2.3입니다.

### <a name="administrator-settings"></a>관리자 설정

관리자는 서버 팜에 대한 SSMS 고급 속성에서 다음 속성을 설정할 수 있습니다.

**AllowedResourceExtensionsForUpload** 보고서 서버에 업로드할 수 있는 리소스 확장을 설정합니다. &ast;.rdl 및 &ast;.pbix와 같은 기본 제공 파일 형식에 대한 확장을 포함할 필요가 없습니다. 기본값은 “&ast;, &ast;.xml, &ast;.xsd, &ast;.xsl, &ast;.png, &ast;.gif, &ast;.jpg, &ast;.tif, &ast;.jpeg, &ast;.tiff, &ast;.bmp, &ast;.pdf, &ast;.svg, &ast;.rtf, &ast;.txt, &ast;.doc, &ast;.docx, &ast;.pps, &ast;.ppt, &ast;.pptx”입니다. 

**SupportedHyperlinkSchemes** 렌더링할 수 있는 하이퍼링크 작업에서 정의할 수 있도록 허용된 URI 구성표의 쉼표로 구분된 목록을 설정하거나 모든 하이퍼링크 구성표를 활성화하는 데 “&ast;”를 설정합니다. 예를 들어 “http,https”를 설정하면 “https://www contoso.com”에 대한 하이퍼링크가 허용되지만 “mailto:bill@contoso.com” 또는 “javascript:window.open(‘www.contoso.com’, ‘_blank’)”에 대한 하이퍼링크를 제거합니다. 기본값은 “&ast;”입니다.

## <a name="august-2018"></a>2018년 8월

2018년 8월부터는 Power BI Report Server에 최적화된 Power BI Desktop의 버전에 많은 새로운 기능이 추가됩니다. 다음과 같은 영역으로 나눌 수 있습니다.

- [보고](#reporting)
- [분석](#analytics)
- [모델링](#modeling)

### <a name="highlights-of-the-august-2018-release"></a>2018년 8월 릴리스의 주요 내용

새로운 기능의 전체 목록에서 특별히 이러한 기능에 주목합니다. 자세한 내용은 [블로그 게시물](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/)을 참조하세요.

#### <a name="report-theming"></a>보고서 테마

보고서 테마는 Power BI Report Server의 2018년 8월 릴리스에 추가되었습니다. 이 기능을 사용하면 신속하게 테마 또는 회사 브랜딩에 맞게 전체 보고서의 색을 지정할 수 있습니다. 테마를 가져올 때 모든 차트는 테마 색을 사용하도록 자동으로 업데이트되고, 사용자는 색상표의 테마 색에 액세스할 수 있습니다. **테마 전환** 단추에서 **테마 가져오기** 옵션을 사용하여 테마 파일을 업로드할 수 있습니다.

테마 파일은 시각적 개체에 적용할 기본 서식 지정과 함께 보고서에서 사용하려는 모든 색을 포함하는 JSON 파일입니다.
보고서의 기본 색만 업데이트하는 간단한 샘플 JSON 테마는 다음과 같습니다.

```json
{
"name": "waveform",
"dataColors": [ "#31B6FD", "#4584D3", "#5BD078", "#A5D028", "#F5C040", "#05E0DB", "#3153FD", "#4C45D3", "#5BD0B0", "#54D028", "#D0F540", "#057BE0" ],
"background":"#FFFFFF",
"foreground": "#F2F2F2",
"tableAccent":"#5BD078"
}
```

#### <a name="conditional-formatting-by-a-different-field"></a>다른 필드별 조건부 서식 지정

모델의 다른 필드에 따라 열의 서식을 지정하는 기능은 조건부 서식 지정에 대해 크게 향상된 기능 중 하나입니다.

#### <a name="conditional-formatting-by-values"></a>값별 조건부 서식 지정

다른 새 조건부 서식 지정 형식은 **필드별 서식** 값입니다. 필드별 서식 값을 통해 16진수 코드 또는 이름을 통해 색을 지정하는 측정값 또는 열을 사용할 수 있고, 배경색 또는 글꼴 색을 적용할 수 있습니다.

#### <a name="report-page-tooltips"></a>보고서 페이지 도구 설명

보고서 페이지 도구 설명 기능은 Power BI Report Server의 2018년 8월 업데이트에 포함됩니다. 이 기능을 통해 보고서에서 다른 시각적 개체에 대한 사용자 지정 도구 설명으로 사용할 보고서 페이지를 디자인할 수 있습니다.

#### <a name="log-axis-improvements"></a>로그 축 향상된 기능

카티전 차트에서 축 로그를 크게 개선했습니다. 이제 완전히 양수 또는 완전히 음수인 데이터가 있는 경우 콤보 차트를 비롯한 카티전 차트의 숫자 축에 대해 로그 눈금을 선택할 수 있습니다.

#### <a name="sap-hana-sso-direct-query"></a>SAP HANA SSO 직접 쿼리

Kerberos에서 SAP HANA SSO 직접 쿼리 지원은 Power BI 보고서에 대해 지금 사용할 수 있습니다.

>[!Note]
>Power BI Desktop에서 만든 보고서를 사용하여 SAP HANA를 관계형 데이터 원본으로 처리하는 경우에만 이 시나리오가 지원됩니다.  Power BI Desktop에서 이 작업을 수행하려면 옵션의 DirectQuery 메뉴에서 "SAP HANA를 관계형 원본으로 처리"를 선택하고, 확인을 클릭합니다.

#### <a name="custom-visuals"></a>사용자 지정 시각적 개체

- 이 릴리스에서 제공된 API 버전은 1.13.0입니다.

- 이제 사용자 지정 시각적 개체는 현재 버전(있는 경우)의 서버 API와 호환 가능한 이전 버전으로 대체할 수 있습니다.

### <a name="reporting"></a>보고 

- [보고서 테마](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#theming)
- [작업을 트리거하는 단추](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#buttons)
- [콤보 차트 선 스타일](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#comboLines)
- [시각적 개체에 대한 기본 정렬 개선](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#sort)
- [숫자 슬라이서](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#numericSlicer)
- [고급 슬라이서 동기화](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#slicerSync)
- [로그 축 향상된 기능](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#logAxis)
- [깔때기형 차트에 대한 데이터 레이블 옵션](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#funnelChart)
- [선 스트로크 너비를 0으로 설정](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#lineStroke)
- [보고서에 고대비 지원](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#highContrast)
- [도넛형 반경 제어](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#donutRadius)
- [파이 및 도넛형 세부 레이블 위치 제어](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#detailLabels)
- [콤보 차트에서 각 측정값에 대해 별도로 데이터 레이블 서식 지정](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#comboLabels)
- [유연성과 서식 지정이 추가된 새로운 시각적 개체 헤더](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#visualHeader)
- [배경 화면 서식 지정](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#wallpaper)
- [테이블 및 행렬에 대한 도구 설명](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#tableTooltips)
- [시각적 개체에 대한 도구 설명 해제](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#tooltips)
- [슬라이서 내게 필요한 옵션](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#slicerAccessibility)
- [서식 지정 창 향상된 기능](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#formattingPane)
- [선 및 콤보 차트에 대한 단계별 선 지원](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#steppedLine)
- [정렬 환경 향상된 기능](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#sorting)
- [Power BI Desktop에서 PDF로 내보내기를 통해 보고서 인쇄](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#print)
- [책갈피 그룹 만들기](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#bookmarks)
- [슬라이서 재작성](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#slicer)
- [보고서 페이지 도구 설명](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#reportPageTooltips)

### <a name="analytics"></a>분석

- [새 DAX 함수: COMBINEVALUES()](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#combineValues)
- [드릴스루 측정](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#measureDrillthrough)
- [다른 필드별 조건부 서식 지정](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#conditionalFormattingField)
- [값별 조건부 서식 지정](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#conditionalFormattingValue)

### <a name="modeling"></a>모델링

- [데이터 보기에서 필터링 및 정렬](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#filterAndSort)
- [로캘 서식 지정 향상](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#locale)
- [측정값에 대한 데이터 범주](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#dataCategory)
- [통계 DAX 함수](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#dax)

## <a name="may-2018"></a>2018년 5월

### <a name="configure-power-bi-ios-mobile-apps-for-report-servers-remotely"></a>원격으로 보고서 서버에 대한 Power BI iOS 모바일 앱 구성

IT 관리자인 경우 이제 조직의 MDM 도구를 사용하여 보고서 서버에 대한 Power BI iOS 모바일 앱 액세스 권한을 원격으로 구성할 수 있습니다. 자세한 내용은 [원격으로 보고서 서버에 대한 Power BI iOS 모바일 앱 액세스 권한 구성](configure-powerbi-mobile-apps-remote.md)을 참조하세요.

## <a name="march-2018"></a>2018년 3월

2018년 3월부터 Power BI Report Server에 최적화된 Power BI Desktop의 버전에 많은 새로운 기능이 추가됩니다. 다음과 같은 영역으로 나눌 수 있습니다.

- [시각적 개체](#visuals-updates)
- [보고](#reporting)
- [분석](#analytics)
- [성능](#performance)
- [보고서 서버](#report-server)
- [기타](#other-improvements)

### <a name="highlights-of-the-march-2018-release"></a>2018년 3월 릴리스의 주요 내용

새로운 기능의 전체 목록에서 특별히 이러한 기능에 주목합니다.

#### <a name="rule-based-conditional-formatting-for-table-and-matrixhttpspowerbimicrosoftcomblogpower-bi-desktop-november-2017-feature-summaryconditionalformatting"></a>[테이블 및 행렬에 대한 규칙 기반 조건부 서식 지정](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#conditionalFormatting)

테이블 또는 행렬의 특정 비즈니스 논리에 따라 열의 배경 또는 글꼴 색을 조건부로 지정하는 규칙을 만듭니다.

#### <a name="show-and-hide-pageshttpspowerbimicrosoftcomblogpower-bi-desktop-january-2018-feature-summaryhidepages"></a>[페이지 표시 및 숨기기](https://powerbi.microsoft.com/blog/power-bi-desktop-january-2018-feature-summary/#hidePages)

reader에게 보고서에 대한 액세스 권한을 부여하려고 하지만 일부 페이지가 완료되지 않았습니다. 이제 준비될 때까지 숨길 수 있습니다. 또는 일반 탐색에서 페이지를 숨길 수 있고 책갈피 또는 드릴스루를 통해 페이지로 이동할 수 있습니다.

#### <a name="bookmarkinghttpspowerbimicrosoftcomblogpower-bi-desktop-march-2018-feature-summarybookmarking"></a>[책갈피](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#bookmarking)

책갈피의 경우 책갈피를 만들어서 보고서에서 데이터를 사용하여 이야기를 만듭니다.

- [책갈피의 교차 강조 표시](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#bookmarkCrossHighlighting): 책갈피는 책갈피를 만들 때 보고서 페이지에서 교차 강조 표시한 상태를 유지 관리하고 표시합니다.
- [책갈피의 추가 유연성](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#bookmarkFlexibility): 책갈피는 보고서에서 설정한 속성을 반영하고 선택한 시각적 개체에만 영향을 줍니다.

#### <a name="multi-select-data-points-across-multiple-chartshttpspowerbimicrosoftcomblogpower-bi-desktop-february-2018-feature-summarycrosshighlight"></a>[여러 차트에서 데이터 요소 다중 선택](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#crosshighlight)

여러 차트에서 여러 데이터 요소를 선택하고 교차 필터링을 전체 페이지에 적용했습니다.

#### <a name="sync-slicers-across-multiple-pages-of-your-reporthttpspowerbimicrosoftcomblogpower-bi-desktop-february-2018-feature-summarysyncslicers"></a>[보고서의 여러 페이지에서 슬라이서 동기화](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#syncSlicers)

슬라이서는 보고서에서 하나 또는 둘 이상의 페이지에 적용할 수 있습니다.

#### <a name="quick-measureshttpspowerbimicrosoftcomblogpower-bi-desktop-february-2018-feature-summaryquickmeasures"></a>[빠른 측정](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#quickMeasures) 

기존 측정값 및 테이블의 숫자 열에 따라 새 측정값을 만듭니다.

#### <a name="drilling-down-filters-other-visualshttpspowerbimicrosoftcomblogpower-bi-desktop-december-feature-summarydrillfiltersothervisuals"></a>[기타 시각적 개체에서 필터 드릴다운](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#drillFiltersOtherVisuals)

하나의 시각적 개체의 지정된 범주에서 드릴다운하면 동일한 범주에 따라 페이지에서 모든 시각적 개체를 필터링할 수 있습니다.

### <a name="visuals-updates"></a>시각적 개체 업데이트

- [테이블 및 행력에 대한 셀 맞춤](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#alignment)
- [테이블 및 행렬 열에 대한 단위 및 정밀도 제어 표시](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#displayUnits)
- [가로 막대형 및 세로 막대형 차트에 대한 데이터 레이블 오버플로](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#overflow)
- [카티전 및 맵 시각적 개체에 대한 데이터 레이블 배경색 제어](https://powerbi.microsoft.com/blog/power-bi-desktop-january-2018-feature-summary/#dataLabelBackground)
- [바/열 패딩 제어](https://powerbi.microsoft.com/blog/power-bi-desktop-january-2018-feature-summary/#padding)
- [차트에서 축 레이블에 사용된 영역 증가](https://powerbi.microsoft.com/blog/power-bi-desktop-january-2018-feature-summary/#axisSize)
- [x축 및 y축 그룹화의 분산형 시각적 개체](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#scatterChart)
- [위도 및 경도에 따라 맵에 대한 고밀도 샘플링](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#highDensityMaps)
- [반응형 슬라이서](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#responsive)
- [상대 날짜 슬라이서의 앵커 날짜 추가](https://powerbi.microsoft.com/blog/power-bi-desktop-january-2018-feature-summary/#anchorDate)

### <a name="reporting"></a>보고

- [보고서의 읽기 모드에서 시각적 개체 헤더 끄기](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#visualHeader)
- [느린 데이터 원본에 대한 보고서 옵션](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#slowDataSource)
- [기본 시각적 개체 배치 향상](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#visualPlacement)
- [선택 창을 통한 시각적 개체 순서 제어](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#selectionPane)
- [보고서에서 개체 잠금](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#lock)
- [서식 지정 및 분석 창 검색](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#search)
- [필드 속성 창 및 필드 설명](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#fieldPropertiesPane)

### <a name="analytics"></a>분석

- [UTCNOW() 및 UTCTODAY()](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#utcDAX)
- [사용자 지정 날짜 테이블 표시](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#customDateTable)
- [다른 시각적 개체의 필터 드릴](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#drillFiltersOtherVisuals)
- [여러 행 카드에 대한 다차원 AS 모델의 셀 수준 서식 지정](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#cellLevelFormatting)

### <a name="performance"></a>성능

- [필터링 성능 개선](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#filtering)
- [DirectQuery 성능 개선](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#dqPerf)
- [열기 및 저장 성능 개선](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#savePerf)
- [“데이터가 없는 항목 표시” 개선](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#showItemsWithNoData)

### <a name="report-server"></a>보고서 서버

#### <a name="export-to-accessible-pdf"></a>액세스할 수 있는 PDF로 내보내기

이제 페이지 매긴 보고서(RDL)를 PDF로 내보내면 액세스할 수 있는/태그가 지정된 PDF 파일을 가져올 수 있습니다. 크기가 크지만 화면 판독기 및 기타 보조 기술에서 쉽게 읽고 탐색할 수 있습니다. **AccessiblePDF** 디바이스 정보 설정을 **True**로 설정하여 액세스할 수 있는 PDF를 활성화합니다. [PDF 디바이스 정보 설정](https://docs.microsoft.com/sql/reporting-services/pdf-device-information-settings) 및 [디바이스 정보 설정 변경](https://docs.microsoft.com/sql/reporting-services/customize-rendering-extension-parameters-in-rsreportserver-config#changing-device-information-settings)을 참조하세요.

### <a name="other-improvements"></a>기타 개선 기능

- [예제의 열 추가 개선](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#addColumnFromExamples)
- [컨설팅 서비스 빠른 링크](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#consultingServices)
- [오류 보고 개선](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#errors)
- [이전에 발생한 오류 보기](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#viewErrors)

## <a name="october-2017"></a>2017년 10월

### <a name="power-bi-report-data-sources"></a>Power BI 보고서 데이터 원본

Power BI Report Server에서 Power BI 보고서는 다양한 데이터 원본에 연결할 수 있습니다. 데이터를 가져오고, 데이터 새로 고침을 예약하거나 DirectQuery 또는 SQL Server Analysis Services에 대한 라이브 연결을 사용하여 직접 쿼리할 수 있습니다. 예약된 새로 고침을 지원하는 데이터 원본 및 DirectQuery를 지원하는 데이터 원본 목록은 "Power BI Report Server에서 Power BI 보고서 데이터 원본"을 참조하세요.

### <a name="scheduled-data-refresh-for-imported-data"></a>가져온 데이터에 대한 데이터 새로 고침 예약

Power BI Report Server에서 예약된 데이터 새로 고침을 설정하여 라이브 연결 또는 DirectQuery가 아닌 포함된 모델로 Power BI 보고서에서 데이터를 최신 상태로 유지할 수 있습니다. 포함된 모델을 사용하여 데이터를 가져오므로 원래 데이터 원본에서 연결이 끊어집니다. 데이터를 최신 상태로 유지하도록 업데이트되어야 하며 예약된 새로 고침은 이를 수행하는 방법입니다. "Power BI Report Server에서 Power BI 보고서에 대한 예약된 새로 고침"에 대해 자세히 알아봅니다.

### <a name="editing-power-bi-reports-from-the-server"></a>서버에서 Power BI 보고서 편집

서버에서 Power BI 보고서(.pbix) 파일을 열고 편집할 수 있지만 업로드한 원래 파일을 다시 가져옵니다.  즉, **서버에서 데이터를 새로 고친 경우 파일을 처음 열 때 데이터는 새로 고쳐지지 않습니다**. 변경 내용을 확인하려면 수동으로 로컬에서 새로 고쳐야 합니다.

### <a name="large-file-uploaddownload"></a>큰 파일 업로드/다운로드

최대 2GB 크기의 파일을 업로드할 수 있지만 기본적으로 이 제한은 SSMS(SQL Server Management Studio)의 보고서 서버 설정에서 1GB로 설정되어 있습니다.  이러한 파일은 SharePoint에 대해서와 마찬가지로 데이터베이스에 저장되며 SQL Server 카탈로그에 대한 특별한 구성은 필요하지 않습니다.  

### <a name="accessing-shared-datasets-as-odata-feeds"></a>OData 피드로 공유 데이터 세트에 액세스

OData 피드로 Power BI Desktop에서 공유 데이터 세트에 액세스할 수 있습니다. 자세한 내용은 [Power BI Report Server에서 OData 피드로 공유 데이터 세트에 액세스](access-dataset-odata.md)를 참조하세요.

### <a name="scale-out"></a>확장

이 릴리스에서 확장을 지원합니다. 부하 분산 장치를 사용하고 최상의 환경을 위한 서버 선호도를 설정합니다. 시나리오는 확장에 대해 아직 최적화되지 않았으므로 여러 노드에 걸쳐 잠재적으로 복제된 모델을 볼 수 있습니다. 시나리오는 네트워크 Load Balancer 및 고정 세션 없이 작동합니다. 그러나 모델이 N번 로드되므로 노드에 걸쳐 메모리가 과도하게 사용되는 것뿐만 아니라 모델이 요청 사이에서 새 노드에 도달할 때 스트리밍되므로 성능이 연결 사이에서 저하되는 것을 볼 수 있습니다.  

### <a name="administrator-settings"></a>관리자 설정

관리자는 서버 팜에 대한 SSMS 고급 속성에서 다음 속성을 설정할 수 있습니다.

* EnableCustomVisuals: True/False
* EnablePowerBIReportEmbeddedModels: True/False
* EnablePowerBIReportExportData: True/False
* MaxFileSizeMb: 기본값은 1000
* ModelCleanupCycleMinutes: 메모리에서 모델을 제거하기 위해 확인하는 주기
* ModelExpirationMinutes: 마지막으로 사용된 시간에 따라 모델 만료 및 모델 제거까지 남은 시간
* ScheduleRefreshTimeoutMinutes: 모델에 대해 적용할 수 있는 데이터 새로 고침 기간 기본적으로 2시간입니다.  하드 상한 제한은 없습니다.

**구성 파일 rsreportserver.config**

```xml
<Configuration>
  <Service>
    <PollingInterval>10</PollingInterval>
    <IsDataModelRefreshService>false</IsDataModelRefreshService>
    <MaxQueueThreads>0</MaxQueueThreads>
  </Service>
</Configuration>
```

### <a name="developer-api"></a>개발자 API

SSRS 2017에 도입된 개발자 API(REST API)는 Excel 파일 및 .pbix 파일 모두와 함께 작동하도록 Power BI Report Server에 대해 확장되었습니다. 하나의 잠재적인 사용 사례는 프로그래밍 방식으로 서버에서 파일을 다운로드하고, 새로 고친 다음 다시 게시하는 것입니다. 예를 들어, PowerPivot 모델로 Excel 통합 문서를 새로 고칠 수 있는 유일한 방법입니다.

Swagger의 Power BI Report Server 버전에서 업데이트될 큰 파일에 대한 별도의 새로운 API가 있습니다. 

### <a name="sql-server-analysis-services-ssas-and-the-power-bi-report-server-memory-footprint"></a>SSAS(SQL Server Analysis Services) 및 Power BI Report Server 메모리 사용 공간

Power BI Report Server는 이제 SSAS(SQL Server Analysis Services)를 내부적으로 호스팅합니다. 예약된 새로 고침과 관련이 없습니다. SSAS 호스팅은 보고서 서버 메모리 사용 공간을 크게 확장합니다. AS.ini 구성 파일을 서버 노드에서 사용할 수 있으므로 SSAS에 익숙한 경우 최대 메모리 제한 및 디스크 캐싱 등을 포함하여 설정을 업데이트할 수 있습니다. 자세한 내용은 [Analysis Services에서 서버 속성](https://docs.microsoft.com/sql/analysis-services/server-properties/server-properties-in-analysis-services)을 참조하세요.

### <a name="viewing-and-interacting-with-excel-workbooks"></a>Excel 통합 문서 보기 및 상호 작용

Excel 및 Power BI에는 업계에서 고유한 도구의 포트폴리오가 포함되어 있습니다. 비즈니스 분석가들이 이를 함께 사용하면 데이터를 더 쉽게 모으고, 셰이프, 분석 및 시각적으로 탐색할 수 있습니다. 웹 포털에서 Power BI 보고서를 보는 것 외에도 비즈니스 사용자는 이제 게시를 위한 단일 위치를 알려주는 Power BI Report Server의 Excel 통합 문서로 동일한 작업을 수행하고, 셀프 서비스 Microsoft BI 콘텐츠를 볼 수 있습니다.

[OOS(Office Online Server)를 Power BI Report Server 미리 보기 환경에 추가하는 방법에 관한 연습](excel-oos.md)을 게시했습니다. 볼륨 라이선스 계정을 사용하는 고객은 볼륨 라이선스 서비스 센터에서 OOS를 무료로 다운로드할 수 있으며, 보기 전용 기능을 확인할 수 있습니다. 구성된 후 사용자는 Excel 통합 문서를 보고 상호 작용할 수 있습니다.

* 외부 데이터 원본 종속성 없음
* 외부 SQL Server Analysis Services 데이터 원본에 대한 라이브 연결
* PowerPivot 데이터 모델 보유

### <a name="support-for-new-table-and-matrix-visuals"></a>새 테이블 및 행렬 시각화 개체에 대한 지원

Power BI Report Server는 이제 새 Power BI 테이블 및 행렬 시각적 개체를 지원합니다. 이러한 시각적 개체를 사용하여 보고서를 작성하려면 2017년 10월 릴리스에 대해 업데이트된 Power BI Desktop 릴리스가 필요합니다. Power BI Desktop(2017년 6월) 릴리스와 함께 설치할 수는 없습니다. Power BI Desktop의 최신 버전은 [Power BI Report Server 다운로드 페이지](https://powerbi.microsoft.com/report-server/)에서 **고급 다운로드 옵션**을 선택합니다.

## <a name="june-2017"></a>2017년 6월

* Power BI Report Server는 GA(일반적으로 사용 가능)합니다.

## <a name="may-2017"></a>2017년 5월

* 사용 가능한 Power BI Report Server 미리 보기
* Power BI 보고서 온-프레미스를 게시하는 기능
  * 사용자 지정 시각적 개체에 대한 지원
  * 앞으로 더 많은 데이터 원본을 사용하여 **Analysis Services 라이브 연결**에 대해 지원합니다.
  * Power BI Report Server에서 호스팅되는 Power BI 보고서를 표시하도록 업데이트된 Power BI 모바일 앱
* 주석을 사용하여 보고서에서 협업 향상

## <a name="next-steps"></a>다음 단계

이러한 원본을 확인하여 Power BI Report Server의 새로운 기능을 최신 상태로 유지합니다.

* [Microsoft Power BI 블로그](https://powerbi.microsoft.com/blog/)
* [SQL Server Reporting Services 팀 블로그](https://blogs.msdn.microsoft.com/sqlrsteamblog/)
* [큐브에서 Guy YouTube 채널](https://aka.ms/guyinacube)

궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](https://community.powerbi.com/)
