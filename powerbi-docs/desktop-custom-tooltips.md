---
title: Power BI Desktop에서 도구 설명 사용자 지정
description: 끌어서 놓기를 사용하여 시각적 개체에 대한 사용자 지정 도구 설명 만들기
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/07/2019
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: d5259ba22287a8a2ade3107e4320c39713dcb45e
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "65239756"
---
# <a name="customizing-tooltips-in-power-bi-desktop"></a>Power BI Desktop에서 도구 설명 사용자 지정
도구 설명은 시각적 개체의 데이터 요소에 대한 자세한 컨텍스트 정보 및 세부 정보를 제공하는 세련된 방법입니다. 다음 이미지는 Power BI Desktop에서 차트에 적용되는 도구 설명을 보여 줍니다.

![기본 도구 설명](media/desktop-custom-tooltips/custom-tooltips-1.png)

시각화가 만들어질 때 기본 도구 설명은 데이터 요소 값 및 범주를 표시합니다. 사용자 지정 도구 설명은 추가 컨텍스트 및 시각적 개체를 보는 사용자에게 유용한 정보를 제공할 수 있습니다. 도구 설명 사용자 지정을 통해 도구 설명의 일부로 표시하는 추가 데이터 요소를 지정할 수 있습니다.

## <a name="how-to-customize-tooltips"></a>도구 설명을 사용자 지정하는 방법
사용자 지정된 도구 설명을 만드는 방법은 **필드** 영역 **시각화** 창의 **도구 설명** 영역에, 필드를 드래그하여 다음 그림과에서 같이 배치합니다. 다음 이미지에서 두 개의 필드가 **도구 설명** 영역에 배치되었습니다.

![도구 설명 필드 추가](media/desktop-custom-tooltips/custom-tooltips-2.png)

도구 설명에 필드가 추가된 후 시각화의 데이터 요소를 가리키면 도구 설명의 해당 필드에 대한 값을 표시합니다.

![사용자 지정 도구 설명](media/desktop-custom-tooltips/custom-tooltips-3.png)

## <a name="customizing-tooltips-with-aggregation-or-quick-calcs"></a>집계 또는 빠른 계산으로 도구 설명 사용자 지정
**도구 설명** 버킷에서 필드 옆의 화살표를 선택하고 사용 가능한 옵션에서 집계 함수를 선택하거나 빠른 계산으로 추가로 도구 설명을 사용자 지정할 수 있습니다. 

![빠른 계산을 포함한 도구 설명](media/desktop-custom-tooltips/custom-tooltips-4.png)

사용자 지정 하는 방법은 여러 가지 **도구 설명**을, 데이터 집합에에서 사용할 수 있는 모든 필드를 사용하여 빠른 정보 및 insights 대시보드 또는 보고서를 보는 사용자에 게 전달 하기 위해 사용할 니다.

