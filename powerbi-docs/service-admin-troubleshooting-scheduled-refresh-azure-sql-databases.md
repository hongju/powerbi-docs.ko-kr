---
title: Azure SQL Database에 대해 예약된 새로 고침의 문제 해결
description: Power BI에서 Azure SQL Database에 대해 예약된 새로 고침의 문제 해결
author: mgblythe
manager: kfile
ms.reviewer: kayu
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: troubleshooting
ms.date: 09/04/2019
ms.author: mblythe
ms.custom: seodec18
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 6d71a1202ba996b70c7477a33ccab936bebbfc5e
ms.sourcegitcommit: e5cf19e16112c7dad1591c3b38d232267ffb3ae1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "72542792"
---
# <a name="troubleshooting-scheduled-refresh-for-azure-sql-databases-in-power-bi"></a>Power BI에서 Azure SQL Database에 대해 예약된 새로 고침의 문제 해결

새로 고침에 대한 자세한 내용은 [Power BI에서 데이터 새로 고침](refresh-data.md) 및 [예약된 새로 고침 구성](refresh-scheduled-refresh.md)을 참조하세요.

Azure SQL 데이터베이스에 예약된 새로 고침을 설정하는 과정에서 자격 증명을 편집할 때 오류(오류 코드 400)가 발생하면 다음에 따라 적절한 방화벽 규칙을 설정합니다.

1. [Azure Portal](https://portal.azure.com)에 로그인합니다.

1. 새로 고침을 구성 중인 Azure SQL 데이터베이스로 이동합니다.

1. **개요** 블레이드의 맨 위에서 **서버 방화벽 설정**을 선택합니다.

1. **방화벽 설정** 블레이드에서 **Azure 서비스에 대한 액세스 허용**이 **켜기**로 설정되어 있는지 확인합니다.

    ![Azure에서 허용된 서비스](media/service-admin-troubleshooting-scheduled-refresh-azure-sql-databases/azurerefresh.png)  

궁금한 점이 더 있나요? [Power BI 커뮤니티를 이용하세요.](http://community.powerbi.com/)
