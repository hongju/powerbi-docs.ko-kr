---
title: "조직의 앱에 Power BI 타일 통합"
description: "타일을 앱에 통합하는 연습, 샘플 코드"
services: powerbi
documentationcenter: 
author: markingmyname
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: get-started-article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 02/13/2018
ms.author: maghan
ms.openlocfilehash: c4c1b9223554491968a541c9d6b698a9655eded5
ms.sourcegitcommit: 2ceea44d3606c15b57142c37649c9d481ec4becc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2018
---
# <a name="integrate-a-tile-into-an-app-user-owns-data"></a>앱에 타일 통합(사용자 소유 데이터)
조직에 대한 콘텐츠를 포함할 때 Power BI JavaScript API와 함께 REST API 호출을 사용하여 타일을 웹앱에 통합하거나 포함하는 방법에 대해 알아봅니다.

![웹 응용 프로그램에 포함된 타일](media/integrate-tile/powerbi-embedded-tile.png)

이 연습을 시작하려면 **Power BI** 계정이 필요합니다. 계정이 없는 경우 [무료 Power BI 계정에 등록](../service-self-service-signup-for-power-bi.md)하거나 테스트를 위해 자신만의 [Azure Active Directory 테넌트](create-an-azure-active-directory-tenant.md)를 만들 수 있습니다.

> [!NOTE]
> 대신 embedtoken을 사용하여 고객의 타일을 포함하려고 하십니까? [고객의 응용 프로그램에 대시보드, 타일 또는 보고서 통합](embed-sample-for-customers.md)을 참조하세요.
> 
> 

타일을 웹앱에 통합하려면, **Power BI** REST API, 또는 Power BI C# SDK와, Azure Active Directory(AD) 인증 **액세스 토큰**을 사용하여 타일을 가져옵니다. 그런 다음, 동일한 액세스 토큰을 사용하여 타일을 로드합니다. **Power BI** API는 특정 **Power BI** 리소스에 대한 프로그래밍 방식 액세스를 제공합니다. 자세한 내용은 [Power BI REST API의 개요](https://msdn.microsoft.com/library/dn877544.aspx) 및 [Power BI JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript)를 참조하세요.

## <a name="download-the-sample"></a>샘플 다운로드
이 문서에서는 GitHub의 [integrate-tile-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-tile-web-app)에 사용된 코드를 보여줍니다. 이 연습을 따라 하기 위해 샘플을 다운로드할 수 있습니다.

## <a name="step-1---register-an-app-in-azure-ad"></a>1단계 - Azure AD에 앱 등록
REST API 호출을 실행하려면 Azure AD를 사용해 응용 프로그램을 등록해야 합니다. 자세한 내용은 [Power BI 콘텐츠를 포함하려면 Azure AD 앱 등록](register-app.md)을 참조하세요.

[integrate-tile-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-tile-web-app)을 다운로드했다면 등록 후에 가져온 **클라이언트 ID**와 **클라이언트 암호**를 사용하여 Azure AD에서 샘플을 인증합니다. 샘플을 구성하려면, **클라이언트 ID**와 **클라이언트 비밀**을 *cloud.config*에서 변경합니다.

![](media/integrate-tile/powerbi-embed-dashboard-register-app4.png)

## <a name="step-2---get-an-access-token-from-azure-ad"></a>2 단계-Azure AD로 액세스 토큰 가져오기
응용 프로그램 내에서 먼저 Azure AD에서 **액세스 토큰**을 가져와야 Power BI REST API로 호출할 수 있습니다. 자세한 내용은 [사용자를 인증하고 Power BI 앱에 대한 Azure AD 액세스 토큰 가져오기](get-azuread-access-token.md)를 참조하세요.

## <a name="step-3---get-a-tile"></a>3단계: 타일 가져오기
**Power BI** 타일을 가져오려면, 주어진 대시보드에서 **Power BI** 타일 목록을 가져오는 [타일 가져오기](https://msdn.microsoft.com/library/mt465741.aspx) 작업을 사용합니다. 타일 목록에서 타일 id와 포함된 URL을 가져올 수 있습니다.

대시보드 ID가 먼저 검색되어야 타일을 가져올 수 있습니다. 대시보드를 검색하는 방법에 대한 자세한 내용은 [앱에 대시보드 통합(사용자 소유 데이터)](integrate-dashboard.md)을 참조하세요.

### <a name="get-tiles-using-an-access-token"></a>액세스 토큰을 사용하여 타일 가져오기
[2단계](#step-2-get-an-access-token-from-azure-ad)에서 검색한 **액세스 토큰**을 사용하면 [타일 가져오기](https://msdn.microsoft.com/library/mt465741.aspx) 작업을 호출할 수 있습니다. [타일 가져오기](https://msdn.microsoft.com/library/mt465741.aspx) 작업은 타일 목록을 반환합니다. 타일의 목록에서 단일 타일을 가져올 수 있습니다. 다음은 타일을 가져오는 전체 C# 메서드입니다. 

REST API를 호출하려면 *권한 부여* 헤더를 *Bearer {access token}* 형식으로 포함해야 합니다.

#### <a name="get-tiles-with-the-rest-api"></a>REST API로 타일 가져오기
**Default.aspx.cs**

```
using Newtonsoft.Json;

//Get a tile from a dashboard. In this sample, you get the first tile.
protected void GetTile(string dashboardId, int index)
{
    //Configure tiles request
    System.Net.WebRequest request = System.Net.WebRequest.Create(
        String.Format("{0}Dashboards/{1}/Tiles",
        baseUri,
        dashboardId)) as System.Net.HttpWebRequest;

    request.Method = "GET";
    request.ContentLength = 0;
    request.Headers.Add("Authorization", String.Format("Bearer {0}", accessToken.Value));

    //Get tiles response from request.GetResponse()
    using (var response = request.GetResponse() as System.Net.HttpWebResponse)
    {
        //Get reader from response stream
        using (var reader = new System.IO.StreamReader(response.GetResponseStream()))
        {
            //Deserialize JSON string
            PBITiles tiles = JsonConvert.DeserializeObject<PBITiles>(reader.ReadToEnd());

            //Sample assumes at least one Dashboard with one Tile.
            //You could write an app that lists all tiles in a dashboard
            if (tiles.value.Length > 0)
                tileEmbedUrl.Text = tiles.value[index].embedUrl;
        }
    }
}

//Power BI Tiles used to deserialize the Get Tiles response.
public class PBITiles
{
    public PBITile[] value { get; set; }
}
public class PBITile
{
    public string id { get; set; }
    public string title { get; set; }
    public string embedUrl { get; set; }
}
```

#### <a name="get-tiles-using-the-net-sdk"></a>.NET SDK를 사용하여 타일 가져오기
.NET SDK를 사용하여 REST API를 직접 호출하는 대신 대시보드 목록을 검색할 수 있습니다.

```
using Microsoft.IdentityModel.Clients.ActiveDirectory;
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

var tokenCredentials = new TokenCredentials(<ACCESS TOKEN>, "Bearer");

// Create a Power BI Client object. It will be used to call Power BI APIs.
using (var client = new PowerBIClient(new Uri(ApiUrl), tokenCredentials))
{
    // Get a list of dashboards your "My Workspace"
    ODataResponseListDashboard tiles = client.Dashboards.GetDashboards();

    // Get a list of dashboards from a group (app workspace)
    ODataResponseListDashboard dashboards = client.Dashboards.GetDashboardsInGroup(groupId);

    Dashboard dashboard = dashboards.Value.FirstOrDefault();

    // Get the first tile from the above dashbaord
    ODataResponseListTile tiles = client.Dashboards.GetTiles(dashboard.Id);

    Tile tile = tiles.Value.FirstOrDefault();
}
```

## <a name="step-4---load-a-tile-using-javascript"></a>4단계 - JavaScript를 사용하여 타일 로드
JavaScript를 사용하여 웹 페이지의 div 요소로 타일을 로드합니다.

**Default.aspx**

```
<!-- Embed Tile-->
<div> 
    <asp:Panel ID="PanelEmbed" runat="server" Visible="true">
        <div>
            <div><b class="step">Step 3</b>: Embed a tile</div>

            <div>Enter an embed url for a tile from Step 2 (starts with https://):</div>
            <input type="text" id="tb_EmbedURL" style="width: 1024px;" />
            <br />
            <input type="button" id="bEmbedTileAction" value="Embed Tile" />
        </div>

        <div id="tileContainer"></div>
    </asp:Panel>
</div>
```

**Site.master**

```
window.onload = function () {
    // client side click to embed a selected tile.
    var el = document.getElementById("bEmbedTileAction");
    if (el.addEventListener) {
        el.addEventListener("click", updateEmbedTile, false);
    } else {
        el.attachEvent('onclick', updateEmbedTile);
    }

    // handle server side post backs, optimize for reload scenarios
    // show embedded tile if all fields were filled in.
    var accessTokenElement = document.getElementById('MainContent_accessTokenTextbox');
    if (accessTokenElement !== null) {
        var accessToken = accessTokenElement.value;
        if (accessToken !== "")
            updateEmbedTile();
    }
};

// update embed tile
function updateEmbedTile() {

    // check if the embed url was selected
    var embedUrl = document.getElementById('tb_EmbedURL').value;
    if (embedUrl === "")
        return;

    // get the access token.
    accessToken = document.getElementById('MainContent_accessTokenTextbox').value;

    // Embed configuration used to describe the what and how to embed.
    // This object is used when calling powerbi.embed.
    // You can find more information at https://github.com/Microsoft/PowerBI-JavaScript/wiki/Embed-Configuration-Details.
    var config = {
        type: 'tile',
        accessToken: accessToken,
        embedUrl: embedUrl
    };

    // Grab the reference to the div HTML element that will host the tile.
    var tileContainer = document.getElementById('tileContainer');

    // Embed the tile and display it within the div container.
    var tile = powerbi.embed(tileContainer, config);

    // tile.on will add an event handler which prints to Log window.
    tile.on("error", function (event) {
        var logView = document.getElementById('logView');
        logView.innerHTML = logView.innerHTML + "Error<br/>";
        logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
        logView.innerHTML = logView.innerHTML + "---------<br/>";
    });
}
```

[integrate-tile-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-tile-web-app)을 다운로드하여 실행하면 샘플이 아래와 같이 표시됩니다.

![웹 응용 프로그램에 포함된 타일](media/integrate-tile/powerbi-embedded-tile.png)

## <a name="working-with-groups-app-workspaces"></a>그룹(앱 작업 영역) 작업
그룹(앱 작업 영역)에서 타일을 포함하려면 다음 REST API 호출을 사용하여 그룹의 대시보드 내에서 사용 가능한 모든 타일 목록을 가져올 수 있습니다. 이 REST API 호출에 대한 자세한 정보를 확인하려면 [타일 가져오기](https://msdn.microsoft.com/library/mt465741.aspx)를 참조하세요. 결과를 반환하라는 요청에 대한 권한이 그룹에 있어야 합니다.

```
https://api.powerbi.com/v1.0/myorg/groups/{groupId}/dashboards/{dashboard_id}/tiles
```

위의 API에는 사용할 수 있는 타일 목록을 반환합니다. 각 타일에 그룹을 포함하도록 지원하는 이미 생성된 EmbedUrl 속성이 있습니다.

```
https://app.powerbi.com/embed?dashboardId={dashboard_id}&tileId={tile_id}&groupId={group_id}
```

## <a name="next-steps"></a>다음 단계
PowerBI-JavaScript Wiki의 [타일 포함](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Tile-Embed)

[Power BI JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript).

GitHub의 [integrate-tile-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-tile-web-app) 샘플.

궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](http://community.powerbi.com/)

