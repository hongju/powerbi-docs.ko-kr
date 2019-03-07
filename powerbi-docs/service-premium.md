---
title: Microsoft Power BI Premium이란?
description: Power BI 프리미엄은 조직 또는 팀의 전용 용량으로, 사용자별 라이선스를 구입하지 않고도 더욱 신뢰할 수 있는 성능과 대용량 데이터 볼륨을 제공합니다.
author: minewiskan
ms.author: owend
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 02/28/2019
ms.custom: seodec18
LocalizationGroup: Premium
ms.openlocfilehash: cb9280f47f1f2d28ce6fabda2dbc173fbdc837ac
ms.sourcegitcommit: 364ffa1178cdfb0a20acffc0fd79922ebc892d72
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57226138"
---
# <a name="what-is-microsoft-power-bi-premium"></a>Microsoft Power BI Premium이란?

> [!NOTE]
> 이 문서는 현재 새로운 기능을 설명하고, 세부 사항을 제공하며 가독성을 향상시키기 위해 업데이트되고 있습니다. 최신 정보는 [Power BI Premium 용량 배포 및 관리](whitepaper-powerbi-premium-deployment.md)를 참조하세요.

Power BI Premium은 조직에 대해 Power BI 서비스를 실행하는 전용 리소스를 제공합니다. 더욱 신뢰할 수 있는 성능을 제공하고 더 큰 데이터 볼륨을 사용하도록 설정합니다. 또한 Premium을 통해 콘텐츠 소비자를 위한 사용자별 Pro 라이선스를 구입할 필요 없이 광범위하게 콘텐츠를 배포할 수 있습니다.  

## <a name="premium-capacity-and-shared-capacity"></a>프리미엄 용량 및 공유 용량

‘프리미엄 용량’에 작업 영역을 할당하여 Power BI Premium을 활용합니다. 프리미엄 용량은 조직을 위한 전용 리소스입니다. 프리미엄 용량에 할당되지 않은 작업 영역은 *공유 용량*에 있습니다. 공유 용량을 사용하면 다른 고객이 공유하는 계산 리소스에서 워크로드가 실행됩니다.

다음 이미지는 Contoso 조직을 예로 사용하여 프리미엄 용량과 공유 용량 간의 관계를 보여 줍니다.

![Power BI Premium의 그림](media/service-premium/premium-chart.png)

| 영역 | 설명 |
| --- | --- |
| **(1)** 프리미엄 용량 내 항목 | <ul><li>앱 작업 영역(멤버 또는 관리자로)에 액세스하고 앱을 게시하려면 Power BI Pro 라이선스가 필요합니다.<li>앱을 공유하려면 Pro 라이선스가 필요하지만 앱을 사용하는 데는 필요하지 않습니다.<li>할당된 라이선스에 관계 없이 모든 대시보드 수신자는 데이터 경고를 설정할 수 있습니다.<li>포함할 REST API는 사용자 계정이 아닌 Pro 라이선스가 있는 서비스 계정을 사용합니다.</ul> |
| **(2)** 공유 용량에서 내 작업 영역 | <ul><li>앱을 공유하거나 사용하려면 Pro 라이선스가 필요합니다.</ul> |
| **(3)** 공유 용량에서 앱 작업 영역 | <ul><li>앱 사용 현황에는 Pro 라이선스가 필요합니다.</ul>|
| | |

공유 용량에서 Power BI는 모든 사용자를 위해 환경의 품질을 보장하도록 더 많은 제한을 개별 사용자에게 적용합니다. 기본적으로 작업 영역은 개인 ‘내 작업 영역’ 및 앱 작업 영역을 포함하여 공유 용량에 있습니다.

다음 표는 공유 용량과 프리미엄 용량 간의 차이점에 대한 요약을 제공합니다.

|  | 공유 용량 | Power BI 프리미엄 용량 |
| --- | --- | --- |
| **새로 고침 빈도** |8/일 |48/일 |
| 전용 하드웨어로 격리 |![사용할 수 없음](media/service-premium/not-available.png) |![](media/service-premium/available.png) |
| 엔터프라이즈 배포 대상 *모든 사용자* | | |
| 앱 및 공유 |![사용할 수 없음](media/service-premium/not-available.png) |![](media/service-premium/available.png) |
| 포함된 API 및 컨트롤 |![사용할 수 없음](media/service-premium/not-available.png) |![](media/service-premium/available.png)<sup>[1](#fnt1)</sup> |
| Power BI 보고서 온-프레미스 게시 |![사용할 수 없음](media/service-premium/not-available.png) |![](media/service-premium/available.png) |
| | | |

<a name="fnt1">1</a> 향후에 Power BI Premium에 제공될 향상된 기능입니다.



### <a name="premium-capacity-nodes"></a>프리미엄 용량 노드

Power BI 프리미엄은 서로 다른 v-코어 용량으로 노드 구성에서 사용할 수 있습니다. 특정 SKU 제품 및 비용에 대한 자세한 내용은 [Power BI 가격 책정](https://powerbi.microsoft.com/pricing/)을 참조하세요. 또한 [비용 계산기](https://powerbi.microsoft.com/calculator/)를 사용할 수 있습니다. 포함된 분석 용량 계획에 관한 정보는 [Power BI 엔터프라이즈 배포 계획 백서](https://aka.ms/pbienterprisedeploy)를 참조하세요. 간단히 설명하면 다음과 같습니다.

* P 노드는 포함된 배포 또는 서비스 배포에 사용할 수 있습니다.

* EM 노드는 포함된 배포에만 사용할 수 있습니다. EM 노드에는 Power BI Pro 라이선스가 없는 사용자와 앱 공유와 같은 프리미엄 기능에 대한 액세스 권한이 없습니다.

| 용량 노드 | 총 V 코어<br/>*(백 엔드+프런트 엔드)*  | 백 엔드 V 코어 <sup>[1](#fn1)</sup> | 프런트 엔드 V 코어 <sup>[2](#fn2)</sup> | DirectQuery/라이브 연결 제한 | 최대 동시 새로 고침 |  가용성
| --- | --- | --- | --- | --- | --- | --- | --- |
| EM1(매월) |1개 가상 코어 |0.5v-코어, 2.5GB RAM |0.5v-코어 |초당 3.75 |  1 | 사용 가능 |
| EM2(매월) |2v-코어 |1v-코어, 5GB RAM |1개 가상 코어 |초당 7.5 |  2 | 사용 가능 |
| EM3(매월) |4v-코어 |2v-코어, 10GB RAM |2v-코어 | | 3 |  사용 가능 |
| P1 |8v-코어 |4v-코어, 25GB RAM |4v-코어 |초당 30 | 6 | 사용 가능함(매월도 사용 가능함) |
| P2 |16v-코어 |8v-코어, 50GB RAM |8v-코어 |초당 60 | 12 | 사용 가능 |
| P3 |32v-코어 |16v-코어, 100GB RAM |16v-코어 |초당 120 | 24 | 사용 가능 |
| | | | | | | |

<a name="fn1">1</a>: 프런트 엔드 V 코어는 웹 서비스에 책임이 있습니다. 예를 들어 대시보드 및 보고서 문서 관리, 액세스 권한 관리, 예약, API, 업로드 및 다운로드, 일반적으로 사용자 환경에 관련된 모든 항목에 책임이 있습니다. 

<a name="fn2">2</a>: 백 엔드 V 코어는 쿼리 처리, 캐시 관리, R 서버 실행, 데이터 새로 고침, 자연어 처리, 실시간 피드, 보고서 및 이미지의 서버 쪽 렌더링 등의 어려운 작업에 책임이 있습니다. 백 엔드 V 코어를 사용하여 메모리의 일정량도 예약됩니다. 큰 데이터 모델 또는 많은 수의 활성 데이터 세트를 처리할 때 충분한 메모리를 갖는 것은 특히 중요해지고 있습니다.

## <a name="workloads-in-premium-capacity"></a>프리미엄 용량에서 워크로드

기본적으로 **Power BI Premium** 및 **Power BI Embedded**의 용량은 클라우드에서 실행 중인 Power BI 쿼리와 연결된 워크로드만 지원합니다. 프리미엄은 또한 **AI**, **데이터 흐름** 및 **페이지를 매긴 보고서**에 대한 추가 워크로드를 지원합니다. 이러한 워크로드는 Power BI 관리 포털에서 또는 Power BI REST API를 통해 사용하도록 설정합니다. 다양한 워크로드가 서로 영향을 미치는 방식을 제어할 수 있도록 각 워크로드가 이용하는 최대 메모리를 설정할 수도 있습니다. 자세한 내용은 [워크로드 구성](service-admin-premium-workloads.md)을 참조하세요.

### <a name="default-memory-settings"></a>기본 메모리 설정

다음 표에서는 사용 가능한 다양한 [용량 노드](#premium-capacity-nodes)를 기반으로 하는 기본 및 최소 메모리 값을 보여줍니다. 메모리는 데이터 흐름에는 동적으로 할당되지만 페이지를 매긴 보고서에는 정적으로 할당됩니다. 자세한 내용은 다음 섹션인 [페이지를 매긴 보고서에 대한 고려 사항](#considerations-for-paginated-reports)을 참조하세요.

#### <a name="microsoft-office-skus-for-software-as-a-service-saas-scenarios"></a>SaaS(Software as a Service)용 Microsoft Office SKU 시나리오

|                     | EM3                      | P1                       | P2                      | P3                       |
|---------------------|--------------------------|--------------------------|-------------------------|--------------------------|
| 페이지가 매겨진 보고서 | 해당 없음 | 기본값 20%, 최솟값 10% | 기본값 20%, 최솟값 5% | 기본값 20%, 최솟값 2.5% |
| 데이터 흐름 | 기본값 20%, 최솟값 8%  | 기본값 20%, 최솟값 4%  | 기본값 20%, 최솟값 2% | 기본값 20%, 최솟값 1%  |
| | | | | |

#### <a name="microsoft-azure-skus-for-platform-as-a-service-paas-scenarios"></a>PaaS(Platform as a Service)용 Microsoft Azure SKU 시나리오

|                  | A1                       | A2                       | A3                      | A4                       | A5                      | A6                        |
|-------------------|--------------------------|--------------------------|-------------------------|--------------------------|-------------------------|---------------------------|
| 페이지가 매겨진 보고서 | 해당 없음                      | 해당 없음                      | 해당 없음                     | 기본값 20%, 최솟값 10% | 기본값 20%, 최솟값 5% | 기본값 20%, 최솟값 2.5% |
| 데이터 흐름         | 기본값 27%, 최솟값 27% | 기본값 20%, 최솟값 16% | 기본값 20%, 최솟값 8% | 기본값 20%, 최솟값 4%  | 기본값 20%, 최솟값 2% | 기본값 20%, 최솟값 1%   |

### <a name="considerations-for-paginated-reports"></a>페이지를 매긴 보고서에 대한 고려 사항

페이지를 매긴 보고서 워크로드를 사용하는 경우 페이지를 매긴 보고서를 통해 콘텐츠에 따라 텍스트 색상을 동적으로 변경하는 경우와 같이 보고서를 렌더링할 때 고유의 코드를 실행할 수 있습니다. 이에 따라 용량 내에 포함된 공간에서 페이지를 매긴 보고서를 실행하여 Power BI Premium 용량을 보호합니다. 워크로드가 활성 상태인지 여부와 관계없이 사용자가 지정하는 최대 메모리를 이 공간에 할당합니다. 동일한 용량에서 Power BI 보고서 또는 데이터 흐름을 사용하는 경우 다른 워크로드에 부정적인 영향을 미치지 않도록 페이지를 매긴 보고서에 충분히 작은 메모리를 설정해야 합니다.

드물지만 페이지를 매긴 보고서 워크로드를 사용할 수 없는 경우가 있습니다. 이런 경우 워크로드에서 관리 포털에 오류 상태를 표시하며 사용자에게는 보고서 렌더링 제한 시간이 표시됩니다. 이 문제를 해결하려면 워크로드를 사용하지 않도록 설정한 다음, 다시 사용하도록 설정하세요.

## <a name="power-bi-report-server"></a>Power BI Report Server

Power BI Premium에는 조직의 Power BI Report Server를 온-프레미스에서 실행할 수 있는 기능도 포함됩니다. 자세한 내용은 [Power BI Report Server 시작](report-server/get-started.md)을 참조하세요.

## <a name="next-steps"></a>다음 단계

[Power BI Premium 용량 배포 및 관리](whitepaper-powerbi-premium-deployment.md)   
[Power BI Premium 구매 방법](service-admin-premium-purchase.md)   
[Power BI 프리미엄 FAQ](service-premium-faq.md)   



궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](https://community.powerbi.com/)
