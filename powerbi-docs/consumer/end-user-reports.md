---
title: Power BI에서 보고서 보기
description: Power BI의 보고서
author: mihart
manager: kvivek
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 12/06/2018
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: 31fe32bff8749b7b8136d980da9ea0e5bec3bc4f
ms.sourcegitcommit: cd85d88fba0d9cc3c7a4dc03d2f35d2bd096759b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2018
ms.locfileid: "53281088"
---
# <a name="reports-in-power-bi"></a>Power BI의 보고서
## <a name="what-is-a-power-bi-report"></a>Power BI 보고서란?
Power BI ***보고서***는 데이터 집합의 다양한 결과 및 통찰력을 나타내는 시각화가 포함된 다각적인 데이터 뷰입니다.  보고서는 단일 시각화나 여러 페이지의 시각화를 포함할 수 있습니다. 작업 역할에 따라 보고서를 *만들거나* , *사용* 또는 소비하는 사람이 될 수 있습니다.

![보고서 페이지](./media/end-user-reports/reportview.png)

이 보고서는 3페이지(또는 탭)로 구성되며 지금 보고 있는 것은 매장 판매 개요 페이지입니다. 이 페이지에는 6가지 시각화와 페이지 제목이 있습니다. 시각화는 대시보드에 *고정*되며 고정된 시각화를 선택할 경우 자신이 고정되어 있는 보고서를 엽니다.

Power BI를 처음 접하는 경우 [Power BI 기본 개념](end-user-basic-concepts.md)을 읽어 보고 적절한 기초 정보를 얻을 수 있습니다.

보고서는 Power BI 서비스 및 Power BI Desktop의 기능입니다. 보고서 작업 환경은 거의 동일합니다. 그러나 모바일의 경우 보고서를 만들 수는 없지만 [보기, 공유 및 보고서에 주석 달기](mobile/mobile-reports-in-the-mobile-apps.md)는 가능합니다.

## <a name="advantages-of-reports"></a>보고서의 이점
보고서는 단일 데이터 집합을 기반으로 합니다. 각 보고서의 시각화는 각기 정보 모음을 나타냅니다. 시각화 요소는 정적인 것이 아니므로 사용자가 데이터를 조사하여 정보와 답변을 찾아가는 과정에서 데이터를 추가 및 제거하고 시각화 유형을 변경하며 필터 및 슬라이서를 적용할 수 있습니다. 대시보드와 거의 유사하게 보고서도 대화형이며 자유롭게 사용자 지정이 가능하고 기본 데이터가 변경되면 시각화도 업데이트됩니다. 

## <a name="dashboards-versus-reports"></a>대시보드 및 보고서
[대시보드](end-user-dashboards.md)는 시각화로 채워진 캔버스이므로 보고서와 혼동됩니다. 하지만 몇 가지 주요 차이점이 있습니다.  

| **기능** | **대시보드** | **보고서** |
| --- | --- | --- |
| 페이지 |한 페이지 |한 페이지 이상 |
| 데이터 소스 |대시보드당 보고서 및 데이터 집합 모두 하나 이상 |보고서당 단일 데이터 집합 |
| Power BI Desktop에서 사용 가능 |아니요 |예, 바탕 화면에서 보고서를 만들고 볼 수 있음 |
| 핀 고정 |기존 시각화(타일)를 현재 대시보드에서 다른 대시보드로만 핀 고정 가능 |핀 시각화(타일로)를 임의 대시보드로 핀 고정 가능. 전체 보고서 페이지를 임의 대시보드로 핀 고정 가능. |
| 구독 |대시보드는 구독할 수 없음 |보고서 페이지 구독 가능 |
| 필터링 |필터링 또는 조각화 불가능 |필터링, 강조 표시 및 조각화를 위한 다양한 방법 |
| 경고 설정 |특정 조건이 충족되는 경우 전자 메일 경고를 만들 수 있음 |아니요 |
| 특정 |한 대시보드를 “주천” 대시보드로 설정할 수 있음 |추천 보고서를 만들 수 없음 |
| 자연어 쿼리 |대시보드에서 사용 가능 |보고서에서 사용 불가능 |
| 시각화 유형 변경 가능 |아니요. 실제로 보고서 소유자가 보고서에서 시각화 유형을 변경하면 대시보드에 고정된 시각화가 업데이트되지 않습니다. |예 |
| 기본 데이터 집합 테이블 및 필드를 볼 수 있음 |아니요. 데이터를 내보낼 수 있지만 대시보드 자체에서 테이블 및 필드를 볼 수 없음 |예. 데이터 집합 테이블 및 필드와 값을 볼 수 있음. |
| 시각화를 만들 수 있음 |"타일 추가"를 사용하여 위젯을 대시보드에 추가하는 것으로 제한됨 |다양한 시각적 개체 유형을 만들고 사용자 지정 시각적 개체를 추가하며 편집 권한으로 시각적 개체를 편집하는 등의 작업이 가능 |
| 사용자 지정 |이동 및 배열, 크기 조정, 링크 추가, 이름 바꾸기, 삭제 및 전체 화면 표시 등 시각화(타일)로 작업을 수행할 수 있음. 하지만 데이터와 시각화 자체는 읽기 전용입니다. |읽기용 보기에서 게시, 포함, 필터, 내보내기, .pbix로 다운로드, 관련 콘텐츠 보기, QR 코드 생성, Excel에서 분석 등을 수행할 수 있습니다.  편집용 보기에서 지금까지 언급한 모든 항목을 수행할 수 있습니다. |

## <a name="report-creators-and-report-consumers"></a>보고서 ***작성자*** 및 보고서 ***소비자***
사용자 역할에 따라 자신의 용도에 따라 또는 동료와 공유하기 위해 보고서를 만들려는 사람이 있을 수 있습니다. 보고서를 만들고 공유하는 방법에 대해 알아보고 싶습니다. 또는 다른 사람에게서 보고서를 받은 사람도 있을 수 있습니다. 보고서를 이해하고 상호 작용하는 방법에 대해 알아보고 싶습니다.

다음은 시작하는 데 도움이 되는 몇 가지 항목을 역할별로 정리한 것입니다.

### <a name="if-you-will-be-creating-and-sharing-reports"></a>보고서를 만들고 공유고 공유하려는 경우
* [Power BI 서비스 둘러보기](end-user-basic-concepts.md)에서 시작하면 보고서와 보고서 도구 위치를 파악할 수 있습니다.
* [보고서 편집기](../service-the-report-editor-take-a-tour.md)를 둘러보세요.
* [데이터 집합에서 새 보고서를 만드는 방법](../service-report-create-new.md)을 살펴봅니다.
* [시각화, 페이지 및 보고서 수준 필터를 사용하는 방법에 살펴봅니다.](end-user-report-filter.md)
* [동료와 보고서를 공유](../service-share-dashboards.md)하는 다양한 방법을 모두 알아봅니다.

### <a name="if-you-will-be-receiving-and-consuming-reports"></a>보고서를 받아 사용하는 경우
* [Power BI 서비스 둘러보기](end-user-basic-concepts.md)에서 시작하면 보고서와 보고서 도구 위치를 파악할 수 있습니다.
* [읽기용 보기](end-user-reading-view.md)에서 [보고서를 여는 방법](end-user-report-open.md)과 모든 사용 가능한 상호 작용에 대해 살펴봅니다. 
* [샘플](../sample-tutorial-connect-to-the-samples.md) 중 하나를 둘러보면 보고서에 금방 익숙해 집니다.  
<!--* Don't need the report any more? You can [remove it](../service-delete.md).-->
* 보고서가 어떤 데이터 집합을 사용 중이며 어떤 대시보드가 보고서에서 고정된 타일이 있는지 확인하려면 [관련된 콘텐츠를 봅니다](end-user-related.md).

> [!TIP]
> 여기서 찾고 있는 항목이 없으면 왼쪽의 목차를 사용하여 모든 *보고서* 항목을 탐색합니다.
> 
> 

## <a name="next-steps"></a>다음 단계
[Power BI란?](../power-bi-overview.md) 

[Power BI - 기본 개념](end-user-basic-concepts.md)

