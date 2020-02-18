---
title: 데이터 흐름에 향상된 컴퓨팅 엔진 사용
description: Power BI Premium에서 데이터 흐름과 함께 향상된 컴퓨팅 엔진을 사용하는 방법을 알아봅니다.
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 01/08/2020
ms.author: davidi
LocalizationGroup: Data from files
ms.openlocfilehash: 1d2bd150d33d95f2ec8759f9e876b3920eede3b6
ms.sourcegitcommit: 4b926ab5f09592680627dca1f0ba016b07a86ec0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2020
ms.locfileid: "75840073"
---
# <a name="the-enhanced-compute-engine"></a>향상된 컴퓨팅 엔진

Power BI의 향상된 컴퓨팅 엔진을 사용하면 Power BI Premium 구독자가 할당된 용량을 사용하여 데이터 흐름의 사용을 최적화할 수 있습니다. 향상된 컴퓨팅 엔진을 사용하면 다음과 같은 이점이 제공됩니다.

* *join*, *distinct*, *filter,* *group by*를 수행하는 작업과 같이 계산된 엔터티에 대해 실행이 오래 걸리는 ETL 단계에 필요한 새로 고침 시간을 대폭 줄여 줍니다.
* 엔터티에 대해 DirectQuery 쿼리를 수행할 수 있습니다(2020년 2월).

이어지는 섹션에서는 향상된 컴퓨팅 엔진을 사용하는 방법을 설명하고 일반적인 질문에 대한 답변을 제공합니다.


## <a name="using-the-enhanced-compute-engine"></a>향상된 컴퓨팅 엔진 사용

향상된 컴퓨팅 엔진은 Power BI 서비스의 **용량 설정** 페이지에 있는 **데이터 흐름** 섹션에서 사용하도록 설정할 수 있습니다. 기본적으로 향상된 컴퓨팅 엔진은 **꺼짐**으로 설정되어 있습니다. 향상된 컴퓨팅 엔진을 켜려면 다음 그림과 같이 토글을 **켜짐**으로 바꾸고 설정을 저장합니다. 

![향상된 컴퓨팅 엔진 켜기](media/service-dataflows-enhanced-compute-engine/enhanced-compute-engine-01.png)

향상된 컴퓨팅 엔진을 켜고 데이터 흐름으로 돌아가면 동일한 용량에 있는 기존의 연결된 엔터티에서 만들어진 *join* 또는 *group by* 작업과 같은 복잡한 작업을 수행하는 계산된 엔터티의 성능이 향상된 것을 볼 수 있습니다. 

컴퓨팅 엔진을 최대한 활용하려면 다음과 같이 ETL 단계를 두 개의 개별적인 데이터 흐름으로 분할해야 합니다.

* **데이터 흐름 1** - 이 데이터 흐름은 데이터 원본에서 필요한 것만 수집하고 이를 데이터 흐름 2에 넣어야 합니다.
* **데이터 흐름 2** - 모든 ETL 작업은 이 두 번째 데이터 흐름에서 수행하되, 동일한 용량에 있는 데이터 흐름 1을 참조해야 합니다. 컴퓨팅 엔진이 반드시 사용되도록 하려면 다른 작업을 수행하기 전에 먼저 접기(filter, group by, distinct, join)가 가능한 작업을 수행해야 합니다.

## <a name="common-questions-and-answers"></a>일반적인 질문과 답변

**질문:** 향상된 컴퓨팅 엔진을 사용하도록 설정했는데 새로 고침이 더 느립니다. 이유가 무엇일까요?

**답변:** 향상된 컴퓨팅 엔진을 사용하도록 설정했는데 새로 고침 시간이 느려졌다면 두 가지 원인이 있을 수 있습니다.

 - 향상된 컴퓨팅 엔진을 사용하도록 설정한 경우 엔진이 제대로 작동하려면 어느 정도의 메모리가 필요합니다. 이에 따라 새로 고침을 수행하는 데 사용할 수 있는 메모리가 줄어들고 새로 고침이 지연될 가능성이 커지며, 결과적으로 동시에 새로 고침될 수 있는 데이터 흐름의 개수가 줄어듭니다. 이 문제를 해결하려면 향상된 컴퓨팅을 사용하도록 설정할 때 동시 데이터 흐름 새로 고침에 사용 가능한 메모리가 전과 동일하게 유지되도록 데이터 흐름에 할당되는 메모리를 늘리시기 바랍니다.

 - 새로 고침이 느려지는 또 다른 원인은 컴퓨팅 엔진은 기존 엔터티에 대해서만 작동한다는 것입니다. 데이터 흐름이 데이터 흐름이 아닌 데이터 원본을 참조하는 경우에는 성능이 향상되지 않습니다. 일부 빅 데이터 시나리오의 경우 데이터 원본에서의 초기 읽기 시에 데이터가 향상된 컴퓨팅 엔진으로 전달되어야 하기 때문에 더 느려지므로 성능이 향상되지 않습니다.  

**질문:** 향상된 컴퓨팅 엔진 토글이 표시되지 않습니다. 이유가 무엇일까요?

**답변:** 향상된 컴퓨팅 엔진은 세계 각 지역에 단계적으로 출시되고 있습니다. 2020년 말에는 모든 지역에서 지원될 것으로 예상됩니다.

**질문:** 컴퓨팅 엔진에서 지원하는 데이터 형식은 무엇인가요?

**답변:** 향상된 컴퓨팅 엔진 및 데이터 흐름은 현재 다음과 같은 데이터 형식을 지원합니다. 데이터 흐름이 이러한 데이터 형식을 사용하지 않을 경우 새로 고침 중에 오류가 발생합니다.

* 날짜/시간
* 10진수
* 텍스트
* 정수
* 표준 시간대
* True/False
* 날짜
* 시간

## <a name="next-steps"></a>다음 단계

이 문서에서는 데이터 흐름에 향상된 컴퓨팅 엔진을 사용하는 방법에 대한 정보를 제공합니다. 다음 문서도 도움이 될 수 있습니다.

* [데이터 흐름을 사용하여 셀프 서비스 데이터 준비](service-dataflows-overview.md)
* [Power BI에서 데이터 흐름 만들기 및 사용](service-dataflows-create-use.md)
* [Power BI Premium의 계산된 엔터티 사용](service-dataflows-computed-entities-premium.md)
* [Power BI 데이터 흐름에 사용할 수 있는 개발자 리소스](service-dataflows-developer-resources.md)

파워 쿼리 및 예약된 새로 고침에 대한 자세한 내용은 다음 문서를 참조하세요.
* [Power BI Desktop을 사용한 쿼리 개요](desktop-query-overview.md)
* [예약된 새로 고침 구성](refresh-scheduled-refresh.md)

공통 데이터 모델에 대한 자세한 내용은 해당 개요 문서를 참조할 수 있습니다.
* [공통 데이터 모델 - 개요 ](https://docs.microsoft.com/powerapps/common-data-model/overview)

