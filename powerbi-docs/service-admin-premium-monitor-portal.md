---
title: 관리 포털을 사용하여 Power BI Premium 용량 모니터링
description: Power BI 관리 포털을 사용하여 프리미엄 용량을 모니터링합니다.
author: minewiskan
ms.author: owend
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 02/05/2019
LocalizationGroup: Premium
ms.openlocfilehash: 59097c07719e4bb8db188e8a86db377076aea7a9
ms.sourcegitcommit: 54d44deb6e03e518ad6378656c769b06f2a0b6dc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55794115"
---
# <a name="monitor-capacities-in-the-admin-portal"></a>관리 포털에서 용량 모니터링

이 문서에서는 관리 포털의 용량 설정 영역을 사용하여 용량 성능을 빠르게 볼 수 있는 방법을 설명합니다.  용량에 대한 가장 심층적인 메트릭을 가져오려면 [Power BI Premium 용량 메트릭](service-admin-premium-monitor-capacity.md) 앱을 사용하는 것이 가장 좋습니다.

## <a name="capacity-metrics"></a>용량 메트릭

관리 포털의 **용량 설정** 영역은 지난 7일간 용량에 의해 배치된 로드 및 활용된 리소스를 나타내는 네 가지 계기를 제공합니다. 이러한 네 개의 타일은 지난 7일간 해당 메트릭이 80%를 초과하는 시간 수를 나타내는 시간별 기간에서 작동합니다. 이 메트릭은 최종 사용자 환경에 대한 잠재적인 성능 저하를 나타냅니다.

![7일간 사용](media/service-admin-premium-monitor-capacity/usage-in-days.png)

| **메트릭** | **설명** |
| --- | --- |
| CPU |CPU 사용률이 80%를 초과한 횟수입니다. |
| 메모리 쓰래싱 |백 엔드 코어에 대한 메모리 압력을 나타냅니다. 특히 이는 여러 데이터 세트의 사용으로 인한 메모리 압력에 따라 데이터 세트가 메모리에서 제거된 횟수를 나타내는 메트릭입니다. |
| 메모리 사용량 |GB(기가바이트)로 표시되는 평균 메모리 사용량입니다. |
| DQ/s | 직접 쿼리 및 라이브 연결이 제한의 80%를 초과한 횟수입니다. <br>  초당 DirectQuery 및 라이브 연결 쿼리의 총 수는 제한됩니다. 제한은 P1에 대해 30/s, P2에 대해 60/s 및 P3에 대해 120/s입니다.  직접 쿼리 및 라이브 연결 쿼리 수가 위의 제한에 추가됩니다. 예를 들어 초당 15개의 DirectQueries 및 15개의 라이브 연결이 있는 경우 제한에 도달합니다.<br> 이는 온-프레미스 및 클라우드 연결에 동일하게 적용됩니다. |
|  |  |

메트릭은 지난 주 동안의 사용률을 반영합니다.  메트릭에 대한 자세한 보기를 보려면 요약 타일 중 하나를 클릭하면 됩니다.  그러면 프리미엄 용량의 각 메트릭에 대한 자세한 차트로 이동합니다. 다음 차트에는 CPU 메트릭에 대한 세부 정보가 표시됩니다.

![자세한 CPU 사용 현황 차트](media/service-admin-premium-monitor-capacity/premium-usage-detailed-chart-cpu.png)

이러한 차트는 지난 주에 대한 시간별로 요약되며, 프리미엄 용량에서 특정 성능 관련 이벤트가 발생한 경우를 격리하는 데 도움이 될 수 있습니다.

또한 메트릭 중 하나에 대한 기본 데이터를 csv 파일로 내보낼 수도 있습니다.  이 내보내기는 지난 주 매일 3분 간격으로 측정된 자세한 정보를 제공합니다.

## <a name="next-steps"></a>다음 단계

이제 Power BI Premium 용량을 모니터링하는 방법을 이해했으므로 용량 최적화에 대해 자세히 알아보세요.

> [!div class="nextstepaction"]
> [Power BI Premium 용량 리소스 관리 및 최적화](service-premium-understand-how-it-works.md)
