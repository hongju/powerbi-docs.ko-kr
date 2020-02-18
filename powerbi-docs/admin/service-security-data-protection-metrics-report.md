---
title: 데이터 보호 메트릭 보고서
description: 데이터 보호 메트릭 보고서에 대한 자세한 정보
author: paulinbar
manager: rkarlin
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 01/17/2020
ms.author: painbar
LocalizationGroup: Data from files
ms.openlocfilehash: 952f47f60e14932ce4b22dbd01bf60d9d7243c62
ms.sourcegitcommit: 02342150eeab52b13a37b7725900eaf84de912bc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2020
ms.locfileid: "76542154"
---
# <a name="data-protection-metrics-report-preview"></a>데이터 보호 메트릭 보고서(미리 보기)

## <a name="what-is-the-data-protection-metrics-report"></a>데이터 보호 메트릭 보고서란?
데이터 보호 메트릭 보고서는 [Power BI 관리자](../service-admin-role.md)가 테넌트의 데이터 민감도 레이블 사용 및 도입을 모니터링하고 추적하는 데 사용할 수 있는 전용 보고서입니다.

![데이터 보호 메트릭 보고서](./media/service-security-data-protection-metrics-report/protection-metrics-seven-days-1.png)
 
보고서 기능:
* 지난 7일, 30일 또는 90일 동안 테넌트의 일별 민감도 레이블 사용량을 보여 주는 100% 기준 누적 세로 막대형 차트입니다. 이 차트를 사용하면 시간이 지남에 따라 다양한 레이블 형식의 상대적 사용량을 쉽게 추적할 수 있습니다.
* 대시보드, 보고서, 데이터 세트 및 데이터 흐름에 대한 테넌트의 현재 민감도 레이블 사용 상태를 보여 주는 도넛형 차트입니다.
* Power BI 경고, 사용자 위험, 활동 로그 및 기타 정보를 사용할 수 있는 Cloud App Security 포털 링크입니다. 자세한 내용은 [Power BI에서 Microsoft Cloud App Security 컨트롤 사용(미리 보기)](./service-security-using-microsoft-cloud-app-security-controls.md)을 참조하세요.

보고서는 24시간마다 새로 고쳐집니다.

## <a name="viewing-the-data-protection-metrics-report"></a>데이터 보호 메트릭 보고서 보기

보고서를 열고 보려면 [Power BI 관리자 역할](../service-admin-role.md)이 있어야 합니다.
보고서를 보려면 **설정 > 관리 포털**로 이동한 다음 **보호 메트릭(미리 보기)** 을 선택합니다.

![보호 메트릭 관리 포털](./media/service-security-data-protection-metrics-report/protection-metrics-admin-portal.png)
 
 
데이터 보호 메트릭 보고서를 처음 열 때는 로드하는 데 몇 초 정도 걸릴 수 있습니다. **데이터 보호 메트릭(자동으로 생성됨)** 이라는 제목의 보고서 및 데이터 세트는 개인 환경에서 “내 작업 영역”에 생성됩니다. 여기에서 보지 않는 것이 좋습니다. 이 보고서는 전체 기능을 갖춘 보고서가 아닙니다. 대신 위에서 설명된 대로 관리 포털에서 보고서를 보세요.

> [!CAUTION]
> 최신 버전의 보고서가 수시로 롤아웃되며 보고서를 최신 버전으로 업데이트하면 원래 보고서에서 변경한 내용이 덮어쓰기되므로 어떤 방식으로든 보고서나 데이터 세트를 변경하지 마세요.

## <a name="report-updates"></a>보고서 업데이트

향상된 버전의 데이터 보호 메트릭 보고서는 정기적으로 릴리스됩니다. 보고서를 열 때 새 버전을 사용할 수 있는 경우 새 버전을 열 것인지 묻는 메시지가 표시됩니다. “예”라고 대답하면 새 버전의 보고서를 로드하고 이전 버전을 덮어씁니다. 이전 보고서 및/또는 데이터 세트에 대한 모든 변경 내용이 사라집니다. 새 버전을 열지 않도록 선택할 수 있지만, 그럴 경우 새 버전의 향상된 기능의 이점을 활용할 수 없습니다. 
## <a name="notes-and-considerations"></a>참고 사항 및 고려 사항
* 데이터 보호 메트릭 보고서를 성공적으로 생성하려면 테넌트에서 [정보 보호](./service-security-enable-data-sensitivity-labels.md)를 사용하도록 설정하고 [민감도 레이블을 적용해야 합니다](../designer/service-security-apply-data-sensitivity-labels.md). 
* Cloud App Security 정보에 액세스하려면 조직에 적절한 [Cloud App Security 라이선스](https://docs.microsoft.com/power-bi/admin/service-security-using-microsoft-cloud-app-security-controls#microsoft-cloud-app-security-licensing)가 있어야 합니다.
* Power BI 관리자가 아닌 사용자로 데이터 보호 메트릭 보고서의 정보를 공유하려는 경우 이 보고서에는 조직에 대한 중요한 정보가 포함되어 있다는 점에 유의해주세요.
* 데이터 보호 메트릭 보고서는 특별한 종류의 보고서이며 “공유한 항목”, “최근” 및 “즐겨찾기” 목록에 표시되지 않습니다.
## <a name="next-steps"></a>다음 단계
* [Power BI의 데이터 보호(미리 보기)](./service-security-data-protection-overview.md)
* [Power BI에서 Microsoft Cloud App Security 제어 사용(미리 보기)](./service-security-using-microsoft-cloud-app-security-controls.md)
* [Power BI 서비스 관리자 역할 이해](../service-admin-role.md)
* [Power BI에서 데이터 민감도 레이블 사용](./service-security-enable-data-sensitivity-labels.md)
