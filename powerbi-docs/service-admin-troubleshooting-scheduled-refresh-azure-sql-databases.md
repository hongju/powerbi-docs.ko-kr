---
title: Azure SQL Database에 대해 예약된 새로 고침의 문제 해결
description: Power BI에서 Azure SQL Database에 대해 예약된 새로 고침의 문제 해결
author: mgblythe
manager: kfile
ms.reviewer: kayu
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 12/06/2017
ms.author: mblythe
ms.custom: seodec18
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 0c22d005044c0ebddc242eb35908e26689fee597
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "61186897"
---
# <a name="troubleshooting-scheduled-refresh-for-azure-sql-databases-in-power-bi"></a>Power BI에서 Azure SQL Database에 대해 예약된 새로 고침의 문제 해결
새로 고침 예약 설정에 대한 자세한 단계는 [Power BI에서 데이터 새로 고침](refresh-data.md)을 반드시 참조하세요.

Azure SQL Database에 새로 고침 예약을 설정할 때 자격 증명 편집 중에 오류 코드 400의 오류가 발생할 경우 다음에 따라 적합한 방화벽 규칙을 구성합니다.

1. Azure 관리 포털에 로그인
2. 새로 고침을 구성할 Azure SQL 서버로 이동
3. 허용된 서비스 섹션에서 ‘Windows Azure 서비스’ 켜기

![Azure에서 허용된 서비스](media/service-admin-troubleshooting-scheduled-refresh-azure-sql-databases/azurerefresh.png)  

궁금한 점이 더 있나요? [Power BI 커뮤니티를 이용하세요.](http://community.powerbi.com/)

