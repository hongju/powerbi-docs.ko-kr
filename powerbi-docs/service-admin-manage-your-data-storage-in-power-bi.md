---
title: 작업 영역에서 데이터 스토리지 관리
description: 보고서 및 데이터 세트를 계속 게시할 수 있도록 개인 또는 작업 영역의 데이터 스토리지를 관리하는 방법을 알아보세요.
author: maggiesMSFT
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 01/23/2020
ms.author: maggies
LocalizationGroup: Administration
ms.openlocfilehash: bc8b8c16675e6d413c22d4ae88018222b02b17d6
ms.sourcegitcommit: a1409030a1616027b138128695b80f6843258168
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76709895"
---
# <a name="manage-data-storage-in-power-bi-workspaces"></a>Power BI 작업 영역에서 데이터 스토리지 관리

보고서 및 데이터 세트를 계속 게시할 수 있도록 개인 또는 작업 영역의 데이터 스토리지를 관리하는 방법을 알아보세요.

## <a name="capacity-limits"></a>용량 제한

내 작업 영역 또는 앱 작업 영역에 대한 작업 영역 스토리지 제한은 작업 영역이 [공유 또는 프리미엄 용량](service-basic-concepts.md#capacities)인지에 따라 다릅니다.

### <a name="shared-capacity-limits"></a>공유 용량 제한
공유 용량의 작업 영역: 

- 작업 영역당 스토리지가 10GB로 제한됩니다.
- 앱 작업 영역의 경우 총사용량이 10GB에 테넌트의 Pro 라이선스의 수를 곱한 값을 초과할 수 없습니다.

### <a name="premium-capacity-limits"></a>프리미엄 용량 제한
프리미엄 용량의 작업 영역:
- 프리미엄 용량당 100TB의 제한이 있습니다.
- 사용자별 스토리지 제한은 없습니다.

[Power BI 가격 책정 모델](https://powerbi.microsoft.com/pricing)의 다른 기능에 대해 살펴봅니다.

## <a name="whats-included-in-storage"></a>스토리지에 포함된 내용

데이터 스토리지에는 자체 데이터 세트 및 Excel 보고서와 다른 사용자가 공유하는 이러한 항목이 포함되어 있습니다. 데이터 세트는 업로드하거나 연결된 데이터 원본 중 하나입니다. 이러한 데이터 원본에는 사용 중인 Power BI Desktop 파일과 Excel 통합 문서가 포함됩니다. 다음 사항도 데이터 용량에 포함됩니다.

* 대시보드에 고정된 Excel 범위입니다.
* Power BI 대시보드에 고정된 Reporting Services 온-프레미스 시각화
* 업로드된 이미지

공유하는 대시보드의 크기는 대시보드에 고정된 항목에 따라 달라집니다. 예를 들어, 두 개의 서로 다른 데이터 세트의 일부인 두 개의 보고서에 속하는 항목을 고정하면, 크기에는 두 개의 데이터 세트가 모두 포함됩니다.

<a name="manage"/>

## <a name="manage-items-you-own"></a>소유한 항목 관리

Power BI 계정에서 사용 중인 데이터 스토리지의 규모를 확인하고 계정을 관리합니다.

1. 자체 스토리지를 관리하려면 탐색 창의 **내 작업 영역**으로 이동합니다.
   
    ![내 작업 영역](media/service-admin-manage-your-data-storage-in-power-bi/pbi_myworkspace.png)

2. 오른쪽 위에 있는 ![기어 아이콘](media/service-admin-manage-your-data-storage-in-power-bi/pbi_gearicon.png) \> **개인 스토리지 관리**를 선택합니다.
   
    위쪽 막대는 사용한 스토리지 한도의 크기를 보여줍니다.
   
    ![스토리지 용량 한도 관리](media/service-admin-manage-your-data-storage-in-power-bi/pbi_persnlstorage.png)
   
    데이터 세트 및 보고서는 다음과 같이 두 탭으로 구분됩니다.
   
    **본인이 소유:** Salesforce 및 Dynamics CRM 등과 같은 서비스 데이터 세트를 포함하여 이러한 보고서와 데이터 세트를 Power BI 계정에 업로드하였습니다.  

    **다른 사람 소유:** 다른 사람이 사용자와 공유한 보고서 및 데이터 세트입니다.
1. 데이터 세트 또는 보고서를 삭제하려면 휴지통 아이콘 ![휴지통 아이콘](media/service-admin-manage-your-data-storage-in-power-bi/pbi_deleteicon.png)을 탭합니다.

본인 또는 다른 사용자가 데이터 세트 기반의 보고서 및 대시보드를 보유할 수 있음을 염두에 둡니다. 그런 데이터 세트를 삭제하면 해당 보고서와 대시보드가 더 이상 작동하지 않습니다.

## <a name="manage-your-workspace"></a>작업 영역 관리
1. **작업 영역** 옆에 있는 화살표 \> 작업 영업 이름을 선택합니다.
   
    ![작업 영역 선택](media/service-admin-manage-your-data-storage-in-power-bi/pbi_groupworkspaces.png)
2. 오른쪽 위에 있는 ![기어 아이콘](media/service-admin-manage-your-data-storage-in-power-bi/pbi_gearicon.png) \> **그룹 스토리지 관리**를 선택합니다.
   
    위쪽 막대는 사용한 그룹 스토리지 한도의 크기를 보여줍니다.
   
    ![작업 영역 스토리지 관리](media/service-admin-manage-your-data-storage-in-power-bi/pbi_groupstorage.png)
   
    데이터 세트 및 보고서는 다음과 같이 두 탭으로 구분됩니다.
   
    **우리 소유:** Salesforce 및 Dynamics CRM 등과 같은 서비스 데이터 세트를 포함하여 사용자 또는 누군가가 이러한 보고서와 데이터 세트를 그룹의 Power BI 계정에 업로드하였습니다.

    **다른 사람 소유:** 다른 사람이 그룹과 공유한 보고서 및 데이터 세트입니다.

3. 데이터 세트 또는 보고서를 삭제하려면 휴지통 아이콘 ![휴지통 아이콘](media/service-admin-manage-your-data-storage-in-power-bi/pbi_deleteicon.png)을 탭합니다.
   
   > [!NOTE]
   > 본인 또는 그룹의 누군가가 데이터 세트 기반의 보고서 및 대시보드를 보유할 수 있음을 염두에 둡니다. 그런 데이터 세트를 삭제하면 해당 보고서와 대시보드가 더 이상 작동하지 않습니다.
   
   관리자, 구성원 또는 참가자 역할로 있는 작업 공간의 모든 멤버는 작업 영역에서 데이터 세트 및 보고서를 삭제할 권한이 있습니다.

## <a name="dataset-limits"></a>데이터 세트 제한
Power BI로 가져오는 데이터 세트당 1GB 제한이 있습니다. Excel 환경을 유지하기로 선택한 경우 데이터를 가져오는 대신에 데이터 세트는 250MB로 제한됩니다.

## <a name="what-happens-when-you-reach-a-limit"></a>제한에 도달할 때 발생하는 현상
수행할 수 있는 작업의 데이터 용량 제한에 도달하면 서비스 내에 프롬프트가 표시됩니다. 

기어 아이콘 ![기어 아이콘](media/service-admin-manage-your-data-storage-in-power-bi/pbi_gearicon.png)을 선택할 경우, 데이터 용량 제한을 초과했다는 것을 나타내는 빨간색 막대가 표시됩니다.

![스토리지 제한에 도달함](media/service-admin-manage-your-data-storage-in-power-bi/manage-storage-limit.png)

이 제한은 **개인 스토리지 관리** 안에도 표시됩니다.

 ![개인 스토리지 관리, 스토리지 용량 한도 도달](media/service-admin-manage-your-data-storage-in-power-bi/manage-storage-limit2.png)

 제한 중 하나에 도달하는 작업을 수행하려는 경우 제한을 초과했다는 메시지가 표시됩니다. 스토리지 용량을 줄이고 한도를 초과하도록 스토리지를 [관리](#manage)할 수 있습니다.

 ![스토리지 제한 초과](media/service-admin-manage-your-data-storage-in-power-bi/powerbi-pro-over-limit.png)

 ## <a name="next-steps"></a>다음 단계

 궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](https://community.powerbi.com/)

