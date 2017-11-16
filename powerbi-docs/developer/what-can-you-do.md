---
title: "개발자는 Power BI로 무엇을 할 수 있나요?"
description: "Power BI는 개발자를 위한 다양한 옵션을 제공합니다. 여기에는 사용자 지정 시각적 개체에서 스트리밍 데이터 집합에 이르는 다양한 옵션이 포함됩니다."
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
ms.date: 07/20/2017
ms.author: asaxton
ms.openlocfilehash: a10cd93a06d14e3e66fd9cce480dc0ec99e67aeb
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2017
---
# <a name="what-can-developers-do-with-power-bi"></a>개발자는 Power BI로 무엇을 할 수 있나요?
Power BI는 개발자를 위한 다양한 옵션을 제공합니다. 여기에는 사용자 지정 시각적 개체에서 스트리밍 데이터 집합에 이르는 다양한 옵션이 포함됩니다.

## <a name="embedding"></a>포함
Power BI 서비스 및 Power BI Embedded in Azure는 함께 대시보드 및 보고서 임베드를 위한 단일 API를 제공합니다. 즉, 콘텐츠 임베드 시 단일 API 인터페이스, 일관된 성능은 물론, 대시보드, 게이트웨이 및 앱 작업 영역 등의 최신 Power BI 기능을 이용할 수 있습니다. 자세한 내용은 [Power BI에 포함](embedding.md)을 참조하세요.

![](media/what-can-you-do/powerbi-embed-sample.png)

## <a name="custom-visuals"></a>사용자 지정 시각적 개체
사용자 지정 시각적 개체를 사용하면 Power BI 보고서 안에서 사용되는 자체 시각적 개체를 만들 수 있습니다. 사용자 지정 시각적 개체는 더 많은 고급 기능과 ES6/ES7 기능에 대한 초기 액세스를 지원하는 JavaScript의 상위 집합인 TypeScript로 작성해야 합니다. 시각적 개체 스타일 지정은 CSS(Cascading Styles Sheet)로 처리됩니다. 편의상 중첩, 변수, mixin, 조건, 루프 등 몇 가지 고급 기능을 지원하는 Less 사전 컴파일러를 사용합니다. 이러한 기능 중 하나를 사용하지 않을 경우 더 소규모의 파일에 일반 CSS만 작성할 수 있습니다.

사용자 지정 시각적 개체의 개발 방법에 대한 자세한 내용은 [Office 스토어에 사용자 지정 시각적 개체 게시](office-store.md)를 참조하세요.

![](media/what-can-you-do/powerbi-custom-visual-store.png)

## <a name="push-data-into-power-bi"></a>Power BI로 데이터 푸시
Power BI API를 사용하여 데이터를 데이터 집합에 푸시할 수 있습니다. 이렇게 하면 데이터 집합 내 테이블에 행을 추가할 수 있습니다. 그러면 새 데이터가 대시보드의 타일과 보고서 내 시각적 개체에 반영될 수 있습니다.

자세한 내용은 [대시보드에 데이터 푸시](walkthrough-push-data.md)를 참조하세요.

## <a name="next-steps"></a>다음 단계
[Power BI에 포함](embedding.md)  
[Power BI Embedded 작업 영역 컬렉션 콘텐츠를 Power BI으로 마이그레이션하는 방법](migrate-from-powerbi-embedded.md)  
[JavaScript Git 리포지토리](https://github.com/Microsoft/PowerBI-JavaScript)  
[Power BI C# Git 리포지토리](https://github.com/Microsoft/PowerBI-CSharp)  
[사용자 지정 시각적 개체를 Office 스토어에 게시](office-store.md)  
[Power BI Visuals Git 리포지토리](https://github.com/Microsoft/PowerBI-visuals)  
[JavaScript 포함 샘플](https://microsoft.github.io/PowerBI-JavaScript/demo/)  
[Apiary의 Power BI API](http://docs.powerbi.apiary.io/#)  
[Power BI 프리미엄 백서](https://aka.ms/pbipremiumwhitepaper)  
궁금한 점이 더 있나요? [Power BI 커뮤니티를 이용하세요.](http://community.powerbi.com/)

