---
title: Power BI에서 보고서 보기
description: Power BI의 보고서
author: mihart
manager: kvivek
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 5/10/2018
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: 02652bd027d7dab8a40d77fb92c5aae8f09d8820
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "65607871"
---
# <a name="reports-in-power-bi"></a>Power BI의 보고서
## <a name="what-is-a-power-bi-report"></a>Power BI 보고서란?
Power BI ***보고서*** 해당 데이터 집합에서 다양 한 결과 및 통찰력을 나타내는 시각적 개체를 사용 하 여 데이터 집합으로 다중 관점 뷰입니다.  보고서는 시각적 개체의 전체 페이지 또는 단일 시각적 개체에 있을 수 있습니다. 작업 역할에 따라가 될 수 있습니다는 *디자인* 보고서 및/또는 있습니다 사람이 될 수는 *소비* 또는 보고서를 사용 합니다.

![보고서 페이지](./media/end-user-reports/power-bi-report.png)

이 보고서는 6 개의 페이지 (또는 탭) 및 감정 페이지를 현재 보고 있는 것입니다. 이 페이지는 6의 다른 시각적 개체 및 페이지 제목입니다.  

Power BI를 처음 접하는 경우 [Power BI 기본 개념](end-user-basic-concepts.md)을 읽어 보고 적절한 기초 정보를 얻을 수 있습니다.

보고서 보기, 공유 및 모바일 장치에서 주석을 추가할 수 있습니다. 자세한 내용은 [Power BI 모바일 보고서](mobile/mobile-reports-in-the-mobile-apps.md)합니다.

## <a name="advantages-of-reports"></a>보고서의 이점
보고서는 단일 데이터 세트를 기반으로 합니다. 보고서의 시각적 개체는 보고서를 만들어 *디자이너* 는 각기 정보 모음을 나타냅니다. 시각적 개체 고정; 없습니다. 답변을 정보를 검색할 데이터를 조사 하면서 시각적 개체 및 필터를 상호 작용할 수 있습니다. 대시보드를와 마찬가지로 보고서는 대화형 이며 자유롭게 사용자 지정할 수 있지만 더-따라서 하 고 기본 데이터가 변경 되 면 시각적 개체 업데이트.

### <a name="safely-interact-with-content"></a>콘텐츠와 안전하게 상호 작용
탐색 하 고 프로그램 콘텐츠, 필터링, 조각화, 구독 및 내보내기, 분명; 상호 작용 기본 데이터 집합 또는 원래 공유 콘텐츠 (대시보드, 보고서 및 앱)에 작업 적용 되지 않습니다.
 
> [!NOTE]
> 기억 데이터 저하 될 수 없습니다. Power BI 탐색 하 고는 "중단 됩니다" 아무 것도 없이 실험에 대 한 좋은 장소입니다.

### <a name="save-your-changes-or-revert-to-the-default-settings"></a>변경 내용을 저장 하거나 기본 설정으로 되돌리기
변경 내용을; 저장할 수 없습니다. 그렇다고 를 수 있지만 이러한 변경 내용의 보기에만 영향을 줍니다. 원래 기본 보기로 되돌리기 간단 하 게 재설정 기본 단추를 선택 합니다.

## <a name="dashboards-versus-reports"></a>대시보드 및 보고서
[대시보드](end-user-dashboards.md) 시각적 표시로 채워진 캔버스 이므로 보고서와 혼동 많습니다. 하지만 몇 가지 주요 차이점이 있습니다.  

| **기능** | **대시보드** | **보고서** |
| --- | --- | --- |
| 페이지 |한 페이지 |한 페이지 이상 |
| 데이터 소스 |대시보드당 보고서 및 데이터 세트 모두 하나 이상 |보고서당 단일 데이터 세트 |
| 필터링 |필터링 또는 조각화 불가능 |필터링, 강조 표시 및 조각화를 위한 다양한 방법 |
| 경고 설정 |특정 조건이 충족되는 경우 전자 메일 경고를 만들 수 있음 |아니요 |
| 특정 |한 대시보드를 “주천” 대시보드로 설정할 수 있음 |추천 보고서를 만들 수 없음 |
| 기본 데이터 세트 테이블 및 필드를 볼 수 있음 |아니요. 데이터를 내보낼 수는 있지만 데이터 집합 테이블 및 대시보드 자체에서 필드를 볼 수 없습니다. |예. 데이터 집합 테이블 및 필드를 볼 권한이 있는 값을 볼 수 있습니다. |
| 사용자 지정 |아니요  |필터링, 내보내기, 관련된 콘텐츠 보기, 책갈피를 추가, QR 코드 생성을 excel 등에서 분석 합니다.   |

<!--| Available in Power BI Desktop |No |Yes, can create and view reports in Desktop |
| Pinning |Can pin existing visuals (tiles) only from current dashboard to your other dashboards |Can pin visuals (as tiles) to any of your dashboards. Can pin entire report pages to any of your dashboards. | -->

## <a name="report-creators-and-report-consumers"></a>보고서 ***작성자*** 및 보고서 ***소비자***
역할에 따라 수를 *디자이너*를 직접 사용 하거나 동료와 공유 하려면 보고서를 만드는 사용자가 있습니다. 보고서를 만들고 공유하는 방법에 대해 알아보고 싶습니다. 또는 다른 사람에게서 보고서를 받은 사람도 있을 수 있습니다. 보고서를 이해하고 상호 작용하는 방법에 대해 알아보고 싶습니다. 보고서를 있다면 **소비자**, 이러한 링크는 합니다. 

* [Power BI 서비스 둘러보기](end-user-basic-concepts.md)에서 시작하면 보고서와 보고서 도구 위치를 파악할 수 있습니다.
* [읽기용 보기](end-user-reading-view.md)에서 [보고서를 여는 방법](end-user-report-open.md)과 모든 사용 가능한 상호 작용에 대해 살펴봅니다.
* [샘플](../sample-tutorial-connect-to-the-samples.md) 중 하나를 둘러보면 보고서에 금방 익숙해 집니다.  
<!--* Don't need the report any more? You can [remove it](../service-delete.md).-->
* 보고서가 어떤 데이터 세트를 사용 중이며 어떤 대시보드가 보고서에서 고정된 타일이 있는지 확인하려면 [관련된 콘텐츠를 봅니다](end-user-related.md).

> [!TIP]
> 여기서 찾고 있는 항목이 없으면 왼쪽의 목차를 사용하여 모든 *보고서* 항목을 탐색합니다.
> 
> 

## <a name="next-steps"></a>다음 단계
[Power BI란?](../power-bi-overview.md) 

[Power BI - 기본 개념](end-user-basic-concepts.md)

