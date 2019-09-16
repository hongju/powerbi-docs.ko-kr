---
title: Power BI Desktop의 보고서 요소 성능을 검사하기 위해 성능 분석기 사용
description: 시각적 개체 및 보고서 요소가 리소스 사용량 및 응답성 측면에서 수행하는 방법을 알아봅니다.
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/15/2019
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 1851e0a55bf01073a6591f64de43830a72eca89b
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "65854416"
---
# <a name="use-performance-analyzer-to-examine-report-element-performance"></a>성능 분석기를 사용하여 보고서 요소 성능 검사

**Power BI Desktop**에서 시각적 요소와 DAX 수식과 같은 각 보고서 요소가 수행하는 방법을 찾을 수 있습니다. **성능 분석기**를 사용하여, 사용자가 상호 작용하는 경우 각 보고서 요소가 어떻게 수행되는지, 그리고 그 수행의 어떤 측면이 리소스를 가장 많이 사용하는지 측정하는 로그를 기록하고 확인할 수 있습니다.

![성능 분석기](media/desktop-performance-analyzer/performance-analyzer-01.png)

성능 분석기는 사용자 상호작용이 시작되는 모든 시각적 개체를 새로 고치거나 업데이트하는 데 필요한 기간을 표시하고 검사하며, 정보를 표시하여 결과를 보고, 드릴다운, 또는 내보내기할 수 있습니다. 성능 분석기는 보고서의 성능에 영향을 주는 시각적 개체를 식별하고 영향의 이유를 확인할 수 있습니다.

## <a name="displaying-the-performance-analyzer-pane"></a>성능 분석기 창 표시

**Power BI Desktop**에서 **보기** 리본을 선택합니다. **보기** 리본의 **표시** 영역에서 성능 분석기 창을 표시하기 위해 **성능 분석기** 옆의 확인란을 선택할 수 있습니다.

![보기 리본에서 선택 성능 분석기](media/desktop-performance-analyzer/performance-analyzer-02.png)

선택하면, 성능 분석기가 보고서 캔버스의 오른쪽에 자체 창으로 표시됩니다.

## <a name="using-performance-analyzer"></a>성능 분석기 사용

성능 분석기는 쿼리를 실행하는 모든 사용자 상호 작용의 결과로 시작되는 보고서 요소를 업데이트하는 데 필요한 처리 시간(만들거나 시각적 개체를 업데이트하는 시간 포함)을 측정합니다. 예를 들어, 슬라이서를 조정하면 수정되어야 할 슬라이서 시각적 개체, 데이터 모델로 보내질 쿼리와 새 설정의 결과로 업데이트해야 하는 영향을 받는 시각적 개체가 필요합니다. 

성능 분석기의 기록을 시작하려면 **기록 시작**을 선택하기만 하면 됩니다.

![기록 시작](media/desktop-performance-analyzer/performance-analyzer-03.png)

보고서에서 수행하는 모든 동작은 Power BI에서 로드된 시각적 개체 순서로 성능 분석기 창에 표시되고 기록됩니다. 예를 들어, 사용자가 새로 고치려면 시간이 오래 걸리는 보고서를 가지고 있을 수 있습니다. 또는 슬라이더를 조정하는 경우 보고서의 특정 시각적 개체를 표시하는 데 시간이 오래 걸립니다. 성능 분석기는 어떤 시각적 개체가 원인인지 알려주고 처리 기간이 가장 오래 걸리는 시각적 개체의 측면이 어떤 것인지를 식별할 수 있습니다. 

기록이 시작되면 **기록 시작** 단추는 흐리게 표시되며(비활성, 기록이 이미 시작하여서) **중지** 단추가 활성화됩니다. 

성능 분석기는 실시간으로 성능 측정 정보를 수집하고 표시합니다. 시각적 개체를 클릭하거나 슬라이서를 이동하거나 다른 방식으로 상호 작용할 때마다, 성능 분석기는 해당 창에 성능 결과를 즉시 표시합니다.

창에 표시될 수 있는 추가 정보가 있으면 추가 정보로 이동하는 스크롤 막대가 나타납니다.

각 상호 작용에는 창에 섹션 식별자가 있어서, 로그 항목을 시작하는 작업을 설명합니다. 다음 이미지에서의 상호 작용은 사용자가 슬라이서를 변경한 것입니다.

![상호 작용 유형을 기반으로 하는 섹션](media/desktop-performance-analyzer/performance-analyzer-04.png)

각 시각적 개체의 로그 정보는 다음과 같은 범주의 태스크를 완료하기 위해 소요된 시간(기간)을 포함합니다.

* **DAX 쿼리** -DAX 쿼리가 필요한 경우, 쿼리를 전송하는 시각적 개체와 결과를 반환하는 Analysis Services 사이의 시간입니다.
* **시각적 개체 표시** - 지도나 웹 이미지를 검색하는 데 필요한 시간을 포함하여 화면에 그리기 위해 시각적 개체에 필요한 시간입니다. 
* **기타** - 시각적 개체가 쿼리를 준비하거나, 다른 시각적 개체가 완료하기를 기다리거나, 다른 백그라운드 프로세스를 수행하는 데 필요한 시간입니다.

![요소의 로그 정보](media/desktop-performance-analyzer/performance-analyzer-06.png)

Performance Analyzer를 사용하여 측정하려는 보고서의 요소를 사용하여 상호작용한 후에는 **중지** 단추를 선택할 수 있습니다. 분석하기 위해 **중지** 단추를 선택한 후에도 창에 성능 정보가 유지됩니다.

성능 분석기 창에서 정보를 지우려면 **지우기**를 선택합니다. **지우기**를 선택하는 경우 모든 정보가 지워지며 저장되지 않습니다. 로그에 정보를 저장하는 방법을 알아보려면 다음 섹션을 참조하세요. 

## <a name="refreshing-visuals"></a>시각적 개체 새로 고침

보고서의 현재 페이지의 모든 시각적 개체를 새로 고치려면 성능 분석기에서 **시각적 개체 새로 고침**을 선택할 수 있으며, 그러면 성능 분석기는 이러한 모든 시각적 개체에 대한 정보를 수집합니다.

또한 개별 시각적 개체를 새로 고칠 수 있습니다. 성능 분석기가 기록하는 중일 경우, 각 시각적 개체의 오른쪽 위 모서리에서 **이 시각적 개체 새로 고침**을 선택하여 해당 성능 정보를 캡처합니다.

![개별 시각적 개체 새로 고침](media/desktop-performance-analyzer/performance-analyzer-07.png)

## <a name="saving-performance-information"></a>성능 정보 저장

**내보내기** 단추를 선택하여 보고서에 대해 성능 분석기에서 만든 정보를 저장할 수 있습니다. **내보내기**를 선택하면 성능 분석기 창의 정보를 사용하여 .json 파일을 만듭니다. 

![성능 분석기에 대 한 로그 파일 저장](media/desktop-performance-analyzer/performance-analyzer-05.png)


## <a name="next-steps"></a>다음 단계
**Power BI Desktop**에 대한 자세한 내용 및 시작하는 방법은 다음 문서를 확인하세요.

* [Power BI Desktop이란?](desktop-what-is-desktop.md)
* [Power BI Desktop을 사용한 쿼리 개요](desktop-query-overview.md)
* [Power BI Desktop의 데이터 원본](desktop-data-sources.md)
* [Power BI Desktop에서 데이터에 연결](desktop-connect-to-data.md)
* [Power BI Desktop에서 데이터 셰이핑 및 결합](desktop-shape-and-combine-data.md)
* [Power BI Desktop의 일반적인 쿼리 작업](desktop-common-query-tasks.md)   

