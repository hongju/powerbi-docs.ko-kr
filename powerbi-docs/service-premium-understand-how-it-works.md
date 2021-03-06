---
title: Power BI Premium 용량 메모리 사용 및 최적화
description: Power BI Premium 용량 메모리 관리 및 최적화를 이해합니다.
ms.date: 04/30/2018
ms.topic: conceptual
ms.service: powerbi
ms.component: powerbi-admin
ms.author: susuresh
ms.reviewer: susuresh
author: suds001
manager: kfile
ms.openlocfilehash: 03c5e56c5f516bb1f09f51463d4c533185fbb63c
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2018
ms.locfileid: "34298461"
---
# <a name="power-bi-premium-capacity-resource-management-and-optimization"></a>Power BI Premium 용량 리소스 관리 및 최적화

이 문서에서는 Power BI Premium 서비스가 리소스를 관리하는 방법을 설명하고 솔루션 계획 및 최적화에 대한 팁을 제공합니다.

## <a name="premium-capacity-memory-management"></a>프리미엄 용량 메모리 관리

 프리미엄 용량 메모리는 다음에서 사용됩니다.

* 로드된 데이터 집합에서 사용되는 메모리
* 데이터 집합 새로 고침에서 사용되는 메모리(예약 및 주문형)
* 보고서 쿼리에서 사용되는 메모리

사용 중인 용량의 게시된 데이터 집합에 대해 요청이 실행되면 해당 데이터 집합은 영구적 저장소에서 메모리로 로드됩니다(이 동작을 이미지 로드라고 함). 로드된 데이터 집합을 메모리에서 유지하면 이 데이터 집합에 대한 향후 쿼리에 빠르게 응답할 수 있습니다. 로드된 데이터 집합을 메모리에서 유지하는 데 필요한 메모리 외에도 보고서 쿼리 및 데이터 집합 새로 고침에는 추가 메모리가 사용됩니다.

### <a name="dataset-memory-estimation"></a>데이터 집합 메모리 추정

데이터 집합을 메모리에 로드하려고 할 때 Power BI는 데이터 집합이 요청된 명령을 완료하는 데 필요한 메모리 양을 추정합니다. 메모리의 데이터 집합은 디스크에 저장될 때의 상태보다 크기가 더 커집니다. 데이터 집합을 새로 고치는 동안에는 유휴 상태일 때 필요한 것보다 두 배의 메모리 용량이 필요합니다.

### <a name="overcommitting-capacity-eviction-and-reloading-of-datasets"></a>데이터 집합의 용량 초과 커밋, 제거 및 다시 로드

Power BI Premium은 용량 초과 커밋의 이점을 제공합니다. 예를 들어 용량 메모리가 유지할 수 있는 것보다 많은 데이터 집합을 게시할 수 있습니다. 사용 중인 용량의 게시된 데이터 집합에 용량에서 맞출 수 있는 것보다 많은 메모리가 필요한 경우에는 일부 데이터 집합이 영구적 저장소에 별도로 저장됩니다. 영구적 저장소는 각 용량과 연결된 100TB 저장소에 포함됩니다.

따라서 메모리에 남아 있는 데이터 집합은 무엇이고 다른 데이터 집합은 어떻게 될까요? 앞에서 설명한 대로 데이터 집합에 대해 요청이 실행되면 데이터 집합이 메모리로 로드됩니다(이미지 로드). 요청은 보고서 쿼리 또는 새로 고침 작업일 수 있습니다.

용량을 초과 커밋할 수 있으므로 용량에서 메모리 부족 문제가 발생할 수 있습니다. 용량에서 메모리 압력 문제가 발생하면(새 데이터 집합을 로드해야 하거나 일부 로드된 데이터 집합의 쿼리에 더 많은 메모리가 필요하기 때문) 노드는 용량 메모리를 차지하는 ‘하나 이상의 데이터 집합을 제거’합니다. 비활성 상태(현재 실행 중인 쿼리/새로 고침 작업이 없음)인 데이터 집합이 먼저 제거되고 제거 순서는 LRU(‘오래 전에 사용한 항목’) 방식으로 결정됩니다. 제거된 데이터 집합에 대해 새 명령이 실행되면 서비스는 이 데이터 집합을 메모리로 다시 로드하려고 시도하여 다른 데이터 집합이 제거될 수도 있습니다. 이 동작을 통해 용량은 메모리에 포함할 수 있는 것보다 훨씬 더 많은 데이터 집합을 제공할 수 있으므로 더 효율적인 활용이 가능합니다.

데이터 집합을 메모리에 로드하는 것은 매우 비용이 많이 드는 작업입니다. 데이터 집합 크기에 따라 작은 데이터 집합의 경우 몇 초에서 ~10GB 데이터 집합 같은 큰 데이터 집합의 경우 수십 초 또는 몇 분까지 계속될 수 있습니다. 프리미엄 용량은 가장 최근에 사용된 데이터 집합을 메모리에서 가능한 한 오래 유지하여 용량을 로드해야 하는 횟수를 최소화하려고 합니다. 추가 메모리가 필요한 경우 일부 데이터 집합을 제거해야 하고 시스템에서는 사용자 환경에 최소한의 영향을 주는 항목을 선택하려고 시도합니다. 추가 메모리가 필요한 경우 일부 데이터 집합을 제거해야 하고 시스템에서는 사용자 환경에 최소한의 영향을 주는 항목을 선택하려고 시도합니다. 예를 들어 마지막 몇 분 내에 활발하게 사용된 데이터 집합은 곧 다시 쿼리될 가능성이 높으므로 시스템은 이러한 데이터 집합의 제거를 방지합니다.

제거 프로세스 자체는 빠른 작업입니다. 데이터 집합이 제거 시 활발하게 사용되고 있지 않으면 사용자는 제거에 의한 큰 영향을 확인하지 못할 수 있습니다. 그러나 너무 많은 데이터 집합이 동시에 활발하게 사용 중이고 이들을 모두 포함할 메모리가 충분하지 않은 경우에는 많은 제거가 발생할 수 있습니다. 이로 인해 ‘삭제’ 상황이 발생합니다. 이 상황에서 데이터 집합은 지속적으로 제거 및 다시 로드되고 사용자는 응답 시간과 성능이 크게 저하되는 것을 확인할 수 있습니다.

### <a name="dataset-refresh-memory-requirement-competing-with-an-active-dataset-memory-requirement"></a>활성 데이터 집합 메모리 요구 사항과 경쟁하는 데이터 집합 새로 고침 메모리 요구 사항

데이터 집합은 사용자별로 일정에 따라 또는 요청 시 새로 고칠 수 있습니다. 앞에서 설명한 대로 전체 새로 고침에 필요한 메모리는 로드된 데이터 및 유휴 데이터 집합에 대한 메모리 크기의 두 배 이상입니다. 새로 고침을 시작하기 전에 새로 고침 메모리 요구 사항이 추정됩니다. 전체 메모리 요구 사항이 용량에서 사용 가능한 메모리보다 크면 일부 데이터 집합이 제거됩니다. 제거 후보는 오래전에 사용한 데이터 집합부터 순서대로 선택됩니다. 즉, 서비스는 최근에 사용된 데이터 집합을 가능한 한 많이 메모리에 유지하려고 합니다.

제거 후에도 필요한 메모리를 사용할 수 없는 경우에는 새로 고침이 다시 시도되도록 큐에 대기됩니다. 서비스는 성공하거나 새로운 새로 고침 작업이 시작될 때까지 다시 시도합니다.

용량의 데이터 집합에 대해 대화형 쿼리가 실행되고 진행 중인 새로 고침으로 인해 사용 가능한 메모리가 충분하지 않으면 해당 요청이 실패하고 사용자가 요청을 다시 시도해야 합니다.

## <a name="cpu-resource-management-in-premium-capacity"></a>프리미엄 용량의 CPU 리소스 관리

CPU 리소스의 두 가지 기본 소비자는 다음과 같습니다.

- 보고서의 쿼리
- 새로 고침(처리)

### <a name="queries-from-reports"></a>보고서의 쿼리

보고서 쿼리에는 용량의 CPU 리소스가 사용됩니다. 보고서에 비효율적인 쿼리가 있거나 동시 사용자가 많은 경우 CPU 리소스가 많이 사용될 수 있고 기존 용량이 로드를 처리하기에 충분하지 않을 수 있습니다.

### <a name="refresh-parallelization-policy"></a>새로 고침 병렬 처리 정책

메모리는 데이터 집합의 새로 고침을 제한할 수 있는 유일한 리소스가 아닙니다. 서버의 가상 코어 수도 요인일 수도 있습니다. 각 새로 고침 작업에는 특정 개수의 가상 코어가 필요하므로 병렬로 새로 고침을 실행할 수 있는 횟수에 대한 제한이 있습니다. SKU당 제한은 다음 표에서 자세히 설명합니다. 이러한 제한을 초과하는 추가 새로 고침은 큐에 대기됩니다.

 | SKU  | 백 엔드 V 코어  | 모델 새로 고침 병렬 처리   |
 | --- | --- | --- |
 | A1  | 0.5  | 1  |
 | A2  | 1  | 2  |
 | A3  | 2  | 3  |
 | A4  | 4  | 6  |
 | A5  | 8  | 12  |
 | A6  | 16  | 24  |
 | EM1  | 0.5  | 1  |
 | EM2  | 1  | 2  |
 | EM3  | 2  | 3  |
 | P1  | 4  | 6  |
 | P2  | 8  | 12  |
 | P3  | 16  | 24  |
 | P4  | 32  | 48  |
 | P5  | 64  | 96  |

 > [!TIP]
> 새로 고침이 지연되는 경우 용량이 지원하는 병렬 새로 고침 수를 확인합니다.

## <a name="example-scenarios"></a>예제 시나리오

다음에서는 몇 가지 일반적인 시나리오 및 서비스에서 수행된 작업을 설명합니다.

 **20개의 예약된 새로 고침이 동시에 모두 제출되는 경우** – Power BI는 동시에 처음 *x*개의 새로 고침을 시작하려고 시도합니다. *x* 값은 해당 SKU에 대한 새로 고침 병렬 처리 정책에 따라 결정됩니다. Power BI가 비활성 데이터 집합(최근에 사용되지 않은 데이터 집합)을 제거하여 충분한 메모리를 얻을 수 없는 경우 일부 *x*개의 새로 고침이 동시에 시작되지 않습니다. 시작할 수 없는 새로 고침은 시작할 수 있을 때까지 큐에 대기됩니다.

 **두 개의 새로 고침이 동시에 실행되고 새로 고침을 완료할 정도의 메모리만 있는 경우** - 완료할 수 있는 새로 고침이 시작됩니다. 다른 새로 고침은 나중에 다시 시도됩니다.

 **여러 데이터 집합을 새로 고치는 동안 많은 데이터 집합이 쿼리되고 있는 경우** - 충분한 메모리를 사용할 수 없는 경우 Power BI는 대화형 쿼리에 우선 순위를 부여하기 위해 활성 새로 고침을 중지하려고 시도합니다. 그러면 새로 고침 성능이 저하됩니다.

 **데이터 집합에 현재 용량 크기로 새로 고치기에 너무 많은 메모리가 필요한 경우** - 새로 고침이 실패합니다. 제거로 더 많은 메모리를 확보하려고 시도하지 않습니다.

 **메모리 급증을 초래하는 단일 데이터 집합을 새로 고치는 경우** - 비활성 데이터 집합을 제거하여 확보할 수 있는 메모리 양보다 급증이 더 큰 경우 급증을 처리할 충분한 메모리가 있을 때까지 나중에 새로 고침이 다시 시도됩니다.

 **모든 비활성 데이터 집합 및 새로 고침을 제거하여 충분한 메모리를 확보할 수 없는 데이터 집합에 대해 쿼리가 실행되는 경우** - 해당 쿼리가 실패합니다. 이러한 종류의 워크로드 요구 사항에 대해서는 더 높은 용량을 구매해야 합니다.

## <a name="troubleshooting-and-testing"></a>문제 해결 및 테스트

보고서가 느리거나 응답하지 않는 경우 먼저 보고서의 한 사용자만 테스트합니다. 그런 다음, 동시 사용자 로드를 늘리기 시작하여 제한을 찾습니다. 대부분의 경우 DAX(보고서 쿼리)를 조정하면 보고서의 성능이 크게 변경되고 용량에서 지원되는 동시 사용자 수가 증가할 수 있습니다.

Azure의 Power BI Embedded 용량을 사용하여 여러 SKU를 테스트하고 예상 워크로드에 대한 최적의 Premium SKU를 결정합니다. Power BI Embedded A4 SKU는 P1, A5 = P2 및 A6 = P3과 같습니다. Azure에서는 Azure Portal에서 강화 및 규모 축소하여 SKU 간에 쉽게 전환할 수 있습니다. 워크로드에 가장 적합한 SKU를 찾고 테스트를 완료한 경우 SKU를 삭제할 수 있습니다.

경우에 따라 컴퓨터에서 모델의 PBIX 파일을 열고 메모리 및 CPU 사용량을 확인하면 문제에 대한 많은 것을 파악할 수 있습니다. 이는 매우 큰 모델에는 도움이 되지 않지만 일부 작은 모델의 경우 컴퓨터에서 모델을 열고, 새로 고치고, 쿼리해 봅니다. 모델을 열 때 사용된 모델 크기, 메모리 및 CPU를 확인합니다. 새로 고치고 쿼리해 봅니다. 작업 관리자를 사용하여 로컬 PBIX 파일에 대한 CPU 및 메모리 사용을 확인합니다. 경우에 따라 컴퓨터 자체의 이러한 메트릭은 P1/P2 같은 하위 프리미엄 용량이 솔루션에 적합하지 않음을 나타낼 수 있습니다.
