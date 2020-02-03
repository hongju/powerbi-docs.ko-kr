---
title: 새로 고침을 지원하지 않는 데이터 소스 문제 해결
description: 새로 고침을 지원하지 않는 데이터 소스 문제 해결
author: maggiesMSFT
ms.reviewer: kayu
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: troubleshooting
ms.date: 12/06/2017
ms.author: maggies
ms.custom: seodec18
LocalizationGroup: Troubleshooting
ms.openlocfilehash: e3fe8626001972acc0b7555f37844b5abb62753b
ms.sourcegitcommit: 90bd747b7c460d17b74cd386d3f5714234b1f6c9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74791988"
---
# <a name="troubleshooting-unsupported-data-source-for-refresh"></a>새로 고침을 지원하지 않는 데이터 소스 문제 해결
예약 새로 고침에 대해 데이터 세트를 구성할 때 오류가 발생할 수 있습니다.

        You cannot schedule refresh for this dataset because it gets data from sources that currently don’t support refresh.

이러한 오류는 Power BI Desktop에서 사용한 데이터 원본이 새로 고침을 지원하지 않을 때 발생합니다.  사용 중인 데이터 원본을 찾아 [Power BI에서 데이터 새로 고침](refresh-data.md)의 지원되는 데이터 원본 목록과 비교해야 합니다. 

## <a name="find-the-data-source"></a>데이터 원본 찾기
어떤 데이터 원본을 사용했는지 잘 모를 경우 Power BI Desktop에서 다음 단계를 통해 찾을 수 있습니다.  

1. Power BI Desktop에서 **보고서** 창에 있는지 확인합니다.  
   ![데스크톱 보고서 창](media/service-admin-troubleshoot-unsupported-data-source-for-refresh/tshoot-report-pane.png)
2. 리본 메뉴에서 **쿼리 편집**을 선택합니다.  
   ![쿼리 편집](media/service-admin-troubleshoot-unsupported-data-source-for-refresh/tshoot-edit-queries.png)
3. **고급 편집기**를 선택합니다.  
   ![고급 편집기](media/service-admin-troubleshoot-unsupported-data-source-for-refresh/tshoot-advanced-editor.png)
4. 원본에 대해 나열된 공급자를 메모해 둡니다.  이 예제에서는 공급자가 ActiveDirectory입니다.  
   ![데이터 원본 공급자](media/service-admin-troubleshoot-unsupported-data-source-for-refresh/tshoot-provider.png)
5. [Power BI 데이터 원본](power-bi-data-sources.md)에 있는 지원되는 데이터 원본 목록과 해당 공급자를 비교합니다.

## <a name="next-steps"></a>다음 단계
[데이터 새로 고침](refresh-data.md)  
[Power BI 게이트웨이 - 개인](service-gateway-personal-mode.md)  
[On-premises data gateway (온-프레미스 데이터 게이트웨이)](service-gateway-onprem.md)  
[온-프레미스 데이터 게이트웨이 문제 해결](service-gateway-onprem-tshoot.md)  
[Power BI 게이트웨이 - 개인 문제 해결](service-admin-troubleshooting-power-bi-personal-gateway.md)  

궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](https://community.powerbi.com/)

