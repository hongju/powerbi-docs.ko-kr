---
title: Power BI 보고서 작성기에서 보고서 계획
description: Power BI 페이지를 매긴 보고서 작성기를 사용하면 다양한 종류의 페이지를 매긴 보고서를 만들 수 있습니다. 유용하고 이해하기 쉬운 보고서를 만들려면 먼저 계획을 세우는 것이 좋습니다.
ms.date: 06/06/2019
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.assetid: 79113505-1ce8-4f8c-9260-d861838f7813
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: fd4a318d7a61f6f2298de6b9d5d23ad2ae063d28
ms.sourcegitcommit: 797bb40f691384cb1b23dd08c1634f672b4a82bb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/12/2019
ms.locfileid: "66840513"
---
# <a name="planning-a-report-in-power-bi-report-builder"></a>Power BI 보고서 작성기에서 보고서 계획
  Power BI 페이지를 매긴 보고서 작성기를 사용하면 다양한 종류의 페이지를 매긴 보고서를 만들 수 있습니다. 예를 들어 요약 또는 세부 판매 데이터, 마케팅 및 판매 추세, 운영 보고서 또는 대시보드를 표시하는 보고서를 만들 수 있습니다. 또한 판매 주문, 제품 카탈로그 또는 양식 편지와 같이 서식이 지정된 다양한 텍스트를 활용하는 보고서를 만들 수 있습니다. 이러한 모든 보고서는 보고서 작성기에서 동일한 기본 빌딩 블록의 다양한 조합을 사용하여 생성됩니다. 유용하고 이해하기 쉬운 보고서를 만들려면 먼저 계획을 세우는 것이 좋습니다. 다음은 시작하기 전에 고려해야 할 몇 가지 사항입니다.  
  
## <a name="in-what-format-do-you-want-the-report-to-appear"></a>보고서를 어떤 형식으로 표시하나요?
  
Power BI 포털과 같은 브라우저에서 온라인으로 보고서를 렌더링하거나 Excel, Word 또는 PDF와 같은 다른 형식으로 내보낼 수 있습니다. 모든 기능을 모든 내보내기 형식으로 사용할 수 있는 것은 아니기 때문에 보고서의 최종 양식은 중요한 고려 사항입니다. 
  
## <a name="in-what-structure-do-you-want-to-present-the-data"></a>데이터를 어떤 구조로 표시하나요?
  
테이블 형식, 행렬(크로스탭 또는 피벗 테이블 보고서와 유사), 차트, 자유 형식 구조 또는 데이터를 표시하기 위한 이들의 조합 중에서 선택할 수 있습니다. 자세한 내용은 [Power BI 보고서 작성기의 테이블, 행렬 및 목록](report-builder-tables-matrices-lists.md)을 참조하세요.  
  
## <a name="how-do-you-want-your-report-to-look"></a>보고서를 어떻게 확인하시겠습니까?
  
보고서 작성기는 보고서에 추가할 수 있는 많은 보고서 항목을 제공하여 더 쉽게 읽을 수 있도록 하고, 핵심 정보를 강조하며, 대상 그룹이 보고서를 탐색하는 데 도움을 줍니다. 보고서를 표시하는 방법을 알면 텍스트 상자, 사각형, 이미지 및 줄과 같은 보고서 항목이 필요한지 여부를 확인할 수 있습니다. 항목을 표시 또는 숨기거나, 문서 맵을 추가하거나, 드릴스루 보고서 또는 하위 보고서를 포함하거나, 다른 보고서에 연결할 수도 있습니다.   
  
## <a name="should-the-data-be-filtered"></a>데이터를 필터링해야 하나요?
  
보고서의 범위를 특정 사용자나 위치, 또는 특정 기간으로 좁히려는 경우가 있을 수 있습니다. 보고서 데이터를 필터링하려면 매개 변수를 사용하여 원하는 데이터만 검색하고 표시합니다. 자세한 내용은 [Power BI 보고서 작성기의 보고서 매개 변수](paginated-reports-parameters.md)를 참조하세요.  
  
## <a name="do-you-need-to-create-calculations"></a>계산을 해야 하나요? 
  
     Sometimes, your data source and datasets do not contain the exact fields that you need for your report. In that situation, you might have to create your own calculated fields. For example, you might want to multiply the price per unit times the quantity to get a line item sales amount. Expressions are also used to provide conditional formatting and other advanced features. For more information, see [Expressions in Power BI Report Builder](report-builder-expressions.md).  
  
## <a name="do-you-want-to-hide-report-items-initially"></a>보고서 항목을 처음에 숨기시겠습니까?
  
보고서를 처음 실행할 때 데이터 영역, 그룹 및 열을 포함한 보고서 항목을 숨길지 여부를 고려합니다. 예를 들어 처음에 요약 테이블을 표시한 다음, 상세 데이터를 드릴다운할 수 있습니다. 
  
## <a name="how-are-you-going-to-deliver-your-report"></a>보고서를 어떻게 전달하나요?  
  
     You can save your report to your local computer and continue to work on it, or run it locally for your own information. However, to share your report with others, you need to save the report to Power BI. Saving it to Power BI lets others run it whenever they want to. Alternatively, you can set up a subscription and e-mail delivery of the report to other individuals. You can have the report delivered in a specific export format if you prefer. 
  
## <a name="next-steps"></a>다음 단계

- [Power BI Premium에서 페이지를 매긴 보고서란?](paginated-reports-report-builder-power-bi.md)
