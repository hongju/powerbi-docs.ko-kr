---
title: "Power BI Desktop 시각적 개체의 데이터 및 레코드 참조"
description: "세부 정보로 드릴링하려면 Power BI Desktop의 데이터 참조 및 레코드 참조 기능을 사용합니다."
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
ms.date: 10/09/2017
ms.author: davidi
ms.openlocfilehash: c43ec48d1bd34a5df2578c6cc117dd3e3bbdb64f
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2017
---
# <a name="use-see-data-and-see-records-in-power-bi-desktop"></a>Power BI Desktop에서 데이터 참조 및 레코드 참조 사용
**Power BI Desktop**에서는 시각적 개체의 세부 정보로 드릴링하고 선택한 시각적 개체에 대한 데이터 또는 개별 데이터 요소의 텍스트 표현을 볼 수 있습니다. 이러한 기능을 때로는 *클릭 광고*, *드릴스루* 또는 드릴스루 세부 정보라고 합니다.

**레코드 참조**를 사용하여 시각적 개체에서 선택한 데이터 요소의 기본 행을 보거나 **데이터 참조**를 사용하여 시각적 개체에서 사용되는 값의 텍스트 버전을 볼 수 있습니다. **데이터 참조** 및 **레코드 참조**를 사용하는 데에는 몇 가지 제한 사항이 있으며, 이 문서의 끝 부분에서 설명합니다.

![](media/desktop-see-data-see-records/see-data-see-records_1.png)

## <a name="using-see-data-in-power-bi-desktop"></a>Power BI Desktop에서 데이터 참조 사용
**데이터 참조** 단추는 리본의 **시각적 도구** 섹션에 있는 **데이터/드릴** 탭에 있습니다.

![](media/desktop-see-data-see-records/see-data-see-records_2.png)

또한 시각적 개체를 마우스 오른쪽 단추로 클릭한 다음 표시되는 메뉴에서 **데이터 참조**를 선택하면 **데이터를 참조**할 수도 있습니다.

![](media/desktop-see-data-see-records/see-data-see-records_3.png)

> [!NOTE]
> 마우스 오른쪽 단추 클릭 메뉴를 사용하려면 시각적 개체에서 데이터 요소 위로 마우스를 가져가야 합니다.
> 
> 

**데이터 참조**를 선택하면 **Power BI Desktop**에서 선택한 시각적 개체에 초점을 맞추고 캔버스 공간을 데이터의 시각적 개체 및 텍스트 표현을 표시하는 데 사용합니다. 아래 그림과 같이 시각적 개체는 캔버스의 위쪽 절반에 표시되고, 데이터는 아래쪽 절반에 표시됩니다. 이 보기는 *가로* 보기입니다.

![](media/desktop-see-data-see-records/see-data-see-records_4.png)

오른쪽 위 모서리의 아이콘을 선택하면 *세로 보기*(또는 가로 보기로 돌아가기)로 전환할 수도 있습니다.

![](media/desktop-see-data-see-records/see-data-see-records_5.png)

보고서로 돌아가려면 캔버스의 왼쪽 위 모서리에 있는 **< 보고서로 돌아가기**를 선택합니다.

![](media/desktop-see-data-see-records/see-data-see-records_6.png)

## <a name="using-see-records-in-power-bi-desktop"></a>Power BI Desktop에서 레코드 참조 사용
시각적 개체의 한 데이터 요소에 초점을 맞추고 그 뒤에 있는 데이터로 드릴링할 수 있습니다. 시각적 개체가 선택되었으면 **레코드 참조**를 사용하는 두 가지 방법이 있습니다. **데이터/드릴** 리본에서 **레코드 참조** 토글 단추를 활성화한 다음 데이터 요소를 클릭하거나 데이터 요소를 마우스 오른쪽 단추로 클릭하고 표시되는 메뉴에서 **레코드 참조**를 선택할 수 있습니다.

![](media/desktop-see-data-see-records/see-data-see-records_7.png)

> [!NOTE]
> 선택한 시각적 개체에서 **레코드 참조**를 지원하지 않으면 리본의 단추가 회색으로 표시됩니다.
> 
> 

**레코드 참조**가 선택되었으면 **Power BI Desktop**에서는 해당 개별 데이터 요소에 초점을 맞추고 아래 이미지와 같이 캔버스 영역을 해당 요소의 데이터를 표시하는 데 사용합니다.

![](media/desktop-see-data-see-records/see-data-see-records_8.png)

보고서로 돌아가려면 캔버스의 왼쪽 위 모서리에 있는 **보고서로 돌아가기** 단추를 선택합니다.

## <a name="limitations"></a>제한 사항
**데이터 참조** 또는 **레코드 참조**를 사용할 때는 다음과 같이 고려해야 할 몇 가지 제한 사항이 있습니다.

* 다음과 같은 시각적 유형만 지원됩니다.
  * **막대형**
  * **열**
  * **맵**
  * **트리 맵**
  * **등치 지역도**
  * **원형**
  * **도넛형**
  * **깔때기형**
* 시각적 개체에서 계산된 측정값을 사용할 때는 **레코드 참조**를 사용할 수 없습니다.
* 라이브 다차원(MD) 모델에 연결된 경우 **레코드 참조**를 사용할 수 없습니다.

## <a name="next-steps"></a>다음 단계
**Power BI Desktop**에는 모든 종류의 보고서 서식 및 데이터 관리 기능이 있습니다. 몇 가지 예를 보려면 다음 리소스를 확인하세요.

* [Power BI Desktop에서 그룹화 및 범주화 사용](desktop-grouping-and-binning.md)
* [Power BI Desktop 보고서에서 눈금선, 눈금에 맞춤, z-순서, 맞춤 및 균등 맞춤 사용](desktop-gridlines-snap-to-grid.md)

