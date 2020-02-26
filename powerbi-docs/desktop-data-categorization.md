---
title: Power BI Desktop의 데이터 분류
description: Power BI Desktop의 데이터 분류
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/15/2020
ms.author: davidi
LocalizationGroup: Model your data
ms.openlocfilehash: 218a05c41c3befed8f8600f6a584560f5be92a1f
ms.sourcegitcommit: a1409030a1616027b138128695b80f6843258168
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76709559"
---
# <a name="specify-data-categories-in-power-bi-desktop"></a>Power BI Desktop에서 데이터 범주 지정
Power BI Desktop에서는 열의 *데이터 범주*를 지정하여 시각화에서 해당 값을 처리하는 방식을 Power BI Desktop에 알려줄 수 있습니다.

Power BI Desktop에서 데이터를 가져올 때는 데이터 자체가 아닌 테이블과 열 이름과 같은 다른 정보와 데이터가 기본 키인지 여부와 같은 정보를 가져옵니다. 이 정보로 Power BI Desktop이 시각화를 만들 때 어떻게 좋은 기본 환경을 만들 수 있는지를 짐작할 수 있습니다.
예를 들어 열에 숫자 값이 있는 경우 사용자가 어떤 방식으로든 열을 집계하려고 한다고 가정하고 Power BI Desktop이 열을 **시각화** 창의 **값** 영역에 배치합니다. 또는 꺾은선형 차트에 날짜 시간 값이 있는 경우 Power BI Desktop에서는 시간 계층 축으로 사용한다고 가정합니다.

그러나 지리 등, 다소 더 까다로운 경우도 있습니다. Excel 워크시트에서 다음 테이블을 고려해 보겠습니다.

![](media/desktop-data-categorization/datacategorizationtable.png)

Power BI Desktop이 **GeoCode** 열의 코드를 국가나 미국 주의 약자로 처리해야 하나요?  이 같은 코드는 여러 가지 중 하나를 의미하기 때문에 분명하지 않습니다. 예를 들어, AL은 알라바마 또는 알바니아가 될 수 있고 AR은 아칸사스나 아르헨티나가 될 수 있으며 CA는 캘리포니아나 캐나다가 될 수 있습니다. 지도에서 GeoCode 필드를 차트로 만들면 차이가 있습니다. 

Power BI Desktop이 국가가 강조 표시된 전 세계 그림을 표시해야 하나요? 또는 시/도가 강조 표시된 미국 그림을 표시해야 하나요?  이와 같은 데이터에 데이터 범주를 지정할 수 있습니다. 그러면 데이터 범주는 Power BI Desktop이 최고의 시각화를 제공하기 위해 사용할 수 있는 정보를 구체화합니다.  

**데이터 범주를 지정하려면**

1. **보고서** 보기 또는 **데이터** 보기의 **필드** 목록에서 다른 분류를 통해 정렬할 필드를 선택합니다.
2. 리본 메뉴의 **모델링** 탭의 **속성** 영역에서 **데이터 범주** 옆에 있는 드롭다운 화살표를 선택합니다.  이 목록에는 열에 대해 선택할 수 있는 데이터 범주가 표시됩니다. 열의 현재 데이터 형식에 적용되지 않는 일부 선택은 비활성화되어 있습니다.  예를 들어, 열이 이진 데이터 형식이라면 Power BI Desktop에서는 지리 데이터 범주를 선택할 수 없습니다. 
3. 원하는 범주를 선택하세요.

   ![](media/desktop-data-categorization/desktop-data-categorization.png)

[Power BI 모바일 앱용 지리 필터링](desktop-mobile-geofiltering.md)에 대해서도 자세히 알아보고 싶을 수 있습니다.

