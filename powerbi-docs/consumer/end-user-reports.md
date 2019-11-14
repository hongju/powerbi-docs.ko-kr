---
title: Power BI 서비스의 보고서
description: 소비자를 위한 Power BI 서비스의 보고서
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 09/05/2019
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: 21a77d585707b19cd8a3d06ad44471fac45d7178
ms.sourcegitcommit: 52aa112ac9194f4bb62b0910c4a1be80e1bf1276
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/16/2019
ms.locfileid: "70903719"
---
# <a name="reports-in-power-bi"></a>Power BI의 보고서

Power BI 보고서는 해당 데이터 세트에서 얻은 다양한 결과 및 인사이트를 나타내는 시각적 개체가 포함된 데이터 세트에 대한 다각적인 데이터 뷰입니다.  보고서에는 단일 시각적 개체 또는 여러 페이지의 시각적 개체가 있을 수 있습니다. 작업 역할에 따라 보고서를 *디자인*하는 사람이 될 수 있습니다. 보고서를 *소비* 또는 사용하는 사람이 될 수도 있습니다. 이 문서는 *소비자*를 위한 것입니다.

![보고서 페이지의 스크린샷.](./media/end-user-reports/power-bi-report.png)

A. 이 보고서에는 6개의 페이지(또는 탭)가 있으며, 현재 **감정** 페이지를 보고 있습니다.    
B. 이 페이지에는 5가지 시각화 개체와 페이지 제목이 있습니다.    
C. ‘필터’ 창에는 모든 보고서 페이지에 적용되는 하나의 필터가 표시됩니다.  필터 창을 축소하려면 화살표( **>** )를 선택합니다.    
D. Power BI 배너에는 보고서 이름과 마지막 업데이트 날짜가 표시됩니다. 화살표를 선택하여 보고서 소유자의 이름도 표시하는 메뉴를 엽니다.    
E. 작업 모음에는 이 보고서에서 수행할 수 있는 작업이 포함되어 있습니다.  예를 들어, 주석을 추가하거나, 책갈피를 보거나, 보고서에서 데이터를 내보낼 수 있습니다.  줄임표(...)를 선택하여 추가 보고서 기능 목록을 표시합니다.    

Power BI를 처음 접하는 경우 [Power BI 서비스 소비자를 위한 기본 개념](end-user-basic-concepts.md)을 읽으면 적절한 기초 정보를 얻을 수 있습니다. 모바일 디바이스에서 보고서를 보고 공유하고 주석을 달 수 있습니다. 자세한 내용은 [Power BI 모바일 앱에서 보고서 탐색](mobile/mobile-reports-in-the-mobile-apps.md)을 참조하세요.

## <a name="advantages-of-reports"></a>보고서의 이점

Power BI는 단일 데이터 세트를 기반으로 보고서를 만듭니다. 보고서 *디자이너*는 정보 모음을 나타내는 보고서에서 시각적 개체를 만듭니다. 시각적 개체는 정적이지 않습니다.  기본 데이터가 변경됨에 따라 업데이트됩니다. 데이터를 탐색하면서 시각적 개체와 필터를 상호 작용하여 인사이트를 검색하고 답변을 찾을 수 있습니다. 대시보드와 같이 보고서는 대화형이며 자유롭게 사용자 지정이 가능합니다.

### <a name="safely-interact-with-content"></a>콘텐츠와 안전하게 상호 작용

필터링, 조각화, 구독 및 내보내기 등 콘텐츠를 탐색하고 상호 작용할 때 보고서를 중단할 수 없습니다. 작업은 기본 데이터 세트 또는 공유된 원래 콘텐츠에 영향을 주지 않습니다. 이는 대시보드, 보고서 및 앱에 적용됩니다.

> [!NOTE]
> 데이터를 손상시킬 수 없음을 기억하세요. Power BI는 중단 없이 탐색하고 실험하기에 좋은 곳입니다.

### <a name="save-your-changes-or-revert-to-the-default-settings"></a>변경 내용을 저장하거나 기본 설정으로 되돌리기

그렇다고 해서 변경 내용을 저장할 수 없다는 의미는 아닙니다. 변경할 수 있지만 이러한 변경 내용은 콘텐츠의 보기에만 영향을 줍니다. 보고서의 원래 기본 보기로 되돌리려면 **기본값으로 다시 설정**을 선택합니다.

![기본값으로 되돌리기 아이콘 스크린샷](./media/end-user-reports/power-bi-reset.png)

## <a name="dashboards-versus-reports"></a>대시보드 및 보고서

[대시보드](end-user-dashboards.md)는 시각적 개체로 채워진 캔버스이므로 보고서와 혼동되기 쉽습니다. 하지만 몇 가지 주요 차이점이 있습니다.  

| **기능** | **대시보드** | **보고서** |
| --- | --- | --- |
| 페이지 |한 페이지 |한 페이지 이상 |
| 데이터 소스 |대시보드당 보고서 및 데이터 세트 모두 하나 이상 |보고서당 단일 데이터 세트 |
| 필터링 |필터링 또는 조각화 불가능 |필터링, 강조 표시 및 조각화를 위한 다양한 방법 |
| 경고 설정 |대시보드가 특정 조건을 충족할 때 이메일로 경고를 만들 수 있습니다. |아니요 |
| 특정 |하나의 대시보드를 주요 대시보드로 설정할 수 있음 |주요 보고서를 만들 수 없음 |
| 기본 데이터 세트 테이블 및 필드를 볼 수 있음 |아니요. 데이터를 내보낼 수 있지만 대시보드 자체에서 데이터 세트 테이블 및 필드를 볼 수 없음 |예. 볼 수 있는 권한이 있는 데이터 세트 테이블, 필드 및 값을 확인할 수 있음 |
| 사용자 지정 |아니요  |필터링, 내보내기, 관련 콘텐츠 보기, 책갈피 추가, QR 코드 생성, Excel에서 분석 등을 할 수 있음 |

<!--| Available in Power BI Desktop |No |Yes, can create and view reports in Desktop |
| Pinning |Can pin existing visuals (tiles) only from current dashboard to your other dashboards |Can pin visuals (as tiles) to any of your dashboards. Can pin entire report pages to any of your dashboards. | -->

## <a name="report-designers-and-report-consumers"></a>보고서 디자이너 및 보고서 소비자

사용자 역할에 따라 직접 사용하거나 동료와 공유할 수 있는 보고서를 만드는 *디자이너*일 수 있습니다. 보고서를 만들고 공유하는 방법에 대해 알아보고자 합니다.

또는 다른 사람에게서 보고서를 받는 *소비자*일 수 있습니다. 보고서를 이해하고 상호 작용하는 방법에 대해 알아보고자 합니다. 보고서 *소비자*인 경우 다음 링크를 사용할 수 있습니다.

* [Power BI 서비스 둘러보기](end-user-basic-concepts.md)에서 시작하면 보고서와 보고서 도구 위치를 파악할 수 있습니다.
* [보고서를 여는 방법](end-user-report-open.md)과 [소비자가 사용할 수 있는 모든 상호 작용](end-user-reading-view.md)에 대해 살펴봅니다.
* [샘플](../sample-tutorial-connect-to-the-samples.md) 중 하나를 둘러보면 보고서에 금방 익숙해 집니다.  
* 보고서가 사용 중인 데이터 세트와 보고서(*고정*)의 시각적 개체를 표시하는 대시보드를 확인하려면 [Power BI의 관련 콘텐츠 보기](end-user-related.md)를 참조하세요.

> [!TIP]
> 여기서 찾고 있는 항목이 없으면 왼쪽의 목차를 사용하여 모든 *보고서* 문서를 탐색합니다.

## <a name="next-steps"></a>다음 단계

[보고서 열기 및 보기](end-user-report-open.md)    
[Power BI 서비스의 대시보드](end-user-dashboards.md)
