---
title: Power BI 디자이너용 대시보드 소개
description: 대시보드는 Power BI 서비스의 핵심 기능입니다. 대시보드는 시각화를 통해 스토리를 알려주는 흔히 캔버스라고 불리는 단일 페이지입니다.
author: maggieMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 12/10/2018
ms.author: maggies
LocalizationGroup: Dashboards
ms.openlocfilehash: 61d7bf9f9794545e963ca19c8f983d6d6cfefa54
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "61150416"
---
# <a name="intro-to-dashboards-for-power-bi-designers"></a>Power BI 디자이너용 대시보드 소개

Power BI ***대시보드***는 시각화를 통해 스토리를 알려주는 흔히 캔버스라고 불리는 단일 페이지입니다. 한 페이지로 제한되기 때문에 잘 디자인된 대시보드는 해당 스토리의 하이라이트만 포함합니다. Readers(읽기 권한자)는 세부 정보에 대한 관련 보고서를 볼 수 있습니다.

![대시보드](media/service-dashboards/power-bi-dashboard2.png)

대시보드는 Power BI 서비스의 기능입니다. 대시보드는 Power BI Desktop에서 사용할 수 없습니다. 모바일 디바이스에서는 대시보드를 만들 수 없지만 [보기 및 공유](mobile-apps-view-dashboard.md)할 수 있습니다.

## <a name="dashboard-basics"></a>대시보드 기본 사항 

대시보드에 표시되는 시각화를 *타일*이라고 합니다. 보고서에서 대시보드로 타일을 고정할 수 있습니다. Power BI를 처음 접하는 경우 [Power BI 기본 개념](service-basic-concepts.md)을 읽으면 적절한 기초 정보를 얻을 수 있습니다.

> [!IMPORTANT]
> 대시 보드를 만들려면 [Power BI Pro](service-free-vs-pro.md) 라이선스가 필요합니다.

대시보드의 시각화는 보고서에서 제공되며 각 보고서는 데이터 세트를 기반으로 합니다. 대시보드를 생각하는 한 가지 방법은 기본 보고서와 데이터 세트로 들어가는 입구로 여기는 것입니다. 시각화를 선택하면 해당 시각화를 기반으로 하는 보고서(및 데이터 세트)로 이동합니다.

![대시보드, 보고서, 데이터 세트 간의 관계를 보여주는 다이어그램](media/service-dashboards/power-bi-diagram.png)

## <a name="advantages-of-dashboards"></a>대시보드의 장점
대시보드는 비즈니스를 모니터링하고 가장 중요한 모든 메트릭을 한 눈에 볼 수 있는 훌륭한 방법입니다. 대시보드의 시각화는 하나 또는 여러 개의 기본 데이터 세트, 하나 또는 여러 개의 기본 보고서에서 제공될 수 있습니다. 대시보드는 온-프레미스 및 클라우드 데이터를 결합하여 데이터의 현재 위치에 관계없이 통합된 보기를 제공합니다.

대시보드는 단지 깔끔한 사진이 아닙니다. 고도의 대화형이며 기본 데이터가 변경되면 타일이 업데이트됩니다.

## <a name="dashboards-versus-reports"></a>대시보드 및 보고서
[보고서](service-reports.md) 및 대시보드는 시각화로 채워진 캔버스이기 때문에 둘 다 비슷해 보입니다. 하지만 주요 차이점이 있습니다.

| **기능** | **대시보드** | **보고서** |
| --- | --- | --- |
| 페이지 |한 페이지 |한 페이지 이상 |
| 데이터 소스 |대시보드당 보고서 및 데이터 세트 모두 하나 이상 |보고서당 단일 데이터 세트 |
| Power BI Desktop에서 사용 가능 |아니요 | Power BI Desktop에서 보고서 작성 및 보기 가능 |
| 구독 |대시보드 구독 가능 |보고서 페이지 구독 가능 |
| 필터링 |필터링 또는 조각화 불가능 |필터링, 강조 표시 및 조각화를 위한 다양한 방법 |
| 추천 |한 대시보드를 “주천” 대시보드로 설정할 수 있음 |추천 보고서를 만들 수 없음 |
| 즐겨찾기 | 대시보드를 *즐겨찾기*로 설정할 수 있음 | 보고서를 *즐겨찾기*로 설정할 수 있음
| 경고 설정 |특정 상황에서 대시보드 타일에서 사용 가능 |보고서에서 사용 불가능 |
| 자연어 쿼리(질문 및 답변) |대시보드에서 사용 가능 | 보고서에서 가용 가능 |
| 기본 데이터 세트 테이블 및 필드를 볼 수 있음 |아니요. 데이터를 내보낼 수 있지만 대시보드 자체에서 테이블 및 필드를 볼 수 없음 |예. 데이터 세트 테이블 및 필드와 값을 볼 수 있습니다. |


## <a name="next-steps"></a>다음 단계
* [샘플 대시보드](sample-tutorial-connect-to-the-samples.md) 중 하나를 둘러보면 대시보드에 금방 익숙해 집니다.
* [대시보드 타일](service-dashboard-tiles.md)에 대해 알아봅니다.
* 개별 대시보드 타일을 추적하고 특정 임계값에 도달하면 전자 메일을 수신하고 싶은가요? [타일에 경고를 만듭니다](service-set-data-alerts.md).
* [Power BI 질문 및 답변](power-bi-tutorial-q-and-a.md)을 사용하여 데이터에 대한 질문을 하고 시각화 형태로 답변을 받는 방법에 대해 알아봅니다.
