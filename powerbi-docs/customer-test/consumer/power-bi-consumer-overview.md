---
title: 소비자용 Power BI
description: Power BI 개요 및 다양한 부분의 연동 방식 - Power BI Desktop, Power BI 서비스, Power BI Mobile, Report Server, Power BI Embedded
author: mihart
manager: kfile
ms.service: powerbi
ms.component: powerbi-service
ms.topic: overview
ms.date: 06/22/2018
ms.author: mihart
LocalizationGroup: Get started
ms.openlocfilehash: 2d0e94517556f071884380468ae88e7641e79310
ms.sourcegitcommit: 8bad5ed58e9e406aca53996415b1240c2972805e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/11/2018
ms.locfileid: "44343419"
---
# <a name="power-bi-for-consumers"></a>소비자용 Power BI
**Power BI**는 관련 없는 데이터 소스를 시각적으로 몰입도가 뛰어나고 일관된 대화형 정보로 변환하는 소프트웨어 서비스, 앱 및 커넥터의 컬렉션입니다. 데이터가 간단한 Excel 스프레드시트이든 클라우드 기반 온-프레미스 하이브리드 데이터 웨어하우스 컬렉션이든 **Power BI**를 통해 손쉽게 데이터 소스를 연결하고, 중요한 내용을 시각화(또는 검색)하고, 이 내용을 원하는 모든 사람과 공유할 수 있습니다.

![Power BI에 대한 입력 소스를 보여 주는 다이어그램](media/power-bi-overview/power-bi-input.png)

**Power BI**는 단순하고 빠르기 때문에 Excel 스프레드시트 또는 로컬 데이터베이스에서 빠른 정보를 생성할 수 있습니다. 하지만 **Power BI**는 강력하면서도 엔터프라이즈급이기 때문에 광범위한 모델링 및 실시간 분석뿐 아니라 사용자 지정 개발에 즉시 사용할 수 있습니다. 따라서 Power BI는 개인 보고서 및 시각화 도구일 수 있으며, 그룹 프로젝트, 사업부 또는 회사 전체의 분석 및 의사 결정 엔진으로 역할도 할 수 있습니다.

## <a name="the-parts-of-power-bi"></a>Power BI의 요소
Power BI는 **Power BI Desktop**이라는 Windows 데스크톱 응용 프로그램, **Power BI 서비스**라는 온라인 SaaS(*Software as a Service*), Windows Phone 및 태블릿뿐 아니라 iOS 및 Android 장치에서 사용할 수 있는 모바일 Power BI **앱**으로 구성됩니다.

![Power BI Desktop, 서비스, 모바일](media/power-bi-overview/power-bi-blocks.png)

이 세 가지 요소(**Desktop**, **서비스** 및 **모바일**)는 직원들이 자신 또는 자신의 역할에 가장 효과적인 방식으로 비즈니스 통찰력을 생성, 공유 또는 소비하도록 설계되었습니다.

## <a name="how-power-bi-matches-your-role"></a>Power BI와 사용자 역할을 일치시키는 방법
Power BI 사용 방법은 프로젝트 또는 팀에서 사용자의 역할에 따라 달라질 수 있습니다. 또한 다른 역할을 맡은 사람은 Power BI를 다른 방식으로 사용할 수도 있습니다.

예를 들어 여러분은 주로 **Power BI 서비스**를 사용하지만 많은 숫자를 다루는 비즈니스 보고서를 만드는 동료는 **Power BI Desktop**을 중점적으로 사용하고 여러분이 보는 Power BI 서비스에 Desktop 보고서를 게시할 수 있습니다. 영업을 담당하는 또 다른 동료는 주로 Power BI 전화 앱을 사용하여 자신의 영업 할당량에 대한 진행 상황을 모니터링하고 새로운 영업 리드에 대한 세부 정보를 확인할 수 있습니다.

개발자인 경우 Power BI API를 사용하여 데이터를 데이터 집합으로 푸시하거나 대시보드와 보고서를 사용자 지정 응용 프로그램에 포함할 수 있습니다. 새로운 시각적 개체에 대한 아이디어가 있나요? 직접 빌드하고 다른 사람과 공유합니다.  

달성하려는 목표 또는 지정된 프로젝트나 작업에서 맡은 역할에 따라 **Power BI**의 각 요소를 서로 다른 시점에 사용할 수 있습니다.

여러분은 실시간 대시보드에서 재고 및 제조 진행 상황을 보고 **Power BI Desktop**을 사용하여 팀을 위해 고객 참여 통계에 대한 보고서를 만들 수 있습니다. Power BI를 사용하는 방법은 상황에 가장 적합한 도구인 Power BI의 기능 또는 서비스를 기반으로 할 수 있지만 Power BI의 각 부분을 사용할 수 있으므로 매우 유연하고 매력적입니다.

## <a name="the-flow-of-work-in-power-bi"></a>Power BI의 작업 흐름
Power BI의 일반적인 작업 흐름은 먼저 데이터 원본에 연결하고 **Power BI Desktop**에서 보고서를 빌드합니다. 그런 다음, 해당 보고서 **Desktop**에서 **Power BI 서비스**로 게시되고 **서비스** 및 **모바일**의 사용자가 보고서를 ‘사용’(보기 및 조작)할 수 있도록 공유됩니다.
때때로 자신과 유사한 권한(‘작성자’ 권한)을 동료에게 부여하여 동료가 **서비스**를 사용하여 보고서를 편집하고 대시보드를 만들고 작업을 공유하게 할 수도 있습니다.

이 작업은 일반적인 워크플로 중 하나이나 항상 이 방식으로 수행되는 것은 아니고 세 가지 기본 Power BI 요소가 서로를 어떻게 보완하는지 보여줍니다.

그러나 클라우드로 이동할 준비가 되지 않았는데 보고서를 회사 방화벽 뒤에서 유지하려 한다면 어떻게 될까요?  계속 읽어보세요.

## <a name="on-premises-reporting-with-power-bi-report-server"></a>Power BI Report Server를 사용하여 온-프레미스 보고
Power BI Report Server에서 제공하는 즉시 사용할 도구와 서비스의 범위에서 Power BI, 모바일 및 페이지가 매겨진 온-프레미스 보고서를 만들고, 배포하고 관리합니다.

![온-프레미스에 대한 다이어그램](media/power-bi-overview/power-bi-report-server2.png)

Power BI Report Server는 방화벽 뒤에 배포한 다음, 웹 브라우저, 모바일 장치 또는 메일로 보는지에 관계없이 다양한 방법으로 적합한 사용자에게 보고서를 배달하는 솔루션입니다. 그리고 Power BI Report Server는 클라우드의 Power BI와 호환되므로 준비가 되면 클라우드로 이동할 수 있습니다.


