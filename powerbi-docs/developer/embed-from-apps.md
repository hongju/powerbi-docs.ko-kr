---
title: 앱에서 보고서 또는 대시보드 포함
description: 앱 작업 영역이 아닌 Power BI 앱에서 보고서 또는 대시보드를 통합하거나 포함하는 방법에 대해 알아봅니다.
author: markingmyname
ms.author: maghan
ms.date: 07/13/2018
ms.topic: how-to
ms.service: powerbi
ms.component: powerbi-developer
ms.custom: mvc
manager: kfile
ms.openlocfilehash: 2817ccb25fc9aa6d3e8150c776558366dcf0ccb6
ms.sourcegitcommit: 0c870a006e525447497e678484874a2f137b9abd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/17/2018
ms.locfileid: "39088842"
---
# <a name="embed-reports-or-dashboards-from-apps"></a>앱에서 보고서 또는 대시보드 포함

**Power BI**에서 앱을 만들어 관련된 **대시보드** 및 **보고서**를 한 곳에 결합한 다음, 조직의 대규모 사용자 그룹에 게시할 수 있습니다. 이러한 앱의 사용은 모든 사용자가 Power BI 사용자인 경우 적합하므로 Power BI 앱을 사용하여 해당 사용자와 콘텐츠를 공유할 수 있습니다. 게시된 Power BI 앱 및 타사 응용 프로그램에 콘텐츠를 포함시키는 방법에 대한 몇 가지 간단한 단계를 공유하고자 합니다.

## <a name="how-to-grab-report-embed-url-for-embedding"></a>임베디드를 위해 보고서 포함 URL을 가져오는 방법

1. 자신과 공유하거나 다른 사용자에게 이 흐름을 통과하도록 안내하여 사용자 작업 영역(‘내 작업 영역’)에서 응용 프로그램을 인스턴스화합니다.

2. Power BI 서비스에서 원하는 보고서를 엽니다.

3. SharePoint Online에서 파일->Embed로 이동하여 여기에서 보고서 포함 URL(아래 스냅샷에서 볼 수 있음)을 가져오거나, GetReports/GetReport REST API를 호출하고 응답에서 해당 보고서 embedURL 필드를 추출합니다(REST 호출은 앱이 사용자의 작업 영역에서 인스턴스화된대로 작업 영역 식별자가 URL의 일부로 포함되지 않아야 함).

4. 3단계에서 검색된 embed URL을 사용하여 JS SDK와 함께 사용합니다.

    ![앱에서 포함](media/embed-from-apps/embed-from-app.png)

## <a name="how-to-grab-dashboard-embed-url-for-embedding"></a>임베디드를 위해 대시보드 포함 URL을 가져오는 방법

1. 자신과 공유하거나 다른 사용자에게 이 흐름을 통과하도록 안내하여 사용자 작업 영역(‘내 작업 영역’)에서 응용 프로그램을 인스턴스화합니다.

2. GetDashboards REST API를 호출하고 해당 대시보드 embedURL 필드를 추출합니다(REST 호출은 앱이 사용자의 작업 영역에서 인스턴스화된대로 작업 영역 식별자가 URL의 일부로 포함되지 않아야 함).

3. 4단계에서 검색된 embed URL을 사용하여 JS SDK와 함께 사용합니다.

## <a name="next-steps"></a>다음 단계

또한 타사 고객 및 조직을 위해 앱 작업 영역에 포함하는 방법을 검토합니다.

> [!div class="nextstepaction"]
>[타사 고객을 위해 포함](embed-sample-for-customers.md)

> [!div class="nextstepaction"]
>[조직에 포함](embed-sample-for-your-organization.md)