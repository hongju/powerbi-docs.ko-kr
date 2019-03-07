---
title: Power BI Premium의 워크로드를 구성하는 방법
description: Power BI Premium 용량의 워크로드를 구성하는 방법을 알아봅니다.
author: minewiskan
ms.author: owend
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 02/26/2019
LocalizationGroup: Premium
ms.openlocfilehash: 5b9bec67fef672d219b11bf3b3750959e72410b6
ms.sourcegitcommit: 364ffa1178cdfb0a20acffc0fd79922ebc892d72
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57226069"
---
# <a name="configure-workloads-in-a-premium-capacity"></a>프리미엄 용량에서 워크로드 구성

이 문서에서는 Power BI Premium 용량에 대한 워크로드를 사용하도록 설정하고 구성하는 방법을 설명합니다. 기본적으로 용량은 Power BI 쿼리 실행과 관련된 워크로드만 지원합니다. 쿼리 워크로드는 프리미엄 용량 SKU에 의해 결정되는 리소스에 최적화되며 제한됩니다. 또한 프리미엄 용량은 용량 리소스를 사용할 수 있는 추가 워크로드를 지원합니다.

## <a name="configure-workloads"></a>워크로드 구성

[데이터 흐름](service-dataflows-overview.md#dataflow-capabilities-on-power-bi-premium) 및 [페이지를 매긴 보고서](paginated-reports-save-to-power-bi-service.md)에 대해 추가 워크로드를 사용하도록 설정하고 구성할 수 있습니다. 이러한 워크로드에 대한 기본 메모리 값은 SKU에 사용 가능한 용량 노드를 기반으로 합니다. 최대 메모리 설정은 누적되지 않습니다. 지정된 최댓값까지의 메모리는 데이터 흐름에 대해 동적으로 할당되지만, 페이지를 매긴 보고서에 대해서는 정적으로 할당됩니다. 

### <a name="to-configure-workloads-in-the-power-bi-admin-portal"></a>Power BI 관리 포털에서 워크로드를 구성하려면

1. **용량 설정** > **프리미엄 용량**에서 용량을 선택합니다.

1. **추가 옵션**에서 **워크로드**를 확장합니다.

1. 하나 이상의 워크로드를 사용하도록 설정하고 **최대 메모리** 값을 설정합니다.   

    
    ![워크로드 활성화](media/service-admin-premium-workloads/admin-portal-workloads.png)

1. **적용**을 클릭합니다.

> [!NOTE]
> 페이지를 매긴 보고서 워크로드를 사용하도록 설정한 경우 페이지를 매긴 보고서를 통해 콘텐츠에 따라 텍스트 색상을 동적으로 변경하는 경우와 같이 보고서를 렌더링할 때 고유의 코드를 실행할 수 있습니다. Power BI Premium 용량은 용량 내 포함된 공간에서 페이지를 매긴 보고서를 실행합니다. 워크로드가 활성 상태인지 여부와 관계없이 사용자가 이 공간에 지정하는 최대 메모리가 사용됩니다. 동일한 용량에서 Power BI 보고서 또는 데이터 흐름을 사용하는 경우 다른 워크로드에 부정적인 영향을 미치지 않도록 페이지를 매긴 보고서에 충분히 작은 메모리를 설정해야 합니다. 드물지만 페이지를 매긴 보고서 워크로드를 사용할 수 없는 경우가 있습니다. 이런 경우 워크로드에서 관리 포털에 오류 상태를 표시하며 사용자에게는 보고서 렌더링 제한 시간이 표시됩니다. 이 문제를 해결하려면 워크로드를 사용하지 않도록 설정한 다음, 다시 사용하도록 설정하세요.


### <a name="rest-api"></a>REST API

[용량](https://docs.microsoft.com/rest/api/power-bi/capacities) REST API를 사용하여 워크로드를 사용하도록 설정하고 용량에 할당할 수 있습니다.


## <a name="next-steps"></a>다음 단계

[Power BI Premium 용량 리소스 관리 및 최적화](service-premium-understand-how-it-works.md)   
[데이터 흐름을 사용한 Power BI의 셀프 서비스 데이터 준비](service-dataflows-overview.md)   
[Power BI Premium에서 페이지를 매긴 보고서란?](paginated-reports-report-builder-power-bi.md)   

궁금한 점이 더 있나요? [Power BI 커뮤니티에 문의](http://community.powerbi.com/)