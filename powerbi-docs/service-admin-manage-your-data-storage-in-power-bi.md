---
title: 작업 영역에서 데이터 스토리지 관리
description: 보고서 및 데이터 세트를 계속 게시할 수 있도록 개인 또는 앱 작업 영역에서 데이터 스토리지를 관리하는 방법을 알아봅니다.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 12/21/2018
ms.author: maggies
LocalizationGroup: Administration
ms.openlocfilehash: e1f1a8fdc5094fd13fc2894d9728951d9f6bde96
ms.sourcegitcommit: 5206651c12f2b91a368f509470b46f3f4c5641e6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53983557"
---
# <a name="manage-data-storage-in-power-bi-workspaces"></a>Power BI 작업 영역에서 데이터 스토리지 관리

보고서 및 데이터 세트를 계속 게시할 수 있도록 개인 또는 앱 작업 영역에서 데이터 스토리지를 관리하는 방법을 알아봅니다.

사용자 및 앱 작업 영역에는 자체 데이터 용량이 있습니다.

* 모든 사용자는 최대 10GB의 데이터 스토리지를 가지고 있습니다.
* Power BI Pro 라이선스가 있는 사용자는 각각 최대 10GB의 데이터 스토리지가 있는 앱 작업 영역을 만들 수 있습니다.
* 프리미엄 용량의 앱 작업 영역은 Power BI Pro 사용자의 스토리지에 포함되지 않습니다.

테넌트 수준에서 테넌트의 모든 Pro 사용자 및 앱 작업 영역에 대해 Pro 사용자 1인당 총 사용량은 10GB를 초과할 수 없습니다.

[Power BI 가격 책정 모델](https://powerbi.microsoft.com/pricing)의 다른 기능에 대해 살펴봅니다.

데이터 스토리지에는 자체 데이터 세트 및 Excel 보고서와 다른 사용자가 공유하는 이러한 항목이 포함되어 있습니다. 데이터 세트는 업로드하거나 연결된 데이터 원본 중 하나입니다. 이러한 데이터 원본에는 사용 중인 Power BI Desktop 파일과 Excel 통합 문서가 포함됩니다. 다음 사항도 데이터 용량에 포함됩니다.

* 대시보드에 고정된 Excel 범위
* Power BI 대시보드에 고정된 Reporting Services 온-프레미스 시각화
* 업로드된 이미지

공유하는 대시보드의 크기는 대시보드에 고정된 항목에 따라 달라집니다. 예를 들어, 두 개의 서로 다른 데이터 세트의 일부인 두 개의 보고서에 속하는 항목을 고정하면, 크기에는 두 개의 데이터 세트가 모두 포함됩니다.

<a name="manage"/>

## <a name="manage-items-you-own"></a>소유한 항목 관리

Power BI 계정에서 사용 중인 데이터 저장소의 규모를 확인하고 계정을 관리합니다.

1. 자체 저장소를 관리하려면 왼쪽 탐색 창의 **내 작업 영역**으로 이동합니다.
   
    ![내 작업 영역](media/service-admin-manage-your-data-storage-in-power-bi/pbi_myworkspace.png)
2. 오른쪽 위 모서리에서 ![기어 아이콘](media/service-admin-manage-your-data-storage-in-power-bi/pbi_gearicon.png)을 선택한 후\> **개인 스토리지 관리**를 선택합니다.
   
    위쪽 막대는 사용한 저장소 한도의 크기를 보여줍니다.
   
    ![스토리지 용량 한도 관리](media/service-admin-manage-your-data-storage-in-power-bi/pbi_persnlstorage.png)
   
    데이터 세트 및 보고서는 다음과 같이 두 탭으로 구분됩니다.
   
    **본인이 소유:** Salesforce 및 Dynamics CRM 등과 같은 서비스 데이터 세트를 포함하여 이러한 보고서와 데이터 세트를 Power BI 계정에 업로드하였습니다.  
    **다른 사람 소유:** 다른 사람이 사용자와 공유한 보고서 및 데이터 세트입니다.
1. 데이터 세트 또는 보고서를 삭제하려면 휴지통 아이콘을 선택합니다. ![휴지통 아이콘](media/service-admin-manage-your-data-storage-in-power-bi/pbi_deleteicon.png).

본인 또는 다른 사용자가 데이터 세트 기반의 보고서 및 대시보드를 보유할 수 있음을 염두에 둡니다. 그런 데이터 세트를 삭제하면 해당 보고서와 대시보드가 더 이상 작동하지 않습니다.

## <a name="manage-your-app-workspace"></a>앱 작업 영역 관리
1. **작업 영역** \> 옆의 화살표를 선택하고 앱 작업 영업 이름을 선택합니다.
   
    ![앱 작업 영역 선택](media/service-admin-manage-your-data-storage-in-power-bi/pbi_groupworkspaces.png)
2. 오른쪽 위 모서리에서 ![기어 아이콘](media/service-admin-manage-your-data-storage-in-power-bi/pbi_gearicon.png)을 선택한 후\> **그룹 스토리지 관리**를 선택합니다.
   
    위쪽 막대는 사용한 그룹 저장소 한도의 크기를 보여줍니다.
   
    ![앱 작업 영역 스토리지 관리](media/service-admin-manage-your-data-storage-in-power-bi/pbi_groupstorage.png)
   
    데이터 세트 및 보고서는 다음과 같이 두 탭으로 구분됩니다.
   
    **우리 소유:** Salesforce 및 Dynamics CRM 등과 같은 서비스 데이터 세트를 포함하여 사용자 또는 누군가가 이러한 보고서와 데이터 세트를 그룹의 Power BI 계정에 업로드하였습니다.
    **다른 사람 소유:** 다른 사람이 그룹과 공유한 보고서 및 데이터 세트입니다.
3. 데이터 세트 또는 보고서를 삭제하려면 휴지통 아이콘을 선택합니다. ![휴지통 아이콘](media/service-admin-manage-your-data-storage-in-power-bi/pbi_deleteicon.png).
   
   > [!NOTE]
   > 앱 작업 공간의 편집 권한이 있는 모든 멤버에게는 앱 작업 영역에서 데이터 세트와 보고서를 삭제하는 권한이 있습니다.
   > 
   > 

본인 또는 그룹의 누군가가 데이터 세트 기반의 보고서 및 대시보드를 보유할 수 있음을 염두에 둡니다. 그런 데이터 세트를 삭제하면 해당 보고서와 대시보드가 더 이상 작동하지 않습니다.

## <a name="dataset-limits"></a>데이터 세트 제한
Power BI로 가져오는 데이터 세트당 1GB 제한이 있습니다. Excel 환경을 유지하기로 선택한 경우 데이터를 가져오는 대신에 데이터 세트는 250MB로 제한됩니다.

## <a name="what-happens-when-you-reach-a-limit"></a>제한에 도달할 때 발생하는 현상
수행할 수 있는 작업의 데이터 용량 제한에 도달하면 서비스 내에 프롬프트가 표시됩니다. 

기어 아이콘 ![기어 아이콘](media/service-admin-manage-your-data-storage-in-power-bi/pbi_gearicon.png)데이터 용량 제한을 초과했다는 것을 나타내는 빨간색 막대가 표시됩니다.

![스토리지 제한에 도달함](media/service-admin-manage-your-data-storage-in-power-bi/manage-storage-limit.png)

이 제한은 **개인 스토리지 관리** 안에도 표시됩니다.

 ![개인 스토리지 관리, 스토리지 용량 한도 도달](media/service-admin-manage-your-data-storage-in-power-bi/manage-storage-limit2.png)

 제한 중 하나에 도달하는 작업을 수행하려는 경우 제한을 초과했다는 메시지가 표시됩니다. 스토리지 용량을 줄이고 한도를 초과하도록 스토리지를 [관리](#manage)할 수 있습니다.

 ![저장소 제한 초과](media/service-admin-manage-your-data-storage-in-power-bi/powerbi-pro-over-limit.png)

 궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](http://community.powerbi.com/)

