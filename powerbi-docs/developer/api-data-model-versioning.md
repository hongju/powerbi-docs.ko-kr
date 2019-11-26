---
title: Power BI 데이터 모델 버전 관리
description: OData 서비스로 노출되는 데이터 모델
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 06/08/2018
ms.openlocfilehash: 89fd2a6c1297abb1d76a30b170b901b41d630f44
ms.sourcegitcommit: c395fe83d63641e0fbd7c98e51bbab224805bbcc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74265683"
---
# <a name="data-model-versioning"></a>데이터 모델 버전 관리

Power BI 데이터 모델 등 OData 서비스에서 노출하는 데이터 모델은 OData 서비스와 해당 클라이언트 간 계약을 정의합니다. 서비스는 기존 클라이언트를 중단하지 않는 범위 내에서만 모델을 확장할 수 있습니다. 속성 제거, 기존 속성 유형 변경과 같이 중요 항목을 변경할 경우 새 모델에 대한 다른 서비스 루트 URL에 새 서비스 버전을 제공해야 합니다.  
  
다음 데이터 모델 추가는 안전한 것으로 간주되며 서비스에서 진입점의 버전을 관리할 필요가 없습니다.  
  
* Null을 허용하거나 기본값이 있는 속성 추가. 기존의 동적 속성과 동일한 이름을 갖는 경우 기존 동적 속성과 동일한 형식(또는 기본 형식)을 가져야 합니다.  
* Null을 허용하거나 컬렉션 값을 갖는 탐색 속성 추가. 기존의 동적 탐색 속성과 동일한 이름을 갖는 경우 기존 동적 탐색 속성과 동일한 형식(또는 기본 형식)을 가져야 합니다.  
* 모델에 새 엔터티 형식 추가  
* 모델에 새 복합 형식 추가  
* 새 엔터티 집합 추가  
* 새 singleton 추가  
* 작업, 함수, 작업 가져오기 또는 함수 가져오기 추가
* Null을 허용하는 작업 매개 변수 추가  
* 형식 정의 또는 열거형 추가  
* 서비스와 올바르게 상호 작용하기 위해 클라이언트에서 이해하지 않아도 되는 모델 요소에 주석 추가  
  
클라이언트는 서비스가 해당 모델에 이러한 증분 변경을 수행할 수 있도록 준비***되어야 합니다***. 특히, 클라이언트는 이전에 서비스에 의해 정의되지 않은 속성 및 파생된 형식을 수신할 준비가 되어야 합니다.  
  
서비스는 인증된 사용자에 따라 해당 데이터 모델을 변경***하지 않아야 합니다***. 데이터 모델이 사용자 또는 사용자 그룹에 종속되는 경우 전체 모델을 제한된 권한의 사용자가 볼 수 있는 모델과 비교할 때 이 섹션에 정의된 대로 모든 변경은 안전한 변경이어야 합니다.  
  
OData 데이터 모델 표준에 대한 자세한 내용은 [OData 버전 4.0 1부: 프로토콜 및 Errata 02](https://docs.oasis-open.org/odata/odata/v4.0/odata-v4.0-part1-protocol.html)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목
[Power BI REST API 개요](https://docs.microsoft.com/rest/api/power-bi/)  