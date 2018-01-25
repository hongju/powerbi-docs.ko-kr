---
title: "Power BI로 Salesforce에 연결"
description: "Power BI용 Salesforce"
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
ms.openlocfilehash: 0a001bec56caf5a8c125afef53b1fbaa6f712eee
ms.sourcegitcommit: d803e85bb0569f6b357ba0586f5702c20d27dac4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="connect-to-salesforce-with-power-bi"></a>Power BI로 Salesforce에 연결
Power BI를 사용하면 Salesforce.com 계정에 쉽게 연결할 수 있습니다. 이 연결을 만들면 데이터가 검색되고, 해당 데이터를 기반으로 하여 대시보드 및 관련 보고서가 자동으로 제공됩니다.

Power BI용 [Salesforce 콘텐츠 팩](https://app.powerbi.com/getdata/services/salesforce)에 연결하거나 Power BI와의 [Salesforce 통합](https://powerbi.microsoft.com/integrations/salesforce)에 대해 자세히 알아보세요.

## <a name="how-to-connect"></a>연결 방법
1. 왼쪽 탐색 창의 맨 아래에 있는 **데이터 가져오기** 를 선택합니다.
   
   ![](media/service-connect-to-salesforce/pbi_getdata.png) 
2. **서비스** 상자에서 **가져오기**를 선택합니다.
   
   ![](media/service-connect-to-salesforce/pbi_getservices.png) 
3. **Salesforce** 를 클릭하고 **가져오기**를 선택합니다.  
   
   ![](media/service-connect-to-salesforce/salesforce.png)
4. **로그인**을 선택하여 로그인 흐름을 시작합니다.
   
    ![](media/service-connect-to-salesforce/dialog.png)
5. 메시지가 표시되면 Salesforce 자격 증명을 입력합니다. **허용** 을 클릭하여 Power BI가 기본 Salesforce 정보 및 데이터에 액세스할 수 있게 합니다.
   
   ![](media/service-connect-to-salesforce/sf_authorize.png)
6. 드롭다운 옵션을 사용하여 Power BI로 가져오려는 항목을 구성합니다.
   
   * **대시보드**
     
     가상 사용자(예: **판매 관리자**)에 따라 미리 정의된 대시보드를 선택합니다. 이러한 대시보드는 Salesforce에서 특정 표준 데이터 집합을 가져오며 사용자 지정 필드를 포함하지 않습니다.
     
     ![](media/service-connect-to-salesforce/pbi_salesforcechooserole.png)
   * **보고서**
     
     Salesforce 계정에서 사용자 지정 보고서를 하나 이상 선택합니다. 이러한 보고서는 Salesforce의 뷰와 일치하며 사용자 지정 필드 또는 개체의 데이터를 포함할 수 있습니다.
     
     ![](media/service-connect-to-salesforce/pbi_salesforcereports.png)
     
     보고서가 표시되지 않는 경우 Salesforce 계정에서 추가하거나 만든 후 다시 연결합니다.
7. **연결** 을 클릭하여 가져오기 프로세스를 시작합니다. 가져오는 동안 가져오기가 진행 중임을 보여 주는 알림이 표시됩니다. 가져오기가 완료되면 왼쪽 탐색 창에 나열된 Salesforce 데이터에 대한 대시보드, 보고서 및 데이터 집합이 표시됩니다.
   
   ![](media/service-connect-to-salesforce/pbi_getdatasalesforcedash.png)

이 대시보드를 변경하여 원하는 방식으로 데이터를 표시할 수 있습니다. 대시보드에서 질문 및 답변에 질문하거나 타일을 클릭하여 [원본 보고서를 열고](service-dashboard-tiles.md) [타일을 변경](service-dashboard-edit-tile.md)할 수 있습니다.

**다음 단계**

* 대시보드 맨 위에 있는 [질문 및 답변 상자에 질문](power-bi-q-and-a.md)합니다.
* 대시보드에서 [타일을 변경](service-dashboard-edit-tile.md)합니다.
* [타일을 선택](service-dashboard-tiles.md)하여 원본 보고서를 엽니다.
* 데이터 집합을 매일 새로 고치도록 예약하는 경우 새로 고침 일정을 변경하거나 **지금 새로 고침**을 사용하여 필요할 때 새로 고칠 수 있습니다.

## <a name="system-requirements"></a>시스템 요구 사항
* API에 액세스할 수 있는 프로덕션 Salesforce 계정을 사용하여 연결되어 있어야 합니다.
* 로그인하는 동안 Power BI 앱에 권한이 부여되어야 합니다.
* 계정에 데이터를 끌어오고 새로 고치는 데 사용할 수 있는 충분한 API 호출이 있어야 합니다.
* 새로 고치려면 유효한 인증 토큰이 필요합니다. Salesforce에서는 응용 프로그램당 5개 인증 토큰으로 제한되므로 5개 이하의 Salesforce 데이터 집합을 가져와야 합니다.

## <a name="troubleshooting"></a>문제 해결
오류가 발생하는 경우 위의 요구 사항을 검토하세요. 또한 사용자 지정 또는 샌드박스 도메인에 로그인하는 기능은 현재 지원되지 않습니다.

## <a name="next-steps"></a>다음 단계
[Power BI 시작](service-get-started.md)

[데이터 가져오기](service-get-data.md)

