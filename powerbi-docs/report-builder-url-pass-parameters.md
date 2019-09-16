---
title: 페이지를 매긴 보고서에 대한 URL에 보고서 매개 변수 전달 - Power BI 보고서 작성기
description: 이 항목에서는 페이지를 매긴 보고서 URL에 보고서 매개 변수를 포함하여 전달하는 방법에 대해 설명합니다.
ms.service: powerbi
ms.subservice: report-builder
ms.custom: ''
ms.topic: conceptual
author: maggiesMSFT
ms.author: maggies
ms.reviewer: cfinlan
ms.date: 08/29/2019
ms.openlocfilehash: add2f82594d83d1e1f177bfad5045c2e0a34ba84
ms.sourcegitcommit: b53a6f5575f5f8bc443ecdca9c72525ce123518f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2019
ms.locfileid: "70189372"
---
# <a name="pass-a-report-parameter-in-a-url-for-a-paginated-report-in-power-bi"></a>Power BI에서 페이지를 매긴 보고서에 대한 URL에 보고서 매개 변수 전달 

보고서 매개 변수를 페이지를 매긴 보고서 URL에 포함하여 보고서에 전달할 수 있습니다. 모든 쿼리 매개 변수에는 해당하는 보고서 매개 변수가 있을 수 있습니다. 따라서 해당 보고서 매개 변수를 전달하여 보고서에 쿼리 매개 변수를 전달합니다. Power BI가 URL에서 인식할 수 있도록 매개 변수 이름 앞에 접두사로  `rp:`를 붙여야 합니다. 

보고서 매개 변수는 대/소문자를 구분하고 다음과 같은 특수 문자를 사용합니다. 

- URL의 매개 변수 부분에 있는 공백은 더하기 기호(+)로 대체됩니다.  예: 

    ```rp:Holiday=Christmas+Day```

- 문자열의 모든 부분에서 세미콜론은 문자로 `%3A`로 대체됩니다.

브라우저에서 적절한 URL 인코딩이 자동으로 수행됩니다. 따라서 문자를 수동으로 인코딩할 필요는 없습니다. 

URL 내에서 보고서 매개 변수를 설정하려면 다음 구문을 사용합니다. 

```
rp:parameter=value
```

예를 들어, 내 작업 영역의 보고서에 정의된 두 개의 매개 변수 “Salesperson” 및 “State”를 지정하려면 다음 URL을 사용합니다. 

```
https://app.powerbi.com/groups/me/rdlreports/xxxxxxx-abc7-40f0-b456-febzf9cdda4d?rp:Salesperson=Tie+Bear&rp:State=Utah 
```

앱의 보고서에 정의된 동일한 두 개의 매개 변수를 지정하려면 다음 URL을 사용합니다. 

```
https://app.powerbi.com/groups/me/apps/xxxxxxx-c4c4-4217-afd9-3920a0d1e2b0/rdlreports/b1d5e659-639e-41d0-b733-05d2bca9853c?rp:Salesperson=Tiggee&State=Utah 
```

매개 변수에 대해 null 값을 전달하려면 다음 구문을 사용합니다. 

```
parameter:isnull=true
```

예:

```
rp:SalesOrderNumber:isnull=true
```

부울 값을 전달하려면 false에 대해 0, true에 대해 1을 사용합니다. 부동 소수점 값을 전달하려면 서버 로캘의 소수 구분 기호를 포함합니다.

> [!NOTE]
> 보고서에 기본값이 있는 보고서 매개 변수가 포함되어 있고  **Prompt**  속성이  **false**(즉 보고서 관리자에서 **Prompt User** 속성을 선택하지 않음)이면 URL 내에서 해당 보고서 매개 변수에 대한 값을 전달할 수 없습니다. 이를 통해 관리자는 최종 사용자가 특정 보고서 매개 변수의 값을 추가하거나 수정하지 못하게 할 수 있습니다.

## <a name="additional-examples"></a>추가 예제 

다음 URL 예제에는 다중 값 매개 변수 “Salesperson”이 포함되어 있습니다. 다중 값 매개 변수의 형식은 각 값에 대해 매개 변수 이름을 반복하는 것입니다. 

```
https://app.powerbi.com/groups/me/rdlreports/xxxxxxx-abc7-40f0-b456-febzf9cdda4d?rp:Salesperson=Tie+Bear&rp:Salesperson=Mickey 
```

다음 URL 예제는 기본 모드 보고서 서버에 대해 값이 “7/1/2005”인 단일 매개 변수 of SellStartDate with를 전달합니다.

```
https://app.powerbi.com/groups/me/rdlreports/xxxxxxx-abc7-40f0-b456-febzf9cdda4d?rp:SellStartDate=7/1/2005
```

## <a name="next-steps"></a>다음 단계

- [Power BI에서 페이지를 매긴 보고서의 URL 매개 변수](report-builder-url-parameters.md)
- [Power BI Premium에서 페이지를 매긴 보고서란?](paginated-reports-report-builder-power-bi.md)