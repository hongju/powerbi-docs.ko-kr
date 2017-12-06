---
title: "Power BI Desktop에서 드릴스루 사용"
description: "Power BI Desktop의 새 보고서 페이지에서 데이터를 드릴다운하는 방법을 알아봅니다."
services: powerbi
documentationcenter: 
author: davidiseminger
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
ms.date: 12/06/2017
ms.author: davidi
ms.openlocfilehash: e4655326b731c118265003ba1f530c5c62ac8bfa
ms.sourcegitcommit: d91436de68a0e833ecff18d976de9d9431bc4121
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/06/2017
---
# <a name="use-drillthrough-in-power-bi-desktop"></a>Power BI Desktop에서 드릴스루 사용
**Power BI Desktop**의 **드릴스루**를 사용하여 공급 업체, 고객 또는 제조업체와 같이 특정 엔터티에 초점을 맞춘 보고서의 페이지를 만들 수 있습니다. 사용자가 해당 보고서 페이지를 사용하여 다른 보고서 페이지에서 데이터 요소를 마우스 오른쪽 단추로 클릭하고 해당 페이지에는 드릴스루하여 해당 컨텍스트로 필터링된 세부 정보를 가져올 수 있습니다.

![](media/desktop-drillthrough/drillthrough_01.png)

## <a name="using-drillthrough"></a>드릴스루 사용
**드릴스루**를 사용하려면 드릴스루를 제공할 엔터티 형식을 확인하려는 시각적 개체가 있는 보고서 페이지를 만듭니다. 예를 들어 제조업체에 대한 드릴스루를 제공하려는 경우 총 판매액, 배송된 총 단위, 범주별 판매액, 지역별 판매액 등을 보여주는 시각적 개체가 포함된 드릴스루 페이지를 만들 수 있습니다. 이런 방식으로 해당 페이지에 드릴스루하는 경우 시각적 개체는 드릴스루하기 위해 클릭하고 선택한 제조업체에 따라 다릅니다.

드릴스루 페이지에 있는 **시각화** 창의 **필드** 섹션에서 드릴스루하려는 필드를 **드릴스루 필터** 웰에 끌어옵니다.

![](media/desktop-drillthrough/drillthrough_02.png)

필드를 **드릴스루 필터** 웹에 추가하는 경우 **Power BI Desktop**은 *뒤로* 시각적 단추를 자동으로 만듭니다. 해당 시각적 개체는 게시된 보고서에서 단추로 표시되고 **Power BI 서비스**에서 보고서를 사용하는 사용자가 쉽게 출처(드릴스루하기 위해 선택한 페이지)에서 보고서 페이지로 돌아올 수 있게 합니다.

![](media/desktop-drillthrough/drillthrough_03.png)

*뒤로* 단추가 이미지이므로 원하는 어떤 이미지로 해당 시각적 개체의 이미지를 바꿀 수 있습니다. 또한 단추를 사용하여 보고서 소비자가 원래 페이지로 돌아오기만 하면 계속 정상적으로 작동합니다. 뒤로 단추에 고유한 이미지를 사용하려면 드릴스루 페이지에서 이미지 시각적 개체를 배치하고, 시각적 개체를 선택하고, *뒤로 단추* 슬라이더를 위에 배치합니다. 그러면 이미지 함수는 *뒤로* 단추가 됩니다.

![](media/desktop-drillthrough/drillthrough_05.png)

**드릴스루** 페이지가 완료되면 드릴스루 페이지에서 **드릴스루 필터** 웰에 배치한 필드를 사용하는 보고서에서 사용자가 데이터 요소를 마우스 오른쪽 단추로 클릭하는 경우 상황에 맞는 메뉴가 나타나고 해당 페이지에 사용자를 드릴스루하게 됩니다.

![](media/desktop-drillthrough/drillthrough_04.png)

드릴스루를 선택하는 경우 페이지가 필터링되어 마우스 오른쪽 단추로 클릭한 데이터 요소에 대한 정보를 표시합니다. 예를 들어 Contoso(제조업체)에 대한 데이터 요소를 마우스 오른쪽 단추로 클릭하고 드릴스루를 선택한 경우 사용한 드릴스루 페이지는 Contoso로 필터링됩니다.

> [!NOTE]
> **드릴스루 필터** 웰에 있는 필드만이 드릴스루 보고서 페이지에 전달됩니다. 다른 컨텍스트 정보를 전달하지 않습니다.
> 
> 

보고서에서 **드릴스루**를 사용하기 위한 단계는 여기까지입니다. 드릴스루 필터에 선택한 엔터티 정보에 대한 확장된 보기를 가져오는 것이 좋습니다.

