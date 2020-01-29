---
title: 페이지를 매긴 보고서를 인쇄할 때 빈 페이지 방지
description: 인쇄할 때 빈 페이지를 방지하도록 페이지를 매긴 보고서를 디자인하기 위한 지침
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.date: 01/14/2020
ms.author: v-pemyer
ms.openlocfilehash: 76d1631b95c30d5ae56ced5d64e5174f6f9db759
ms.sourcegitcommit: 0ae9328e7b35799d5d9613a6d79d2f86f53d9ab0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2020
ms.locfileid: "76041868"
---
# <a name="avoid-blank-pages-when-printing-paginated-reports"></a>페이지를 매긴 보고서를 인쇄할 때 빈 페이지 방지

이 문서에서는 독자가 Power BI [페이지를 매긴 보고서](../paginated-reports-report-builder-power-bi.md)를 디자인하는 보고서 작성자라고 가정하고, PDF 또는 Microsoft Word 등의 하드 페이지 형식으로 보고서를 내보낼 때 빈 페이지를 방지하는 데 도움이 되는 권장 사항을 제공합니다.

## <a name="page-setup"></a>페이지 설정

보고서 페이지 크기 속성은 페이지 방향, 크기, 여백을 결정합니다. 이러한 보고서 속성에 액세스하는 방법은 다음과 같습니다.

- 보고서 **속성 페이지** 사용: 보고서 캔버스 밖의 진한 회색 영역을 마우스 오른쪽 단추로 클릭한 다음 _보고서 속성_을 선택합니다.
- [**속성** 창](../paginated-reports-report-design-view.md#4-properties-pane) 사용: 보고서 캔버스 밖의 진한 회색 영역을 클릭하여 보고서 개체를 선택합니다. **속성** 창이 열려 있어야 합니다.

보고서 **속성 페이지**의 **페이지 설정** 페이지는 페이지 설정 속성을 보고 업데이트할 수 있는 친숙한 인터페이스를 제공합니다.

![그림은 페이지 설정 페이지가 강조 표시된 보고서 속성 창을 보여 줍니다.](media/report-paginated-blank-page/report-page-setup-properties.png)

모든 페이지 크기 속성이 올바르게 구성되어 있는지 확인합니다.

|속성|권장|
|---------|---------|
|페이지 단위|관련 단위(인치 또는 센티미터)를 선택합니다.|
|방향|올바른 옵션(세로 또는 가로)을 선택합니다.|
|용지 크기|페이지 크기를 선택하거나 사용자 지정 너비 및 높이 값을 할당합니다.|
|여백|왼쪽, 오른쪽, 위쪽 및 아래쪽 여백에 적절한 값을 설정합니다.|
|||

## <a name="report-body-width"></a>보고서 본문 너비

페이지 크기 속성은 보고서 개체에 사용할 수 있는 공간을 결정합니다. 보고서 개체는 데이터 영역, 데이터 시각화 또는 기타 보고서 항목일 수 있습니다.

빈 페이지가 출력되는 일반적인 이유는 보고서 본문 너비가 _사용 가능한 페이지 공간을 초과_하기 때문입니다.

보고서 본문 너비는 **속성**창을 사용해야만 보고 설정할 수 있습니다. 먼저 보고서 본문의 빈 영역 아무 곳이나 클릭합니다.

![그림은 보고서 본문 너비 속성이 강조 표시된 속성 창을 보여 줍니다.](media/report-paginated-blank-page/report-body-properties-width.png)

너비 값이 사용 가능한 페이지 너비를 초과하지 않는지 확인합니다. 다음 수식에 따릅니다.

```Report body width <= Report page width - (Left margin + Right margin)```

> [!NOTE]
> 제거하려는 공간에 이미 보고서 개체가 있으면 보고서 본문 너비를 줄일 수 없습니다. 너비를 줄이려면 먼저 해당 개체의 위치 또는 크기를 조정해야 합니다.
>
> 또한 새 개체를 추가하거나 기존 개체의 크기나 위치를 조정하면 보고서 본문 너비가 자동으로 증가할 수 있습니다. 보고서 디자이너는 포함된 개체의 위치와 크기에 맞게 항상 본문 너비를 늘립니다.

## <a name="report-body-height"></a>보고서 본문 높이

빈 페이지가 출력되는 또 다른 이유는 보고서 본문에서 마지막 개체 뒤에 초과 공백이 있기 때문입니다.

항상 본문의 높이를 줄여 후행 공백을 제거하는 것이 좋습니다.

![그림은 보고서 디자인을 보여 줍니다. 테이블릭스 데이터 영역 아래의 공간이 강조 표시되고 불필요한 것으로 표시되어 있습니다.](media/report-paginated-blank-page/report-body-remove-trailing-space.png)

## <a name="page-break-options"></a>페이지 나누기 옵션

각 데이터 영역과 데이터 시각화에는 페이지 나누기 옵션이 있습니다. 이러한 옵션은 해당 속성 페이지 또는 **속성** 창에서 액세스할 수 있습니다.

**뒤에 페이지 나누기 추가** 속성이 불필요하게 사용 설정되어 있지 않아야 합니다.

![그림은 테이블릭스 속성 창을 보여 줍니다. “뒤에 페이지 나누기 추가” 속성이 사용 설정되어 있습니다.](media/report-paginated-blank-page/data-region-page-break-option-after.png)

## <a name="consume-container-whitespace"></a>컨테이너 공백 사용

빈 페이지 문제가 계속되면 보고서 **ConsumeContainerWhitespace** 속성을 사용하지 않도록 설정해 볼 수도 있습니다. 이 속성은 **속성** 창에서만 설정할 수 있습니다.

![그림은 ConsumeContainerWhitespace 속성이 강조 표시된 속성 창을 보여 줍니다.](media/report-paginated-blank-page/report-properties-consumecontainerwhitespace.png)

이 속성은 기본적으로 사용하도록 설정되어 있습니다. 이 속성은 보고서 본문이나 사각형 등으로 컨테이너의 최소 공백을 사용해야 하는지 여부를 지정합니다. 내용 오른쪽과 아래의 공백만 영향을 받습니다.

## <a name="printer-paper-size"></a>프린터 용지 크기

마지막으로 보고서를 용지로 인쇄하는 경우, 프린터에 올바른 용지가 로드되어 있는지 확인합니다. 물리적인 용지 크기는 [보고서 페이지 크기](#page-setup)와 일치해야 합니다.

## <a name="next-steps"></a>다음 단계

이 문서와 관련된 보다 자세한 내용을 알아보려면 다음 리소스를 참조하세요.

- [Power BI Premium에서 페이지를 매긴 보고서란?](../paginated-reports-report-builder-power-bi.md)
- [Power BI 페이지를 매긴 보고서의 페이지 매김](../paginated-reports-pagination.md)
- 질문이 있으십니까? [Power BI 커뮤니티에 질문하세요.](https://community.powerbi.com/)
- 제안? [Power BI 개선을 위한 아이디어 제공](https://ideas.powerbi.com)
