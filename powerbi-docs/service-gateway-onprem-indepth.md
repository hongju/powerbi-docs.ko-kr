---
title: 온-프레미스 데이터 게이트웨이 심층 분석
description: 이 문서에서는 온-프레미스 게이트웨이에 대해 자세히 살펴봅니다. Analysis Services로 작업 시 서비스가 Azure Active Directory 및 로컬 Active Directory에서 작동하는 방식을 살펴봅니다.
author: mgblythe
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 07/15/2019
ms.author: mblythe
LocalizationGroup: Gateways
ms.openlocfilehash: e8807feeccccebab8837ac571ae4340c5c0c9b1a
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2019
ms.locfileid: "73881585"
---
# <a name="on-premises-data-gateway-in-depth"></a>온-프레미스 데이터 게이트웨이 심층 분석

[!INCLUDE [gateway-rewrite](includes/gateway-rewrite.md)]

이 문서의 정보를 Power BI 및 일반 문서에 걸쳐 여러 문서로 이동했습니다. 각 제목 아래의 링크를 따라 관련 콘텐츠를 찾을 수 있습니다.

## <a name="how-the-gateway-works"></a>게이트웨이 작동 방법

[온-프레미스 데이터 게이트웨이 아키텍처](/data-integration/gateway/service-gateway-onprem-indepth)를 참조하세요.

## <a name="list-of-available-data-source-types"></a>사용 가능한 데이터 원본 유형 목록

[데이터 원본 관리](service-gateway-data-sources.md)를 참조하세요.

## <a name="authentication-to-on-premises-data-sources"></a>온-프레미스 데이터 원본에 대한 인증

[온-프레미스 데이터 원본에 대한 인증](/data-integration/gateway/service-gateway-onprem-indepth#authentication-to-on-premises-data-sources)을 참조하세요.

## <a name="authentication-to-a-live-analysis-services-data-source"></a>라이브 Analysis Services 데이터 원본에 대한 인증

[라이브 Analysis Services 데이터 원본에 대한 인증](service-gateway-enterprise-manage-ssas.md#authentication-to-a-live-analysis-services-data-source)을 참조하세요.

## <a name="role-based-security"></a>역할 기반 보안

[역할 기반 보안](service-gateway-enterprise-manage-ssas.md#role-based-security)을 참조하세요.

## <a name="row-level-security"></a>행 수준 보안

[행 수준 보안](service-gateway-enterprise-manage-ssas.md#row-level-security)을 참조하세요.

## <a name="what-about-azure-active-directory"></a>Azure Active Directory의 경우

[Azure Active Directory](/data-integration/gateway/service-gateway-onprem-indepth#azure-active-directory)를 참조하세요.

## <a name="how-do-i-tell-what-my-upn-is"></a>내 UPN이 무엇인지 어떻게 확인합니까?

[내 UPN이 무엇인지 어떻게 확인하나요?](/data-integration/gateway/service-gateway-onprem-indepth#how-do-i-tell-what-my-upn-is)를 참조하세요.

## <a name="map-user-names-for-analysis-services-data-sources"></a>Analysis Services 데이터 원본의 사용자 이름 매핑

[Analysis Services 데이터 원본의 사용자 이름 매핑](service-gateway-enterprise-manage-ssas.md#map-user-names-for-analysis-services-data-sources)을 참조하세요.

## <a name="synchronize-an-on-premises-active-directory-with-azure-active-directory"></a>Azure Active Directory와 온-프레미스 Active Directory 동기화

[Azure Active Directory와 온-프레미스 Active Directory 동기화](/data-integration/gateway/service-gateway-onprem-indepth#synchronize-an-on-premises-active-directory-with-azure-active-directory)를 참조하세요.

## <a name="what-to-do-next"></a>다음을 수행하려면 어떻게 합니까?

데이터 원본에 대한 문서를 참조하세요.

[데이터 원본 관리](service-gateway-data-sources.md)
[데이터 원본 관리 - Analysis Services](service-gateway-enterprise-manage-ssas.md)  
[데이터 원본 관리 - SAP HANA](service-gateway-enterprise-manage-sap.md)  
[데이터 원본 관리 - SQL Server](service-gateway-enterprise-manage-sql.md)  
[데이터 원본 관리 - Oracle](service-gateway-onprem-manage-oracle.md)  
[데이터 원본 관리 - 가져오기/예약된 새로 고침](service-gateway-enterprise-manage-scheduled-refresh.md)  

## <a name="where-things-can-go-wrong"></a>문제가 발생할 수 있는 경우

[온-프레미스 데이터 게이트웨이 문제 해결](/data-integration/gateway/service-gateway-tshoot) 및 [게이트웨이 문제 해결 - Power BI](service-gateway-onprem-tshoot.md)를 참조하세요.

## <a name="sign-in-account"></a>로그인 계정

[로그인 계정](/data-integration/gateway/service-gateway-onprem-indepth#sign-in-account)을 참조하세요.

## <a name="windows-service-account"></a>Windows 서비스 계정

[온-프레미스 데이터 게이트웨이 서비스 계정 변경](/data-integration/gateway/service-gateway-service-account)을 참조하세요.

## <a name="ports"></a>포트

[포트](/data-integration/gateway/service-gateway-communication#ports)를 참조하세요.

## <a name="forcing-https-communication-with-azure-service-bus"></a>HTTPS가 Azure Service Bus와 통신하도록 강제 적용

[HTTPS가 Azure Service Bus와 통신하도록 강제 적용](/data-integration/gateway/service-gateway-communication#force-https-communication-with-azure-service-bus)을 참조하세요.

## <a name="support-for-tls-12"></a>TLS 1.2에 대한 지원

[게이트웨이 트래픽에 대한 TLS 1.2](/data-integration/gateway/service-gateway-communication#tls-12-for-gateway-traffic)를 참조하세요.

## <a name="how-to-restart-the-gateway"></a>게이트웨이를 다시 시작하는 방법

[게이트웨이 다시 시작](/data-integration/gateway/service-gateway-restart)을 참조하세요.

## <a name="next-steps"></a>다음 단계

[온-프레미스 데이터 게이트웨이란?](service-gateway-onprem.md)

궁금한 점이 더 있나요? [Power BI 커뮤니티를 이용하세요.](https://community.powerbi.com/)