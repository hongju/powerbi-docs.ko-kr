---
title: Power BI 모바일 앱의 특정 위치에 대한 링크 만들기
description: Power BI 모바일 앱에서 URI(Uniform Resource Identifier)를 사용하여 특정 대시보드, 타일 또는 보고서에 대한 딥 링크를 만드는 방법에 대해 알아봅니다.
author: mshenhav
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: conceptual
ms.date: 04/24/2019
ms.author: mshenhav
ms.openlocfilehash: 427019d831aa02723f17efd3de78081c368717c2
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2019
ms.locfileid: "73879283"
---
# <a name="create-a-link-to-a-specific-location-in-the-power-bi-mobile-apps"></a>Power BI 모바일 앱의 특정 위치에 대한 링크 만들기
링크를 사용하여 Power BI의 보고서, 대시보드 및 타일에 직접 액세스할 수 있습니다.

Power BI 모바일에서 링크를 사용하는 경우는 다음과 같이 두 가지입니다. 

* **앱 외부**에서 Power BI를 열고 특정 콘텐츠(보고서/대시보드/앱) 표시. 이것은 주로 다른 앱에서 Power BI 모바일을 열기 위한 통합 시나리오입니다. 
* Power BI 내에서 **이동**하는 경우. Power BI에서 사용자 지정 탐색을 사용하려는 경우입니다.


## <a name="use-links-from-outside-of-power-bi"></a>Power BI 외부에서 링크 사용
Power BI 앱 외부에서 링크를 사용하는 경우, 링크가 앱으로 열리도록 해야 하며, 디바이스에 앱이 설치되어 있지 않다면 설치 제안이 표시되도록 해야 합니다. 정확히 이 기능을 수행할 수 있도록 특별한 링크 형식이 준비되어 있습니다. 이 링크 형식을 사용하면 디바이스가 링크를 사용하여 앱을 열게 되고, 디바이스에 앱이 설치되어 있지 않다면 스토어로 이동하여 앱을 받으라는 제안이 표시됩니다.

링크는 다음과 같이 시작해야 합니다.  
```html
https://app.powerbi.com/Redirect?[**QUERYPARAMS**]
```

> [!IMPORTANT]
> 콘텐츠가 정부, 중국과 같은 특수 데이터 센터에 호스트된 경우, 링크가 `app.powerbigov.us` 또는 `app.powerbi.cn`과 같이 올바른 Power BI 주소로 시작해야 합니다.   
>


**쿼리 매개 변수**는 다음과 같습니다.
* **action**(필수) = OpenApp / OpenDashboard / OpenTile / OpenReport
* **appId** = 특정 앱의 일부인 보고서 또는 대시보드를 열려는 경우 
* **groupObjectId** = (내 작업 영역이 아닌) 작업 영역의 일부인 보고서 또는 대시보드를 열려는 경우
* **dashboardObjectId** = 대시보드 개체 ID(action이 OpenDashboard 또는 OpenTile인 경우)
* **reportObjectId** = 보고서 개체 ID(action이 OpenReport인 경우)
* **tileObjectId** = 타일 개체 ID(action이 OpenTile인 경우)
* **reportPage** = 특정 보고서 섹션을 열려는 경우(action이 OpenReport인 경우)
* **ctid** = 항목 조직 ID(B2B 시나리오에서 사용. 항목이 사용자 조직에 속한 것이면 생략 가능)

**예:**

* 앱 링크 열기 
  ```html
  https://app.powerbi.com/Redirect?action=OpenApp&appId=appidguid&ctid=organizationid
  ```

* 특정 앱의 일부인 대시보드 열기 
  ```html
  https://app.powerbi.com/Redirect?action=OpenDashboard&appId=**appidguid**&dashboardObjectId=**dashboardidguid**&ctid=**organizationid**
  ```

* 작업 영역의 일부인 보고서 열기
  ```html
  https://app.powerbi.com/Redirect?Action=OpenReport&reportObjectId=**reportidguid**&groupObjectId=**groupidguid**&reportPage=**ReportSectionName**
  ```

### <a name="how-to-get-the-right-link-format"></a>올바른 링크 형식을 구성하는 방법

#### <a name="links-of-apps-and-items-in-app"></a>앱 링크와 앱에 있는 항목 링크

**앱과 앱에 포함된 보고서 및 대시보드**의 경우, 링크를 얻는 가장 쉬운 방법은 작업 영역으로 이동해서 “앱 업데이트”를 선택하는 것입니다. 이렇게 하면 “앱 게시” 환경이 열리고 ‘액세스’ 탭에서 **링크** 섹션을 찾을 수 있습니다. 이 섹션을 확장하면 앱과 콘텐츠를 직접 액세스하는 데 사용할 수 있는 앱 링크와 해당 앱의 콘텐츠 링크를 볼 수 있습니다.

![Power BI 앱 게시 링크 ](./media/mobile-apps-links/mobile-link-copy-app-links.png)

#### <a name="links-of-items-not-in-app"></a>앱에 포함되지 않은 항목의 링크 

특정 앱의 일부가 아닌 보고서 및 대시보드의 경우, 항목 URL에서 ID를 추출해야 합니다.

예를 들어, 36자의 **대시보드** 개체 ID를 찾으려면 Power BI 서비스에서 해당 대시보드로 이동합니다. 

```html
https://app.powerbi.com/groups/me/dashboards/**dashboard guid comes here**?ctid=**organization id comes here**`
```

36자의 **보고서** 개체 ID를 찾으려면 Power BI 서비스에서 해당 보고서로 이동합니다.
다음은 “내 작업 영역”에 있는 보고서를 사용한 예입니다.

```html
https://app.powerbi.com/groups/me/reports/**report guid comes here**/ReportSection3?ctid=**organization id comes here**`
```
위 URL은 보고서 페이지 **“ReportSection3”** 도 포함하고 있습니다.

다음은 (내 작업 영역이 아닌) 작업 영역에 있는 보고서를 사용한 예입니다.

```html
https://app.powerbi.com/groups/**groupid comes here**/reports/**reportid comes here**/ReportSection1?ctid=**organizationid comes here**
```

## <a name="use-links-inside-power-bi"></a>Power BI 내의 링크 사용

Power BI 내의 링크는 Power BI 서비스에서와 동일한 방식으로 모바일 앱에서 작동합니다.

보고서에 다른 Power BI 항목을 가리키는 링크를 추가하려면 브라우저 주소 표시줄에서 항목 URL을 복사하면 됩니다. [보고서에 있는 텍스트 상자에 하이퍼링크를 추가하는 방법](https://docs.microsoft.com/power-bi/service-add-hyperlink-to-text-box)을 자세히 알아보세요.

## <a name="use-report-url-with-filter"></a>필터가 있는 보고서 URL 사용
Power BI 모바일 앱은 Power BI 서비스와 마찬가지로 필터 쿼리 매개 변수를 포함하는 보고서 URL을 지원합니다. Power BI 모바일 앱에서 보고서를 열어서 특정 상태로 필터링할 수도 있습니다. 예를 들어, 다음 URL은 판매 보고서를 열고 지역을 기준으로 필터링합니다.

```html
https://app.powerbi.com/groups/me/reports/**report guid comes here**/ReportSection3?ctid=**organization id comes here**&filter=Store/Territory eq 'NC'
```

[보고서를 필터링하는 쿼리 매개 변수를 작성하는 방법](https://docs.microsoft.com/power-bi/service-url-filters)을 자세히 알아보세요.

## <a name="next-steps"></a>다음 단계
사용자 의견은 나중에 구현할 사항을 결정하는 데 도움이 됩니다. 따라서 Power BI 모바일 앱에서 참조하고자 하는 다른 기능에 대해 꼭 투표해주세요. 

* [모바일 디바이스용 Power BI 앱](mobile-apps-for-mobile-devices.md)
* Twitter에서 @MSPowerBI 팔로우
* [Power BI 커뮤니티](https://community.powerbi.com/)에서 대화에 참여
* [Power BI란?](../../fundamentals/power-bi-overview.md)

