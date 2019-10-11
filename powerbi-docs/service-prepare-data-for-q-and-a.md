---
title: Power BI의 Q&A로 Excel 데이터가 잘 작동하게 합니다.
description: Power BI의 질문 및 답변에서 데이터가 잘 작동하게 만드는 방법
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/13/2019
ms.author: maggies
LocalizationGroup: Ask questions of your data
ms.openlocfilehash: 7ed8eb8e205c05582d2cfd93030ab056be77912a
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "65624979"
---
# <a name="make-excel-data-work-well-with-qa-in-power-bi"></a>Power BI의 Q&A로 Excel 데이터가 잘 작동하게 합니다.
데이터 모델을 만들거나 Power BI에 사용할 Excel 통합 문서를 작성하는 사람이라면 다음을 확인하세요.

Power BI에서는 질문 및 답변으로 구조화된 데이터를 검색하고 질문에 맞는 시각화를 선택할 수 있으므로 매우 유용한 도구입니다.   

질문 및 답변은 테이블, 범위를 가지거나 PowerPivot 모델을 포함하는 모든 업로드된 Excel 파일에서 작동할 수 있지만 보다 최적화하고 데이터 정리를 수행한다면 보다 우수한 질문 및 답변 성능을 제공합니다. 데이터 세트를 기반으로 보고서 및 대시보드를 공유하려는 경우 동료들이 간단하게 질문을 하고 적절한 답변을 받을 수 있도록 해야 합니다.

## <a name="how-qa-works-with-excel"></a>질문 및 답변이 Excel에서 잘 작동하게 만드는 방법
질문 및 답변에는 데이터 전반에서 작동하는 핵심적인 자연어 이해 기능 집합이 포함되어 있습니다. Excel 테이블, 열 및 계산된 필드 이름을 검색하는 컨텍스트 종속 키워드를 포함합니다. 또한 데이터를 필터링, 정렬, 집계, 그룹화 및 표시하는 방법에 대한 기본 제공 지식을 포함하고 있습니다. 

예를 들어, "Product", "Month", "Units Sold", "Gross Sales" 및 "Profit"이라는 열이 있는 "Sales"라는 Excel 테이블에서 이러한 엔터티에 대한 질문을 할 수 있습니다. show sales(판매량 표시), total profit by month(월간 총 수익), sort products by units sold(판매 단위로 제품 정렬) 등으로 질문할 수 있습니다. [대시보드 및 보고서에서 질문 및 답변 사용](power-bi-tutorial-q-and-a.md) 및 [질문 및 답변 쿼리에 지정할 수 있는 시각화 유형](visuals/power-bi-visualization-types-for-reports-and-q-and-a.md)에 대해 자세히 알아보세요.

## <a name="prepare-an-excel-dataset-for-qa"></a>질문 및 답변에 대한 Excel 데이터 세트 준비
질문 및 답변에서는 테이블, 열 및 계산된 필드 이름을 사용하여 데이터 관련 질문에 답변하므로 통합 문서에서 호출하는 엔터티가 중요합니다!

다음은 통합 문서에서 대부분의 질문 및 답변에 대한 몇 가지 팁입니다.

* 데이터가 Excel 테이블인지 확인합니다. 다음은 [Excel 테이블을 만드는 방법](https://support.office.com/article/Create-an-Excel-table-in-a-worksheet-e81aa349-b006-4f8a-9806-5af9df0ac664)입니다.
* 테이블, 열 및 계산된 필드의 이름이 자연어로 인식되는지 확인합니다.
  
  예를 들어, 판매 데이터를 포함하는 테이블인 경우 테이블을 "Sales"라고 합니다. "Year", "Product", "Sales Rep" 및 "Amount"와 같은 열 이름이 질문 및 답변에서 잘 작동합니다.

* 통합 문서에 파워 피벗 데이터 모델이 있는 경우 더 많은 최적화를 수행할 수 있습니다. 사내 팀의 자연어 전문가가 제공하는 [Power BI 질문 및 답변 이해 2부](http://blogs.msdn.com/b/powerbi/archive/2014/02/27/demystifying-power-bi-q-amp-a-part-2.aspx)에 대해 자세히 알아보세요.

* Power BI Desktop에서 데이터 세트를 열고 새 열을 만들고, 계산된 측정값을 만들고, 필드를 연결하여 고유 값을 만들고, 데이터를 유형별로(예: 날짜, 문자열, 지리, 이미지, URL) 분류합니다.

## <a name="next-steps"></a>다음 단계

- [소비자에 대한 질문과 대답](consumer/end-user-q-and-a.md)  
- [대시보드 및 보고서에서 질문 및 답변 사용](power-bi-tutorial-q-and-a.md)
- [Q&A에 대한 온-프레미스 데이터 집합 준비](service-q-and-a-direct-query.md)   
- [Power BI에 대한 데이터 가져오기](service-get-data.md)  

궁금한 점이 더 있나요? [Power BI 커뮤니티를 이용하세요.](http://community.powerbi.com/)

