---
title: Power BI Desktop에서 보고서 테마 사용
description: Power BI Desktop에서 사용자 지정 색상표를 사용하고 전체 보고서에 적용하는 방법을 알아봅니다.
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/23/2020
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 5a4ed3ffc833b2405a3c231b80047c71b40a64cc
ms.sourcegitcommit: 08f65ea314b547b41b51afef6876e56182190266
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2020
ms.locfileid: "76753700"
---
# <a name="use-report-themes-in-power-bi-desktop"></a>Power BI Desktop에서 보고서 테마 사용

Power BI Desktop ‘보고서 테마’를 사용하여 회사 색을 사용하거나 아이콘 세트를 변경하거나 새로운 기본 시각적 개체 서식 지정을 적용하는 등의 디자인 변경 내용을 전체 보고서에 적용할 수 있습니다. 보고서 테마를 적용하면 보고서의 모든 시각적 개체는 선택한 테마의 색과 서식을 기본값으로 사용합니다. 몇 가지 예외가 적용되며 이에 대해서는 이 문서의 뒷부분에서 설명합니다.

![보고서 테마](media/desktop-report-themes/report-themes-1a.png)

보고서 테마의 유형은 다음과 같이 기본 제공 보고서 테마와 사용자 지정 보고서 테마 파일 두 가지입니다.

- 기본 제공 보고서 테마는 Power BI Desktop과 함께 설치된 다양한 종류의 미리 정의된 색 구성표를 제공합니다. 기본 제공 보고서 테마는 Power BI Desktop 메뉴에서 직접 선택합니다.

- 사용자 지정 보고서 테마 파일은 해당 기본 구조를 정의하는 JSON 파일에 생성되는 보고서 테마입니다. 사용자 지정 보고서 테마를 적용하려면 해당 JSON 파일을 Power BI Desktop으로 가져와 보고서에 적용합니다.

  [**테마 사용자 지정** 대화 상자](#create-and-customize-a-theme-in-power-bi-desktop-preview)를 사용하여 Power BI Desktop에서 기존 보고서 테마를 사용자 지정할 수도 있습니다.

**시각화** 창의 **서식** 섹션에 나열된 요소는 거의 모두 Power BI Desktop에서 직접 설정한 사용자 지정을 통해 또는 보고서 테마 JSON 파일을 통해 사용자 지정하고 표준화할 수 있습니다. 보고서의 기본 모양과 느낌을 세분화된 수준까지 완전히 제어할 수 있게 하는 것이 목표입니다.

## <a name="how-report-themes-work"></a>보고서 테마 작동 방법

Power BI Desktop 보고서에 보고서 테마를 적용하려면 [사용할 수 있는 기본 제공 보고서 테마](#built-in-report-themes) 중에서 선택하거나, [테마 사용자 지정 JSON 파일 가져오기](#import-custom-report-theme-files)를 하거나, [**테마 사용자 지정** 대화 상자](#create-and-customize-a-theme-in-power-bi-desktop-preview)를 사용할 수 있습니다.

사용자 지정할 수 있는 기본값에 대한 자세한 내용은 아래의 [보고서 테마 JSON 형식](#report-theme-json-file-format) 섹션을 확인하세요.

### <a name="built-in-report-themes"></a>기본 제공 보고서 테마

사용 가능한 기본 제공 보고서 테마에서 선택하려면 다음을 수행합니다.

1. **홈** 리본에서 **테마 전환**을 선택합니다.

   ![보고서 테마 선택](media/desktop-report-themes/report-themes-2a.png)

2. 드롭다운 메뉴에서 포함된 테마 중 하나를 선택합니다.

   이제 보고서 테마가 보고서에 적용됩니다.

다음 표에서는 사용 가능한 기본 제공 보고서 테마를 보여 줍니다.

| 기본 제공 보고서 테마 | 기본 색 시퀀스 |
|------ |---------- |
| 기본값 | ![기본값](media/desktop-report-themes/report-themes-color-scheme-default.png)|
| Highrise | ![Highrise](media/desktop-report-themes/report-themes-color-scheme-highrise.png)|
| 경영진 | ![경영진](media/desktop-report-themes/report-themes-color-scheme-executive.png)|
| Frontier| ![Frontier](media/desktop-report-themes/report-themes-color-scheme-frontier.png)|
| 혁신 | ![혁신](media/desktop-report-themes/report-themes-color-scheme-innovative.png)|
| Bloom | ![Bloom](media/desktop-report-themes/report-themes-color-scheme-bloom.png)|
| Tidal| ![Tidal](media/desktop-report-themes/report-themes-color-scheme-tidal.png)|
| 온도 | ![온도](media/desktop-report-themes/report-themes-color-scheme-temperature.png)|
| Solar| ![Solar](media/desktop-report-themes/report-themes-color-scheme-solar.png)|
| Divergent | ![Divergent](media/desktop-report-themes/report-themes-color-scheme-divergent.png)|
| Storm | ![Storm](media/desktop-report-themes/report-themes-color-scheme-storm.png)|
| Classic | ![Classic](media/desktop-report-themes/report-themes-color-scheme-classic.png)|
| 도시 공원 | ![도시 공원](media/desktop-report-themes/report-themes-color-scheme-city-park.png)|
| 교실 | ![교실](media/desktop-report-themes/report-themes-color-scheme-classroom.png)|
| 색맹 지원 | ![색맹 지원](media/desktop-report-themes/report-themes-color-scheme-colorblind-safe.png)|
| 일렉트로닉 | ![일렉트로닉](media/desktop-report-themes/report-themes-color-scheme-electric.png)|
| 고대비 | ![고대비](media/desktop-report-themes/report-themes-color-scheme-high-contrast.png)|
| 일몰 | ![일몰](media/desktop-report-themes/report-themes-color-scheme-sunset.png)|
| 석양 | ![석양](media/desktop-report-themes/report-themes-color-scheme-twilight.png)|

## <a name="customize-report-themes"></a>보고서 테마 사용자 지정

Power BI Desktop의 2019년 12월 릴리스부터 다음 두 가지 방법으로 보고서 테마를 사용자 지정할 수 있습니다.

- [Power BI Desktop에서 테마 만들기 및 사용자 지정(미리 보기)](#create-and-customize-a-theme-in-power-bi-desktop-preview)
- [사용자 지정 보고서 테마 JSON 파일 만들기 및 사용자 지정](#introduction-to-report-theme-json-files)

### <a name="create-and-customize-a-theme-in-power-bi-desktop-preview"></a>Power BI Desktop에서 테마 만들기 및 사용자 지정(미리 보기)

Power BI Desktop의 2019년 12월 릴리스부터 Power BI Desktop에서 직접 테마를 사용자 지정하는 기능이 미리 보기 방식으로 제공됩니다.

Power BI Desktop에서 직접 테마를 사용자 지정하려면 다음을 수행합니다.

1. **파일** > **옵션 및 설정** > **옵션**을 선택합니다.

2. **미리 보기 기능** 섹션에서 **현재 테마 사용자 지정**을 선택하고 **확인**을 선택합니다.

   ![사용자 지정 테마 사용](media/desktop-report-themes/report-themes_5a.png)

   미리 보기 기능을 사용하려면 Power BI Desktop을 다시 시작하라는 메시지가 표시될 수 있습니다. 다시 시작하면 현재 적용된 테마에 대한 사용자 지정을 시작할 수 있습니다.

3. **홈** 리본에서 **테마 전환** > **현재 테마 사용자 지정**을 선택합니다.

   현재 보고서에 적용된 보고서의 테마를 사용자 지정하는 방법이 표시된 대화 상자가 나타납니다.

   ![테마 사용자 지정](media/desktop-report-themes/report-themes_5b.png)

4. 기존 테마가 마음에 들어 몇 가지 사항만 조정하려면 테마를 선택하거나 가져온 다음에 **현재 테마 사용자 지정**을 선택합니다.

   ![현재 테마 사용자 지정](media/desktop-report-themes/report-themes_5c.png)

사용자 지정할 수 있는 테마 설정은 다음 범주로 제공되며, **테마 사용자 지정** 창에 반영됩니다.

- **이름 및 색**: 테마 이름 및 색 설정에는 [테마 색](#how-report-theme-colors-stick-with-your-reports), 감정 색, 다른 색, 그리고 [구조 색(고급)](#setting-structural-colors)이 포함됩니다.
- **텍스트**: 텍스트 설정에는 레이블, 제목, 카드 및 KPI, 탭 머리글 등에 대한 [기본 텍스트 클래스 기본값](#setting-formatted-text-defaults)을 설정하는 글꼴 패밀리, 크기 및 색이 포함됩니다.
- **시각적 개체**: 시각적 개체 설정에는 배경, 테두리, 헤더 및 도구 설명이 포함됩니다.
- **페이지**: 페이지 요소 설정에는 배경 화면과 배경이 포함됩니다.
- **필터 창**: 필터 창 설정에는 배경색, 투명도, 글꼴 및 아이콘 색, 크기, 필터 카드가 포함됩니다.

변경을 수행한 후에는 **적용 및 저장**을 선택하여 테마를 저장합니다. 이제 해당 테마를 현재 보고서에서 사용하고 내보낼 수 있습니다.

이 방법으로 현재 테마를 사용자 지정하면 테마를 빠르고 쉽게 사용자 지정할 수 있습니다. 하지만 더 세부적으로 테마를 조정하려면 테마의 [JSON 파일](#report-theme-json-file-format)을 수정해야 합니다.

> [!TIP]
> **테마 사용자 지정** 대화 상자에서 컨트롤을 사용하여 가장 일반적인 보고서 테마 옵션을 사용자 지정할 수 있습니다. 더 많은 제어를 위해 선택적으로 테마의 JSON 파일을 내보내고 해당 파일의 설정을 수정하여 수동으로 세부적인 조정을 수행할 수 있습니다. 세부적으로 조정된 JSON 파일의 이름을 바꿔 나중에 가져올 수 있습니다.

### <a name="import-custom-report-theme-files"></a>사용자 지정 보고서 테마 파일 가져오기

사용자 지정 보고서 테마 파일을 가져오려면 다음을 수행합니다.

1. **홈** 리본에서 **테마 전환**을 선택하고 드롭다운 메뉴에서 **테마 가져오기**를 선택합니다.

   ![테마 가져오기](media/desktop-report-themes/report-themes-3a.png)

   사용자를 JSON 테마 파일의 위치로 이동시키는 창이 나타납니다.

2. 다음 이미지에서는 몇 개의 휴일 테마 파일이 제공됩니다. 3월의 휴일 테마인 *St Patricks Day.json*을 선택하겠습니다.

   ![휴일 테마](media/desktop-report-themes/report-themes_4.png)

   테마 파일이 성공적으로 로드되면 Power BI Desktop에서 성공 메시지를 표시합니다.

   ![테마를 성공적으로 가져옴](media/desktop-report-themes/report-themes_5.png)

## <a name="introduction-to-report-theme-json-files"></a>보고서 테마 JSON 파일 소개

 이전 섹션에 언급된 기본 JSON 파일(St Patricks Day.json)을 열면 다음과 같이 표시됩니다.

 ```json
    {
        "name": "St Patrick's Day",
        "dataColors": ["#568410", "#3A6108", "#70A322", "#915203", "#D79A12", "#bb7711", "#114400", "#aacc66"],
        "background":"#FFFFFF",
        "foreground": "#3A6108",
        "tableAccent": "#568410"
    }
```

이 보고서 테마 JSON 파일에는 다음과 같은 줄이 있습니다.

- **name**: 보고서 테마 이름입니다. 이 필드는 유일한 필수 필드입니다.
- **dataColors**: Power BI Desktop 시각적 개체의 데이터에 사용할 색 16진수 코드 목록입니다. 이 목록에는 원하는 만큼 색을 포함할 수 있습니다.
- **background**, **firstLevelElements**및 **tableAccent** (등): 색 클래스입니다. 색 클래스를 사용하면 보고서에서 한 번에 여러 색을 설정할 수 있습니다.

이 JSON 파일을 기준으로 사용하여 가져올 고유한 사용자 지정 보고서 테마 파일을 만들 수 있습니다. 보고서의 기본 색만 조정하려면 파일에서 이름 및 16진수 코드를 변경합니다.

보고서 테마 JSON 파일에서는 변경하려는 서식만 정의합니다. JSON 파일에서 지정하지 않은 모든 항목은 Power BI Desktop 기본 설정으로 되돌아갑니다.

JSON 파일을 만들게 되면 많은 장점이 있습니다. 예를 들어 모든 차트가 글꼴 크기 12를 사용하거나, 특정 시각적 개체가 특정 글꼴 패밀리를 사용하거나, 특정 차트 유형의 경우 데이터 레이블을 끄도록 지정할 수 있습니다. JSON 파일을 사용하면 차트 및 보고서를 표준화하는 보고서 테마 파일을 만들 수 있으므로 쉽게 조직 보고서에 대한 일관성을 유지할 수 있습니다.

JSON 파일의 서식에 대한 자세한 내용은 [보고서 테마 JSON 파일 서식](#report-theme-json-file-format)을 참조하세요.

> [!NOTE]
> [**테마 사용자 지정** 대화 상자](#create-and-customize-a-theme-in-power-bi-desktop-preview)를 사용하여 사용자 지정 JSON 보고서 테마를 수정하는 것이 안전합니다.  이 대화 상자는 제어할 수 없는 테마 설정을 수정하지 않으며 전체 보고서 테마에 대한 변경 내용을 업데이트합니다.

## <a name="how-report-theme-colors-stick-with-your-reports"></a>보고서에서 보고서 테마 색을 유지하는 방법

Power BI 서비스에 보고서를 게시하는 경우 보고서 테마 색이 유지됩니다. **서식** 패널의 **데이터 색** 섹션에는 보고서 테마가 반영됩니다.

보고서 테마에 사용할 수 있는 색을 보려면 다음을 수행합니다.

1. 시각적 개체를 선택합니다.

2. **시각화** 창의 **서식** 섹션에서 **데이터 색**을 선택합니다.

3. 항목 드롭다운을 선택하여 보고서 테마에 대한 **테마 색** 정보를 봅니다.

   ![테마 색](media/desktop-report-themes/report-themes_8.png)

이 예제에서는 세인트 패트릭스 데이 보고서 테마에서 다수의 녹색 및 갈색을 적용한 후 테마 색을 봅니다. 모두 녹색으로 보이십니까? 해당 색이 가져와서 적용한 보고서 테마의 일부이기 때문입니다.

색상표의 색도 현재 테마를 기준으로 합니다. 예를 들어 데이터 요소에 대해 맨 위 행의 세 번째 색을 선택한다고 가정해보겠습니다. 나중에 다른 테마로 변경하는 경우 Microsoft Office에서 테마를 변경할 때와 마찬가지로 해당 데이터 요소의 색이 자동으로 새 테마에 있는 맨 위 행의 세 번째 색으로 업데이트됩니다.

### <a name="situations-when-report-theme-colors-wont-stick-to-your-reports"></a>보고서에 보고서 테마 색을 유지하지 않는 경우

색 선택의 **사용자 지정 색** 옵션을 사용하여 시각적 개체에서 특정 데이터 요소에 사용자 지정 색 집합(또는 개별 색)을 적용해 보겠습니다. 보고서 테마를 적용하면 이 보고서 테마는 사용자 지정된 데이터 요소 색을 ‘재정의하지 않습니다’.

**테마 색** 섹션을 사용하여 데이터 요소 색을 수동으로 설정할 수도 있습니다. 이러한 색은 새 보고서 테마를 적용할 때 ‘업데이트되지 않습니다’. 새 보고서 테마를 적용할 때 색이 업데이트되도록 기본 색으로 되돌리려면 **기본값으로 되돌리기**를 선택하거나 색 선택의 **테마 색** 색상표에서 색을 선택합니다.

![기본값으로 되돌리기](media/desktop-report-themes/report-themes_9.png)

많은 사용자 지정 시각적 개체가 보고서 테마에 적용되지 않습니다.

## <a name="custom-report-theme-files-you-can-use-right-now"></a>지금 바로 사용할 수 있는 사용자 지정 보고서 테마 파일

보고서 테마를 시작하고 싶으신가요? [테마 갤러리](https://community.powerbi.com/t5/Themes-Gallery/bd-p/ThemesGallery)에서 사용자 지정 보고서 테마를 확인해 보거나 다음과 같은 이미 만들어져 있는 사용자 지정 보고서 테마 JSON 파일을 사용해 보세요. 이 파일은 다운로드하여 Power BI Desktop 보고서로 가져올 수 있습니다.

- [파형 테마](https://community.powerbi.com/t5/Themes-Gallery/Waveform/m-p/140536). 이 보고서 테마는 보고서 테마의 첫 번째 릴리스를 발표한 [블로그 게시물](https://powerbi.microsoft.com/blog/power-bi-desktop-march-feature-summary/)에 소개되었습니다. [Waveform.json을 다운로드](https://go.microsoft.com/fwlink/?linkid=843924)합니다.

  ![Waveform.json 테마](media/desktop-report-themes/report-themes_10.png)

- [색맹 사용자용 테마](https://community.powerbi.com/t5/Themes-Gallery/Color-Blind-Friendly/m-p/140597).
시각 장애가 있는 사용자가 더 쉽게 읽을 수 있는 보고서 테마입니다. [ColorblindSafe-Longer.json을 다운로드](https://go.microsoft.com/fwlink/?linkid=843923)합니다.

  ![ColorblindSafe-Longer.json 테마](media/desktop-report-themes/report-themes_11.png)을 탭합니다.

- 파워 뷰 테마. Apothecary.json이 포함되어 있습니다. [파워 뷰 테마를 zip 파일로 다운로드](https://go.microsoft.com/fwlink/?linkid=843925)합니다.

  ![Apothecary.json 테마](media/desktop-report-themes/report-themes_12.png)

- 밸런타인데이 테마.

  ![밸런타인데이 테마](media/desktop-report-themes/report-themes_13.png)

  발렌타인데이 JSON 파일의 코드는 다음과 같습니다.

   ```json
       {
           "name": "Valentine's Day",
           "dataColors": ["#990011", "#cc1144", "#ee7799", "#eebbcc", "#cc4477", "#cc5555", "#882222", "#A30E33"],
           "background":"#FFFFFF",
           "foreground": "#ee7799",
           "tableAccent": "#990011"
       }
   ```

시작점으로 사용할 수 있는 몇 가지 추가 보고서 테마는 다음과 같습니다.

- [Sunflower-twilight](https://community.powerbi.com/t5/Themes-Gallery/Sunflower-Twilight/m-p/140749)
- [Plum](https://community.powerbi.com/t5/Themes-Gallery/Plum/m-p/140711)
- [Autumn](https://community.powerbi.com/t5/Themes-Gallery/Autumn/m-p/140746)
- [High contrast](https://community.powerbi.com/t5/Themes-Gallery/Color-Blind-Friendly/m-p/140597)

보고서 테마를 사용하여 Power BI Desktop 보고서가 사용자, 조직 또는 현재 시즌이나 휴일을 다양하게 반영하도록 할 수 있습니다.

## <a name="export-report-themes-preview"></a>보고서 테마 내보내기(미리 보기)

Power BI Desktop의 2019년 12월 릴리스부터 현재 적용된 보고서 테마를 Power BI Desktop에서 JSON 파일로 직접 내보내는 옵션을 사용할 수 있습니다. 보고서 테마를 내보낸 후에는 다른 보고서에서 다시 사용할 수 있습니다. 이 옵션을 사용하면 기본 제공 테마 대부분의 JSON 파일을 내보낼 수 있습니다. 유일한 예외는 가져올 때 다른 테마를 작성하는 기반이 되는 기준 테마인 클래식 및 기본 테마입니다.

현재 적용된 테마를 Power BI Desktop에서 내보내려면 다음을 수행합니다.

1. **파일** > **옵션 및 설정** > **옵션**을 선택합니다.

2. **미리 보기 기능** 섹션에서 **현재 테마 사용자 지정**을 선택하고 **확인**을 선택합니다.

   미리 보기 기능을 사용하려면 Power BI Desktop을 다시 시작하라는 메시지가 표시될 수 있습니다. 다시 시작하면 현재 적용된 테마 내보내기를 시작할 수 있습니다.

3. **홈** 리본에서 **테마 전환** > **현재 테마 내보내기**를 선택합니다.

4. **다른 이름으로 저장** 대화 상자에서 JSON 파일을 저장할 디렉터리를 찾은 후 **저장**을 선택합니다.

## <a name="report-theme-json-file-format"></a>보고서 테마 JSON 파일 서식

가장 기본적인 수준의 테마 JSON 파일에는 필수 줄인 **name**만 있습니다.

```json
{
    "name": "Custom Theme"
}
```

**name** 이외의 다른 모든 요소는 선택 사항입니다. 즉, 특별히 서식을 지정하려는 속성만 테마 파일에 추가하고 나머지는 Power BI의 기본값을 계속 사용할 수 있습니다.

### <a name="setting-theme-colors"></a>테마 색 설정

**name**에서 다음과 같은 기본 데이터 색 관련 속성을 추가할 수 있습니다.

- **dataColors**: Power BI Desktop 시각적 개체의 데이터를 나타내는 색 도형에 사용할 색 16진수 코드 목록입니다. 이 목록에는 원하는 만큼 색을 포함할 수 있습니다. 이 목록의 모든 색을 사용했으나 시각적 개체에 더 많은 색이 필요하면 Power BI의 기본 색상표를 사용하도록 다시 되돌립니다.
- **good**, **neutral**, **bad**: 이러한 속성은 폭포 차트 및 KPI 시각적 개체에서 사용되는 상태 색을 설정합니다.
- **maximum**, **center**, **minimum**, **null**: 이러한 색은 조건부 서식 지정 대화 상자에서 다양한 그라데이션 색을 설정합니다.

이러한 색을 정의하는 기본 테마는 다음과 같이 표시될 수 있습니다.

```json
{
    "name": "Custom Theme",
    "dataColors": [
        "#118DFF",
        "#12239E",
        "#E66C37",
        "#6B007B",
        "#E044A7",
        "#744EC2",
        "#D9B300",
        "#D64550",
        "#197278",
        "#1AAB40"
    ],
    "good": "#1AAB40",
    "neutral": "#D9B300",
    "bad": "#D64554",
    "maximum": "#118DFF",
    "center": "#D9B300",
    "minimum": "#DEEFFF",
    "null": "#FF7F48"
}
```

### <a name="setting-structural-colors"></a>구조 색 설정

그런 다음 **background** 및 **firstLevelElements** 같은 다양한 색 클래스를 추가할 수 있습니다. 해당 색 클래스는 보고서의 요소에 대한 구조 색(예: 축 눈금선, 강조 색 및 시각적 개체 요소의 배경 색)을 설정합니다.

다음 테이블에서는 서식을 지정할 수 있는 여섯 가지 색 클래스를 보여 줍니다.  **색 클래스** 이름은 [**테마 사용자 지정** 대화 상자](#create-and-customize-a-theme-in-power-bi-desktop-preview)에서 “이름 및 색” 섹션의 “고급” 하위 섹션에 있는 이름에 해당합니다.

|색 클래스  |서식 지정 대상  |
|---------|---------|
|**foreground** | 레이블 배경색(데이터 요소 외부에 있는 경우) <br> 추세선 색 <br>  텍스트 상자 기본 색 <br> 테이블 및 행렬 값 및 합계 글꼴 색 데이터 막대 축 색 <br> 카드 데이터 레이블 <br> 계기 설명선 값 색 <br> KPI 목표 색 <br>  KPI 텍스트 색 <br> 슬라이서 항목 색(포커스 모드인 경우)  <br> 슬라이서 드롭다운 항목 글꼴 색 <br> 슬라이서 숫자 입력 글꼴 색 <br> 슬라이서 머리글 글꼴 색 <br> 분산형 차트 비율 선 색 <br> 꺾은선형 차트 예측 선 색 <br> 지도 지시선 색 <br> 필터 창 및 카드 텍스트 색|
|**foregroundNeutralSecondary** |레이블 색  <br> 범례 레이블 색 <br> 축 레이블 색 <br> 테이블 및 행렬 머리글 글꼴 색 <br> 계기 대상 및 대상 지시선 색 <br>  KPI 추세 축 색 <br> 슬라이서 슬라이더 색 <br> 슬라이서 항목 글꼴 색 <br> 슬라이서 윤곽선 색 <br> 꺾은선형 차트 가리킨 색 <br> 여러 행 카드 제목 색 <br> 리본 차트 스트로크 색 <br> 도형 맵 테두리 색 <br> 단추 텍스트 글꼴 색 <br> 단추 아이콘 선 색 <br> 단추 윤곽선 색 |
| **foregroundNeutralTertiary** | 범례 흐리게 색 <br> 카드 범주 레이블 색 <br> 여러 행 카드 범주 레이블 색 <br> 여러 행 카드 막대 색 <br> 깔때기형 차트 변환율 스트로크 색 
| **backgroundLight** | 축 눈금선 색 <br> 테이블 및 행렬 눈금 색 <br> 슬라이서 헤더 배경색(포커스 모드인 경우)  <br> 여러 행 카드 윤곽선 색  <br> 도형 채우기 색 <br> 계기 원호 배경색 <br> 적용된 필터 카드 배경색 <br> |
**backgroundNeutral** | 테이블 및 행렬 눈금 윤곽선 색 <br> 도형 맵 기본 색 <br> 리본 차트 리본 채우기 색(일치하는 계열 옵션이 해제된 경우) |
**background** | 레이블 배경색(데이터 요소 내에 있는 경우) <br> 슬라이서 드롭다운 항목 배경색  <br> 도넛형 차트 스트로크 색 <br> 트리맵 스트로크 색 <br> 콤보 차트 배경색 <br> 단추 채우기 색 <br> 필터 창 및 사용 가능한 필터 카드 배경색 |
**tableAccent** | 있는 경우 테이블 및 행렬 눈금 윤곽선 색을 재정의합니다. |


색 클래스를 설정하는 샘플 테마는 다음과 같습니다.

```json
{
    "name": "Custom Theme",
    "firstLevelElements": "#252423",
    "secondLevelElements": "#605E5C",
    "thirdLevelElements": "#F3F2F1",
    "fourthLevelElements": "#B3B0AD",
    "background": "#FFFFFF",
    "secondaryBackground": "#C8C6C4",
    "tableAccent": "#118DFF"
}
```

> [!TIP]
> 일반적인 “흰색” **배경**에 “검정” **firstLevelElements**와 다른 “어두운 테마” 또는 기타 다채로운 테마를 제작하는 경우, 다른 구조 색상 및 [기본 텍스트 클래스 색](#setting-formatted-text-defaults)에 대한 값도 설정해야 합니다.  이렇게 하면, 예를 들어 레이블 배경이 있는 차트의 데이터 레이블이 예상 스타일과 일치하고 읽을 수 있을 뿐 아니라 축 눈금선이 표시되도록 할 수 있습니다.

### <a name="setting-formatted-text-defaults"></a>서식 있는 텍스트 기본값 설정

다음으로, JSON 파일에 텍스트 클래스를 추가할 수 있습니다. 텍스트 클래스는 색 클래스와 유사하지만 보고서에서 텍스트 그룹의 글꼴 크기, 색 및 패밀리를 업데이트할 수 있도록 고안되었습니다.

12개의 텍스트 클래스가 있지만 보고서의 모든 텍스트 서식 지정을 변경하는 데는 ‘기본 클래스’라는 네 개의 클래스만 설정하면 됩니다.  이러한 네 가지 기본 클래스는 “텍스트” 섹션의 [**테마 사용자 지정** 대화 상자](#create-and-customize-a-theme-in-power-bi-desktop-preview)에서 설정할 수 있습니다. “일반”은 **레이블**, “제목”은 **제목**, “카드 및 KPI”는 **콜아웃**, 그리고 “탭 머리글”은 **머리글**에 해당합니다.

‘보조 클래스’로 간주되는 다른 텍스트 클래스는 연결된 기본 클래스에서 해당 속성을 자동으로 파생시킵니다. 보조 클래스는 기본 클래스에 비해 더 밝은 텍스트 색 음영 또는 더 크거나 더 작은 텍스트 크기 비율을 선택하는 경우가 많습니다.

**레이블** 클래스를 예로 들어 보겠습니다. **레이블** 클래스의 기본 서식 지정은 Segoe UI, #252423(진한 회색) 및 12포인트입니다. 이 클래스는 테이블 및 행렬에서 값을 서식 지정하는 데 사용됩니다. 일반적으로 테이블 또는 행렬의 합계는 서식 지정은 비슷하지만 눈에 띄도록 **굵은 레이블** 클래스를 사용하여 굵게 표시합니다. 하지만 테마 JSON에서 이 클래스를 지정할 필요는 없습니다. Power BI에서 자동으로 지정합니다. 나중에 테마에서 글꼴이 14포인트인 레이블을 지정하기로 결정하는 경우 **굵은 레이블** 클래스를 업데이트할 필요도 없습니다. **레이블** 클래스의 텍스트 서식 지정을 상속하기 때문입니다.

아래 테이블에서는 다음 정보를 보여 줍니다.

- 네 가지 각 기본 텍스트 클래스, 서식 지정 대상 및 해당 기본 설정
- 기본 클래스와 고유하게 비교되는 각 보조 클래스, 서식 지정 대상 및 해당 기본 설정

|기본 클래스  |보조 클래스  |JSON 클래스 이름  | 기본 설정  |연결된 시각적 개체  |
|---------|---------|---------|---------|---------|
| 설명선   | 해당 없음   | callout | DIN <br> #252423 <br> 45pt |카드 데이터 레이블 <br> KPI 지표|
|머리글|해당 없음|header|Segoe UI Semibold <br> #252423 <br> 12pt |주요 영향 요인 머리글 |
| 제목 || title    |DIN <br> #252423 <br> 12pt |범주 축 제목 <br> 값 축 제목 <br> 여러 행 카드 제목* <br> 슬라이서 머리글|
|-| 큰 제목 | largeTitle    |14pt   |시각적 개체 제목 |
|레이블 ||label |Segoe UI<br>#252423<br>10pt |테이블 및 행렬 열 머리글 <br> 행렬 행 머리글<br>테이블 및 행렬 눈금<br>테이블 및 행렬 값 |
|-|약간 굵게 |semiboldLabel| Segoe UI Semibold   | 주요 영향 요인 프로필 텍스트
|-|대형    |largeLabel |12pt   | 여러 행 카드 데이터 레이블 |
|-|소형    |smallLabel |9pt    |참조선 레이블 * <br>슬라이서 날짜 범위 레이블<br> 슬라이서 숫자 입력 텍스트 스타일<br>슬라이서 검색 상자<br>주요 영향 요인 텍스트|
|-|밝게    |lightLabel |#605E5C    |범례 텍스트<br>단추 텍스트<br>범주 축 레이블<br>깔때기형 차트 데이터 레이블<br>깔때기형 차트 변환율 레이블<br>계기 대상<br>분산형 차트 범주 레이블<br>슬라이서 항목|
|-|굵게 |boldLabel  |Segoe UI Bold  |행렬 부분합<br>행렬 총합계<br>테이블 합계 |
|-|크게 및 밝게  |largeLightLabel    |#605E5C<br>12pt    |카드 범주 레이블<br>계기 레이블<br>여러 행 카드 범주 레이블 |
|-|작게 및 밝게  |smallLightLabel    |#605E5C<br>9pt |데이터 레이블<br>값 축 레이블|

*\*또한 별표 표시 항목은 보고서 테마의 첫 번째 데이터 색을 기준으로 색이 지정됩니다.*

> [!TIP]
> *밝은* 텍스트 클래스의 변형에서는 위에 정의된 [구조 색](#setting-structural-colors)에서 밝은 색상을 사용합니다.  “어두운 테마”를 제작하는 경우 “firstLevelElements”(기본 텍스트 색과 일치), “secondLevelElements”(텍스트의 예상 “밝은” 색상과 일치) 및 “배경”(1단계 및 2단계 요소 색상에 충분한 대비)도 설정해야 합니다.

다음은 기본 텍스트 클래스만 설정하는 테마의 예제입니다.

```json
{
    "name": "Custom Theme",
    "textClasses": {
        "callout": {
            "fontSize": 45,
            "fontFace": "DIN",
            "color": "#252423"
        },
        "title": {
            "fontSize": 12,
            "fontFace": "DIN",
            "color": "#252423"
        },
        "header": {
            "fontSize": 12,
            "fontFace": "Segoe UI Semibold",
            "color": "#252423"
        },
        "label": {
            "fontSize": 10,
            "fontFace": "Segoe UI",
            "color": "#252423"
        }
    }
}
```

보조 클래스는 기본 클래스에서 속성이 상속되므로 테마 파일에 속성을 설정할 필요가 없습니다. 하지만 상속 규칙을 사용하지 않으려는 경우(예를 들어 테이블에서 합계 값을 굵게 표시하지 않으려는 경우) 기본 클래스를 서식 지정하는 것처럼 명시적으로 테마 파일에서 보조 클래스를 서식 지정할 수 있습니다.

### <a name="setting-visual-property-defaults-visualstyles"></a>시각적 개체 속성 기본값 설정(`visualStyles`)

마지막으로, 보고서에 모든 시각적 개체 서식 지정이 더 자세하고 세부적인 수준으로 제어되는 확장된 서식의 JSON 파일을 만들려면 **visualStyles** 섹션을 JSON 파일에 추가하여 서식 지정 세부 정보를 중첩합니다. **visualStyles** 섹션의 템플릿 예제는 다음과 같습니다.

```json
    "visualStyles": {
        "<visualName>": {
            "<styleName>": {
                "<cardName>": [{
                    "<propertyName>": <propertyValue>
                }]
            }
        }
    }
```

**visualName** 및 **cardName** 섹션의 경우 특정 시각적 개체 및 cardName을 사용합니다. 현재는 **styleName**이 항상 별표(*)지만 이후 릴리스에서는 시각적 개체에 대해 다양한 스타일을 만들고 이름을 지정할 수 있습니다(테이블 및 행렬 스타일 기능과 유사함). **propertyName**은 서식 지정 옵션의 이름이고 **propertyValue**는 해당 서식 지정 옵션의 값입니다.

**visualName** 및 **cardName**의 경우 해당 설정이 특정 속성이 있는 모든 시각적 개체나 카드에 적용되도록 하려면 별표를 따옴표로 묶어서 사용합니다. 시각적 개체 및 카드 이름 둘 다에 별표를 사용하면 효과적으로 모든 시각적 개체의 모든 텍스트에 대해 특정 글꼴 크기나 특정 글꼴 패밀리와 같은 설정을 보고서에서 전역적으로 적용할 수 있습니다.

다음은 시각적 개체 스타일을 통해 몇 가지 속성을 설정하는 예제입니다.

```json
{
   "name":"Custom Theme",
   "visualStyles":{
      "*": {
         "*": {
            "*": [{
                "wordWrap": true
            }],
            "categoryAxis": [{
                "gridlineStyle": "dotted"
            }],
            "filterCard": [
              {
                "$id": "Applied",
                "foregroundColor": {"solid": {"color": "#252423" } }
              },
              {
                "$id":"Available",
                "border": true
              }
            ]
         }
      },
      "scatterChart": {
         "*": {
            "bubbles": [{
                  "bubbleSize": -10
            }]
         }
      }
   }
}
```

이 예제에서는 다음과 같이 설정합니다.

- 모든 위치에서 자동 줄 바꿈을 켭니다.
- 범주 축이 있는 모든 시각적 개체에 대해 눈금선 스타일을 점선으로 설정합니다.
- 사용 가능한 필터 카드 및 적용된 필터 카드에 대해 몇 가지 서식을 설정합니다(“$id”를 사용하여 다른 버전의 필터 카드를 설정하는 서식에 유의해야 함).
- 분산형 차트의 거품 크기를 -10으로 설정합니다.

> [!NOTE]
> 조정할 서식 지정 요소만 지정해야 합니다. JSON 파일에 포함되지 않은 서식 지정 요소는 모두 해당 기본값과 설정으로 되돌아갑니다.

### <a name="visualstyles-definition-list"></a>`visualStyles` 정의 목록

이 섹션의 테이블에서는 시각적 개체 이름(**visualName**), 카드 이름(**cardName**) 및 속성 이름(**propertyName**) 및 JSON 파일을 만드는 데 필요한 열거형을 정의합니다.

| visualName 값 |
| --- |
| areaChart |
| barChart |
| basicShape |
| card |
| clusteredBarChart |
| clusteredColumnChart |
| columnChart |
| comboChart |
| donutChart |
| filledMap |
| funnel |
| gauge |
| hundredPercentStackedBarChart |
| hundredPercentStackedColumnChart |
| image |
| KPI |
| lineChart |
| lineClusteredColumnComboChart |
| lineStackedColumnComboChart |
| map |
| multiRowCard |
| pieChart |
| pivotTable |
| ribbonChart |
| scatterChart |
| shapeMap |
| slicer |
| stackedAreaChart |
| tableEx |
| treemap |
| waterfallChart |

다음 표에서는 **cardName** 값을 정의합니다. 각 셀의 첫 번째 값은 JSON 파일 용어입니다. 두 번째 값은 Power BI Desktop 사용자 인터페이스에 표시되는 카드의 이름입니다.

| cardName 값 |
| --- |
| axis: 게이지 축 |
| breakdown: 분석 결과 |
| bubbles: 거품형 |
| calloutValue: 설명선 값 |
| card: card |
| cardTitle: 카드 타일 |
| categoryAxis: X축 |
| categoryLabels: 범주 레이블 |
| columnFormatting: 필드 서식 |
| columnHeaders: 열 머리글 |
| dataLabels: 데이터 레이블 |
| fill: 채우기 |
| fillPoint: 채우기 점 |
| forecast: 예측 |
| general: 일반 |
| goals: 목표 |
| grid: 그리드 |
| header: 머리글 |
| imageScaling: 크기 조정 |
| indicator: 표시기 |
| items: 항목 |
| labels: 데이터 레이블 |
| legend: 범례 |
| lineStyles: 도형 |
| mapControls: 지도 컨트롤 |
| mapStyles: 지도 스타일 |
| numericInputStyle: 숫자 입력 |
| percentBarLabel: 변환율 레이블 |
| plotArea: 플롯 영역 |
| plotAreaShading: 대칭 음영 |
| ratioLine: 비율 선 |
| referenceLine: 상수 선 |
| ribbonChart: 리본 |
| rotation: 회전 |
| rowHeaders: 행 머리글 |
| selection: 선택 컨트롤 |
| sentimentColors: 감정 색 |
| shape: 셰이프 |
| slider: 슬라이더 |
| status: 색 구분 |
| subTotals: 부분합 |
| target: 대상 |
| total: 총합계 |
| trend: 추세선 |
| trendline: 추세 축 |
| valueAxis: Y축 |
| values: 값 |
| wordWrap: 자동 줄 바꿈 |
| xAxisReferenceLine: X축 상수 선 |
| y1AxisReferenceLine: 상수 선 |
| zoom: 확대/축소 |

### <a name="properties-within-each-card"></a>각 카드 내의 속성

다음 섹션에서는 각 카드 내의 속성을 정의합니다. 카드 이름 뒤에는 각 속성 이름이 차례로 나옵니다. 속성마다 서식 지정 창이 나타나는 경우 표시되는 이름, 서식 지정 옵션에서 수행하는 작업에 대한 설명 및 서식 지정 옵션의 유형이 나옵니다. 이 방법을 사용하면 테마 파일에서 사용할 수 있는 값의 종류를 알 수 있습니다.

**dateTime**을 사용하는 경우 날짜는 시작 시 날짜/시간을 사용하여 작은따옴표로 묶인 ISO 날짜여야 합니다. 다음 예제를 참조하십시오.

  "datetime'2011-10-05T14:48:00.000Z'"

Booleans은 true 또는 false입니다. 문자열은 "문자열입니다."와 같이 큰따옴표로 묶여야 합니다. 숫자는 따옴표로 묶지 않으며 값 자체입니다.

색은 다음 서식을 사용합니다. 다음 예제에서 “FFFFFF”는 사용자 지정 16진수 코드로 바뀝니다.

    { "solid": { "color": "#FFFFFF" } }

드롭다운 서식 지정 옵션에 가장 일반적으로 사용되는 열거는 창에 표시되는 어떤 옵션으로도 값이 설정될 수 있음을 의미합니다. 예를 들어 범례 위치로 “RightCenter”를 설정하거나 원형 데이터 레이블로 “데이터 값, 총계에 대한 비율”을 설정할 수 있습니다. 열거 옵션은 속성 목록 아래에 표시됩니다.

```json
{
      "general":{
        "responsive": {
          "type": [
            "bool"
          ],
          "displayName": [
            "(Preview) Responsive"
          ],
          "description": [
            "The visual will adapt to size changes"
          ]
        },
        "legend": {
        "show": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Show"
          ]
        },
        "position": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Position"
          ],
          "description": [
            "Select the location for the legend"
          ]
        },
        "showTitle": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Title"
          ],
          "description": [
            "Display a title for legend symbols"
          ]
        },
        "labelColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Color"
          ]
        },
        "fontFamily": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Font family"
          ]
        },
        "fontSize": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Text Size"
          ]
        }
      },
      "categoryAxis": {
        "show": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Show"
          ]
        },
        "axisScale": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Scale type"
          ]
        },
        "start": {
          "type": [
            "numeric",
            "dateTime"
          ],
          "displayName": [
            "Start"
          ],
          "description": [
            "Enter a starting value (optional)"
          ]
        },
        "end": {
          "type": [
            "numeric",
            "dateTime"
          ],
          "displayName": [
            "End"
          ],
          "description": [
            "Enter an ending value (optional)"
          ]
        },
        "axisType": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Type"
          ]
        },
        "showAxisTitle": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Title"
          ],
          "description": [
            "Title for the X-axis",
            "Title for the Y-axis"
          ]
        },
        "axisStyle": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Style"
          ]
        },
        "labelColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Color"
          ]
        },
        "fontFamily": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Font family"
          ]
        },
        "fontSize": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Text Size"
          ]
        },
        "labelDisplayUnits": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Display units"
          ],
          "description": [
            "Select the units (millions, billions, etc.)"
          ]
        },
        "labelPrecision": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Value decimal places"
          ],
          "description": [
            "Select the number of decimal places to display for the values"
          ]
        },
        "concatenateLabels": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Concatenate labels"
          ],
          "description": [
            "Always concatenate levels of the hierarchy instead of drawing the hierarchy."
          ]
        },
        "preferredCategoryWidth": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Minimum category width"
          ]
        },
        "titleColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Title color"
          ]
        },
        "titleFontFamily": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Font family"
          ]
        },
        "titleFontSize": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Title text size"
          ]
        },
        "position": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Position"
          ],
          "description": [
            "Select left or right"
          ]
        },
        "color": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Color"
          ],
          "description": [
            "Select color for data labels"
          ]
        },
        "duration": {
          "type": [
            "numeric"
          ]
        }
      },
      "valueAxis": {
        "show": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Show"
          ]
        },
        "position": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Position"
          ],
          "description": [
            "Select left or right"
          ]
        },
        "axisScale": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Scale type"
          ]
        },
        "start": {
          "type": [
            "numeric",
            "dateTime"
          ],
          "displayName": [
            "Start"
          ],
          "description": [
            "Enter a starting value (optional)"
          ]
        },
        "end": {
          "type": [
            "numeric",
            "dateTime"
          ],
          "displayName": [
            "End"
          ],
          "description": [
            "Enter an ending value (optional)"
          ]
        },
        "showAxisTitle": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Title"
          ],
          "description": [
            "Title for the Y-axis",
            "Title for the X-axis"
          ]
        },
        "axisStyle": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Style"
          ]
        },
        "labelColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Color"
          ]
        },
        "fontFamily": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Font family"
          ]
        },
        "fontSize": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Text Size"
          ]
        },
        "labelDisplayUnits": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Display units"
          ],
          "description": [
            "Select the units (millions, billions, etc.)"
          ]
        },
        "labelPrecision": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Value decimal places"
          ],
          "description": [
            "Select the number of decimal places to display for the values"
          ]
        },
        "titleColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Title color"
          ]
        },
        "titleFontFamily": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Font family"
          ]
        },
        "titleFontSize": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Title text size"
          ]
        },
        "axisLabel": {
          "type": [
            "none"
          ],
          "displayName": [
            "Y-Axis (Column)"
          ]
        },
        "secShow": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Show secondary"
          ]
        },
        "alignZeros": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Align zeros"
          ],
          "description": [
            "Align the zero tick marks for both value axes"
          ]
        },
        "secAxisLabel": {
          "type": [
            "none"
          ],
          "displayName": [
            "Y-Axis (Line)"
          ]
        },
        "secPosition": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Position"
          ],
          "description": [
            "Select left or right"
          ]
        },
        "secAxisScale": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Scale type"
          ]
        },
        "secStart": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Start"
          ],
          "description": [
            "Enter a starting value (optional)"
          ]
        },
        "secEnd": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "End"
          ],
          "description": [
            "Enter an ending value (optional)"
          ]
        },
        "secShowAxisTitle": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Title"
          ],
          "description": [
            "Title for the Y-axis"
          ]
        },
        "secAxisStyle": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Style"
          ]
        },
        "secLabelColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Color"
          ]
        },
        "secFontFamily": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Font family"
          ]
        },
        "secFontSize": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Text Size"
          ]
        },
        "secLabelDisplayUnits": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Display units"
          ],
          "description": [
            "Select the units (millions, billions, etc.)"
          ]
        },
        "secLabelPrecision": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Value decimal places"
          ],
          "description": [
            "Select the number of decimal places to display for the values"
          ]
        },
        "secTitleColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Title color"
          ]
        },
        "secTitleFontFamily": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Font family"
          ]
        },
        "secTitleFontSize": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Title text size"
          ]
        }
      },
      "dataPoint": {
        "defaultColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Default color",
            "Default Column Color"
          ]
        },
        "fill": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Fill"
          ]
        },
        "defaultCategoryColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Default color",
            "Default Column Color"
          ]
        },
        "showAllDataPoints": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Show all"
          ]
        }
      },
      "labels": {
        "show": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Show"
          ]
        },
        "showSeries": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Show"
          ]
        },
        "color": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Color"
          ],
          "description": [
            "Select color for data labels"
          ]
        },
        "labelDisplayUnits": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Display units"
          ],
          "description": [
            "Select the units (millions, billions, etc.)"
          ]
        },
        "labelPrecision": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Value decimal places"
          ],
          "description": [
            "Select the number of decimal places to display for the values"
          ]
        },
        "showAll": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Customize series"
          ]
        },
        "fontSize": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Text Size"
          ]
        },
        "fontFamily": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Font family"
          ]
        },
        "labelDensity": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Label density"
          ]
        },
        "labelOrientation": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Orientation"
          ]
        },
        "labelPosition": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Position"
          ]
        },
        "percentageLabelPrecision": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "% decimal places"
          ],
          "description": [
            "Select the number of decimal places to display for the percentages"
          ]
        },
        "labelStyle": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Label style"
          ]
        }
      },
      "lineStyles": {
        "strokeWidth": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Stroke width"
          ]
        },
        "strokeLineJoin": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Join type"
          ]
        },
        "lineStyle": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Line style"
          ]
        },
        "showMarker": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Show marker"
          ]
        },
        "markerShape": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Marker shape"
          ]
        },
        "markerSize": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Marker size"
          ]
        },
        "markerColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Marker color"
          ]
        },
        "showSeries": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Customize series",
            "Show"
          ]
        },
        "shadeArea": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Shade area"
          ]
        }
      },
      "plotArea": {
        "transparency": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Transparency"
          ],
          "description": [
            "Set transparency for background color"
          ]
        }
      },
      "trend": {
        "show": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Show"
          ]
        },
        "displayName": {
          "type": [
            "text"
          ],
          "displayName": [
            "Name"
          ],
          "description": [
            "Set trend line name"
          ]
        },
        "lineColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Color"
          ],
          "description": [
            "Set trend line color"
          ]
        },
        "transparency": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Transparency"
          ],
          "description": [
            "Set transparency for trend line color"
          ]
        },
        "style": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Style"
          ],
          "description": [
            "Set trend line style"
          ]
        },
        "combineSeries": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Combine Series"
          ],
          "description": [
            "Show one trend line per series or combine"
          ]
        }
      },
      "y1AxisReferenceLine": {
        "show": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Show"
          ]
        },
        "value": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Value"
          ],
          "description": [
            "Set reference line numeric value"
          ]
        },
        "lineColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Color"
          ],
          "description": [
            "Set reference line color"
          ]
        },
        "transparency": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Transparency"
          ],
          "description": [
            "Set transparency for reference line color"
          ]
        },
        "style": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Line style"
          ]
        },
        "position": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Position"
          ],
          "description": [
            "Arrange relative to chart data points"
          ]
        },
        "dataLabelShow": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Data label"
          ],
          "description": [
            "Display a data label for the reference line"
          ]
        },
        "dataLabelColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Color"
          ],
          "description": [
            "Set the reference line data label color"
          ]
        },
        "dataLabelDecimalPoints": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Decimal Places"
          ]
        },
        "dataLabelHorizontalPosition": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Horizontal Position"
          ],
          "description": [
            "Set the horizontal position for the reference line data label"
          ]
        },
        "dataLabelVerticalPosition": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Vertical Position"
          ],
          "description": [
            "Set the vertical position for the reference line data label"
          ]
        },
        "dataLabelDisplayUnits": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Display units"
          ],
          "description": [
            "Select the units (millions, billions, etc.)"
          ]
        }
      },
      "referenceLine": {
        "show": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Show"
          ]
        },
        "displayName": {
          "type": [
            "text"
          ],
          "displayName": [
            "Name"
          ],
          "description": [
            "Set reference line name"
          ]
        },
        "value": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Value"
          ],
          "description": [
            "Set reference line numeric value"
          ]
        },
        "lineColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Color"
          ],
          "description": [
            "Set reference line color"
          ]
        },
        "transparency": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Transparency"
          ],
          "description": [
            "Set transparency for reference line color"
          ]
        },
        "style": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Line style"
          ]
        },
        "position": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Position"
          ],
          "description": [
            "Arrange relative to chart data points"
          ]
        },
        "dataLabelShow": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Data label"
          ],
          "description": [
            "Display a data label for the reference line"
          ]
        },
        "dataLabelColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Color"
          ],
          "description": [
            "Set the reference line data label color"
          ]
        },
        "dataLabelDecimalPoints": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Decimal Places"
          ]
        },
        "dataLabelHorizontalPosition": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Horizontal Position"
          ],
          "description": [
            "Set the horizontal position for the reference line data label"
          ]
        },
        "dataLabelVerticalPosition": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Vertical Position"
          ],
          "description": [
            "Set the vertical position for the reference line data label"
          ]
        },
        "dataLabelDisplayUnits": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Display units"
          ],
          "description": [
            "Select the units (millions, billions, etc.)"
          ]
        }
      },
      "line": {
        "lineColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Line color"
          ]
        },
        "transparency": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Transparency"
          ],
          "description": [
            "Set transparency for background color"
          ]
        },
        "weight": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Weight"
          ]
        },
        "roundEdge": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Round edges"
          ]
        }
      },
      "fill": {
        "show": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Show"
          ]
        },
        "fillColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Fill color"
          ]
        },
        "transparency": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Transparency"
          ],
          "description": [
            "Set transparency for background color"
          ]
        }
      },
      "rotation": {
        "angle": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Rotation"
          ]
        }
      },
      "categoryLabels": {
        "show": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Show"
          ]
        },
        "color": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Color"
          ],
          "description": [
            "Select color for data labels"
          ]
        },
        "fontSize": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Text Size"
          ]
        },
        "fontFamily": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Font family"
          ]
        }
      },
      "wordWrap": {
        "show": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Show"
          ]
        }
      },
      "dataLabels": {
        "color": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Color"
          ],
          "description": [
            "Select color for data labels"
          ]
        },
        "fontSize": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Text Size"
          ]
        },
        "fontFamily": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Font family"
          ]
        }
      },
      "cardTitle": {
        "color": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Color"
          ],
          "description": [
            "Select color for data labels"
          ]
        },
        "fontSize": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Text Size"
          ]
        },
        "fontFamily": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Font family"
          ]
        }
      },
      "card": {
        "outline": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Outline"
          ]
        },
        "outlineColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Outline color"
          ],
          "description": [
            "Color of the outline"
          ]
        },
        "outlineWeight": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Outline weight"
          ],
          "description": [
            "Thickness of the outline in pixels"
          ]
        },
        "barShow": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Show bar"
          ],
          "description": [
            "Display a bar to the left side of the card as an accent"
          ]
        },
        "barColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Bar color"
          ]
        },
        "barWeight": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Bar thickness"
          ],
          "description": [
            "Thickness of the bar in pixels"
          ]
        },
        "cardPadding": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Padding"
          ],
          "description": [
            "Background"
          ]
        },
        "cardBackground": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Background"
          ]
        }
      },
      "percentBarLabel": {
        "show": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Show"
          ]
        },
        "color": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Color"
          ],
          "description": [
            "Select color for data labels"
          ]
        },
        "fontSize": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Text Size"
          ]
        },
        "fontFamily": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Font family"
          ]
        }
      },
      "axis": {
        "min": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Min"
          ]
        },
        "max": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Max"
          ]
        },
        "target": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Target"
          ]
        }
      },
      "target": {
        "show": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Show"
          ]
        },
        "color": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Color"
          ],
          "description": [
            "Select color for data labels"
          ]
        },
        "labelDisplayUnits": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Display units"
          ],
          "description": [
            "Select the units (millions, billions, etc.)"
          ]
        },
        "labelPrecision": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Value decimal places"
          ],
          "description": [
            "Select the number of decimal places to display for the values"
          ]
        },
        "fontSize": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Text Size"
          ]
        },
        "fontFamily": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Font family"
          ]
        }
      },
      "calloutValue": {
        "show": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Show"
          ]
        },
        "color": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Color"
          ],
          "description": [
            "Select color for data labels"
          ]
        },
        "labelDisplayUnits": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Display units"
          ],
          "description": [
            "Select the units (millions, billions, etc.)"
          ]
        },
        "labelPrecision": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Value decimal places"
          ],
          "description": [
            "Select the number of decimal places to display for the values"
          ]
        }
      },
      "forecast": {
        "show": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Show"
          ]
        },
        "displayName": {
          "type": [
            "text"
          ],
          "displayName": [
            "Name"
          ],
          "description": [
            "Set forecast name"
          ]
        },
        "confidenceBandStyle": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Confidence band style"
          ],
          "description": [
            "Set forecast confidence band style"
          ]
        },
        "lineColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Color"
          ],
          "description": [
            "Set forecast line color"
          ]
        },
        "transparency": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Transparency"
          ],
          "description": [
            "Set transparency for background color"
          ]
        },
        "style": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Line style"
          ]
        },
        "transform": {
          "type": [
            "queryTransform"
          ]
        }
      },
      "bubbles": {
        "bubbleSize": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Size"
          ]
        }
      },
      "mapControls": {
        "autoZoom": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Auto zoom"
          ]
        },
        "zoomLevel": {
          "type": [
            "numeric"
          ]
        },
        "centerLatitude": {
          "type": [
            "numeric"
          ]
        },
        "centerLongitude": {
          "type": [
            "numeric"
          ]
        }
      },
      "mapStyles": {
        "mapTheme": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Theme"
          ]
        }
      },
      "shape": {
        "map": {
          "type": [
            "geoJson"
          ]
        },
        "projectionEnum": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Projection"
          ],
          "description": [
            "Projection"
          ]
        }
      },
      "zoom": {
        "autoZoom": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Auto zoom"
          ],
          "description": [
            "Zoom in on shapes with available data"
          ]
        },
        "selectionZoom": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Selection zoom"
          ],
          "description": [
            "Zoom in on selected shapes"
          ]
        },
        "manualZoom": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Manual zoom"
          ],
          "description": [
            "Allow user to zoom and pan"
          ]
        }
      },
      "xAxisReferenceLine": {
        "show": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Show"
          ]
        },
        "value": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Value"
          ],
          "description": [
            "Set reference line numeric value"
          ]
        },
        "lineColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Color"
          ],
          "description": [
            "Set reference line color"
          ]
        },
        "transparency": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Transparency"
          ],
          "description": [
            "Set transparency for reference line color"
          ]
        },
        "style": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Line style"
          ]
        },
        "position": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Position"
          ],
          "description": [
            "Arrange relative to chart data points"
          ]
        },
        "dataLabelShow": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Data label"
          ],
          "description": [
            "Display a data label for the reference line"
          ]
        },
        "dataLabelColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Color"
          ],
          "description": [
            "Set the reference line data label color"
          ]
        },
        "dataLabelDecimalPoints": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Decimal Places"
          ]
        },
        "dataLabelHorizontalPosition": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Horizontal Position"
          ],
          "description": [
            "Set the horizontal position for the reference line data label"
          ]
        },
        "dataLabelVerticalPosition": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Vertical Position"
          ],
          "description": [
            "Set the vertical position for the reference line data label"
          ]
        },
        "dataLabelDisplayUnits": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Display units"
          ],
          "description": [
            "Select the units (millions, billions, etc.)"
          ]
        }
      },
      "fillPoint": {
        "show": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Show"
          ]
        }
      },
      "colorByCategory": {
        "show": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Show"
          ]
        }
      },
      "plotAreaShading": {
        "show": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Show"
          ]
        },
        "upperShadingColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Upper shading"
          ],
          "description": [
            "Shading color of the upper region"
          ]
        },
        "lowerShadingColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Lower shading"
          ],
          "description": [
            "Shading color of the lower region"
          ]
        },
        "transparency": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Transparency"
          ],
          "description": [
            "Set transparency for background color"
          ]
        }
      },
      "ratioLine": {
        "show": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Show"
          ]
        },
        "lineColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Color"
          ],
          "description": [
            "Set reference line color"
          ]
        },
        "transparency": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Transparency"
          ],
          "description": [
            "Set transparency for line color"
          ]
        },
        "style": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Line style"
          ]
        }
      },
      "grid": {
        "outlineColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Outline color"
          ],
          "description": [
            "Color of the outline"
          ]
        },
        "outlineWeight": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Outline weight"
          ],
          "description": [
            "Thickness of the outline in pixels"
          ]
        },
        "gridVertical": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Vert grid"
          ],
          "description": [
            "Show/Hide the vertical gridlines"
          ]
        },
        "gridVerticalColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Vert grid color"
          ],
          "description": [
            "Color for the vertical gridlines"
          ]
        },
        "gridVerticalWeight": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Vert grid thickness"
          ],
          "description": [
            "Thickness of the vertical gridlines in pixels"
          ]
        },
        "gridHorizontal": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Horiz grid"
          ],
          "description": [
            "Show/Hide the horizontal gridlines"
          ]
        },
        "gridHorizontalColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Horiz grid color"
          ],
          "description": [
            "Color for the horizontal gridlines"
          ]
        },
        "gridHorizontalWeight": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Horiz grid thickness"
          ],
          "description": [
            "Thickness of the horizontal gridlines in pixels"
          ]
        },
        "rowPadding": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Row padding"
          ],
          "description": [
            "Padding in pixels applied to top and bottom of every row"
          ]
        },
        "imageHeight": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Image height"
          ],
          "description": [
            "The height of images in pixels"
          ]
        },
        "textSize": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Text Size"
          ]
        }
      },
      "columnHeaders": {
        "outline": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Outline"
          ]
        },
        "fontColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Font color"
          ],
          "description": [
            "Font color of the cells"
          ]
        },
        "backColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Background color"
          ],
          "description": [
            "Background color of the cells"
          ]
        },
        "wordWrap": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Word wrap"
          ]
        },
        "fontFamily": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Font family"
          ]
        },
        "fontSize": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Text Size"
          ]
        },
        "autoSizeColumnWidth": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Auto-size column width"
          ]
        },
        "urlIcon": {
          "type": [
            "bool"
          ],
          "displayName": [
            "URL icon"
          ],
          "description": [
            "Show an icon instead of the full URL"
          ]
        }
      },
      "values": {
        "outline": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Outline"
          ]
        },
        "backColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Color scales"
          ]
        },
        "fontColorPrimary": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Font color"
          ],
          "description": [
            "Font color of the odd rows"
          ]
        },
        "backColorPrimary": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Background color"
          ],
          "description": [
            "Background color of the odd rows"
          ]
        },
        "fontColorSecondary": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Alternate font color"
          ],
          "description": [
            "Font color of the even rows"
          ]
        },
        "backColorSecondary": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Alternate background color"
          ],
          "description": [
            "Background color of the even rows"
          ]
        },
        "urlIcon": {
          "type": [
            "bool"
          ],
          "displayName": [
            "URL icon"
          ],
          "description": [
            "Show an icon instead of the full URL"
          ]
        },
        "fontFamily": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Font family"
          ]
        },
        "fontSize": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Text Size"
          ]
        },
        "wordWrap": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Word wrap"
          ]
        },
        "bandedRowHeaders": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Banded row style"
          ],
          "description": [
            "Apply banded row style to the last level of the row group headers, using the colors of the values."
          ]
        },
        "valuesOnRow": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Show on rows"
          ],
          "description": [
            "Show values in row groups rather than columns"
          ]
        }
      },
      "total": {
        "outline": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Outline"
          ]
        },
        "fontColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Font color"
          ],
          "description": [
            "Font color of the cells"
          ]
        },
        "backColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Background color"
          ],
          "description": [
            "Background color of the cells"
          ]
        },
        "applyToHeaders": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Apply to labels"
          ]
        },
        "totals": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Totals"
          ]
        },
        "fontFamily": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Font family"
          ]
        },
        "fontSize": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Text Size"
          ]
        }
      },
      "columnFormatting": {
        "fontColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Font color"
          ],
          "description": [
            "Font color of the cells"
          ]
        },
        "backColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Background color"
          ],
          "description": [
            "Background color of the cells"
          ]
        },
        "styleHeader": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Color header"
          ]
        },
        "styleValues": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Color values"
          ]
        },
        "styleTotal": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Color total"
          ]
        },
        "styleSubtotals": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Color subtotals"
          ]
        }
      },
      "rowHeaders": {
        "outline": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Outline"
          ]
        },
        "fontColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Font color"
          ],
          "description": [
            "Font color of the cells"
          ]
        },
        "backColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Background color"
          ],
          "description": [
            "Background color of the cells"
          ]
        },
        "wordWrap": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Word wrap"
          ]
        },
        "fontFamily": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Font family"
          ]
        },
        "fontSize": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Text Size"
          ]
        },
        "stepped": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Stepped layout"
          ],
          "description": [
            "Render row headers with stepped layout"
          ]
        },
        "steppedLayoutIndentation": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Stepped layout indentation"
          ],
          "description": [
            "Set the indentation, in pixels, applied to row headers"
          ]
        },
        "urlIcon": {
          "type": [
            "bool"
          ],
          "displayName": [
            "URL icon"
          ],
          "description": [
            "Show an icon instead of the full URL"
          ]
        }
      },
      "subTotals": {
        "outline": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Outline"
          ]
        },
        "fontColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Font color"
          ],
          "description": [
            "Font color of the cells"
          ]
        },
        "backColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Background color"
          ],
          "description": [
            "Background color of the cells"
          ]
        },
        "fontFamily": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Font family"
          ]
        },
        "fontSize": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Text Size"
          ]
        },
        "rowSubtotals": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Total row"
          ]
        },
        "columnSubtotals": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Total column"
          ]
        },
        "applyToHeaders": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Apply to labels"
          ]
        }
      },
      "selection": {
        "selectAllCheckboxEnabled": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Select All"
          ]
        },
        "singleSelect": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Single Select"
          ]
        }
      },
      "header": {
        "show": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Show"
          ]
        },
        "fontColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Font color"
          ],
          "description": [
            "Font color of the cells"
          ]
        },
        "background": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Background"
          ]
        },
        "outline": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Outline"
          ]
        },
        "textSize": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Text Size"
          ]
        },
        "fontFamily": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Font family"
          ]
        }
      },
      "items": {
        "fontColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Font color"
          ],
          "description": [
            "Font color of the cells"
          ]
        },
        "background": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Background"
          ]
        },
        "outline": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Outline"
          ]
        },
        "textSize": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Text Size"
          ]
        },
        "fontFamily": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Font family"
          ]
        }
      },
      "numericInputStyle": {
        "fontColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Font color"
          ],
          "description": [
            "Font color of the cells"
          ]
        },
        "textSize": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Text Size"
          ]
        },
        "fontFamily": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Font family"
          ]
        },
        "background": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Background"
          ]
        }
      },
      "slider": {
        "show": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Show"
          ]
        },
        "color": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Color"
          ]
        }
      },
      "dateRange": {
        "includeToday": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Include today"
          ]
        }
      },
      "sentimentColors": {
        "increaseFill": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Increase"
          ]
        },
        "decreaseFill": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Decrease"
          ]
        },
        "totalFill": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Total"
          ]
        },
        "otherFill": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Other"
          ]
        }
      },
      "breakdown": {
        "maxBreakdowns": {
          "type": [
            "integer"
          ],
          "displayName": [
            "Max breakdowns"
          ],
          "description": [
            "The number of individual breakdowns to show (rest grouped into Other)"
          ]
        }
      },
      "indicator": {
        "indicatorDisplayUnits": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Display units"
          ],
          "description": [
            "Select the units (millions, billions, etc.)"
          ]
        },
        "indicatorPrecision": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Value decimal places"
          ],
          "description": [
            "Select the number of decimal places to display for the values"
          ]
        },
        "kpiFormat": {
          "type": [
            "text"
          ],
          "displayName": [
            "Format"
          ]
        }
      },
      "trendline": {
        "show": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Show"
          ]
        }
      },
      "goals": {
        "showGoal": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Goal"
          ]
        },
        "showDistance": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Distance"
          ]
        }
      },
      "status": {
        "direction": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Direction"
          ]
        },
        "goodColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Good Color"
          ]
        },
        "neutralColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Neutral Color"
          ]
        },
        "badColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Bad Color"
          ]
        }
      }
```



### <a name="enumerations-in-the-json-file"></a>JSON 파일의 열거형
다음 섹션에서는 JSON 파일에서 사용할 수는 열거형을 정의합니다.

```json
    {
        "legend": {
            "position": [
                {
                    "value": "Top",
                    "displayName": "Top"
                },
                {
                    "value": "Bottom",
                    "displayName": "Bottom"
                },
                {
                    "value": "Left",
                    "displayName": "Left"
                },
                {
                    "value": "Right",
                    "displayName": "Right"
                },
                {
                    "value": "TopCenter",
                    "displayName": "Top Center"
                },
                {
                    "value": "BottomCenter",
                    "displayName": "Bottom Center"
                },
                {
                    "value": "LeftCenter",
                    "displayName": "Left Center"
                },
                {
                    "value": "RightCenter",
                    "displayName": "Right center"
                }
            ],
            "legendMarkerRendering": [
                {
                    "value": "markerOnly",
                    "displayName": "Markers only"
                },
                {
                    "value": "lineAndMarker",
                    "displayName": "Line and markers"
                },
                {
                    "value": "lineOnly",
                    "displayName": "Line only"
                }
            ]
        },
        "categoryAxis": {
            "axisScale": [
                {
                    "value": "linear",
                    "displayName": "Linear"
                },
                {
                    "value": "log",
                    "displayName": "Log"
                }
            ],
            "axisType": [
                {
                    "value": "Scalar",
                    "displayName": "Continuous"
                },
                {
                    "value": "Categorical",
                    "displayName": "Categorical"
                }
            ],
            "axisStyle": [
                {
                    "value": "showTitleOnly",
                    "displayName": "Show title only"
                },
                {
                    "value": "showUnitOnly",
                    "displayName": "Show unit only"
                },
                {
                    "value": "showBoth",
                    "displayName": "Show both"
                }
            ],
            "gridlineStyle": [
                {
                    "value": "dashed",
                    "displayName": "Dashed"
                },
                {
                    "value": "solid",
                    "displayName": "Solid"
                },
                {
                    "value": "dotted",
                    "displayName": "Dotted"
                }
            ],
            "position": [
                {
                    "value": "Left",
                    "displayName": "Left"
                },
                {
                    "value": "Right",
                    "displayName": "Right"
                }
            ]
        },
        "valueAxis": {
            "position": [
                {
                    "value": "Left",
                    "displayName": "Left"
                },
                {
                    "value": "Right",
                    "displayName": "Right"
                }
            ],
            "axisScale": [
                {
                    "value": "linear",
                    "displayName": "Linear"
                },
                {
                    "value": "log",
                    "displayName": "Log"
                }
            ],
            "axisStyle": [
                {
                    "value": "showTitleOnly",
                    "displayName": "Show title only"
                },
                {
                    "value": "showUnitOnly",
                    "displayName": "Show unit only"
                },
                {
                    "value": "showBoth",
                    "displayName": "Show both"
                }
            ],
            "gridlineStyle": [
                {
                    "value": "dashed",
                    "displayName": "Dashed"
                },
                {
                    "value": "solid",
                    "displayName": "Solid"
                },
                {
                    "value": "dotted",
                    "displayName": "Dotted"
                }
            ],
            "secPosition": [
                {
                    "value": "Left",
                    "displayName": "Left"
                },
                {
                    "value": "Right",
                    "displayName": "Right"
                }
            ],
            "secAxisScale": [
                {
                    "value": "linear",
                    "displayName": "Linear"
                },
                {
                    "value": "log",
                    "displayName": "Log"
                }
            ],
            "secAxisStyle": [
                {
                    "value": "showTitleOnly",
                    "displayName": "Show title only"
                },
                {
                    "value": "showUnitOnly",
                    "displayName": "Show unit only"
                },
                {
                    "value": "showBoth",
                    "displayName": "Show both"
                }
            ]
        },
        "lineStyles": {
            "strokeLineJoin": [
                {
                    "value": "miter",
                    "displayName": "Miter"
                },
                {
                    "value": "round",
                    "displayName": "Round"
                },
                {
                    "value": "bevel",
                    "displayName": "Bevel"
                }
            ],
            "lineStyle": [
                {
                    "value": "dashed",
                    "displayName": "Dashed"
                },
                {
                    "value": "solid",
                    "displayName": "Solid"
                },
                {
                    "value": "dotted",
                    "displayName": "Dotted"
                }
            ],
            "markerShape": [
                {
                    "value": "circle",
                    "displayName": "●"
                },
                {
                    "value": "square",
                    "displayName": "■"
                },
                {
                    "value": "diamond",
                    "displayName": "◆"
                },
                {
                    "value": "triangle",
                    "displayName": "▲"
                },
                {
                    "value": "x",
                    "displayName": "☓"
                },
                {
                    "value": "shortDash",
                    "displayName": " -"
                },
                {
                    "value": "longDash",
                    "displayName": "—"
                },
                {
                    "value": "plus",
                    "displayName": "+"
                }
            ]
        },
        "trend": {
            "style": [
                {
                    "value": "dashed",
                    "displayName": "Dashed"
                },
                {
                    "value": "solid",
                    "displayName": "Solid"
                },
                {
                    "value": "dotted",
                    "displayName": "Dotted"
            }
        ]
    },
    "y1AxisReferenceLine": {
        "style": [
            {
                "value": "dashed",
                "displayName": "Dashed"
            },
            {
                "value": "solid",
                "displayName": "Solid"
            },
            {
                "value": "dotted",
                "displayName": "Dotted"
            }
        ],
        "position": [
            {
                "value": "back",
                "displayName": "Behind"
            },
            {
                "value": "front",
                "displayName": "In Front"
            }
        ],
        "dataLabelText": [
            {
                "value": "Value",
                "displayName": "Value"
            },
            {
                "value": "Name",
                "displayName": "Name"
            },
            {
                "value": "ValueAndName",
                "displayName": "Name and Value"
            }
        ],
        "dataLabelHorizontalPosition": [
            {
                "value": "left",
                "displayName": "Left"
            },
            {
                "value": "right",
                "displayName": "Right"
            }
        ],
        "dataLabelVerticalPosition": [
            {
                "value": "above",
                "displayName": "Above"
            },
            {
                "value": "under",
                "displayName": "Under"
            }
        ]
    },
    "referenceLine": {
        "style": [
            {
                "value": "dashed",
                "displayName": "Dashed"
            },
            {
                "value": "solid",
                "displayName": "Solid"
            },
            {
                "value": "dotted",
                "displayName": "Dotted"
            }
        ],
        "position": [
            {
                "value": "back",
                "displayName": "Behind"
            },
            {
                "value": "front",
                "displayName": "In Front"
            }
        ],
        "dataLabelText": [
      {
        "value": "Value",
        "displayName": "Value"
      },
      {
        "value": "Name",
        "displayName": "Name"
      },
      {
        "value": "ValueAndName",
        "displayName": "Name and Value"
      }
    ],
    "dataLabelHorizontalPosition": [
      {
        "value": "left",
        "displayName": "Left"
      },
      {
        "value": "right",
        "displayName": "Right"
      }
    ],
    "dataLabelVerticalPosition": [
      {
        "value": "above",
        "displayName": "Above"
      },
      {
        "value": "under",
        "displayName": "Under"
      }
    ]
    },
    "labels": {
    "labelOrientation": [
      {
        "value": "vertical",
        "displayName": "Vertical"
      },
      {
        "value": "horizontal",
        "displayName": "Horizontal"
      }
    ],
    "labelPosition": [
      {
        "value": "Auto",
        "displayName": "Auto"
      },
      {
        "value": "InsideEnd",
        "displayName": "Inside End"
      },
      {
        "value": "OutsideEnd",
        "displayName": "Outside End"
      },
      {
        "value": "InsideCenter",
        "displayName": "Inside Center"
      },
      {
        "value": "InsideBase",
        "displayName": "Inside Base"
      }
    ],
    "labelStyle": [
      {
        "value": "Category",
        "displayName": "Category"
      },
      {
        "value": "Data",
        "displayName": "Data value"
      },
      {
        "value": "Percent of total",
        "displayName": "Percent of total"
      },
      {
        "value": "Both",
        "displayName": "Category, data value"
      },
      {
        "value": "Category, percent of total",
        "displayName": "Category, percent of total"
      },
      {
        "value": "Data value, percent of total",
        "displayName": "Data value, percent of total"
      },
      {
        "value": "Category, data value, percent of total",
        "displayName": "All detail labels"
      }
     ]
    },
    "card": {
        "outline": [
          {
            "value": "None",
            "displayName": "None"
          },
          {
            "value": "BottomOnly",
            "displayName": "Bottom only"
          },
          {
            "value": "TopOnly",
            "displayName": "Top only"
          },
          {
            "value": "LeftOnly",
            "displayName": "Left only"
          },
          {
            "value": "RightOnly",
            "displayName": "Right only"
          },
          {
            "value": "TopBottom",
            "displayName": "Top + bottom"
          },
          {
            "value": "LeftRight",
            "displayName": "Left + right"
          },
          {
            "value": "Frame",
            "displayName": "Frame"
          }
         ]
    },
    "imageScaling": {
        "imageScalingType": [
          {
            "value": "Normal",
            "displayName": "Normal"
          },
          {
            "value": "Fit",
            "displayName": "Fit"
          },
          {
            "value": "Fill",
            "displayName": "Fill"
          }
        ]
    },
    "forecast": {
        "confidenceBandStyle": [
          {
            "value": "fill",
            "displayName": "Fill"
          },
          {
            "value": "line",
            "displayName": "Line"
          },
          {
            "value": "none",
            "displayName": "None"
          }
        ],
        "style": [
          {
            "value": "dashed",
            "displayName": "Dashed"
          },
          {
            "value": "solid",
            "displayName": "Solid"
          },
          {
            "value": "dotted",
            "displayName": "Dotted"
          }
        ]
        },
        "mapStyles": {
        "mapTheme": [
          {
            "value": "aerial",
            "displayName": "Aerial"
          },
          {
            "value": "canvasDark",
            "displayName": "Dark"
          },
          {
            "value": "canvasLight",
            "displayName": "Light"
          },
          {
            "value": "grayscale",
            "displayName": "Grayscale"
          },
          {
            "value": "road",
            "displayName": "Road"
          }
        ]
    },
    "shape": {
        "projectionEnum": [
          {
            "value": "albersUsa",
            "displayName": "Albers USA"
          },
          {
            "value": "equirectangular",
            "displayName": "Equirectangular"
          },
          {
            "value": "mercator",
            "displayName": "Mercator"
          },
          {
            "value": "orthographic",
            "displayName": "Orthographic"
          }
        ]
        },
        "xAxisReferenceLine": {
        "style": [
          {
            "value": "dashed",
            "displayName": "Dashed"
          },
          {
            "value": "solid",
            "displayName": "Solid"
          },
          {
            "value": "dotted",
            "displayName": "Dotted"
          }
        ],
        "position": [
          {
            "value": "back",
            "displayName": "Behind"
          },
          {
            "value": "front",
            "displayName": "In Front"
          }
        ],
        "dataLabelText": [
          {
            "value": "Value",
            "displayName": "Value"
          },
          {
            "value": "Name",
            "displayName": "Name"
          },
          {
            "value": "ValueAndName",
            "displayName": "Name and Value"
          }
        ],
        "dataLabelHorizontalPosition": [
          {
            "value": "left",
            "displayName": "Left"
          },
          {
            "value": "right",
            "displayName": "Right"
          }
        ],
        "dataLabelVerticalPosition": [
          {
            "value": "above",
            "displayName": "Above"
          },
          {
            "value": "under",
            "displayName": "Under"
          }
        ]
        },
        "ratioLine": {
        "style": [
          {
            "value": "dashed",
            "displayName": "Dashed"
          },
          {
            "value": "solid",
            "displayName": "Solid"
          },
          {
            "value": "dotted",
            "displayName": "Dotted"
          }
        ]
        },
        "columnHeaders": {
        "outline": [
          {
            "value": "None",
            "displayName": "None"
          },
          {
            "value": "BottomOnly",
            "displayName": "Bottom only"
          },
          {
            "value": "TopOnly",
            "displayName": "Top only"
          },
          {
            "value": "LeftOnly",
            "displayName": "Left only"
          },
          {
            "value": "RightOnly",
            "displayName": "Right only"
          },
          {
            "value": "TopBottom",
            "displayName": "Top + bottom"
          },
          {
            "value": "LeftRight",
            "displayName": "Left + right"
          },
          {
            "value": "Frame",
            "displayName": "Frame"
          }
        ]
        },
        "values": {
        "outline": [
          {
            "value": "None",
            "displayName": "None"
          },
          {
            "value": "BottomOnly",
            "displayName": "Bottom only"
          },
          {
            "value": "TopOnly",
            "displayName": "Top only"
          },
          {
            "value": "LeftOnly",
            "displayName": "Left only"
          },
          {
            "value": "RightOnly",
            "displayName": "Right only"
          },
          {
            "value": "TopBottom",
            "displayName": "Top + bottom"
          },
          {
            "value": "LeftRight",
            "displayName": "Left + right"
          },
          {
            "value": "Frame",
            "displayName": "Frame"
          }
        ]
        },
        "total": {
        "outline": [
          {
            "value": "None",
            "displayName": "None"
          },
          {
            "value": "BottomOnly",
            "displayName": "Bottom only"
          },
          {
            "value": "TopOnly",
            "displayName": "Top only"
          },
          {
            "value": "LeftOnly",
            "displayName": "Left only"
          },
          {
            "value": "RightOnly",
            "displayName": "Right only"
          },
          {
            "value": "TopBottom",
            "displayName": "Top + bottom"
          },
          {
            "value": "LeftRight",
            "displayName": "Left + right"
          },
          {
            "value": "Frame",
            "displayName": "Frame"
          }
        ]
        },
        "rowHeaders": {
        "outline": [
          {
            "value": "None",
            "displayName": "None"
          },
          {
            "value": "BottomOnly",
            "displayName": "Bottom only"
          },
          {
            "value": "TopOnly",
            "displayName": "Top only"
          },
          {
            "value": "LeftOnly",
            "displayName": "Left only"
          },
          {
            "value": "RightOnly",
            "displayName": "Right only"
          },
          {
            "value": "TopBottom",
            "displayName": "Top + bottom"
          },
          {
            "value": "LeftRight",
            "displayName": "Left + right"
          },
          {
            "value": "Frame",
            "displayName": "Frame"
          }
        ]
        },
        "subTotals": {
        "outline": [
          {
            "value": "None",
            "displayName": "None"
          },
          {
            "value": "BottomOnly",
            "displayName": "Bottom only"
          },
          {
            "value": "TopOnly",
            "displayName": "Top only"
          },
          {
            "value": "LeftOnly",
            "displayName": "Left only"
          },
          {
            "value": "RightOnly",
            "displayName": "Right only"
          },
          {
            "value": "TopBottom",
            "displayName": "Top + bottom"
          },
          {
            "value": "LeftRight",
            "displayName": "Left + right"
          },
          {
            "value": "Frame",
            "displayName": "Frame"
          }
        ],
        "rowSubtotalsPosition": [
          {
            "value": "Top",
            "displayName": "Top"
          },
          {
            "value": "Bottom",
            "displayName": "Bottom"
          }
        ]
        },
        "general": {
        "orientation": [
          {
            "value": "vertical",
            "displayName": "Vertical"
          },
          {
            "value": "horizontal",
            "displayName": "Horizontal"
          }
        ]
        },
        "data": {
        "relativeRange": [
          {
            "value": "Last",
            "displayName": "Last"
          },
          {
            "value": "Next",
            "displayName": "Next"
          },
          {
            "value": "This",
            "displayName": "This"
          }
        ],
        "relativePeriod": [
          {
            "value": "None",
            "displayName": "Select"
          },
          {
            "value": "Days",
            "displayName": "Days"
          },
          {
            "value": "Weeks",
            "displayName": "Weeks"
          },
          {
            "value": "Calendar Weeks",
            "displayName": "Weeks (Calendar)"
          },
          {
            "value": "Months",
            "displayName": "Months"
          },
          {
            "value": "Calendar Months",
            "displayName": "Months (Calendar)"
          },
          {
            "value": "Years",
            "displayName": "Years"
          },
          {
            "value": "Calendar Years",
            "displayName": "Years (Calendar)"
          }
        ],
        "mode": [
          {
            "value": "Between",
            "displayName": "Between"
          },
          {
            "value": "Before",
            "displayName": "Before"
          },
          {
            "value": "After",
            "displayName": "After"
          },
          {
            "value": "Basic",
            "displayName": "List"
          },
          {
            "value": "Dropdown",
            "displayName": "Dropdown"
          },
          {
            "value": "Relative",
            "displayName": "Relative"
          },
          {
            "value": "Single",
            "displayName": "Single Value"
          }
        ]
        },
        "header": {
        "outline": [
          {
            "value": "None",
            "displayName": "None"
          },
          {
            "value": "BottomOnly",
            "displayName": "Bottom only"
          },
          {
            "value": "TopOnly",
            "displayName": "Top only"
          },
          {
            "value": "LeftOnly",
            "displayName": "Left only"
          },
          {
            "value": "RightOnly",
            "displayName": "Right only"
          },
          {
            "value": "TopBottom",
            "displayName": "Top + bottom"
          },
          {
            "value": "LeftRight",
            "displayName": "Left + right"
          },
          {
            "value": "Frame",
            "displayName": "Frame"
          }
        ]
        },
        "items": {
        "outline": [
          {
            "value": "None",
            "displayName": "None"
          },
          {
            "value": "BottomOnly",
            "displayName": "Bottom only"
          },
          {
            "value": "TopOnly",
            "displayName": "Top only"
          },
          {
            "value": "LeftOnly",
            "displayName": "Left only"
          },
          {
            "value": "RightOnly",
            "displayName": "Right only"
          },
          {
            "value": "TopBottom",
            "displayName": "Top + bottom"
          },
          {
            "value": "LeftRight",
            "displayName": "Left + right"
          },
          {
            "value": "Frame",
            "displayName": "Frame"
          }
        ]
        },
        "status": {
        "direction": [
          {
            "value": "Positive",
            "displayName": "High is good"
          },
          {
            "value": "Negative",
            "displayName": "Low is good"
          }
         ]
       }
    }
  }
}
```

## <a name="limitations-and-considerations"></a>제한 사항 및 고려 사항

원래 테마인 “클래식” 테마 중 하나를 사용하거나 원래 테마 이외에 가져온 사용자 지정 테마를 사용하는 경우 테마 대화 상자의 텍스트 섹션을 구성할 수 없습니다.

이 제한의 영향을 받는 기본 제공 테마에는 다음 테마가 포함됩니다.
* Classic
* 도시 공원
* 교실
* 색맹 지원
* 일렉트로닉
* 고대비
* 일몰
* 석양

영향을 받는 테마 중 하나를 사용하고 텍스트 설정을 수정할 필요가 없는 경우에는 문제없이 대화 상자의 다른 탭을 안전하게 사용할 수 있습니다. 그러나 영향을 받는 테마 중 하나와 함께 텍스트 클래스를 사용하려는 경우 다음과 같은 몇 가지 옵션이 있습니다.

- 텍스트 클래스를 사용하도록 설정하는 가장 빠르고 쉬운 방법은 기본 테마 옵션을 선택하는 것입니다.
- 현재 사용자 지정 테마를 유지하려면 텍스트 탭을 사용하도록 설정합니다.
  1. 현재 테마를 내보냅니다.
  1. 기본 테마를 선택합니다.
  1. 첫 번째 단계에서 내보낸 사용자 지정 테마를 가져옵니다.

보고서의 텍스트는 다르게 보이지만 테마 대화 상자의 텍스트 탭에 액세스할 수 있습니다.


