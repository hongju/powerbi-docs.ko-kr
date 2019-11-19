---
title: Power BI 질문 및 답변의 제한 사항
description: Power BI 질문 및 답변의 현재 제한 사항
author: mohaali
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 10/18/2019
ms.author: mohaali
ms.openlocfilehash: 9f1beed3408d53a58a0fb725f9d98a4a95bb1b7c
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2019
ms.locfileid: "73874891"
---
# <a name="limitations-of-power-bi-qa"></a>Power BI 질문 및 답변의 제한 사항

Power BI 질문 및 답변에는 현재 몇 가지 제한 사항이 있습니다.

## <a name="data-sources"></a>데이터 원본

### <a name="supported-data-sources"></a>지원되는 데이터 원본

Power BI 질문 및 답변은 Power BI 서비스에서 다음과 같은 데이터 원본 구성을 지원합니다.

- 가져오기 모드
- Azure Analysis Services에 라이브 연결
- 게이트웨이를 사용하여 SQL Server Analysis Services에 라이브 연결
- Power BI 데이터 세트. Power BI Desktop은 Power BI 데이터 세트를 사용하는 경우 질문 및 답변으로 오류를 보고합니다. 그러나 Power BI 서비스에 보고서를 게시하면 오류가 사라집니다.

이러한 각 구성에서 행 수준 보안도 지원됩니다.

### <a name="data-sources-not-supported"></a>지원되지 않는 데이터 원본

Power BI 질문 및 답변은 현재 다음과 같은 구성을 지원하지 않습니다.

- 모든 데이터 원본 형식을 사용한 개체 수준 보안
- 모든 원본에 대한 DirectQuery 이 구성을 지원하는 대체 방법은 DirectQuery를 사용하는 Azure Analysis Services와의 라이브 연결을 이용하는 것입니다.
- 복합 모델
- Reporting Services 

## <a name="tooling-limitations"></a>도구 제한 사항

사용자는 새로운 도구 대화 상자를 사용하여 질문 및 답변의 자연어를 사용자 지정하고 개선할 수 있습니다. 도구에 대한 자세한 내용은 [질문 및 답변 도구 소개](q-and-a-tooling-intro.md)를 참조하세요.

## <a name="review-question-limitations"></a>질문 검토 제한 사항

질문 검토는 데이터 모델에 대한 질문을 최대 28일 동안만 저장합니다. 새로운 질문 검토 기능을 사용하는 경우 몇 가지 질문이 기록되지 않을 수 있습니다. 이 동작은 의도적인 것으로, 자연어 엔진이 일련의 데이터 정리 단계를 수행하여 사용자의 모든 키 입력이 기록되거나 표시되지 않도록 하기 때문입니다.

테넌트 관리자는 테넌트 관리자 설정을 사용하여 질문 저장 기능을 관리할 수 있습니다. 사용 권한은 보안 그룹을 기반으로 합니다. 

사용자는 **설정** > **일반**을 선택하고 **질문 및 답변에서 발화를 기록하도록 허용**의 선택을 취소하여 질문이 기록되지 않도록 할 수도 있습니다. 

## <a name="teach-qa-limitations"></a>Q&A 교육 제한 사항

Q&A 교육을 사용하면 다음 두 가지 유형의 오류를 수정할 수 있습니다.

- 필드에 단어를 할당합니다.
- 필터 조건에 단어를 할당합니다.

현재, 인식된 용어를 다시 정의하거나 다른 유형의 조건 또는 문구를 정의하는 기능은 지원되지 않습니다. 또한 필터링 조건을 정의할 때 다음을 포함하여 제한된 언어 하위 집합만 사용할 수 있습니다.

- ‘Country’가 ‘USA’임
- ‘Country’가 ‘USA’가 아님
- ‘Weight’ > 2000
- ‘Weight’ = 2000
- ‘Weight’ < 2000

> [!NOTE]
> 질문 및 답변 도구는 가져오기 모드만 지원합니다. 아직 온-프레미스 또는 Azure Analysis Services 데이터 원본에 연결하는 기능은 지원되지 않습니다. 현재 제한 사항은 Power BI의 후속 릴리스에서 제거될 예정입니다.

### <a name="statements-not-supported"></a>지원되지 않는 문

- 조건에 측정값을 사용하는 기능은 현재 지원되지 않습니다. 대신, 측정값을 계산 열로 변환하여 사용할 수 있습니다.
- 다중 조건은 지원되지 않습니다. 대체 방법으로, 다중 조건 문 부울을 평가하는 DAX 계산 열을 만들고 이 필드를 대신 사용합니다.
- 질문 및 답변에서 데이터 하위 집합을 묻는 메시지를 표시할 때 필터 조건을 지정하지 않으면, 전체 문에 빨간색 밑줄이 없더라도 정의를 저장할 수 없습니다.
