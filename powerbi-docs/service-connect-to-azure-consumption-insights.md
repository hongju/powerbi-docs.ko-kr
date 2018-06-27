---
title: Power BI로 Microsoft Azure Consumption Insights에 연결
description: Power BI용 Microsoft Azure Consumption Insights
author: SarinaJoan
manager: kfile
ms.reviewer: maggies
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 31f1d4161801b45307e92ad3f654d30843897dc8
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2018
ms.locfileid: "34244160"
---
# <a name="connect-to-microsoft-azure-consumption-insights-with-power-bi"></a>Power BI로 Microsoft Azure Consumption Insights에 연결
Power BI 콘텐츠 팩을 사용하여 Power BI에서 Microsoft Azure 소비 데이터를 탐색하고 모니터링합니다. 하루에 한 번 자동으로 데이터가 새로 고쳐집니다.

Power BI용 [Microsoft Azure Consumption Insights 콘텐츠 팩](https://app.powerbi.com/getdata/services/azureconsumption)에 연결합니다.

## <a name="how-to-connect"></a>연결 방법
1. 왼쪽 탐색 창의 맨 아래에 있는 **데이터 가져오기** 를 선택합니다.
   
    ![](media/service-connect-to-azure-consumption-insights/getdata.png)
2. **서비스** 상자에서 **가져오기**를 선택합니다.
   
   ![](media/service-connect-to-azure-consumption-insights/services.png)
3. **Microsoft Azure Consumption Insights 콘텐츠 팩** \> **가져오기**를 선택합니다. 
   
   ![](media/service-connect-to-azure-consumption-insights/mazureconsumption.png)
4. 가져올 데이터의 개월 수를 입력하고 Azure Enterprise 등록 번호를 입력합니다. 아래에서 [해당 매개 변수 찾기](#FindingParams)에 대한 세부 정보를 참조하세요.
   
    ![](media/service-connect-to-azure-consumption-insights/azureconsumptionparams.png)
5. 연결할 선택키를 제공합니다. 등록을 위한 키는 Azure EA 포털에서 찾을 수 있습니다. 
   
    ![](media/service-connect-to-azure-consumption-insights/msazureconsumptioncreds.png)
6. 가져오기 프로세스가 자동으로 시작됩니다. 완료되면 새 대시보드, 보고서 및 모델이 탐색 창에 나타납니다. 대시보드를 선택하여 가져온 데이터를 표시합니다.
   
   ![](media/service-connect-to-azure-consumption-insights/msazureconsumptiondashboard.png)

**다음 단계**

* 대시보드 맨 위에 있는 [질문 및 답변 상자에 질문](power-bi-q-and-a.md)합니다.
* 대시보드에서 [타일을 변경](service-dashboard-edit-tile.md)합니다.
* [타일을 선택](service-dashboard-tiles.md)하여 원본 보고서를 엽니다.
* 데이터 집합을 매일 새로 고치도록 예약하는 경우 새로 고침 일정을 변경하거나 **지금 새로 고침**을 사용하여 필요할 때 새로 고칠 수 있습니다.

## <a name="whats-included"></a>포함된 내용
Microsoft Azure Consumption Insights 콘텐츠 팩에는 연결 흐름 중에 사용자가 제공하는 월 기간 동안의 월간 보고 데이터가 포함되어 있습니다. 이 기간은 변동되는 기간이므로 포함되는 날짜는 데이터 집합을 새로 고치면 업데이트됩니다.

## <a name="system-requirements"></a>시스템 요구 사항
콘텐츠 팩을 사용하려면 Azure Portal 내의 엔터프라이즈 기능에 액세스해야 합니다. 

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>매개 변수 찾기
Power BI 보고는 대금 청구 정보를 볼 수 있는 EA Direct, 파트너 및 간접 고객에게 제공됩니다. 연결 흐름이 예상하는 값 각각을 찾는 데 대한 자세한 내용은 아래를 읽습니다.

**월 수**

* (오늘부터)가져올 데이터 개월 수를 나타내는 1부터 36 사이의 숫자여야 합니다.

**등록 번호**

* "등록 세부 정보"의 [Azure Enterprise Portal](https://ea.azure.com/)의 홈 화면에서 찾을 수 있는 Azure Enterprise 등록 번호입니다.
  
    ![](media/service-connect-to-azure-consumption-insights/params2.png)

**선택키**

* Azure 엔터프라이즈 포털의 "사용량 다운로드" > "API 선택키"에서 키를 찾을 수 있습니다
  
    ![](media/service-connect-to-azure-consumption-insights/creds2.png)

**추가 도움말**

* Azure Enterprise Power BI 팩 설정에 대한 추가 도움말을 보려면 Azure Enterprise Portal에 로그인한 후 "도움말" 아래의 API 도움말 파일과 보고서 -> 사용량 다운로드 -> API 액세스 키에서 추가 지침을 확인하세요. 

## <a name="next-steps"></a>다음 단계
[Power BI에서 시작](service-get-started.md)

[Power BI에서 데이터 가져오기](service-get-data.md)

