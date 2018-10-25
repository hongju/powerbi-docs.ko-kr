---
title: Power BI로 MailChimp에 연결
description: Power BI용 MailChimp
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: e6e09ceb6aa40f26e145b5ace7a3c9e94bfcb44d
ms.sourcegitcommit: 0ff358f1ff87e88daf837443ecd1398ca949d2b6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/21/2018
ms.locfileid: "46547755"
---
# <a name="connect-to-mailchimp-with-power-bi"></a>Power BI로 MailChimp에 연결
Power BI 콘텐츠 팩은 MailChimp 계정에서 데이터를 끌어오고 데이터를 탐색할 수 있게 해주는 대시보드, 일련의 보고서 및 데이터 집합을 생성합니다. 분석을 가져와서 [MailChimp 대시보드](https://powerbi.microsoft.com/integrations/mailchimp)를 만들고 캠페인, 보고서 및 개별 구독자의 추세를 빠르게 확인할 수 있습니다. 데이터가 매일 새로 고쳐지도록 설정되어 모니터링하는 데이터를 최신 상태를 유지합니다.

Power BI용 [MailChimp 콘텐츠 팩](https://app.powerbi.com/getdata/services/mailchimp)에 연결합니다.

## <a name="how-to-connect"></a>연결 방법
1. 왼쪽 탐색 창의 맨 아래에 있는 **데이터 가져오기** 를 선택합니다.
   
    ![](media/service-connect-to-mailchimp/pbi_getdata.png)
2. **서비스** 상자에서 **가져오기**를 선택합니다.
   
   ![](media/service-connect-to-mailchimp/pbi_getservices.png)
3. **MailChimp** \> **가져오기**를 선택합니다.
   
   ![](media/service-connect-to-mailchimp/mailchimp.png)
4. 인증 방법에 대해 **oAuth2** \> **로그인**을 선택합니다.
   
    메시지가 표시되면 MailChimp 자격 증명을 입력하고 인증 프로세스를 따릅니다.
   
    처음 연결하는 경우 Power BI에 계정에 대한 읽기 전용 액세스를 허용하라는 메시지가 표시됩니다. **허용**을 선택하여 가져오기 프로세스를 시작합니다. 이 작업은 계정의 데이터 볼륨에 따라 몇 분 정도 걸릴 수 있습니다.
   
    ![](media/service-connect-to-mailchimp/allow.png)
5. Power BI가 데이터를 가져오면 왼쪽 탐색 창에 새 대시보드, 보고서 및 데이터 집합이 표시됩니다. Power BI가 데이터를 표시하기 위해 만든 기본 대시보드입니다. 이 대시보드를 수정하여 원하는 방식으로 데이터를 표시할 수 있습니다.
   
   ![](media/service-connect-to-mailchimp/pbi_mailchimpnewdash.png)

**다음 단계**

* 대시보드 맨 위에 있는 [질문 및 답변 상자에 질문](consumer/end-user-q-and-a.md)합니다.
* 대시보드에서 [타일을 변경](service-dashboard-edit-tile.md)합니다.
* [타일을 선택](consumer/end-user-tiles.md)하여 원본 보고서를 엽니다.
* 데이터 집합을 매일 새로 고치도록 예약하는 경우 새로 고침 일정을 변경하거나 **지금 새로 고침**을 사용하여 필요할 때 새로 고칠 수 있습니다.

## <a name="next-steps"></a>다음 단계
[Power BI란?](power-bi-overview.md)

[Power BI - 기본 개념](consumer/end-user-basic-concepts.md)

