---
title: Power BI Desktop의 식 기반 제목
description: Power BI Desktop에서 조건부 프로그래밍 서식을 사용하여 프로그래밍 식에 따라 변경되는 동적 제목 만들기
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: reference
ms.date: 04/10/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 7917edc17bd93d96c22641b14c4c70bfe3222e10
ms.sourcegitcommit: ba95d4979f1869f49a7d266c591f95e2810fdb29
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/19/2019
ms.locfileid: "69621263"
---
# <a name="expression-based-titles-in-power-bi-desktop"></a>Power BI Desktop의 식 기반 제목

Power BI 시각적 개체의 동적 사용자 지정 제목을 만들 수 있습니다. 필드, 변수 또는 기타 프로그래밍 요소를 기반으로 하는 DAX(Data Analysis Expression)를 만들면 시각적 개체의 제목이 필요에 따라 자동으로 조정될 수 있습니다. 이러한 변경은 필터, 선택 항목 또는 기타 사용자 조작과 구성을 기반으로 합니다.

![Power BI Desktop 조건부 서식 옵션 스크린샷](media/desktop-conditional-formatting-visual-titles/expression-based-title-01.png)

‘식 기반 제목’이라고도 하는 동적 제목을 만드는 방법은 간단합니다.  

## <a name="create-a-field-for-your-title"></a>제목에 사용할 필드 만들기

식 기반 제목을 만드는 첫 번째 단계는 제목에 사용할 필드를 모델에 만드는 것입니다. 

시각적 개체 제목에 표시할 내용이나 표현하려는 내용을 반영하는 모든 종류의 창의적인 방법이 있습니다. 몇 가지 예를 살펴보겠습니다.

시각적 개체가 제품의 브랜드 이름으로 받는 필터 컨텍스트에 따라 변경되는 식을 만들 수 있습니다. 다음 이미지는 이러한 필드의 DAX 수식을 보여 줍니다.

![DAX 수식 스크린샷](media/desktop-conditional-formatting-visual-titles/expression-based-title-02.png)

또 다른 예는 사용자의 언어 또는 문화권에 따라 변경되는 동적 제목을 사용하는 것입니다. `USERCULTURE()` 함수를 사용하여 DAX 측정값에 언어별 제목을 만들 수 있습니다. 이 함수는 해당 운영 체제 또는 브라우저 설정에 따라 사용자의 문화권 코드를 반환합니다. 다음 DAX switch 문을 사용하여 올바른 번역된 값을 선택할 수 있습니다. 

```
SWITCH (
  USERCULTURE(),
  "de-DE", “Umsatz nach Produkt”,
  "fr-FR", “Ventes par produit”,
  “Sales by product”
)
```

또는 모든 번역이 포함된 조회 테이블에서 문자열을 검색할 수 있습니다. 모델에 해당 테이블을 배치합니다. 

지금까지 살펴본 것은 Power BI Desktop에서 시각적 개체의 동적 식 기반 제목을 만드는 데 사용할 수 있는 몇 가지 예일 뿐입니다. 모델이 허용하는 범위 내에서 아무 제약 없이 창의적인 제목을 만들 수 있습니다.


## <a name="select-your-field-for-your-title"></a>제목에 사용할 필드 선택

모델에 만든 필드의 DAX 식을 만들었으면 시각적 개체의 제목에 적용해야 합니다.

필드를 선택하고 적용하려면 **시각화** 창으로 이동합니다. **서식** 영역에서 **제목**을 선택하여 시각적 개체의 제목 옵션을 표시합니다. 

**제목 텍스트**를 마우스 오른쪽 단추로 클릭하면 상황에 맞는 메뉴가 나타나며, 여기서 **<em>fx</em>조건부 서식 지정**을 선택할 수 있습니다. 해당 메뉴 항목을 선택하면 **제목 텍스트** 대화 상자가 나타납니다. 

![제목 텍스트 대화 상자 스크린샷](media/desktop-conditional-formatting-visual-titles/expression-based-title-02b.png)

이 창에서 제목에 사용하기 위해 만든 필드를 선택할 수 있습니다.

## <a name="limitations-and-considerations"></a>제한 사항 및 고려 사항

시각적 개체에 대한 식 기반 제목의 현재 구현에는 몇 가지 제한 사항이 있습니다.

* 식 기반 서식은 현재 Python 시각적 개체, R 시각적 개체 또는 주요 인플루언서 시각적 개체에서 지원되지 않습니다.
* 제목을 위해 만든 필드는 문자열 데이터 형식이어야 합니다. 숫자, 날짜/시간 또는 기타 데이터 형식을 반환하는 측정값은 현재 지원되지 않습니다.
* 시각적 개체를 대시보드에 고정하면 식 기반 제목이 전달되지 않습니다.

## <a name="next-steps"></a>다음 단계

이 문서에서는 사용자가 보고서를 조작할 때 변경될 수 있는 동적 필드로 시각적 개체의 제목을 바꾸는 DAX 식을 만드는 방법을 설명했습니다. 다음 문서도 유용할 수 있습니다.

* [테이블에서 조건부 서식 지정](desktop-conditional-table-formatting.md)
* [Power BI Desktop에서 교차 보고서 드릴스루 사용](desktop-cross-report-drill-through.md)
* [Power BI Desktop에서 드릴스루 사용](desktop-drillthrough.md)
