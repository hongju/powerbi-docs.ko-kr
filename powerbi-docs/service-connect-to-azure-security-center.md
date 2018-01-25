---
title: "Power BI로 Azure Security Center에 연결"
description: "Power BI용 Azure Security Center"
services: powerbi
documentationcenter: 
author: joeshoukry
manager: kfile
backup: maggiesMSFT
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/16/2017
ms.author: yshoukry
ms.openlocfilehash: e26a26d7cba2ae3d68586a2e0dcdf87481009bd6
ms.sourcegitcommit: d803e85bb0569f6b357ba0586f5702c20d27dac4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="connect-to-azure-security-center-with-power-bi"></a>Power BI로 Azure Security Center에 연결
Azure 보안 데이터를 Power BI와 연결하여 Azure 워크로드 보안에 대한 정보를 얻습니다. Power BI는 데이터를 분석하고 탐색할 수 있도록 하는 Azure Security Center에 대시보드 및 보고서를 자동으로 만듭니다.

Power BI용 [Azure Security Center 콘텐츠 팩](https://app.powerbi.com/getdata/services/azure-security-center)에 연결합니다.

## <a name="how-to-connect"></a>연결 방법
1. 왼쪽 탐색 창의 맨 아래에 있는 **데이터 가져오기** 를 선택합니다.
   
   ![](media/service-connect-to-azure-security-center/getdata.png)
2. **서비스** 상자에서 **가져오기**를 선택합니다.
   
   ![](media/service-connect-to-azure-security-center/services.png)
3. **Azure Security Center**\>**가져오기**를 선택합니다.
   
   ![](media/service-connect-to-azure-security-center/asc.png)
4. 구독 ID를 지정합니다. 아래 [이러한 매개 변수 찾기](#FindingParams)에서 세부 정보를 참조하세요.
   
   ![](media/service-connect-to-azure-security-center/params.png)
5. **인증 방법**에 대해 **oAuth2** \> **로그인**을 선택합니다. 메시지가 표시되면 Azure 자격 증명을 입력합니다.
   
    ![](media/service-connect-to-azure-security-center/creds.png)
6. 승인되면 가져오기 프로세스가 자동으로 시작됩니다. 완료되면 새 대시보드, 보고서 및 모델이 탐색 창에 나타납니다. 대시보드를 선택하여 가져온 데이터를 표시합니다.
   
     ![](media/service-connect-to-azure-security-center/dashboard.png)

**다음 단계**

* 대시보드 맨 위에 있는 [질문 및 답변 상자에 질문](power-bi-q-and-a.md)합니다.
* 대시보드에서 [타일을 변경](service-dashboard-edit-tile.md)합니다.
* [타일을 선택](service-dashboard-tiles.md)하여 원본 보고서를 엽니다.
* 데이터 집합을 매일 새로 고치도록 예약하는 경우 새로 고침 일정을 변경하거나 **지금 새로 고침**을 사용하여 필요할 때 새로 고칠 수 있습니다.

## <a name="whats-included"></a>포함된 내용
콘텐츠 팩에는 리소스 보안 상태, 경고 분석 및 방지 분석에 대한 정보가 포함되어 있습니다.

## <a name="system-requirements"></a>시스템 요구 사항
이 콘텐츠 팩은 Azure Security Center를 사용하여 구독 ID에 액세스해야 합니다. Azure Portal의 [Azure Security Center](https://portal.azure.com/#blade/Microsoft_Azure_Security/SecurityDashboardStartBladeV2)에서 자세한 내용을 참조하세요.

콘텐츠 팩에는 조직 계정(개인 계정이 아닌)과 연결할 사용자도 필요합니다.

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>매개 변수 찾기
두 가지 간단한 방법으로 구독 ID를 찾을 수 있습니다.

1. https://portal.azure.com -&gt; 찾아보기 -&gt; 구독 -&gt; 구독 ID에서
2. https://manage.windowsazure.com -&gt; 설정  -&gt; 구독 ID에서

구독 ID는 숫자와 문자의 긴 집합으로, 위 \#4단계의 예와 유사합니다. 

## <a name="troubleshooting"></a>문제 해결
계정 크기에 따라 데이터를 로드하는 데 시간이 걸릴 수 있습니다. 로그인하는 동안 오류가 발생하면 매개 변수 및 계정에서 Azure Security Center를 사용하도록 설정했는지 확인하세요.

콘텐츠 팩이 로드되지만 표시되는 데이터가 없으면 조직 계정으로 연결 중인지 확인합니다. Azure Security Center에서 개인 계정이 지원되지만, 사용자가 조직 계정이 아닌 계정으로 연결하면 API(및 콘텐츠 팩)는 예상되는 값을 반환하지 않습니다. 조직 계정에 대한 액세스를 제공하고 연결을 다시 시도하십시오.

## <a name="next-steps"></a>다음 단계
[Power BI에서 시작](service-get-started.md)

[Power BI에서 데이터 가져오기](service-get-data.md)

