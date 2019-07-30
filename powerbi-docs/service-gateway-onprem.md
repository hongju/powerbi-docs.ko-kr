---
title: 온-프레미스 데이터 게이트웨이
description: Power BI의 온-프레미스 데이터 게이트웨이에 대한 개요입니다. DirectQuery 데이터 원본으로 작업하는 데 이 게이트웨이를 사용할 수 있습니다. 또한 이 게이트웨이를 사용하여 온-프레미스 데이터로 클라우드 데이터 세트를 새로 고칠 수도 있습니다.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
LocalizationGroup: Gateways
ms.date: 07/15/2019
ms.openlocfilehash: 57c4292913a2056ab285716de1e1b83e2313f723
ms.sourcegitcommit: 9d13ef7a257b5006fca5f92acf5b611f5cd143a2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/18/2019
ms.locfileid: "68307092"
---
# <a name="what-is-an-on-premises-data-gateway"></a>온-프레미스 데이터 게이트웨이란?

[!INCLUDE [gateway-rewrite](includes/gateway-rewrite.md)]

온-프레미스 데이터 게이트웨이는 온-프레미스 데이터(클라우드에 없는 데이터)와 Power BI, PowerApps, Microsoft Flow, Azure Analysis Services, Logic Apps를 포함한 Microsoft 클라우드 서비스 간에 빠르고 안전한 데이터 전송을 제공하는 브리지 역할을 합니다. 게이트웨이를 사용하여 조직에서는 데이터베이스와 기타 데이터 원본을 온-프레미스 네트워크에 유지하면서도 클라우드 서비스에서 해당 온-프레미스 데이터를 안전하게 사용할 수 있습니다.

## <a name="how-the-gateway-works"></a>게이트웨이 작동 방법

![게이트웨이 개요](media/service-gateway-onprem/on-premises-data-gateway.png)

게이트웨이의 작동 방식에 대한 자세한 내용은 [온-프레미스 데이터 게이트웨이 아키텍처](/data-integration/gateway/service-gateway-onprem-indepth)를 참조하세요.

## <a name="types-of-gateways"></a>게이트웨이 유형

시나리오마다 각각 두 가지 유형의 게이트웨이가 있습니다.

* **온-프레미스 데이터 게이트웨이** - 여러 사용자가 여러 온-프레미스 데이터 원본에 연결할 수 있습니다. 단일 게이트웨이 설치를 통해 지원되는 모든 서비스와 함께 온-프레미스 데이터 게이트웨이를 사용할 수 있습니다. 이 게이트웨이는 여러 사용자가 여러 데이터 원본에 액세스하는 복잡한 시나리오에 적합합니다.

* **온-프레미스 데이터 게이트웨이(개인 모드)** – 한 사용자가 원본에 연결하며 다른 사용자와 공유할 수 없습니다. 온-프레미스 데이터 게이트웨이(개인 모드)는 Power BI에서만 사용할 수 있습니다. 이 게이트웨이는 보고서를 만드는 유일한 사용자이며 데이터 원본을 다른 사용자와 공유할 필요가 없는 시나리오에 적합합니다.

## <a name="using-a-gateway"></a>게이트웨이 사용

게이트웨이 사용에는 4개의 기본 단계가 있습니다.

1. 로컬 컴퓨터에 [게이트웨이를 다운로드하여 설치](/data-integration/gateway/service-gateway-install)합니다.
2. 방화벽 및 기타 네트워크 요구 사항에 따라 게이트웨이를 [구성](/data-integration/gateway/service-gateway-app)합니다.
3. 다른 네트워크 요구 사항을 관리할 수도 있는 [게이트웨이 관리자를 추가](/data-integration/gateway/service-gateway-manage)합니다.
4. 오류가 발생한 경우 게이트웨이 [문제를 해결](service-gateway-onprem-tshoot.md)합니다.

## <a name="next-steps"></a>다음 단계

* [온-프레미스 데이터 게이트웨이 설치](/data-integration/gateway/service-gateway-install)


궁금한 점이 더 있나요? [Power BI 커뮤니티를 이용하세요.](http://community.powerbi.com/)
