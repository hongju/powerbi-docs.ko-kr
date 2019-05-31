---
title: Power BI 모바일 앱의 특정 위치에 대한 링크 만들기
description: Power BI 모바일 앱에서 URI(Uniform Resource Identifier)를 사용하여 특정 대시보드, 타일 또는 보고서에 대한 딥 링크를 만드는 방법에 대해 알아봅니다.
author: mshenhav
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: conceptual
ms.date: 04/24/2019
ms.author: mshenhav
ms.openlocfilehash: 4e09b10e38b018f8e5572343b343a243ace3bf81
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "64906520"
---
# <a name="create-a-link-to-a-specific-location-in-the-power-bi-mobile-apps"></a>Power BI 모바일 앱의 특정 위치에 대한 링크 만들기
링크를 사용 하 여 Power BI에서 특정 항목에 직접 액세스할 수 있습니다. 보고서, 대시보드 및 타일입니다.

Power BI 모바일에서 링크를 사용 하는 방법은 주로 두 개의 시나리오가 있습니다. 

* Power BI에서 열려는 **앱 외부에서**, 및 특정 콘텐츠 (앱/보고서/대시보드)를 방문 합니다. 이것이 일반적으로 통합 시나리오를 다른 앱에서 Power BI Mobile을 열려고 할 때입니다. 
* 하 **이동** Power BI 내에서. 이것이 일반적으로 Power BI에서 사용자 지정 탐색을 만들려는 경우입니다.


## <a name="use-links-from-outside-of-power-bi"></a>Power BI 외부에서 사용 하 여 링크
앱에서 열 수를 확인 하려는 Power BI 앱 외부에서 링크를 사용 하면 장치에서 다음 사용자가 설치 하도록 제공 하는 앱이 설치 되지 경우. 정확 하 게 지원 하기 위해 특별 링크 형식을 만들었습니다. 이 링크 형식에는 장치 앱을 사용 하는 링크를 열려면을 가져오려고 스토어로 이동 하 여 사용자는 제공할 앱을 장치에 설치 되어 있지 않으면, 있는지 확인 하십시오.

다음 링크를 시작할지  
```html
https://app.powerbi.com/Redirect?[**QUERYPARAMS**]
```

> [!IMPORTANT]
> 경우 콘텐츠는 정부, 중국 등과 같은 특수 한 데이터 센터에서 호스팅됩니다. 링크와 같은 올바른 Power BI 주소를 사용 하 여 시작 해야 `app.powerbigov.us` 또는 `app.powerbi.cn`합니다.   
>


합니다 **쿼리 매개 변수** 됩니다.
* **작업** (필수) OpenApp = / OpenDashboard / OpenTile / OpenReport
* **appId** = 보고서 또는 앱의 일부인 대시보드를 열려는 경우 
* **groupObjectId** = 작업 영역 (내 작업 영역에 없습니다)의 일부인 대시보드 또는 보고서를 열려는 경우
* **dashboardObjectId** 대시보드 개체 ID (작업이 OpenDashboard 또는 OpenTile) =
* **reportObjectId** = 보고서 개체 ID (작업 OpenReport 경우)
* **tileObjectId** = 타일 개체 ID (작업 OpenTile 경우)
* **reportPage** = (동작은 OpenReport) 하는 경우 특정 보고서 섹션을 열려고 할 경우
* **ctid** = 항목 조직 ID (B2B 시나리오에 대 한 관련이 있습니다. 이 경우 생략할 수 있습니다 사용자의 조직에 속하는 항목).

**예제:**

* 앱 열기 링크 
  ```html
  https://app.powerbi.com/Redirect?action=OpenApp&appId=appidguid&ctid=organizationid
  ```

* 앱의 일부인 대시보드 열기 
  ```html
  https://app.powerbi.com/Redirect?action=OpenDashboard&appId=**appidguid**&dashboardObjectId=**dashboardidguid**&ctid=**organizationid**
  ```

* 작업 영역에 포함 된 보고서 열기
  ```html
  https://app.powerbi.com/Redirect?Action=OpenReport&reportObjectId=**reportidguid**&groupObjectId=**groupidguid**&reportPage=**ReportSectionName**
  ```

### <a name="how-to-get-the-right-link-format"></a>오른쪽 링크 형식을 가져오는 방법

#### <a name="links-of-apps-and-items-in-app"></a>앱 및 앱에서 항목의 링크

에 대 한 **보고서, 앱 및 앱의 일부인 대시보드**, 링크를 가져오는 가장 쉬운 방법은 앱 작업 영역으로 이동 하 고 "앱 업데이트"를 선택 하는 것입니다. 이 "앱에 게시 하는 방법" 환경을 열고 액세스 탭에서 찾을 수 있습니다는 **링크** 섹션입니다. 직접 액세스 하 고 섹션에는 앱 목록이 표시 됩니다 하 고 모든 해당 콘텐츠를 연결 하는 확장을 사용할 수 있습니다.

![Power BI 앱 링크를 게시 ](./media/mobile-apps-links/mobile-link-copy-app-links.png)

#### <a name="links-of-items-not-in-app"></a>앱에 없는 항목의 링크 

보고서 및 대시보드를 앱의 일부분이 아닌 항목 URL에서 Id를 추출 해야 합니다.

예를 들어, 36 자의 찾으려는 **대시보드** 개체 ID, Power BI 서비스의 특정 대시보드로 이동 

```html
https://app.powerbi.com/groups/me/dashboards/**dashboard guid comes here**?ctid=**organization id comes here**`
```

36 자의 찾으려고 **보고서** 개체 ID, Power BI 서비스에서 특정 보고서로 이동 합니다.
이 "내 작업 영역"에서 보고서의 예

```html
https://app.powerbi.com/groups/me/reports/**report guid comes here**/ReportSection3?ctid=**organization id comes here**`
```
위의 URL도 포함 됩니다. 특정 보고서 페이지 **"ReportSection3"** 합니다.

이것이 (없습니다: 내 작업 영역) 작업 영역에서 보고서의 예

```html
https://app.powerbi.com/groups/**groupid comes here**/reports/**reportid comes here**/ReportSection1?ctid=**organizationid comes here**
```

## <a name="use-links-inside-power-bi"></a>Power BI 내에서 링크를 사용 합니다.

Power BI 서비스에서와 똑같이 모바일 앱에서 Power BI 내에서 링크가 작동 합니다.

다른 Power BI 항목을 가리키는 보고서에 링크를 추가 하려는 경우 브라우저 주소 표시줄에서 해당 항목 URL만 복사할 수 있습니다. 에 대해 자세히 알아보세요 [보고서에서 텍스트 상자에 하이퍼링크를 추가 하는 방법을](https://docs.microsoft.com/power-bi/service-add-hyperlink-to-text-box)합니다.

## <a name="use-report-url-with-filter"></a>필터로 사용 하 여 보고서 URL
Power BI 서비스와 동일 하지만, Power BI 모바일 앱도 지원 필터 쿼리 매개 변수를 포함 하는 보고서 URL입니다. Power BI 모바일 앱에서 보고서를 열 수 있으며 특정 상태로 필터링 수 있습니다. 예를 들어이 URL이 판매 보고서 열리고 지역별 필터링

```html
https://app.powerbi.com/groups/me/reports/**report guid comes here**/ReportSection3?ctid=**organization id comes here**&filter=Store/Territory eq 'NC'
```

자세한 내용은 [쿼리 매개 변수 필터를 작성 하는 방법을 보고](https://docs.microsoft.com/power-bi/service-url-filters)합니다.

## <a name="next-steps"></a>다음 단계
사용자 의견은 나중에 구현할 사항을 결정하는 데 도움이 됩니다. 따라서 Power BI 모바일 앱에서 참조하고자 하는 다른 기능에 대해 꼭 투표해주세요. 

* [모바일 디바이스용 Power BI 앱](mobile-apps-for-mobile-devices.md)
* Twitter에서 @MSPowerBI 팔로우
* [Power BI 커뮤니티](http://community.powerbi.com/)에서 대화에 참여
* [Power BI란?](../../power-bi-overview.md)

