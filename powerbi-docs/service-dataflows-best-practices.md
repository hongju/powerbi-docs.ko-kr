---
title: Power BI 데이터 흐름에 관한 모범 사례
description: Power BI 데이터 흐름에 관한 모범 사례
author: mohaali
manager: mohaali
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 09/19/2019
ms.author: davidi
LocalizationGroup: Data from files
ms.openlocfilehash: c499a83b87eb15031d75974084468f418a17804a
ms.sourcegitcommit: 200291eac5769549ba5c47ef3951e2f3d094426e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/19/2019
ms.locfileid: "71142303"
---
# <a name="dataflows-best-practice"></a>데이터 흐름 모범 사례

이 문서에서는 Power BI 데이터 흐름 디자인에 대한 모범 사례를 제공합니다. 이 지침을 사용하여 데이터 흐름를 만드는 방법을 알아보고 고유한 데이터 흐름에 이러한 사례를 적용할 수 있습니다.

> [!NOTE]
> 이 문서의 권장 사항은 지침입니다. 이 문서에 나오는 각 모범 사례에 대해 정당한 사유도 함께 제공될 수 있습니다. 
> 
> 

### <a name="split-ingestion-and-transformation-to-use-the-enhanced-compute-engine"></a>향상된 컴퓨팅 엔진을 사용하기 위한 수집 및 변환 분할

데이터 흐름를 만들 때 모든 엔터티, 변환, 조인 및 향상된 기능을 포함하는 단일 데이터 흐름을 한곳에서 만들 수 있습니다. 좀 더 작은 데이터 세트의 경우 단일 데이터 흐름이 효과적일 수 있습니다. 하지만 더 큰 데이터 볼륨을 처리할 때는 조인이나 특정 변환을 수행할 경우 제한 또는 메모리 한계가 발생할 수 있습니다. 이러한 문제를 해결하기 위해 훨씬 더 큰 데이터 볼륨으로 확장되는 향상된 엔진이 Power BI Premium 사용자를 위해 릴리스되었습니다. 향상된 컴퓨팅 엔진은 연결된 엔터티 또는 계산된 엔터티에만 작동하므로 수집을 위한 별도의 데이터 흐름을 만들고 복잡한 모든 병합 및 변환을 수행하는 연결된 데이터 흐름을 만들어 향상된 엔진의 이점을 누릴 수 있습니다.

데이터 흐름을 분할하는 경우도 새로 고침 문제를 진단하고 디버그하는 데 유용합니다. 한도가 제한된 원본으로 작업할 때 특히 유용합니다.

### <a name="perform-actions-that-can-use-the-enhanced-compute-engine"></a>향상된 컴퓨팅 엔진을 사용할 수 있는 작업 수행

다른 유형의 변환을 수행하기 전에 계산된 엔터티에서 먼저 조인 및 필터 변환을 수행하도록 하여 향상된 컴퓨팅 엔진을 활용합니다.

### <a name="split-dataflows-when-connecting-to-sharepoint"></a>SharePoint에 연결할 때 데이터 흐름 분할

SharePoint를 사용하고 여러 파일에 연결하는 경우 간헐적으로 오류가 발생할 수 있습니다. SharePoint의 제한 때문에 안정적인 대응 능력을 유지해야 합니다. 따라서, SharePoint에서 Excel 파일에 연결하는 경우 단일 데이터 흐름에서 모든 파일을 다운로드하려고 할 수 있습니다. 20개 이상의 파일을 다운로드하는 경우 새로 고침 부하를 분할하고 SharePoint 제한을 극복하기 위해 두 개의 데이터 흐름를 만듭니다.

### <a name="avoid-scheduling-refresh-for-linked-entities-inside-the-same-workspace"></a>동일한 작업 영역 내의 연결된 엔터티에 대한 새로 고침 예약 방지

연결된 엔터티를 포함하는 데이터 흐름이 정기적으로 잠기는 경우 데이터 흐름을 새로 고치는 동안 동일한 작업 영역 내의 종속된 데이터 흐름이 잠겨질 수 있습니다. 이러한 잠금은 트랜잭션 정확도를 제공하고 데이터 흐름를 성공적으로 새로 고쳐지도록 하지만 사용자가 편집하지 못하도록 차단할 수 있습니다. 

연결된 데이터 흐름에 대해 별도의 일정을 설정하는 경우 데이터 흐름이 불필요하게 새로 고쳐지고 데이터 흐름을 편집하지 못하도록 차단할 수 있습니다. 이 문제를 방지하기 위한 다음과 같은 두 가지 권장 사항이 있습니다. 

* 원본 데이터 흐름과 동일한 작업 영역에서 연결된 데이터 흐름에 대한 새로 고침 일정을 설정하지 않도록 방지
* 새로 고침 일정을 개별적으로 구성하고 잠금 동작을 방지하려는 경우 데이터 흐름을 별도의 작업 영역으로 구분합니다.

### <a name="create-a-separate-workspace-for-ingestion-transformation"></a>수집, 변환에 대해 별도의 작업 영역 만들기

기본 원본 시스템의 원시 데이터에 대한 액세스를 허용하지 않고 많은 사용자에게 기본 데이터 흐름 데이터에 대한 액세스 권한을 제공하려면 공유해야 하는 모든 데이터를 포함하는 별도의 작업 영역을 만들고 사용 권한을 할당합니다. 개별 데이터 흐름 권한은 현재 지원되지 않습니다.

### <a name="ensure-capacity-is-in-the-same-region"></a>용량이 동일한 지역에 있는지 확인

데이터 흐름은 현재 다중 지역을 지원하지 않습니다. 프리미엄 용량은 Power BI 테넌트와 동일한 지역에 있어야 합니다.

### <a name="separate-on-premises-sources-from-cloud-sources"></a>클라우드 원본에서 온-프레미스 원본 분리

앞에서 설명한 모범 사례 외에도 온-프레미스, 클라우드, SQL Server, Spark, Dynamics 등의 각 원본 유형에 대해 별도의 데이터 흐름을 만들 수 있습니다. 데이터 원본 유형에 따라 데이터 흐름을 분할하는 것이 좋습니다. 이러한 원본 유형별 분리를 통해 문제를 더 빠르게 해결할 수 있으며, 데이터 흐름를 새로 고칠 때 내부 제한을 방지할 수 있습니다.

### <a name="separate-dataflows-into-a-separate-capacity"></a>데이터 흐름을 별도의 용량으로 구분

한도 제한이 발생하거나, 용량의 메모리 제한으로 인해 데이터 흐름에서 정기적으로 오류가 발생하는 경우 데이터 흐름를 분리하거나 추가 메모리를 위해 프리미엄 용량을 확장하는 것이 좋습니다.

## <a name="next-steps"></a>다음 단계

이 문서에는 데이터 흐름에 관한 모범 사례 정보가 제공되어 있습니다. 다음 문서도 데이터 흐름에 대한 자세한 내용을 알아보는 데 유용할 수 있습니다.

* [데이터 흐름을 사용하여 셀프 서비스 데이터 준비](service-dataflows-overview.md)
* [Power BI에서 데이터 흐름 만들기 및 사용](service-dataflows-create-use.md)
* [Power BI Premium의 계산된 엔터티 사용](service-dataflows-computed-entities-premium.md)
* [온-프레미스 데이터 원본으로 만든 데이터 흐름 사용](service-dataflows-on-premises-gateways.md)

CDM 개발 및 자습서 리소스에 대한 내용은 다음을 참조하세요.
* [공통 데이터 모델 - 개요 ](https://docs.microsoft.com/powerapps/common-data-model/overview)
* [CDM 폴더](https://go.microsoft.com/fwlink/?linkid=2045304)
* [CDM 모델 파일 정의](https://go.microsoft.com/fwlink/?linkid=2045521)


파워 쿼리 및 예약된 새로 고침에 대한 자세한 내용은 다음 문서를 참조하세요.
* [Power BI Desktop을 사용한 쿼리 개요](desktop-query-overview.md)
* [예약된 새로 고침 구성](refresh-scheduled-refresh.md)
