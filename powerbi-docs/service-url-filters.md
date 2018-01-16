---
title: "URL을 사용하여 Power BI 보고서 매개 변수 추가"
description: "URL 쿼리 문자열 매개 변수를 사용하여 보고서를 필터링하며 두 개 이상의 필드를 필터링할 수도 있습니다."
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/08/2018
ms.author: mihart
ms.openlocfilehash: 8a818c26a6f9afd134133464b972091faaad093d
ms.sourcegitcommit: 804ee18b4c892b7dcbd7d7d5d987b16ef16fc2bb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2018
---
# <a name="filter-a-report-using-query-string-parameters-in-the-url"></a>URL에 쿼리 문자열 매개 변수를 사용하여 보고서 필터링
Power BI 서비스에서 보고서를 열면 보고서의 페이지마다 고유한 URL을 보유합니다. 보고서 페이지를 필터링하려면 보고서 캔버스에서 필터 창을 사용할 수 있습니다.  또는 URL에 쿼리 문자열 매개 변수를 추가하여 보고서를 필터링할 수 있습니다. 동료에게 보여 주고 싶은 보고서가 있고 이를 위해 미리 필터링하려고 할 수 있습니다. 이 작업을 수행하는 한 가지 방법은 보고서에 대한 기본 URL로 시작하고 필터 매개 변수를 URL에 추가한 후 전체 URL을 전자 메일로 보내는 것입니다.

![](media/service-url-filters/power-bi-report2.png)

<iframe width="640" height="360" src="https://www.youtube.com/embed/WQFtN8nvM4A?list=PLv2BtOtLblH3YE_Ycas5B1GtcoFfJXavO&amp;showinfo=0" frameborder="0" allowfullscreen></iframe>

## <a name="query-string-parameter-syntax-for-filtering"></a>필터링을 위한 쿼리 문자열 매개 변수 구문
구문은 매우 간단합니다. 보고서 URL로 시작하고 물음표를 추가한 다음 필터 구문을 추가하면 됩니다.

URL?filter=***Table***/***Field*** eq '***value***'

![](media/service-url-filters/power-bi-filter-urls7b.png)

* **Table** 및 **Field** 이름은 대소문자를 구분하고 **value**는 구분하지 않습니다.
* 보고서 보기에서 숨겨진 필드는 계속 필터링할 수 있습니다.
* **Value**는 작은따옴표로 묶어야 합니다.
* 필드 유형은 숫자 또는 문자열이어야 합니다.
* 테이블 및 필드 이름에는 공백을 포함할 수 없습니다.

여전히 혼동되는 경우 계속 읽어 보고 자세히 분석합니다.  

## <a name="filter-on-a-field"></a>필드 필터링
보고서에 대한 URL이 다음과 같다고 가정합니다.

![](media/service-url-filters/power-bi-filter-urls6.png)

North Carolina에 매장이 있다는 것을 맵 시각화(위)에서 확인할 수 있습니다.

>[!NOTE]
>이 예제는 [소매점 분석 샘플](sample-datasets.md)을 토대로 합니다.
> 

"NC"(North Carolina)의 매장에 대한 데이터만 표시하도록 보고서를 필터링하려면 다음으로 URL을 추가합니다.

?filter=Store/Territory eq 'NC'

![](media/service-url-filters/power-bi-filter-urls7.png)

>[!NOTE]
>*NC*는 **Store** 테이블의 **Territory** 필드에 저장된 값입니다.
> 
> 

보고서는 North Carolina에 대해 필터링되며 보고서 페이지에 있는 모든 시각화는 North Carolina에 대한 데이터만 표시합니다.

![](media/service-url-filters/power-bi-report4.png)

## <a name="filter-on-multiple-fields"></a>여러 필드 필터링
또한 URL에 추가 매개 변수를 추가하여 여러 필드에서 필터링할 수 있습니다. 우리의 원래 필터 매개 변수로 돌아갑니다.

```
?filter=Store/Territory eq 'NC'
```

추가 필드를 필터링하려면 `and` 및 다른 필드를 동일한 형식으로 추가합니다. 예를 들면 다음과 같습니다.

```
?filter=Store/Territory eq 'NC' and Store/Chain eq 'Fashions Direct'
```

<iframe width="640" height="360" src="https://www.youtube.com/embed/0sDGKxOaC8w?showinfo=0" frameborder="0" allowfullscreen></iframe>


### <a name="using-dax-to-filter-on-multiple-values"></a>DAX를 사용하여 여러 값을 필터링
여러 값을 필터링하는 한 가지 방법은 두 필드를 하나의 값으로 연결하는 계산된 열을 만드는 것입니다. 그런 다음 해당 값을 필터링할 수 있습니다.

예를 들어 Territory 및 Chain이라는 두 필드가 있습니다. Power BI Desktop에서 TerritoryChain이라는 [새 계산된 열](desktop-tutorial-create-calculated-columns.md)(필드)을 만듭니다. **필드** 이름에는 공백을 포함할 수 없다는 점에 유의하세요. 다음은 해당 열에 대한 DAX 수식입니다

TerritoryChain = [Territory] & " - " & [Chain]

보고서를 Power BI 서비스에 게시한 후 URL 쿼리 문자열을 사용하여 NC에 있는 Lindseys 매장으로만 표시 데이터를 필터링합니다.

https://app.powerbi.com/groups/me/reports/8d6e300b-696f-498e-b611-41ae03366851/ReportSection3?filter=Store/TerritoryChain eq 'NC–Lindseys'

## <a name="pin-a-tile-from-a-filtered-report"></a>필터링된 보고서에서 타일 고정
쿼리 문자열 매개 변수를 사용하여 보고서를 필터링했으면 보고서에서 대시보드로 시각화를 고정할 수 있습니다. 대시보드의 타일에는 필터링된 데이터가 표시되고 대시보드 타일을 클릭하면 타일 생성에 사용된 보고서가 열립니다.  하지만 URL을 사용하여 수행했던 필터링은 보고서와 함께 저장되지 않으며 대시보드 타일을 선택하면 보고서가 필터링되지 않은 상태로 열립니다.  따라서 대시보드 타일에 표시된 데이터는 보고서 시각화에 표시된 데이터와 일치하지 않습니다.

다른 결과를 보고 싶을 때 도움이 되는 경우가 있을 수 있습니다. 대시보드에서는 필터링되고 보고서에서는 필터링되지 않도록 하는 경우가 그렇습니다.

## <a name="limitations-and-troubleshooting"></a>제한 사항 및 문제 해결
쿼리 문자열 매개 변수를 사용할 때 알아야 할 몇 가지 사항이 있습니다.

* 쿼리 문자열 필터링은 [웹에 게시](service-publish-to-web.md) 또는 Power BI Embedded에는 작동하지 않습니다.   
* 필드 유형은 숫자 또는 문자열이어야 합니다.
* 테이블 및 필드 이름에는 공백을 포함할 수 없습니다.

## <a name="next-steps"></a>다음 단계
[시각화를 대시보드에 고정](service-dashboard-pin-tile-from-report.md)  
[사용해 보세요. 무료입니다!](https://powerbi.com/)

궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](http://community.powerbi.com/)

