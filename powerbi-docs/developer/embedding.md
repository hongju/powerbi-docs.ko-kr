---
title: Power BI를 사용한 임베디드 분석
description: Power BI는 대시보드 및 보고서에 대한 임베디드 분석을 사용하기 위한 API를 애플리케이션에 제공합니다. 임베디드 분석 소프트웨어, 임베디드 분석 도구 또는 임베디드 비즈니스 인텔리전스 도구를 사용하여 PaaS 환경과 SaaS 환경 모두에 Power BI와 함께 포함하는 방법을 자세히 알아봅니다.
author: rkarlin
ms.author: rkarlin
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: overview
helpviewer_keywords:
- embedded analytics
- embedding
- Power BI embedding
- app owns data
- user owns data
- Power BI APIs
ms.custom: seodec18
ms.date: 05/15/2019
ms.openlocfilehash: a212691f2af877e3b86e021a4f48644f4fa6e8e3
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "66051053"
---
# <a name="embedded-analytics-with-power-bi"></a>Power BI를 사용한 임베디드 분석

Power BI 서비스(SaaS) 및 Azure의 Power BI Embedded(PaaS)에는 대시보드 및 보고서 포함을 위한 API가 있습니다. 콘텐츠를 포함 하는,이 대시보드, 게이트웨이 및 앱 작업 영역을 같은 최신 Power BI 기능에 액세스할을 수 있습니다.

[포함 설정 도구](https://aka.ms/embedsetup)를 통해 신속하게 시작하고 샘플 애플리케이션을 다운로드할 수 있습니다.

사용자에게 적합한 솔루션을 선택합니다.

* [조직에 대한 콘텐츠를 포함하면](embedding.md#embedding-for-your-organization) Power BI 서비스를 확장할 수 있습니다. 이 작업을 수행 하려면 구현 합니다 [조직에 대 한 Embed](https://aka.ms/embedsetup/UserOwnsData) 솔루션입니다.
* [고객을 위해 포함](embedding.md#embedding-for-your-customers) 대시보드 및 보고서를 Power BI 계정이 없는 사용자를 포함할 수 있습니다. 이 작업을 수행 하려면 구현 합니다 [고객에 대 한 Embed](https://aka.ms/embedsetup/AppOwnsData) 솔루션입니다.

![PBIE 샘플](media/what-can-you-do/what-can-you-do-02.png)

## <a name="use-apis"></a>Api 사용

Power BI 콘텐츠 포함에 대 한 두 가지 주요 시나리오는
- 조직의 사용자 (Power BI 라이선스가)에 대 한 포함 합니다. 
 
- 사용자와 Power BI 라이선스가 필요 하지 않습니다 하는 고객에 대 한 포함 합니다. 

합니다 [Power BI REST API](https://docs.microsoft.com/rest/api/power-bi/) 시나리오 둘 다 사용할 수 있습니다.

Power BI 라이선스가 없는 고객 및 사용자의 경우 조직 또는 고객에게 서비스를 제공할 때 사용하는 것과 동일한 API를 사용하여 대시보드 및 보고서를 사용자 지정 애플리케이션에 포함할 수 있습니다. 고객 관리 응용 프로그램 데이터를 봅니다. 또한 조직의 Power BI 사용자는 추가 옵션이 보려는 *자신이* Power BI에서 직접 또는 포함된 된 응용 프로그램의 컨텍스트에서 합니다. 포함 필요에 따라 JavaScript 및 REST API를 완벽하게 활용할 수 있습니다.

포함 작동 방식을 이해 하려면 참조는 [JavaScript 포함 샘플](https://microsoft.github.io/PowerBI-JavaScript/demo/)합니다.

## <a name="embedding-for-your-organization"></a>조직에 대한 콘텐츠 포함

**조직에 대한 콘텐츠를 포함하면** Power BI 서비스를 확장할 수 있습니다. 이 포함 된 콘텐츠를 보려면 Power BI 서비스에 응용 프로그램의 사용자가 로그인을 해야 합니다. 조직 내 사용자가 로그인하면 본인이 소유하거나 Power BI 서비스에서 사용자가 공유한 대시보드 및 보고서에만 액세스할 수 있습니다.

조직 포함 예제와 같은 내부 응용 프로그램을 포함할 [SharePoint Online](https://powerbi.microsoft.com/blog/integrate-power-bi-reports-in-sharepoint-online/)를 [(관리자 권한을 있어야)는 Microsoft Teams 통합](https://powerbi.microsoft.com/blog/power-bi-teams-up-with-microsoft-teams/), 및 [Microsoft Dynamics](https://docs.microsoft.com/dynamics365/customer-engagement/basics/add-edit-power-bi-visualizations-dashboard).

조직에 포함 하려면 참조 [자습서: 조직에 대 한 응용 프로그램에 Power BI 콘텐츠 포함](embed-sample-for-your-organization.md)합니다.

편집, 저장 등과 같은 셀프 서비스 기능은 Power BI 사용자에 대해 포함하는 경우 [JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript)를 통해 사용할 수 있습니다.

진행할 수 있습니다 합니다 [포함 설치 도구](https://aka.ms/embedsetup/UserOwnsData) 를 시작 하 고 조직에 대 한 보고서를 통합을 통해 안내 하는 샘플 응용 프로그램을 다운로드 합니다.

## <a name="embedding-for-your-customers"></a>고객에 대한 콘텐츠 포함

**고객을 위해 포함** 대시보드 및 Power BI 계정이 없는 사용자에 대 한 보고서를 포함할 수 있습니다. 이 포함이 라고도 *Power BI Embedded*합니다.

[Power BI Embedded](azure-pbie-what-is-power-bi-embedded.md) 되는 **Microsoft Azure** 응용 프로그램에 시각적 개체, 보고서 및 대시보드를 포함 하는 독립 소프트웨어 공급 업체 (Isv) 및 개발자를 신속 하 게 수 있는 서비스입니다. 포함이 용량 기반 시간당 요금된 모델을 통해 수행 됩니다.

![고객에 대한 콘텐츠를 포함하는 워크플로 포함](media/embedding/powerbi-embed-flow.png)

Power BI Embedded에는 ISV, 해당 개발자 및 고객에 대한 혜택이 있습니다. 예를 들어 ISV는 Power BI Desktop을 사용하여 시각적 개체를 무료로 만들 수 있습니다. 시각적 분석 개발 작업을 최소화 하 여 isv가 시장 출시 시간을 달성 하 고 차별화 된 데이터 환경 경쟁에서 차별화 합니다. Isv 자신이 포함 된 분석을 사용 하 여 만든 추가 값에 대 한 프리미엄 요금을 청구 하도록 선택할 수도 있습니다.

Power BI Embedded에서 고객은 Power BI에 대해 알 필요가 없습니다. 포함 된 응용 프로그램을 만드는 두 가지 방법을 사용할 수 있습니다.
- Power BI Pro 계정 
- 서비스 사용자 

Power BI Pro 계정은 응용 프로그램의 마스터 계정 (생각해보면 프록시 계정으로) 처럼 작동합니다. 이 계정을 생성할 수 있습니다. 응용 프로그램의 Power BI 대시보드 및 보고서에 대 한 액세스를 제공 하는 토큰을 포함 합니다.

[서비스 주체](embed-service-principal.md)는 **앱 전용** 토큰을 사용하여 Power BI 콘텐츠를 애플리케이션에 포함할 수 있습니다. 생성할 수 있습니다이 응용 프로그램의 Power BI 대시보드 및 보고서에 대 한 액세스를 제공 하는 토큰을 포함 합니다.

Power BI Embedded를 사용 하는 개발자가 응용 프로그램의 핵심 기능 보다는 지출 한도 시각적 개체 개발 하는 시간 및 분석 개발에 집중 하는 시간을 투자할 합니다. 신속 하 게 고객 보고서 및 대시보드 요구 사항을 충족할 수 있으며 완전히 문서화 된 Api 및 Sdk를 사용 하 여 쉽게 포함. 앱에서 탐색하기 쉬운 데이터 탐색을 설정하여 ISV를 사용하면 고객이 모든 디바이스에서 상황에 맞는 신속한 데이터 기반 결정을 내릴 수 있습니다.

> [!IMPORTANT]
> Power BI 서비스에 필요한 포함 수행 고객에 게 응용 프로그램의 포함 된 콘텐츠를 보려면 Power BI 계정이 필요는 없습니다. 

프로덕션으로 이동할 준비가 되면 앱 작업 영역은 전용 용량에 할당되어야 합니다. Microsoft Azure 내에서 Power BI Embedded는 애플리케이션에서 사용할 [전용 용량](azure-pbie-create-capacity.md)을 제공합니다.

세부 정보를 포함 하는 경우, 참조 [Power BI 콘텐츠를 포함 하는 방법을](embed-sample-for-customers.md)합니다.

## <a name="next-steps"></a>다음 단계

이제 Power BI 콘텐츠를 애플리케이션에 포함하거나 고객에 대한 Power BI 콘텐츠를 포함할 수 있습니다.

> [!div class="nextstepaction"]
> [조직에 포함](embed-sample-for-your-organization.md)

> [!div class="nextstepaction"]
> [Power BI Embedded란?](azure-pbie-what-is-power-bi-embedded.md)

> [!div class="nextstepaction"]
>[고객에 대한 콘텐츠 포함](embed-sample-for-customers.md)

궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](http://community.powerbi.com/)
