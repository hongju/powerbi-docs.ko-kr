---
title: SharePoint 목록에서 보고서 만들기
description: 이 자습서에서는 SharePoint 목록 데이터를 Power BI 보고서로 변환하는 방법을 보여줍니다.
author: AdamDWilson
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: tutorial
ms.date: 11/27/2019
ms.author: adamw
LocalizationGroup: Visualizations
ms.openlocfilehash: a583957cddfc6554aae323624caaa5430038cecf
ms.sourcegitcommit: 97597ff7d9ac2c08c364ecf0c729eab5d59850ce
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2020
ms.locfileid: "75772704"
---
# <a name="create-a-report-on-a-sharepoint-list"></a>SharePoint 목록에서 보고서 만들기

손쉽게 설정하고 업데이트할 수 있으므로 많은 팀과 조직에서 SharePoint Online의 목록을 사용하여 데이터를 저장합니다.  경우에 따라, 목록 자체를 보는 것보다 차트에서 데이터를 보다 신속하게 파악할 수 있습니다. 이 자습서에서는 SharePoint 목록 데이터를 Power BI 보고서로 변환하는 방법을 보여줍니다.

5분 분량의 자습서 비디오를 시청하거나 아래로 스크롤하여 단계별 지침을 확인하세요.

<iframe width="400" height="450" src="https://www.youtube.com/embed/OZO3x2NF8Ak" frameborder="0" allowfullscreen></iframe>

## <a name="part-1-connect-to-your-sharepoint-list"></a>1부: SharePoint 목록에 연결

1. 아직 설치하지 않은 경우 [Power BI Desktop](https://powerbi.microsoft.com/desktop/)를 다운로드하여 설치합니다.
2. Power BI Desktop을 열고 리본에 있는 홈 탭에서 **데이터 가져오기** > **추가**를 선택합니다.
3. **Online Services**을 선택한 다음 **SharePoint Online 목록**을 선택합니다.  

    <img src="media/desktop-sharepoint-online-list/desktop-sharepoint-online-list-getdata.png" alt="get data" width="350"/>

4. **연결**을 선택합니다.
4. 목록이 포함된 SharePoint Online 사이트의 주소(또는 URL)를 찾습니다.  SharePoint Online의 페이지에서는, 일반적으로 탐색 창에서 **홈**을 선택하거나, 맨 위에 있는 사이트의 아이콘을 선택하고 웹 브라우저의 주소 표시줄에서 주소를 복사하여 사이트 주소를 가져올 수 있습니다.

   이 단계의 비디오를 시청하세요.
   <iframe width="400" height="300" src="https://www.youtube.com/embed/OZO3x2NF8Ak?start=48&end=90" frameborder="0" allowfullscreen></iframe>

5. Power BI Desktop의 열기 대화 상자에서 **사이트 URL** 필드에 주소를 붙여 넣습니다.

6. 다음 이미지와 같이 SharePoint 액세스 화면이 표시되거나 표시되지 않을 수 있습니다.  표시되지 않는 경우, 10단계로 건너뜁니다.  표시되는 경우, 페이지의 왼쪽에서 **Microsoft 계정**을 선택합니다.

    <img src="media/desktop-sharepoint-online-list/desktop-sharepoint-online-list-auth1.png" alt="choose Microsoft account" width="500"/>

7. **로그인**을 선택하고 Microsoft Office 365에 로그인하는 데 사용할 사용자 이름 및 암호를 입력합니다.

    <img src="media/desktop-sharepoint-online-list/desktop-sharepoint-online-list-auth2.png" alt="sign in" width="500"/>

8. 로그인을 마치면 **연결**을 선택합니다.

9. 탐색기의 왼쪽에서 연결하려는 SharePoint 목록 옆에 있는 확인란을 선택합니다.

    <img src="media/desktop-sharepoint-online-list/desktop-sharepoint-online-list-select-list.png" alt="get data" width="450"/>

10. **로드**를 선택합니다.  Power BI에서 목록 데이터를 새 보고서로 로드합니다.

## <a name="part-2-create-a-report"></a>2부: 보고서 만들기

1. 왼쪽에서, **데이터** 아이콘을 선택하여 SharePoint 목록 데이터가 로드되었는지 확인합니다.

2. 숫자가 있는 목록 열의 오른쪽에 있는 **필드 창**에 합계 또는 시그마, 아이콘이 표시되는지 확인합니다.  그렇지 않은 경우, 테이블 뷰에서 열 머리글을 선택하고 **모델링** 탭을 선택한 다음, 데이터에 따라 **데이터 형식**을 **10진수** 또는 **정수**로 변경합니다.  변경 내용을 확인하라는 메시지가 표시되면 **예**를 선택합니다.  숫자가 특수 형식(예: 통화)인 경우 **형식**을 설정하여 선택할 수도 있습니다.

   이 단계의 비디오를 시청하세요.
   <iframe width="400" height="300" src="https://www.youtube.com/embed/OZO3x2NF8Ak?start=147&end=204" frameborder="0" allowfullscreen></iframe>

3. 왼쪽에서 **보고서** 아이콘을 선택합니다.
4. 오른쪽의 **필드** 창에서 시각화하려는 열 옆에 있는 확인란을 선택하여 열을 선택합니다.

   이 단계의 비디오를 시청하세요.
   <iframe width="400" height="300" src="https://www.youtube.com/embed/OZO3x2NF8Ak?start=215&end=252" frameborder="0" allowfullscreen></iframe>

5. 필요한 경우 시각적 개체 유형을 변경합니다.
6. 기존 시각적 개체의 선택을 취소하고 **필드** 창에서 다른 열의 확인란을 선택하여 동일한 보고서에서 여러 개의 시각화를 만들 수 있습니다.
7. 보고서를 저장하려면 **저장**을 선택합니다.
