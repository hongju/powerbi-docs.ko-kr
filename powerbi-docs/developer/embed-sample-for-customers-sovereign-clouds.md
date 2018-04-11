---
title: 소버린 클라우드용 고객의 응용 프로그램에 Power BI 콘텐츠 포함
description: 고객의 Power BI API를 사용하여 웹앱에 대시보드, 타일 또는 보고서를 통합하거나 포함하는 방법을 알아봅니다.
services: powerbi
documentationcenter: ''
author: markingmyname
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: get-started-article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 03/28/2018
ms.author: maghan
ms.openlocfilehash: bef0748f1431a29c96d7aa23ab457683e247724a
ms.sourcegitcommit: e571de2afa3f34fac06a6aab0df0e8940cb00a0d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2018
---
# <a name="embed-a-power-bi-dashboard-tile-or-report-into-your-application-for-sovereign-clouds"></a>소버린 클라우드용 응용 프로그램에 Power BI 대시보드, 타일 또는 보고서 포함
고객에 대한 콘텐츠를 포함하는 경우 Power BI JavaScript API와 함께 Power BI .NET SDK를 사용하여 대시보드, 타일 또는 보고서를 웹앱에 통합하거나 포함하는 방법에 대해 알아봅니다. 일반적으로 ISV 시나리오입니다.

Power BI는 소버린(개인용) 클라우드도 지원합니다. 각 소버린 클라우드에는 고유한 소속이 있습니다. 다른 소버린 클라우드는 다음과 같습니다.

* 미국 GCC(정부 커뮤니티 클라우드)

* U. S. DoDCON(군용 계약업체)

* U. S. DoD(군대)

* 독일 클라우드용 Power BI

![포함된 대시보드](media/embed-sample-for-customers/powerbi-embed-dashboard.png)

이 연습을 시작하려면 **Power BI 계정**이 필요합니다. 계정이 설정되어 있지 않으면 정부 유형에 따라 [미국 정부 Power BI 계정](../service-govus-signup.md) 또는 [독일 클라우드용 Power BI 계정에 등록](https://powerbi.microsoft.com/en-us/power-bi-germany/?ru=https%3A%2F%2Fapp.powerbi.de%2F%3FnoSignUpCheck%3D1)할 수 있습니다.

> [!NOTE]
> 대신 조직의 대시보드를 포함하려고 하십니까? [조직의 앱에 대시보드 통합](integrate-dashboard.md)을 참조하세요.
>

대시보드를 웹앱에 통합하려면 **Power BI** API와 Azure Active Directory(AD) 인증 **액세스 토큰**을 사용하여 대시보드를 가져옵니다. 그런 다음 포함 토큰을 사용하여 대시보드를 로드합니다. **Power BI** API는 특정 **Power BI** 리소스에 대한 프로그래밍 방식 액세스를 제공합니다. 자세한 내용은 [Power BI REST API의 개요](https://msdn.microsoft.com/library/dn877544.aspx), [Power BI .NET SDK](https://github.com/Microsoft/PowerBI-CSharp) 및 [Power BI JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript)를 참조하세요.

## <a name="download-the-sample"></a>샘플 다운로드
이 아티클에서는 GitHub에서 [고객에 대한 콘텐츠 포함 샘플](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data/PowerBIEmbedded_AppOwnsData)에서 사용되는 코드를 보여줍니다. 이 연습을 따라 하기 위해 샘플을 다운로드할 수 있습니다.

* GCC(정부 커뮤니티 클라우드):
    1. GCCCloud.config 콘텐츠로 Cloud.config 파일을 덮어씁니다.
    2. Web.config 파일에서 Clientid(네이티브 앱 클라이언트 ID), groupid, 사용자(마스터 사용자) 및 암호를 업데이트합니다.
    3. Web.config 파일에서 다음과 같이 GCC 매개 변수를 추가합니다.

```xml
<add key="authorityUrl" value="https://login.windows.net/common/oauth2/authorize/" />

<add key="resourceUrl" value="https://analysis.usgovcloudapi.net/powerbi/api" />

<add key="apiUrl" value="https://api.powerbigov.us/" />

<add key="embedUrlBase" value="https://app.powerbigov.us" />
```

* DoDCON(군용 계약업체):
    1. TBCloud.config 콘텐츠로 Cloud.config 파일을 덮어씁니다.
    2. Web.config 파일에서 Clientid(네이티브 앱 클라이언트 ID), groupid, 사용자(마스터 사용자) 및 암호를 업데이트합니다.
    3. Web.config 파일에서 다음과 같이 DoDCON 매개 변수를 추가합니다.

```xml
<add key="authorityUrl" value="https://login.windows.net/common/oauth2/authorize/" />

<add key="resourceUrl" value="https://high.analysis.usgovcloudapi.net/powerbi/api" />

<add key="apiUrl" value="https://api.high.powerbigov.us/" />

<add key="embedUrlBase" value="https://app.high.powerbigov.us" />
```

* DoD(군대):
    1. PFCloud.config 콘텐츠로 Cloud.config 파일을 덮어씁니다.
    2. Web.config 파일에서 Clientid(네이티브 앱 클라이언트 ID), groupid, 사용자(마스터 사용자) 및 암호를 업데이트합니다.
    3. Web.config 파일에서 다음과 같이 DoDCON 매개 변수를 추가합니다.

```xml
<add key="authorityUrl" value="https://login.windows.net/common/oauth2/authorize/" />

<add key="resourceUrl" value="https://mil.analysis.usgovcloudapi.net/powerbi/api" />

<add key="apiUrl" value="https://api.mil.powerbigov.us/" />

<add key="embedUrlBase" value="https://app.mil.powerbigov.us" />
```

* 독일 클라우드용 Power BI 매개 변수
    1. Cloud.config 파일을 독일 클라우드용 Power BI 콘텐츠로 덮어씁니다.
    2. Web.config 파일에서 Clientid(네이티브 앱 클라이언트 ID), groupid, 사용자(마스터 사용자) 및 암호를 업데이트합니다.
    3. 독일 클라우드용 Power BI 매개 변수를 다음과 같이 web.config 파일에 추가합니다.

```xml
<add key="authorityUrl" value=https://login.microsoftonline.de/common/oauth2/authorize/" />

<add key="resourceUrl" value="https://analysis.cloudapi.de/powerbi/api" />

<add key="apiUrl" value="https://api.powerbi.de/" />

<add key="embedUrlBase" value="https://app.powerbi.de" />
```

## <a name="step-1---register-an-app-in-azure-ad"></a>1단계 - Azure AD에 앱 등록
REST API 호출을 실행하려면 Azure AD를 사용해 응용 프로그램을 등록해야 합니다. 자세한 내용은 [Power BI 콘텐츠를 포함하려면 Azure AD 앱 등록](register-app.md)을 참조하세요. 소버린 클라우드 소속이 서로 다르기 때문에 응용 프로그램을 등록하기 위한 개별 URL이 있습니다.

* GCC(정부 커뮤니티 클라우드) - https://app.powerbigov.us/apps 

* DoDCON(군용 계약업체) - https://app.high.powerbigov.us/apps 

* DoD(군대) - https://app.mil.powerbigov.us/apps

* 독일 클라우드용 Power BI - https://app.powerbi.de/apps

[고객에 대한 콘텐츠 포함 샘플](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data)을 다운로드했다면 Azure AD에서 샘플이 인증을 받을 수 있도록, 등록 후에 얻은 **클라이언트 ID**를 사용합니다. 샘플을 구성하려면, *web.config* 파일에서 **clientId**를 변경합니다.


## <a name="step-2---get-an-access-token-from-azure-ad"></a>2 단계-Azure AD로 액세스 토큰 가져오기
응용 프로그램 내에서 먼저 Azure AD에서 **액세스 토큰**을 가져와야 Power BI REST API로 호출할 수 있습니다. 자세한 내용은 [사용자를 인증하고 Power BI 앱에 대한 Azure AD 액세스 토큰 가져오기](get-azuread-access-token.md)를 참조하세요. 소버린 클라우드 소속이 서로 다르기 때문에 응용 프로그램에 대한 액세스 토큰을 얻기 위한 개별 URL이 있습니다.

* GCC(정부 커뮤니티 클라우드) - https://login.microsoftonline.com

* DoDCON(군용 계약업체) - http://login.microsoftonline.us

* DoD(군대) - https://login.microsoftonline.us

* 독일 클라우드용 Power BI - https://login.microsoftonline.de

**Controllers\HomeController.cs**의 각 콘텐츠 항목 작업 내에서 이 예제를 볼 수 있습니다.

## <a name="step-3---get-a-content-item"></a>3 단계-콘텐츠 항목 가져오기
Power BI 콘텐츠를 포함하려면 제대로 포함되었는지 확인하기 위해 몇 가지를 수행해야 합니다. 이러한 모든 단계를 REST API를 사용하여 직접 수행할 수 있지만, 여기에 나오는 샘플 응용 프로그램과 예제는 NET SDK를 사용하여 만들어집니다.

### <a name="create-the-power-bi-client-with-your-access-token"></a>액세스 토큰으로 Power BI 클라이언트 만들기
사용자 액세스 토큰을 사용해 사용자는 Power BI API와 상호 작용할 수 있는 Power BI 클라이언트 개체를 만들 수 있습니다. 이렇게 하려면 AccessToken을 *Microsoft.Rest.TokenCredentials* 개체로 래핑합니다.

```csharp
using Microsoft.IdentityModel.Clients.ActiveDirectory;
using Microsoft.Rest;
using Microsoft.PowerBI.Api.V2;

var tokenCredentials = new TokenCredentials(authenticationResult.AccessToken, "Bearer");

// Create a Power BI Client object. It will be used to call Power BI APIs.
using (var client = new PowerBIClient(new Uri(ApiUrl), tokenCredentials))
{
    // Your code to embed items.
}
```

### <a name="get-the-content-item-you-want-to-embed"></a>포함하려는 콘텐츠 항목 가져오기
Power BI 클라이언트 개체를 사용하여 포함하려는 항목에 참조를 검색할 수 있습니다. 대시보드, 타일 또는 보고서를 포함할 수 있습니다. 다음은 주어진 작업 영역에서 첫 번째 대시보드, 타일 또는 보고서를 검색하는 방법을 보여주는 예입니다.

이 방법의 샘플은 [앱 소유 데이터 샘플](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data)의 **Controllers\HomeController.cs**에서 찾을 수 있습니다.

**대시보드**

```csharp
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// You will need to provide the GroupID where the dashboard resides.
ODataResponseListDashboard dashboards = client.Dashboards.GetDashboardsInGroup(GroupId);

// Get the first report in the group.
Dashboard dashboard = dashboards.Value.FirstOrDefault();
```

**타일**

```csharp
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// To retrieve the tile, you first need to retrieve the dashboard.

// You will need to provide the GroupID where the dashboard resides.
ODataResponseListDashboard dashboards = client.Dashboards.GetDashboardsInGroup(GroupId);

// Get the first report in the group.
Dashboard dashboard = dashboards.Value.FirstOrDefault();

// Get a list of tiles from a specific dashboard
ODataResponseListTile tiles = client.Dashboards.GetTilesInGroup(GroupId, dashboard.Id);

// Get the first tile in the group.
Tile tile = tiles.Value.FirstOrDefault();
```

**보고서**

```csharp
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// You will need to provide the GroupID where the dashboard resides.
ODataResponseListReport reports = client.Reports.GetReportsInGroupAsync(GroupId);

// Get the first report in the group.
Report report = reports.Value.FirstOrDefault();
```

### <a name="create-the-embed-token"></a>포함 토큰을 만듭니다.
JavaScript API에서 사용할 수 있는 embed 토큰이 생성되어야 합니다. embed 토큰은 포함한 항목에 한정됩니다. 즉, Power BI 콘텐츠의 구성 요소를 포함하는 경우 이에 대한 새 embed 토큰을 만들어야 합니다. 어떤 **accessLevel**을 사용할지를 포함한 자세한 내용은 사용 하려면 [GenerateToken API](https://msdn.microsoft.com/library/mt784614.aspx)를 참조하세요.

> [!IMPORTANT]
> 포함 토큰은 개발 테스트 전용이므로 Power BI 마스터 계정에서 생성할 수 있는 포함 토큰의 수는 제한적입니다. 프로덕션 포함 시나리오를 위해 [용량을 구입해야](https://docs.microsoft.com/power-bi/developer/embedded-faq#technical) 합니다. 용량을 구입할 때 토큰 생성은 제한 없이 포함시킬 수 있습니다.

이 샘플은 [조직에 대한 콘텐츠 포함 샘플](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data)의 **Controllers\HomeController.cs** 내에서 찾을 수 있습니다.

이는 **EmbedConfig** 및 **TileEmbedConfig**에 대한 클래스가 생성되었음을 의미합니다. 이들에 대한 샘플은 **Models\EmbedConfig.cs** 및 **Models\TileEmbedConfig.cs** 내에서 찾아볼 수 있습니다.

**대시보드**

```csharp
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// Generate Embed Token.
var generateTokenRequestParameters = new GenerateTokenRequest(accessLevel: "view");
EmbedToken tokenResponse = client.Dashboards.GenerateTokenInGroup(GroupId, dashboard.Id, generateTokenRequestParameters);

// Generate Embed Configuration.
var embedConfig = new EmbedConfig()
{
    EmbedToken = tokenResponse,
    EmbedUrl = dashboard.EmbedUrl,
    Id = dashboard.Id
};
```

**타일**

```csharp
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// Generate Embed Token for a tile.
var generateTokenRequestParameters = new GenerateTokenRequest(accessLevel: "view");
EmbedToken tokenResponse = client.Tiles.GenerateTokenInGroup(GroupId, dashboard.Id, tile.Id, generateTokenRequestParameters);

// Generate Embed Configuration.
var embedConfig = new TileEmbedConfig()
{
    EmbedToken = tokenResponse,
    EmbedUrl = tile.EmbedUrl,
    Id = tile.Id,
    dashboardId = dashboard.Id
};
```

**보고서**

```csharp
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// Generate Embed Token.
var generateTokenRequestParameters = new GenerateTokenRequest(accessLevel: "view");
EmbedToken tokenResponse = client.Reports.GenerateTokenInGroup(GroupId, report.Id, generateTokenRequestParameters);

// Generate Embed Configuration.
var embedConfig = new EmbedConfig()
{
    EmbedToken = tokenResponse,
    EmbedUrl = report.EmbedUrl,
    Id = report.Id
};
```
## <a name="step-4---load-an-item-using-javascript"></a>4 단계-JavaScript를 사용하여 항목을 로드합니다.
JavaScript를 사용하여 웹 페이지의 div 요소로 대시보드를 로드합니다. 샘플은 EmbedConfig/TileEmbedConfig 모델을 대시보드, 타일 또는 보고서에 대한 보기와 함께 사용합니다. JavaScript API 사용에 관한 전체 샘플인 경우 [Microsoft Power BI Embedded 샘플](https://microsoft.github.io/PowerBI-JavaScript/demo)을 사용할 수 있습니다.

이 응용 프로그램 샘플은 [조직에 대한 콘텐츠 포함 샘플](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data) 내에서 사용할 수 있습니다.

**Views\Home\EmbedDashboard.cshtml**

```csharp
<script src="~/scripts/powerbi.js"></script>
<div id="dashboardContainer"></div>
<script>
    // Read embed application token from Model
    var accessToken = "@Model.EmbedToken.Token";

    // Read embed URL from Model
    var embedUrl = "@Html.Raw(Model.EmbedUrl)";

    // Read dashboard Id from Model
    var embedDashboardId = "@Model.Id";

    // Get models. models contains enums that can be used.
    var models = window['powerbi-client'].models;

    // Embed configuration used to describe the what and how to embed.
    // This object is used when calling powerbi.embed.
    // This also includes settings and options such as filters.
    // You can find more information at https://github.com/Microsoft/PowerBI-JavaScript/wiki/Embed-Configuration-Details.
    var config = {
        type: 'dashboard',
        tokenType: models.TokenType.Embed,
        accessToken: accessToken,
        embedUrl: embedUrl,
        id: embedDashboardId
    };

    // Get a reference to the embedded dashboard HTML element
    var dashboardContainer = $('#dashboardContainer')[0];

    // Embed the dashboard and display it within the div container.
    var dashboard = powerbi.embed(dashboardContainer, config);
</script>
```

**Views\Home\EmbedTile.cshtml**

```csharp
<script src="~/scripts/powerbi.js"></script>
<div id="tileContainer"></div>
<script>
    // Read embed application token from Model
    var accessToken = "@Model.EmbedToken.Token";

    // Read embed URL from Model
    var embedUrl = "@Html.Raw(Model.EmbedUrl)";

    // Read tile Id from Model
    var embedTileId = "@Model.Id";

    // Read dashboard Id from Model
    var embedDashboardeId = "@Model.dashboardId";

    // Get models. models contains enums that can be used.
    var models = window['powerbi-client'].models;

    // Embed configuration used to describe the what and how to embed.
    // This object is used when calling powerbi.embed.
    // This also includes settings and options such as filters.
    // You can find more information at https://github.com/Microsoft/PowerBI-JavaScript/wiki/Embed-Configuration-Details.
    var config = {
        type: 'tile',
        tokenType: models.TokenType.Embed,
        accessToken: accessToken,
        embedUrl: embedUrl,
        id: embedTileId,
        dashboardId: embedDashboardeId
    };

    // Get a reference to the embedded tile HTML element
    var tileContainer = $('#tileContainer')[0];

    // Embed the tile and display it within the div container.
    var tile = powerbi.embed(tileContainer, config);
</script>
```

**Views\Home\EmbedReport.cshtml**

```csharp
<script src="~/scripts/powerbi.js"></script>
<div id="reportContainer"></div>
<script>
    // Read embed application token from Model
    var accessToken = "@Model.EmbedToken.Token";

    // Read embed URL from Model
    var embedUrl = "@Html.Raw(Model.EmbedUrl)";

    // Read report Id from Model
    var embedReportId = "@Model.Id";

    // Get models. models contains enums that can be used.
    var models = window['powerbi-client'].models;

    // Embed configuration used to describe the what and how to embed.
    // This object is used when calling powerbi.embed.
    // This also includes settings and options such as filters.
    // You can find more information at https://github.com/Microsoft/PowerBI-JavaScript/wiki/Embed-Configuration-Details.
    var config = {
        type: 'report',
        tokenType: models.TokenType.Embed,
        accessToken: accessToken,
        embedUrl: embedUrl,
        id: embedReportId,
        permissions: models.Permissions.All,
        settings: {
            filterPaneEnabled: true,
            navContentPaneEnabled: true
        }
    };

    // Get a reference to the embedded report HTML element
    var reportContainer = $('#reportContainer')[0];

    // Embed the report and display it within the div container.
    var report = powerbi.embed(reportContainer, config);
</script>
```

## <a name="next-steps"></a>다음 단계

* 검토하기 위한 샘플 응용 프로그램은 GitHub에서 사용할 수 있습니다. 위의 예제는 이 샘플을 기반으로 하고 있습니다. 자세한 내용은 [조직에 대한 콘텐츠 포함 샘플](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data)을 참조하세요.
* JavaScript API에 대한 자세한 내용은 [Power BI JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript)를 참조하세요.
* 독일 클라우드용 Power BI에 대한 자세한 내용은 [독일 클라우드용 Power BI FAQ](https://docs.microsoft.com/en-us/power-bi/service-govde-faq)를 참조하세요.
* [Power BI 작업 영역 컬렉션 콘텐츠를 Power BI로 마이그레이션하는 방법](migrate-from-powerbi-embedded.md)

제한 사항 및 고려 사항
* 이제 GCC 계정은 P 및 EM 용량만을 지원합니다.

궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](http://community.powerbi.com/)
