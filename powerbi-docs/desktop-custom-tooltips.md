---
title: Power BI Desktop에서 도구 설명 사용자 지정
description: 끌어서 놓기를 사용하여 시각적 개체에 대한 사용자 지정 도구 설명 만들기
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/15/2020
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 93177ac56bc2d8ecfe4b85f4ab66daef6bf0f0f3
ms.sourcegitcommit: 3d6b27e3936e451339d8c11e9af1a72c725a5668
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2020
ms.locfileid: "76161024"
---
# <a name="customize-tooltips-in-power-bi-desktop"></a>Power BI Desktop에서 도구 설명 사용자 지정

도구 설명은 시각적 개체의 데이터 요소에 대한 자세한 컨텍스트 정보 및 세부 정보를 제공하는 세련된 방법입니다. 다음 이미지는 Power BI Desktop에서 차트에 적용되는 도구 설명을 보여 줍니다.

![기본 도구 설명](media/desktop-custom-tooltips/custom-tooltips-1.png)

시각화가 만들어질 때 기본 도구 설명은 데이터 요소 값 및 범주를 표시합니다. 도구 설명 정보를 사용자 지정하면 유용한 경우가 많습니다. 도구 설명을 사용자 지정하면 시각적 개체를 보는 사용자에게 추가적인 컨텍스트와 정보를 제공할 수 있습니다. 사용자 지정 도구 설명을 통해 도구 설명의 일부로 표시하는 추가 데이터 요소를 지정할 수 있습니다.

## <a name="how-to-customize-tooltips"></a>도구 설명을 사용자 지정하는 방법

사용자 지정된 도구 설명을 만들려면 다음 그림과 같이 **시각화** 창의 **필드** 영역에서 **도구 설명** 버킷으로 필드를 끌어서 놓습니다. 다음 그림에서는 세 개의 필드가 **도구 설명** 버킷에 배치되었습니다.

![도구 설명 필드 추가](media/desktop-custom-tooltips/custom-tooltips-2.png)

도구 설명이 **도구 설명**에 추가된 후 시각화의 데이터 요소를 마우스로 가리키면 해당 필드의 값이 표시됩니다.

![사용자 지정 도구 설명](media/desktop-custom-tooltips/custom-tooltips-3.png)

## <a name="customizing-tooltips-with-aggregation-or-quick-measures"></a>집계 또는 빠른 측정으로 도구 설명 사용자 지정

집계 함수 또는 *빠른 측정*을 선택하여 도구 설명을 추가로 사용자 지정할 수 있습니다. **도구 설명** 버킷의 필드 옆에 있는 화살표를 선택합니다. 그런 다음 사용할 수 있는 옵션 중에서 선택합니다.

![빠른 측정을 포함한 도구 설명](media/desktop-custom-tooltips/custom-tooltips-4.png)

대시보드 또는 보고서를 보는 사용자에게 신속한 정보를 전달하기 위해 데이터 세트에서 사용할 수 있는 모든 필드를 사용하여 도구 설명을 사용자 지정하는 많은 방법이 있습니다.
