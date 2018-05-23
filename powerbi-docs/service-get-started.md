---
title: Power BI 서비스 시작
description: Power BI 서비스 시작
author: adamw
manager: kfile
ms.reviewer: ''
featuredvideoid: B2vd4MQrz4M
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 03/01/2018
ms.author: mihart
LocalizationGroup: Get started
ms.openlocfilehash: d66653ebe9232cb6da2f3c53b01e791ca9966db9
ms.sourcegitcommit: dcde910817720c05880ffe24755034f916c9b890
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2018
---
# <a name="get-started-with-power-bi-service-apppowerbicom"></a>Power BI 서비스(app.powerbi.com) 시작
이 자습서는 ***Power BI 서비스***를 시작할 때 도움이 됩니다. Power BI 서비스를 다른 Power BI 제품에 적용하는 방법을 이해하려면 [Power BI란?](guided-learning/gettingstarted.yml?tutorial-step=1)을 참조하여 시작하는 것이 좋습니다.

![바탕 화면, 서비스, 모바일 간의 관계를 보여주는 아트](media/service-get-started/power-bi-components.png)

Power BI 서비스에는 무료 버전과 프로 버전에 있습니다. 사용 중인 버전에 관계없이 *계정이 이미 있는 경우* 브라우저를 열고 app.powerbi.com을 입력하여 Power BI 서비스를 엽니다. 새 사용자인 경우 대신 www.powerbi.com에서 시작하는 것이 좋습니다. 여기에서 서비스에 로그인하기 전에 Power BI에 대해 자세히 알아볼 수 있습니다.  사용할 준비가 되었으면 상단 오른쪽 모서리에 표시되는 **무료 가입** 링크를 선택합니다. 관리자가 사용자를 대신해 Power BI를 이미 활성화한 경우 무료 가입 단추를 사용하는 대신 app.powerbi.com으로 바로 이동하세요. 

![체험 등록 또는 로그인](media/service-get-started/power-bi-sign-up.png)

Power BI Desktop에 대한 도움말 찾고 있는 경우 [데스크톱 시작](desktop-getting-started.md)을 참조하세요. Power BI 모바일에 도움을 찾고 있는 경우 [모바일 장치에 대한 Power BI 앱](mobile-apps-for-mobile-devices.md)을 참조하세요.

> [!TIP]
> 대신 무료 자가 진행식 교육 과정을 더 선호합니까? [EdX에서 데이터 분석 및 시각화 코스에 등록](http://aka.ms/edxpbi)합니다.

[YouTube 재생 목록](https://www.youtube.com/playlist?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP)을 방문합니다. 시작하는 데 도움이 되는 유용한 비디오는 Power BI 서비스 소개입니다.
> 
> <iframe width="560" height="315" src="https://www.youtube.com/embed/B2vd4MQrz4M" frameborder="0" allowfullscreen></iframe>
> 
> 
> 

Microsoft Power BI는 중요한 정보를 최신 상태로 유지하는 데 도움이 됩니다.  Power BI 서비스를 사용하면 ***대시보드***를 통해 비즈니스의 실상을 잘 파악할 수 있습니다.  대시보드에는 클릭하여 ***보고서***를 열고 자세히 탐색할 수 있는 ***타일***이 표시됩니다.  여러 ***데이터 집합***에 연결하여 관련 데이터를 모두 한 곳으로 가져옵니다. Power BI의 구성 요소를 이해하는 데 도움이 필요한 경우  [Power BI - 기본 개념](service-basic-concepts.md)을 참조하세요.

Excel 또는 CSV 파일에 중요한 데이터가 있는 경우 Power BI 대시보드를 만들어 어디서나 최신 정보를 받고 다른 사람과 통찰력을 공유할 수 있습니다.  Salesforce와 같은 SaaS 응용 프로그램에 대한 구독이 있는 경우  먼저 Salesforce에 연결하여 해당 데이터에서 자동으로 대시보드를 생성하거나 [다른 모든 SaaS 앱을 체크 아웃](service-get-data.md)합니다. 조직의 일부인 경우 [앱](service-create-distribute-apps.md)이 자신에게 게시되었는지 확인합니다.

[Power BI에 대한 데이터를 가져오는](service-get-data.md) 다른 모든 방법에 대해 알아보세요.

## <a name="step-1-get-data"></a>1단계: 데이터 가져오기
다음은 CSV 파일에서 데이터를 가져오는 예제입니다. 이 자습서의 설명을 따라하려면 [이 샘플 CSV 파일을 다운로드](http://go.microsoft.com/fwlink/?LinkID=521962)하세요.

1. [Power BI에 로그인합니다](http://www.powerbi.com/). 계정이 없는 경우 무료로 등록할 수 있습니다.
2. Power BI는 브라우저에서 열립니다. 왼쪽 탐색 표시줄의 맨 아래에 있는 **데이터 가져오기**를 선택합니다.
   
   ![데이터 가져오기](media/service-get-started/getdata3.png)
3. **파일**을 선택합니다. 
   
   ![파일 가져오기](media/service-get-started/gs1.png)
4. 컴퓨터에서 파일을 찾은 다음 **열기**를 선택합니다. 비즈니스용 OneDrive에 저장한 경우 해당 옵션을 선택합니다. 로컬에 저장한 경우 **로컬 파일**을 선택합니다. 
   
   ![데이터 가져오기 > 파일 화면](media/service-get-started/gs2.png)
5. 이 자습서에서는 보고서 및 대시보드를 만드는 데 사용할 수 있게 Excel 파일을 데이터 집합으로 추가하기 위해 **가져오기**를 선택할 것입니다. **업로드**를 선택할 경우 전체 Excel 통합 문서가 Power BI에 업로드되어 Excel에서 온라인으로 열어 편집할 수 있습니다.
   
   ![가져오기 선택](media/service-get-started/power-bi-import.png)
6. 데이터 집합이 준비되면 **데이터 집합 보기**를 선택하여 보고서 편집기에서 엽니다. 

    ![데이터 집합이 준비되었습니다 대화 상자](media/service-get-started/power-bi-gs.png)

    아직 시각화를 만들지 않았기 때문에 보고서 캔버스는 비어 있을 것입니다.

    ![빈 보고서 캔버스](media/service-get-started/power-bi-report-editor.png)

6. 상단의 메뉴 모음을 살펴보고 **읽기용 보기**에 대한 옵션이 있는 것을 확인합니다. 읽기용 보기에 대한 옵션이 있다는 것은 현재 **편집용 보기**에 있다는 것입니다. 

    ![읽기용 보기 옵션](media/service-get-started/power-bi-editing-view.png)

    편집용 보기에 있을 때는 자신이 보고서의 *소유자*이고 *작성자*이므로 보고서를 만들고 수정할 수 있습니다. 동료와 보고서를 공유할 경우 동료는 *소비자*이므로 읽기용 보기에서 보고서와 상호 작용만 가능합니다. [읽기용 보기 및 편집용 보기](service-reading-view-and-editing-view.md)에 대해 자세히 알아보세요.
    
    [둘러보기](service-the-report-editor-take-a-tour.md)를 통해 보고서 편집기에 익숙해질 수 있습니다.
   > 
 

## <a name="step-2-start-exploring-your-dataset"></a>2단계: 데이터 집합 살펴보기 시작
데이터에 연결되었으므로 탐색을 시작합니다.  관심 있는 항목을 발견했다면 대시보드를 만들어 이를 모니터링하고 시간이 지남에 따라 어떻게 변경되는지 확인할 수 있습니다. 작동 원리를 살펴보겠습니다.
    
1. 보고서 편집기에서 페이지의 오른쪽에 있는 **필드** 창을 사용하여 시각화를 구축할 수 있습니다.  **총 판매량** 및 **날짜** 옆에 있는 확인란을 선택합니다.
   
   ![필드 목록](media/service-get-started/fields.png)

2. Power BI에서 데이터를 분석하고 시각적 개체를 만듭니다.  **날짜**를 먼저 선택한 경우에는 테이블이 표시되고,  **총 판매량**을 먼저 선택한 경우에는 차트가 표시됩니다. 데이터를 표시하는 다른 방법으로 전환합니다. 이 데이터를 꺾은선형 차트로 표시해 보겠습니다. **시각화 창**에서 꺾은선형 차트 아이콘(템플릿이라고도 함)을 선택합니다.
   
   ![아이콘이 선택된 보고서 편집기](media/service-get-started/gettingstart5new.png)

3. 흥미로워 보이므로 대시보드에 *고정*해 보겠습니다. 시각화를 마우스로 가리키고 **고정** 아이콘을 선택합니다.  이 시각화를 고정하면 대시보드에 저장되고 최신 상태로 유지되므로 최신 값을 한눈에 추적할 수 있습니다.
   
   ![고정 아이콘](media/service-get-started/pinnew.png)

5. 새 보고서이므로 먼저 저장해야 시각화를 대시보드에 고정할 수 있다는 메시지가 표시됩니다. 보고서에 이름(예: *기간별 매출*)을 지정하고 **저장 및 계속**을 선택합니다. 
   
   ![보고서 저장 대화 상자](media/service-get-started/pbi_getstartsaveb4pinnew.png)
   
6. 새 대시보드에 꺾은선형 차트를 고정하고 "자습서에 대한 재무 샘플"이라는 이름을 지정하겠습니다. 
   
   ![보고서 이름 지정](media/service-get-started/power-bi-pin.png)
   
 1. **고정**을 선택합니다.
   
    오른쪽 위에 나타나는 성공 메시지를 통해 시각화가 타일로 대시보드에 추가되었음을 알 수 있습니다.
   
    ![대시보드에 고정 대화 상자](media/service-get-started/power-bi-pin-success.png)

8. **대시보드로 이동**을 선택하여 꺾은선형 차트가 새 대시보드에 타일로 고정되었는지 확인합니다. 시각화 타일을 추가하고 [타일의 이름을 바꾸고, 크기를 조정하고, 연결하고, 위치를 변경](service-dashboard-edit-tile.md)하여 대시보드의 모양을 개선합니다.
   
   ![시각화가 고정된 대시보드](media/service-get-started/power-bi-new-dashboard.png)
   
   언제든지 대시보드에서 새 타일을 선택하여 보고서로 돌아갑니다. Power BI가 읽기용 보기에서 보고서 편집기로 돌아갑니다. 편집용 보기로 다시 전환하려면 상단 메뉴 모음에서 **보고서 편집**을 선택합니다. 편집용 보기로 전환되면 타일을 계속 탐색하고 고정합니다. 

## <a name="step-3--continue-the-exploration-with-qa-natural-language-querying"></a>3단계: 질문 및 답변 탐색 계속(자연어 쿼리)
1. 데이터의 빠른 탐색을 위해 질문 및 답변 상자에 질문을 합니다. 질문 및 답변의 질문 상자는 대시보드의 상단(**데이터에 대해 질문하기**) 및 보고서의 상단 메뉴 모음(**질문하기**)에 있습니다. 예를 들어 "어떤 세그먼트에서 가장 많은 수익을 냈나요"라고 입력해 보세요.
   
   ![질문 및 답변 캔버스](media/service-get-started/powerbi-qna.png)

2. 질문 및 답변에서 답변을 검색하고 시각화 형태로 제공합니다. 고정 아이콘 선택 ![고정 아이콘](media/service-get-started/pbi_pinicon.png) 이 시각화도 대시보드에 표시합니다.
3. 시각화를 "자습서용 재무 샘플" 대시보드에 고정합니다.
   
    ![대시보드에 고정 대화 상자](media/service-get-started/power-bi-pin2.png)

4. 대시보드로 돌아가면 새 타일이 표시됩니다.

   ![차트가 고정된 대시보드](media/service-get-started/power-bi-final-dashboard.png)

## <a name="next-steps"></a>다음 단계
더 시도할 준비가 되었다면  Power BI를 자세히 탐색하는 몇 가지 유용한 방법은 다음과 같습니다.

* [다른 데이터 집합에 연결](service-get-data.md)합니다.
* 동료와 [대시보드를 공유](service-share-dashboards.md)합니다.
* [대시보드를 설계하는 팁](service-dashboards-design-tips.md)을 확인합니다.
* 대시보드를 [모바일 장치의 Power BI 앱](mobile-apps-for-mobile-devices.md)에서 봅니다.

바로 시작할 준비가 되지 않았다면 Power BI에 익숙해질 수 있도록 설계된 다음 항목에서 시작합니다.

* [보고서, 데이터 집합, 대시보드 및 타일이 모두 결합되는 방법에 대한 자세한 정보](service-basic-concepts.md)
* [Power BI 학습 도우미](guided-learning/index.md) 사이트를 방문하여 몇 가지 간단한 과정을 수강해 보세요.
* [Power BI 비디오](videos.md)를 시청하세요.
* [사용할 수 있는 샘플 확인](sample-datasets.md)

### <a name="stay-in-touch-with-power-bi"></a>Power BI를 사용하여 최신 정보 확인
* [@MSPowerBI Twitter](https://twitter.com/mspowerbi)에서 팔로우
* [YouTube 비디오 채널](https://www.youtube.com/channel/UCy--PYvwBwAeuYaR8JLmrfg) 구독
* 필요에 따라 [Power BI 시작 웹 세미나](webinars.md) 시청
* 어디에서 도움을 얻을 수 있는지 알고 계십니까? [도움을 받을 수 있는 10가지 팁](service-tips-for-finding-help.md) 페이지를 참조하세요.

궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](http://community.powerbi.com/)

