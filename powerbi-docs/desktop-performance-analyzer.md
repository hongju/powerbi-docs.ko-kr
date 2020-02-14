---
title: Power BI Desktop에서 성능 분석기를 사용하여 보고서 요소 성능 검사
description: 리소스 사용량 및 응답성 측면에서 시각적 개체와 보고서 요소가 수행하는 방법을 알아봅니다.
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/23/2020
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: e3e9e8ebc7feda46cb4c79ffd1535807d04a178b
ms.sourcegitcommit: a1409030a1616027b138128695b80f6843258168
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76709780"
---
# <a name="use-performance-analyzer-to-examine-report-element-performance"></a>성능 분석기를 사용하여 보고서 요소 성능 검사

**Power BI Desktop**에서는 시각적 개체 및 DAX 수식과 같은 각 보고서 요소에서 수행하는 방법을 확인할 수 있습니다. **성능 분석기**를 사용하면 각 보고서 요소에서 사용자와 상호 작용할 때 수행하는 방법과 리소스를 가장 많이(또는 가장 적게) 사용하는 성능 측면을 측정하는 로그를 확인하고 기록할 수 있습니다.

![성능 분석기](media/desktop-performance-analyzer/performance-analyzer-01.png)

성능 분석기는 사용자 상호 작용에서 시작하는 모든 시각적 개체를 업데이트하거나 새로 고치는 데 필요한 기간을 검사하고 표시하며, 결과를 보거나 드릴다운하거나 내보낼 수 있도록 정보를 제공합니다. 성능 분석기는 보고서 성능에 영향을 주는 시각적 개체를 식별하고 영향의 원인을 파악하는 데 도움이 됩니다.

## <a name="displaying-the-performance-analyzer-pane"></a>성능 분석기 창 표시

**Power BI Desktop**에서 **보기** 리본을 선택합니다. **보기** 리본의 **표시** 영역에서 **성능 분석기** 옆의 확인란을 선택하여 성능 분석기 창을 표시할 수 있습니다.

![보기 리본에서 성능 분석기 선택](media/desktop-performance-analyzer/performance-analyzer-02.png)

이 확인란이 선택되면 성능 분석기가 보고서 캔버스의 오른쪽에 있는 자체 창에 표시됩니다.

## <a name="using-performance-analyzer"></a>성능 분석기 사용

성능 분석기는 쿼리를 실행하는 사용자 상호 작용의 결과로 시작된 보고서 요소를 업데이트하는 데 필요한 처리 시간(시각적 개체를 만들거나 업데이트하는 시간 포함)을 측정합니다. 예를 들어 슬라이서를 조정하려면 수정할 슬라이서 시각적 개체, 데이터 모델로 보낼 쿼리 및 새 설정으로 인해 업데이트해야 하는 영향을 받는 시각적 개체가 필요합니다. 

성능 분석기에서 기록을 시작하도록 하려면 **기록 시작**만 선택하면 됩니다.

![기록 시작](media/desktop-performance-analyzer/performance-analyzer-03.png)

보고서에서 수행한 모든 작업은 Power BI에서 시각적 개체를 로드하는 순서대로 성능 분석기 창에 표시되고 기록됩니다. 예를 들어 사용자가 새로 고치는 데 시간이 오래 걸린다는 보고서가 있을 수 있습니다. 또는 슬라이더를 조정할 때 보고서의 특정 시각적 개체를 표시하는 데 시간이 오래 걸립니다. 성능 분석기는 원인이 되는 시각적 개체를 알려줄 수 있으며, 처리하는 시간이 가장 오래 걸리는 시각적 개체를 식별합니다. 

기록이 시작되면 **기록 시작** 단추가 회색으로 표시되고(이미 기록을 시작했으므로 비활성), **중지** 단추가 활성화됩니다. 

성능 분석기는 성능 측정 정보를 실시간으로 수집하여 표시합니다. 따라서 시각적 개체를 클릭하거나 슬라이서를 이동하거나 다른 방식으로 상호 작용할 때마다 성능 분석기는 성능 결과를 창에 즉시 표시합니다.

창에 표시할 수 있는 것보다 많은 정보가 있는 경우 추가 정보로 이동할 수 있는 스크롤 막대가 표시됩니다.

각 상호 작용의 창에는 로그 항목을 시작한 작업을 설명하는 섹션 식별자가 있습니다. 다음 이미지에서 상호 작용은 사용자가 슬라이서를 변경했다는 것입니다.

![상호 작용 유형에 기반한 섹션](media/desktop-performance-analyzer/performance-analyzer-04.png)

각 시각적 개체의 로그 정보에는 다음과 같은 범주의 작업을 완료하는 데 소요된 시간(기간)이 포함됩니다.

* **DAX 쿼리** - DAX 쿼리가 필요한 경우 이는 시각적 개체에서 쿼리를 보내는 시간과 Analysis Services에서 결과를 반환하는 시간 사이의 기간입니다.
* **시각적 개체 표시** - 시각적 개체에서 웹 이미지 또는 지오코딩을 검색하는 데 필요한 시간을 포함하여 화면에 그리는 데 필요한 시간입니다. 
* **기타** - 시각적 개체에서 쿼리를 준비하거나, 다른 시각적 개체가 완료될 때까지 기다리거나, 다른 백그라운드 처리를 수행하는 데 필요한 시간입니다.

**기간(밀리초)** 값은 각 작업에 대해 *시작*과 *끝* 타임스탬프 사이의 차이를 표시합니다. 대부분의 캔버스 및 시각적 개체 작업은 여러 작업에서 공유되는 단일 사용자 인터페이스 스레드에서 순차적으로 실행됩니다. 보고된 기간에는 다른 작업이 완료될 때까지 대기하는 데 소요된 시간이 포함됩니다. GitHub 및 관련 [문서](https://github.com/microsoft/powerbi-desktop-samples/blob/master/Performance%20Analyzer/Power%20BI%20Performance%20Analyzer%20Export%20File%20Format.docx)의 [성능 분석기 샘플](https://github.com/microsoft/powerbi-desktop-samples/tree/master/Performance%20Analyzer)은 시각적 개체 쿼리 데이터 및 렌더링 방법에 대한 세부 정보를 제공합니다.


![로그 정보 요소](media/desktop-performance-analyzer/performance-analyzer-06.png)

성능 분석기를 사용하여 측정하려는 보고서의 요소와 상호 작용한 후에는 **중지** 단추를 선택할 수 있습니다. 분석하기 위해 **중지**를 선택한 후에도 성능 정보는 창에 남아 있습니다.

성능 분석기 창에서 정보를 지우려면 **지우기**를 선택합니다. **지우기**가 선택되면 모든 정보가 지워지고 저장되지 않습니다. 정보를 로그에 저장하는 방법을 일아보려면 다음 섹션을 참조하세요. 

## <a name="refreshing-visuals"></a>시각적 개체 새로 고침

성능 분석기 창에서 **시각적 개체 새로 고침**을 선택하여 보고서의 현재 페이지에 있는 모든 시각적 개체를 새로 고치고, 이에 따라 성능 분석기에서 이러한 모든 시각적 개체에 대한 정보를 수집할 수 있습니다.

시각적 개체를 개별적으로 새로 고칠 수도 있습니다. 성능 분석기에서 기록하고 있으면 각 시각적 개체의 오른쪽 위 모서리에 있는 **이 시각적 개체 새로 고침**을 선택하여 해당 시각적 개체를 새로 고치고 관련 성능 정보를 캡처할 수 있습니다.

![개별 시각적 개체 새로 고침](media/desktop-performance-analyzer/performance-analyzer-07.png)

## <a name="saving-performance-information"></a>성능 정보 저장

**내보내기** 단추를 선택하여 성능 분석기에서 보고서에 대해 만드는 정보를 저장할 수 있습니다. **내보내기**가 선택되면 성능 분석기 창의 정보가 포함된 .json 파일이 만들어집니다. 

![성능 분석기의 로그 파일 저장](media/desktop-performance-analyzer/performance-analyzer-05.png)


## <a name="next-steps"></a>다음 단계
**Power BI Desktop**에 대한 자세한 내용 및 시작하는 방법은 다음 문서를 확인하세요.

* [Power BI Desktop이란?](desktop-what-is-desktop.md)
* [Power BI Desktop을 사용한 쿼리 개요](desktop-query-overview.md)
* [Power BI Desktop의 데이터 원본](desktop-data-sources.md)
* [Power BI Desktop에서 데이터에 연결](desktop-connect-to-data.md)
* [Power BI Desktop에서 데이터 셰이핑 및 결합](desktop-shape-and-combine-data.md)
* [Power BI Desktop의 일반적인 쿼리 작업](desktop-common-query-tasks.md)   

성능 분석기 샘플에 대한 자세한 내용은 다음 리소스를 확인하세요.

* [성능 분석기 샘플](https://github.com/microsoft/powerbi-desktop-samples/tree/master/Performance%20Analyzer)
* [성능 분석기 샘플 설명서](https://github.com/microsoft/powerbi-desktop-samples/blob/master/Performance%20Analyzer/Power%20BI%20Performance%20Analyzer%20Export%20File%20Format.docx)