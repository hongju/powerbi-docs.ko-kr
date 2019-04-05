---
title: Power BI Premium의 쿼리 캐싱
description: Power BI Premium의 쿼리 캐싱
author: maggiesMSFT
manager: kfile
ms.reviewer: bhmerc
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/03/2019
ms.author: maggies
LocalizationGroup: ''
ms.openlocfilehash: fbfd8c98743144e0c9604aca4174d6ef32916e77
ms.sourcegitcommit: de0b72915183a8a784d3227838bd704c1c209422
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/04/2019
ms.locfileid: "58914279"
---
# <a name="query-caching-in-power-bi-premium"></a>Power BI Premium의 쿼리 캐싱

Power BI Premium을 사용하는 조직은 *쿼리 캐싱*을 활용하여 데이터 세트와 관련된 보고서의 속도를 개선할 수 있습니다. 쿼리 캐싱은 프리미엄 용량이 해당 로컬 캐싱 서비스를 사용하여 쿼리 결과를 유지하도록 지시하므로 기본 데이터 소스가 해당 결과를 계산하지 않게 됩니다.

> [!IMPORTANT]
> 쿼리 캐싱은 Power BI Premium에서만 지원됩니다. Azure Analysis Services 또는 SQL Server Analysis Services를 활용하는 LiveConnect 데이터 세트에는 적용되지 않습니다.

캐시된 쿼리 결과는 사용자 및 데이터 세트 컨텍스트에 지정되고 항상 보안 규칙을 준수합니다. 현재 서비스에서는 표시되는 초기 페이지에 대한 쿼리 캐싱만을 수행합니다. 즉, 보고서와 상호 작용할 때 쿼리는 캐시되지 않습니다. 캐시는 개인 책갈피 및 영구 필터를 반영합니다. 쿼리가 캐시되면 동일한 쿼리를 통해 구동되는 [대시보드 타일](service-dashboard-tiles.md)에도 도움이 됩니다. 데이터 세트에 자주 액세스하여 자주 새로 고칠 필요가 없는 경우에 특히 성능에 도움이 됩니다. 쿼리 캐시는 쿼리의 전체 수를 줄여서 프리미엄 용량에서 부하를 줄일 수도 있습니다.

Power BI 서비스에 있는 데이터 세트의 **설정** 페이지에서 쿼리 캐싱 동작을 제어할 수 있습니다. 세 가지 설정이 있습니다.

- **용량 기본값**: 데이터 세트는 프리미엄 용량의 설정을 상속합니다. 용량 기본값은 Power BI Premium 용량 관리자에 의해 제어됩니다.

- **끄기**: 이 데이터 세트에서 쿼리 캐싱을 사용하지 않습니다.

- **켜기**: 이 데이터 세트에서 쿼리 캐싱을 사용합니다.

![쿼리 캐싱 대화 상자](media/power-bi-query-caching/power-bi-query-caching.png)

> [!NOTE]
> 캐싱 설정을 **켜기**에서 **끄기**로 변경하면 이전에 저장된 모든 데이터 세트에 대한 쿼리 결과가 용량 캐시에서 제거됩니다. 명시적으로 캐싱을 해제할 수 있습니다. 또는 관리자가 설정한 용량 기본값 설정을 **끄기**로 되돌리면 됩니다. 해제하면 다음에 보고서가 이 데이터 세트에 대해 쿼리를 실행하는 경우 약간의 지연이 발생할 수 있습니다. 해당 보고서 쿼리가 저장된 결과를 활용하지 않고 요청 시 실행되므로 지연이 발생합니다. 또한 필수 데이터 세트는 쿼리를 처리하기 전에 메모리에 로드되어야 합니다.


