---
title: Power BI REST API 제한 사항
description: Power BI REST API에는 다음과 같은 제한 사항이 있습니다.
author: markingmyname
manager: kfile
ms.author: maghan
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 06/08/2018
ms.openlocfilehash: df17563d384359fe33123ed87743754bb33bf04d
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2019
ms.locfileid: "54277977"
---
# <a name="power-bi-rest-api-limitations"></a>Power BI REST API 제한 사항  
  
**행을 게시하려면**  
  
* 최대 75개 열
* 최대 75개 테이블
* 단일 POST 행 요청당 최대 10,000개 행  
* 데이터 세트마다 시간당 1,000,000개 행 추가  
* 데이터 세트당 최대 5개 보류 POST 행 요청  
* 데이터 세트마다 분당 120개 POST 행 요청
* 테이블에 250,000개 이상 행이 있는 경우 데이터 세트마다 시간당 120개 POST 행 요청    
* FIFO 데이터 세트의 테이블당 최대 200,000개 행 저장  
* ‘보존 안 함 정책’ 데이터 세트의 테이블당 최대 5,000,000개 행 저장  
* POST 행 작업에서 문자열 열에 대한 값당 4,000자
  
## <a name="see-also"></a>참고 항목

[Azure AD 서비스 제한 및 제한 사항](https://docs.microsoft.com/azure/active-directory/active-directory-service-limits-restrictions)   
[Power BI REST API 개요](https://docs.microsoft.com/rest/api/power-bi/)