---
title: "Power BI 프리미엄이란?"
description: "Power BI 프리미엄은 조직 또는 팀의 전용 용량으로, 사용자별 라이선스를 구입하지 않고도 더욱 신뢰할 수 있는 성능과 대용량 데이터 볼륨을 제공합니다."
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
ms.date: 02/05/2018
ms.author: maghan
ms.openlocfilehash: b2e41884ca799ca07223a4b5444e39b38aa2102a
ms.sourcegitcommit: db37f5cef31808e7882bbb1e9157adb973c2cdbc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2018
---
# <a name="power-bi-premium---what-is-it"></a>Power BI 프리미엄이란?
Power BI 프리미엄은 더욱 신뢰할 수 있는 성능과 더 큰 데이터 볼륨을 제공하여 조직 또는 팀에 대한 Power BI 서비스 실행에 전용 리소스를 제공합니다. 또한 프리미엄을 통해 뷰어를 위한 사용자별 라이선스를 구입할 필요 없이 광범위하게 콘텐츠를 배포할 수 있습니다.

프리미엄 용량에 작업 영역을 할당하여 Power BI 프리미엄을 활용할 수 있습니다. *프리미엄 용량*은 조직을 위한 전용 리소스입니다. 프리미엄 용량에 할당되지 않은 작업 영역의 경우 이는 공유 용량에 있게 됩니다.

*공유 용량*은 다른 고객에 의해 공유되는 계산 리소스에서 작업을 실행하는 Power BI에 익숙한 환경입니다. 공유 용량에서 모든 사용자를 위해 환경의 품질을 보장하도록 더 많은 제한이 개별 사용자에게 적용됩니다.

[!INCLUDE [powerbi-premium-illustration](./includes/powerbi-premium-illustration.md)]

<iframe width="560" height="315" src="https://www.youtube.com/embed/lNQDkN0GXzU?rel=0&amp;showinfo=0" frameborder="0" allowfullscreen></iframe>

## <a name="capacity-tiers"></a>용량 계층
Power BI 내에는 두 가지 유형의 용량이 있습니다. 공유 용량 및 Power BI 프리미엄 용량입니다. 차이점을 살펴보면 다음과 같습니다.

|  | 공유 용량 | Power BI 프리미엄 용량 |
| --- | --- | --- |
| **새로 고침 빈도** |8/일 |제한되지 않음 |
| **전용 하드웨어로 격리** |![](media/service-premium/not-available.png "사용할 수 없음") |![](media/service-premium/available.png "사용 가능함") |
| **엔터프라이즈 배포 대상** ***모든 사용자*** | | |
| 앱 |![](media/service-premium/not-available.png "사용할 수 없음") |![](media/service-premium/available.png "사용 가능함")<sup>1</sup> |
| 포함된 API 및 컨트롤 |![](media/service-premium/not-available.png "사용할 수 없음") |![](media/service-premium/available.png "사용 가능함")<sup>2</sup> |
| **Power BI 보고서 온-프레미스 게시** |![](media/service-premium/not-available.png "사용할 수 없음") |![](media/service-premium/available.png "사용 가능함") |

<sup>1</sup> 앱에서 무료 사용자 사용에는 웹 및 모바일에서 콘텐츠 보기, 질문 및 답변 사용, 신속한 정보 활용, Cortana, CSV, Excel 및 PowerPoint로 내보내기가 포함됩니다. 공유 데이터 집합에서 보고서 만들기, Excel에서 분석처럼 나열되지 않은 다른 작업에는 Pro 라이선스가 필요합니다. [Power BI Pro와 무료 버전](service-free-vs-pro.md) 기능에 대해 자세히 알아보세요.  
*<sup>2</sup> Power BI 프리미엄에 제공되는 향후 개선 사항은 GA를 게시합니다.*

### <a name="premium-capacity"></a>프리미엄 용량
Power BI 프리미엄 용량의 사용을 시작하려면 작업 영역을 용량에 할당해야 합니다. 작업 영역을 프리미엄 용량에 할당하는 방법에 대한 자세한 내용은 [Power BI 프리미엄 관리](service-admin-premium-manage.md)를 참조하세요.

작업 영역이 프리미엄 용량으로 뒷받침되면 Power BI 프리미엄의 장점을 이용할 수 있습니다.

* 예약된 새로 고침: 사용자 우선 순위는 가져온 모델로 새로 고침을 예약할 때 하루 8x개로 제한되어 있었습니다. 이 제한은 프리미엄 작업 영역에서 데이터 집합에 대해 해제되었습니다. DirectQuery에 대한 예약된 캐시 새로 고침 설정에 적용되지 않습니다. 프리미엄 및 공유 용량 사이에는 동일하게 유지됩니다.
* 전용 하드웨어로 격리 – 공유 용량의 특성으로 보고서 및 대시보드의 성능은 안전 조치에도 불구하고 용량에서 다른 작업의 리소스 요청에 의해 영향을 받을 수 있습니다. 반대로, 프리미엄은 관련되지 않은 작업에서 분리하여 작업에 대한 보다 일관된 신뢰할 수 있는 성능을 제공합니다.

앱이 프리미엄 용량에 의해 뒷받침되는 경우(즉, 현재 프리미엄에 할당된 앱 작업 영역에서 게시되었음) 게시된 앱은 할당된 라이선스에 관계 없이 조직의 모든 사용자가 사용할 수 있습니다. 이는 Power BI 무료 사용자도 이러한 게시된 앱을 사용할 수 있음을 의미합니다.

### <a name="shared-capacity"></a>공유 용량
기본적으로 작업 영역은 공유 용량에 있게 됩니다. 이는 앱 작업 영역과 함께 개인적인 *내 작업 영역*을 포함합니다. 공유 용량은 다른 고객에 의해 공유되는 계산 리소스에서 작업을 실행하는 Power BI에 익숙한 환경입니다.

<a name="premiumskus"/>

### <a name="premium-capacity-nodes"></a>프리미엄 용량 노드
Power BI 프리미엄은 서로 다른 v-코어 용량으로 노드 구성에서 사용할 수 있습니다. 특정 SKU 제품 및 비용에 대한 자세한 내용은 [Power BI 가격 책정](https://powerbi.microsoft.com/pricing/)을 참조하세요. 또한 [비용 계산기](https://powerbi.microsoft.com/calculator/)를 사용할 수 있습니다. 포함된 분석 용량 계획에 관한 정보는 [Power BI 엔터프라이즈 배포 계획 백서](https://aka.ms/pbienterprisedeploy)를 참조하세요.

* P 노드는 포함된 배포 또는 서비스 배포에 사용할 수 있습니다.
* EM 노드는 포함된 배포에만 사용할 수 있습니다.
* EM1 및 EM2 
* 이 표의 링크는 Office 365 전역 관리자인 사용자에 대해서만 정상적으로 작동하고, 그 외의 사용자는 404 오류를 수신합니다. 

| 용량 노드 | 총 코어<br/>*(백 엔드 + 프런트 엔드)* | 백 엔드 코어 | 프런트 엔드 코어 | DirectQuery/라이브 연결 제한 | 사용량이 가장 많은 시간에 최대 페이지 렌더링 | 가용성 |
| --- | --- | --- | --- | --- | --- | --- |
| [EM1(매월)](https://portal.office.com/SubscriptionDetails?OfferId=4004702D-749C-4F74-BF47-3048F1833780&adminportal=1) |1개 가상 코어 |0.5개 코어, 2.5GB RAM |0.5개 코어 |초당 3.75 |150-300 |사용 가능함 |
| [EM2(매월)](https://portal.office.com/SubscriptionDetails?OfferId=4004702D-749C-4F74-BF47-3048F1833780&adminportal=1) |2v-코어 |1개 코어, 5GB RAM |1개 코어 |초당 7.5 |301-600 |사용 가능함 |
| [EM3(매월)](https://portal.office.com/SubscriptionDetails?OfferId=4004702D-749C-4F74-BF47-3048F1833780&adminportal=1) |4v-코어 |2개 코어, 10GB RAM |2개 코어 | |601-1,200 |사용 가능함 |
| [P1](https://portal.office.com/SubscriptionDetails?OfferId=b3ec5615-cc11-48de-967d-8d79f7cb0af1&adminportal=1) |8v-코어 |4개 코어, 25GB RAM |4개 코어 |초당 30 |1,201-2,400 |사용 가능함([매월](https://portal.office.com/SubscriptionDetails?OfferId=E4C8EDD3-74A1-4D42-A738-C647972FBE81&adminportal=1)도 사용 가능함) |
| [P2](https://portal.office.com/SubscriptionDetails?OfferId=062F2AA7-B4BC-4B0E-980F-2072102D8605&adminportal=1) |16v-코어 |8개 코어, 50GB RAM |8개 코어 |초당 60 |2,401-4,800 |사용 가능함 |
| [P3](https://portal.office.com/SubscriptionDetails?OfferId=40c7d673-375c-42a1-84ca-f993a524fed0&adminportal=1) |32v-코어 |16개 코어, 100GB RAM |16개 코어 |초당 120 |4,801-9600 |사용 가능함 |

* 프런트 엔드 코어는 웹 서비스, 대시보드 및 보고서 문서 관리, 액세스 권한 관리, 예약, API, 업로드 및 다운로드, 일반적으로 사용자 환경에 관련된 모든 항목에 책임이 있습니다.
* 백 엔드 코어는 어려운 작업: 쿼리 처리, 캐시 관리, R 서버 실행, 데이터 새로 고침, 자연어 처리, 실시간 피드, 보고서 및 이미지의 서버 쪽 렌더링에 책임이 있습니다. 백 엔드 코어를 사용하여 메모리의 일정량도 예약됩니다. 큰 데이터 모델 또는 많은 수의 활성 데이터 집합을 처리할 때 충분한 메모리를 갖는 것은 특히 중요해지고 있습니다.

## <a name="power-bi-report-server"></a>Power BI Report Server
Power BI 프리미엄은 Power BI Report Server 온-프레미스를 실행할 수 있는 권한을 포함합니다. 자세한 내용은 [Power BI Report Server 시작](report-server/get-started.md)을 참조하세요.

## <a name="next-steps"></a>다음 단계
[Power BI 프리미엄 FAQ](service-premium-faq.md)  
[Power BI 프리미엄 릴리스 정보](service-premium-release-notes.md)  
[Power BI 프리미엄 구매 방법](service-admin-premium-purchase.md)  
[Power BI 프리미엄 관리](service-admin-premium-manage.md)  
[Microsoft Power BI 프리미엄 백서](https://aka.ms/pbipremiumwhitepaper)  
[Power BI 엔터프라이즈 배포 계획 백서](https://aka.ms/pbienterprisedeploy)  
[조직에서 Power BI 관리](service-admin-administering-power-bi-in-your-organization.md)  

궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](https://community.powerbi.com/)

