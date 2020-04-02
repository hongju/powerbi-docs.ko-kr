---
title: 보안 포털 또는 웹 사이트에 보고서 포함
description: Power BI 포함 기능을 사용하여 사용자가 내부 웹 포털에 보고서를 쉽고 안전하게 포함하도록 할 수 있습니다.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: lukaszp
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 01/30/2020
LocalizationGroup: Share your work
ms.openlocfilehash: f4da9179ef140fd254939a4121e91dd032269c98
ms.sourcegitcommit: 53c2b5ea4ee1fe2659804d5ccc8e4bb445a8bcad
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/01/2020
ms.locfileid: "76913597"
---
# <a name="embed-a-report-in-a-secure-portal-or-website"></a>보안 포털 또는 웹 사이트에 보고서 포함

Power BI 보고서의 새 **포함** 옵션을 사용하여 내부 웹 포털에 보고서를 쉽고 안전하게 포함할 수 있습니다. 이러한 포털은 **클라우드 기반**이거나 **온-프레미스에 호스트**될 수 있습니다(예: SharePoint 2019). 포함된 보고서는 [RLS(행 수준 보안)](service-admin-rls.md)를 통해 모든 항목 사용 권한 및 데이터 보안을 준수합니다. 이 기능은 URL 또는 iFrame을 허용하는 모든 포털에 대한 코드 없는 포함을 지원합니다. 

**포함** 옵션은 또한 [URL 필터](service-url-filters.md) 및 URL 설정을 지원합니다. 또한 기본 HTML 및 JavaScript 지식만 있으면 로우 코드 접근 방식을 사용하는 포털과 통합할 수 있습니다.

## <a name="how-to-embed-power-bi-reports-into-portals"></a>Power BI 보고서를 포털에 **포함**하는 방법

1. 새로운 **포함** 옵션은 Power BI 서비스의 보고서에 대한 **파일** 메뉴에서 사용 가능합니다.

    ![안전한 포함 옵션 드롭다운 목록 옵션](media/service-embed-secure/secure-embed-drop-down-menu.png)

2. **포함** 옵션을 선택하면 보고서를 안전하게 포함하는 데 사용할 수 있는 링크와 iFrame을 제공하는 대화 상자가 열립니다.

    ![포함 옵션 대화 상자](media/service-embed-secure/secure-embed-code-dialog.png)

3. 보고서 URL을 직접 열거나 웹 포털에 포함된 보고서를 열거나 상관없이 보고서에 액세스하려면 인증을 받아야 합니다. 사용자가 브라우저 세션에서 Power BI에 로그인하지 않은 경우 다음 화면이 표시됩니다. 사용자가 **로그인**을 선택하면 새 브라우저 창 또는 탭이 열릴 수 있습니다. 로그인 메시지가 표시되지 않는 경우 팝업 차단을 확인합니다.

    ![로그인하여 보고서 보기](media/service-embed-secure/secure-embed-sign-in.png)

4. 사용자가 로그인한 이후 보고서가 열리고, 데이터가 표시되어 페이지를 탐색하거나 필터를 설정할 수 있습니다. 보기 권한이 있는 사용자만 Power BI에서 보고서를 볼 수 있습니다. 모든 [RLS(행 수준 보안)](service-admin-rls.md) 규칙 또한 적용됩니다. 마지막으로 사용자는 올바른 사용 허가가 있어야 합니다. 사용자에게 Power BI Pro 라이선스가 필요하거나 보고서가 Power BI Premium 용량 내 작업 영역에 있어야 합니다. 사용자는 새 브라우저 창을 열 때마다 로그인해야 합니다. 하지만 로그인한 이후에는 다른 보고서가 자동으로 로드됩니다.

    ![보고서 포함](media/service-embed-secure/secure-embed-report.png)

5. IFrame을 사용하는 경우 **높이**와 **너비**를 포털의 웹 페이지에 맞게 편집해야 할 수 있습니다.

    ![높이 및 너비 설정](media/service-embed-secure/secure-embed-size.png)

## <a name="granting-report-access"></a>보고서 액세스 권한 부여

**포함** 옵션은 자동으로 사용자가 보고서를 볼 수 있도록 허용하지 않습니다. 보기 권한은 Power BI 서비스에서 설정합니다.

Power BI 서비스에서 포함된 보고서를 액세스해야 하는 사용자와 공유할 수 있습니다. Office 365 그룹을 사용하는 경우 사용자를 작업 영역의 구성원으로 나열할 수 있습니다. 자세한 내용은 [Power BI 및 Office 365에서 작업 영역을 관리](service-manage-app-workspace-in-power-bi-and-office-365.md)하는 방법을 참조하세요.

## <a name="licensing"></a>라이선싱

포함된 보고서를 보려면 사용자가 Power BI Pro 라이선스가 필요하거나, [Power BI Premium 용량(EM 또는 P SKU)](service-admin-premium-purchase.md)에 있는 작업 영역에 있어야 합니다.

## <a name="customize-your-embed-experience-using-url-settings"></a>URL 설정을 사용한 포함 환경 사용자 지정

포함 URL의 입력 설정을 사용하여 사용자 환경을 사용자 지정할 수 있습니다. 제공된 iFrame에서 URL의 **src** 설정을 업데이트할 수 있습니다.

| 속성  | 설명  |  |  |  |
|--------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---|---|---|
| pageName  | **pageName** 쿼리 문자열 매개 변수를 사용하여 어떤 보고서 페이지를 열지 설정할 수 있습니다. 아래 그림과 같이 Power BI 서비스에 있는 보고서를 볼 때 보고서 URL의 끝에서 이 값을 확인할 수 있습니다. |  |  |  |
| URL 필터  | Power BI UI로부터 받은 포함 URL의 [URL 필터](service-url-filters.md)를 사용하여 포함된 내용을 필터링할 수 있습니다. 이러한 방식으로 기본 HTML 및 JavaScript 환경만으로 로우 코드 통합을 빌드할 수 있습니다.  |  |  |  |

## <a name="set-which-page-opens-for-an-embedded-report"></a>포함된 보고서에 대해 열리는 페이지 설정 

Power BI 서비스에 있는 보고서를 볼 때 보고서 URL의 끝에서 **pageName** 값을 확인할 수 있습니다.

1. 웹 브라우저에서 Power BI 서비스의 보고서를 연 다음 주소 표시줄에서 URL을 복사합니다.

    ![보고서 섹션](media/service-embed-secure/secure-embed-report-section.png)

2. **pageName** 설정을 URL에 추가합니다.

    ![pageName 추가](media/service-embed-secure/secure-embed-append-page-name.png)

## <a name="filter-report-content-using-url-filters"></a>URL 필터를 사용하여 보고서 내용 필터링 

[URL 필터](service-url-filters.md)를 사용하여 다른 보고서 보기를 제공할 수 있습니다. 예를 들어 아래 URL은 보고서를 필터링하여 에너지 산업에 대한 데이터를 표시합니다.

**pageName** 및 [URL 필터](service-url-filters.md)의 조합은 강력할 수 있습니다. 기본 HTML 및 JavaScript를 사용하여 환경을 빌드할 수 있습니다.

예를 들어 HTML 페이지에 추가할 수 있는 단추는 다음과 같습니다.

```html
<button class="textLarge" onclick='show("ReportSection", "Energy");' style="display: inline-block;">Show Energy</button>
```

단추를 선택하면 iFrame을 업데이트된 URL로 업데이트하는 기능이 호출됩니다. 여기에는 에너지 산업 필터가 포함됩니다.

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

* 페이지를 매긴 보고서는 보안 포함 시나리오로 지원되며 URL 매개 변수를 사용하여 페이지를 매긴 보고서도 지원됩니다. [페이지를 매긴 보고서의 URL에서 보고서 매개 변수를 전달하는 방법](report-builder-url-pass-parameters.md)에 대해 자세히 알아보세요.

* Azure B2B(Business to Business)를 사용한 외부 게스트 사용자를 지원하지 않습니다.

* 보안 포함은 Power BI 서비스에 게시된 보고서에 대해 작동합니다.

* 사용자는 새 브라우저 창을 열 때마다 보고서를 보려면 로그인해야 합니다.

* 일부 브라우저의 경우, 특히 InPrivate 또는 시크릿 모드를 사용하는 경우 로그인 이후 페이지를 새로 고쳐야 합니다.

* 지원되지 않는 브라우저 버전을 사용하는 경우 문제가 발생할 수 있습니다. Power BI는 [다음 목록의 브라우저](power-bi-browsers.md)를 지원합니다.

* 클래식 SharePoint Server는 버전 11 이전의 Internet Explorer 버전이 필요하거나 호환성 보기 모드를 사용해야 하므로 지원되지 않습니다.

* Single Sign-On 환경을 위해 [SharePoint Online에 포함 옵션](service-embed-report-spo.md)을 사용하거나 [사용자 소유 데이터](developer/embed-sample-for-your-organization.md) 포함 방법을 사용하여 사용자 지정 통합을 빌드합니다. 

* **포함** 옵션에 제공되는 자동 인증 기능은 Power BI JavaScript API에서 작동하지 않습니다. Power BI JavaScript API의 경우 [사용자 소유 데이터](developer/embed-sample-for-your-organization.md) 포함 방법을 사용합니다. 

* 인증 토큰 수명은 AAD 설정에 따라 제어됩니다. 인증 토큰이 만료되면 브라우저를 새로 고쳐 업데이트된 인증 토큰을 가져와야 합니다. 기본 수명은 1시간이지만 조직에 따라 더 짧거나 더 길 수 있습니다.

## <a name="next-steps"></a>다음 단계

* [Power BI에서 작업을 공유하는 방법](service-how-to-collaborate-distribute-dashboards-reports.md)

* [URL에 쿼리 문자열 매개 변수를 사용하여 보고서 필터링](service-url-filters.md)

* [SharePoint Online에 보고서 웹 파트 포함](service-embed-report-spo.md)

* [Power BI에서 웹에 게시](service-publish-to-web.md)
