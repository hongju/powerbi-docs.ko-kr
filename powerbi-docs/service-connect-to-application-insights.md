---
title: "Application Insights에 연결 Power BI에 연결"
description: "Power BI용 Application Insights"
services: powerbi
documentationcenter: 
author: SarinaJoan
manager: kfile
backup: maggiesMSFT
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 04cc92bd33f342097b9952a744d8dfffced22bb3
ms.sourcegitcommit: d91b7bf18d5c504037134f375886633379f28ede
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/27/2018
---
# <a name="connect-to-application-insights-with-power-bi"></a>Power BI로 Application Insights에 연결
Power BI를 사용하여 [Application Insights](https://azure.microsoft.com/documentation/articles/app-insights-overview/) 원격 분석에서 강력한 사용자 지정 대시보드를 만듭니다. 새로운 방식으로 앱 원격 분석을 구상합니다. 여러 앱 또는 구성 요소 서비스에서 하나의 대시보드에 메트릭을 결합합니다. Application Insights용 Power BI 콘텐츠 팩의 첫 번째 버전은 활성 사용자, 페이지 보기, 세션, 브라우저와 OS 버전 및 맵에서 사용자의 지리적 분포와 같은 일반적인 사용 관련 메트릭에 대한 위젯을 포함합니다.

[Power BI용 Application Insights 콘텐츠 팩](https://app.powerbi.com/getdata/services/application-insights)에 연결합니다.

>[!NOTE]
>연결하려면 Azure Preview 포털에서 응용 프로그램에 대한 Application Insights 개요 블레이드에 액세스하세요. 요구 사항에 대한 자세한 내용은 아래에 나와 있습니다.

## <a name="how-to-connect"></a>연결 방법
1. 왼쪽 탐색 창의 맨 아래에 있는 **데이터 가져오기** 를 선택합니다.
   
    ![데이터 단추 가져오기](media/service-connect-to-application-insights/pbi_getdata.png)
2. **서비스** 상자에서 **가져오기**를 선택합니다.
   
    ![서비스 단추 가져오기](media/service-connect-to-application-insights/pbi_getservices.png)
3. **Application Insights** > **가져오기**를 선택합니다.
   
    ![Application Insights 콘텐츠 팩](media/service-connect-to-application-insights/appinsights.png)
4. **Application Insights 리소스 이름**, **리소스 그룹**및 **구독 ID**를 포함하여 연결하려는 응용 프로그램의 세부 정보를 제공합니다. 자세한 내용은 아래 [Application Insights 매개 변수 찾기](#FindingAppInsightsParams)를 참조하세요.
   
    ![Application Insights 연결 대화 상자](media/service-connect-to-application-insights/pbi_contpkappinsitconnectndialog.png)    
5. **로그인** 을 선택하고 연결할 화면을 따릅니다.
   
    ![Application Insights 연결 로그인](media/service-connect-to-application-insights/pbi_contpkappinsitconnectn2.png)
6. 가져오기 프로세스가 자동으로 시작됩니다. 완료되면 알림이 보여지고 새 대시보드, 보고서 및 모델이 별표로 표시된 탐색 창에 나타납니다.  대시보드를 선택하여 가져온 데이터를 표시합니다.
   
    ![Application Insights 대시보드](media/service-connect-to-application-insights/pbi_contpkappinsitdash.png)

**다음 단계**

* 대시보드 맨 위에 있는 [질문 및 답변 상자에 질문](power-bi-q-and-a.md)합니다.
* 대시보드에서 [타일을 변경](service-dashboard-edit-tile.md)합니다.
* [타일을 선택](service-dashboard-tiles.md)하여 원본 보고서를 엽니다.
* 데이터 집합을 매일 새로 고치도록 예약하는 경우 새로 고침 일정을 변경하거나 **지금 새로 고침**을 사용하여 필요할 때 새로 고칠 수 있습니다.

## <a name="whats-included"></a>포함된 내용
Application Insights 콘텐츠 팩은 다음 테이블 및 메트릭을 포함합니다.  

    ´´´
    - ApplicationDetails  
    - UniqueUsersLast7Days   
    - UniqueUsersLast30Days   
    - UniqueUsersDailyLast30Days  
    - UniqueUsersByCountryLast7Days  
    - UniqueUsersByCountryLast30Days   
    - PageViewsDailyLast30Days   
    - SessionsLast7Days   
    - SessionsLast30Days  
    - PageViewsByBrowserVersionDailyLast30Days   
    - UniqueUsersByOperatingSystemLast7Days   
    - UniqueUsersByOperatingSystemLast30Days    
    - SessionsDailyLast30Days   
    - SessionsByCountryLast7Days   
    - SessionsByCountryLast30Days   
    - PageViewsByCountryDailyLast30Days  
    ´´´ 

<a name="FindingAppInsightsParams"></a>

## <a name="finding-parameters"></a>매개 변수 찾기
리소스 이름, 리소스 그룹 및 구독 ID는 모두 Azure Portal에서 찾을 수 있습니다. 이름을 선택하면 세부 정보 보기가 열리고 Essentials 드롭 다운을 사용하여 필요한 모든 값을 찾을 수 있습니다.

![Application Insights 매개 변수](media/service-connect-to-application-insights/pbi_contpkappinsitparams.png)

Power BI의 이러한 필드에 복사하고 붙여넣습니다.

![Application Insights 매개 변수](media/service-connect-to-application-insights/pbi_contpkappinsitparam2.png)

## <a name="next-steps"></a>다음 단계
[Power BI에서 시작](service-get-started.md)

[Power BI에서 데이터 가져오기](service-get-data.md)

