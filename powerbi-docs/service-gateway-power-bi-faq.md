---
title: 온-프레미스 데이터 게이트웨이 FAQ - Power BI
description: 이 문서는 Power BI에 대한 온-프레미스 데이터 게이트웨이 FAQ입니다. 이 문서에서는 자주 묻는 질문을 Power BI에서 사용되는 해당 게이트웨이에 대해 하나의 스폿으로 수집합니다.
author: mgblythe
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 07/15/2019
ms.author: mblythe
LocalizationGroup: Gateways
ms.openlocfilehash: 4aa3d46741044498846865278db51859980a19b9
ms.sourcegitcommit: 0d7ad791a2d2bef45d5d60e38e0af4c9fc22187b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74010833"
---
# <a name="on-premises-data-gateway-faq---power-bi"></a>온-프레미스 데이터 게이트웨이 FAQ - Power BI

[!INCLUDE [gateway-rewrite](includes/gateway-rewrite.md)]

## <a name="power-bi"></a>Power BI

**질문:** 온-프레미스 데이터 게이트웨이(개인 모드)를 업그레이드해야 하나요?

**답변:** 아니요. Power BI용 게이트웨이(개인 모드)를 계속 사용할 수 있습니다.

**질문:** 게이트웨이를 설치하고 Power BI 서비스에서 관리하는 데 필요한 특별한 권한이 있나요?

**답변:** 특별한 권한이 필요하지 않습니다.

**질문:** 온-프레미스 데이터 원본에 연결된 파워 피벗 데이터 모델이 있는 Excel 통합 문서를 업로드할 수 있나요? 이 시나리오에 게이트웨이가 필요한가요? 

**답변:** 예. 통합 문서를 업로드할 수 있습니다. 또한 아니요, 게이트웨이가 필요하지 않습니다. 그러나 데이터가 Excel 데이터 모델에 위치하기 때문에 Excel 통합 문서를 기반으로 하는 Power BI의 보고서는 라이브가 아닙니다. Power BI에서 보고서를 새로 고치려면 매번 업데이트된 통합 문서를 다시 업로드해야 합니다. 또는 예약된 새로 고침으로 게이트웨이를 사용합니다.

**질문:** 사용자가 DirectQuery 연결이 있는 대시보드를 공유할 경우 다른 사용자가 동일한 권한이 없는 경우에도 데이터를 볼 수 있나요? 

**답변:** Azure Analysis Services에 연결된 대시보드의 경우, 사용자는 액세스한 데이터만 볼 수 있습니다. 사용자가 동일한 사용 권한이 없는 경우, 어떠한 데이터도 볼 수 없습니다. 다른 데이터 원본의 경우 모든 사용자는 해당 데이터 원본에 대해 관리자가 입력한 자격 증명을 공유합니다.

**질문:** 내 Oracle 서버에 연결할 수 없는 이유는 무엇인가요? 

**답변:** Oracle 서버에 연결하기 위해 Oracle 클라이언트를 설치하고 적절한 서버 정보로 tnsnames.ora 파일을 구성해야 할 수 있습니다. 게이트웨이 외부의 별도 설치입니다. 자세한 내용은 [Oracle 클라이언트 설치](service-gateway-onprem-manage-oracle.md#install-the-oracle-client)를 참조하세요.

**질문:** R 스크립트를 사용하고 있습니다. 지원됩니까?

**답변**: R 스크립트는 개인 모드에서만 지원됩니다.

## <a name="analysis-services-in-power-bi"></a>Power BI의 Analysis Services

**질문:** msdmpump.dll을 사용하여 Analysis Services에 사용자 지정 유효 사용자 이름 매핑을 만들 수 있나요? 

**답변:** 아니요. 지금은 사용하도록 지원되지 않습니다.

**질문:** 게이트웨이를 사용하여 다차원(OLAP) 인스턴스에 연결할 수 있나요? 

**답변:** 예. 온-프레미스 데이터 게이트웨이는 Analysis Services 테이블 형식 및 다차원 모델에 대한 라이브 연결을 지원합니다.

**질문:** Windows 인증을 사용하는 내 온-프레미스 서버의 다른 도메인에 있는 컴퓨터에서 게이트웨이를 설치하면 어떻게 되나요? 

**답변:** 보장은 없습니다. 모두 두 도메인 간의 트러스트 관계에 따라 달라집니다. 서로 다른 두 도메인이 트러스트된 도메인 모델에 있는 경우 게이트웨이에서 Analysis Services 서버에 연결하고 유효한 사용자 이름을 확인할 수 있습니다. 그렇지 않은 경우 로그인 오류가 발생할 수 있습니다.

**질문:** 온-프레미스 Analysis Services 서버에 전달되는 유효 사용자 이름을 찾으려면 어떻게 하나요? 

**답변:** [문제 해결 문서](service-gateway-onprem-tshoot.md)에 이 질문의 답변이 있습니다.

## <a name="next-steps"></a>다음 단계

* [온-프레미스 데이터 게이트웨이 문제 해결](/data-integration/gateway/service-gateway-tshoot)

궁금한 점이 더 있나요? [Power BI 커뮤니티](https://community.powerbi.com/)를 사용해 보세요.

