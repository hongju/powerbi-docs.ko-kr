---
title: Power BI API로 무엇을 할 수 있나요?
description: Power BI API로 무엇을 할 수 있나요?
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 03/25/2019
ms.openlocfilehash: bbca4e5bf52ee0d4674cfcdc28edd53e90033a98
ms.sourcegitcommit: 6272c4a0f267708ca7d38a45774f3bedd680f2d6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/06/2020
ms.locfileid: "74265216"
---
# <a name="what-can-developers-do-with-the-power-bi-api"></a>개발자는 Power BI API로 무엇을 할 수 있나요?

Power BI REST API를 사용하여 Power BI 보고서, 대시보드 및 타일과 통합된 앱을 만들 수 있습니다.

Power BI REST API를 사용하면 보고서, 데이터 세트 및 작업 영역과 같은 Power BI 개체에서 관리 작업을 수행할 수 있습니다.

다음은 Power BI API로 수행할 수 있는 몇 가지 작업입니다.

| **자세히 알아보려면** | **이 정보를 참조하세요.** |
|----------------------------------------------------------------------------------|------------------------------------------------------------------------------------|
| Power BI 사용자 및 Power BI 비사용자를 위한 보고서, 대시보드 및 타일을 포함합니다. | [Power BI 대시보드, 보고서 및 타일을 포함하는 방법](embedding-content.md) |
| Power BI 개체에서 관리 작업을 수행합니다. | [Power BI REST API 참조](https://docs.microsoft.com/rest/api/power-bi/) |
| 기존 비즈니스 워크플로를 확장하여 키 데이터를 Power BI 대시보드에 푸시 | [대시보드에 데이터 푸시 ](walkthrough-push-data.md) |
| Power BI에 인증. | [Power BI에 인증 ](get-azuread-access-token.md) |

> [!NOTE]
> Power BI API는 계속해서 작업 영역을 그룹으로 참조합니다. 그룹 참조는 작업 영역에서 작업 중임을 나타냅니다.

## <a name="api-developer-tools"></a>API 개발자 도구

| 도구 | 설명 |  |  |
|-------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------|---|---|
| [플레이그라운드 도구](https://microsoft.github.io/PowerBI-JavaScript/demo) | Power BI JavaScript API를 사용하는 전체 예제를 사용해보세요. 이 도구로 다양한 유형의 Power BI Embedded 샘플을 빠르게 재생할 수도 있습니다. |  |  |
| [Power BI JavaScript wiki](https://github.com/Microsoft/powerbi-javascript/wiki) | Power BI JavaScript API에 대한 자세한 내용을 알아보려면 |  |  |
| [Postman](https://www.getpostman.com/) | 요청을 실행하고, 테스트하고, 디버그하고, 모니터링하고, 자동화된 테스트 등을 실행합니다. |

## <a name="push-data-into-power-bi"></a>Power BI로 데이터 푸시

Power BI API를 사용하여 [데이터를 데이터 세트에 푸시](walkthrough-push-data.md)할 수 있습니다. 이 기능을 사용하여 데이터 세트 내 테이블에 행을 추가할 수 있습니다. 그러면 새 데이터가 대시보드의 타일과 보고서 내 시각적 개체에 반영됩니다.

![데이터 푸시 샘플](media/what-can-you-do/powerbi-push-data.png)

## <a name="github-repositories"></a>GitHub 리포지토리

* [Power BI 개발자 샘플](https://github.com/Microsoft/PowerBI-Developer-Samples)
* [.NET SDK](https://github.com/Microsoft/PowerBI-CSharp)
* [JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript)

## <a name="next-steps"></a>다음 단계

* [데이터 세트에 데이터 푸시](walkthrough-push-data.md)
* [Power BI 사용자 지정 시각적 개체 개발](visuals/custom-visual-develop-tutorial.md)
* [Power BI REST API 참조](rest-api-reference.md)
* [Power BI REST API](https://docs.microsoft.com/rest/api/power-bi/)

궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](https://community.powerbi.com/)
