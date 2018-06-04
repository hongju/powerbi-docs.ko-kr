---
title: Power BI 전화 앱에 대해 최적화된 보고서 만들기
description: Power BI 전화 앱에 대해 Power BI Desktop에서 보고서 페이지를 최적화하는 방법을 알아봅니다.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 05/17/2018
ms.author: maggies
LocalizationGroup: Create reports
ms.openlocfilehash: 6ac85bcaba34f705b0f21efc86ed1583e69c8c2c
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34721067"
---
# <a name="create-reports-optimized-for-the-power-bi-phone-apps"></a>Power BI 전화 앱에 대해 최적화된 보고서 만들기
[Power BI Desktop에서 보고서를 만들](desktop-report-view.md) 때, 특별히 전화용으로 보고서를 만들어 전화에서 Mobile Apps로 사용하는 경험을 향상시킬 수 있습니다. 최적의 경험을 위해 시각적 개체를 어쩌면 모두 포함하지 않고 크기를 조정하고 정렬하여 휴대폰용 보고서를 조정합니다. 또한 휴대폰에서 볼 수 있도록 크기를 적절히 조정하는 [*반응형* 시각적 개체](#optimize-a-visual-for-any-size) 및 [반응형 슬라이서](#enhance-slicers-to-to-work-well-in-phone-reports)를 만들 수 있습니다. 또한 보고서에 필터를 추가하는 경우 해당 필터는 휴대폰 보고서에 자동으로 나타납니다. 보고서 구독자는 해당 필터를 확인하고 해당 필터로 보고서를 필터링할 수 있습니다.

![휴대폰에 최적화된 보고서](media/desktop-create-phone-report/desktop-create-phone-report-1.png)

## <a name="lay-out-a-report-page-for-the-phone-in-power-bi-desktop"></a>Power BI Desktop에서의 전화용 보고서 페이지 레이아웃
[Power BI Desktop에서 보고서를 만든](desktop-report-view.md) 후, 전화용으로 최적화할 수 있습니다.

1. Power BI Desktop의 왼쪽 탐색 모음에서 **보고서 보기**를 선택합니다.
   
    ![보고서 보기 아이콘](media/desktop-create-phone-report/desktop-create-phone-report-2.png)
2. **보기** 탭에서 **휴대폰 레이아웃**을 선택합니다.  
   
    ![휴대폰 레이아웃 아이콘](media/desktop-create-phone-report/desktop-create-phone-report-3.png)
   
    빈 전화 캔버스가 표시됩니다. 원본 보고서 페이지의 모든 시각적 개체는 오른쪽의 시각화 창에 나열됩니다.
3. 전화 레이아웃에 시각적 개체를 추가하려면 시각화 창에서 전화 캔버스로 끌어옵니다.
   
    전화 보고서는 그리드 레이아웃을 사용합니다. 시각적 개체를 모바일 캔버스로 끌어오면 해당 그리드로 딸깍 소리를 내며 맞춰집니다.
   
    ![시각적 개체 끌어서 놓기](media/desktop-create-phone-report/desktop-create-phone-report-4.gif)
   
    마스터 보고서 페이지의 일부 또는 모든 시각적 개체를 전화 보고서 페이지에 추가할 수 있습니다. 각 시각적 개체는 한 번만 추가할 수 있습니다.
4. 그리드 위의 시각적 개체를 대시보드 및 모바일 대시보드 위의 타일에 대해서와 마찬가지로 크기를 조정할 수 있습니다.
   
   > [!NOTE]
   > 전화 보고서 그리드는 다양한 크기의 전화에 맞게 크기를 조정함으로써 보고서가 크고 작은 전화 화면에서 모두 잘 나옵니다.
   > 
   > 
   
   ![시각적 개체 크기 조정](media/desktop-create-phone-report/desktop-create-phone-report-5.gif)

## <a name="optimize-a-visual-for-any-size"></a>모든 크기에 대해 시각적 개체 최적화
대시보드 또는 보고서에서 시각적 개체를 *반응형*으로 설정하여 화면 크기와 상관없이 최대 데이터 양 및 정보를 표시하도록 동적으로 변경할 수 있습니다. 

시각적 개체 크기가 변경되면, Power BI는 데이터 보기의 우선 순위를 지정합니다. 예를 들어 패딩을 제거하고 범례를 시각적으로 맨 위로 자동으로 이동하여 시각적 개체 크기가 작아져도 정보를 계속 제공할 수 있도록 합니다.

![반응형 시각적 개체 크기 조정](media/desktop-create-phone-report/desktop-create-phone-report-6.gif)

각 시각적 개체에 대해 응답성을 사용하도록 설정할지 여부를 선택합니다. [시각적 개체 최적화](desktop-create-responsive-visuals.md)에 대해 자세히 알아보세요.

## <a name="considerations-when-creating-phone-report-layouts"></a>휴대폰 보고서 레이아웃을 만들 때 고려 사항
* 여러 페이지의 보고서인 경우 모든 페이지 또는 일부만 최적화할 수 있습니다. 
* 보고서 페이지에 대한 배경색을 정의한 경우 전화 보고서는 동일한 배경색을 갖게 됩니다.
* 전화에 대해서만 서식 지정 설정을 수정할 수 없습니다. 서식 지정은 마스터 및 모바일 레이아웃 간에 일관됩니다. 예를 들어 글꼴 크기는 같을 것입니다.
* 서식 지정, 데이터 집합, 필터 또는 기타 특성을 변경하는 것과 같이 시각적 개체를 변경하려면 일반 보고서 작성 모드로 돌아갑니다.
* Power BI는 모바일 앱에서 휴대폰 보고서에 대한 기본 제목 및 페이지 이름을 제공합니다. 보고서에 제목 및 페이지 이름에 대한 텍스트 시각적 개체를 만들었다면 전화 보고서에는 추가하지 않는 것이 좋습니다.     

## <a name="remove-a-visual-from-the-phone-layout"></a>전화 레이아웃에서 시각적 개체 제거
* 시각적 개체를 제거 하려면, 전화 캔버스에서 시각적 개체의 오른쪽 위에 있는 X를 클릭하거나 그것을 선택하고 **삭제**를 누릅니다.
  
   여기서 시각적 개체를 제거하면 휴대폰 레이아웃 캔버스에서만 제거됩니다. 시각적 개체와 원본 보고서가 영향을 받지 않습니다.
  
   ![시각적 개체 제거](media/desktop-create-phone-report/desktop-create-phone-report-7.gif)

## <a name="enhance-slicers-to-to-work-well-in-phone-reports"></a>전화 보고서에서 잘 작동하도록 슬라이서 강화
슬라이서는 보고서 데이터의 캔버스 상 필터링을 제공합니다. 일반 보고서 작성 모드에서 슬라이서를 디자인할 때 전화 보고서에서 더 유용하도록 슬라이서 설정을 일부 수정할 수 있습니다.

* 보고서를 읽는 사람이 항목을 하나만 또는 여러 개 선택할 수 있는지 결정합니다.
* 보고서를 보다 검색하기 쉽게 하려면 슬라이서 주위에 상자를 배치합니다.
* 슬라이서를 수직, 수평 또는 *반응형*이 되게 합니다. 

슬라이서를 반응형으로 설정하는 경우 크기와 셰이프를 변경함에 따라 더 많거나 적은 옵션이 표시됩니다. 길게, 짧게, 넓게 또는 좁게 적용할 수 있습니다. 충분히 작게 만드는 경우 보고서 페이지에 필터 아이콘만 표시됩니다. 

![Power BI 반응형 슬라이서](media/desktop-create-phone-report/desktop-create-phone-report-8.png)

[반응형 슬라이서 만들기](power-bi-slicer-filter-responsive.md)에 대해 자세히 알아보세요.

## <a name="publish-a-phone-report"></a>전화 보고서 게시
* 전화 버전의 보고서를 게시하려면 [주 보고서를 Power BI Desktop에서 Power BI 서비스에 게시](desktop-upload-desktop-files.md)하고 동시에 전화 버전을 게시합니다.
  
    [Power BI에서 공유 및 사용 권한](service-how-to-collaborate-distribute-dashboards-reports.md)에 대해 자세히 알아보세요.

## <a name="view-optimized-and-unoptimized-reports-on-a-phone"></a>전화로 최적화된 보고서와 최적화되지 않은 보고서 보기
전화 상의 Mobile Apps에서 Power BI는 최적화된 전화 보고서와 최적화되지 않은 전화 보고서를 자동으로 검색합니다. 전화에 최적화된 보고서가 있다면 Power BI 전화 앱은 전화 보고서 모드에서 보고서를 자동으로 엽니다.

전화에 최적화된 보고서가 없다면 보고서는 최적화되지 않은 가로 보기 화면으로 열립니다.  

휴대폰 보고서에서 휴대폰을 가로 보기 방향으로 바꿀 경우 보고서 최적화 여부에 상관없이 보고서는 최적화되지 않은 보기에서 원본 보고서 레이아웃으로 열립니다.

일부 페이지만 최적화하는 경우, 독자가 세로 보기 메시지를 보게 될 것이며 이는 보고서가 가로 보기로 사용 가능하다는 것을 의미합니다.

![최적화되지 않은 휴대폰 페이지](media/desktop-create-phone-report/desktop-create-phone-report-9.png)

보고서 독자는 전화를 옆으로 돌려 페이지를 가로 보기 모드로 볼 수 있습니다. [휴대폰에 대해 최적화된 Power BI 보고서와 상호 작용](mobile-apps-view-phone-report.md)하는 것은 어떤지에 대해 자세히 알아보세요.

## <a name="next-steps"></a>다음 단계
* [Power BI에서 대시보드 휴대폰 보기 만들기](service-create-dashboard-mobile-phone-view.md)
* [휴대폰에 대해 최적화된 Power BI 보고서 보기](mobile-apps-view-phone-report.md)
* [모든 크기에 최적화된 반응형 시각적 개체 만들기](desktop-create-responsive-visuals.md)
* 궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](http://community.powerbi.com/)

