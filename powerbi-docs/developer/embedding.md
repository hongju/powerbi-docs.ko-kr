---
title: "Power BI에 포함"
description: "Power BI는 대시보드 및 보고서를 응용 프로그램에 포함하기 위한 API를 제공합니다."
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
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/05/2017
ms.author: asaxton
ms.openlocfilehash: 36eb4231b6b3d3278d571722bde731051ffdf05e
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2017
---
# <a name="embedding-with-power-bi"></a>Power BI에 포함
Power BI는 대시보드 및 보고서를 응용 프로그램에 포함하기 위한 API를 제공합니다. 또한 콘텐츠를 포함할 경우 일관된 기능은 물론, 대시보드, 게이트웨이 및 앱 작업 영역과 같은 최신 Power BI 기능에 액세스 권한을 제공합니다.

## <a name="a-single-api"></a>단일 API
Power BI 콘텐츠를 포함할 때 두 가지 주요 시나리오가 있습니다. 조직에 대한 콘텐츠를 포함하는 경우 및 고객에 대한 콘텐츠를 포함하는 경우입니다. 두 시나리오 모두에 Power BI REST API를 사용할 수 있습니다. 그러면 조직 또는 고객에게 제공하기 위해 동일한 API를 사용하여 대시보드 및 보고서를 사용자 지정 응용 프로그램에 포함할 수 있습니다. 포함 필요에 따라 JavaScript 및 REST API를 완벽하게 활용할 수 있습니다.

포함 작동 방법의 예제를 보려면 [JavaScript 포함 샘플](https://microsoft.github.io/PowerBI-JavaScript/demo/)을 참조하세요.

## <a name="embedding-for-your-organization"></a>조직에 대한 콘텐츠 포함
조직에 대한 콘텐츠를 포함하면 Power BI 서비스를 확장할 수 있습니다. 이 경우에는 콘텐츠를 보려고 할 때 응용 프로그램의 최종 사용자가 Power BI 서비스에 로그인해야 합니다. 조직의 사용자가 로그인하면 Power BI 서비스에서 공유된 대시보드 및 보고서에 대한 액세스 권한만을 갖습니다. 

*조직에 대한 콘텐츠가 포함된 예로 내부 웹 응용 프로그램, SharePoint Online 웹 파트 및 Microsoft 팀 통합을 들 수 있습니다.*

조직에 대한 콘텐츠를 포함하는 경우 다음 항목을 참조하세요.

* [대시보드를 응용 프로그램에 통합](integrate-dashboard.md)
* [타일을 앱에 통합](integrate-tile.md)
* [보고서를 앱에 통합](integrate-report.md)

편집, 저장 등과 같은 셀프 서비스 기능은 Power BI 사용자에 대해 포함하는 경우 [JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript)를 통해 사용할 수 있습니다.

## <a name="embedding-for-your-customers"></a>고객에 대한 콘텐츠 포함
고객에 대한 콘텐츠를 포함하면 Power BI에 대한 계정이 없는 사용자에게 대시보드 및 보고서를 포함하는 기능을 제공합니다. 고객은 Power BI에 대해 알 필요가 없습니다. 하나 이상의 Power BI Pro 계정이 필요합니다. Power BI Pro 계정은 응용 프로그램에 대한 마스터 계정처럼 작동합니다. 이것을 프록시 계정으로 간주합니다. 또한 Power BI Pro 계정을 사용하면 Power BI 서비스 내에서 대시보드 및 보고서에 대한 액세스를 제공하는 embed 토큰을 생성할 수 있습니다. 

*고객에 대한 콘텐츠를 포함하는 예로 다른 회사에 판매되는 ISV 응용 프로그램을 들 수 있습니다.*

![고객에 대한 콘텐츠를 포함하는 워크플로 포함](media/embedding/powerbi-embed-flow.png)

대시보드, 보고서 및 타일을 포함하려면 조직에 대한 콘텐츠를 포함하기 위해 사용하는 동일한 API를 사용합니다.

> [!IMPORTANT]
> 포함 작업이 Power BI 서비스에 종속되는 반면 고객의 Power BI에 대해 종속되지는 않습니다. 응용 프로그램에 임베드된 콘텐츠를 보기 위해 Power BI에 가입할 필요는 없습니다.
> 
> 

프로덕션으로 이동할 준비가 되면 앱 작업 영역은 용량에 할당되어야 합니다. Microsoft Azure 내에서 Power BI Embedded는 응용 프로그램에서 사용할 용량을 제공합니다.

포함하는 방법에 대한 자세한 내용은 [Power BI 대시보드, 보고서 및 타일을 포함하는 방법](embedding-content.md)을 참조하세요.

Azure 안에서 Power BI 작업 영역 컬렉션 서비스를 사용한 경우 콘텐츠 마이그레이션 방법은 [Power BI 작업 영역 컬렉션 Azure 서비스에서 콘텐츠 마이그레이션](migrate-from-powerbi-embedded.md)을 참조하세요.

## <a name="next-steps"></a>다음 단계
[Power BI 대시보드, 보고서 및 타일을 포함하는 방법](embedding-content.md)  
[Power BI Embedded 작업 영역 컬렉션 콘텐츠를 Power BI으로 마이그레이션하는 방법](migrate-from-powerbi-embedded.md)  
[Power BI 프리미엄이란?](../service-premium.md)  
[JavaScript API Git 리포지토리](https://github.com/Microsoft/PowerBI-JavaScript)  
[Power BI C# Git 리포지토리](https://github.com/Microsoft/PowerBI-CSharp)  
[JavaScript 포함 샘플](https://microsoft.github.io/PowerBI-JavaScript/demo/)  
[포함된 분석 용량 계획 백서](https://aka.ms/pbiewhitepaper)  
[Power BI 프리미엄 백서](https://aka.ms/pbipremiumwhitepaper)  

궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](http://community.powerbi.com/)

