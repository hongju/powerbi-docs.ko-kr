---
title: "Power BI Desktop의 데이터 분류"
description: "Power BI Desktop의 데이터 분류"
services: powerbi
documentationcenter: 
author: davidiseminger
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
ms.date: 12/06/2017
ms.author: davidi
ms.openlocfilehash: 733006c1fcec2b541e0f2e3011f4c1f631608698
ms.sourcegitcommit: d91436de68a0e833ecff18d976de9d9431bc4121
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/06/2017
---
# <a name="data-categorization-in-power-bi-desktop"></a>Power BI Desktop의 데이터 분류
**Power BI Desktop**에서는 열의 데이터 범주를 지정하여 시각화에서 해당 값을 처리하는 방식을 Power BI Desktop에 알려줄 수 있습니다.

Power BI Desktop이 데이터를 가져올 때는 데이터 자체만 가져오는 것이 아니라 테이블, 열 이름, 주요 키 여부 등과 같은 정보를 함께 가져옵니다.  이 정보로 Power BI Desktop이 시각화를 만들 때 어떻게 좋은 기본 환경을 만들 수 있는지를 짐작할 수 있습니다. 

다음 예에서는 Power BI Desktop이 열에 숫자 값이 있음을 감지하면 사용자가 어떤 식으로든 이를 집계하려 한다고 가정하고 값 열에 배치합니다. 또는 날짜 시간 값이 있는 열의 경우 꺾은선형 차트에서 시 계층 축으로 사용할 수 있다고 가정합니다.

그러나 지리 등, 다소 더 까다로운 경우도 있습니다. Excel 워크시트에서 다음 테이블을 고려해 보겠습니다.

![](media/desktop-data-categorization/datacategorizationtable.png)

Power BI Desktop이 GeoCode 열의 코드를 국가나 미국 주의 약자로 처리해야 합니까?  이 같은 코드는 여러 가지 중 하나를 의미하기 때문에 분명하지 않습니다.  예를 들어, AL은 알라바마 또는 알바니아가 될 수 있고 AR은 아칸사스나 아르헨티나가 될 수 있으며 CA는 캘리포니아나 캐나다가 될 수 있습니다. 지도에서 GeoCode 필드를 차트로 만들면 차이가 있습니다.  Power BI Desktop이 국가가 강조된 세계의 이미지를 표시해야 할까요 아니면 주가 강조된 미국의 이미지를 표시해야 할까요?  이같은 데이터에 데이터 범주를 지정할 수 있습니다. 그러면 데이터 범주는 Power BI Desktop이 최고의 시각화를 제공하기 위해 사용할 수 있는 정보를 구체화합니다.  

**데이터 범주를 지정하려면**

1. 보고서 뷰 또는 데이터 뷰의 **필드** 목록에서 다른 분류를 통해 정렬할 필드를 선택합니다.
2. 리본 메뉴의 **데이터 도구 모델링** 탭에서 **데이터 범주:** 드롭다운 목록을 클릭합니다.  그러면 열에 선택 가능한 데이터 범주의 목록이 표시됩니다.  열의 현재 데이터 형식에 적용되지 않는 일부 선택은 비활성화되어 있습니다.  예를 들어, 열이 이진 데이터 형식이라면 Power BI Desktop에서는 지리 데이터 범주를 선택할 수 없습니다. 

![](media/desktop-data-categorization/datacategorization.gif)

이것으로 끝입니다!  시각적 요소에 일반적으로 발생하는 모든 동작이 이제 자동으로 작동합니다.  

[Power BI 모바일 앱용 지리 필터링](desktop-mobile-geofiltering.md)에 대해서도 자세히 알아보고 싶을 수 있습니다.

