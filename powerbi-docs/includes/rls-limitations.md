---
author: mgblythe
ms.service: powerbi
ms.topic: include
ms.date: 09/13/2019
ms.author: mblythe
ms.openlocfilehash: b2be085c48b303304d46ea93c272e6a860143c51
ms.sourcegitcommit: a97c0c34f888e44abf4c9aa657ec9463a32be06f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2019
ms.locfileid: "71074861"
---
## <a name="limitations"></a>제한 사항

다음은 클라우드 모델의 행 수준 보안에 대한 현재 제한 목록입니다.

* 이전에 Power BI 서비스에 역할 및 규칙을 정의한 경우 Power BI Desktop에서 이를 다시 생성해야 합니다.

* Power BI Desktop으로 생성된 데이터 세트에서만 RLS를 정의할 수 있습니다. Excel로 만든 데이터 세트에 RLS를 사용하려는 경우 먼저 파일을 Power BI Desktop(PBIX) 파일로 변환해야 합니다. [자세히 알아보기](../desktop-import-excel-workbooks.md)

* ETL 및 DirectQuery 연결만이 지원됩니다. Analysis Services에 대한 라이브 연결은 온-프레미스 모델에서 처리됩니다.

* 현재 Cortana는 RLS로 지원되지 않습니다.

## <a name="known-issues"></a>알려진 문제

Power BI Desktop에서 이전에 게시된 보고서를 게시하려고 하면 오류 메시지가 표시되는 알려진 문제가 있습니다. 시나리오는 다음과 같습니다.

1. Anna에게는 Power BI 서비스에 게시된 데이터 세트와 구성된 RLS가 있습니다.

1. Anna는 Power BI Desktop에서 보고서를 업데이트하고 다시 게시합니다.

1. Anna는 오류를 받습니다.

**해결 방법:** 이 문제가 해결될 때까지 Power BI 서비스에서 Power BI Desktop 파일을 다시 게시합니다. **데이터 가져오기** > **파일**을 선택하여 이를 수행할 수 있습니다.
