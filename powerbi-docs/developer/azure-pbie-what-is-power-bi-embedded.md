---
title: Azure Power BI Embedded 및 임베디드 분석의 정의 | Microsoft Docs
description: Power BI Embedded는 뛰어난 시각적 개체, 보고서 및 대시보드를 앱에 신속하게 추가할 수 있도록 지원하여 ISV와 개발자가 Power BI 기능을 사용하는 방식을 단순화하기 위한 임베디드 분석 도구로 설계되었습니다. Power BI Embedded를 통해 임베디드 분석 소프트웨어, 임베디드 분석 도구 또는 임베디드 비즈니스 인텔리전스 도구를 사용하는 방법을 알아봅니다.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: nishalit
ms.service: power-bi-embedded
ms.subservice: ''
ms.devlang: csharp, javascript
ms.topic: overview
ms.custom: seodec18
ms.date: 12/10/2018
ms.openlocfilehash: f04621fdfe7e6055d84fa4d2672c874837ff5ea4
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2019
ms.locfileid: "73864928"
---
# <a name="what-is-power-bi-embedded-in-azure"></a>Azure의 Power BI Embedded란?

Power BI Embedded는 ISV 및 개발자가 임베디드 분석과 함께 Power BI 기능을 사용하는 방식을 간소화하도록 설계되었습니다. Power BI Embedded는 뛰어난 시각적 개체, 보고서 및 대시보드를 앱에 빠르게 추가할 수 있도록 지원하여 Power BI 기능을 간소화합니다. Microsoft Azure에 빌드된 앱이 기계 학습, IoT 등의 서비스를 사용하는 방식과 비슷합니다. 해당 앱에서 쉽게 사용할 수 있는 데이터 탐색을 설정하여 ISV는 고객들이 상황에 맞는 신속한 데이터 기반 결정을 내릴 수 있도록 지원합니다.

> [!VIDEO https://www.youtube.com/embed/iEHfUuoZseo]

2017년 5월, Power BI와 Power BI Embedded 서비스 컨버전스를 발표했습니다. 융합을 통해 하나의 API 서페이스, 일관된 기능 집합은 물론, 두 서비스 전반에서 최신 기능에 대한 액세스를 제공했습니다. 또한 Power BI 사용 방식을 간소화하여 용량을 기반으로 한 가격 책정 모델을 선보이기도 했습니다.

Power BI Embedded의 개발로 ISV와 개발자는 Power BI API를 사용하여 앱에 인텔리전스를 포함하는 방식으로 더 높은 유연성을 확보할 수 있게 되었습니다. ISV와 개발자가 최소한의 노력으로 개발을 완료해 시장 출시 시점을 앞당기고 앱에 Microsoft의 최상급의 분석 기능을 도입할 수 있게 됨으로써 차별화된 서비스를 제공할 수 있습니다. 마찬가지로, 개발자는 시각적 분석 기능을 개발하는 대신, 자신의 솔루션에 집중하는 데 시간을 할애하여 고객의 요구를 충족할 수 있습니다. 또한 Power BI Embedded를 통해 사용자는 이미 사용하고 있는 유사한 개발 환경(Visual Studio 및 Azure) 내에서 작업할 수 있습니다.

Power BI 콘텐츠가 포함된 기존 앱이 Power BI Premium을 사용 중인가요? 앱을 제공하는 ISV, 개발자 또는 이러한 앱을 사용하는 조직 모두 별도의 조치가 필요하지 않습니다. 사용자는 물론, 고객도 중단 없이 이러한 앱을 계속 사용할 수 있습니다. Power BI 작업 영역 컬렉션에 기반하여 구축된 기존 앱이 있고 통합된 API 서페이스 및 새 용량 기반 Azure SKU를 활용하는 데 관심이 있다면 설명서에서 마이그레이션 지침을 참조하세요.

## <a name="comparing-power-bi-embedded-with-power-bi-premium"></a>Power BI Embedded와 Power BI Premium 비교

**Power BI Embedded**는 고객을 위해 애플리케이션을 구축하는 독립 소프트웨어 공급업체(ISV) 및 개발자용입니다. 서비스를 직접 구축하기 보다는 애플리케이션 데이터 시각화를 지원하는 타사 비즈니스 인텔리전스 서비스로 사용할 수 있습니다. Power BI Embedded는 개발자가 고객을 위해 보고서 및 대시보드를 애플리케이션에 포함할 수 있는 PaaS(Platform as a Service) 분석 솔루션입니다. **Power BI Premium**은 조직의 가장 중요한 비즈니스 데이터의 단일 보기를 제공하는 SaaS(software-as-a-service) 분석 솔루션입니다. 

[Power BI Embedded](https://azure.microsoft.com/pricing/details/power-bi-embedded/)가 종량제 기능인 반면, [Power BI Premium](https://powerbi.microsoft.com/calculator/)은 월별 요금이 필요합니다. 비교 방식에 대한 자세한 내용은 이 [동영상](https://www.youtube.com/watch?v=0y2oJikC6Xc&t=0s&list=PLv2BtOtLblH1dQPV49Ni12olDcUoW-GEl&index=3)에서 확인하세요.

## <a name="easy-to-use-tools"></a>사용하기 쉬운 도구

Power BI Embedded를 사용하면 가장 잘 할 수 있는 것, 즉 훌륭한 앱 구축에 집중할 수 있습니다. 이미 보유하고 있는 도구와 기술을 사용하여 Power BI Embedded로 관리하고 개발할 수 있습니다.

* [**Azure Portal**](https://portal.azure.com/): 모든 Azure 서비스를 관리하는 웹 기반 애플리케이션입니다.
* [**Visual Studio Code**](https://code.visualstudio.com/docs): 확장 프로그램을 지원하는 Windows, macOS 및 Linux용 다운로드 가능한 오픈 소스의 무료 코드 편집기입니다.
* [**Power BI Desktop**](https://powerbi.microsoft.com/desktop/): 시각적 분석을 사용하여 풍부한 대화형 보고서를 만드는 다운로드 가능한 무료 도구입니다.

REST API를 사용하여 Power BI Embedded는 어떠한 언어의 개발도 지원합니다.

## <a name="engage-with-the-power-bi-engineering-team"></a>Power BI 엔지니어링 팀과 협력

* [커뮤니티](https://community.powerbi.com/): Power BI에 관해 질의를 주고받을 수 있습니다.
* [Power BI Ideas](https://ideas.powerbi.com): 기능을 요청 및 제안합니다.
* [Reddit](https://www.reddit.com/r/PowerBI/): Power BI에 관해 논의합니다.

## <a name="next-steps"></a>다음 단계

용량 노드 세부 정보는 [가격 책정 페이지](https://azure.microsoft.com/pricing/details/power-bi-embedded/)를 참조하세요.

Power BI Embedded 용량을 만들려면 [Azure Portal에서 Power BI Embedded 용량 만들기](azure-pbie-create-capacity.md)를 참조하세요.

Power BI 콘텐츠를 포함하려면 [Power BI 대시보드, 보고서 및 타일 포함 방법](https://powerbi.microsoft.com/documentation/powerbi-developer-embedding-content/)을 참조하세요.
