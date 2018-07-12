---
title: 보고서 페이지의 크기 변경
description: Power BI 보고서에서 페이지에 대한 표시 설정을 변경합니다.
author: mihart
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 01/24/2018
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: e4ffc542a9564ba3893245ef637b3edd01c38640
ms.sourcegitcommit: 127df71c357127cca1b3caf5684489b19ff61493
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/03/2018
ms.locfileid: "37598758"
---
# <a name="change-the-size-of-a-report-page"></a>보고서 페이지의 크기 변경
[이전 문서 및 비디오](power-bi-report-display-settings.md)에서는 Power BI 보고서에서 페이지 표시를 제어하는 두 가지 방법으로 **보기** 및 **페이지 크기**에 대해 알아보았습니다. 페이지 보기 및 페이지 크기는 Power BI 서비스와 Power BI Desktop 모두에서 사용할 수 있고 모양과 기능이 거의 동일하지만, 이 자습서에서는 Power BI 서비스를 사용하겠습니다.

### <a name="prerequisites"></a>필수 조건
- Power BI 서비스   
- [소매점 분석 샘플 보고서](sample-retail-analysis.md)

## <a name="first-lets-change-the-page-view-setting"></a>먼저, 페이지 보기 설정을 변경해보겠습니다.

1. 읽기용 보기 또는 편집용 보기에서 보고서를 열고 **새 상점**에 대한 보고서 탭을 선택합니다. 기본적으로 이 보고서 페이지는 **페이지에 맞춤** 설정을 사용하여 표시됩니다.  이 경우 페이지에 맞춤은 스크롤 막대 없이 보고서 페이지를 표시하지만 일부 세부 정보와 제목이 너무 작아서 읽을 수 없습니다.

   ![](media/power-bi-change-report-display-settings/pbi_fit_to_page.png)
2. 캔버스에서 시각화를 선택하지 않았는지 확인합니다. **보기** 를 선택하고 표시 옵션을 검토합니다.

   * 읽기용 보기에서 볼 수 있습니다.

     ![](media/power-bi-change-report-display-settings/power-bi-page-view-menu-new.png)
   * 편집용 보기에서 볼 수 있습니다.

     ![](media/power-bi-change-report-display-settings/power-bi-view-editing-view.png)

3. **실제 크기** 설정을 사용하면 페이지 모양이 어떻게 되는지 확인해보겠습니다.

   ![](media/power-bi-change-report-display-settings/power-bi-actal-size2.png)

   그다지 좋지 않습니다. 대시보드에 스크롤 막대가 이제 두 개 있습니다.
4. **너비에 맞추기**로 전환합니다.

   ![](media/power-bi-change-report-display-settings/pbi_fit_to_width.png)

   이제 스크롤 막대가 있지만 세부 정보를 읽는 것이 더 쉬워졌으므로 모양이 향상되었습니다.

## <a name="change-the-default-view-for-a-report-page"></a>보고서 페이지의 기본 보기 변경
보고서 *작성자*인 경우 보고서 페이지의 기본 보기를 변경할 수 있습니다. 다른 사용자와 보고서를 공유하는 경우 사용자가 설정한 보기를 사용하여 보고서 페이지가 열립니다. 보고서 *소비자*는 보기를 변경할 수 있지만 보고서 밖으로 나간 후에는 변경 내용을 저장할 수 없습니다.

1. 보고서의 **새 상점** 페이지에서 **실제 크기** 보기로 다시 전환합니다.

   ![](media/power-bi-change-report-display-settings/power-bi-actual-size.png)

2. **구역 월별 판매량** 보고서 페이지에서 보기를 **너비에 맞추기**로 설정합니다.

3. **개요** 보고서 페이지에서 기본 보기 설정을 그대로 둡니다.

4. 이제 **파일 > 저장**을 선택하여 보고서를 저장합니다. 다음에 이 보고서를 열면 새로운 보기 설정을 사용하여 페이지가 표시됩니다. 실제로 살펴보겠습니다.

   ![](media/power-bi-change-report-display-settings/power-bi-save.png)
3. 위쪽 탐색 모음에서 현재 작업 영역의 이름을 선택하여 해당 작업 영역으로 돌아갑니다.  

   ![](media/power-bi-change-report-display-settings/power-bi-my-workspace.png)
4. **보고서** 탭을 선택하고 동일한 보고서(소매점 분석 샘플)를 선택합니다.

    ![](media/power-bi-change-report-display-settings/power-bi-new-report2.png)
5. 보고서의 각 페이지를 열고 새로운 설정을 살펴봅니다.

   ![](media/power-bi-change-report-display-settings/power-bi-page-view.gif)

## <a name="now-lets-explore-the-page-size-setting"></a>이제 *페이지 크기* 설정을 살펴보겠습니다.
페이지 크기 설정은 [편집용 보기](service-interact-with-a-report-in-editing-view.md)에서만 사용할 수 있으므로 페이지 크기 설정을 변경하려면 보고서에 대한 편집(*작성자*) 권한이 필요합니다. [샘플](sample-datasets.md) 중 하나에 연결한 경우 해당 보고서에 대한 *작성자* 권한이 있습니다.

1. 편집용 보기에서 [소매점 분석 샘플](sample-retail-analysis.md)의 "지역 월간 판매량" 페이지를 엽니다.
2. 캔버스에서 시각화를 선택하지 않았는지 확인합니다.  **시각화** 창에서 페인트 롤러 아이콘 ![](media/power-bi-change-report-display-settings/power-bi-paintroller.png)을 선택합니다.
3. **페이지 크기** &gt; **형식**을 선택하여 페이지 크기 옵션을 표시합니다.

   ![](media/power-bi-change-report-display-settings/power-bi-page-size-menu-new.png)
4. **Letter**를 선택합니다.  캔버스에서 816 x 1056픽셀(Letter 크기) 내에 맞는 콘텐츠만 캔버스의 흰색 부분에 남아 있습니다.

   ![](media/power-bi-change-report-display-settings/power-bi-letter-new.png)
5. **페이지 크기** **16:9** 비율을 선택합니다.

   ![](media/power-bi-change-report-display-settings/power-bi-16-to-9-new.png)

   보고서 페이지의 너비:높이를 16:9로 표시합니다. 실제 사용되는 픽셀 크기를 보려면 회색 표시된 너비 및 높이 필드 (1280x720)를 확인합니다. 보고서 캔버스 주위에는 빈 공간이 많은데 이전에 **보기**를 "너비에 맞추기"로 설정했기 때문입니다.
7. **페이지 크기** 옵션을 계속 탐색합니다.

## <a name="use-page-view-and-page-size-together"></a>페이지 보기 및 페이지 크기를 함께 사용
보고서를 동료들과 공유하거나 다른 응용 프로그램에 포함하는 경우 페이지 보기 및 페이지 크기를 함께 사용하여 가장 잘 표시되는 보고서를 만듭니다.

이 연습에서는 너비가 500픽셀이고 높이가 750픽셀인 공간을 포함하는 응용 프로그램에 표시될 보고서 페이지를 만듭니다.

이전 단계에서 보고서 페이지가 너비 1280, 높이 720에 표시되는 것을 보았습니다. 따라서 시각적 개체를 모두 맞추려면 크기를 조정하고 정렬하는 작업을 많이 해야 합니다.

1. 현재 캔버스 영역의 절반 미만에 맞게 시각적 개체의 크기를 조정하고 이동합니다.

    ![](media/power-bi-change-report-display-settings/power-bi-custom-view.gif)
2. **페이지 크기** &gt; **사용자 지정**을 선택합니다.
3. 너비를 500으로 설정하고 높이를 750으로 설정합니다.

    ![](media/power-bi-change-report-display-settings/power-bi-custom-new.png)
4. 보고서 페이지가 가장 잘 표시되도록 조정합니다. **보기 > 실제 크기**와 **보기 > 페이지에 맞추기**를 전환하면서 조정합니다.

    ![](media/power-bi-change-report-display-settings/power-bi-final-new.png)

## <a name="next-steps"></a>다음 단계
[Cortana에 대한 보고서 만들기](service-cortana-answer-cards.md)

[Power BI 보고서의 페이지 표시 설정](power-bi-report-display-settings.md)으로 돌아가기

궁금한 점이 더 있나요? [Power BI 커뮤니티를 이용하세요.](http://community.powerbi.com/)
