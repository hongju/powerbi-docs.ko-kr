---
title: 대시보드는 무엇이고, 여는 방법은 무엇인가요?
description: 대시보드는 Power BI 서비스의 핵심 기능입니다.
author: mihart
manager: kvivek
ms.custom: seodec18
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 05/12/2019
ms.author: mihart
LocalizationGroup: Dashboards
ms.openlocfilehash: 81987b864224b6afd254a3bffe17ecbb019198d0
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "65608344"
---
# <a name="dashboards-for-power-bi-service-consumers"></a>Power BI 서비스 소비자에 대한 대시보드

Power BI ***대시보드***는 보통 캔버스라고도 하며 스토리를 전달하기 위해 시각화를 사용하는 단일 페이지입니다. 한 페이지로 제한되기 때문에 해당 스토리의 가장 중요한 요소만 포함할 경우 잘 디자인된 대시보드라 할 수 있습니다.

![대시보드](media/end-user-dashboards/power-bi-dashboard2.png)

시각화를 대시보드에 표시 라고 *타일* 되며 *고정* 보고서에서 대시보드로 *디자이너*합니다. 대부분의 경우, 타일을 선택 하면 보고서 페이지에 시각화가 만들어진 합니다. Power BI를 처음 접하는 경우 [Power BI 기본 개념](end-user-basic-concepts.md)을 읽으면 적절한 기초 정보를 얻을 수 있습니다.

> [!NOTE]
> 대시보드를 [모바일 디바이스에서 보고 공유](mobile/mobile-apps-view-dashboard.md)할 수 있습니다.
>
> 공유된 대시보드를 보려면 Power BI Pro가 필요합니다.
> 

대시보드의 시각화는 보고서를 기반으로 하며 각 보고서는 한 개의 데이터 세트를 기반으로 합니다. 사실, 대시보드를 생각하는 한 가지 방법은 기본 보고서와 데이터 세트로 들어가는 입구로 여기는 것입니다. 시각화를 선택하면 이를 만드는 데 사용한 보고서(및 데이터 세트)로 이동합니다.

![대시보드, 보고서, 데이터 세트 간의 관계를 보여주는 다이어그램](media/end-user-dashboards/power-bi-diagram.png)

## <a name="advantages-of-dashboards"></a>대시보드의 장점
대시보드는 비즈니스를 모니터링하고, 답변을 찾고, 가장 중요한 모든 메트릭을 한 눈에 볼 수 있는 훌륭한 방법입니다. 대시보드의 시각화는 하나 또는 여러 개의 기본 데이터 세트, 하나 또는 여러 개의 기본 보고서에서 제공될 수 있습니다. 대시보드는 온-프레미스 및 클라우드 데이터를 결합하여 데이터의 현재 위치와 관계없이 통합된 보기를 제공합니다.

대시보드는 단순한 예쁜 그림이;를 하지 않습니다. 대화형 및 기본 데이터가 변경 되 면 타일이 업데이트 합니다.

## <a name="dashboards-versus-reports-for-power-bi-consumers"></a>대시보드 및 Power BI ***소비자*** 보고서
대개 보고서는 시각화로 채워진 캔버스이므로 대시보드와 혼동됩니다. 하지만 Power BI 소비자 관점과의 몇 가지 주요한 차이점이 있습니다. 

| **기능** | **대시보드** | **보고서** |
| --- | --- | --- |
| 페이지 |한 페이지 |한 페이지 이상 |
| 데이터 소스 |대시보드당 보고서 및 데이터 세트 모두 하나 이상 |보고서당 단일 데이터 세트 |
| 필터링 |필터링 또는 조각화 불가능 |필터링, 강조 표시 및 조각화를 위한 다양한 방법 |
| 경고 설정 |특정 조건이 충족되는 경우 전자 메일 경고를 만들 수 있음 |아니요 |
| 추천 |한 대시보드를 “주천” 대시보드로 설정할 수 있음 |추천 보고서를 만들 수 없음 |
| 기본 데이터 세트 테이블 및 필드를 볼 수 있음 |아니요. 데이터를 내보낼 수 있지만 대시보드 자체에서 테이블 및 필드를 볼 수 없음 |예. 데이터 세트 테이블 및 필드와 값을 볼 수 있습니다. |


## <a name="dashboard-creators-and-dashboard-consumers"></a>대시보드 작성자 및 대시보드 소비자
Power BI ***소비자***는 작성자의 대시보드를 받습니다.  이 항목에서 계속 대시보드에 대해 알아봅니다.

* [대시보드 보기](end-user-dashboard-open.md)
* [대시보드 타일](end-user-tiles.md)과 선택할 경우 어떻게 되는지 알아보세요.
* 개별 대시보드 타일을 추적하고 특정 임계값에 도달하면 전자 메일을 수신하고 싶은가요? [타일에 경고를 만듭니다](end-user-alerts.md).
* 즐겁게 대시보드 질문을 활용하세요. [Power BI 질문 및 답변](end-user-q-and-a.md)을 사용하여 데이터에 대한 질문을 하고 시각화 형태로 답변을 받는 방법에 대해 알아봅니다.

> [!TIP]
> 여기서 찾고 있는 항목이 없으면 왼쪽 내용에 있는 목차를 사용합니다.
> 

## <a name="next-steps"></a>다음 단계
[대시보드 보기](end-user-dashboard-open.md) 