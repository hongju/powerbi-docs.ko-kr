---
title: Power BI Report Server에 대한 REST API를 사용하여 개발
description: REST API는 Power BI Report Server 카탈로그의 개체에 대한 프로그래밍 방식 액세스를 제공합니다.
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 05/25/2018
ms.openlocfilehash: 8f35b7a3c19751b4537a49fa8cb30f4347f080ed
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "64770754"
---
# <a name="develop-with-the-rest-apis-for-power-bi-report-server"></a>Power BI Report Server에 대한 REST API를 사용하여 개발

Power BI Report Server는 REST(Representational State Transfer) API를 지원합니다. REST API는 HTTP 작업(메서드)의 집합을 지원하는 서비스 엔드포인트가며, 보고서 서버 내에서 리소스에 대한 액세스 만들기, 검색, 업데이트 또는 삭제를 제공합니다.

REST API는 Power BI Report Server 카탈로그의 개체에 대한 프로그래밍 방식 액세스를 제공합니다. 개체의 예로는 폴더, 보고서, KPI, 데이터 원본, 데이터 세트, 새로 고침 계획, 구독 등이 있습니다. REST API를 사용하여, 예를 들어, 폴더 계층을 탐색하고, 폴더의 내용을 검색하거나 보고서 정의를 다운로드할 수 있습니다. 개체를 만들고, 업데이트하고 삭제할 수도 있습니다. 개체를 사용하는 예로는 보고서 업로드, 새로 고침 계획 실행, 폴더 삭제 등이 있습니다.

[!INCLUDE [GDPR-related guidance](../includes/gdpr-hybrid-note.md)]

## <a name="components-of-a-rest-api-requestresponse"></a>REST API 요청/응답의 구성 요소

REST API 요청/응답 쌍은 5개의 구성 요소로 구분될 수 있습니다.

* **요청 URI**는 `{URI-scheme} :// {URI-host} / {resource-path} ? {query-string}`으로 구성됩니다. 요청 URI는 요청 메시지 헤더에 포함되어 있지만 대부분의 언어 또는 프레임워크에서는 요청 메시지에서 이를 별도로 전달해야 하므로 여기에서는 별도로 호출합니다.
  
  * URI 체계: 요청을 전송하는 데 사용되는 프로토콜을 나타냅니다. 예: `http` 또는 `https`
  * URI 호스트: REST 서비스 엔드포인트가 호스트되는 서버의 도메인 이름 또는 IP 주소를 지정합니다(예: `myserver.contoso.com`).
  * 리소스 경로: 해당 리소스의 선택을 결정하는 데 서비스에서 사용하는 여러 세그먼트를 포함할 수 있는 리소스 또는 리소스 컬렉션을 지정합니다. 예: `CatalogItems(01234567-89ab-cdef-0123-456789abcdef)/Properties`는 CatalogItem에 대한 지정된 속성을 가져오는 데 사용할 수 있습니다.
  * 쿼리 문자열(선택 사항): API 버전 또는 리소스 선택 조건과 같은 추가 단순 매개 변수를 제공합니다.
* HTTP 요청 메시지 헤더 필드:
  
  * 요청하는 작업의 유형을 서비스에 알려주는 필수 [HTTP 메서드](https://www.w3.org/Protocols/rfc2616/rfc2616-sec9.html)(작업 또는 동사라고도 함) Reporting Services REST API는 DELETE, GET, HEAD, PUT, POST 및 PATCH 메서드를 지원합니다.
  * 지정된 URI 및 HTTP 메서드의 필요에 따른 선택적 추가 헤더 필드
* URI 및 HTTP 작업을 지원하는 선택적 HTTP **요청 메시지 본문** 필드 예를 들어, POST 작업은 복잡한 매개 변수로 전달되는 MIME 인코딩된 개체를 포함합니다. POST 또는 PUT 작업의 경우 본문에 대한 MIME 인코딩된 유형도 `Content-type` 요청 헤더에서 지정되어야 합니다. 일부 서비스에서는 `application/json`과 같은 특정 MIME 유형을 사용해야 합니다.
* HTTP **응답 메시지 헤더** 필드:
  
  * 2xx 성공 코드에서 4xx 또는 5xx 오류 코드에까지 이르는 [HTTP 상태 코드](http://www.w3.org/Protocols/HTTP/HTRESP.html) 또는 API 설명서에 나와 있는 것처럼 서비스 정의된 상태 코드가 반환될 수 있습니다.
  * 요청의 응답을 지원하는 데 필요한 선택적 추가 헤더 필드(예: `Content-type` 응답 헤더)
* 선택적 HTTP **응답 메시지 본문** 필드:
  
  * MIME 인코딩된 응답 개체는 데이터를 반환하는 GET 메서드의 응답과 같이 HTTP 응답 본문에서 반환됩니다. 일반적으로 이러한 개체는 `Content-type` 응답 헤더로 표시된 대로 JSON 또는 XML과 같은 구조적 형식으로 반환됩니다.

## <a name="api-documentation"></a>API 설명서

최신 API 설명서에 대한 최신 REST API를 호출합니다. REST API는OpenAPI 사양(즉 swagger 규격)을 기반으로 하며 설명서는 [SwaggerHub](https://app.swaggerhub.com/apis/microsoft-rs/PBIRS/2.0)에서 제공합니다. API 문서화를 넘어 SwaggerHub를 통해 JavaScript, TypeScript, C#, Java, Python, Ruby 등의 언어로 클라이언트 라이브러리를 생성할 수 있습니다.

## <a name="testing-api-calls"></a>API 호출 테스트

HTTP 요청/응답 메시지를 테스트하는 도구는 [Fiddler](http://www.telerik.com/fiddler)입니다. Fiddler는 HTTP 요청/응답 메시지를 진단하기 쉽게 만들어 REST 요청을 가로챌 수 있는 무료 웹 디버깅 프록시입니다.

## <a name="next-steps"></a>다음 단계

[SwaggerHub](https://app.swaggerhub.com/apis/microsoft-rs/PBIRS/2.0)를 통해 사용 가능한 API를 검토합니다.

샘플은 [GitHub](https://github.com/Microsoft/Reporting-Services)에서 제공됩니다. 샘플은 TypeScript, React 및 PowerShell 예제와 함께 웹팩을 기반으로 한 HTML5 앱을 포함합니다.

궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](https://community.powerbi.com/)