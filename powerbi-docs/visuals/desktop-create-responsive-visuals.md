---
title: 모든 크기의 Power BI 시각적 개체 최적화
description: Power BI 휴대폰 앱에 대해 Power BI Desktop 및 Power BI 서비스에서 기존 보고서의 시각적 개체를 최적화하는 방법을 알아봅니다.
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 04/13/2018
ms.author: mihart
LocalizationGroup: Create reports
ms.openlocfilehash: 4372f37cf6afc8fe51d6650ddd888bd41d3ea678
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2019
ms.locfileid: "54280128"
---
# <a name="optimize-a-power-bi-visual-for-any-size"></a>모든 크기의 Power BI 시각적 개체 최적화
기본적으로 새 보고서를 만들 때 시각적 개체는 ‘반응형’입니다. 화면 크기와 관계없이 최대 데이터양과 인사이트를 표시하도록 동적으로 변경됩니다. 이전 보고서의 경우에도 동적으로 크기를 조정하도록 시각적 개체를 설정할 수 있습니다.

시각적 개체 크기가 변경되면, Power BI는 데이터 보기의 우선 순위를 지정합니다. 예를 들어 패딩을 제거하고 범례를 시각적으로 맨 위로 자동으로 이동하여 시각적 개체 크기가 작아져도 정보를 계속 제공할 수 있도록 합니다. 응답성은 휴대폰에 있는 Power BI 모바일 앱의 시각적 개체에 특히 유용합니다.

![반응형 시각적 개체 크기 조정](media/desktop-create-responsive-visuals/power-bi-responsive-visual.gif)

X축 및 Y축과 슬라이서가 있는 시각적 개체는 반응에 따라 크기가 조정될 수 있습니다.

## <a name="turn-on-responsiveness-in-power-bi-desktop"></a>Power BI Desktop에서 반응형 켜기
1. Power BI Desktop의 이전 보고서에서는 **보기** 탭에서 **데스크톱 레이아웃**에 있는지 확인합니다.
   
    ![데스크톱 레이아웃 아이콘](media/desktop-create-responsive-visuals/power-bi-desktop-layout.png)
2. 시각적 개체를 선택하고 **시각화** 창에서 **서식** 섹션을 선택합니다.
3. **일반**을 확장하고 > **반응형**을 **켜기**로 밉니다.
   
    ![반응형 켜기](media/desktop-create-responsive-visuals/power-bi-turn-responsive-on.png)
   
     이제 [휴대폰에 최적화된 보고서를 만들고](../desktop-create-phone-report.md) 이 시각적 개체를 추가하면 적절하게 크기가 조정됩니다.

## <a name="turn-on-responsiveness-in-the-power-bi-service"></a>Power BI 서비스에서 반응형 켜기
Power BI 서비스에 있는 이전 보고서의 시각적 개체에 대해 반응형을 켤 수 있습니다. 보고서를 편집할 수 있어야 합니다.

1. Power BI 서비스([https://powerbi.com](https://powerbi.com))의 보고서에서 **보고서 편집**을 선택합니다.
2. 시각적 개체를 선택하고 **시각화** 창에서 **서식** 섹션을 선택합니다.
3. **일반**을 확장하고 > **반응형**을 **켜기**로 밉니다.
   
    ![반응형 켜기](media/desktop-create-responsive-visuals/power-bi-turn-responsive-on.png)
   
     이제 [이 보고서의 휴대폰 보기를 만들고](../desktop-create-phone-report.md) 이 시각적 개체를 추가하면 적절하게 크기가 조정됩니다.

## <a name="next-steps"></a>다음 단계
* [Power BI 전화 앱에 대해 최적화된 보고서 만들기](../desktop-create-phone-report.md)
* [휴대폰에 대해 최적화된 Power BI 보고서 보기](../consumer/mobile/mobile-apps-view-phone-report.md)
* 궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](http://community.powerbi.com/)

