---
title: 개발자는 Power BI로 무엇을 할 수 있나요?
description: Power BI는 개발자를 위한 다양한 옵션을 제공합니다. 여기에는 사용자 지정 시각적 개체에서 스트리밍 데이터 집합에 이르는 다양한 옵션이 포함됩니다.
author: markingmyname
ms.author: maghan
ms.date: 05/03/2018
ms.topic: overview
ms.service: powerbi
ms.component: powerbi-developer
ms.custom: mvc
manager: kfile
ms.openlocfilehash: ee9f5b2e89a1746267090da3485076d67a99d6f9
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/17/2018
ms.locfileid: "34290571"
---
# <a name="what-can-developers-do-with-power-bi"></a>개발자는 Power BI로 무엇을 할 수 있나요?

개발자는 Power BI 콘텐츠를 응용 프로그램에 포함할 수 있는 다양한 옵션을 사용할 수 있습니다. 이러한 옵션에는 **Power BI에 포함**, **사용자 지정 시각적 개체** 및 **Power BI에 데이터 푸시**가 포함됩니다.

## <a name="embedding"></a>포함
Power BI 서비스(SaaS) 및 Azure의 Power BI Embedded(PaaS)에는 대시보드 및 보고서 포함을 위한 API가 있습니다. 즉, 일련의 기능은 물론, 콘텐츠 포함 시 대시보드, 게이트웨이 및 앱 작업 영역 등의 최신 Power BI 기능을 이용할 수 있습니다.

![PBIE 샘플](media/what-can-you-do/what-can-you-do-01.png)

## <a name="develop-custom-visuals"></a>사용자 지정 시각적 개체 개발
사용자 지정 시각적 개체를 사용하면 Power BI 보고서 안에서 사용되는 자체 시각적 개체를 만들 수 있습니다. 사용자 지정 시각적 개체는 JavaScript의 상위 집합인 TypeScript로 작성해야 합니다. TypeScript는 일부 고급 기능과 ES6/ES7 기능에 대한 초기 액세스를 지원합니다. 시각적 개체 스타일 지정은 CSS(Cascading Styles Sheet)로 처리됩니다. 편의상 중첩, 변수, 조건, 루프 등 몇 가지 고급 기능을 지원하는 Less 사전 컴파일러를 사용합니다. 이러한 기능 중 하나를 사용하지 않을 경우 더 소규모의 파일에 일반 CSS만 작성할 수 있습니다.

![CV 샘플](media/what-can-you-do/powerbi-custom-visual-store.png)

## <a name="push-data-into-power-bi"></a>Power BI로 데이터 푸시
Power BI API를 사용하여 데이터를 데이터 집합에 푸시할 수 있습니다. 이렇게 하면 데이터 집합 내 테이블에 행을 추가할 수 있습니다. 그러면 새 데이터가 대시보드의 타일과 보고서 내 시각적 개체에 반영될 수 있습니다.

![데이터 푸시 샘플](media/what-can-you-do/powerbi-push-data.png)

## <a name="next-steps"></a>다음 단계
[Power BI에 포함](embedding.md)  
[사용자 지정 시각적 개체를 Office 스토어에 게시](office-store.md)  
[대시보드에 데이터 푸시](walkthrough-push-data.md)
