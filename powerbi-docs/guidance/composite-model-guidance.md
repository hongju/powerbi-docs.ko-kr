---
title: Power BI Desktop의 복합 모델 지침
description: 복합 모델 개발에 대한 지침입니다.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 12/24/2019
ms.author: v-pemyer
ms.openlocfilehash: fa9ecd66d30839e169252065f7f736189b71b6ce
ms.sourcegitcommit: 8b300151b5c59bc66bfef1ca2ad08593d4d05d6a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/30/2020
ms.locfileid: "76889483"
---
# <a name="composite-model-guidance-in-power-bi-desktop"></a>Power BI Desktop의 복합 모델 지침

이 문서는 Power BI 복합 모델을 개발하는 데이터 모델러를 대상으로 작성되었습니다. 복합 모델 사용 사례를 설명하고 디자인 지침을 제공합니다. 특히, 이 지침은 복합 모델이 솔루션에 적합한지 여부를 결정하는 데 도움이 됩니다. 그러므로 이 문서는 최적의 모델을 디자인하는 데도 도움이 됩니다.

> [!NOTE]
> 복합 모델에 대한 소개는 이 문서에서 다루지 않습니다. 복합 모델에 대해 잘 모르는 경우 먼저 [Power BI Desktop에서 복합 모델 사용](../desktop-composite-models.md) 문서를 읽는 것이 좋습니다.
>
> 복합 모델은 하나 이상의 DirectQuery 원본으로 구성되기 때문에 [모델 관계](../desktop-relationships-understand.md), [DirectQuery 모델](../desktop-directquery-about.md), [DirectQuery 모델 디자인 지침](directquery-model-guidance.md)을 자세히 이해하는 것도 중요합니다.

## <a name="composite-model-use-cases"></a>복합 모델 사용 사례

가능하면 가져오기 모드에서 모델을 개발하는 것이 좋습니다. 이 모드는 가장 뛰어난 디자인 유연성과 최고의 성능을 제공합니다.

그러나 대규모 데이터 볼륨 또는 거의 실시간 데이터에 대한 보고와 관련된 과제는 가져오기 모델로 해결할 수 없습니다. 이러한 사용 사례에서는 단일 데이터 원본에 데이터가 저장되는 경우 [DirectQuery 모드에서 지원](../power-bi-data-sources.md)하는 DirectQuery 모델을 고려할 수 있습니다.

또한 다음과 같은 상황에서 복합 모델 개발을 고려할 수 있습니다.

- 모델이 DirectQuery 모델일 수 있지만 성능을 향상시키려고 합니다. 복합 모델에서는 각 테이블에 적절한 스토리지를 구성하여 성능을 향상시킬 수 있습니다. [집계](../desktop-aggregations.md)를 추가할 수도 있습니다. 이러한 최적화는 모두 이 문서의 뒷부분에서 설명합니다.
- DirectQuery 모델을 모델로 가져와야 하는 추가 데이터와 결합하려고 합니다. 가져온 데이터는 다른 데이터 원본 또는 계산된 테이블에서 로드할 수 있습니다.
- 두 개 이상의 DirectQuery 데이터 원본을 단일 모델로 결합하려고 합니다.

> [!NOTE]
> 복합 모델은 라이브 연결 원본 또는 DirectQuery 분석 데이터베이스 원본을 결합할 수 없습니다. 라이브 연결 원본에는 [외부 호스트형 모델](../service-datasets-understand.md#external-hosted-models)과 Power BI 데이터 세트가 포함됩니다. DirectQuery 분석 데이터베이스 원본에는 SAP Business Warehouse와 SAP HANA가 포함됩니다.

## <a name="optimize-model-design"></a>모델 디자인 최적화

복합 모델은 테이블 [스토리지 모드](../desktop-storage-mode.md)를 구성하고 [집계](../desktop-aggregations.md)를 추가하여 최적화할 수 있습니다.

### <a name="table-storage-mode"></a>테이블 스토리지 모드

복합 모델에서는 계산된 테이블을 제외하고 각 테이블에 대해 스토리지 모드를 구성할 수 있습니다.

- **DirectQuery**: 대규모 데이터 볼륨을 나타내는 테이블 또는 거의 실시간 결과를 제공해야 하는 테이블에 이 모드를 설정하는 것이 좋습니다. 이러한 테이블로 데이터를 가져올 수 없습니다. 일반적으로 이러한 테이블은 팩트 유형 테이블입니다(요약에 사용되는 테이블).
- **가져오기**: 차원 유형 테이블(필터링 및 그룹화에 사용되는 테이블)에 이 모드를 설정하는 것이 좋습니다. 실제로 DirectQuery 모드에서 지원되지 않는 원본을 기반으로 하는 테이블을 위한 유일한 옵션입니다. 계산된 테이블은 항상 가져오기 테이블입니다.
- **이중**: 동일한 원본에서 DirectQuery 팩트 유형 테이블과 함께 쿼리될 가능성이 있는 차원 유형 테이블에 이 모드를 설정하는 것이 좋습니다.

Power BI가 복합 모델을 쿼리할 수 있는 몇 가지 시나리오는 다음과 같습니다.

- **가져오기 또는 이중 테이블만 쿼리**: 모든 데이터가 모델 캐시에서 검색됩니다. 가능한 가장 빠른 성능을 제공합니다. 이 시나리오는 필터 또는 슬라이서 시각적 개체가 쿼리하는 차원 유형 테이블에 일반적입니다.
- **동일한 원본에서 이중 테이블 또는 DirectQuery 테이블을 쿼리**: 모든 데이터는 하나 이상의 기본 쿼리를 DirectQuery 원본에 전송하여 검색됩니다. 특히 원본 테이블에 적절한 인덱스가 있을 때 가능한 가장 빠른 성능을 제공합니다. 이 시나리오는 이중 차원 유형 테이블 및 DirectQuery 팩트 유형 테이블과 관련된 쿼리에 일반적입니다. 이러한 쿼리는 _내부 아일랜드_이며, 따라서 모든 일 대 일 또는 일 대 다 관계는 [강력한 관계](../desktop-relationships-understand.md#strong-relationships)로 평가됩니다.
- **다른 모든 쿼리**: 이러한 쿼리는 교차 아일랜드 관계를 포함합니다. 이는 가져오기 테이블이 DirectQuery 테이블과 관련이 있거나, 이중 테이블이 다른 원본의 DirectQuery 테이블과 관련되어 있기 때문입니다(이 경우에는 가져오기 테이블로 동작함). 모든 관계는 [약한 관계](../desktop-relationships-understand.md#weak-relationships)로 평가됩니다. 이는 DirectQuery가 아닌 테이블에 적용된 그룹화를 DirectQuery 원본에 가상 테이블로 보내야 함을 의미하기도 합니다. 이 경우 기본 쿼리는 특히, 대규모 그룹화 집합에서는 비효율적일 수 있습니다. 그리고 기본 쿼리에서 중요한 데이터가 노출될 가능성이 있습니다.

요약하면, 다음과 같이 하는 것이 좋습니다.

- 복합 모델이 적합한 솔루션이라고 간주합니다. 이 모델은 다른 데이터 원본의 모델 수준 통합을 허용하지만 디자인 복잡성 때문에 불리한 면도 있을 수 있습니다.
- 테이블이 대규모 데이터 볼륨을 저장하는 팩트 유형 테이블인 경우 또는 거의 실시간 결과를 제공해야 하는 경우 스토리지 모드를 **DirectQuery**로 설정합니다.
- 테이블이 차원 유형 테이블이고 동일한 원본을 기반으로 하는 **DirectQuery** 팩트 유형 테이블과 함께 쿼리되는 경우 스토리지 모드를 **이중**으로 설정합니다.
- 원본 데이터베이스와 동기화된 이중 테이블(및 모든 계산된 종속 테이블)에 대한 모델 캐시를 유지하기 위해 적절한 새로 고침 빈도를 구성합니다.
- 데이터 원본(모델 캐시 포함) 간 데이터 무결성을 보장하도록 노력합니다. 관련된 열 값이 일치하지 않을 경우 약한 관계가 해당 행을 제거합니다.
- 효율적인 조인, 필터링 및 그룹화를 위해 적절한 인덱스를 사용하여 DirectQuery 데이터 원본을 최적화합니다.
- 기본 쿼리를 가로챌 위험이 있는 경우에는 중요한 데이터를 가져오기 또는 이중 테이블로 로드하지 않습니다. 자세한 내용은 [Power BI Desktop에서 복합 모델 사용(보안 사항)](../desktop-composite-models.md#security-implications)을 참조하세요.

### <a name="aggregations"></a>집계

복합 모델의 DirectQuery 테이블에 집계를 추가할 수 있습니다. 집계는 모델에 캐시되므로 모델 테이블처럼 사용할 수는 없지만 가져오기 테이블로 동작합니다. 이는 "상위 세분성" 쿼리의 성능을 개선하기 위한 것입니다. 자세한 내용은 [Power BI Desktop의 집계](../desktop-aggregations.md)를 참조하세요.

집계 테이블은 기본 규칙을 따르는 것이 좋습니다. 행 수가 기본 테이블의 1/10 이하여야 합니다. 예를 들어 기본 테이블이 10억 행을 저장하는 경우 집계 테이블은 1억 행을 초과하지 않아야 합니다. 이 규칙은 집계 테이블을 만들고 유지 관리하는 비용을 기준으로 적절한 성능 향상을 보장합니다.

## <a name="next-steps"></a>다음 단계

이 문서와 관련된 보다 자세한 내용을 알아보려면 다음 리소스를 참조하세요.

- [Power BI Desktop에서 복합 모델 사용](../desktop-composite-models.md)
- [Power BI Desktop의 모델 관계](../desktop-relationships-understand.md)
- [Power BI Desktop의 DirectQuery 모델](../desktop-directquery-about.md)
- [Power BI Desktop에서 DirectQuery 사용](../desktop-use-directquery.md)
- [Power BI Desktop의 DirectQuery 모델 문제 해결](../desktop-directquery-troubleshoot.md)
- [Power BI 데이터 원본](../power-bi-data-sources.md)
- [Power BI Desktop의 스토리지 모드](../desktop-storage-mode.md)
- [Power BI Desktop의 집계](../desktop-aggregations.md)
- 궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](https://community.powerbi.com/)
- 제안? [Power BI 개선을 위한 아이디어 제공](https://ideas.powerbi.com)
