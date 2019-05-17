---
title: '자습서: Power BI Desktop을 사용한 Facebook 분석'
description: '자습서: Power BI Desktop을 사용한 Facebook 분석'
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: tutorial
ms.date: 11/28/2018
ms.author: davidi
LocalizationGroup: Learn more
ms.openlocfilehash: 8d80d0a2d976661f2b62476be7742b755d11f1c9
ms.sourcegitcommit: 5e83fa6c93a0bc6599f76cc070fb0e5c1fce0082
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/13/2019
ms.locfileid: "56216542"
---
# <a name="tutorial-facebook-analytics-using-power-bi-desktop"></a>자습서: Power BI Desktop을 사용한 Facebook 분석

이 자습서에서는 Facebook에서 데이터를 가져오고 Power BI Desktop에서 사용하는 방법을 알아봅니다. Power BI Facebook 페이지에 연결하여 이 페이지에서 데이터를 가져오고, 가져온 데이터에 변환을 적용하고, 보고서 시각화에서 데이터를 사용합니다.

## <a name="connect-to-a-facebook-page"></a>Facebook 페이지에 연결

이 자습서에서는 [Microsoft Power BI Facebook 페이지](https://www.facebook.com/microsoftbi)(*https://www.facebook.com/microsoftbi*)의 데이터를 사용합니다. 개인 Facebook 계정을 제외하고 이 페이지에 연결하여 데이터를 가져오는 데는 특별한 자격 증명이 필요하지 않습니다.

1. Power BI Desktop을 열고 **시작** 대화 상자에서 **데이터 가져오기**를 선택하거나, **홈** 리본 메뉴의 **데이터 가져오기**를 선택한 다음, **자세히...** 를 선택합니다.
   
2. **데이터 가져오기** 대화 상자의 **온라인 서비스** 그룹에서 **Facebook**을 선택한 다음, **연결**을 선택합니다.
   
   ![데이터 가져오기](media/desktop-tutorial-facebook-analytics/t_fb_getdataother.png)
   
   타사 서비스의 사용에 따른 위험을 경고하는 대화 상자가 나타납니다.
   
   ![타사 경고](media/desktop-tutorial-facebook-analytics/t_fb_connectingtotps.png)
   
3. **계속**을 선택합니다. **Facebook** 대화 상자가 나타납니다.
   
4. **사용자 이름** 텍스트 상자에 **microsoftbi** 페이지 이름을 입력하거나 붙여넣고 **연결** 드롭다운에서 **게시**를 선택한 다음, **확인**을 선택합니다.
   
   ![연결](media/desktop-tutorial-facebook-analytics/2.png)
   
5. 자격 증명을 묻는 메시지가 표시되면 Facebook 계정에 로그인하고 해당 계정을 통한 Power BI 액세스를 허용합니다.
   
   ![자격 증명](media/desktop-tutorial-facebook-analytics/facebookcredentials.png)

   Power BI Facebook 페이지에 연결한 후 페이지의 **게시** 데이터 미리 보기가 표시됩니다. 
   
   ![데이터 미리 보기](media/desktop-tutorial-facebook-analytics/t_fb_1-loadpreview.png)
   
## <a name="shape-and-transform-the-imported-data"></a>가져온 데이터 모양 지정 및 변환

시간에 따라 어떤 게시물에 가장 많은 댓글이 있는지 확인하고 표시하려고 하지만 **게시** 데이터 미리 보기에서는 **created_time** 데이터가 읽고 이해하기 어렵고 댓글 데이터가 전혀 없음을 알 수 있습니다. 데이터를 최대한 활용하려면 데이터의 모양을 지정하고 데이터를 정리해야 합니다. Power BI Desktop **파워 쿼리 편집기**를 사용하여 Power BI Desktop으로 가져오기 전이나 가져온 후에 데이터를 편집할 수 있습니다. 

### <a name="split-the-datetime-column"></a>날짜/시간 열 분할

먼저 **created_time** 열의 날짜 및 시간 값을 보다 읽기 쉽게 구분합니다. 

1. Facebook 데이터 미리 보기에서 **편집**을 선택합니다. 
   
   ![데이터 미리 보기 편집](media/desktop-tutorial-facebook-analytics/t_fb_1-editpreview.png)
   
   Power BI Desktop **파워 쿼리 편집기**가 새 창에서 열리고 Power BI Facebook 페이지에 데이터 미리 보기가 표시됩니다. 
   
   ![파워 쿼리 편집기](media/desktop-tutorial-facebook-analytics/t_fb_1-intoqueryeditor.png)
   
2. **created_time** 열을 선택합니다. 이 열은 현재 열 머리글에 **ABC** 아이콘으로 표시된 텍스트 데이터 형식입니다. 머리글을 마우스 오른쪽 단추로 클릭하고 **열 분할 > 구분 기호 기준**을 선택하거나, 리본 메뉴의 [홈] 탭에 있는 **변환** 아래에서 **열 분할 > 구분 기호 기준**을 선택합니다.  
   
   ![구분 기호로 열 분할](media/desktop-tutorial-facebook-analytics/delimiter1.png)
   
3. **구분 기호로 열 분할** 대화 상자의 드롭다운에서 **사용자 지정**을 선택하고 입력 필드에 **T**(created_time 값의 시간 부분을 시작하는 문자)를 입력한 다음, **확인**을 선택합니다. 
   
   ![구분 기호로 열 분할 대화 상자](media/desktop-tutorial-facebook-analytics/delimiter2.png)
   
   해당 열은 **T** 구분 기호의 앞뒤에 문자열을 포함하는 두 개의 열로 분할되고 각각 **created_time.1** 및 **created_time.2**로 이름이 지정됩니다. 지금까지 Power BI에서는 데이터 형식을 자동으로 검색하여 첫 번째 열에 대해 **날짜**로, 두 번째 열에 대해 **시간**으로 변경하고 날짜 및 시간 값의 서식을 보다 읽기 쉽게 지정했습니다.
   
4. 각 열 머리글을 두 번 클릭하거나 각 열을 선택한 다음, 리본에 있는 **변환** 탭의 **열** 그룹에서 **이름 바꾸기**를 선택하고 각각 새 열 머리글 **created_date** 및 **created_time**을 입력하여 열의 이름을 바꿉니다.
   
   ![새 날짜 및 시간 열](media/desktop-tutorial-facebook-analytics/delimiter3.png)
   
### <a name="expand-the-nested-column"></a>중첩 열 확장

날짜 및 시간 데이터를 원하는 방식으로 표시했으므로 중첩 열을 확장하여 댓글 데이터를 표시합니다. 

1. **object_link** 열을 선택한 후 ![확장 아이콘](media/desktop-tutorial-facebook-analytics/14.png) 아이콘을 선택하여 **확장/집계** 대화 상자를 엽니다. **connections**를 선택한 후 **확인**을 선택합니다. 
   
   ![object_link 확장](media/desktop-tutorial-facebook-analytics/expand1.png)
   
   열 제목이 **object_link.connections**로 변경됩니다.
2. **object_link.connections** 열의 맨 위에 있는 ![확장 아이콘](media/desktop-tutorial-facebook-analytics/14.png) 아이콘을 다시 선택하고, **comments**를 선택한 후, **확인**을 선택합니다. 열 제목이 **object_link.connections.comments**로 변경됩니다.
   
3. **object_link.connections.comments** 열의 맨 위에 있는 ![확장 아이콘](media/desktop-tutorial-facebook-analytics/14.png) 아이콘을 선택하고, 이때 대화 상자에서 [확장] 대신 **집계**를 선택합니다. **# Count of id**를 선택한 후 **확인**을 선택합니다. 
   
   ![댓글 집계](media/desktop-tutorial-facebook-analytics/expand2.png)
   
   이제 열에 각 메시지에 대한 댓글 수가 표시됩니다. 
   
4. **Count of object_link.connections.comments.id** 열의 이름을 **Number of comments**로 바꿉니다.
   
5. **Number of comments** 머리글 옆의 아래쪽 화살표를 선택하고 **내림차순 정렬**을 선택하면 게시물이 가장 많은 댓글부터 가장 적은 댓글 순으로 정렬됩니다. 
   
   ![메시지당 댓글 수](media/desktop-tutorial-facebook-analytics/data-fixed.png)
   
### <a name="review-query-steps"></a>쿼리 단계 검토

**파워 쿼리 편집기**에서 데이터의 모양을 지정하고 데이터를 변환할 때 각 단계가 [파워 쿼리 편집기] 창의 오른쪽에 있는 **쿼리 설정** 창의 **적용된 단계** 영역에 기록되었습니다. 적용된 단계를 통해 이전 단계로 돌아가서 정확히 무엇을 변경했는지 확인하고, 필요한 경우 변경 내용을 편집, 삭제 또는 다시 정렬할 수 있습니다(단, 이전 단계를 변경하면 이후 단계가 중단될 수 있으므로 이 작업은 위험할 수 있음). 

지금까지 데이터 변환을 적용한 후 적용된 단계는 다음과 같이 표시됩니다.
   
   ![적용된 단계](media/desktop-tutorial-facebook-analytics/applied-steps.png)
   
   >[!TIP]
   >적용된 단계의 기초는 **M** 언어라고도 하는 **파워 쿼리 언어**로 작성된 수식입니다. 수식을 보고 편집하려면 리본 메뉴의 [홈] 탭에 있는 **쿼리** 그룹에서 **고급 편집기**를 선택합니다. 

### <a name="import-the-transformed-data"></a>변환된 데이터 가져오기

데이터에 만족하면 리본 메뉴의 [홈] 탭에서 **닫기 및 적용** > **닫기 및 적용**을 선택하여 Power BI Desktop으로 가져옵니다. 
   
   ![닫기 및 적용](media/desktop-tutorial-facebook-analytics/t_fb_1-loadandclose.png)
   
   대화 상자에 Power BI Desktop 데이터 모델에 데이터를 로드하는 작업의 진행률이 표시됩니다. 
   
   ![데이터 로드 중](media/desktop-tutorial-facebook-analytics/t_fb_1-loading.png)
   
   데이터가 로드되면 보고서 보기의 필드 목록에 새 쿼리로 표시됩니다.
   
   ![새 쿼리](media/desktop-tutorial-facebook-analytics/fb-newquery.png)
   
## <a name="use-the-data-in-report-visualizations"></a>보고서 시각화에 데이터 사용 

이제 Facebook 페이지에서 데이터를 가져왔으므로 시각화를 사용하여 데이터를 쉽고 빠르게 파악할 수 있습니다. 시각화를 만드는 것은 쉽습니다. **필드** 목록에서 필드를 선택하거나 보고서 캔버스로 끌어서 놓으면 됩니다.

### <a name="create-a-bar-chart"></a>가로 막대형 차트 만들기

1. Power BI Desktop 보고서 보기의 필드 목록에서 **message**를 선택하거나 캔버스로 끌어서 놓습니다. 모든 게시 메시지를 보여주는 테이블이 캔버스에 나타납니다. 
   
   ![새 쿼리](media/desktop-tutorial-facebook-analytics/table-viz.png)
   
2. 해당 테이블을 선택한 채 필드 목록에서 **Number of comments**를 선택하거나 테이블로 끌어서 놓습니다. 
   
3. [시각화] 창에서 **누적 가로 막대형 차트** 아이콘을 선택합니다. 테이블은 게시물당 댓글 수를 보여주는 가로 막대형 차트로 변경됩니다. 
   
   ![가로 막대형 차트](media/desktop-tutorial-facebook-analytics/barchart1.png)
   
4. 시각화의 오른쪽 위에 있는 줄임표(...)를 선택한 다음, **Number of comments를 기준으로 정렬**을 선택하여 내림차순 댓글 수별로 테이블을 정렬합니다. 
   
   ![댓글 수를 기준으로 정렬](media/desktop-tutorial-facebook-analytics/barchart2.png)
   
5. 가장 많은 댓글이 **공백** 메시지와 연결되어 있었습니다(이러한 게시물은 스토리, 링크, 비디오 또는 기타 텍스트가 아닌 콘텐츠였을 수 있음). 공백 행을 필터링하려면 [시각화] 창의 맨 아래에 있는 **필터**에서 **메시지(모두)** 를 선택하고, **모두 선택**을 선택한 다음, **공백**을 선택하여 선택 취소합니다. 필터 항목이 **메시지가 (공백)이 아님**으로 변경되고 공백 행이 차트 시각화에 표시되지 않습니다. 
   
   ![공백 필터링](media/desktop-tutorial-facebook-analytics/barchart3.png)
   
### <a name="format-the-chart"></a>차트 서식 지정

시각화는 더 흥미로워지지만 차트에서 게시 텍스트를 많이 볼 수 없습니다. 게시 텍스트를 더 많이 표시하려면:

1. 차트 시각화의 핸들을 사용하여 차트 크기를 가능한 한 크게 변경합니다. 
   
2. 차트를 선택한 채 [시각화] 창에서 **서식 지정 아이콘**(페인트 롤러)을 선택합니다.
   
3. **Y축** 옆의 아래쪽 화살표를 선택하고 **최대 크기** 옆의 슬라이더를 완전히 오른쪽(50%)으로 끕니다. 
4. 또한 더 많은 텍스트가 표시되도록 **텍스트 크기**를 **10**으로 줄입니다.
   
   ![변경 내용 서식 지정](media/desktop-tutorial-facebook-analytics/barchart4.png)
   
   이제 차트에 더 많은 게시 콘텐츠가 표시됩니다. 
   
   ![더 많은 게시물 표시](media/desktop-tutorial-facebook-analytics/barchart5.png)
   
차트의 X축(댓글 수)이 정확한 값을 표시하지 않고 차트의 맨 아래에 사라진 것으로 보입니다. 대신에 데이터 레이블을 사용하기로 합니다. 

1. 서식 지정 아이콘을 선택한 다음, **X축** 옆의 슬라이더를 선택하여 **해제**로 전환합니다. 
   
2. **데이터 레이블** 옆의 슬라이더를 선택하여 **설정**으로 전환합니다. 이제 차트에 각 게시물에 대한 정확한 댓글 수가 표시됩니다.
   
   ![데이터 레이블 적용](media/desktop-tutorial-facebook-analytics/barchart6.png)
   
### <a name="edit-the-data-type"></a>데이터 형식 편집

더 나아지기는 했지만 데이터 레이블에는 모두 **.0** 소수 자릿수가 포함되는데, **게시물 수**는 정수여야 하기 때문에 이 소수 자릿수가 혼란을 주고 잘못 이해될 수 있습니다. **게시물 수** 열의 데이터 형식을 정수로 변경해야 합니다.

1. 데이터 형식을 편집하려면 필드 목록에서 **쿼리1**을 마우스 오른쪽 단추로 클릭하거나 마우스로 가리키고 **기타 옵션** 줄임표(...)를 선택한 다음, **쿼리 편집**을 선택합니다. 리본 메뉴에 있는 [홈] 탭의 **외부 데이터** 영역에서 **쿼리 편집**을 선택한 다음, 드롭다운에서 **쿼리 편집**을 선택할 수도 있습니다. Power BI Desktop **파워 쿼리 편집기**가 별도 창에서 열립니다.
   
   ![필드 목록에서 쿼리 편집](media/desktop-tutorial-facebook-analytics/editquery1.png)     ![리본에서 쿼리 편집](media/desktop-tutorial-facebook-analytics/t_fb_editquery.png)
   
2. 파워 쿼리 편집기에서 **Number of comments** 열을 선택하고 다음 중 한 방법으로 데이터 형식을 **정수**로 변경합니다. 
   - **Number of comments** 열 머리글 옆의 **1.2** 아이콘을 선택하고 드롭다운에서 **정수** 선택 또는
   - 열 머리글을 마우스 오른쪽 단추로 클릭하고 **형식 변경 > 정수** 선택 또는
   - **데이터 형식: 정수**를 [홈] 탭의 **변환** 그룹에서 선택하거나 **변환** 탭의 **열** 그룹을 선택하고 **데이터 형식: 정수** 선택.
   
   열 머리글의 아이콘이 정수 데이터 형식을 나타내는 **123**으로 변경됩니다.
   
   ![데이터 형식 변경](media/desktop-tutorial-facebook-analytics/change-datatype.png)
   
3. **닫기 및 적용**을 선택하거나, **적용**을 선택하여 [파워 쿼리 편집기] 창이 열린 상태로 변경 내용을 적용합니다. 변경 내용이 로드되면 차트의 데이터 레이블이 정수가 됩니다. 
   
   ![정수가 있는 차트](media/desktop-tutorial-facebook-analytics/vis-3.png)
   
### <a name="create-a-date-slicer"></a>날짜 슬라이서 만들기

시간에 따른 게시물에 대한 댓글 수를 시각화하려고 합니다. 슬라이서 시각화를 만들어 차트 데이터를 여러 시간 프레임으로 필터링할 수 있습니다. 

1. 캔버스의 빈 영역을 클릭한 다음, [시각화] 창에서 **슬라이서 아이콘**을 선택합니다. 빈 슬라이서 시각화가 나타납니다. 
   
   ![슬라이서 아이콘 선택](media/desktop-tutorial-facebook-analytics/slicer1.png)
   
2. 필드 목록에서 **created_date** 필드를 선택하거나 새 슬라이서로 끌어서 놓습니다. 슬라이서는 필드의 날짜 데이터 형식을 기준으로 날짜 범위 슬라이더로 변경됩니다.
   
   ![날짜 범위 슬라이더 슬라이서](media/desktop-tutorial-facebook-analytics/slicer2.png)
   
3. 슬라이더 핸들을 움직여 다른 날짜 범위를 선택하고 차트 데이터 필터에 이에 따라 어떻게 필터링되는지 확인합니다. 슬라이서에서 날짜 필드를 선택하고 특정 날짜를 입력하거나 달력 팝업에서 선택할 수도 있습니다.
    
   ![데이터 조각화](media/desktop-tutorial-facebook-analytics/slicer3.png)
   
### <a name="format-the-visualizations"></a>시각화 서식 지정

차트에 더 자세하고 매력적인 제목을 제공하고자 합니다. 

1. 차트를 선택한 채 **서식** 아이콘을 선택하고 드롭다운 화살표를 선택하여 **제목**을 확장합니다.
2. **제목 텍스트**를 **Comments per post**로 변경합니다. 
3. **글꼴색** 옆의 드롭다운 화살표를 선택하고 녹색을 선택하여 시각화의 녹색 막대와 일치시킵니다.
4. **텍스트 크기**를 **10**으로 늘리고 **글꼴 패밀리**를 **Segoe (Bold)** 로 변경합니다.

![차트 제목 서식 지정](media/desktop-tutorial-facebook-analytics/formatting1.png)

다른 서식 옵션 및 설정을 사용하여 시각화 모양을 변경해 봅니다. 

![시각화](media/desktop-tutorial-facebook-analytics/vis-1.png)

## <a name="create-more-visualizations"></a>추가 시각화 만들기

살펴봤듯이 보고서에서 시각화를 쉽게 사용자 지정하여 원하는 방식으로 데이터를 표시할 수 있습니다. 예를 들어 가져온 Facebook 데이터를 사용하여 시간에 따른 댓글 수를 보여주는 이 꺾은선형 차트를 만들어 봅니다.

![꺾은선형 차트](media/desktop-tutorial-facebook-analytics/moreviz.png)

Power BI Desktop은 다양한 데이터 원본에서 데이터를 가져오고 이 데이터를 풍부한 대화형 방식으로 시각화하기 위해 분석 요구 사항에 맞게 모양을 지정하는 원활한 엔드투엔드 환경을 제공합니다. 보고서가 준비되면 [Power BI 서비스로 업로드](desktop-upload-desktop-files.md)하고 보고서에 따라 대시보드를 만든 후 다른 Power BI 사용자와 공유할 수 있습니다.

## <a name="next-steps"></a>다음 단계
* [다른 Power BI Desktop 자습서 참고](http://go.microsoft.com/fwlink/?LinkID=521937)
* [Power BI Desktop 동영상 시청](http://go.microsoft.com/fwlink/?LinkID=519322)
* [Power BI 포럼 방문](http://go.microsoft.com/fwlink/?LinkID=519326)
* [Power BI 블로그 참고](http://go.microsoft.com/fwlink/?LinkID=519327)

