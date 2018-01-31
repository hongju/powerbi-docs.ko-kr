---
title: "iFrame을 사용하여 보고서 포함"
description: "Power BI Report Server 자체를 신속하게 설치할 수 있습니다. 몇 분 이내에 다운로드, 설치 및 구성하도록 실행합니다."
services: powerbi
documentationcenter: 
author: markingmyname
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 11/09/2017
ms.author: maghan
ms.openlocfilehash: 56835bfb25c8c930099fadf710137f69fa89fc2e
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/30/2018
---
# <a name="quickstart-embed-a-power-bi-report-using-an-iframe-and-url-parameters"></a>빠른 시작: iFrame 및 URL 매개 변수를 사용하여 Power BI 보고서 포함

응용 프로그램에서 iFrame을 사용하여 모든 보고서를 포함할 수 있습니다. 

## <a name="url-parameter"></a>URL 매개 변수

보고서에 대한 모든 URL에 `?rs:Embed=true`의 쿼리 문자열 매개 변수를 추가할 수 있습니다.

예:

```
http://myserver/reports/powerbi/Sales?rs:embed=true
```

Power BI Report Server 내의 모든 보고서 유형에서 작동합니다.

## <a name="iframe"></a>iFrame

URL이 있으면 보고서를 호스팅하기 위해 웹 페이지 내에서 iFrame을 만들 수 있습니다.

예:

```
<iframe width="800" height="600" src="http://myserver/reports/powerbi/Sales?rs:embed=true" frameborder="0" allowFullScreen="true"></iframe>
```

## <a name="url-filter"></a>URL 필터

Power BI 보고서에서 반환된 데이터를 필터링하기 위해 URL에 쿼리 문자열 매개 변수를 추가할 수 있습니다.

구문은 간단합니다. 보고서 URL로 시작하고 물음표를 추가한 다음 이 필터 구문을 추가하면 됩니다.

URL?filter=***Table***/***Field*** eq '***value***'

다음 고려 사항을 염두에 두십시오.

- **Table** 및 **Field** 이름은 대소문자를 구분하고 **value**는 구분하지 않습니다.
- 보고서 보기에서 숨겨진 필드가 있는 보고서를 필터링할 수 있습니다.
- **Value**는 작은따옴표로 묶어야 합니다.
- 필드 형식은 문자열이어야 합니다.
- 테이블 및 필드 이름에는 공백을 포함할 수 없습니다.

###  <a name="example-filter-on-a-field"></a>예제: 필드 필터링

이 예제는 [소매점 분석 샘플](../sample-datasets.md)을 사용합니다. 보고서 폴더에서 이 보고서에의 URL이 이름이 "power-bi"인 폴더에 있다고 가정하겠습니다.

```
https://report-server/reports/power-bi/Retail-Analysis-Sample
```

소매점 분석 샘플의 지도 시각화에는 노스캐롤라이나 및 기타 주에 위치한 매장을 보여 줍니다.

![소매점 분석 샘플 맵 시각화](media/quickstart-embed/report-server-retail-analysis-sample-map.png)

*NC*는 **Store** 테이블의 **Territory** 필드에 저장된 값입니다. NC(노스캐롤라이나)의 매장에 대한 데이터만 표시하도록 보고서를 필터링하려면 다음을 URL에 추가합니다.

?filter=Store/Territory eq 'NC'

이제 보고서는 노스캐롤라이나에 대해 필터링되며 보고서 페이지에 있는 모든 시각화는 노스캐롤라이나에 대한 데이터만 표시합니다.

![소매점 분석 샘플 필터링 시각화](media/quickstart-embed/report-server-retail-analysis-sample-filtered-map.png)

### <a name="create-a-dax-formula-to-filter-on-multiple-values"></a>여러 값에 대해 필터링하는 DAX 수식만들기

여러 값을 필터링하는 한 가지 방법은 Power BI Desktop에서 두 필드를 하나의 값으로 연결하는 계산된 열을 만드는 것입니다. 그런 다음 해당 값을 필터링할 수 있습니다.

예를 들어 소매점 분석 샘플에는 Territory 및 Chain 등의 두 필드가 있습니다. Power BI Desktop에서 TerritoryChain이라는 [계산된 열](../desktop-tutorial-create-calculated-columns.md)(필드)을 만들 수 있습니다. **필드** 이름에는 공백을 포함할 수 없다는 점에 유의하세요. 다음은 해당 열에 대한 DAX 수식입니다

TerritoryChain = [Territory] & "-" & [Chain]

보고서를 Power BI Report Server에 게시한 후 URL 쿼리 문자열을 사용하여 NC에 있는 Lindseys 매장으로만 표시 데이터를 필터링합니다.

```
https://report-server/reports/power-bi/Retail-Analysis-Sample?filter=Store/TerritoryChain eq 'NC-Lindseys'

```

## <a name="next-steps"></a>다음 단계

[빠른 시작: Power BI Report Server용 Power BI 보고서 만들기](quickstart-create-powerbi-report.md)  
[빠른 시작: Power BI Report Server에 페이지가 매겨진 보고서 만들기](quickstart-create-paginated-report.md)  

궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](https://community.powerbi.com/)