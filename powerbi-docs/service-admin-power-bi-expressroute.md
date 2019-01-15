---
title: Power BI 및 ExpressRoute
description: Power BI 및 ExpressRoute
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 12/03/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 0c4618150094a4eabb0dc9745e9ac93e4f342ff1
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2019
ms.locfileid: "54291099"
---
# <a name="power-bi-and-expressroute"></a>Power BI 및 ExpressRoute

**ExpressRoute**는 Azure 데이터 센터(Power BI가 위치함)와 온-프레미스 인프라 간의 개인 연결을 만들거나 Azure 데이터 센터와 공동 배치 환경 간에 개인 연결을 만들 수 있게 해주는 Azure 서비스입니다.

**Power BI** 및 **ExpressRoute**를 사용하여 조직에서 Power BI에 (또는 ISP의 공동 배치 기능을 사용하여) 네트워크 연결을 만들 수 있으며 이는 인터넷을 우회하여 중요한 Power BI 데이터 및 연결의 보안을 강화합니다.

자세한 내용은 [ExpressRoute 개요](/azure/expressroute/expressroute-introduction)를 참조하세요. Power BI는 Power BI가 공용 인터넷을 통해 데이터를 가져오거나 전송하는 ExpressRoute와 호환됩니다(몇 가지 예외가 있음). Power BI에서 사용하는 URL 목록은 [Power BI URL](power-bi-whitelist-urls.md)을 참조하세요.

![ExpressRoute 다이어그램](media/service-admin-power-bi-expressroute/pbi_expressroute_1.png)