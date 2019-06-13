---
title: Power BI Embedded 성능에 대한 모범 사례
description: 이 문서에서는 포함된 분석 모범 사례에 대한 지침을 제공합니다.
author: rkarlin
ms.author: rkarlin
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 12/12/2018
ms.openlocfilehash: d2e4a29b3dd7e36081458ff6ca51b0006a10466f
ms.sourcegitcommit: 81ba3572531cbe95ea0b887b94e91f94050f3129
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2019
ms.locfileid: "66750949"
---
# <a name="power-bi-embedded-performance-best-practices"></a>Power BI Embedded 성능에 대한 모범 사례

이 문서에서는 애플리케이션의 보고서, 대시보드 및 타일을 더 빠르게 렌더링하기 위한 추천 사항을 제공합니다.

## <a name="embed-parameters"></a>포함 매개 변수

Powerbi.embed() 메서드는 보고서, 대시보드 또는 타일을 포함하는 매개 변수를 거의 받지 않습니다. 이러한 매개변수는 성능에 영향을 미칩니다.

### <a name="embed-url"></a>포함 URL

포함 URL은 직접 생성하지 마세요. 대신 [보고서 가져오기](/rest/api/power-bi/reports/getreportsingroup), [대시보드 가져오기](/rest/api/power-bi/dashboards/getdashboardsingroup) 또는 [타일 가져오기](/rest/api/power-bi/dashboards/gettilesingroup) API를 호출하여 포함 URL을 가져옵니다. **_config_** 라는 URL에 새 매개 변수를 추가하여 성능을 향상시켰습니다.

### <a name="permissions"></a>권한

**편집 모드**에 보고서를 포함시키지 않으려면 **보기** 권한을 제공합니다. 이렇게 하면 포함 코드에서 편집 모드에 사용되는 구성 요소를 초기화하지 않습니다.

### <a name="filters-bookmarks-and-slicers"></a>필터, 책갈피 및 슬라이서

일반적으로 보고서 시각적 개체는 캐시된 데이터와 함께 저장됩니다. 캐시된 데이터는 인식된 성능을 제공하는 데 사용됩니다. 쿼리가 실행되는 동안 보고서에서 캐시된 데이터를 렌더링합니다. 필터, 책갈피 또는 슬라이서가 제공되는 경우 캐시된 데이터는 관련이 없습니다. 그러면 시각적 쿼리를 실행한 후에만 시각적 개체가 렌더링됩니다.

동일한 필터를 사용하여 보고서를 포함하는 경우 필터 목록을 로드 구성에 전달하지 않으려면 필터가 이미 적용된 보고서를 저장합니다.

## <a name="preload"></a>미리 로드

최종 사용자 성능을 향상시키려면 *preload*(미리 로드) JavaScript API를 사용합니다.
Powerbi.preload()는 나중에 보고서에 포함하는 데 사용되는 JavaScript, CSS 파일 및 기타 아티팩트를 다운로드합니다.

보고서를 즉시 포함하지 않을 경우 미리 로드를 호출합니다. 예를 들어 단추 클릭에 보고서를 포함하는 경우 이전 페이지가 로드될 때 미리 로드를 호출하는 것이 좋습니다. 그러면 애플리케이션 사용자가 단추를 클릭하면 렌더링이 더 빨라집니다.

## <a name="measure-performance"></a>성능 측정

성능을 측정하려면 다음을 사용합니다.

1. 로드됨: 보고서가 초기화될 때까지의 시간입니다(회전은 사용자에게 표시되지 않음).
2. 렌더링됨: 실제 데이터를 사용하여 보고서가 완전히 렌더링될 때까지 걸리는 시간입니다. 보고서가 다시 렌더링될 때마다(즉 필터가 적용된 후) 렌더링됨 이벤트가 발생합니다. 보고서를 먼저 측정하려면 먼저 발생한 이벤트에서 계산을 수행해야 합니다.

캐시된 데이터는 사용 가능할 때 렌더링되지만 이 데이터에 대한 이벤트가 아직 없습니다.

## <a name="update-tools-and-sdk-packages"></a>도구 및 SDK 패키지 업데이트

도구 및 SDK 패키지를 최신 상태로 유지합니다.

* 항상 최신 버전의 [Power BI Desktop](https://powerbi.microsoft.com/desktop/)을 사용합니다.

* 최신 버전의 [Power BI 클라이언트 SDK](https://github.com/Microsoft/PowerBI-JavaScript)를 설치합니다. 더욱 향상된 기능을 계속 릴리스하고 있으므로 수시로 후속 조치를 수행해야 합니다.

* 설치할 패키지는 다음과 같습니다.
    * Npm 패키지: powerbi-client
    * NuGet 패키지: Microsoft.PowerBI.JavaScript

> [!Note]
> 로드 시간은 주로 보고서 및 데이터 자체와 관련된 요소, 즉 시각적 개체 수, 데이터 크기, 쿼리와 계산된 측정값의 복잡성에 따라 달라집니다. 보고서의 로드 시간을 향상시키려면 [모범 사례](../power-bi-reports-performance.md)를 따르세요.

## <a name="next-steps"></a>다음 단계

* [Power BI 보고서 성능 모범 사례](../power-bi-reports-performance.md)
* [Power BI Embedded 문제를 해결 하는 방법](embedded-troubleshoot.md)
* [Power BI Embedded FAQ](embedded-faq.md)
