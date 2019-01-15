---
title: Power BI 질문 및 답변 시작
description: Power BI 서비스에서 소매점 분석 샘플을 사용하여 질문 및 답변을 시작합니다.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 11/21/2018
ms.author: maggies
LocalizationGroup: Ask questions of your data
ms.openlocfilehash: 87783b928fdec1cadf5318ae184858c37daa4acc
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2019
ms.locfileid: "54279254"
---
# <a name="get-started-with-power-bi-qa"></a>Power BI 질문 및 답변 시작

경우에 따라 자연어를 사용하여 질문을 하면 가장 빠르게 사용자 데이터로 답변을 받을 수 있습니다.  이 빠른 시작에서는 동일한 시각화를 만드는 두 가지 방법(첫 번째는 보고서로 빌드하고 두 번째는 Q&A에서 질문)을 살펴봅니다. Power BI 서비스를 사용할 예정이지만, 프로세스는 Power BI Desktop을 사용할 때와 거의 동일합니다.

단계를 따르려면 편집할 수 있는 보고서를 사용해야 하므로 Power BI에 제공되는 샘플 중 하나를 사용하겠습니다.

## <a name="create-a-visual-in-the-report-editor"></a>보고서 편집기에서 시각적 개체 만들기

1. Power BI 작업 영역에서 **데이터 가져오기** \> **샘플** \> **소매 분석 샘플** > **연결**을 선택하세요.
   
2. 대시보드에는 "Last Year Sales and This Year Sales"에 대한 영역 차트 타일이 포함되어 있습니다.  이 타일을 선택합니다. 이 타일이 질문 및 답변으로 생성된 경우 타일을 선택하면 질문 및 답변이 열립니다. 하지만 이 타일은 보고서에서 생성되었으므로 이 시각화를 포함하는 페이지에 열립니다.

    ![소매점 분석 샘플 대시보드](media/power-bi-visualization-introduction-to-q-and-a/power-bi-dashboard.png)

1. **보고서 편집**을 선택하여 편집용 보기에서 보고서를 엽니다.  보고서의 소유자가 아닌 경우 편집용 보기에서 보고서를 여는 옵션이 없습니다.
   
    ![보고서 편집 단추](media/power-bi-visualization-introduction-to-q-and-a/power-bi-edit-report.png)
4. 영역형 차트를 선택하고 **필드** 창의 설정을 검토합니다.  보고서 작성자는 세 가지 값(**시간 > 회계 월**, **영업 > 올해 판매액**, **영업 >지난해 판매액 >값**)을 선택하고 **축** 및 **값** 웰에서 구성하여 이 차트를 작성했습니다.
   
    ![시각화 창](media/power-bi-visualization-introduction-to-q-and-a/gnatutorial_3-new.png)

## <a name="create-the-same-visual-with-qa"></a>Q&A를 통해 동일한 시각적 개체 만들기

질문 및 답변을 사용하여 이와 동일한 꺾은선형 차트를 만들려면 어떻게 해야 합니까?

![질문하기 상자](media/power-bi-visualization-introduction-to-q-and-a/power-bi-qna.png)

1. 소매점 분석 샘플 대시보드로 다시 이동합니다.
2. 자연어를 사용하여 다음과 같은 질문을 질문상자에 입력합니다.
   
   **월별 올해 판매 및 작년 판매를 영역 차트로 표시**
   
   질문을 입력하면 질문 및 답변에서 답변을 표시하는 데 가장 적합한 시각화를 선택합니다. 그러면 질문을 수정할 때 시각화가 동적으로 변경됩니다. 또한 Q&A를 사용하면 제안, 자동 완성 및 맞춤법 수정을 통해 질문에 서식을 지정할 수 있습니다.
   
   질문 입력을 완료하면 보고서에서 본 것과 똑같은 차트가 생성됩니다.  하지만 이러한 방식으로 만들면 훨씬 더 빠릅니다!
   
   ![질문 예제](media/power-bi-visualization-introduction-to-q-and-a/powerbi-qna-areachart.png)
3. 보고서 작업과 마찬가지로 Q&A 내에 시각화, 필터 및 필드 창에 대한 액세스 권한이 있습니다.  추가로 탐색하고 시각적 개체를 수정하려면 이들 창을 엽니다.
4. 대시보드로 차트를 고정하려면 고정 아이콘을 선택합니다. ![고정 아이콘](media/power-bi-visualization-introduction-to-q-and-a/pinnooutline.png).

## <a name="next-steps"></a>다음 단계
[Power BI의 질문 및 답변](consumer/end-user-q-and-a.md)

[Power BI의 질문 및 답변에서 데이터가 잘 작동하도록 설정](service-prepare-data-for-q-and-a.md)

궁금한 점이 더 있나요? [Power BI 커뮤니티를 이용하세요.](http://community.powerbi.com/)

