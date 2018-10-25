---
title: 소비자용 Power BI 필터 창 개요
description: Power BI 서비스의 보고서 필터 창 개요
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 09/25/2018
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: c49e075bd7fbe2debb0b577a1ce2771491d5fac4
ms.sourcegitcommit: 52ac456bf2ac025b22ea634c28482f22e1cc19ac
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/10/2018
ms.locfileid: "48908282"
---
# <a name="take-a-tour-of-the-report-filters-pane"></a>보고서 필터 창 둘러보기
이 문서에서는 Power BI 서비스의 보고서 필터 창에 대해 알아봅니다.

Power BI에서 데이터를 필터링하는 다양한 방법이 있으며, [필터 및 강조 표시 정보](../power-bi-reports-filters-and-highlighting.md)를 먼저 읽어보는 것이 좋습니다.

![브라우저의 보고서](media/end-user-report-filter/power-bi-browser.png)

## <a name="working-with-the-report-filters-pane"></a>보고서 필터 창 작업
동료와 보고서를 공유할 때 **필터** 창을 찾습니다. 필터 창이 보고서의 오른쪽 가장자리를 따라 축소되는 경우가 있습니다. 축소된 창을 선택하여 확장합니다.   

![브라우저의 보고서](media/end-user-report-filter/power-bi-expanded.png)

필터 창에는 보고서 ‘디자이너’가 보고서에 추가한 필터가 포함되어 있습니다. ‘소비자’는 필터와 상호 작용하고 해당 변경 내용을 저장할 수 있지만 보고서에 새 필터를 추가할 수 없습니다.

Power BI 서비스에서 보고서는 필터 창에서 수행한 모든 변경 내용을 유지하고 해당 변경 내용이 보고서의 모바일 버전에 적용됩니다. 필터 창을 디자이너 기본값으로 다시 설정하려면 위의 메뉴 모음에서 **기본값으로 다시 설정**을 선택합니다.     

## <a name="open-the-filters-pane"></a>필터 창 열기
보고서가 열린 경우 필터 창은 보고서 캔버스의 오른쪽에 표시됩니다. 창이 표시되지 않는 경우 오른쪽 위 모서리의 화살표를 선택하여 확장합니다.  

이 예제에서 6개의 필터가 있는 시각적 개체를 선택했습니다. 보고서 페이지에도 필터가 있으며, **페이지 수준 필터** 머리글 아래 나열되어 있습니다. 하나의 [드릴스루 필터](../power-bi-report-add-filter.md)가 있으며 전체 보고서에도 필터가 있습니다. **FiscalYear**는 2013 또는 2014입니다.

![필터 목록](media/end-user-report-filter/power-bi-filter-list.png)

일부 필터는 필터 옆에 **All**이라는 단어가 있으며 이는 모든 값이 필터에 포함되고 있는 것을 의미합니다.  예를 들어 아래 스크린샷의 **Chain(All)** 은 이 보고서 페이지가 모든 상점 체인에 대한 데이터를 포함한다는 것을 알려줍니다.  반면 **FiscalYear는 2013 또는 2014입니다**의 보고서 수준 필터는 보고서가 2013 및 2014년의 회계 연도에 대한 데이터만을 포함한다는 것을 알려줍니다.

이 보고서를 보는 모든 사용자가 이 필터와 상호 작용할 수 있습니다.

* 필터 옆의 화살표를 마우스로 가리키고 선택하여 필터의 세부 정보를 봅니다.
  
   ![Lindseys가 선택된 상태로 표시](media/end-user-report-filter/power-bi-expan-filter.png)
* 필터를 변경합니다. 예를 들어 **Lindseys**를 **Fashions Direct**로 변경합니다.
  
     ![Fashions Direct가 선택된 상태로 표시](media/end-user-report-filter/power-bi-filter-chain.png)

* 위의 메뉴 모음에서 **기본값으로 다시 설정**을 선택하여 필터를 원래 상태로 다시 설정합니다.    
    ![기본값으로 다시 설정](media/end-user-report-filter/power-bi-reset-to-default.png)
    
* 필터 이름 옆의 **x**를 선택하여 필터를 삭제합니다.
  
  필터를 삭제하면 목록에서 제거하지만 보고서에서는 해당 데이터가 삭제되지 않습니다.  예를 들어 **FiscalYear는 2013 또는 2014입니다** 필터를 삭제하는 경우 회계 연도 데이터는 보고서에 그대로 유지되지만 2013 및 2014를 표시하도록 더 이상 필터링되지 않습니다. 데이터가 포함하는 모든 회계 연도를 표시합니다.  그러나 필터를 삭제하면 목록에서 제거되므로 다시 수정할 수 없습니다. 더 나은 옵션은 지우개 아이콘 ![지우개 아이콘](media/end-user-report-filter/power-bi-eraser-icon.png)을 선택하여 필터를 지우는 것입니다.
  
  ![x가 강조 표시됨](media/end-user-report-filter/power-bi-delete-filter.png)



## <a name="clear-a-filter"></a>필터 지우기
 고급 또는 기본 필터링 모드에서 지우개 아이콘  ![지우개 아이콘](media/end-user-report-filter/pbi_erasericon.jpg) 을 선택하여 필터를 지웁니다. 


## <a name="types-of-filters-text-field-filters"></a>필터 종류: 텍스트 필드 필터
### <a name="list-mode"></a>목록 모드
확인란을 선택/해제하여 값을 선택 또는 선택 취소합니다. **모두** 확인란은 모든 확인란의 상태를 켜기 또는 끄기로 전환하는 데 사용할 수 있습니다. 확인란은 해당 필드에 대해 사용 가능한 모든 값을 나타냅니다.  필터를 조정하면 선택 항목을 반영하도록 재작성이 업데이트됩니다. 

![목록 모드 필터](media/end-user-report-filter/pbi_restatement.png)

재작성에서 "is Amarilla or Carretera"라고 어떻게 말하는지 확인합니다.

### <a name="advanced-mode"></a>고급 모드
**고급 필터링**을 선택하여 고급 모드로 전환합니다. 드롭다운 컨트롤 및 텍스트 상자를 사용하여 포함할 필드를 식별합니다. **And** 및 **Or**중에서 선택하여 복잡한 필터 식을 작성할 수 있습니다. 원하는 값을 설정했으면 **필터 적용** 단추를 선택합니다.  

![고급 모드](media/end-user-report-filter/aboutfilters.png)

## <a name="types-of-filters-numeric-field-filters"></a>필터 종류: 숫자 필드 필터
### <a name="list-mode"></a>목록 모드
값이 한정된 경우 필드 이름을 선택하면 목록이 표시됩니다.  확인란 사용에 대한 도움말은 위의 **텍스트 필드 필터** &gt; **목록 모드**를 참조하세요.   

### <a name="advanced-mode"></a>고급 모드
값이 한정되지 않거나 범위를 나타내는 경우 필드 이름을 선택하면 고급 필터 모드가 열립니다. 드롭다운 및 텍스트 상자를 사용하여 표시할 값 범위를 지정합니다. 

![고급 필터](media/end-user-report-filter/pbi_dropdown-and-text.png)

**And** 및 **Or**중에서 선택하여 복잡한 필터 식을 작성할 수 있습니다. 원하는 값을 설정했으면 **필터 적용** 단추를 선택합니다.

## <a name="types-of-filters-date-and-time"></a>필터 종류: 날짜 및 시간
### <a name="list-mode"></a>목록 모드
값이 한정된 경우 필드 이름을 선택하면 목록이 표시됩니다.  확인란 사용에 대한 도움말은 위의 **텍스트 필드 필터** &gt; **목록 모드**를 참조하세요.   

### <a name="advanced-mode"></a>고급 모드
필드 값이 날짜 또는 시간을 나타내는 경우 날짜/시간 필터를 사용할 때 시작/끝 시간을 지정할 수 있습니다.  

![날짜/시간 필터](media/end-user-report-filter/pbi_date-time-filters.png)


## <a name="next-steps"></a>다음 단계
[보고서 페이지에서 시각적 개체가 서로 교차 필터링 및 교차 강조 표시되는 방식 및 이유 알아보기](end-user-interactions.md)