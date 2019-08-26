---
title: Power BI 서비스에서 Power BI Desktop으로 보고서 다운로드(미리 보기)
description: Power BI 서비스에서 Power BI Desktop 파일로 보고서 다운로드
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 08/12/2019
ms.author: maggies
LocalizationGroup: Reports
ms.openlocfilehash: 61fc821e63889951aefd0ef815f885ffa8a880cf
ms.sourcegitcommit: d12bc6df16be1f1993232898f52eb80d0c9fb04e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/13/2019
ms.locfileid: "68994820"
---
# <a name="download-a-report-from-the-power-bi-service-to-power-bi-desktop-preview"></a>Power BI 서비스에서 Power BI Desktop으로 보고서 다운로드(미리 보기)
Power BI Desktop에서 로컬 컴퓨터의 보고서(*.pbix* 파일)를 Power BI 서비스에 게시할 수 있습니다. Power BI 보고서는 다른 방향으로도 이동할 수 있습니다. Power BI 서비스에서 Power BI Desktop으로 보고서를 다운로드할 수 있습니다. 두 경우 모두, Power BI 보고서의 확장명은 .pbix입니다.

이 문서의 뒷부분에서 유의해야 할 몇 가지 제한 사항과 고려 사항을 설명합니다.

![파일 드롭다운](media/service-export-to-pbix/power-bi-file-export.png)

## <a name="download-the-report-as-a-pbix-file"></a>.pbix 파일로 보고서 다운로드

2016년 11월 23일 이후에 [Power BI Desktop에서 생성](guided-learning/publishingandsharing.yml?tutorial-step=2)되고 업데이트된 보고서만 다운로드할 수 있습니다. 보고서가 그전에 만들어진 경우에는 Power BI 서비스의 **보고서 다운로드** 메뉴 옵션이 회색으로 표시됩니다.

.Pbix 파일을 다운로드하려면 다음 단계를 따르세요.

1. Power BI 서비스에서 다운로드하려는 보고서를 [편집용 보기](https://docs.microsoft.com/power-bi/service-interact-with-a-report-in-editing-view)로 엽니다.

2. 위쪽 탐색 모음에서 **파일 > 보고서 다운로드**를 선택합니다.
   
3. 보고서를 다운로드하는 동안 상태 배너가 진행 상태를 표시합니다. 파일이 준비되면 .pbix 파일을 저장할 위치를 묻는 메시지가 표시됩니다. 파일의 기본 이름은 보고서의 제목과 일치합니다.
   
4. 아직 설치하지 않은 경우 [Power BI Desktop을 설치](desktop-get-the-desktop.md)하고, Power BI Desktop에서 .pbix 파일을 엽니다.
   
    Power BI Desktop에서 보고서를 열 때, Power BI 서비스 보고서에서 사용할 수 있는 일부 기능이 Power BI Desktop에서는 제공되지 않는다는 경고 메시지가 표시될 수도 있습니다.
   
    ![경고 대화 상자](media/service-export-to-pbix/power-bi-export-to-pbix_2.png)

5. Power BI Desktop의 보고서 편집기는 Power BI 서비스의 보고서 편집기와 비슷합니다.  
   
    ![Power BI Desktop 보고서 편집기](media/service-export-to-pbix/power-bi-desktop.png)

## <a name="considerations-and-troubleshooting"></a>고려 사항 및 문제 해결
Power BI 서비스에서 .pbix 파일을 다운로드하는 경우와 관련된 몇 가지 중요한 고려 사항 및 제한 사항이 있습니다.

* 파일을 다운로드하려면 보고서의 액세스 권한을 편집해야 합니다.
* 보고서가 Power BI Desktop에서 생성되어 Power BI 서비스에 ‘게시’되었거나, .pbix 파일이 Power BI 서비스에 ‘업로드’된 상태여야 합니다.
* 보고서는 2016년 11월 23일 이후 게시되거나 업데이트되어야 합니다. 이전에 게시된 보고서는 다운로드할 수 없습니다.
* 원래 Power BI 서비스에서 만든 보고서 및 콘텐츠 팩에는 이 기능이 적용되지 않습니다.
* 다운로드한 파일을 열 때는 항상 최신 버전의 Power BI Desktop을 사용합니다. 이전 버전의 Power BI Desktop에서는 다운로드한 .pbix 파일이 열리지 않을 수도 있습니다.
* 관리자가 데이터 다운로드 기능을 끈 경우에는 Power BI 서비스에 이 기능이 표시되지 않습니다.
* 증분 새로 고침을 사용하는 데이터 세트는 .pbix 파일로 다운로드할 수 없습니다.

## <a name="next-steps"></a>다음 단계
이 기능에 대한 1분 비디오 **큐브에서 Guy**를 참조하세요.

<iframe width="560" height="315" src="https://www.youtube.com/embed/ymWqU5jiUl0" frameborder="0" allowfullscreen></iframe>

Power BI 서비스의 사용 방법을 학습하는 데 도움이 되는 몇 가지 추가 문서는 다음과 같습니다.

* [Power BI의 보고서](consumer/end-user-reports.md)
* [Power BI 서비스의 디자이너를 위한 기본 개념](service-basic-concepts.md)

Power BI Desktop을 설치한 후에 빠르게 시작하고 실행하는 데 도움이 되는 다음 문서를 참조하세요.

* [Power BI Desktop 시작](desktop-getting-started.md)

궁금한 점이 더 있나요? [Power BI 커뮤니티를 이용](http://community.powerbi.com/)하세요.

