---
title: "Power BI에서 조직의 사용자 지정 시각적 개체 사용"
description: "Power BI에서 조직의 사용자 지정 시각적 개체 사용, 관리 및 만들기"
services: powerbi
documentationcenter: 
author: markingmyname
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 02/06/2018
ms.author: maghan
LocalizationGroup: Visualizations
ms.openlocfilehash: 6f7827f7804fcd52e7d922ebc8ffad5a8036b33c
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/24/2018
---
# <a name="using-organization-custom-visuals-in-power-bi-preview"></a>Power BI에서 조직의 사용자 지정 시각적 개체 사용(미리 보기)

Power BI에서 사용자 지정 시각적 개체를 사용하여 사용자에게 맞는 고유한 유형의 시각적 개체를 만들거나 전달하려는 데이터 정보를 만들 수 있습니다. 이러한 사용자 지정 시각적 개체는 일반적으로 개발자가 만들며, Power BI에 포함된 여러 시각적 개체가 요구 사항을 충족하지 못할 때 사용자 지정 시각적 개체를 만듭니다. 

일부 조직에서 사용자 지정 시각적 개체는 조직에 고유한 특정 데이터 또는 정보를 전달하는 데 필요하거나, 특별한 데이터 요구 사항이 있거나, 개인 비즈니스 방법을 강조할 수 있기 때문에 훨씬 더 중요합니다. 이러한 조직은 사용자 지정 시각적 개체를 개발하고, 조직에서 공유하고, 적절하게 관리해야 합니다. Power BI 사용자 지정 시각적 개체(현재 미리 보기로 제공)를 통해 조직은 이러한 작업을 수행할 수 있습니다. 

다음 이미지는 Power BI에서 조직의 사용자 지정 시각적 개체(미리 보기)가 관리자에서 나와 개발 및 유지 관리를 거쳐 마지막으로 데이터 분석까지 흐르는 프로세스를 보여줍니다.

![](media/power-bi-custom-visuals-organizational/custom-visual-org-01.jpg)

## <a name="how-to-enable-organizational-custom-visuals-preview"></a>조직의 사용자 지정 시각적 개체(미리 보기) 사용 방법

조직의 사용자 지정 시각적 개체는 현재 미리 보기로 제공되므로 Power BI Desktop에서 이 기능을 사용하도록 설정해야 합니다. 이 미리 보기 기능을 사용하려면 아래 이미지에 표시된 것처럼 리본에서 [파일] > [옵션 및 설정] > [옵션]을 선택한 다음, 왼쪽 창에서 [미리 보기 기능]을 선택하고 [조직의 사용자 지정 시각적 개체] 옆의 확인란을 선택합니다.

![](media/power-bi-custom-visuals-organizational/custom-visual-org-02.jpg)

조직의 시각적 개체는 관리 포털에서 Power BI 관리자가 배포하고 관리합니다. 조직의 리포지토리에 배포되면 조직의 사용자는 쉽게 검색할 수 있고 조직의 사용자 지정 시각적 개체를 Power BI Desktop에서 바로 보고서로 가져올 수 있습니다.

## <a name="using-organizational-custom-visuals"></a>조직의 사용자 지정 시각적 개체 사용

만든 보고서에서 조직의 사용자 지정 시각적 개체를 사용하는 방법에 대한 자세한 내용은 [조직의 시각적 개체를 보고서로 가져오는 방법에 대한 자세한 정보](power-bi-custom-visuals.md) 문서를 참조하세요.
 
## <a name="administering-organizational-custom-visuals"></a>조직의 사용자 지정 시각적 개체 관리

조직에서 조직의 사용자 지정 시각적 개체를 관리하고 배포하는 방법에 대한 자세한 내용은 [조직의 사용자 지정 시각적 개체 배포 및 관리에 대한 자세한 정보](https://go.microsoft.com/fwlink/?linkid=866790) 문서를 참조하세요.

> [!WARNING]
> 사용자 지정 시각적 개체에는 보안 또는 개인 정보 위험이 있는 코드가 포함될 수 있습니다. 조직의 리포지토리에 배포하기 전에 사용자 지정 시각적 개체의 작성자와 원본을 신뢰할 수 있는지 확인하세요. 
> 

## <a name="considerations-and-limitations"></a>고려 사항 및 제한 사항
 
조직의 사용자 지정 시각적 개체는 미리 보기로 제공되므로 알고 있고 주의해야 할 몇 가지 고려 사항과 제한 사항이 있습니다.
 
관리자:

* 레거시 사용자 지정 시각적 개체(예: 새 버전의 API를 기반으로 빌드된 사용자 지정 시각적 개체)는 지원되지 않습니다.

* 현재 위치(In-place) 업데이트가 아직 지원되지 않습니다. 시각적 개체를 업데이트하려면 새 버전의 시각적 개체를 조직의 리포지토리에 업로드해야 합니다. PBIVIZ 파일에 동일한 시각적 개체 ID가 있는지도 확인해야 합니다. 그런 다음, 보고서 작성자는 새 버전을 보고서에 가져올 수 있으며 보고서에 있는 현재 버전의 시각적 개체를 현재 위치에서(In-place) 바꿀 수 있습니다.

* 리포지토리에서 사용자 지정 시각적 개체를 삭제하면 삭제된 시각적 개체를 사용하는 기존 보고서는 렌더링을 중지합니다. 리포지토리에서 삭제 작업은 되돌릴 수 없습니다.
 
최종 사용자:

* 공개 마켓플레이스(AppSource)와 조직의 리포지토리에서 동일한 시각적 개체(동일한 시각적 개체 ID) 사용은 지원되지 않습니다. 이 경우 가져온 최신 시각적 개체가 사용됩니다.

* 대시보드 및 보고서에 있는 조직의 시각적 개체의 외부 공유가 지원되지 않습니다. 조직의 사용자 지정 시각적 개체가 포함된 대시보드를 보는 조직 외부의 사용자에게는 비어 있는 시각적 개체가 표시됩니다. 

* Power BI 작업 영역 컬렉션은 조직의 시각적 개체에 대해 지원되지 않습니다.

* 웹에 게시된 보고서에 있는 조직의 사용자 지정 시각적 개체는 렌더링되지 않습니다.

* 조직의 리포지토리를 통해 배포된 경우 AppSource 마켓플레이스의 Visio 시각적 개체, PowerApps 시각적 개체 및 GlobeMap 시각적 개체는 렌더링되지 않습니다.

* 관리자가 리포지토리에서 사용자 지정 시각적 개체를 삭제하고 해당 시각적 개체가 보고서에 사용되는 경우, 시각적 개체는 렌더링을 중지하며, 보고서를 저장하려면 해당 시각적 개체를 보고서에서 제거해야 합니다.