---
title: Power BI에서 크기를 조정할 수 있는 반응형 슬라이서 만들기
description: 보고서에 맞게 크기를 조정할 수 있는 반응형 슬라이서를 만드는 방법을 알아봅니다.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/04/2018
ms.author: maggies
LocalizationGroup: Create reports
ms.openlocfilehash: fed4119946cb762fb4d9aee3b5300be225a6e379
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "61419829"
---
# <a name="create-a-responsive-slicer-you-can-resize-in-power-bi"></a>Power BI에서 크기를 조정할 수 있는 반응형 슬라이서 만들기

반응형 슬라이서 크기를 보고서 공간에 맞게 조정합니다. 반응형 슬라이서를 사용하면 가로부터 정사각형 및 세로까지 다양한 크기와 모양으로 크기를 변경할 수 있으며, 사용자가 조작하는 대로 슬라이서의 값이 자동으로 다시 정렬됩니다. Power BI Desktop 및 Power BI 서비스에서 수평 슬라이서 및 날짜/범위 슬라이서를 반응형으로 만들 수 있습니다. 또한 날짜/범위 슬라이서는 손끝으로 손쉽게 변경할 수 있도록 터치 영역이 개선되었습니다. 반응형 슬라이서를 원하는 대로 작게 또는 크게 변경할 수 있습니다. 그러면 Power BI 서비스 및 Power BI 모바일 앱의 보고서에 잘 맞도록 자동으로 크기가 변경됩니다. 

![다양한 모양이 될 수 있는 반응형 슬라이서](media/power-bi-slicer-filter-responsive/power-bi-slicer-filter-responsive-0-slicer.gif)

## <a name="create-a-slicer"></a>슬라이서 만들기

동적 슬라이서를 만드는 첫 번째 단계는 기본 슬라이서를 만드는 것입니다. 

1. **시각화** 창에서 **슬라이서** 아이콘 ![슬라이서 아이콘](media/power-bi-slicer-filter-responsive/power-bi-slicer-filter-responsive-0-slicer-icon.png)을 선택합니다.
2. 필터링할 필드를 **필드**로 끌어옵니다.

    ![슬라이서에 필드 추가](media/power-bi-slicer-filter-responsive/power-bi-slicer-filter-responsive-1-create.png)

## <a name="convert-to-a-horizontal-slicer"></a>가로 슬라이서로 변환

1. 선택한 슬러이서를 사용하여 **시각화** 창에서 **서식** 탭을 선택합니다.
2. **일반** 섹션을 확장한 다음 **방향**에서 **가로**를 선택합니다.

    ![슬라이서를 가로로 설정](media/power-bi-slicer-filter-responsive/power-bi-slicer-filter-responsive-2-horizontal.png) 

1.  더 많은 값을 표시하도록 더 넓게 표시할 수 있습니다.

     ![슬라이서를 더 넓게](media/power-bi-slicer-filter-responsive/power-bi-slicer-filter-responsive-3-wider.png)

## <a name="make-it-responsive-and-experiment-with-it"></a>반응형으로 전환 및 시험

이 단계는 쉽습니다. 

1. **서식** 탭의 **일반** 섹션에 있는 **방향** 바로 아래에서 **반응형**을 **켜기**로 밉니다.  

    ![슬라이서가 이제 반응함](media/power-bi-slicer-filter-responsive/power-bi-slicer-filter-responsive-4-responsive-on.png)

1. 이제 조작할 수 있습니다. 모서리를 끌어서 짧게, 높게, 넓게 및 좁게 만듭니다. 충분히 작게 만드는 경우 필터 아이콘만 표시됩니다.

    ![반응형 슬라이서가 너무 작으면 필터 아이콘이 됨](media/power-bi-slicer-filter-responsive/power-bi-slicer-filter-responsive-5-mini-icon.png)

## <a name="add-it-to-a-phone-report-layout"></a>휴대폰 보고서 레이아웃에 추가

Power BI Desktop에서는 보고서의 각 페이지에 대한 휴대폰 레이아웃을 만들 수 있습니다. 페이지에 휴대폰 레이아웃이 있는 경우 휴대폰에서 세로 보기로 표시됩니다. 그렇지 않은 경우 가로 보기로 봐야 합니다. 

1. **보기** 탭에서 **휴대폰 레이아웃**을 선택합니다.

     ![휴대폰 레이아웃 아이콘, 보기 메뉴](media/power-bi-slicer-filter-responsive/power-bi-slicer-filter-responsive-6-phone-layout-button.png)
    
1. 휴대폰 보고서에서 원하는 모든 시각적 개체를 그리드로 끌어 옵니다. 반응형 슬라이서를 끌 때 원하는 크기로 만듭니다. 이 경우에는 필터 아이콘입니다.

    ![휴대폰 보고서 레이아웃에 슬라이서 추가](media/power-bi-slicer-filter-responsive/power-bi-slicer-filter-responsive-7-phone-slicer-icon.png)

[Power BI 모바일 앱에 최적화된 보고서](desktop-create-phone-report.md) 만들기에 대한 자세한 내용을 읽어 보세요.

## <a name="make-a-time-or-range-slicer-responsive"></a>타일 또는 범위 슬라이서를 반응형으로 만들기

동일한 단계에 따라 시간 또는 범위 슬라이서를 반응형으로 만들 수 있습니다. **반응형**을 **켜기**로 설정한 후 다음과 같은 몇 가지를 확인할 수 있습니다.

- 시각적 개체는 캔버스에서 허용되는 크기에 따라 입력란의 순서를 최적화합니다. 
- 데이터 요소 표시는 캔버스에서 허용된 크기에 따라 슬라이서를 최대한 사용 가능하도록 최적화됩니다. 
- 슬라이더에서 새 라운드 핸들바는 터치 상호 작용을 최적화합니다. 
- 시각적 개체가 너무 작아서 유용하게 사용할 수 없는 경우 해당 위치에서 시각적 유형을 나타내는 아이콘이 됩니다. 이와 상호 작용하려면 두 번 탭하여 포커스 모드로 엽니다. 그러면 유용한 공간이 기능 손실 없이 보고서 페이지에 저장됩니다.

## <a name="next-steps"></a>다음 단계

- [Power BI 서비스의 슬라이서](visuals/power-bi-visualization-slicers.md)
- 궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](http://community.powerbi.com/)