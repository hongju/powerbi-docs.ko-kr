---
title: 조직의 앱에 대시보드 통합
description: Power BI API를 사용하여 웹앱에 대시보드를 통합하고 포함하는 방법을 알아봅니다.
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 02/13/2018
ms.author: maghan
ms.openlocfilehash: 979b76350b9867bbc684a70bd89a82f88993e625
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34290272"
---
# <a name="integrate-a-dashboard-into-an-app-for-your-organization"></a>조직의 앱에 대시보드 통합
조직에 대한 콘텐츠를 포함할 때 Power BI JavaScript API와 함께 REST API 호출을 사용하여 대시보드를 웹앱에 통합하거나 포함하는 방법에 대해 알아봅니다.

![포함된 대시보드](media/integrate-dashboard/powerbi-embed-dashboard.png)

이 연습을 시작하려면 **Power BI** 계정이 필요합니다. 계정이 없는 경우 [무료 Power BI 계정에 등록](../service-self-service-signup-for-power-bi.md)하거나 테스트를 위해 자신만의 [Azure Active Directory 테넌트](create-an-azure-active-directory-tenant.md)를 만들 수 있습니다.

> [!NOTE]
> 대신 embedtoken을 사용하여 고객의 대시보드를 포함하려고 하십니까? [고객의 응용 프로그램에 대시보드, 타일 또는 보고서 통합](embed-sample-for-customers.md)을 참조하세요.
> 
> 

대시보드를 웹앱에 통합하려면 **Power BI** REST API 또는 Power BI C# SDK 및 Azure AD(Active Directory) 권한 부여 **액세스 토큰**을 사용하여 대시보드를 가져옵니다. 그런 다음 대시보드를 동일한 액세스 토큰을 사용하여 대시보드를 로드합니다. **Power BI** API는 특정 **Power BI** 리소스에 대한 프로그래밍 방식 액세스를 제공합니다. 자세한 내용은 [Power BI REST API의 개요](https://msdn.microsoft.com/library/dn877544.aspx) 및 [Power BI JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript)를 참조하세요.

## <a name="download-the-sample"></a>샘플 다운로드
이 문서에서는 GitHub의 [integrate-dashboard-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-dashboard-web-app)에 사용된 코드를 보여줍니다. 이 연습을 따라 하기 위해 샘플을 다운로드할 수 있습니다.

## <a name="step-1---register-an-app-in-azure-ad"></a>1단계 - Azure AD에 앱 등록
REST API 호출을 실행하려면 Azure AD를 사용해 응용 프로그램을 등록해야 합니다. 자세한 내용은 [포함된 Power BI 콘텐츠에 Azure AD 앱 등록](register-app.md)을 참조하세요.

[대시보드 통합 샘플](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-dashboard-web-app)을 다운로드했으면 Azure AD에서 샘플을 인증할 수 있도록 등록 후에 얻은 **클라이언트 ID**와 **클라이언트 비밀**을 사용합니다. 샘플을 구성하려면, **클라이언트 ID**와 **클라이언트 비밀**을 *cloud.config*에서 변경합니다.

![](media/integrate-dashboard/powerbi-embed-dashboard-register-app4.png)

## <a name="step-2---get-an-access-token-from-azure-ad"></a>2 단계-Azure AD로 액세스 토큰 가져오기
응용 프로그램 내에서 먼저 Azure AD에서 **액세스 토큰**을 가져와야 Power BI REST API로 호출할 수 있습니다. 자세한 내용은 [사용자 인증 및 Power BI 앱에 대한 Azure AD 액세스 토큰 가져오기](get-azuread-access-token.md)를 참조하세요.

## <a name="step-3---get-a-dashboard"></a>3단계 - 대시보드 가져오기
**Power BI** 대시보드를 가져오려면, **Power BI** 대시보드 목록을 가져오는 [대시보드 가져오기](https://msdn.microsoft.com/library/mt465739.aspx) 작업을 사용합니다. 대시보드 목록에서, 대시보드 ID를 얻을 수 있습니다.

![](media/integrate-dashboard/powerbi-embed-dashboard-get-dashboards.png)

### <a name="get-dashboards-using-an-access-token"></a>액세스 토큰을 사용하여 대시보드 가져오기
[2단계](#step-2-get-an-access-token-from-azure-ad)에서 검색한 **액세스 토큰**을 사용하면 [대시보드 가져오기](https://msdn.microsoft.com/library/mt465739.aspx) 작업을 호출할 수 있습니다. [대시보드 가져오기](https://msdn.microsoft.com/library/mt465739.aspx) 작업은 대시보드 목록을 반환합니다. 대시보드 목록에서 하나의 대시보드를 가져올 수 있습니다. 다음은 대시보드를 가져오는 C# 메서드입니다. 

REST API를 호출하려면 *권한 부여* 헤더를 *Bearer {access token}* 형식으로 포함해야 합니다.

#### <a name="get-dashboards-with-the-rest-api"></a>REST API로 대시보드 가져오기
**Default.aspx.cs**

```
protected void getDashboardsButton_Click(object sender, EventArgs e)
{
    string responseContent = string.Empty;

    //Configure dashboards request
    System.Net.WebRequest request = System.Net.WebRequest.Create(String.Format("{0}dashboards", baseUri)) as System.Net.HttpWebRequest;
    request.Method = "GET";
    request.ContentLength = 0;
    request.Headers.Add("Authorization", String.Format("Bearer {0}", authResult.AccessToken));

    //Get dashboards response from request.GetResponse()
    using (var response = request.GetResponse() as System.Net.HttpWebResponse)
    {
        //Get reader from response stream
        using (var reader = new System.IO.StreamReader(response.GetResponseStream()))
        {
            responseContent = reader.ReadToEnd();

            //Deserialize JSON string
            PBIDashboards PBIDashboards = JsonConvert.DeserializeObject<PBIDashboards>(responseContent);

            if (PBIDashboards != null)
            {
                var gridViewDashboards = PBIDashboards.value.Select(dashboard => new {
                    Id = dashboard.id,
                    DisplayName = dashboard.displayName,
                    EmbedUrl = dashboard.embedUrl
                });

                this.GridView1.DataSource = gridViewDashboards;
                this.GridView1.DataBind();
            }
        }
    }
}

//Power BI Dashboards used to deserialize the Get Dashboards response.
public class PBIDashboards
{
    public PBIDashboard[] value { get; set; }
}
public class PBIDashboard
{
    public string id { get; set; }
    public string displayName { get; set; }
    public string embedUrl { get; set; }
    public bool isReadOnly { get; set; }
}
```

#### <a name="get-dashboards-using-the-net-sdk"></a>.NET SDK를 사용하여 대시보드 가져오기
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
    ODataResponseListDashboard dashboards = client.Dashboards.GetDashboards();

    // Get a list of dashboards from a group (app workspace)
    ODataResponseListDashboard dashboards = client.Dashboards.GetDashboardsInGroup(groupId);

    Dashboard dashboard = dashboards.Value.FirstOrDefault();

    var embedUrl = dashboard.EmbedUrl
}
```

## <a name="step-4---load-a-dashboard-using-javascript"></a>4단계 - JavaScript를 사용하여 대시보드 로드
JavaScript를 사용하여 웹 페이지의 div 요소로 대시보드를 로드합니다.

**Default.aspx**

```
<!-- Embed Dashboard-->
<div> 
    <asp:Panel ID="PanelEmbed" runat="server" Visible="true">
        <div>
            <div><b class="step">Step 3</b>: Embed a dashboard</div>

            <div>Enter an embed url for a dashboard from Step 2 (starts with https://):</div>
            <input type="text" id="tb_EmbedURL" style="width: 1024px;" />
            <br />
            <input type="button" id="bEmbedDashboardAction" value="Embed Dashboard" />
        </div>

        <div id="dashboardContainer"></div>
    </asp:Panel>
</div>
```

**Site.master**

```
window.onload = function () {
    // client side click to embed a selected dashboard.
    var el = document.getElementById("bEmbedDashboardAction");
    if (el.addEventListener) {
        el.addEventListener("click", updateEmbedDashboard, false);
    } else {
        el.attachEvent('onclick', updateEmbedDashboard);
    }

    // handle server side post backs, optimize for reload scenarios
    // show embedded dashboard if all fields were filled in.
    var accessTokenElement = document.getElementById('MainContent_accessTokenTextbox');
    if (accessTokenElement !== null) {
        var accessToken = accessTokenElement.value;
        if (accessToken !== "")
            updateEmbedDashboard();
    }
};

// update embed dashboard
function updateEmbedDashboard() {

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
        type: 'dashboard',
        accessToken: accessToken,
        embedUrl: embedUrl
    };

    // Grab the reference to the div HTML element that will host the dashboard.
    var dashboardContainer = document.getElementById('dashboardContainer');

    // Embed the dashboard and display it within the div container.
    var dashboard = powerbi.embed(dashboardContainer, config);

    // dashboard.on will add an event handler which prints to Log window.
    dashboard.on("tileClicked", function (event) {
        var logView = document.getElementById('logView');
        logView.innerHTML = logView.innerHTML + "Tile Clicked<br/>";
        logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
        logView.innerHTML = logView.innerHTML + "---------<br/>";
    });

    // dashboard.on will add an event handler which prints to Log window.
    dashboard.on("error", function (event) {
        var logView = document.getElementById('logView');
        logView.innerHTML = logView.innerHTML + "Error<br/>";
        logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
        logView.innerHTML = logView.innerHTML + "---------<br/>";
    });
}
```

[대시보드 통합 샘플](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-dashboard-web-app)을 다운로드하여 실행하면, 샘플이 아래와 같이 표시됩니다.

![](media/integrate-dashboard/powerbi-embed-dashboard.png)

## <a name="tile-clicked-events"></a>이벤트 클릭한 타일
위의 예제에서 대시보드의 타일을 클릭할 때 이벤트를 처리할 수 있음을 알 수 있습니다. 이벤트에 대한 자세한 내용은 [JavaScript API 내에서 이벤트 처리](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Handling-Events)를 참조하세요.

```
// dashboard.on will add an event handler which prints to Log window.
dashboard.on("tileClicked", function (event) {
    var logView = document.getElementById('logView');
    logView.innerHTML = logView.innerHTML + "Tile Clicked<br/>";
    logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
    logView.innerHTML = logView.innerHTML + "---------<br/>";
});

// dashboard.on will add an event handler which prints to Log window.
dashboard.on("error", function (event) {
    var logView = document.getElementById('logView');
    logView.innerHTML = logView.innerHTML + "Error<br/>";
    logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
    logView.innerHTML = logView.innerHTML + "---------<br/>";
});
```

[대시보드 샘플 통합](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/PowerBI.com%20Integrate/integrate-dashboard-web-app)을 다운로드하고 실행한 경우 타일을 클릭하면 대시보드 아래의 텍스트가 출력됩니다. 텍스트는 다음과 유사하게 나타납니다. 이렇게 하면 타일이 클릭되었음을 기록할 수 있고 사용자를 적절한 위치로 이동합니다.

```
Tile Clicked
{ "event": "TileClick", "reportEmbedUrl": "", "navigationUrl": "https://app.powerbi.com/dashboards/fcff76f9-15ff-4a8e-8242-275ac9c25b90/qna?q=count%20of%20new%20hires%20from%20July%202014%20to%20December%202014", "tileId": "0e99b45c-9b53-4920-b239-cee7d37d2369" }
---------
Tile Clicked
{ "event": "TileClick", "reportEmbedUrl": "https://app.powerbi.com/reportEmbed?reportId=ab199308-80b1-4626-9823-43a84623bd9c", "navigationUrl": "https://app.powerbi.com/reports/ab199308-80b1-4626-9823-43a84623bd9c/ReportSection1", "tileId": "ffc30447-674a-4511-944f-79e182d719de", "pageName": "ReportSection1" }
---------
```

## <a name="working-with-groups-app-workspaces"></a>그룹(앱 작업 영역) 작업
그룹(앱 작업 영역)에서 대시보드를 포함하려면 다음 REST API 호출을 사용하여 그룹 내에서 사용 가능한 모든 대시보드 목록을 가져올 수 있습니다. 이 REST API 호출에 대한 자세한 정보를 확인하려면 [대시보드 가져오기](https://msdn.microsoft.com/library/mt465739.aspx)를 참조하세요. 결과를 반환하라는 요청에 대한 권한이 그룹에 있어야 합니다.

```
https://api.powerbi.com/v1.0/myorg/groups/{groupId}/dashboards
```

위의 API에는 사용할 수 있는 대시보드 목록을 반환합니다. 각 대시보드에 그룹을 포함하도록 지원하는 이미 생성된 EmbedUrl 속성이 있습니다.

```
https://app.powerbi.com/dashboardEmbed?dashboardId={dashboardId}&groupId={groupId}
```

## <a name="limitations"></a>제한 사항
* 포함된 대시보드에 액세스하는 최종 사용자는 Power BI 계정을 가지고 있고 대시보드에 액세스할 수 있어야 합니다. 대시보드를 소유하거나 사용자와 대시보드를 공유했습니다.
* 현재 포함된 대시보드에 Q&A가 지원되지 않습니다.
* 보안 그룹과 대시보드를 공유하는 경우 일시적인 제한으로 사용자는 대시보드가 포함된 것으로 보이기 전에 PowerBI.com에서 대시보드에 처음 액세스해야 합니다.

## <a name="next-steps"></a>다음 단계
검토하기 위한 샘플 응용 프로그램은 GitHub에서 사용할 수 있습니다. 위의 예제는 이 샘플을 기반으로 하고 있습니다. 자세한 내용은 [integrate-dashboard-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-dashboard-web-app)을 참조하세요.

JavaScript API에 사용할 수 있는 자세한 정보는 [Power BI JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript)를 참조하세요.

궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](http://community.powerbi.com/)

