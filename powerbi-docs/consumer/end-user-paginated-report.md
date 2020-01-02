---
title: Power BI 서비스의 페이지를 매긴 보고서
description: 페이지를 매긴 보고서에 대해 설명하고 Power BI 서비스에서 페이지를 매긴 보고서를 보는 방법을 안내하는 설명서
author: mihart
ms.reviewer: chris finlan
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 12/02/2019
ms.author: mihart
LocalizationGroup: Common tasks
ms.openlocfilehash: a66189707bc6b688be012eeb59881ce4a8517ea1
ms.sourcegitcommit: e492895259aa39960063f9b337a144a60c20125a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74830482"
---
# <a name="paginated-reports-in-the-power-bi-service"></a>Power BI 서비스의 페이지를 매긴 보고서
지금까지 [Power BI 보고서](end-user-reports.md)에 대해 알아보았습니다. Power BI 보고서는 사용자가 가장 자주 사용하게 되는 유형의 보고서입니다. 이 외에도 *페이지를 매긴 보고서*라는 유형의 보고서가 있습니다. 보고서 *디자이너*가 프리미엄 용량 작업 영역에서 또는 이 작업 영역에 있는 앱에서 사용자에게 페이지를 매긴 보고서를 공유하는 경우가 있습니다. 

## <a name="what-is-a-paginated-report"></a>페이지를 매긴 보고서란?

이러한 보고서를 *‘페이지를 매긴’* 보고서라고 하는 이유는 인쇄된 페이지에 잘 맞춰지도록 서식이 지정되었기 때문입니다. 페이지를 매긴 보고서는 테이블이 여러 페이지에 걸쳐 나타나는 경우에도 테이블의 모든 데이터가 표시된다는 장점이 있습니다. 페이지를 매긴 보고서는 보고서 *디자이너*가 보고서 페이지 레이아웃을 정확하게 제어할 수 있기 때문에 이러한 보고서를 “픽셀 수준까지 완벽하다”라고도 합니다.

보고서 *디자이너*가 페이지를 매긴 보고서를 만든다는 것은 실제로는 *보고서 정의*를 만든다는 것과 같습니다. 보고서 정의는 데이터를 포함하지 않습니다. 데이터를 가져올 위치, 가져올 데이터 및 데이터 표시 방법을 지정합니다. 보고서를 실행하면 보고서 처리기가 보고서 정의를 받아서 데이터를 가져오고 이를 보고서 레이아웃과 결합하여 보고서를 생성합니다. 보고서가 기본 데이터를 표시하는 경우도 있고 보고서가 데이터를 표시하려면 사용자가 먼저 매개 변수를 입력해야 하는 경우도 있습니다. 

   ![보고서의 매개 변수](./media/end-user-paginated-report/power-bi-report-parameters.png)

이처럼 매개 변수를 설정하는 것이 페이지를 매긴 보고서에서 요구되는 상호 작용의 범위입니다. 청구 분석가는 페이지를 매긴 보고서를 사용하여 청구서를 만들거나 인쇄할 수 있습니다. 판매 관리자는 페이지를 매긴 보고서를 사용하여 매장이나 판매원을 기준으로 주문을 확인할 수 있습니다. 

아래의 간단한 페이지를 매긴 보고서는 사용자가 **Year**(연도) 매개 변수를 선택하면 해당 연도의 이익을 표시합니다. 

![1개의 매개 변수가 있는 간단한 보고서](./media/end-user-paginated-report/power-bi-report-simple.png)

페이지를 매신 보고서와 비교해 보면 Power BI 보고서는 훨씬 더 많은 상호 작용이 수반됩니다. Power BI 보고서는 임시 보고를 지원하며, 사용자 지정 시각적 개체를 비롯해 훨씬 더 많은 유형의 시각적 개체를 지원합니다.

## <a name="identify-a-paginated-report"></a>페이지를 매긴 보고서 식별하기

콘텐츠 목록과 홈 시작 페이지에서는 아이콘 ![페이지를 매긴 보고서 아이콘](media/end-user-paginated-report/power-bi-report-icon.png)을 보고 페이지를 매긴 보고서를 식별할 수 있습니다.  페이지를 매긴 보고서는 사용자에게 직접 공유될 수도 있고 [Power BI 앱](end-user-apps.md)의 일부로 공유될 수도 있습니다. 보고서 *디자이너*가 권한을 부여한 경우, 페이지를 매긴 보고서를 다시 공유하고 본인과 다른 사용자가 구독하도록 할 수 있습니다.

![여러 아이콘이 표시된 보고서 목록](./media/end-user-paginated-report/power-bi-report-list.png)

## <a name="interact-with-a-paginated-report"></a>페이지를 매긴 보고서에서 상호 작용하기

페이지를 매긴 보고서에서 상호 작용하는 방법은 다른 보고서와 다릅니다. 인쇄, 책갈피 추가, 내보내기, 메모 달기 등을 할 수 있지만, 여타 보고서보다 상호 작용의 정도가 훨씬 작습니다. 페이지를 매긴 보고서에서는 사용자가 보고서 캔버스를 채우도록 요구하는 경우가 많습니다.  보고서에 기본 데이터가 표시되며 사용자가 매개 변수를 입력하면 다른 데이터를 볼 수 있는 경우도 있습니다.

### <a name="print-a-paginated-report"></a>페이지를 매긴 보고서 인쇄하기

*페이지를 매긴* 보고서는 페이지에 잘 맞도록, 제대로 잘 인쇄되도록 서식이 지정되어 있습니다. 브라우저에서 보는 모습을 그대로 인쇄본에서도 볼 수 있습니다. 길이가 긴 테이블이 여러 페이지에 걸쳐 있는 경우에도 테이블 전체가 인쇄됩니다. 

페이지를 매긴 보고서에는 여러 페이지가 있을 수 있습니다. 예를 들어 이 보고서에는 563페이지가 있습니다. 각 페이지는 청구서당 한 페이지가 정확하게 배치되고 머리글과 바닥글이 반복됩니다. 아래 보고서를 인쇄하면 청구서와 청구서 사이에 페이지 나누기가 삽입됩니다.

   ![Tailspin Toys의 페이지를 매긴 보고서 중 1페이지](./media/end-user-paginated-report/power-bi-paginated-500.png)


### <a name="navigate-the-paginated-report"></a>페이지를 매긴 보고서 탐색하기

아래 판매 주문 보고서에는 Business type(비즈니스 유형), Reseller(재판매인), Order number(주문 번호)라는 3개의 매개 변수가 있습니다. 

![3개의 매개 변수가 있는 보고서](./media/end-user-paginated-report/power-bi-parameter.png)

표시되는 정보를 변경하려면 3개의 매개 변수에 다른 값을 입력하고 **보고서 보기**를 선택합니다. 여기서는 **Specialty bike shop**(전문 자전거 상점), **Alpine Ski House**(알파인 스키하우스), 주문 번호 **SO46085**를 선택했습니다. **보고서 보기**를 선택하면 보고서 캔버스가 새로운 판매 주문으로 새로 고침됩니다.

![매개 변수 변경](./media/end-user-paginated-report/power-bi-order.png)

앞에서 선택한 매개 변수를 바탕으로 새로운 판매 주문이 표시됩니다. 

![새로운 판매 주문](./media/end-user-paginated-report/power-bi-new-order.png)

페이지가 여러 개인 페이지를 매긴 보고서도 있습니다.  페이지 컨트롤을 사용하여 보고서를 탐색합니다. 

![페이지 컨트롤](./media/end-user-paginated-report/power-bi-page.png)

### <a name="export-the-paginated-report"></a>페이지를 매긴 보고서 내보내기
페이지를 매긴 보고서는 PDF, Word, XML, PowerPoint, Excel과 같은 다양한 형식으로 내보낼 수 있습니다. 보고서를 내보낼 때는 서식의 되도록 많은 부분이 그대로 유지됩니다. Excel, Word, PowerPoint, MHTML, PDF로 내보내진 페이지를 매긴 보고서는 “픽셀 수준까지 완벽한” 서식을 유지합니다. 

![새로운 판매 주문](./media/end-user-paginated-report/power-bi-exporting.png)

![4가지 내보내기 유형](./media/end-user-paginated-report/power-bi-four.png)

### <a name="subscribe-to-the-paginated-report"></a>페이지를 매긴 보고서 구독하기
페이지를 매긴 보고서를 구독하면 Power BI에서 보고서가 파일로 첨부된 메일이 발송됩니다. 구독을 설정할 때 매일, 매주, 매시간, 매월 중에서 메일을 받아 볼 빈도를 선택할 수 있습니다. 구독은 전체 보고서 출력을 최대 25MB까지 첨부 파일로 포함합니다. 전체 보고서를 내보내거나 미리 매개 변수를 선택할 수 있습니다. Excel, PDF, PowerPoint와 같은 여러 첨부 파일 유형을 선택할 수 있습니다.  

![구독 형식](./media/end-user-paginated-report/power-bi-export-list.png)

## <a name="considerations-and-troubleshooting"></a>고려 사항 및 문제 해결

- 페이지를 매긴 보고서는 사용자가 매개 변수를 선택하고 **보고서 보기**를 선택하기 전까지 빈 상태로 표시될 수 있습니다.

- 페이지를 매긴 보고서가 없다면 나에게 페이지를 매긴 보고서를 공유한 사람이 없기 때문일 수 있습니다. 또는 내가 페이지를 매긴 보고서를 볼 수 있도록 시스템 관리자가 설정하지 않았기 때문일 수도 있습니다. 

 

## <a name="next-steps"></a>다음 단계
- [Power BI 보고서](end-user-reports.md)
- 궁금한 점이 더 있나요? [Power BI 커뮤니티](https://community.powerbi.com/)를 사용해 보세요.

