---
title: 자동 조직에 대 한 포함 하는 경우 Power BI 앱 설치
description: 조직에 대 한 포함 하는 경우 설치 Power BI 앱을 자동 하는 방법에 알아봅니다.
ms.subservice: powerbi-developer
author: rkarlin
ms.author: rkarlin
manager: kfile
ms.topic: how-to
ms.service: powerbi
ms.custom: ''
ms.date: 04/16/2019
ms.openlocfilehash: bb9ba5531c2a23f15ccbf98261e246ab7080aecb
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "61376228"
---
# <a name="auto-install-power-bi-apps-when-embedding-for-your-organization"></a>조직에 대 한 포함 하는 경우 Power BI 앱 자동 설치

앱에서 콘텐츠를 포함 하는 포함 하는 사용자에 게 해야 합니다 [앱에 대 한 액세스](../service-create-distribute-apps.md)합니다. 앱 사용자에 대 한 설치 된 경우 원활 하 게 작동을 포함 합니다. 자세한 내용은 [앱에서 대시보드 또는 보고서 포함](embed-from-apps.md)합니다. 모든 앱이 될 수 있는 PowerBI.com에서 정의 하는 것이 불가능 [자동으로 설치](https://powerbi.microsoft.com/blog/automatically-install-apps/)합니다. 그러나이 이렇게 테 넌 트 수준에서 수행 되 고 모든 앱에 적용 됩니다.

## <a name="auto-install-app-on-embedding"></a>포함에 대 한 앱을 자동으로 설치 합니다.

사용자가 앱에 액세스할 경우 앱 설치 되지 않은 실패를 포함 합니다. 앱에서 포함 하는 경우 이러한 오류를 방지할 수 있습니다, 포함 되 면 앱의 자동 설치를 허용할 수 있습니다. 이 작업을 자동으로 설치 됩니다 포함 하는 사용자가 앱 설치 되지 않은 경우를 의미 합니다. 따라서 콘텐츠 가져옵니다 포함 즉시 사용자에 대 한 원활한 환경을 생성 합니다.

## <a name="embed-for-power-bi-users-user-owns-data"></a>Power BI 사용자 (사용자 소유 데이터) 포함

사용자에 게 앱의 자동 설치를 허용 하려면 ' 콘텐츠 만들기 ' 권한이 응용 프로그램을 지정 해야 하면 [응용 프로그램을 등록](register-app.md#register-with-the-power-bi-application-registration-tool), 이미 앱을 등록 하는 경우 추가 합니다.

![콘텐츠를 만드는 앱 등록](media/embed-auto-install-app/register-app-create-content.png)

다음으로 embed URL에서 앱 ID를 제공 해야 합니다. 앱 ID를 제공 하려면 앱 작성자는 먼저 해야 앱을 설치한 다음 지원 되는 중 하나를 사용 하 여 [Power BI Rest API](https://docs.microsoft.com/rest/api/power-bi/) 호출 [보고서 가져오기](https://docs.microsoft.com/rest/api/power-bi/reports/getreports) 하거나 [대시보드 가져오기](https://docs.microsoft.com/rest/api/power-bi/dashboards/getdashboards)합니다. 그런 다음 앱 작성자는 REST API 응답에서 embed Url을 사용 해야 합니다. 앱에서 콘텐츠를 하는 경우 앱 ID URL에 나타납니다.  Embed URL를 설정한 후에 정기적으로 포함 하려면 사용할 수 있습니다.

## <a name="secure-embed"></a>보안 포함

앱의 자동 설치를 사용 하려면 앱 작성자는 먼저 앱을 설치 하 고 PowerBI.com에서 앱에 보고서로 이동 하 고 일반적인 방식으로 링크를 가져올 이동 해야 합니다. 링크를 사용할 수 있는 앱에 대 한 액세스를 사용 하 여 다른 모든 사용자는 보고서를 포함할 수 있습니다.

## <a name="considerations-and-limitations"></a>고려 사항 및 제한 사항

* 이 시나리오에 대 한 대시보드와 보고서만 포함할 수 있습니다.

* 이 기능은 현재 지원 되지 않습니다 앱 소유 데이터 시나리오를 포함 하는 SharePoint에 대 한.