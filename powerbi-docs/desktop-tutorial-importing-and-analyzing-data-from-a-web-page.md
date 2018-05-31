---
title: '자습서: Power BI Desktop을 사용하여 웹 페이지에서 데이터 가져오기 및 분석'
description: '자습서: Power BI Desktop을 사용하여 웹 페이지에서 데이터 가져오기 및 분석'
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: tutorial
ms.date: 05/21/2018
ms.author: davidi
LocalizationGroup: Learn more
ms.openlocfilehash: 20bcc45fa95bcff6eb8a761dae58c67a875f55cd
ms.sourcegitcommit: e6db826c2f43a69e4c63d5f4920baa8f66bc41be
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/23/2018
ms.locfileid: "34455999"
---
# <a name="tutorial-analyze-web-page-data-using-power-bi-desktop"></a>자습서: Power BI Desktop을 사용하여 웹 페이지 데이터 분석

오래된 축구 팬으로서 몇 년 동안 UEFA 유럽 선수권 대회(유로컵)에 대해 보고하려고 합니다. Power BI Desktop을 사용하면 웹 페이지에서 보고서로 이 데이터를 가져와서 데이터를 표시하는 시각화를 만들 수 있습니다. 이 자습서에서는 Power BI Desktop을 사용하여 다음을 수행하는 방법을 알아봅니다.

- 웹 데이터 원본에 연결하고 사용 가능한 테이블을 탐색합니다.
- **파워 쿼리 편집기**에서 데이터를 셰이핑 및 변환합니다.
- 쿼리 이름을 지정하고, Power BI Desktop 보고서로 가져오고, 
- 맵 및 원형 차트 시각화를 만들고 사용자 지정합니다.

## <a name="connect-to-a-web-data-source"></a>웹 데이터 원본에 연결

http://en.wikipedia.org/wiki/UEFA_European_Football_Championship의 UEFA 유럽 축구 선수권 대회 Wikipedia 페이지에 있는 Results 테이블에서 UEFA 우승팀 데이터를 가져올 수 있습니다. 

![Wikipedia Results 테이블](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage1.png)

데이터를 가져오려면:

1. Power BI Desktop **홈** 리본 탭에서 **데이터 가져오기** 옆에 있는 화살표를 드롭다운하고 **웹**을 선택합니다.
   
   ![리본에서 데이터 가져오기](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/get-data-web3.png) 
   
   >[!NOTE]
   >**데이터 가져오기** 항목 자체를 선택하거나 Power BI **시작** 대화 상자에서 **데이터 가져오기**를 선택하고 **데이터 가져오기** 대화 상자의 **모두** 또는 **기타** 섹션에서 **웹**을 선택한 다음, **연결**을 선택할 수도 있습니다.
   
2. **웹에서** 대화 상자의 **URL** 텍스트 상자에 URL `http://en.wikipedia.org/wiki/UEFA_European_Football_Championship`을 붙여넣은 다음, **확인**을 선택합니다.
   
    ![대화 상자에서 데이터 가져오기](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/get-data-web2.png)
   
   Wikipedia 웹 페이지에 연결한 후 Power BI **탐색기** 대화 상자에는 페이지에서 사용 가능한 테이블 목록이 표시됩니다. 테이블 이름을 선택하여 데이터를 미리 볼 수 있습니다. 정확히 원하는 셰이프가 아니더라도 원하는 데이터가 **Results[edit]** 테이블에 있습니다. 보고서에 로드하기 전에 데이터를 다시 셰이핑하고 정리합니다. 
   
   ![탐색기 대화 상자](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/tutorialimanaly_navigator.png)
   
   >[!NOTE]
   >**미리 보기** 창에는 선택된 가장 최근 테이블이 표시되지만, 선택된 모든 테이블은 **편집** 또는 **로드**를 선택할 때 **파워 쿼리 편집기**로 로드됩니다. 
   
3. **탐색기** 목록에서 **Results[edit]** 테이블을 선택한 후 **편집**을 선택합니다. 
   
   테이블의 미리 보기가 **파워 쿼리 편집기**에서 열리고, 여기에서 변환을 적용하여 데이터를 정리할 수 있습니다. 
   
   ![파워 쿼리 편집기](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage3.png)
   
## <a name="shape-data-in-power-query-editor"></a>파워 쿼리 편집기에서 데이터 셰이핑

우승한 연도와 국가만 표시하여 데이터를 더 쉽게 검색하려 합니다. **파워 쿼리 편집기**를 사용하여 이러한 데이터 셰이핑 및 정리 단계를 수행할 수 있습니다.

먼저 테이블에서 **Year** 및 **Final Winners**를 제외한 모든 열을 제거합니다.

1. **파워 쿼리 편집기** 그리드에서 **Year** 및 **Final Winners** 열을 선택합니다(여러 항목을 선택하려면 **Ctrl** 키를 누르고 있음).
   
2. 마우스 오른쪽 단추를 클릭하고 드롭다운에서 **다른 열 제거**를 선택하거나, **홈** 리본 탭의 **열 관리** 그룹에서 **열 제거** > **다른 열 제거**를 선택하여 테이블에서 다른 모든 열을 제거합니다. 
   
   ![다른 열 제거 드롭다운](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/get-data-web6.png) 또는 ![다른 열 제거 리본](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage4.png)

다음으로 **Year** 열 셀에서 추가 단어 **Details**를 제거합니다.

1. **Year** 열을 선택합니다.
   
2. 마우스 오른쪽 단추를 클릭하고 드롭다운에서 **값 바꾸기**를 선택하거나, **홈** 리본 탭의 **변환** 그룹에서 **값 바꾸기**를 선택합니다(**변환** 탭의 **열** 그룹에도 있음). 
   
   ![값 바꾸기 드롭다운](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/get-data-web7.png) 또는 ![값 바꾸기 리본](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/get-data-web8a.png)
   
3. **값 바꾸기** 대화 상자에서 **찾을 값** 텍스트 상자에 **Details**를 입력하고 **바꿀 내용** 텍스트 상자를 비워둔 다음, **확인**을 선택하여 **Year** 항목에서 “Details” 단어를 삭제합니다.
   
   ![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage6.png)

일부 **Year** 셀에는 연도 값이 아닌 “Year”라는 단어만 포함됩니다. **Year** 열을 필터링하여 “Year” 단어를 포함하지 않는 행만 표시합니다. 

1. **Year** 열에서 필터 드롭다운 화살표를 선택합니다.
   
2. 드롭다운에서 아래쪽으로 스크롤하여 **Year** 옵션 옆에 있는 확인란을 선택 취소한 다음, **확인**을 선택하여 **Year** 열에 “Year”라는 단어만 있는 행을 제거합니다. 

   ![데이터 필터링](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage7.png)

**Year** 열의 데이터를 정리했으므로 **Final Winner** 열을 작업할 수 있습니다. 현재 최종 우승자 데이터만 확인하므로 이 열의 이름을 **Country**로 바꿀 수 있습니다. 열 이름을 바꾸려면:

1. **Final Winner** 열 머리글을 두 번 클릭하거나 길게 탭합니다. 또는 
   - **Final Winners** 열 머리글을 마우스 오른쪽 단추로 클릭하고 드롭다운에서 **이름 바꾸기**를 선택합니다. 또는 
   - **Final Winners** 열을 선택하고 리본의 **변환** 탭에 있는 **임의 열** 그룹에서 **이름 바꾸기**를 선택합니다. 
   
   ![이름 바꾸기 드롭다운](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage7a.png) 또는 ![이름 바꾸기 리본](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/get-data-web8.png)
   
2. 머리글에 **Country**를 입력하고 **Enter** 키를 눌러 열 이름을 바꿉니다.

또한 **Country** 열에서 null 값이 포함된 행(예: “2020”)을 필터링하려 합니다. **Year** 값으로 작업한 대로 필터 메뉴를 사용하거나 다음을 수행할 수 있습니다.

1. 값이 *null*인 **2020** 행에서 **Country** 셀을 마우스 오른쪽 단추로 클릭합니다. 
2. 상황에 맞는 메뉴에서 **텍스트 필터** >  **같지 않음**을 선택하여 해당 셀 값이 포함된 모든 행을 제거합니다.
   
   ![텍스트 필터](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/get-data-web11.png)
   
## <a name="import-the-query-into-report-view"></a>보고서 보기로 쿼리 가져오기

이제 원하는 방식으로 데이터를 셰이핑했으므로 쿼리 이름을 “Euro Cup Winners”로 지정하고 보고서로 가져올 준비가 되었습니다.

1. **쿼리 설정** 창에서 **이름** 텍스트 상자에 **Euro Cup Winners**를 입력한 다음, **Enter** 키를 누릅니다.
   
   ![쿼리 이름 지정](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage8.png)

2. **홈** 리본 탭에서 **닫기 및 적용** > **닫기 및 적용**을 선택합니다.
   
   ![닫기 및 적용](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage9.png)
   
이 쿼리는 Power BI Desktop **보고서 보기**로 로드되고, 여기에서 **필드** 창에 표시됩니다. 
   
   ![필드 창](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage11.png)
>[!TIP]
>항상 **파워 쿼리 편집기**로 돌아가서 다음과 같이 쿼리를 편집하고 구체화할 수 있습니다.
>- **필드** 창의 **Euro Cup Winners** 옆에 있는 **추가 옵션** 줄임표(**...**)를 선택하고 드롭다운에서 **쿼리 편집**을 선택하거나,
>- 보고서 보기의 **홈** 리본 탭에 있는 **외부 데이터** 그룹에서 **쿼리 편집** > **쿼리 편집**을 선택합니다. 

## <a name="create-a-visualization"></a>시각화 만들기

데이터를 기반으로 시각화를 만들려면: 

1. **필드** 창에서 **국가** 필드를 선택하거나 보고서 캔버스로 끌어옵니다. Power BI Desktop은 데이터를 국가 이름으로 인식하고 **맵** 시각화를 자동으로 만듭니다. 
   
   ![맵 시각화](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/get-data-web14.png)
   
2. 모든 우승 국가 이름이 표시되도록 모서리의 핸들을 끌어 맵을 확대합니다.  

   ![맵 확대](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage14.png)
   
3. 맵에는 유로컵 토너먼트에서 우승한 모든 국가에 대한 동일한 데이터 요소가 표시됩니다. 각 데이터 요소의 크기에 해당 국가가 우승한 빈도를 반영하려면 **시각화** 창의 아래쪽 부분에 있는 **크기** 아래의 **데이터 필드를 여기에 끌어오기**로 **Year** 필드를 끌어옵니다. 이 필드는 **Count of Year** 측정값으로 자동으로 변경되고 이제 맵 시각화에는 더 많은 토너먼트에서 우승한 국가에 대한 더 큰 데이터 요소가 표시됩니다. 
   
   ![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage15.png)
   

## <a name="customize-the-visualization"></a>시각화 사용자 지정

살펴본 것처럼 데이터를 기반으로 시각화를 쉽게 만들 수 있습니다. 원하는 방식으로 데이터를 더 잘 표시하도록 시각화를 쉽게 사용자 지정할 수도 있습니다. 

### <a name="format-the-map"></a>맵 서식 지정
시각화를 선택한 다음, **시각화** 창에서 **형식**(페인트 롤러) 아이콘을 선택하여 시각화 모양을 변경할 수 있습니다. 예를 들어 서독이 토너먼트에서 2회 우승했고 독일이 1회 우승했으므로 시각화의 “독일” 데이터 요소가 잘못될 수 있고, 맵에는 두 요소를 구분하거나 함께 추가하는 대신 두 요소를 겹쳐 놓습니다. 이러한 두 요소에 색상을 다르게 지정하여 강조 표시할 수 있습니다. 맵에 보다 구체적이고 매력적인 제목을 제공할 수도 있습니다. 

1. 시각화를 선택한 상태로 **형식** 아이콘을 선택한 다음, **데이터 색**을 선택하여 데이터 색 옵션을 확장합니다. 
   
   ![데이터 색 지정](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/get-data-web15.png)
   
2. **모두 표시**를 **켜기**로 전하고 나서 **West Germany** 옆의 드롭다운을 선택하고 노란색을 선택합니다. 
   
   ![색 변경](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/get-data-web16.png)
   
3. **제목**을 선택하여 제목 옵션을 확장하고 **제목 텍스트** 필드에 현재 제목 대신 **Euro Cup Winners**를 입력합니다. 
4. **글꼴 색**을 빨간색으로 변경하고, **텍스트 크기**를 **12**로 변경하고, **글꼴 패밀리**를 **Segoe (Bold)** 로 변경합니다. 
   
   ![데이터 색 지정](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/get-data-web17.png)
   

이제 맵 시각화는 다음과 같이 표시됩니다.

![서식 지정된 맵 시각화](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/get-data-web18.png)
   
### <a name="change-the-visualization-type"></a>시각화 형식 변경
시각화를 선택한 다음, **시각화** 창의 맨 위에서 다른 아이콘을 선택하여 시각화 형식을 변경할 수 있습니다. 예를 들어 해당 국가가 더 이상 세계 지도에 존재하지 않으므로 맵 시각화에는 소비에트 연방 및 체코슬로바키아에 대한 데이터가 없습니다. 트리 맵 또는 원형 차트 같은 다른 시각화 형식은 모든 값을 표시하므로 더욱 정확할 수 있습니다. 

맵을 원형 차트로 변경하려면 맵을 선택한 다음, **시각화** 창에서 **원형 차트** 아이콘을 선택합니다. 
   
![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/get-data-web19.png)

>[!TIP]
>- **데이터 색** 서식 옵션을 사용하여 “독일” 및 “서독”을 같은 색으로 설정할 수 있습니다. 
>- 원형 차트에서 가장 많이 우승한 국가를 함께 그룹화하려면 시각화의 오른쪽 위에 있는 줄임표(**...**)를 선택한 다음, 드롭다운에서 **연도 수별 정렬**을 선택합니다. 

Power BI Desktop은 다양한 데이터 원본에서 데이터를 가져오고 이 데이터를 풍부한 대화형 방식으로 시각화하기 위해 분석 요구 사항에 맞게 모양을 지정하는 원활한 종단 간 환경을 제공합니다. 보고서가 준비되면 [Power BI로 업로드](desktop-upload-desktop-files.md)하고 보고서에 따라 대시보드를 만든 후 다른 Power BI 사용자와 공유할 수 있습니다.

## <a name="see-also"></a>참고 항목
* [다른 Power BI Desktop 자습서 참고](http://go.microsoft.com/fwlink/?LinkID=521937)
* [Power BI Desktop 동영상 시청](http://go.microsoft.com/fwlink/?LinkID=519322)
* [Power BI 포럼 방문](http://go.microsoft.com/fwlink/?LinkID=519326)
* [Power BI 블로그 참고](http://go.microsoft.com/fwlink/?LinkID=519327)

