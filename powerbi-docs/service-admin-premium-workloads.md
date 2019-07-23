---
title: Power BI Premium의 워크로드를 구성하는 방법
description: Power BI Premium 용량의 워크로드를 구성하는 방법을 알아봅니다.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 04/15/2019
LocalizationGroup: Premium
ms.openlocfilehash: c84bebef5589ec391e3640ff3be674b1fb5a0ebd
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "65564876"
---
# <a name="configure-workloads-in-a-premium-capacity"></a>프리미엄 용량에서 워크로드 구성

이 문서에서는 Power BI Premium 용량에 대한 워크로드를 사용하도록 설정하고 구성하는 방법을 설명합니다. 기본적으로 용량은 Power BI 쿼리 실행과 관련된 워크로드만 지원합니다. **[AI(Cognitive Services)](service-cognitive-services.md)** , **[데이터 흐름](service-dataflows-overview.md#dataflow-capabilities-on-power-bi-premium)** 및 **[페이지를 매긴 보고서](paginated-reports-save-to-power-bi-service.md)** 에 대해 추가 워크로드를 사용하도록 설정하고 구성할 수도 있습니다.

## <a name="default-memory-settings"></a>기본 메모리 설정

쿼리 워크로드는 프리미엄 용량 SKU에 의해 결정되는 리소스에 최적화되며 제한됩니다. 또한 프리미엄 용량은 용량 리소스를 사용할 수 있는 추가 워크로드를 지원합니다. 이러한 워크로드에 대한 기본 메모리 값은 SKU에 사용 가능한 용량 노드를 기반으로 합니다. 최대 메모리 설정은 누적되지 않습니다. 지정된 최댓값까지의 메모리는 AI 및 데이터 흐름에 대해 동적으로 할당되지만, 페이지를 매긴 보고서에 대해서는 정적으로 할당됩니다. 

### <a name="microsoft-office-skus-for-software-as-a-service-saas-scenarios"></a>SaaS(Software as a Service)용 Microsoft Office SKU 시나리오

|                     | EM2                      | EM3                       | P1                      | P2                       | P3                       |
|---------------------|--------------------------|--------------------------|-------------------------|--------------------------|--------------------------|
| AI | 해당 없음 | 해당 없음 | 20% 기본; 최소 20% | 기본값 20%, 최솟값 10% | 기본값 20%, 최솟값 5% |
| 데이터 흐름 | 해당 없음 |기본값 20%, 최소값 12%  | 기본값 20%, 최솟값 5%  | 기본값 20%, 최소값 3% | 기본값 20%, 최솟값 2%  |
| 페이지를 매긴 보고서 | 해당 없음 |해당 없음 | 기본값 20%, 최솟값 10% | 기본값 20%, 최솟값 5% | 기본값 20%, 최솟값 2.5% |
| | | | | | |

### <a name="microsoft-azure-skus-for-platform-as-a-service-paas-scenarios"></a>PaaS(Platform as a Service)용 Microsoft Azure SKU 시나리오

|                  | A1                       | A2                       | A3                      | A4                       | A5                      | A6                        |
|-------------------|--------------------------|--------------------------|-------------------------|--------------------------|-------------------------|---------------------------|
| AI | 해당 없음                      | 20% 기본; 최소 100%                     | 20% 기본; 최소 50%                     | 20% 기본; 최소 20% | 기본값 20%, 최솟값 10% | 기본값 20%, 최솟값 5% |
| 데이터 흐름         | 기본값 40%, 최소값 40% | 기본값 24%, 최소값 24% | 기본값 20%, 최소값 12% | 기본값 20%, 최솟값 5%  | 기본값 20%, 최소값 3% | 기본값 20%, 최솟값 2%   |
| 페이지를 매긴 보고서 | 해당 없음                      | 해당 없음                      | 해당 없음                     | 기본값 20%, 최솟값 10% | 기본값 20%, 최솟값 5% | 기본값 20%, 최솟값 2.5% |
| | | | | | |

## <a name="workload-settings"></a>작업 설정

### <a name="ai-preview"></a>AI (미리 보기)

외에 **최대 메모리** 설정, AI 워크 로드에는 추가 설정이 **Power BI Desktop에서 사용 하도록 허용**합니다. 기본값은 **해제**합니다. 이 설정은 나중에 사용 하기 위해 예약 됩니다 하 고 모든 테 넌 트에 나타날 수 없습니다.

### <a name="datasets-preview"></a>데이터 집합 (미리 보기)

기본적으로 데이터 집합 작업 사용 가능 하 고 비활성화할 수 없습니다. 이 워크 로드는 추가 설정이 포함 **XMLA 끝점**합니다. 기본값은 **1**를 사용 하도록 설정 하는 의미입니다. 이 설정은 클라이언트 응용 프로그램에서 연결 유지 설정 작업 영역 및 앱 수준에서 보안 그룹 구성원 자격을 지정 합니다. 자세한 내용은 참조 하세요 [클라이언트 응용 프로그램 및 도구를 사용 하 여 데이터 집합에 Connect](service-premium-connect-tools.md)합니다.

### <a name="dataflows"></a>데이터 흐름

이외에 **최대 메모리** 설정, 데이터 흐름 워크 로드가 추가 설정이 **컨테이너 크기**합니다. 이 설정을 사용 하면 더 복잡 하 고 계산 집약적 데이터 흐름을 처리 하는 것에 대 한 데이터 흐름 작업 성능을 최적화할 수 있습니다.

데이터 흐름을 새로 고칠 때 데이터 흐름 작업 데이터 흐름의 각 엔터티에 대 한 컨테이너를 생성 합니다. 각 컨테이너에서 볼륨까지 메모리 컨테이너 크기 설정에 지정 된 걸릴 수 있습니다. 모든 Sku에 대 한 기본값은 **700MB**합니다. 이 설정을 변경 하는 것이 좋습니다.

- 데이터 흐름이 새로 고침 하는 데 너무 오래 걸리는 또는 제한 시간에 데이터 흐름 새로 고침이 실패 합니다.
- 데이터 흐름 엔터티에 계산 단계, 예를 들어, 조인이 포함 됩니다.  

사용 하는 것이 좋습니다.의 합니다 [Power BI Premium 용량 메트릭을](service-admin-premium-monitor-capacity.md) 데이터 흐름 작업 성능을 분석 하는 앱입니다. 

경우에 따라 컨테이너 크기를 늘리면는 성능이 향상 되지 않을 수 있습니다. 예를 들어 데이터 흐름 중요 한 계산을 수행 하지 않고 원본 에서만에서 데이터를 가져오는, 하는 경우 아마도 컨테이너 크기를 변경 도움이 되지 않습니다. 새로 고침 작업 엔터티에 대 한 더 많은 메모리를 할당 하려면 데이터 흐름 작업을 통해 컨테이너 크기를 늘리면 도움이 될 수 있습니다. 더 많은 메모리를 할당 함으로써 과도 하 게 계산된 엔터티 새로 고침 하는 데 걸리는 시간을 줄일 수 있습니다. 

컨테이너 크기 값을 데이터 흐름 작업에 대 한 최대 메모리를 초과할 수 없습니다. 예를 들어 P1 용량 25GB 메모리에 있습니다. 경우 최대 메모리 (%) 데이터 흐름 작업 설정 된 컨테이너 크기 (MB) 5000 20%를 초과할 수 없습니다. 모든 경우에 값을 높게 설정 하는 경우에 컨테이너 크기는 최대 메모리를 초과할 수 없습니다. 

### <a name="paginated-reports-preview"></a>페이지 매긴된 보고서 (미리 보기)

페이지가 매겨진된 보고서는 보고서를 렌더링할 때 실행 되도록 사용자 지정 코드를 허용 합니다. 예를 들어 동적으로 콘텐츠를 기반으로 하는 텍스트 색을 변경, 추가 메모리 걸릴 수 있습니다는. Power BI Premium 용량은 용량 내 포함된 공간에서 페이지를 매긴 보고서를 실행합니다. 최대 메모리는 지정한 *여부* 워크 로드를 활성화 합니다. 낮은 설정 되어 있는지 확인에서 기본적으로 최대 메모리 설정을 변경 하는 경우 한다는 충분 하지 않습니다 부정적인 영향을 기타 워크 로드.

경우에 따라 페이지를 매긴 보고서 워크 로드를 사용할 수 없게 될 수 있습니다. 이 경우 워크 로드 관리 포털의 오류 상태를 보여 줍니다. 및 사용자에 게 보고서 렌더링에 대 한 제한 시간을 표시 합니다. 이 문제를 완화 하려면 워크 로드를 사용 하지 않도록 설정 하 고 다시 활성화 합니다.

## <a name="configure-workloads"></a>워크로드 구성

워크로드를 사용할 예정인 경우에만 워크로드를 사용하도록 설정하여 용량의 사용 가능한 리소스를 최대화합니다. 기본 설정이 용량 리소스 요구 사항을 충족하지 않는다고 결정한 경우에만 메모리 설정을 변경합니다.  

### <a name="to-configure-workloads-in-the-power-bi-admin-portal"></a>Power BI 관리 포털에서 워크로드를 구성하려면

1. **용량 설정** > **프리미엄 용량**에서 용량을 선택합니다.

1. **추가 옵션**에서 **워크로드**를 확장합니다.

1. 하나 이상의 워크로드를 사용하도록 설정하고 **최대 메모리** 값을 설정합니다.   

    
    ![워크로드 활성화](media/service-admin-premium-workloads/admin-portal-workloads.png)

1. **적용**을 클릭합니다.

### <a name="rest-api"></a>REST API

[용량](https://docs.microsoft.com/rest/api/power-bi/capacities) REST API를 사용하여 워크로드를 사용하도록 설정하고 용량에 할당할 수 있습니다.

## <a name="monitoring-workloads"></a>워크로드 모니터링

[Power BI Premium 용량 메트릭 앱](service-admin-premium-monitor-capacity.md)은 용량을 사용하도록 설정한 워크로드를 모니터링할 데이터 세트, 데이터 흐름 및 페이지를 매긴 보고서 메트릭을 제공합니다. 

## <a name="next-steps"></a>다음 단계

[Power BI 프리미엄 용량 최적화](service-premium-capacity-optimize.md)     
[데이터 흐름을 사용한 Power BI의 셀프 서비스 데이터 준비](service-dataflows-overview.md)   
[Power BI Premium에서 페이지를 매긴 보고서란?](paginated-reports-report-builder-power-bi.md)   

궁금한 점이 더 있나요? [Power BI 커뮤니티에 문의](http://community.powerbi.com/)