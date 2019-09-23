---
title: 실시간 데이터에 대한 자동 보존 정책을 사용하는 Power BI API
description: Power BI 서비스의 자동 보존 정책 자세히 알아보기
author: rkarlin
ms.author: rkarlin
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 06/08/2018
ms.openlocfilehash: 07726535246f8b115402373c315062151177d27c
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "61347350"
---
# <a name="automatic-retention-policy-for-real-time-data"></a>실시간 데이터에 대한 자동 보존 정책

Power BI 서비스의 자동 보존 정책은 쿼리 문자열 매개 변수로, 기본 보존 정책이 이전 데이터를 자동으로 정리하는 동시에 대시보드로 지속적으로 이동하는 새 데이터 흐름을 유지할 수 있습니다. 첫 번째 보존 정책은 *FIFO(선입선출)* 라고 합니다. 이 정책을 사용하도록 설정하면 200,000개 행에 도달할 때까지 테이블에 데이터가 수집됩니다. 데이터가 200,000개 행을 초과하면 데이터 세트에서 오래된 행부터 삭제됩니다. 이 경우 최신 데이터 중 200,000~210,000개 행만 유지됩니다.  
  
<center>

![보존 정책](media/api-Automatic-retention-policy-for-real-time-data/retention-policy.png) 

</center>

데이터 세트를 처음 만들 때 보존 정책이 사용하도록 설정됩니다. POST 데이터 세트에 “기본 보존 정책” 쿼리 매개 변수를 추가하고 *basicFIFO*와 동일하게 설정하기만 하면 됩니다.  
  
    POST https://api.powerbi.com/v1.0/myorg/datasets?defaultRetentionPolicy={None | basicFIFO}