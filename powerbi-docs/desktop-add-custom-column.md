---
title: "Power BI Desktop에서 사용자 지정 열 추가"
description: "Power BI Desktop에서 신속하게 새로운 사용자 지정 열 만들기"
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
ms.date: 01/24/2018
ms.author: davidi
ms.openlocfilehash: 9e2c5bb215ffee880af56a1147dcd4adfbbf17d5
ms.sourcegitcommit: 7249ff35c73adc2d25f2e12bc0147afa1f31c232
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2018
---
# <a name="add-a-custom-column-in-power-bi-desktop"></a>Power BI Desktop에서 사용자 지정 열 추가
**Power BI Desktop**에서 **쿼리 편집기**를 사용하여 새 사용자 지정 데이터 열을 모델에 쉽게 추가할 수 있습니다. 사용자 지정 열을 정의하는 [M 수식](https://msdn.microsoft.com/library/mt270235.aspx)을 만들 수 있는 간편한 단추를 사용하여 사용자 지정 열을 만들거나 이름을 바꿀 수 있습니다. M 수식에는 [포괄적인 함수 참조 콘텐츠 집합](https://msdn.microsoft.com/library/mt779182.aspx)이 있습니다. 

![](media/desktop-add-custom-column/add-custom-column_01.png)

사용자 지정 열을 만드는 작업은 **쿼리 편집기**에서 만든 쿼리에 대한 또 다른 **적용된 단계**입니다. 즉, 언제든지 변경하거나, 이전 또는 이후로 이동하거나, 수정할 수 있습니다.

## <a name="use-query-editor-to-add-a-new-custom-column"></a>쿼리 편집기를 사용하여 새 사용자 지정 열 추가
새 사용자 지정 열을 만들려면 **쿼리 편집기**를 실행합니다. **Power BI Desktop**의 **홈** 리본에서 **쿼리 편집**을 선택하여 이 작업을 수행할 수 있습니다.

![](media/desktop-add-custom-column/add-column-from-example_02.png)

**쿼리 편집기**를 실행하고 일부 데이터를 로드하고 나면 리본에서 **열 추가** 탭을 선택한 후 **사용자 지정 열**을 선택하여 사용자 지정 열을 추가할 수 있습니다.

![](media/desktop-add-custom-column/add-custom-column_02.png)

이 작업을 수행할 때 표시되는 **사용자 지정 열 추가** 창에 대한 내용은 다음 섹션에서 설명합니다.

## <a name="the-add-custom-column-window"></a>사용자 지정 열 추가 창
**사용자 지정 열 추가** 창에는 오른쪽 창에 사용 가능한 필드 목록이 표시되고, 위쪽에 사용자 지정 열의 이름이 표시되며(해당 텍스트 상자에 새 이름을 입력하기만 하면 이름을 바꿀 수 있음), [**M** 수식](https://msdn.microsoft.com/library/mt779182.aspx)이 표시됩니다. 이 수식은 오른쪽에서 필드를 삽입하거나, 연산자를 추가하거나, 새 사용자 지정 열을 정의할 때 사용되는 수식을 작성하는 방법으로 만들거나 작성할 수 있습니다. 

![](media/desktop-add-custom-column/add-custom-column_03.png)

## <a name="create-formulas-for-your-custom-column"></a>사용자 지정 열의 수식 만들기
오른쪽에 있는 **사용 가능한 열:** 목록에서 필드를 선택하고 **<< 삽입**을 선택하여 사용자 지정 열 수식에 추가할 수 있습니다. 간단하게 목록에서 열을 두 번 클릭하여 추가할 수도 있습니다.

수식을 입력하고 열을 작성할 때 발견된 구문 오류가 있는지 여부를 실시간으로(입력할 때) 알려주는 표시기가 창 아래쪽에 표시됩니다. 오류가 없으면 녹색 확인 표시가 표시됩니다.

![](media/desktop-add-custom-column/add-custom-column_04.png)

하지만 구문에 몇 가지 오류가 있을 경우 발견된 오류와 함께 노란색 경고 아이콘이 표시되고, 수식에서 오류가 발견된 위치로 커서를 이동하는 링크가 표시됩니다.

![](media/desktop-add-custom-column/add-custom-column_05.png)

**확인**을 선택하면 모델에 사용자 지정 열이 추가되고 쿼리의 **적용된 단계**에 **추가된 사용자 지정 항목** 단계가 추가됩니다.

![](media/desktop-add-custom-column/add-custom-column_06.png)

**적용된 단계** 창에서 **추가된 사용자 지정 항목** 단계를 두 번 클릭하면 **사용자 지정 열 추가** 창이 다시 나타나는데, 사용자가 만든 사용자 지정 열 수식이 이미 로드되어 있어 필요에 따라 수정할 수 있습니다.

## <a name="using-the-advanced-editor-for-custom-columns"></a>고급 편집기를 사용하여 사용자 지정 열 만들기
또한 **고급 편집기**를 사용하여 사용자 지정 열을 만들 수도 있습니다(그리고 이 경우 쿼리 단계 수정 가능). **쿼리 편집기**에서 **보기** 탭을 선택한 후 **고급 편집기**를 선택하면 **고급 편집기**가 표시됩니다.

![](media/desktop-add-custom-column/add-custom-column_07.png)

**고급 편집기**는 쿼리에 대한 모든 권한을 제공합니다.

## <a name="next-steps"></a>다음 단계
**쿼리 편집기**에 제공한 예제를 기준으로 열을 만드는 등 사용자 지정 열을 만드는 다른 방법도 있습니다. 예제로 사용자 지정 열을 만드는 방법에 자세한 내용은 다음 문서를 참조하세요.

* [Power BI Desktop에서 예제로 열 추가](desktop-add-column-from-example.md)
* [M 수식 언어 소개](https://msdn.microsoft.com/library/mt270235.aspx)
* [M 함수 참조](https://msdn.microsoft.com/library/mt779182.aspx)  

