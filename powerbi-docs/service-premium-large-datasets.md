---
title: 대형 데이터 집합을 위한 Power BI 프리미엄 지원
description: Power BI 프리미엄은 이제 최대 10GB의 데이터 집합을 지원합니다.
author: jocaplan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 10/18/2018
ms.author: jocaplan
LocalizationGroup: Premium
ms.openlocfilehash: 0449d7953b5cefb4c76d89f05ec5b3fa70e9c0da
ms.sourcegitcommit: a739a99e1006834a0f56e387c0bd9d945fb8a76b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2018
ms.locfileid: "51679388"
---
# <a name="power-bi-premium-support-for-large-datasets"></a>대형 데이터 집합을 위한 Power BI 프리미엄 지원

Power BI 프리미엄은 최대 10GB 크기의 Power BI Desktop(.pbix) 파일 업로드를 지원합니다. 업로드한 후에는 데이터 집합 크기를 최대 12GB까지 새로 고칠 수 있습니다. 큰 데이터 집합을 사용하려면 프리미엄 용량에 할당된 작업 영역에 게시합니다.
 
## <a name="best-practices"></a>모범 사례

이 섹션에서는 큰 데이터 집합을 사용한 작업에 대한 모범 사례를 설명합니다.

**대규모 모델은 리소스 용량을 매우 많이 사용할 수 있습니다**. 1GB 보다 큰 모델에는 최소 P1 SKU를 사용하는 것이 좋습니다. A3까지 A SKU가 지원하는 작업 영역에 대형 모델을 게시하는 것이 효과적일 수 있지만 새로 고치는 작업은 가능하지 않습니다.

다음 표에는 다양한 .pbix 크기에 대한 권장 SKU를 설명합니다.

   |SKU  |.pbix의 크기   |
   |---------|---------|
   |P1    | < 3GB        |
   |P2    | < 6GB        |
   |P3, P4, P5    | 최대 10GB   |

Power BI Embedded A4 SKU는 P1 SKU, A5 = P2 및 A6 = P3과 같습니다. 대형 모델을 A 및 EM SKU에 게시하면 공유 용량의 모델 크기 제한 오류와 관련이 없는 오류가 반환될 수 있습니다. A 및 EM SKU의 대형 모델에 대한 새로 고침 오류로 인해 시간 초과를 가리킬 가능성이 높습니다. 이러한 시나리오에 대한 오류 메시지를 개선하기 위해 노력하고 있습니다.

**.pbix 파일은 고도로 압축된 상태의 데이터를 나타냅니다**. 데이터는 메모리에 로드될 때 여러 번 확장할 가능성이 있으며, 거기서부터 데이터 새로 고침 중 여러 번 더 확장할 수도 있습니다.

**큰 데이터 집합의 예정된 새로 고침에는 시간이 오래 걸리고** 리소스를 매우 많이 사용할 수 있습니다. 따라서 너무 많은 겹치는 새로 고침은 예약하지 마십시오. 예약된 새로 고침 작업에 대한 제한 시간은 이 용량에서 모든 데이터 집합에 두 배인 4시간이 되었음을 확인할 수 있습니다. [증분 새로 고침](service-premium-incremental-refresh.md)을 사용하는 것이 좋습니다. 더 빠르고, 더 안정적이며, 리소스 소모가 더 적기 때문입니다.

**큰 데이터 집합의 초기 보고서 로드에는 시간이 오래 걸릴 수 있습니다**. 데이터 집합을 마지막으로 사용한 후 시간이 꽤 지난 경우 모델이 프리미엄 용량의 메모리에 로드되기 때문입니다. 로딩 시간이 더 긴 보고서의 로딩 표시줄에 로드 진행률이 표시됩니다.

**프리미엄 용량에서 작업 영역을 제거하는 경우** 모델 및 관련된 모든 보고서 및 대시보드는 작동하지 않게 됩니다.

**쿼리당 메모리 및 시간 제약 조건은 프리미엄 용량에서 훨씬 더 높긴 하지만**, 필터 및 슬라이서를 사용하여 필요한 것만 표시하도록 시각적 개체를 제한하는 것이 가장 좋습니다.

**다음 단계**

[Power BI Premium이란?](service-premium.md)
[Power BI Premium 릴리스 정보](service-premium-release-notes.md)
[Microsoft Power BI Premium 백서](https://aka.ms/pbipremiumwhitepaper)
[Power BI Enterprise 배포 계획 백서](https://aka.ms/pbienterprisedeploy)

궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](https://community.powerbi.com/)
