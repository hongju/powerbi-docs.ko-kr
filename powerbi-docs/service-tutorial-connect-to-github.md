---
title: '자습서: Power BI를 사용 하 여 GitHub 리포지토리에 연결'
description: 이 자습서에서는 Power BI를 사용하여 GitHub 서비스의 실제 데이터에 연결하고, Power BI에서 대시보드와 보고서를 자동으로 만듭니다.
author: maggiesMSFT
manager: kfile
ms.reviewer: SarinaJoan
ms.service: powerbi
ms.subservice: powerbi-service
ms.custom: connect-to-services
ms.topic: tutorial
ms.date: 04/19/2019
ms.author: maggies
LocalizationGroup: Connect to services
ms.openlocfilehash: 3aeb1fc16ae200399125a2366a8993d45aad34c4
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "64578602"
---
# <a name="tutorial-connect-to-a-github-repo-with-power-bi"></a>자습서: Power BI를 사용 하 여 GitHub 리포지토리에 연결
이 자습서에서는 Power BI를 사용하여 GitHub 서비스의 실제 데이터에 연결하고, Power BI에서 대시보드와 보고서를 자동으로 만듭니다. Power BI 콘텐츠 공용 저장소에 연결 (라고도 *리포지토리*) 다음과 같은 질문에 대 한 답변을 표시: 얼마나 많은 사람들이 Power BI 공개 콘텐츠에 기여하나요? 가장 많이 기여한 사람은 누구인가요? 어떤 요일이 가장 많이 기여하는가요? 및 다른 질문을 추가 합니다. 

![Power BI의 GitHub 보고서](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-punch-card.png)

이 자습서에서 수행하는 단계는 다음과 같습니다.

> [!div class="checklist"]
> * GitHub 계정이 아직 없는 경우 이 계정에 등록 
> * Power BI 계정에 로그인 또는 해당 계정이 아직 없는 경우 이 계정에 등록
> * Power BI 서비스 열기
> * GitHub 앱 찾기
> * Power BI 공용 GitHub 리포지토리에 대한 정보 입력
> * GitHub 데이터를 사용하여 대시보드 및 보고서 보기
> * 앱을 삭제하여 리소스 정리

아직 Power BI에 등록하지 않은 경우 시작하기 전에 [평가판에 등록합니다](https://app.powerbi.com/signupredirect?pbi_source=web).

## <a name="prerequisites"></a>필수 조건

이 자습서를 완료하려면 GitHub 계정이 필요합니다. 아직 GitHub 계정이 없으면 다음을 수행합니다. 

- 등록 된 [GitHub 계정](https://docs.microsoft.com/contribute/get-started-setup-github)합니다.


## <a name="how-to-connect"></a>연결 방법
1. Power BI 서비스 (https://app.powerbi.com) 에 로그인합니다. 
2. 왼쪽 탐색 창에서 **앱**, **앱 가져오기**를 차례로 선택합니다.
   
   ![Power BI 앱 가져오기](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial.png) 

3. 선택 **앱**, 형식 **GitHub** 검색 상자에 > **지금**합니다.
   
   ![Power BI - GitHub 가져오기](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-app-source.png) 

4. **Power BI 앱이 설치?** 선택 **설치**합니다.
5. **새 앱이 준비**를 선택 **앱으로 이동**합니다.
6. **새 앱을 시작 하세요**를 선택 **데이터 연결**합니다.

    ![새 앱 시작](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-connect-data.png)

7. 리포지토리의 리포지토리 이름과 리포지토리 소유자를 입력합니다. 이 리포지토리에 대한 URL은 https://github.com/MicrosoftDocs/powerbi-docs 이므로 **리포지토리 소유자**는 **MicrosoftDocs**이고 **리포지토리**는 **powerbi-docs**입니다. 
   
    ![Power BI - GitHub 리포지토리 이름](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-connect.png)

5. 만든 GitHub 자격 증명을 입력합니다. 브라우저에서 GitHub에 이미 로그인되어 있으면 Power BI에서 이 단계를 건너뛸 수 있습니다. 

6. 에 대 한 **인증 방법을**, 유지 **oAuth2** 선택한 \> **로그인**합니다.

7. GitHub 인증 화면을 따릅니다. GitHub 데이터에 대한 Power BI 권한을 부여합니다.
   
   이제 Power BI에서 GitHub와 연결하고 데이터에 연결할 수 있습니다.  하루에 한 번 데이터가 새로 고쳐집니다.

8. Power BI가 데이터를 가져오면 새 GitHub 작업 영역의 내용을 표시 합니다. 
9. 왼쪽된 탐색 모음에서 작업 영역 이름 옆의 화살표를 선택 합니다. 작업 영역 대시보드 및 보고서를 포함 하는 것이 표시 됩니다. 

    ![왼쪽된 탐색 창의 앱](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-left-nav-expanded.png)

10. 대시보드 이름 옆의 줄임표 (...) > **이름 바꾸기** > 형식 **GitHub 대시보드**합니다.
 
    ![Power BI - GitHub 타일](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-left-nav.png) 

8. 글로벌 탐색 아이콘을 선택하여 왼쪽 탐색 영역을 최소화하면 더 많은 공간을 확보할 수 있습니다.

    ![전역 탐색 아이콘](media/service-tutorial-connect-to-github/power-bi-global-navigation-icon.png)

10. GitHub 대시보드를 선택 합니다.
    
    GitHub 대시보드에 표시 되는 값 다를 수 있으므로 라이브 데이터를 포함 합니다.

    ![Power BI - GitHub 대시보드](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-new-dashboard.png)

    

## <a name="ask-a-question"></a>질문하기

1. **데이터에 대해 질문하기**에 커서를 놓습니다. Power BI는 **시작하기 위한 질문**을 제공합니다. 

1. **how many users are there**을 선택합니다.
 
    ![얼마나 많은 사용자가 사항이](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-qna-how-many-users.png)

13. **how many** 및 **users are there** 사이에, **pull requests per**를 입력합니다. 

     Power BI는 사용자 당 끌어오기 요청 수를 보여 주는 가로 막대형 차트를 만듭니다.

    ![사용자 당 얼마나 많은 끌어오기 요청 사항이](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-qna-how-many-prs.png)


13. 그런 다음 대시보드를 고정 하려면 pin을 선택 **q&a 종료**합니다.

## <a name="view-the-github-report"></a>GitHub 보고서 보기 

1. GitHub 대시보드에서, **Pull Requests by Month** 세로 막대형 차트를 선택하여 관련된 보고서를 엽니다.

    ![월 세로 막대형 차트에서 끌어오기 요청](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-column-chart.png)

2. **Total pull requests by user** 차트에서 사용자 이름을 선택합니다. 이 예제에서는 해당 시간의 대부분이 2월에 해당한다는 것을 볼 수 있습니다.

    ![Power BI - GitHub 보고서(강조 표시)](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-cross-filter-total-prs.png)

3. **Punch Card** 탭을 선택하여 보고서의 다음 페이지를 표시합니다. 
 
    ![Power BI - GitHub 보고서 펀치 카드](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-tues-3pm.png)

    분명히 화요일 오후 3시는 사람들이 작업을 체크인할 때 *커밋*에 대한 가장 일반적인 시간 및 요일입니다.

## <a name="clean-up-resources"></a>리소스 정리

자습서를 완료했으므로 GitHub 앱을 삭제할 수 있습니다. 

1. 왼쪽 탐색 모음에서 **앱**을 선택합니다.
2. GitHub 타일 위를 마우스로 가리키고 **삭제** 휴지통을 선택합니다.

    ![GitHub 앱 삭제](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-delete.png)

## <a name="next-steps"></a>다음 단계

이 자습서에서는 GitHub 공용 리포지토리에 연결하고 데이터를 가져와서 Power BI의 대시보드 및 보고서에서 서식을 지정했습니다. 대시보드 및 보고서를 탐색하여 데이터에 대한 몇 가지 질문에 답변했습니다. 이제 Salesforce, Microsoft Dynamics 및 Google Analytics와 같은 다른 서비스에 연결하는 방법에 대해 자세히 알아볼 수 있습니다. 
 
> [!div class="nextstepaction"]
> [사용하는 온라인 서비스에 연결](service-connect-to-services.md)


