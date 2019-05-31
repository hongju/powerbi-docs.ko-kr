---
title: Power BI Desktop의 보고서 요소 성능을 검사를 사용 하 여 성능 분석기
description: 시각적 개체 및 보고서 요소 리소스 사용량 및 응답성 측면에서 수행 하는 방법을 알아봅니다
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
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "65854416"
---
# <a name="use-performance-analyzer-to-examine-report-element-performance"></a>Performance Analyzer를 사용 하 여 보고서 요소 성능 검사

**Power BI Desktop** 찾을 수 있습니다 각 시각적 개체에서 DAX 수식을 등 보고서 요소를 수행 하는 방법을 확장 합니다. 사용 하는 **Performance Analyzer**, 볼 수 있습니다 및 레코드를 기록 하는 사용자 상호 작용 하는 경우 각 보고서 요소의 수행 하는 방법을 측정 되며 해당 성능의 측면 대부분 (또는 최소) 리소스를 많이 사용 합니다.

![성능 분석기](media/desktop-performance-analyzer/performance-analyzer-01.png)

Performance Analyzer 검사 업데이트나 모든 시각적 개체를 새로 고치는 데 필요한 기간을 표시 하는 사용자 상호 작용을 시작 및 보기을 드릴 다운 하거나 결과 내보낼 수 있도록 정보를 제공 합니다. 성능 분석 보고서의 성능에 영향을 주는 시각적 개체를 식별 하 고 영향 이유를 확인할 수 있습니다.

## <a name="displaying-the-performance-analyzer-pane"></a>Performance Analyzer 창 표시

**Power BI Desktop** 를 선택 합니다 **보기** 리본. 에 **표시** 영역의 합니다 **뷰** 리본 옆의 확인란을 선택할 수 있습니다 **Performance Analyzer** Performance Analyzer 창을 표시 하려면.

![보기 리본에서 선택 성능 분석기](media/desktop-performance-analyzer/performance-analyzer-02.png)

선택 하면 성능 분석기 자체 창에서 보고서 캔버스의 오른쪽에 표시 됩니다.

## <a name="using-performance-analyzer"></a>Performance Analyzer를 사용 하 여

성능 분석기 측정값 (만들거나 시각적 개체를 업데이트 하는 시간 포함)의 처리 시간 쿼리를 실행 하는 모든 사용자 상호 작용으로 인해 시작 하는 보고서 요소를 업데이트 해야 합니다. 새 설정을 업데이트 해야 하는 영향을 받는 시각적 개체 확인 하 고 수정할 수는 쿼리 데이터 모델을 전송할 수 있도록 슬라이서 visual 예를 들어 필요 슬라이서를 조정 합니다. 

Performance Analyzer 녹음을 시작 하도록 선택 하기만 하면 됩니다 **기록을 시작**

![기록 시작](media/desktop-performance-analyzer/performance-analyzer-03.png)

보고서에 수행할 동작 표시 되 고 Power BI에서 시각적 개체를 로드 되도록 순서로 Performance Analyzer 창에서 기록 됩니다. 예를 들어 경우가 있습니다 보고서 즉 사용자가 새로 고치려면 시간이 오래 걸립니다. 또는 특정 보고서의 시각적 개체는 시간이 슬라이더를 조정 하는 경우 표시 됩니다. 성능 분석기 처리 기간이 가장 긴 시간이 하는 visual이 원인, 시각적 개체의 측면을 식별 알 수 있습니다. 

기록 시작 되 면 합니다 **기록을 시작** 단추는 흐리게 표시 아웃 (비활성, 녹음/녹화 이미 롤아웃하기 시작 했습니다 때문) 및 **중지** 단추가 활성화 됩니다. 

성능 분석기를 수집 하 고 실시간으로 성능 측정 정보를 표시 합니다. 시각적 개체를 클릭할 때마다 슬라이서를 이동 하거나 다른 방식에서으로 상호 작용 성능 분석기 성능 결과 해당 창에 즉시 표시 합니다.

창에 표시 될 수 있는 추가 정보가 있으면 추가 정보로 이동 하는 스크롤 막대가 나타납니다.

로그 항목을 시작 하는 작업을 설명 하는 창에서 섹션 식별자를가 하는 각 상호 작용 합니다. 다음 이미지에서는 상호 작용은 사용자가 슬라이서를 변경 했습니다.

![상호 작용 유형을 기반으로 하는 섹션](media/desktop-performance-analyzer/performance-analyzer-04.png)

각 시각적 개체의 로그 정보에 소요 된 시간 (기간) 다음과 같은 범주의 태스크를 완료 하려면 포함 합니다.

* **DAX 쿼리** -DAX 쿼리를 필요한 경우 결과 반환 하는 Analysis Services에 대 한 쿼리를 전송 하는 시각적 개체 사이의 시간입니다.
* **시각적 표시** -지 오 코딩 나 웹 이미지를 검색 하는 데 필요한 시간을 포함 하 여 화면에 그릴 시각적 개체에 필요한 시간. 
* **다른** -쿼리를 준비, 대기를 완료 하려면 다른 시각적 개체 또는 다른 백그라운드 프로세스를 수행에 대 한 시각적 개체에 필요한 시간.

![요소의 로그 정보](media/desktop-performance-analyzer/performance-analyzer-06.png)

Performance Analyzer를 사용 하 여 측정 하려는 보고서의 요소를 사용 하 여 작용할 했으므로, 후 선택할 수 있습니다 합니다 **중지** 단추입니다. 성능 정보를 선택한 후 창의 남아 **중지** 분석할 수 있도록 합니다.

선택 Performance Analyzer 창에서 정보를 지우려면 **의 선택을 취소**합니다. 정보를 모두 지우고 선택 하면 저장 되지 않습니다 **명확한**합니다. 로그에 정보를 저장 하는 방법을 알아보려면 다음 섹션을 참조 하세요. 

## <a name="refreshing-visuals"></a>시각적 개체 새로 고침

선택할 수 있습니다 **시각적 개체 새로 고침** Performance Analyzer 창의 보고서의 현재 페이지의 모든 시각적 개체를 새로 고치고 있습니다 Performance Analyzer 이러한 모든 시각적 개체에 대 한 정보를 수집 합니다.

또한 개별 시각적 개체를 새로 고칠 수 있습니다. Performance Analyzer는 녹음 하는 경우 선택할 수 있습니다 **이 시각적 개체 새로 고침** 해당 시각적 개체를 새로 고치려면 각 시각적 개체의 오른쪽 위 모서리에서 찾은 해당 성능 정보를 캡처합니다.

![개별 시각적 개체 새로 고침](media/desktop-performance-analyzer/performance-analyzer-07.png)

## <a name="saving-performance-information"></a>성능 정보를 저장합니다.

선택 하 여 성능 분석기에서 만든 보고서에 대 한 정보를 저장할 수 있습니다 합니다 **내보내기** 단추입니다. 선택 **내보내기** Performance Analyzer 창에서 정보를 사용 하 여.json 파일을 만듭니다. 

![성능 분석기에 대 한 로그 파일 저장](media/desktop-performance-analyzer/performance-analyzer-05.png)


## <a name="next-steps"></a>다음 단계
**Power BI Desktop**에 대한 자세한 내용 및 시작하는 방법은 다음 문서를 확인하세요.

* [Power BI Desktop이란?](desktop-what-is-desktop.md)
* [Power BI Desktop을 사용한 쿼리 개요](desktop-query-overview.md)
* [Power BI Desktop의 데이터 원본](desktop-data-sources.md)
* [Power BI Desktop에서 데이터에 연결](desktop-connect-to-data.md)
* [Power BI Desktop에서 데이터 셰이핑 및 결합](desktop-shape-and-combine-data.md)
* [Power BI Desktop의 일반적인 쿼리 작업](desktop-common-query-tasks.md)   

