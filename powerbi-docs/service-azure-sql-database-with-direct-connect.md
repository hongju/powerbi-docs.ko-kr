---
title: "DirectQuery를 사용한 Azure SQL Database"
description: "DirectQuery를 사용한 Azure SQL Database"
services: powerbi
documentationcenter: 
author: guyinacube
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 08/10/2017
ms.author: asaxton
ms.openlocfilehash: 83613f0ed915a03b65b90d4bf61e37568b922182
ms.sourcegitcommit: c2deaff54434da67698a14cc00172a2119ed1a56
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/09/2017
---
# <a name="azure-sql-database-with-directquery"></a>DirectQuery를 사용한 Azure SQL Database
Azure SQL Database에 직접 연결하고 라이브 데이터를 사용하는 보고서를 작성하는 방법에 대해 알아보세요. Power BI가 아닌 소스에서 데이터를 유지할 수 있습니다.

DirectQuery를 사용할 경우 보고서 뷰에서 데이터를 탐색할 때 쿼리가 Azure SQL Database로 다시 전송됩니다. 이 환경은 연결하는 데이터베이스와 엔터티를 잘 알고 있는 사용자에게 제안됩니다.

**참고:**

* 연결 시 정규화된 서버 이름을 지정합니다(자세한 내용은 아래 참조).
* 데이터베이스에 대한 방화벽 규칙이 "[Azure 서비스에 대한 액세스 허용](https://msdn.microsoft.com/library/azure/ee621782.aspx)으로 구성되었는지 확인합니다.
* 열 선택 또는 필터 추가와 같은 모든 작업은 쿼리를 다시 데이터베이스로 보냅니다.
* 약 15분마다 타일이 새로 고쳐집니다.(새로 고침을 예약할 필요가 없음) 연결하는 경우 고급 설정에서 조정될 수 있습니다.
* DirectQuery 데이터 집합에 대해 질문 및 답변을 사용할 수 없습니다.
* 스키마 변경 내용은 자동으로 선택되지 않습니다.

이러한 제한 사항 및 참고는 환경이 계속 향상됨에 따라 변경될 수 있습니다. 연결 단계는 아래에서 자세히 설명합니다. 

## <a name="power-bi-desktop-and-directquery"></a>Power BI Desktop 및 DirectQuery
DirectQuery를 사용하여 Azure SQL Database에 연결하려면 Power BI Desktop을 사용해야 합니다. 이 방법은 유연성 및 기능을 추가로 제공합니다. Power BI Desktop를 사용하여 만든 보고서는 Power BI 서비스에 게시할 수 있습니다. Power BI Desktop 내에서 [DirectQuery를 사용하는 Azure SQL Database](desktop-use-directquery.md)에 연결하는 방법에 대해 자세히 확인할 수 있습니다. 

## <a name="connecting-through-power-bi"></a>Power BI를 통해 연결
더 이상 Power BI 서비스로부터 Azure SQL Database에 직접 연결할 수 없습니다. [Azure SQL Database 커넥터](https://app.powerbi.com/getdata/bigdata/azure-sql-database-with-live-connect)를 선택하면, Power BI Desktop 내에서 연결할지 묻는 메시지가 나타납니다. 그런 다음 Power BI Desktop 보고서를 Power BI 서비스에 게시할 수 있습니다. 

![](media/service-azure-sql-database-with-direct-connect/azure-sql-database-in-power-bi.png)

### <a name="finding-parameter-values"></a>매개 변수 값 찾기
정규화된 서버 이름과 데이터베이스 이름은 Azure Portal에서 확인할 수 있습니다.

![](media/service-azure-sql-database-with-direct-connect/azureportnew_update.png)

![](media/service-azure-sql-database-with-direct-connect/azureportal_update.png)

## <a name="next-steps"></a>다음 단계
[Power BI Desktop에서 DirectQuery 사용](desktop-use-directquery.md)  
[Power BI 시작](service-get-started.md)  
[Power BI에 대한 데이터 가져오기](service-get-data.md)  
궁금한 점이 더 있나요? [Power BI 커뮤니티를 이용하세요.](http://community.powerbi.com/)

