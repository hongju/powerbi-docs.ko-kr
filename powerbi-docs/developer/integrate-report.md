---
title: "조직의 앱에 Power BI 보고서 통합"
description: "Power BI API를 사용하여 웹앱에 보고서를 통합하고 포함하는 방법을 알아봅니다."
services: powerbi
documentationcenter: 
author: guyinacube
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
ms.date: 10/05/2017
ms.author: asaxton
ms.openlocfilehash: 4dd18fba5b5e3da0f8973a77166551086cc3f3cf
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2017
---
# <a name="integrate-a-report-into-an-app-for-your-organization"></a>조직의 앱에 보고서 통합
조직에 대한 콘텐츠를 포함할 때 Power BI JavaScript API와 함께 REST API 호출을 사용하여 보고서를 웹앱에 통합하거나 포함하는 방법에 대해 알아봅니다.

![포함된 보고서 샘플](media/integrate-report/powerbi-embedded-report.png)

이 연습을 시작하려면 **Power BI** 계정이 필요합니다. 계정이 없는 경우 [무료 Power BI 계정에 등록](../service-self-service-signup-for-power-bi.md)하거나 테스트를 위해 자신만의 [Azure Active Directory 테넌트](create-an-azure-active-directory-tenant.md)를 만들 수 있습니다.

> [!NOTE]
> 대신 embedtoken을 사용하여 고객의 보고서를 포함하려고 하십니까? [고객의 응용 프로그램에 대시보드, 타일 또는 보고서 통합](embed-sample-for-customers.md)을 참조하세요.
> 
> 

보고서를 웹앱에 통합하려면 **Power BI** REST API 또는 Power BI C# SDK 및 Azure Active Directory (AD) 권한 부여 **액세스 토큰**을 사용하여 보고서를 가져옵니다. 그런 다음, 동일한 액세스 토큰을 사용하여 보고서를 로드합니다. **Power BI** API는 특정 **Power BI** 리소스에 대한 프로그래밍 방식 액세스를 제공합니다. 자세한 내용은 [Power BI REST API의 개요](https://msdn.microsoft.com/library/dn877544.aspx) 및 [Power BI JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript)를 참조하세요.

## <a name="download-the-sample"></a>샘플 다운로드
이 문서에서는 GitHub의 [integrate-report-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-report-web-app)에 사용된 코드를 보여줍니다. 이 연습을 따라 하기 위해 샘플을 다운로드할 수 있습니다.

## <a name="step-1---register-an-app-in-azure-ad"></a>1단계 - Azure AD에 앱 등록
REST API 호출을 실행하려면 Azure AD를 사용해 응용 프로그램을 등록해야 합니다. 자세한 내용은 [Power BI 콘텐츠를 포함하려면 Azure AD 앱 등록](register-app.md)을 참조하세요.

[integrate-report-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-report-web-app)을 다운로드했다면 등록 후에 가져온 **클라이언트 ID**와 **클라이언트 암호**를 사용하여 Azure AD에서 샘플을 인증합니다. 샘플을 구성하려면, **클라이언트 ID**와 **클라이언트 비밀**을 *cloud.config*에서 변경합니다.

![](media/integrate-report/powerbi-embed-dashboard-register-app4.png)

## <a name="step-2---get-an-access-token-from-azure-ad"></a>2 단계-Azure AD로 액세스 토큰 가져오기
응용 프로그램 내에서 먼저 Azure AD에서 **액세스 토큰**을 가져와야 Power BI REST API로 호출할 수 있습니다. 자세한 내용은 [사용자를 인증하고 Power BI 앱에 대한 Azure AD 액세스 토큰 가져오기](get-azuread-access-token.md)를 참조하세요.

## <a name="step-3---get-a-report"></a>3단계: 보고서 가져오기
**Power BI** 보고서를 가져오려면, **Power BI** 보고서 목록을 가져오는 [보고서 가져오기](https://msdn.microsoft.com/library/mt634543.aspx) 작업을 사용합니다. 보고서 목록에서 보고서 id를 가져올 수 있습니다.

### <a name="get-reports-using-an-access-token"></a>액세스 토큰을 사용하여 보고서 가져오기
[2단계](#step-2-get-an-access-token-from-azure-ad)에서 검색한 **액세스 토큰**을 사용하면 [보고서 가져오기](https://msdn.microsoft.com/library/mt634543.aspx) 작업을 호출할 수 있습니다. [보고서 가져오기](https://msdn.microsoft.com/library/mt634543.aspx) 작업은 보고서 목록을 반환합니다. 보고서 목록에서 단일 보고서를 가져올 수 있습니다. 다음은 보고서를 가져오는 전체 C# 메서드입니다. Power BI REST API를 사용하는 방법에 대한 예제는 [APIARY의 Power BI REST API](http://docs.powerbi.apiary.io/)를 참조합니다.

REST API를 호출하려면 *권한 부여* 헤더를 *Bearer {access token}* 형식으로 포함해야 합니다.

#### <a name="get-reports-with-the-rest-api"></a>REST API를 사용 하 여 보고서 가져오기
**Default.aspx.cs**

```
using Newtonsoft.Json;

//Get a Report. In this sample, you get the first Report.
protected void GetReport(int index)
{
    //Configure Reports request
    System.Net.WebRequest request = System.Net.WebRequest.Create(
        String.Format("{0}/Reports",
        baseUri)) as System.Net.HttpWebRequest;

    request.Method = "GET";
    request.ContentLength = 0;
    request.Headers.Add("Authorization", String.Format("Bearer {0}", accessToken.Value));

    //Get Reports response from request.GetResponse()
    using (var response = request.GetResponse() as System.Net.HttpWebResponse)
    {
        //Get reader from response stream
        using (var reader = new System.IO.StreamReader(response.GetResponseStream()))
        {
            //Deserialize JSON string
            PBIReports Reports = JsonConvert.DeserializeObject<PBIReports>(reader.ReadToEnd());

            //Sample assumes at least one Report.
            //You could write an app that lists all Reports
            if (Reports.value.Length > 0)
            {
                var report = Reports.value[index];

                txtEmbedUrl.Text = report.embedUrl;
                txtReportId.Text = report.id;
                txtReportName.Text = report.name;
            }
        }
    }
}

//Power BI Reports used to deserialize the Get Reports response.
public class PBIReports
{
    public PBIReport[] value { get; set; }
}
public class PBIReport
{
    public string id { get; set; }
    public string name { get; set; }
    public string webUrl { get; set; }
    public string embedUrl { get; set; }
}
```

#### <a name="get-reports-using-the-net-sdk"></a>.NET SDK를 사용하여 보고서 가져오기
.NET SDK를 사용하여 REST API를 직접 호출하는 대신 보고서 목록을 검색할 수 있습니다.

```
using Microsoft.IdentityModel.Clients.ActiveDirectory;
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

var tokenCredentials = new TokenCredentials(<ACCESS TOKEN>, "Bearer");

// Create a Power BI Client object. It will be used to call Power BI APIs.
using (var client = new PowerBIClient(new Uri(ApiUrl), tokenCredentials))
{
    // Get the first report all reports in that workspace
    ODataResponseListReport reports = client.Reports.GetReports();

    Report report = reports.Value.FirstOrDefault();

    var embedUrl = report.EmbedUrl;
}
```

## <a name="step-4---load-a-report-using-javascript"></a>4단계 - JavaScript를 사용하여 보고서 로드
JavaScript를 사용하여 웹 페이지의 div 요소로 보고서를 로드합니다.

**Default.aspx**

```
<!-- Embed Report-->
<div> 
    <asp:Panel ID="PanelEmbed" runat="server" Visible="true">
        <div>
            <div><b class="step">Step 3</b>: Embed a report</div>

            <div>Enter an embed url for a report from Step 2 (starts with https://):</div>
            <input type="text" id="tb_EmbedURL" style="width: 1024px;" />
            <br />
            <input type="button" id="bEmbedReportAction" value="Embed Report" />
        </div>

        <div id="reportContainer"></div>
    </asp:Panel>
</div>
```

**Site.master**

```
window.onload = function () {
    // client side click to embed a selected report.
    var el = document.getElementById("bEmbedReportAction");
    if (el.addEventListener) {
        el.addEventListener("click", updateEmbedReporte, false);
    } else {
        el.attachEvent('onclick', updateEmbedReport);
    }

    // handle server side post backs, optimize for reload scenarios
    // show embedded report if all fields were filled in.
    var accessTokenElement = document.getElementById('MainContent_accessTokenTextbox');
    if (accessTokenElement !== null) {
        var accessToken = accessTokenElement.value;
        if (accessToken !== "")
            updateEmbedReport();
    }
};

// update embed report
function updateEmbedReport() {

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
        type: 'report',
        accessToken: accessToken,
        embedUrl: embedUrl
    };

    // Grab the reference to the div HTML element that will host the report.
    var reportContainer = document.getElementById('reportContainer');

    // Embed the report and display it within the div container.
    var report = powerbi.embed(reportContainer, config);

    // report.on will add an event handler which prints to Log window.
    report.on("error", function (event) {
        var logView = document.getElementById('logView');
        logView.innerHTML = logView.innerHTML + "Error<br/>";
        logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
        logView.innerHTML = logView.innerHTML + "---------<br/>";
    });
}
```

[integrate-report-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-report-web-app)을 다운로드하여 실행하면 샘플이 아래와 같이 표시됩니다.

![포함된 보고서 샘플](media/integrate-report/powerbi-embedded-report.png)

## <a name="working-with-groups-app-workspaces"></a>그룹(앱 작업 영역) 작업
그룹(앱 작업 영역)에서 보고서를 포함하려면 다음 REST API 호출을 사용하여 그룹의 대시보드 내에서 사용 가능한 모든 보고서 목록을 가져올 수 있습니다. 이 REST API 호출에 대한 자세한 정보를 확인하려면 [보고서 가져오기](https://msdn.microsoft.com/library/mt634543.aspx)를 참조하세요. 결과를 반환하라는 요청에 대한 권한이 그룹에 있어야 합니다.

```
https://api.powerbi.com/v1.0/myorg/groups/{group_id}/reports
```

위의 API에는 사용할 수 있는 보고서 목록을 반환합니다. 각 보고서에 그룹을 포함하도록 지원하는 이미 생성된 EmbedUrl 속성이 있습니다.

```
https://app.powerbi.com/reportEmbed?reportId={report_id}&groupId={group_id}
```

## <a name="next-steps"></a>다음 단계
검토하기 위한 샘플 응용 프로그램은 GitHub에서 사용할 수 있습니다. 자세한 내용은 [integrate-report-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-report-web-app)을 참조하세요.

JavaScript API에 사용할 수 있는 자세한 정보는 [Power BI JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript)를 참조하세요.

궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](http://community.powerbi.com/)

