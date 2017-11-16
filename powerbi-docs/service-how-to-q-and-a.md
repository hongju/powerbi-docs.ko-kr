---
title: "Power BI 사용 방법 질문 및 답변"
description: "Power BI 사용 방법 질문 및 답변"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
editor: 
tags: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 09/25/2017
ms.author: mihart
ms.openlocfilehash: a6736916a4bb2e94c1f5e1e3c3c3e5339cf990ec
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2017
---
# <a name="how-to-use-power-bi-qa"></a>Power BI 사용 방법 질문 및 답변
## <a name="ask-questions-of-your-data-using-natural-language"></a>자연어를 사용하여 데이터에 대해 질문하기
대시보드를 시작합니다. 질문 및 답변 상자에서 자연어로 질문을 입력할 수 있습니다. 질문 및 답변에서 사용자가 입력한 단어를 인식하고 답변이 있는 위치(데이터 집합)를 찾아냅니다. 또한 자동 완성, 재작성, 기타 텍스트 및 시각적 보조 기능으로 질문을 만들 수 있도록 지원합니다.

![](media/service-how-to-q-and-a/powerbi-qna.png)

질문에 대한 답변이 대화형 시각화로 표시되고 질문을 수정함에 따라 업데이트됩니다.

질문 및 답변은 대화형으로 재미도 있으며 시각화가 진행하는 흥미로운 경로를 표시함에 따라 대개 하나의 질문은 다른 항목으로 연결됩니다. Amanda가 Q&A를 사용하여 시각적 개체를 만들고 해당 시각적 개체를 보고 대시보드에 고정하는 과정을 시청합니다.

> [!NOTE]
> Q&A는 [iPads, iPhones, iPod Touch 장치에서 iOS용 Microsoft Power BI 앱](mobile-apps-ios-qna.md)에서도 사용할 수 있습니다.
> 
> 

<iframe width="560" height="315" src="https://www.youtube.com/embed/qMf7OLJfCz8?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

## <a name="use-natural-language-to-ask-questions-about-your-data"></a>자연어를 사용하여 데이터에 대해 질문하기
1. 질문 상자에 커서를 놓습니다. 입력을 시작하기 전에 질문 및 답변이 제안과 함께 새 화면을 표시하여 질문 형성을 돕습니다.
   
   ![](media/service-how-to-q-and-a/powerbi-qna-cursor.png)  
   
   이 목록에는 다음이 포함됩니다.  
   a.  대시보드에 이미 고정된 [타일](service-dashboard-tiles.md)을 만드는 데 사용된 질문과  
   b.  [기본 데이터 집합](service-get-data.md)에 있는 표 이름을 포함합니다.  
   
   시작 지점으로 항상 이러한 질문 중 하나를 선택하고 지속적으로 질문을 구체화하여 사용자가 찾고 있는 특정 대답을 찾을 수 있습니다. 또는 테이블 이름을 사용하여 새 질문을 입력할 수 있습니다.
2. 드롭다운 목록에서 선택하거나 직접 질문을 입력합니다.  
   
   ![](media/service-how-to-q-and-a/powerbi-qna-list.png)
3. 질문을 입력하면 Power BI 질문 및 답변에서 답변을 표시하는 데 가장 적합한 [시각화](power-bi-visualization-types-for-reports-and-q-and-a.md)를 선택합니다. 그러면 질문을 수정할 때 시각화가 동적으로 변경됩니다. 또한 자동 완성, 질문 재작성, 기타 텍스트 및 시각적 보조 기능으로 질문을 만들 수 있도록 지원합니다.  
   ![](media/service-how-to-q-and-a/powerbi-qna-viz.png)
4. 쿼리를 입력하면 Power BI는 해당 대시보드에 타일이 있는 데이터 집합에서 답변을 찾습니다.  모든 타일이 datasetA 에 있는 경우 답변은 datasetA 에서 제공됩니다.  타일이 *datasetA* 및 *datasetB* 에 있는 경우 질문 및 답변은 이러한 두 데이터 집합에서 가장 적합한 답변을 검색합니다.
   
   > [!TIP]
   > *datasetA* 에 타일이 하나만 있는 경우 대시보드에서 제거하면 질문 및 답변에서 datasetA 에 더 이상 액세스할 수 없으므로 주의해야 합니다.
   > 
   > 
5. 결과에 만족했으면 오른쪽 상단에 있는 고정 아이콘을 선택하여 [시각화를 대시보드에 고정](service-dashboard-pin-tile-from-q-and-a.md)합니다. 대시보드를 사용자와 공유하거나 앱의 일부인 경우 고정할 수 없습니다.
   
   ![](media/service-how-to-q-and-a/pbi_qna_finish-typing-question.jpg)

### <a name="tell-qa-which-visualization-to-use"></a>질문 및 답변에 사용할 시각화 알리기.
질문 및 답변으로 데이터에 자체적으로 알릴 수 있도록 할 뿐만 아니라 어떻게 표시할지까지도 알릴 수 있습니다. 질문 끝에 "<visualization type>으로"를 추가하기만 하면 됩니다.  예를 들어 "show inventory volume by plant as a map" 및 "show total inventory as a card"를 입력합니다.  직접 시도해 봅니다.

## <a name="how-does-qa-know-how-to-answer-questions"></a>질문 및 답변에서 질문에 답변하는 방법을 어떻게 알 수 있나요?
### <a name="which-datasets-does-qa-use"></a>질문 및 답변에서 어떤 데이터 집합을 사용하나요?
질문 및 답변에서 데이터 관련 질문에 답변하는 방법을 어떻게 알 수 있나요? 질문 및 답변에서는 기본 데이터 집합의 테이블, 열 및 계산된 필드 이름을 사용합니다. 따라서 사용자(또는 데이터 집합 소유자)가 어떤 것을 호출하는지가 중요합니다. 

예를 들어, "Product", "Month", "Units Sold", "Gross Sales" 및 "Profit"이라는 열이 있는 "Sales"라는 Excel 테이블이 있다고 가정합니다. 이러한 엔터티에 대해 질문을 할 수 있습니다.  "판매액 표시", "월별 총수익" , "판매된 단위별 제품 정렬" 등으로 질문할 수 있습니다.

질문 및 답변에서는 데이터 집합이 구성되는 방식을 기반으로 질문에 대답할 수 있습니다. Salesforce에서는 데이터에 대해 어떻게 작동하나요? salesforce.com 계정에 연결하면 Power BI가 대시보드를 자동으로 생성합니다.  질문 및 답변으로 질문을 시작하기 전에 대시보드 시각화에 표시되는 데이터와 질문 및 답변 드롭다운에 표시되는 데이터를 확인합니다.

* 시각화 축 레이블과 값에 "sales", "account", "month" 및 "opportunities"가 포함되는 경우 "Which *account* has the highest *opportunity* 또는 show *sales* by month as a bar chart"와 같은 질문을 자신 있게 할 수 있습니다.
* 드롭다운에 "salesperson", "state" 및 "year"를 포함하는 경우 "which *salesperson* had the lowest *sales* in *Florida* in *2013*"과 같은 질문을 자신 있게 할 수 있습니다.

Google 분석의 웹 사이트 성능 데이터가 있는 경우 웹 페이지에 소요된 시간, 페이지 순 방문 수 및 사용자 참여율에 대한 질문 및 답변을 할 수 있습니다. 또는 인구 통계 데이터를 쿼리하는 경우 지역별 연령 및 가구 소득에 대한 질문을 할 수 있습니다.

### <a name="which-visualization-does-qa-use"></a>질문 및 답변에서 사용하는 시각화는 무엇인가요?
질문 및 답변에서는 표시되는 데이터를 기반으로 최적의 시각화를 선택합니다. 경우에 따라 기본 데이터 집합의 데이터가 특정 형식 또는 범주로 정의되며 이렇게 하면 질문 및 답변에서 데이터를 표시하는 방법을 알리는 데 도움이 됩니다. 예를 들어 데이터가 날짜 형식으로 정의되는 경우 꺾은선형 차트로 표시될 가능성이 높습니다. 도시로 분류된 데이터는 지도로 표시될 가능성이 높습니다.

질문에 사용할 시각화를 추가하여 사용할 시각화를 알리는 방법도 있습니다. 하지만 질문 및 답변에서 항상 사용자가 요청한 시각화 유형으로 데이터를 표시할 수 있는 것은 아님을 유의해야 합니다.

질문 및 답변에서 인식하는 키워드에 대한 정보는 [질문하기 위한 팁](service-q-and-a-tips.md)을 참조하세요.

## <a name="next-steps"></a>다음 단계
[Power BI의 Q&A](service-q-and-a.md)로 돌아가기  
[자습서: 소매점 판매 샘플에서 질문 및 답변 사용](power-bi-visualization-introduction-to-q-and-a.md)  
[질문 및 답변에서 질문하기 위한 팁](service-q-and-a-tips.md)  
[질문 및 답변을 위한 통합 문서 준비](service-prepare-data-for-q-and-a.md)  
[Q&A에서 대시보드에 타일 고정](service-dashboard-pin-tile-from-q-and-a.md)  

