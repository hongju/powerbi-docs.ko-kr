---
title: Power BI 시각적 개체에서 데이터 내보내기
description: 보고서 시각적 개체 및 대시보드 시각적 개체에서 데이터를 내보내고 Excel에서 봅니다.
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: jtlLGRKBvXY
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 4/9/2019
ms.author: mihart
LocalizationGroup: Consumers
ms.openlocfilehash: d4384db8e05a69b138e76377e7c7b845867fa881
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "61063848"
---
# <a name="export-data-from-visual"></a>시각적 데이터 내보내기
시각적 개체를 만드는 데 사용된 데이터를 보려면, Excel로 데이터를 내보내기하거나 [Power BI에서 해당 데이터를 표시할 수 있습니다](end-user-show-data.md). 데이터를 내보내는 옵션에는 특정 형식 또는 라이선스와 콘텐츠에 대한 편집 권한이 있어야 합니다. 내보낼 수 없는 경우, Power BI 관리자에게 문의하십시오. 

## <a name="from-a-visual-on-a-power-bi-dashboard"></a>Power BI 대시보드의 시각적 개체에서

1. Power BI 대시보드를 시작합니다. 여기에서는 ***마케팅 및 판매 샘플*** 앱의 대시보드를 사용합니다. [AppSource.com에서 이 앱을 다운로드](https://appsource.microsoft.com/en-us/product/power-bi/microsoft-retail-analysis-sample.salesandmarketingsample-preview?flightCodes=e2b06c7a-a438-4d99-9eb6-4324ce87f282)할 수 있습니다 .

    ![](media/end-user-export/power-bi-dashboard.png)

2. 줄임표(...)를 표시하려면 시각적 개체 위에 마우스를 놓고 동작 메뉴를 표시하도록 클릭합니다.

    ![](media/end-user-export/power-bi-dashboard-export-visual.png)

3. **Excel로 내보내기**를 선택합니다.

4. 사용 중인 브라우저에 따라 다음 작업이 달라집니다. 파일을 저장하라는 메시지가 나타나거나 브라우저의 맨 아래에서 내보낸 파일에 대한 링크를 확인할 수 있습니다. 

    ![](media/end-user-export/power-bi-export-browser.png)

5. Excel에서 파일을 엽니다.  

    ![](media/end-user-export/power-bi-excel.png)


## <a name="from-a-visual-in-a-report"></a>보고서의 시각적 개체에서
.csv 또는.xlsx(Excel) 형식으로 보고서의 시각적 개체에서 데이터를 내보낼 수 있습니다. 

1. 대시보드에서, 기본 보고서를 열기 위해 타일을 선택합니다. 이 예제에서는 위와 동일한 시각적 개체로 *총 단위 YTD Var %*를 선택하겠습니다. 

    ![](media/end-user-export/power-bi-export-report.png)

    이 타일은 *영업 및 마케팅 샘플* 보고서에서 생성되었으므로 해당 보고서가 열립니다. 그리고, 선택한 타일 시각적 개체를 포함하는 페이지가 열립니다. 

2. 보고서에서 해당 타일을 선택합니다. 오른쪽에 있는 **필터** 창을 확인합니다. 이 시각적 개체에 필터가 적용되어 있습니다. 필터에 대한 자세한 내용은 [보고서에서 필터 사용](end-user-report-filter.md)을 참조하세요.

    ![](media/end-user-export/power-bi-export-filters.png)


3. 시각화의 오른쪽 위 모서리에 있는 줄임표를 선택합니다. **데이터 내보내기**를 선택합니다.

    ![](media/end-user-export/power-bi-export-report2.png)

4. 요약된 데이터 또는 기본 데이터를 내보내는 옵션이 표시됩니다. *영업 및 마케팅 샘플* 앱을 사용 중인 경우, **기본 데이터**는 비활성화됩니다. 하지만 두 옵션을 사용할 수 있는 보고서를 볼 수 있습니다. 차이에 대한 설명은 다음과 같습니다.

    **요약된 데이터**: 시각적 개체에 표시되는 내용에 대한 데이터를 내보내려면 이 옵션을 선택합니다. 이 유형의 내보내기는 시각적 개체를 만드는 데 사용한 데이터만 보여 줍니다. 시각적 개체에 적용된 필터가 있는 경우에는 내보내는 데이터도 필터링됩니다. 예를 들어 이 시각적 개체에서 내보내기에는 2014년 중부 지역에 대한 데이터만 그리고 제조업체 중 다음 4곳에 대한 데이터만 포함됩니다: VanArsdel, Natura, Aliqui 및 Prirum.
  

    **기본 데이터**: 시각적 개체에 표시되는 내용에 대한 데이터와 **함께** 기본 데이터 세트의 추가 데이터를 내보내려면 이 옵션을 선택합니다. 이 데이터 집합에 포함되어 있지만 시각적 개체에서 사용되지 않는 데이터를 포함할 수 있습니다. 

    ![](media/end-user-export/power-bi-export-report3.png)

5. 사용 중인 브라우저에 따라 다음 작업이 달라집니다. 파일을 저장하라는 메시지가 나타나거나 브라우저의 맨 아래에서 내보낸 파일에 대한 링크를 확인할 수 있습니다. 

    ![](media/end-user-export/power-bi-export-edge.png)


7. Excel에서 파일을 엽니다. 대시보드에서 동일한 시각적 개체에서 내보낸 데이터와 내보낸 데이터의 양을 비교합니다. 이 내보내기에서 다른 점은 **기본 데이터**가 포함되어 있다는 것입니다. 

    ![](media/end-user-export/power-bi-underlying.png)

