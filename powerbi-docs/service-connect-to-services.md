---
title: Power BI에서 사용하는 서비스에 연결
description: Salesforce, Microsoft Dynamics CRM, Google 분석과 같은 비즈니스를 운영하는 데 사용하는 다양한 서비스에 연결합니다.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.topic: conceptual
ms.date: 04/19/2019
ms.author: maggies
LocalizationGroup: Connect to services
ms.openlocfilehash: 53abb5f82b75773817c72b53dd3e522cb4ccc63e
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "64578742"
---
# <a name="connect-to-the-services-you-use-with-power-bi"></a>Power BI에서 사용하는 서비스에 연결
Power BI를 사용하여, 비즈니스를 운영하기 위해  Salesforce, Microsoft Dynamics, Google 분석과 같은 다양한 서비스에 연결할 수 있습니다. Power BI는 서비스에 연결할 자격 증명을 사용하여 시작합니다. 비즈니스에 대한 시각적 통찰력을 제공하고 자동으로 데이터를 표시하는 Power BI 보고서 집합과 하나의 대시보드로 구성된 Power BI *작업 영역*이 생성됩니다.

[연결할 수 있는 서비스](https://app.powerbi.com/getdata/services)를 모두 보려면 Power BI에 로그인합니다. 

![AppSource 앱](media/service-connect-to-services/overview.png)

앱을 설치한 후, Power BI 서비스([https://app.powerbi.com](https://app.powerbi.com))에서 앱 및 작업 영역에서 대시보드 및 보고서를 볼 수 있습니다. 또한 Power BI 모바일 앱에서 보고서와 대시보드를 볼 수 있습니다. 작업 영역에서, 대시보드 및 보고서를 조직의 요구에 맞게 수정한 다음 동료에게 *앱*으로 배포할 수 있습니다. 

![Power BI 모바일 앱의 Google 웹로그 분석 앱](media/service-connect-to-services/power-bi-service-mobile-app-240.png)

## <a name="get-started"></a>시작
[!INCLUDE [powerbi-service-apps-get-more-apps](./includes/powerbi-service-apps-get-more-apps.md)]

## <a name="edit-the-dashboard-and-reports"></a>대시보드 및 보고서를 편집 합니다.
가져오기가 완료되면 새 앱이 앱 페이지에 표시됩니다.

1. 왼쪽 탐색 창에서 **앱**을 선택하고 앱을 선택합니다.
   
     ![앱 페이지](media/service-connect-to-services/power-bi-service-apps-open-app.png)
2. 질문 및 답변 상자에서 입력하여 질문하고 타일을 클릭하여 기본 보고서를 열 수 있습니다. 
   
    ![Google 웹로그 분석 대시보드](media/service-connect-to-services/googleanalytics2.png)
   
    대시보드 및 보고서를 조직의 요구에 맞게 변경합니다. 그런 다음 [동료에게 앱을 배포](service-create-distribute-apps.md)합니다.

## <a name="whats-included"></a>포함된 내용
서비스에 연결한 후, 새로 생성한 앱 및 대시보드, 보고서 및 데이터 세트가 있는 작업 영역을 볼 수 있습니다. 서비스의 데이터는 특정 시나리오에 초점을 맞추며 서비스의 모든 정보가 포함되어 있지는 않을 수 있습니다. 하루에 한 번 자동으로 데이터가 새로 고쳐지도록 예약됩니다. 데이터 세트를 선택하여 일정을 제어할 수 있습니다.

또한 Google 분석 등 [Power BI Desktop에서 많은 서비스에 연결](desktop-data-sources.md)할 수 있으며, 사용자 고유의 사용자 지정된 대시보드 및 보고서를 만들 수 있습니다.  

특정 서비스에 연결하는 방법에 대한 자세한 내용은 개별 도움말 페이지를 참조합니다.

## <a name="troubleshooting"></a>문제 해결
**빈 타일**  
Power BI가 서비스에 먼저 연결하는 동안, 대시보드에 빈 타일 집합이 표시될 수 있습니다. 2시간 후에 빈 대시보드가 계속 나타나면, 연결하지 못한 것입니다. 문제 해결 정보가 포함된 오류 메시지가 표시되지 않은 경우, 지원 티켓을 제출합니다.

* 오른쪽 위 모퉁이에서 물음표 아이콘( **?** ) > **도움말 보기**를 선택합니다.
  
    ![도움말 보기 아이콘](media/service-connect-to-services/power-bi-service-get-help.png)

**누락된 정보**  
대시보드 및 보고서는 특정 시나리오에 초점을 맞춘 서비스의 콘텐츠를 포함합니다. 앱에서 특정 메트릭을 찾는데 표시되지 않는 경우, [Power BI 지원](https://support.powerbi.com/forums/265200-power-bi) 페이지에 아이디어를 추가합니다.

## <a name="suggesting-services"></a>서비스 제안
Power BI 앱에 제안하려는 서비스를 사용하나요? [Power BI 지원](https://support.powerbi.com/forums/265200-power-bi) 페이지로 이동하여 의견을 알려 주세요.

직접 배포할 템플릿 앱을 만드는 데 관심이 있으면, [Power BI에서 템플릿 앱 만들기](service-template-apps-create.md)를 참조하세요. Power BI 파트너는 거의 또는 전혀 코딩 없이 Power BI 앱을 작성하고 Power BI 고객에게 배포할 수 있습니다. 

## <a name="next-steps"></a>다음 단계
* [동료에게 앱 배포](service-create-distribute-apps.md)
* [Power BI에서 새 작업 영역 만들기](service-create-the-new-workspaces.md)
* 궁금한 점이 있나요? [Power BI 커뮤니티에 질문합니다.](http://community.powerbi.com/)
* 궁금한 점이 있나요? [Power BI 커뮤니티에 질문합니다.](http://community.powerbi.com/)

