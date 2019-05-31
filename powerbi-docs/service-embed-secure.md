---
title: 보안 포털 또는 웹 사이트에 보고서 포함
description: Power BI 기능 사용 하면 사용자를 쉽게 포함 하 고 안전 하 게 내부 웹 포털에서 보고서를 포함 합니다.
author: rkarlin
ms.author: rkarlin
manager: kfile
ms.reviewer: lukaszp
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/20/2019
LocalizationGroup: Share your work
ms.openlocfilehash: bf9d7bcdf6ddaf7d0063843a5314233989b2dadd
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "66222253"
---
# <a name="embed-a-report-in-a-secure-portal-or-website"></a>보안 포털 또는 웹 사이트에 보고서 포함

새 **Embed** 쉽고 안전 하 게 보고서 포함할 수 있습니다 내부 웹 포털에서 Power BI에 대 한 옵션을 보고 합니다. 이러한 포털 수 **클라우드 기반** 또는 **호스팅된 온-프레미스**, SharePoint 2019 등입니다. 포함 된 보고서를 통해 모든 항목 권한 및 데이터 보안 유지 [행 수준 보안 (RLS)](service-admin-rls.md)합니다. 코드 없는 포함 URL 또는 iFrame 허용 하는 모든 포털에 제공 합니다. 

합니다 **Embed** 지원 옵션 [URL 필터](service-url-filters.md) 및 URL 설정 합니다. 만 기본 HTML 및 JavaScript를 알 필요가 로우 코드 방법을 사용 하는 포털을 통합할 수 있습니다.

## <a name="how-to-embed-power-bi-reports-into-portals"></a>Power BI 보고서를 포털에 **포함**하는 방법

1. 새로운 **포함** 옵션은 Power BI 서비스의 보고서에 대한 **파일** 메뉴에서 사용 가능합니다.

    ![안전한 포함 옵션 드롭다운 목록 옵션](media/service-embed-secure/secure-embed-drop-down-menu.png)

2. 선택 합니다 **Embed** 옵션 링크와 보고서를 안전 하 게 포함 하 여 iFrame을 제공 하는 대화 상자를 엽니다.

    ![포함 옵션 대화 상자](media/service-embed-secure/secure-embed-code-dialog.png)

3. 에서는 사용자가 보고서 URL에 직접 또는 웹 포털에 포함 된 하나 보고서 액세스에는 인증이 필요 합니다. 사용자가 없습니다 로그인 Power BI에 브라우저 세션의 경우 다음 화면에 표시 됩니다. 선택할 때 **로그인**, 새 브라우저 창이 나 탭을 열 수 있습니다. 로그인 하 라는 메시지가 표시 되지 경우 팝업 차단 기능에 대 한 확인 하 게 합니다.

    ![로그인하여 보고서 보기](media/service-embed-secure/secure-embed-sign-in.png)

4. 사용자가 로그인 한 후 보고서가 열리면 데이터를 표시 하 고 페이지 탐색 및 필터 설정을 허용 합니다. 보기 권한이 있는 사용자만 Power BI에서 보고서를 볼 수 있습니다. 모든 [행 수준 보안 (RLS)](service-admin-rls.md) 규칙도 적용 됩니다. 마지막으로 사용자는 올바른 사용 허가가 있어야 합니다. 사용자에게 Power BI Pro 라이선스가 필요하거나 보고서가 Power BI Premium 용량 내 작업 영역에 있어야 합니다. 사용자가 새 브라우저 창을 열 때마다 로그인 해야 합니다. 그러나 로그인 한 후 다른 보고서 자동으로 로드 합니다.

    ![보고서 포함](media/service-embed-secure/secure-embed-report.png)

5. IFrame을 사용 하는 경우 편집 해야 할 수 있습니다 합니다 **높이** 하 고 **너비** 포털의 웹 페이지에 맞게 조정 해야 합니다.

    ![높이 및 너비 설정](media/service-embed-secure/secure-embed-size.png)

## <a name="granting-report-access"></a>보고서 액세스 권한 부여

합니다 **Embed** 옵션 사용자가 보고서를 볼 수를 자동으로 허용 하지 않습니다. 사용 권한 보기는 Power BI 서비스에서 설정 됩니다.

Power BI 서비스에 대 한 액세스가 필요한 사용자를 사용 하 여 포함 된 보고서를 공유할 수 있습니다. Office 365 그룹을 사용 하는 경우 앱 작업 영역 구성원으로 사용자를 나열할 수 있습니다. 자세한 내용은 참조 하는 방법 [Power BI 및 Office 365에서 앱 작업 영역 관리](service-manage-app-workspace-in-power-bi-and-office-365.md)합니다.

## <a name="licensing"></a>라이선싱

포함된 된 보고서를 보려면 사용자는 Power BI Pro 라이선스 필요 또는 콘텐츠가 있는 작업 영역에는 [Power BI 프리미엄 용량 (전각 또는 P SKU)](service-admin-premium-purchase.md)합니다.

## <a name="customize-your-embed-experience-using-url-settings"></a>URL 설정을 사용한 포함 환경 사용자 지정

Embed URL의 입력된 설정을 사용 하 여 사용자 환경을 사용자 지정할 수 있습니다. 제공 된 iFrame의 URL을 업데이트할 수 있습니다 **src** 설정 합니다.

| 속성  | 설명  |  |  |  |
|--------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---|---|---|
| pageName  | 사용할 수는 **pageName** 쿼리 문자열 매개 변수를 열려면 보고서 페이지를 설정 합니다. 찾을 수 있습니다이 값을 보고서 URL의 끝에 Power BI 서비스에서 보고서를 볼 때 아래와 같이. |  |  |  |
| URL 필터  | 사용할 수 있습니다 [URL 필터](service-url-filters.md) embed URL에 포함 콘텐츠를 필터링 하려면 Power BI UI에서 수신 합니다. 이러한 방식으로 기본 HTML 및 JavaScript 환경만으로 로우 코드 통합을 빌드할 수 있습니다.  |  |  |  |

## <a name="set-which-page-opens-for-an-embedded-report"></a>집합에 포함된 된 보고서에 대 한 페이지를 엽니다 

찾을 수 있습니다 합니다 **pageName** Power BI 서비스에서 보고서를 볼 때 보고서 URL의 끝에 있는 값입니다.

1. 웹 브라우저에서 Power BI 서비스에서 보고서를 열고 주소 표시줄의 URL을 복사 합니다.

    ![보고서 섹션](media/service-embed-secure/secure-embed-report-section.png)

2. **pageName** 설정을 URL에 추가합니다.

    ![pageName 추가](media/service-embed-secure/secure-embed-append-page-name.png)

## <a name="filter-report-content-using-url-filters"></a>URL 필터를 사용하여 보고서 내용 필터링 

사용할 수 있습니다 [URL 필터](service-url-filters.md) 다른 보고서 뷰를 제공 합니다. 예를 들어 아래 URL은 보고서를 필터링하여 에너지 산업에 대한 데이터를 표시합니다.

**pageName** 및 [URL 필터](service-url-filters.md)의 조합은 강력할 수 있습니다. 기본 HTML 및 JavaScript를 사용하여 환경을 빌드할 수 있습니다.

예를 들어 이것은 단추 HTML 페이지에 추가할 수 있습니다.

```html
<button class="textLarge" onclick='show("ReportSection", "Energy");' style="display: inline-block;">Show Energy</button>
```

옵션을 선택 하면 단추는 에너지 산업 필터를 포함 하는 업데이트 된 URL을 사용 하 여 iFrame을 업데이트 하는 함수를 호출 합니다.

```javascript
function show(pageName, filterValue)

{

var newUrl = baseUrl + "&pageName=" + pageName;

if(null != filterValue && "" != filterValue)

{

newUrl += "&$filter=Industries/Industry eq '" + filterValue + "'";

}

//Assumes there’s an iFrame on the page with id=”iFrame”

var report = document.getElementById("iFrame")

report.src = newUrl;

}
```

![필터](media/service-embed-secure/secure-embed-filter.png)

원하는 만큼 단추를 추가하여 로우 코드 사용자 지정 환경을 생성할 수 있습니다. 

## <a name="considerations-and-limitations"></a>고려 사항 및 제한 사항

* Azure B2B(Business to Business)를 사용한 외부 게스트 사용자를 지원하지 않습니다.

* 보안 포함은 Power BI 서비스에 게시된 보고서에 대해 작동합니다.

* 사용자가 새 브라우저 창을 열 때마다 보고서를 보려면 로그인 해야 합니다.

* 일부 브라우저를 사용 해야 InPrivate 또는 Incognito 모드를 사용 하는 경우에 특히, 로그인 한 후 페이지를 새로 고칠 수 있습니다.

* Single sign-on 환경을 위해, SharePoint Online 옵션에 포함을 사용 하거나 사용 하 여 사용자 지정 통합 빌드를 [사용자 소유 데이터](developer/embed-sample-for-your-organization.md) 메서드를 포함 합니다. 

* **포함** 옵션에 제공되는 자동 인증 기능은 Power BI JavaScript API에서 작동하지 않습니다. Power BI JavaScript API를 사용 합니다 [사용자 소유 데이터](developer/embed-sample-for-your-organization.md) 메서드를 포함 합니다. 

## <a name="next-steps"></a>다음 단계

* [Power BI에서 공유 하는 방법](service-how-to-collaborate-distribute-dashboards-reports.md)

* [URL에 쿼리 문자열 매개 변수를 사용 하 여 보고서 필터링](service-url-filters.md)

* [SharePoint Online에 보고서 웹 파트 포함](service-embed-report-spo.md)

* [Power BI에서 웹에 게시](service-publish-to-web.md)