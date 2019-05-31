---
title: 보고서를 필터링 하 고 Power BI-동료와 공유
description: Power BI 보고서를 필터링하여 조직의 동료와 공유하는 방법에 대해 알아봅니다.
author: maggiesMSFT
manager: kfile
ms.reviewer: lukaszp
featuredvideoid: 0tUwn8DHo3s
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/24/2019
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: 5f3808884e63521ec1dd775d876f1cf707bbe56b
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "64770688"
---
# <a name="filter-a-power-bi-report-and-share-it-with-coworkers"></a>Power BI 보고서를 필터링 하 고 동료와 공유
다른 사람에게 대시보드 및 보고서에 대한 액세스 권한을 부여하려면 *공유*를 사용하는 것이 좋습니다. 필터링된 버전의 보고서를 공유하려면 어떻게 해야 할까요? 아마도 특정 도시, 판매 직원 또는 연도의 데이터만 보여 주는 보고서일 수도 있습니다. 시도 보고서를 필터링 하 고, 공유 또는 사용자 지정 URL 만들기. 받는 사람이 처음 열 때 보고서가 필터링됩니다. URL을 수정하여 필터를 제거할 수 있습니다. 

또한 Power BI는 [보고서를 공동 작업하고 배포하는 여러 방법](service-how-to-collaborate-distribute-dashboards-reports.md)을 제공합니다. 공유에서 사용자와 해당 수신자는 [Power BI Pro 라이선스](service-features-license-type.md)가 필요하거나 콘텐츠는 [프리미엄 용량](service-premium-what-is.md)에 있어야 합니다. 

## <a name="two-ways-to-filter-a-report"></a>보고서를 필터링 하는 두 가지 방법

### <a name="set-a-filter"></a>필터 설정

[편집용 보기](consumer/end-user-reading-view.md)에서 보고서를 열고, 필터를 적용하고, 보고서를 저장합니다.
   
이 예에서는 [소매점 분석 샘플](sample-tutorial-connect-to-the-samples.md)을 필터링하여 **지역**이 **NC**인 값만 보여 줍니다.
   
![필터 창 보고](media/service-share-reports/power-bi-filter-report2.png)

### <a name="create-a-filter-in-the-url"></a>URL에서 필터 만들기

보고서 페이지의 URL 끝에 다음과 같이 추가합니다.
   
?filter=*tablename*/*fieldname* eq *value*
   
필드 형식 숫자, 날짜/시간 또는 문자열 이어야 합니다. *tablename* 또는 *fieldname* 값은 공백을 포함할 수 없습니다.
   
이 예에서 테이블 이름은 **Store**, 필드 이름은 **Territory**, 그리고 필터링하려는 값은 **NC**입니다.
   
?filter=Store/Territory eq 'NC'
   
![필터링된 보고서 URL](media/service-share-reports/power-bi-filter-url3.png)
   
브라우저에서 슬래시, 공백 및 아포스트로피를 나타내는 특수 문자를 추가하여 다음과 같이 처리합니다.
   
app.powerbi.com/groups/me/reports/010ae9ad-a9ab-4904-a7a1-xxxxxxxxxxxx/ReportSection2?filter=Store%252FTerritory%20eq%20%27NC%27

문서를 참조 하세요 [URL에 쿼리 문자열 매개 변수를 사용 하 여 보고서를 필터링](service-url-filters.md) 훨씬 더 많은 세부 정보에 대 한 합니다.

## <a name="share-the-filtered-report"></a>필터링 된 보고서를 공유 합니다.

1. 경우 있습니다 [보고서를 공유](service-share-dashboards.md)의 선택을 취소 합니다 **받는 사람에 게 전자 메일 알림 보내기** 확인란 합니다.

    ![보고서 공유 대화 상자](media/service-share-reports/power-bi-share-report-dialog.png)

4. 이전에 만든 필터를 사용하여 링크를 보냅니다.

## <a name="next-steps"></a>다음 단계
* 의견이 있으신가요? 제안 사항이 있으시면 [Power BI 커뮤니티 사이트](https://community.powerbi.com/)를 방문하세요.
* [대시보드 및 보고서를 공동 작업 및 공유하는 방법](service-how-to-collaborate-distribute-dashboards-reports.md)
* [대시보드 공유](service-share-dashboards.md)
* 궁금한 점이 더 있나요? [Power BI 커뮤니티를 이용](http://community.powerbi.com/)하세요.

