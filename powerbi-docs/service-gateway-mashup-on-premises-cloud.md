---
title: 온-프레미스 및 클라우드 데이터 원본 병합 또는 추가
description: 온-프레미스 데이터 게이트웨이를 사용하여 동일한 쿼리에서 온-프레미스 및 클라우드 데이터 원본을 병합하거나 추가합니다.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-gateways
ms.topic: conceptual
ms.date: 06/06/2018
ms.author: mblythe
LocalizationGroup: Gateways
ms.openlocfilehash: 3550a3fc0cfc51b61e1d7e51a50c2a36325f2388
ms.sourcegitcommit: 49570ab8f5b5cd5bab4cd388f4281b1372bcb80b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2018
ms.locfileid: "35250658"
---
# <a name="merge-or-append-on-premises-and-cloud-data-sources"></a>온-프레미스 및 클라우드 데이터 원본 병합 또는 추가

온-프레미스 데이터 게이트웨이를 사용하여 동일한 쿼리에서 온-프레미스 및 클라우드 데이터 원본을 병합하거나 추가할 수 있습니다. 이것은 별도의 쿼리를 사용하지 않고 여러 소스의 데이터를 매시업하려고 할 때 유용합니다.

## <a name="prerequisites"></a>필수 조건

- 로컬 컴퓨터에 [게이트웨이가 설치되었습니다](service-gateway-install.md).
- 온-프레미스 및 클라우드 데이터 원본을 결합하는 쿼리가 포함된 Power BI Desktop 파일입니다.

1. Power BI 서비스의 오른쪽 위 모서리에서 기어 아이콘 ![설정 기어 아이콘](media/service-gateway-mashup-on-premises-cloud/icon-gear.png) > **게이트웨이 관리**를 선택합니다.

    ![게이트웨이 관리](media/service-gateway-mashup-on-premises-cloud/manage-gateways.png)

2. 구성할 게이트웨이를 선택합니다.

3. **게이트웨이 클러스터 설정**에서 **사용자의 클라우드 데이터 원본이 이 게이트웨이 클러스터를 통해 새로 고치도록 허용** > **적용**을 선택합니다.

    ![이 게이트웨이 클러스터를 통해 새로 고침](media/service-gateway-mashup-on-premises-cloud/refresh-gateway-cluster.png)

4. 이 게이트웨이 클러스터 아래에서 쿼리에 사용된 모든 [온-프레미스 데이터 원본](service-gateway-enterprise-manage-scheduled-refresh.md#add-a-data-source)을 추가합니다. 여기에 클라우드 데이터 원본을 추가할 필요가 없습니다.

4. 온-프레미스 및 클라우드 데이터 원본을 결합한 쿼리로 Power BI Desktop 파일을 Power BI 서비스에 업로드합니다.

5. 새 데이터 집합의 **데이터 집합 설정** 페이지에서 다음을 수행합니다.

    - 온-프레미스 원본의 경우 이 데이터 원본과 연결된 게이트웨이를 선택합니다.

    - **데이터 원본 자격 증명**에서 필요에 따라 클라우드 데이터 원본 자격 증명을 편집합니다.

    ![데이터 집합 설정](media/service-gateway-mashup-on-premises-cloud/dataset-settings.png)

6. 클라우드 자격 증명을 설정하면 이제 **지금 새로 고침** 옵션을 사용하여 데이터 집합을 새로 고치거나 정기적으로 새로 고치도록 예약할 수 있습니다.


## <a name="next-steps"></a>다음 단계

게이트웨이에 대해 데이터 새로 고침에 대한 자세한 내용은 [예약된 새로 고침을 위해 데이터 원본 사용](service-gateway-enterprise-manage-scheduled-refresh.md#using-the-data-source-for-scheduled-refresh)을 참조하세요.