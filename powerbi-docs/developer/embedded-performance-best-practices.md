---
title: Power BI Embedded 성능에 대한 모범 사례
description: 이 문서에서는 포함된 분석 모범 사례에 대한 지침을 제공합니다.
author: KesemSharabi
ms.author: kesharab
manager: rkarlin
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 12/12/2018
ms.openlocfilehash: 93c26d64193346b9b2db52bb2d0a0bbe32a4e97b
ms.sourcegitcommit: 57e45f291714ac99390996a163436fa1f76db427
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/26/2019
ms.locfileid: "71305702"
---
# <a name="power-bi-embedded-performance-best-practices"></a>Power BI Embedded 성능에 대한 모범 사례

이 문서에서는 애플리케이션의 보고서, 대시보드 및 타일을 더 빠르게 렌더링하기 위한 추천 사항을 제공합니다.

> [!Note]
> 로드 시간은 주로 시각적 개체, 데이터 크기, 쿼리 및 계산된 측정값의 복잡성을 포함하여 보고서 및 데이터 자체와 관련된 요소에 따라 달라집니다. 자세한 내용은 [Power BI 성능 모범 사례](../power-bi-reports-performance.md)를 참조하세요.

## <a name="update-tools-and-sdk-packages"></a>도구 및 SDK 패키지 업데이트

도구 및 SDK 패키지를 최신 상태로 유지합니다.

* 항상 최신 버전의 [Power BI Desktop](https://powerbi.microsoft.com/desktop/)을 사용합니다.

* 최신 버전의 [Power BI 클라이언트 SDK](https://github.com/Microsoft/PowerBI-JavaScript)를 설치합니다. 향상된 추가 기능을 계속 릴리스하고 있으므로 수시로 후속 조치를 수행해야 합니다.

## <a name="embed-parameters"></a>포함 매개 변수

`powerbi.embed(element, config)` 메서드는 요소와 구성을 받습니다. 구성 매개 변수는 성능에 영향을 주는 필드를 포함합니다.

### <a name="embed-url"></a>포함 URL

포함 URL은 직접 생성하지 마세요. 대신, [보고서 가져오기](/rest/api/power-bi/reports/getreportsingroup), [대시보드 가져오기](/rest/api/power-bi/dashboards/getdashboardsingroup) 또는 [타일 가져오기](/rest/api/power-bi/dashboards/gettilesingroup) API를 호출하여 포함 URL을 가져옵니다. URL에 **_config_** 라는 새 매개 변수를 추가하여 성능을 향상시켰습니다.

### <a name="permissions"></a>권한

편집 모드에 보고서를 포함시키지 않으려면 **보기** 권한을 제공합니다. 이렇게 하면 포함된 코드에서 편집 모드에 사용되는 구성 요소를 초기화하지 않습니다.

### <a name="filters-bookmarks-and-slicers"></a>필터, 책갈피 및 슬라이서

일반적으로 보고서 시각적 개체는 캐시된 데이터와 함께 저장됩니다. 캐시된 데이터는 인식된 성능을 제공하는 데 사용됩니다. 쿼리가 실행되는 동안 보고서에서 캐시된 데이터를 렌더링합니다. 필터, 책갈피 또는 슬라이서가 제공되는 경우 캐시된 데이터는 관련이 없으며 시각적 쿼리가 종료된 후에만 시각적 개체가 렌더링됩니다.

동일한 필터, 책갈피 및 슬라이서를 사용하여 보고서를 포함하는 경우 성능을 향상시키려면 이미 적용된 필터, 책갈피 및 슬라이서를 사용하여 보고서를 저장합니다. 그러면 필터, 책갈피 및 슬라이서를 포함하는 캐시된 데이터로 보고서가 렌더링됩니다.

## <a name="switching-between-reports"></a>보고서 간 전환

동일한 iframe에 여러 보고서를 포함하는 경우 각 보고서에 대해 새 iframe을 생성하지 마세요. 대신, 새 보고서를 포함하는 다른 구성의 `powerbi.embed(element, config)`를 사용합니다.

> [!NOTE]
> '앱 소유 데이터' 시나리오에 대한 보고서 간 전환은 새 포함 토큰을 생성하는 데 필요하기 때문에 매우 효과적일 수 있습니다.

## <a name="query-caching"></a>쿼리 캐싱

Power BI Premium 용량 또는 Power BI Embedded 용량을 사용하는 조직은 쿼리 캐싱을 활용하여 데이터 세트와 관련된 보고서의 속도를 개선할 수 있습니다.

[Power BI의 쿼리 캐싱에 대해 자세히 알아보세요](../power-bi-query-caching.md).

## <a name="preload"></a>미리 로드

최종 사용자 성능을 높이려면 `powerbi.preload()`를 사용합니다. `powerbi.preload()` 메서드는 나중에 보고서를 포함하는 데 사용되는 JavaScript, CSS 파일 및 기타 아티팩트를 다운로드합니다.

보고서를 즉시 포함하지 않을 경우 `powerbi.preload()`를 호출합니다. 예를 들어, Power BI Embedded 콘텐츠가 홈페이지에 나타나지 않는 경우, `powerbi.preload()`를 사용하여 콘텐츠 포함을 위해 사용되는 아티팩트를 다운로드하고 캐시합니다.

## <a name="bootstrapping-the-iframe"></a>Iframe 부트스트래핑

> [!NOTE]
> iframe을 부트스트래핑하려면 [Power BI client SDK](https://github.com/Microsoft/PowerBI-JavaScript) 버전 2.9가 필요합니다.

`powerbi.bootstrap(element, config)`를 사용하면 모든 필수 매개 변수를 사용할 수 있기 전에 포함을 시작할 수 있습니다. 부트스트랩 API는 iframe을 준비하고 초기화합니다.
부트스트랩 API를 사용할 때도 동일한 HTML 요소에 대해 `powerbi.embed(element, config)`를 호출해야 합니다.

예를 들어, 이 기능의 사용 사례 중 하나는 iframe 부트스트랩과, 포함을 위한 백 엔드 호출을 병렬로 실행하는 것입니다.
> [!TIP]
> iframe이 최종 사용자에게 표시되기 전에 이를 생성하는 것이 가능한 경우 부트스트랩 API를 사용하세요.

[iframe 부트스트랩에 대해 자세히 알아보세요](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Bootstrap-For-Better-Performance).

## <a name="measure-performance"></a>성능 측정

### <a name="performance-events"></a>성능 이벤트

포함된 성능을 측정하려면 다음 두 가지 이벤트를 사용할 수 있습니다.

1. 로드 이벤트: 보고서가 초기화될 때까지의 시간입니다(로드가 완료되면 Power BI 로고가 사라짐).
2. 렌더링 이벤트: 실제 데이터를 사용하여 보고서가 완전히 렌더링될 때 까지의 시간입니다. 보고서가 다시 렌더링될 때마다(예: 필터가 적용된 후) 렌더링됨 이벤트가 발생합니다. 보고서를 측정하려면 먼저 발생한 이벤트에서 계산을 수행해야 합니다.

캐시된 데이터는 사용 가능한 경우 렌더링되지만 추가 이벤트는 생성되지 않습니다.

[이벤트 처리에 대해 자세히 알아보세요](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Handling-Events).

### <a name="performance-analyzer"></a>성능 분석기

보고서 요소의 성능을 검사하려면 Power BI Desktop에서 성능 분석기를 사용할 수 있습니다.
성능 분석기를 사용하여 각 보고서 요소가 수행하는 방식을 측정하는 로그를 보고 기록할 수 있습니다.

[성능 분석기에 대해 자세히 알아보세요](../desktop-performance-analyzer.md).

> [!NOTE]
> 포함된 보고서 성능을 powerbi.com의 성능과 비교하는 것을 항상 기억하세요. 이렇게 하면 성능 문제를 파악하는 데 도움이 될 수 있습니다.

## <a name="next-steps"></a>다음 단계

* [Power BI 보고서 성능 모범 사례](../power-bi-reports-performance.md)
* [Power BI Embedded 문제를 해결 하는 방법](embedded-troubleshoot.md)
* [Power BI Embedded FAQ](embedded-faq.md)
