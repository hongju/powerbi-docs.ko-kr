---
title: Power BI Desktop의 식 기반 제목
description: Power BI Desktop에서 변경 하는 프로그래밍 방식으로 식을 기반으로 프로그래밍 방식으로 조건부 서식을 사용 하 여 동적 제목 만들기
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: reference
ms.date: 04/10/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: b90ef66d2c118a70f1b18ed4fe302ce1db23e45c
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "64769750"
---
# <a name="expression-based-titles-in-power-bi-desktop"></a>Power BI Desktop의 식 기반 제목

Power BI 시각적 개체를 위한 동적 사용자 지정 제목을 만들 수 있습니다. 필드, 변수 또는 기타 프로그래밍 요소에 기반한 데이터 분석 식(DAX)을 작성함으로써 시각적 개체의 제목을 필요에 따라 자동으로 조정할 수 있습니다. 이러한 변경 내용은 필터, 선택 항목 또는 다른 사용자 상호 작용 및 구성을 기반으로 합니다.

![Power BI Desktop 스크린샷 조건부 서식 지정 옵션](media/desktop-conditional-formatting-visual-titles/expression-based-title-01.png)

동적 제목 작성 라고도 *제목 식 기반*, 간단 합니다. 

## <a name="create-a-field-for-your-title"></a>제목에 대한 필드 만들기

식 기반 제목을 만드는 첫 번째 단계는 제목에 사용할 필드를 모델에서 만드는 것입니다. 

말하고 싶은 것, 혹은 표현하고 싶은 것을 시각화 개체의 제목에 반영하는 여러 가지 창조적인 방법이 있습니다. 몇 가지 예를 살펴보겠습니다.

제품의 브랜드 이름에 대해 시각적 개체가 수신하는 필터 컨텍스트를 기반으로 변경되는 식을 만들 수 있습니다. 다음 이미지에서는 이러한 필드에 대한 DAX 수식을 보여줍니다.

![스크린 샷의 DAX 수식](media/desktop-conditional-formatting-visual-titles/expression-based-title-02.png)

또 다른 예로 사용자의 언어 또는 문화권에 따라 변경 되는 동적 제목을 사용 합니다. 언어별 제목 DAX 측정값에서 사용 하 여 만들 수 있습니다는 `USERCULTURE()` 함수입니다. 이 함수에는 운영 체제 또는 브라우저 설정에 따라 사용자에 대 한 문화권 코드를 반환 합니다. 올바른 변환 된 값을 선택 하려면 다음 DAX switch를 사용할 수 있습니다. 

```
SWITCH (
  USERCULTURE(),
  "de-DE", “Umsatz nach Produkt”,
  "fr-FR", “Ventes par produit”,
  “Sales by product”
)
```

또는 모든 번역을 포함하는 조회 테이블에서 문자열을 검색할 수 있습니다. 모델에 해당 테이블을 추가합니다. 

이들은 Power BI Desktop에서 시각화 개체에 대해 동적, 식 기반 제목을 만드는 데 사용할 수 있는 몇 가지 예입니다. 제목을 사용하여 수행할 수 있는 작업은 여러분의 상상 및 모델에 의해서만 제한됩니다.


## <a name="select-your-field-for-your-title"></a>제목에 대한 필드를 선택합니다.

모델에서 만든 필드에 대한 DAX 식을 작성한 후에 시각적 개체의 제목에 적용해야 합니다.

필드를 선택하고 적용하려면 **시각화** 창으로 이동합니다. **서식** 영역에서 **제목**을 선택하여 시각적 개체에 대한 제목 옵션을 표시합니다. 

**제목 텍스트**를 마우스 오른쪽 버튼으로 클릭하면 **fx 조건부 서식**을 선택할 수 있는 상황에 맞는 메뉴가 나타납니다. 해당 메뉴 항목을 선택하는 경우 **제목 텍스트** 대화 상자가 나타납니다. 

![스크린 샷의 제목 텍스트 대화 상자](media/desktop-conditional-formatting-visual-titles/expression-based-title-02b.png)

해당 창에서 사용자가 만든 제목에 사용할 필드를 선택할 수 있습니다.

## <a name="limitations-and-considerations"></a>제한 사항 및 고려 사항

시각적 개체에 대한 식 기반 제목의 현재 구현에 몇 가지 제한이 있습니다.

* 식 기반 제목 형식은 Python 시각적 개체, R 시각적 개체 또는 주요 영향 요인 시각적 개체에서 현재 지원되지 않습니다.
* 제목에 대해 만든 필드는 문자열 데이터 형식이어야 합니다. 숫자 또는 날짜/시간(또는 다른 데이터 형식)을 반환하는 측정값은 현재 지원되지 않습니다.

## <a name="next-steps"></a>다음 단계

이 문서에서는 사용자가 보고서를 조작할 때 변경할 수 있는 동적 필드로 시각적 개체의 제목을 설정 하는 DAX 식을 만드는 방법을 설명 합니다. 유용할 수 있습니다 다음 문서도 합니다.

* [Power BI Desktop에서 교차 보고서 드릴스루 사용](desktop-cross-report-drill-through.md)
* [Power BI Desktop에서 드릴스루 사용](desktop-drillthrough.md)