---
title: Power BI API로 무엇을 할 수 있나요?
description: Power BI API로 무엇을 할 수 있나요?
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 05/25/2018
ms.openlocfilehash: d8cad602b178dd55184e00e2a318c374433b1a46
ms.sourcegitcommit: 0abcbc7898463adfa6e50b348747256c4b94e360
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2019
ms.locfileid: "55762332"
---
# <a name="what-can-developers-do-with-the-power-bi-api"></a>개발자는 Power BI API로 무엇을 할 수 있나요?

Power BI는 대화형 대시보드를 표시하며 다양한 데이터 원본에서 실시간으로 만들어지고 업데이트됩니다. REST 호출을 지원하는 프로그래밍 언어를 사용하여 실시간으로 Power BI 대시보드와 통합되는 앱을 만들 수 있습니다. Power BI 타일 및 보고서를 앱에 통합할 수도 있습니다.

개발자는 대화형 보고서 및 대시보드에서 사용될 수 있는 자체 데이터 시각화를 빌드할 수도 있습니다.

다음은 Power BI API로 수행할 수 있는 몇 가지 작업입니다.

| **수행할 작업** | **이동 위치** |
| --- | --- |
| Power BI 사용자 및 비Power BI 사용자를 위한 대시보드, 보고서 및 타일 포함(앱 소유 데이터) |[Power BI 대시보드, 보고서 및 타일을 포함하는 방법](embedding-content.md) |
| 기존 비즈니스 워크플로를 확장하여 키 데이터를 Power BI 대시보드에 푸시 |[대시보드에 데이터 푸시](walkthrough-push-data.md) |
| Power BI에 인증. |[Power BI에 인증](get-azuread-access-token.md) |
| 사용자 지정 시각적 개체 만들기 |[Power BI 사용자 지정 시각적 개체 개발](custom-visual-develop-tutorial.md) |

> [!NOTE]
> Power BI API는 계속 그룹으로 앱 작업 영역을 참조합니다. 그룹에 대한 참조는 앱 작업 영역과 작업 중임을 의미합니다.

## <a name="power-bi-developer-samples"></a>Power BI 개발자 샘플

Power BI 개발자 샘플에는 대시보드, 보고서 및 타일 포함에 대한 항목이 포함됩니다.

[Power BI 개발자 샘플](https://github.com/Microsoft/PowerBI-Developer-Samples)

* **앱 소유 데이터** 내 샘플은 Power BI 비사용자에 포함되기 위한 것입니다.
* **사용자 소유 데이터** 내 샘플은 Power BI 사용자에 포함되기 위한 것입니다.

## <a name="github-repositories"></a>GitHub 리포지토리

* [.NET SDK](https://github.com/Microsoft/PowerBI-CSharp)
* [JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript)
* [사용자 지정 시각적 개체](https://github.com/Microsoft/PowerBI-visuals)

## <a name="developer-tools"></a>개발자 도구

다음은 Power BI 항목 개발에 도움이 되도록 사용할 수 있는 도구입니다.

[포함 설정 도구](https://aka.ms/embedsetup)를 통해 Power BI 콘텐츠를 포함하는 방법에 대한 샘플 애플리케이션을 신속하게 다운로드하여 시작할 수 있습니다.

사용자에게 적합한 솔루션을 선택합니다.

* [고객에 대한 콘텐츠를 포함하면](embedding.md#embedding-for-your-customers) Power BI에 대한 계정이 없는 사용자에게 대시보드 및 보고서를 포함하는 기능을 제공합니다. [고객에 대한 콘텐츠 포함](https://aka.ms/embedsetup/AppOwnsData) 솔루션을 실행합니다.

* [조직에 대한 콘텐츠를 포함하면](embedding.md#embedding-for-your-organization) Power BI 서비스를 확장할 수 있습니다. [조직에 대한 콘텐츠 포함](https://aka.ms/embedsetup/UserOwnsData) 솔루션을 실행합니다.

JavaScript API 사용에 대한 전체 샘플의 경우 [Playground 도구](https://microsoft.github.io/PowerBI-JavaScript/demo)를 사용할 수 있습니다. 이 도구로 다양한 유형의 Power BI Embedded 샘플을 빠르게 재생할 수 있습니다. [PowerBI-JavaScript Wiki](https://github.com/Microsoft/powerbi-javascript/wiki) 페이지를 방문하여 JavaScript API에 대한 추가 정보를 얻을 수도 있습니다.

## <a name="push-data-into-power-bi"></a>Power BI로 데이터 푸시

Power BI API를 사용하여 데이터를 데이터 세트에 푸시할 수 있습니다. 이 기능을 사용하여 데이터 세트 내 테이블에 행을 추가할 수 있습니다. 그러면 새 데이터가 대시보드의 타일과 보고서 내 시각적 개체에 반영될 수 있습니다.

![데이터 푸시 샘플](media/what-can-you-do/powerbi-push-data.png)

## <a name="next-steps"></a>다음 단계

[데이터 세트에 데이터 푸시](walkthrough-push-data.md)  
[Power BI 사용자 지정 시각적 개체 개발](custom-visual-develop-tutorial.md)  
[Power BI REST API 참조](https://docs.microsoft.com/rest/api/power-bi/)  

궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](http://community.powerbi.com/)
