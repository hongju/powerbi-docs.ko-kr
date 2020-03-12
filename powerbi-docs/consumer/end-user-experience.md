---
title: Power BI 서비스 살펴보기
description: Power BI 탐색 환경 개요
author: mihart
ms.reviewer: ''
featuredvideoid: G26dr2PsEpk
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: quickstart
ms.date: 01/31/2020
ms.author: mihart
LocalizationGroup: Get started
ms.openlocfilehash: fbd629ea7d2c5bb71471ac8073a5a823f1b2c192
ms.sourcegitcommit: 8e3d53cf971853c32eff4531d2d3cdb725a199af
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "76975151"
---
# <a name="quickstart---getting-around-in-power-bi-service"></a>빠른 시작 - Power BI 서비스 살펴보기

[!INCLUDE [power-bi-service-new-look-include](../includes/power-bi-service-new-look-include.md)]

이제 Power BI의 기본 사항을 알아보았으므로 **Power BI 서비스**를 살펴보겠습니다. 앞서 언급했듯이 특정 팀원이 **Power BI Desktop**에서 모든 시간을 보내면서 데이터를 결합하고 다른 사용자를 위한 보고서를 만들 수 있습니다. 반면 Power BI 서비스를 이용하는 내내 다른 사람이 만든 콘텐츠를 보고 상호 작용할 수도 있습니다(**소비** 경험). 이 빠른 시작에서는 샘플 데이터를 가져오고, 해당 데이터를 사용하여 Power BI 서비스 이용 방법을 알아봅니다. 
 
## <a name="prerequisites"></a>필수 조건

- 아직 Power BI에 등록하지 않은 경우 시작하기 전에 [평가판에 등록합니다](https://app.powerbi.com/signupredirect?pbi_source=web).

- [Power BI 서비스 기본 개념](end-user-basic-concepts.md)을 참조합니다.



## <a name="open-the-power-bi-service"></a>Power BI 서비스 열기


시작하려면 Power BI 서비스(app.powerbi.com)를 열고 **홈**으로 이동합니다. 
1. 왼쪽 탐색 창이 축소되어 있으면 탐색 창 아이콘 ![3개의 가로줄이 있는 아이콘](./media/end-user-experience/power-bi-burger.png) 을 선택하여 펼칩니다. 

1. 아직 열려 있지 않으면 **홈**을 선택합니다. 


1. 샘플 데이터를 가져옵니다. Power BI 서비스 둘러보기에서 사용할 샘플 데이터를 가져오겠습니다. 살펴볼 수 있도록 여러 가지 유형의 샘플 데이터가 제공되는데, 이번에는 마케팅과 영업 관련 데이터를 사용하겠습니다. 

    진행하려면 다음 지침을에 따라 [영업 및 마케팅 샘플 앱](end-user-app-marketing.md)을 설치합니다.

1. 앱이 설치되면 탐색 창에서 **앱**을 선택합니다. 

   ![처음으로 열린 Power BI 서비스](./media/end-user-experience/power-bi-home-steps.png)


2. **앱** 화면에서 **영업 및 마케팅 샘플** 앱을 선택합니다.

    ![처음으로 열린 Power BI 서비스](./media/end-user-experience/power-bi-sample-app.png)

2. **앱 탐색**을 선택합니다.

    ![샘플 선택](./media/end-user-experience/power-bi-explore.png)


3. Power BI 서비스에서 앱의 대시보드가 열립니다. Power BI 서비스가 Power BI Desktop과 차이가 나는 부분이 대시보드입니다. 여기 샘플에는 보고서와 데이터 세트도 포함되어 있습니다. 

    ![대시보드](media/end-user-experience/power-bi-dash.png)

    ‘소비자’는 수신하는 대부분의 앱에서 기본 데이터 세트에 직접 액세스할 수 없습니다.  Power BI 샘플은 모든 Power BI 고객을 위해 만들어지므로 데이터 세트가 포함되어 있습니다. ‘디자이너' 동료는 데이터 세트를 사용하여 새 대시보드와 보고서를 만드는 방법을 알아봅니다.  

## <a name="view-content-dashboards-and-reports"></a>콘텐츠 보기(대시보드 및 보고서)
먼저 기본 콘텐츠(대시보드, 보고서, 앱)가 어떻게 구성되는지 살펴보겠습니다. 콘텐츠는 작업 영역 컨텍스트 내에서 표시됩니다. 모든 소비자에게는 작업 영역이 하나 이상 있고, 이런 작업 영역을 **내 작업 영역**이라고 합니다. 앱을 설치할 때마다 해당 앱의 작업 영역이 만들어집니다.  영업 및 마케팅 샘플 앱을 설치했으므로 이제 두 개의 작업 영역이 있습니다. 

왼쪽 탐색 창에서 **작업 영역**을 선택하여 직접 확인해 보세요. 

![내 작업 영역 ](./media/end-user-experience/power-bi-workspaces.png)

**내 작업 영역**에는 소유하고 만드는 모든 콘텐츠가 저장됩니다. 고유한 콘텐츠에 대한 개인 샌드박스 또는 작업 영역으로 생각하면 됩니다. 대부분의 Power BI ‘소비자'는 새 콘텐츠를 만드는 일이 업무에 포함되어 있지 않으므로 **내 작업 영역**이 비어 있는 상태로 유지됩니다.   정의상 ‘소비자'는 다른 사용자가 만든 데이터를 사용하고 해당 데이터를 이용해 비즈니스 의사 결정을 내립니다.  콘텐츠를 만드는 경우 대신 [‘디자이너'를 위한 Power BI 문서](../power-bi-creator-landing.md)를 읽어 보시기 바랍니다. 

**앱 작업 영역**에는 특정 앱의 모든 콘텐츠가 포함됩니다.  ‘디자이너'는 앱을 만들 때 해당 앱을 활용하는 데 필요한 모든 콘텐츠를 함께 묶습니다.   영업 및 마케팅 작업 영역을 선택하여 ‘디자이너'가 앱에 무엇을 묶었는지 확인해 보세요.  

![앱 작업 영역 화면](./media/end-user-experience/power-bi-app-workspace.png)

영업 및 마케팅 앱 작업 영역에는 대시보드, 보고서 및 데이터 세트가 하나씩 포함되어 있습니다. 모든 앱에 이러한 세 가지 콘텐츠가 포함되어 있는 것은 아닙니다. 앱에 따라 대시보드가 하나만, 각 콘텐츠 유형이 3개씩 또는 보고서가 20개 포함되어 있을 수도 있습니다. ‘디자이너'가 앱에 무엇을 포함하는지에 따라 달라집니다.  영업 및 마케팅 데이터는 샘플이므로 데이터 세트를 포함합니다. 하지만 일반적으로는 ‘소비자'의 앱 작업 영역에 데이터 세트가 포함되지 않습니다.  

작업 영역은 단순한 콘텐츠 목록 이상의 기능을 제공합니다. 이 페이지에서는 작업 영역의 대시보드와 보고서에 관해 자세히 알아볼 수 있습니다. 콘텐츠 소유자, 마지막으로 새로 고친 날짜, 관련 콘텐츠, 인증 등을 확인해 보세요. 몇 분밖에 걸리지 않습니다. 작업 영역에 설명이 있으면 해당 설명을 참조하여 작업 영역 목표와 작업 영역을 비즈니스 목적에 맞게 활용하는 방법을 더 잘 이해할 수 있습니다. 그리고 작업 영역에 많은 콘텐츠가 포함된 경우 검색 및 정렬 옵션을 사용하여 필요한 항목을 신속하게 찾을 수 있습니다.

![추가 작업 메뉴가 표시된 앱 작업 영역 화면](./media/end-user-experience/power-bi-workspace-app.png)

작업 영역은 필요한 데이터를 얻는 경로 중 하나이기도 합니다. 목록에서 대시보드나 보고서를 선택하여 엽니다.  별표 아이콘을 가리키고 선택하여 대시보드나 보고서를 즐겨찾기에 추가합니다. ‘디자이너'가 [공유 권한](end-user-shared-with-me.md)을 부여한 경우에는 마우스로 가리킬 때 해당 작업도 표시됩니다.  

![가리킬 때 표시되는 메뉴](./media/end-user-experience/power-bi-hover.png)

대시보드 이름을 선택하여 대시보드를 엽니다.

![대시보드 열기](./media/end-user-experience/power-bi-dashboard-open.png)

## <a name="favorite-a-dashboard-and-a-report"></a>대시보드 및 보고서 즐겨찾기
**즐겨찾기**를 통해 가장 중요한 콘텐츠에 빠르게 액세스할 수 있습니다. 작업 영역에서 대시보드를 즐겨찾기에 추가하는 방법을 알아봤습니다. 대시보드나 보고서에서 직접 즐겨찾기를 만들 수도 있습니다.

1. 대시보드가 열려 있는 상태에서 메뉴 모음에서 **즐겨찾기**를 선택합니다.
   
   ![즐겨찾기 추가](./media/end-user-experience/power-bi-select-favorite.png)
   
   **즐겨찾기**가 **즐겨찾기에서 제거**로 변경되고 별표 아이콘이 노란색으로 바뀝니다.
   
   ![즐겨찾기 제거](./media/end-user-experience/power-bi-unfavorite.png)

2. 즐겨찾기에 추가된 모든 콘텐츠의 목록을 표시하려면 탐색 창에서 **즐겨찾기** 오른쪽에 있는 화살표를 선택합니다. 탐색 창은 Power BI 서비스의 영구 기능이기 때문에 Power BI 서비스의 어디에서든 이 목록에 액세스할 수 있습니다.
   
    ![즐겨찾기 플라이아웃](./media/end-user-experience/power-bi-favorites-flyout.png)
   
    이 Power BI 사용자에게는 4개의 즐겨찾기가 있습니다. 즐겨찾기는 대시보드, 보고서 또는 앱일 수 있습니다.  


자세한 내용은 [즐겨찾기](end-user-favorite.md)를 참조하세요.

## <a name="locate-your-most-recent-content"></a>가장 최근의 콘텐츠 찾기

1. 즐겨찾기와 마찬가지로, 탐색 창에서 **최근** 옆에 있는 화살표를 선택하여 Power BI 서비스의 어디에서든 가장 최근에 액세스한 콘텐츠를 빠르게 확인할 수 있습니다.

   ![최근 플라이아웃](./media/end-user-experience/power-bi-flyout-recent.png)

    플라이아웃에서 콘텐츠를 선택하여 엽니다.

2. 최근 콘텐츠를 열지 않고 정보를 보거나 공유, 인사이트 보기 또는 Excel로 내보내기와 같은 다른 작업을 수행하려는 경우가 있습니다. 이러한 경우 탐색 창에서 **최근** 또는 해당 아이콘을 선택하여 **최근** 창을 엽니다. 이 예제에서는 Power BI 사용자에게 두 개 이상의 작업 영역이 있으므로 이 목록에는 모든 작업 영역의 콘텐츠가 포함될 수 있습니다.

   ![최근 창](./media/end-user-experience/power-bi-recent-action.png)

자세한 내용은 [Power BI의 최근 항목](end-user-recent.md)을 참조하세요.

### <a name="search-and-sort-content"></a>콘텐츠 검색 및 정렬
Power BI 서비스를 처음 사용하는 경우 몇 개의 콘텐츠만 있습니다. 그러나 동료가 콘텐츠 공유를 시작하고 앱 다운로드를 시작하면 긴 콘텐츠 목록이 표시될 수 있습니다. 그러면 검색 및 정렬이 매우 유용해집니다.

검색은 Power BI 서비스의 거의 모든 부분에서 사용할 수 있습니다. 검색 상자 또는 검색 돋보기 아이콘만 찾으면 됩니다.    
![돋보기 아이콘](./media/end-user-experience/power-bi-search-icon.png)

검색 필드에 대시보드, 보고서, 통합 문서, 앱 또는 소유자의 이름을 전부 또는 일부 입력합니다. Power BI가 모든 콘텐츠를 검색합니다.

![보고서 검색](./media/end-user-experience/power-bi-search-field.png)

또한 콘텐츠를 정렬하는 다양한 방법이 있습니다. 열 머리글을 마우스로 가리키고 열을 정렬할 수 있음을 나타내는 화살표를 찾습니다. 모든 열을 정렬할 수 있는 것은 아닙니다. 

![형식 열 머리글 옆의 화살표](./media/end-user-experience/power-bi-sort-icon.png)

또는 캔버스의 오른쪽 위에 있는 정렬 컨트롤을 찾습니다. 날짜, 이름 또는 소유자별로 오름차순이나 내림차순으로 정렬할지 선택합니다.  

![내용 정렬](./media/end-user-experience/power-bi-sort-date.png)


자세한 내용은 [Power BI 탐색: 검색 및 정렬](end-user-search-sort.md)을 참조하세요.

## <a name="power-bi-home"></a>Power BI 홈
마지막으로 이 빠른 시작을 시작했던 Power BI **홈**을 살펴보겠습니다. 

![홈 캔버스](./media/end-user-experience/power-bi-home-oldest.png)

홈에는 검색 및 정렬 도구, 탐색 창이 있고 대시보드, 보고서 및 앱을 열기 위해 선택할 수 있는 *카드*가 포함된 캔버스도 있습니다. 처음에는 홈 캔버스에 그다지 많은 카드가 표시되지 않을 수 있으나, 동료들과 Power BI를 사용하다 보면 점점 더 많아집니다. 홈 캔버스에 표시되는 권장 콘텐츠 및 학습 리소스도 업데이트됩니다.

자세한 내용은 [Power BI 홈](end-user-home.md)을 참조하세요.

## <a name="clean-up-resources"></a>리소스 정리
이 빠른 시작을 완료한 후 필요한 경우 샘플 대시보드, 보고서 및 데이터 세트를 삭제할 수 있습니다.

1. Power BI 서비스(app.powerbi.com)를 열고 로그인합니다.    
2. Power BI 홈을 열고 **작업 영역**까지 아래로 스크롤한 후 *영업 및 마케팅*을 선택합니다.      

3. 대시보드, 보고서 또는 데이터 세트를 마우스로 가리키고 **추가 옵션(...)**  > **삭제**를 선택합니다. 3개 모두 제거할 때까지 반복합니다.

    ![대시보드 삭제](./media/end-user-experience/power-bi-delete.png)



## <a name="next-steps"></a>다음 단계

> [!div class="nextstepaction"]
> [Power BI 서비스의 읽기용 보기](end-user-reading-view.md)
