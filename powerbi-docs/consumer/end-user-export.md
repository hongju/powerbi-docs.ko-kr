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
ms.translationtype: HT
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

1. 대시보드에서 기본 보고서를 열고 타일을 선택 합니다.  이 예제에서는 선택 하겠습니다 동일한 시각적 위와 *총 단위 YTD Var %* 합니다. 

    ![](media/end-user-export/power-bi-export-report.png)

    이 타일을 만든 이후에 *영업 및 마케팅 샘플* 보고서 열리는 보고서입니다. 및 선택한 타일 시각적 개체를 포함 하는 페이지에 열립니다. 

2. 보고서에서 타일을 선택 합니다. 알림 합니다 **필터** 오른쪽에 있는 창입니다. 이 시각적 개체에 필터를 적용 합니다. 필터에 대 한 자세한 내용은 참조 하세요 [보고서에 필터를 사용 하 여](end-user-report-filter.md)입니다.

    ![](media/end-user-export/power-bi-export-filters.png)


3. 시각화의 오른쪽 위 모서리에 있는 줄임표를 선택합니다. 선택할 **데이터 내보내기**합니다.

    ![](media/end-user-export/power-bi-export-report2.png)

4. 요약 된 데이터 나 원본 데이터를 내보내는 옵션이 표시 됩니다. 사용 중인 경우는 *영업 및 마케팅 샘플* 앱 **기본 데이터** 수 없게 됩니다. 하지만 두 옵션을 사용할 수 있는 보고서를 발생할 수 있습니다. 차이 설명은 다음과 같습니다.

    **요약 된 데이터**: 시각적 개체에 표시 되는 내용에 대 한 데이터를 내보내려면이 옵션을 선택 합니다.  이 유형의 내보내기는 시각적 개체를 만드는 데 사용한 데이터만 보여 줍니다. 시각적 개체에 적용 된 필터가 있는 경우에 내보내는 데이터를도 필터링 됩니다. 예를 들어이 시각적 개체 내보내기만 2014에 대 한 데이터 중부 지역 및 제조업체 중 4 개에 대 한 데이터만 포함 됩니다. VanArsdel, Natura, Aliqui, 및 Prirum 합니다.
  

    **내부 데이터**: 시각적 개체에 표시 되는 내용에 대 한 데이터를 내보내려면이 옵션을 선택 **plus** 기본 데이터 집합에서 데이터를 추가 합니다.  이 데이터 집합에 포함 되어 있지만 시각적 개체에서 미사용 데이터를 포함할 수 있습니다. 

    ![](media/end-user-export/power-bi-export-report3.png)

5. 사용 중인 브라우저에 따라 다음 작업이 달라집니다. 파일을 저장하라는 메시지가 나타나거나 브라우저의 맨 아래에서 내보낸 파일에 대한 링크를 확인할 수 있습니다. 

    ![](media/end-user-export/power-bi-export-edge.png)


7. Excel에서 파일을 엽니다. 대시보드에서 동일한 시각적 개체에서 내보낸 데이터와 내보낸 데이터의 양을 비교합니다. 이 내보내기에서 다른 점은 **기본 데이터**가 포함되어 있다는 것입니다. 

    ![](media/end-user-export/power-bi-underlying.png)

