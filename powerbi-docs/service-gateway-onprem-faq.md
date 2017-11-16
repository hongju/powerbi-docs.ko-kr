---
title: "온-프레미스 데이터 게이트웨이 FAQ"
description: "온-프레미스 데이터 게이트웨이 FAQ입니다. 질문과 대답을 해당 게이트웨이에 대해 하나의 스폿으로 수집합니다."
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: powerbi
ms.date: 10/05/2017
ms.author: davidi
ms.openlocfilehash: 063fd92829c6b642fc33e578026d109d891b8fd5
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2017
---
# <a name="on-premises-data-gateway-faq"></a>온-프레미스 데이터 게이트웨이 FAQ
<!-- Shared FAQ shared Include -->
[!INCLUDE [gateway-onprem-faq-shared-include](./includes/gateway-onprem-faq-shared-include.md)]

## <a name="analysis-services"></a>Analysis Services
**질문:** msdmpump.dll을 사용하여 Analysis Services에 사용자 지정 유효 사용자 이름 매핑을 만들 수 있나요?  
**답변:** 아니요. 지금은 지원되지 않습니다.

**질문:** 게이트웨이를 사용하여 다차원(OLAP) 인스턴스에 연결할 수 있나요?  
**답변:** 예! 온 프레미스 데이터 게이트웨이는 Analysis Services 테이블 형식 및 다차원 모델에 대한 라이브 연결을 지원합니다.

**질문:** Windows 인증을 사용하는 내 온-프레미스 서버의 다른 도메인에 있는 컴퓨터에서 게이트웨이를 설치하면 어떻게 되나요?  
**답변:** 보장은 없습니다. 모두 두 도메인 간의 트러스트 관계에 따라 달라집니다. 서로 다른 두 도메인이 트러스트된 도메인 모델에 있는 경우 게이트웨이에서 Analysis Services 서버에 연결하고 유효 사용자 이름을 확인할 수 있습니다. 그렇지 않은 경우 로그인 오류가 발생할 수 있습니다.

**질문:** 온-프레미스 Analysis Services 서버에 전달되는 유효 사용자 이름을 찾으려면 어떻게 하나요?  
**답변:** [문제 해결 문서](service-gateway-onprem-tshoot.md)에 답변이 있습니다.

**질문:** Analysis Services에 25개의 데이터베이스가 있습니다. 게이트웨이에 대해 모든 데이터베이스를 한 번에 사용하도록 설정하는 방법이 있나요?  
**응답:** 아니요. 이는 로드맵 상에 있지만 아직 시간 범위는 없습니다.

## <a name="administration"></a>관리
**질문:** 게이트웨이에 대해 둘 이상의 관리자를 포함할 수 있나요?  
**답변:** 예! 게이트웨이를 관리하는 경우 관리자 탭으로 이동하여 관리자를 더 추가할 수 있습니다.

**질문:** 게이트웨이 관리자는 게이트웨이가 설치된 컴퓨터의 관리자여야 하나요?  
**응답:** 아니요. 게이트웨이 관리자는 서비스 내에서 게이트웨이를 관리하는 데 사용됩니다.

**질문:** 내 조직의 사용자가 게이트웨이를 만들지 못하게 할 수 있나요?  
**응답:** 아니요. 이는 로드맵 상에 있지만 아직 시간 범위는 없습니다.

**질문:** 내 조직에서 게이트웨이의 사용량 및 통계 정보를 얻을 수 있나요?  
**응답:** 아니요. 이는 로드맵 상에 있지만 아직 시간 범위는 없습니다.

## <a name="power-bi"></a>Power BI
**질문:** 개인 게이트웨이를 업그레이드해야 하나요?
**답변:** 아니요, Power BI용 개인 게이트웨이를 계속 사용할 수 있습니다.

**질문:** 온-프레미스 데이터 게이트웨이를 통해 연결되어 있을 때 Power BI에서 대시보드 타일을 얼마나 자주 새로 고치나요?  
**답변:** 약 10분입니다. DirectQuery 연결은 여기에 해당합니다. 이는 타일이 온-프레미스 서버에서 쿼리를 발급하거나 10분 마다 새 데이터를 표시하는 것을 의미하지 않습니다.

**질문:** 온-프레미스 데이터 원본에 연결된 파워 피벗 데이터 모델이 있는 Excel 통합 문서를 업로드할 수 있나요? 이 시나리오에 게이트웨이가 필요한가요?  
**답변:** 예, 통합 문서를 업로드할 수 있습니다. 또한 아니요, 게이트웨이가 필요하지 않습니다. 그러나 데이터가 Excel 데이터 모델에 위치하기 때문에 Excel 통합 문서를 기반으로 하는 Power BI의 보고서는 라이브가 아닙니다. Power BI에서 보고서를 새로 고치려면 매번 업데이트된 통합 문서를 다시 업로드해야 합니다. 또는 예약된 새로 고침으로 게이트웨이를 사용합니다.

**질문:** 사용자가 DirectQuery 연결이 있는 대시보드를 공유할 경우 다른 사용자가 동일한 권한이 없는 경우에도 데이터를 볼 수 있나요?  
**답변:** Analysis Services에 연결된 대시보드의 경우, 사용자는 액세스한 데이터만 볼 수 있습니다. 사용자가 동일한 사용 권한이 없는 경우, 어떠한 데이터도 볼 수 없습니다. 다른 데이터 원본의 경우 모든 사용자는 해당 데이터 원본에 대해 관리자가 입력한 자격 증명을 공유합니다.

**질문:** 내 Oracle 서버에 연결할 수 없는 이유는 무엇입니까?  
**답변:** Oracle 서버에 연결하기 위해 Oracle 클라이언트를 설치하고 적절한 서버 정보로 tnsnames.ora 파일을 구성해야 할 수 있습니다. 게이트웨이 외부의 별도 설치입니다. 자세한 내용은 [Oracle 클라이언트 설치](service-gateway-onprem-manage-oracle.md#installing-the-oracle-client)를 참조하세요.

**질문:** 게이트웨이에서 ExpressRoute를 사용하는가요?  
**답변:** 예. ExpressRoute 및 Power BI에 대한 자세한 내용은 [Power BI 및 ExpressRoute](service-admin-power-bi-expressroute.md)를 참조하세요.

## <a name="next-steps"></a>다음 단계
[온-프레미스 데이터 게이트웨이](service-gateway-onprem.md)  
[온-프레미스 데이터 게이트웨이 심층 분석](service-gateway-onprem-indepth.md)  
[온-프레미스 데이터 게이트웨이 문제 해결](service-gateway-onprem-tshoot.md)  
궁금한 점이 더 있나요? [Power BI 커뮤니티를 이용하세요.](http://community.powerbi.com/)

