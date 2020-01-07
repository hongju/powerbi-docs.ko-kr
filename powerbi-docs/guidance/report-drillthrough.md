---
title: 보고서 페이지 드릴스루
description: 보고서 페이지 드릴스루 설명 가이드
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 11/28/2019
ms.author: v-pemyer
ms.openlocfilehash: b674c621c30491a00c529af7f2fcd9eb87f3ecfa
ms.sourcegitcommit: e492895259aa39960063f9b337a144a60c20125a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74834773"
---
# <a name="report-page-drillthrough"></a>보고서 페이지 드릴스루

이 문서에서는 독자가 Power BI 보고서를 디자인하는 보고서 작성자라고 가정하고, [보고서 페이지 드릴스루](../desktop-drillthrough.md)를 만들기 위한 제안 및 권장 사항을 제공합니다.

보고서 사용자가 다음과 같은 흐름을 달성할 수 있도록 보고서를 디자인하는 것이 좋습니다.

1. 보고서 페이지 보기.
2. 더 깊이 있게 분석할 수 있도록 시각적 개체 요소 식별하기.
3. 시각적 개체 요소를 마우스 오른쪽 단추로 클릭하여 드릴스루하기.
4. 무료 분석 수행하기.
5. 원본 보고서 페이지로 돌아가기.

## <a name="suggestions"></a>제안

두 가지 유형의 드릴스루 시나리오를 살펴보세요.

- [추가적인 깊이](#additional-depth)
- [보다 넓은 관점](#broader-perspective)

### <a name="additional-depth"></a>추가적인 깊이

보고서 페이지에 요약된 결과가 표시되는 경우, 드릴스루 페이지가 있으면 보고서 사용자가 트랜잭션 수준 세부 정보를 확인할 수 있습니다. 이와 같은 디자인 접근 방식은 사용자가 필요할 때만 관련 트랜잭션을 볼 수 있도록 해 줍니다.

다음 예에서는 보고서 사용자가 월간 판매량 요약에서 드릴스루하면 무슨 일이 일어나는지 보여 줍니다. 드릴스루 페이지는 특정 월의 상세한 주문 목록을 포함합니다.

![“Sales Summary”(판매량 요약)라는 행렬 시각적 개체가 행에 연도와 월을 기준으로 매출을 그룹화하고 열에 국가를 그룹화합니다. 드릴스루 페이지도 표시되어 있습니다.](media/report-drillthrough/suggestion-drillthrough-add-depth.png)

### <a name="broader-perspective"></a>보다 넓은 관점

드릴스루 페이지는 ‘추가적인 깊이’의 반대 효과를 달성합니다. 이 시나리오는 종합적인 보기를 드릴스루하는 데 좋습니다.

다음 예에서는 보고서 사용자가 우편 번호에서 드릴스루하면 무슨 일이 일어나는지 보여 줍니다. 드릴스루 페이지에는 이 우편 번호에 대한 일반적인 정보가 표시됩니다.

![테이블 시각적 개체에 Zip Code(우편 번호), Average of Violation Points(위반 요소 평균), Average of Grade Rating(등급 평균)이라는 3개의 열이 있습니다. 드릴스루 페이지도 표시되어 있습니다.](media/report-drillthrough/suggestion-drillthrough-broader-perspective.png)

## <a name="recommendations"></a>권장 사항

보고서를 디자인할 때는 다음과 같은 방식을 따르는 것이 권장됩니다.

- **스타일:** 드릴스루 페이지에 보고서와 동일한 테마와 스타일을 사용하는 것이 좋습니다. 이렇게 하면 사용자가 페이지 도구 설명을 보고 보고서와의 일관성을 느낄 수 있습니다.
- **드릴스루 필터:** 드릴스루 페이지를 디자인할 때 실제와 동일한 결과를 미리 보기로 볼 수 있도록 드릴스루 필터를 설정하세요. 보고서를 게시하기 전에 필터를 제거하는 것도 잊지 마세요.
- **추가 기능:** 드릴스루 페이지는 여타 보고서 페이지와 같습니다. 슬라이서, 필터와 같은 추가적인 대화형 기능으로 한층 강화할 수도 있습니다.
- **공백:** 공백을 표시하거나 드릴스루 필터가 적용되었을 때 오류를 생성할 수 있는 시각적 개체는 추가하지 마세요.
- **페이지 표시 유형:** 드릴스루 페이지는 숨기는 것이 좋습니다. 드릴스루 페이지를 표시된 상태로 유지하려는 경우에는 사용자가 이전에 설정된 드릴스루 필터를 지울 수 있는 단추도 적용하세요. 단추에 [책갈피](../desktop-bookmarks.md)를 할당하세요. 책갈피는 모든 필터를 제거하도록 구성되어야 합니다.
- **뒤로 단추:** 드릴스루 필터를 할당하면 뒤로 [단추](../desktop-buttons.md)가 자동으로 추가됩니다. 이 단추는 그대로 두는 것이 좋습니다. 이렇게 하면 보고서 사용자가 원본 페이지로 손쉽게 돌아갈 수 있습니다.
- **시인성:** 시각적 개체 헤더 아이콘 텍스트를 설정하거나 텍스트 상자에 지침을 추가하여 드릴스루 페이지의 시인성을 높이세요. [이 블로그 게시물](https://alluringbi.com/2019/10/23/overlays-for-true-self-serve-reporting/)에서 설명하는 것처럼 오버레이를 디자인할 수도 있습니다.

> [!TIP]
> Power BI 페이지를 매긴 보고서에 드릴스루를 구성할 수 있습니다. 이렇게 하려면 Power BI 보고서에 링크를 추가하면 됩니다. 링크는 [URL 매개 변수](/blog/url-parameters-for-paginated-reports-are-now-available/)를 정의할 수 있습니다.

## <a name="next-steps"></a>다음 단계

이 문서와 관련된 보다 자세한 내용을 알아보려면 다음 리소스를 참조하세요.

- [Power BI Desktop에서 드릴스루 사용](../desktop-drillthrough.md)
- Guy in a cube 비디오: [Drilling into drillthrough in Power BI Desktop](https://www.youtube.com/watch?v=2x9lLHDbtDk)(Power BI Desktop의 드릴스루 살펴보기)
- 궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](https://community.powerbi.com/)
