---
title: 클라이언트 응용 프로그램 및 도구 (미리 보기)를 사용 하 여 Power BI 프리미엄 데이터 집합에 연결
description: 클라이언트 응용 프로그램 및 도구에서 Power BI 프리미엄의 데이터 집합에 연결 하는 방법에 설명 합니다.
author: minewiskan
ms.author: owend
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 05/20/2019
ms.custom: seodec18
LocalizationGroup: Premium
ms.openlocfilehash: 063f43cb2345ccb3d1fec5c414100beb8ccde451
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "65941511"
---
# <a name="connect-to-datasets-with-client-applications-and-tools-preview"></a>클라이언트 응용 프로그램 및 도구 (미리 보기)를 사용 하 여 데이터 집합에 연결

Power BI 프리미엄 작업 영역 및 데이터 집합 지원 *읽기 전용* Microsoft 및 타사 클라이언트 응용 프로그램 및 도구에서 연결 합니다. 

> [!NOTE]
> 이 문서는 Power BI 프리미엄 작업 영역 및 데이터 집합에 대 한 읽기 전용 연결 소개만 제공 됩니다. 것 *아닙니다* 프로그래밍 기능, 도구 및 응용 프로그램, 아키텍처 및 작업 영역 및 데이터 집합 관리에 대 한 자세한 정보를 제공 하기 위한 것입니다. 여기에 설명 된 주제 Analysis Services 테이블 형식 모델 데이터베이스 아키텍처 및 관리의 확실 하 게 이해를 해야 합니다.

## <a name="protocol"></a>프로토콜

Power BI 프리미엄을 사용 합니다 [XML for Analysis](https://docs.microsoft.com/bi-reference/xmla/xml-for-analysis-xmla-reference) 클라이언트 응용 프로그램 및 작업 영역 및 데이터 집합을 관리 하는 엔진 간의 통신에 대 한 프로토콜 (XMLA). 이러한 연락 내용은 할는 일반적으로 XMLA 끝점 이라고 합니다. XMLA는 내부적으로 Power BI 의미 체계 모델링, 거 버 넌 스, 수명 주기 및 데이터 관리를 실행 하는 Microsoft Analysis Services 엔진을 사용 하 여 동일한 통신 프로토콜입니다. 

대부분의 클라이언트 응용 프로그램 및 도구 통신 하지 않습니다 명시적으로 엔진을 사용 하 여 XMLA 끝점을 사용 하 여. 대신, MSOLAP, ADOMD 및 AMO와 같은 클라이언트 라이브러리는 XMLA를 사용 하 여 단독으로 통신 하는 엔진 및 클라이언트 응용 프로그램 간의 중개자로 사용 합니다.


## <a name="supported-tools"></a>지원 되는 도구

이러한 도구는 Power BI 프리미엄 작업 영역 및 데이터 집합에 대 한 읽기 전용 액세스를 지원합니다.

**SQL Server Management Studio (SSMS)** -지원 DAX, MDX, XMLA 및 TraceEvent 쿼리 합니다. 18.0 버전이 필요합니다. 다운로드 [여기](https://docs.microsoft.com/sql/ssms/download-sql-server-management-studio-ssms)합니다. 

**SQL Server Profiler** -SSMS 18.0 (미리 보기)에 포함 된이 도구는 제공 추적 및 서버 이벤트 디버깅 합니다. 캡처 및 파일 또는 나중에 분석할 수는 테이블에 각 이벤트에 대 한 데이터를 저장할 수 있습니다. 공식적으로 SQL Server에 대 한 사용 되지 않음 동안 Profiler는 SSMS에 포함 될 계속 하 고 Analysis Services 및 Power BI 프리미엄에 이제는 계속 지원. 자세한 내용은 참조 하세요 [SQL Server Profiler](https://docs.microsoft.com/sql/tools/sql-server-profiler/sql-server-profiler)합니다.

**DAX Studio** -오픈 소스 분석 서비스에 대해 쿼리를 실행 하 고 DAX를 분석 하기 위한 커뮤니티 도구입니다. 버전 2.8.2 필요 이상. 자세한 내용은 참조 하세요 [daxstudio.org](https://daxstudio.org/)합니다.

**Excel 피벗 테이블** -간편 실행 Office 16.0.11326.10000 이상 버전이 필요 합니다.

**제 3 자** -클라이언트 데이터 시각화 응용 프로그램 및 도구에 연결할 수 있는, 쿼리를 포함 하 고 Power BI 프리미엄의 데이터 집합을 사용 합니다. 대부분의 도구에는 MSOLAP 클라이언트 라이브러리의 최신 버전이 필요 하지만 일부 ADOMD를 사용할 수 있습니다.

## <a name="client-libraries"></a>클라이언트 라이브러리

클라이언트 라이브러리는 Power BI 프리미엄 작업 영역에 연결 하는 클라이언트 응용 프로그램 및 도구에 대 한 필요 합니다. Power BI premium에서 Analysis Services에 연결 하는 데 동일한 클라이언트 라이브러리도 지원 됩니다. 세 클라이언트 라이브러리를 설치 하 고 일반 응용 프로그램 업데이트와 함께 업데이트 하는 Excel, SQL Server Management Studio (SSMS) 및 SQL Server Data Tools (SSDT)와 같은 Microsoft 클라이언트 응용 프로그램. 경우에 따라 제 3 자 응용 프로그램 및 도구를 사용 하 여 특히 최신 버전의 클라이언트 라이브러리를 설치 해야 합니다. 클라이언트 라이브러리는 매월 업데이트 됩니다. 자세한 내용은 참조 하세요 [Analysis Services에 연결 하기 위한 클라이언트 라이브러리](https://docs.microsoft.com/azure/analysis-services/analysis-services-data-providers)합니다.

## <a name="connecting-to-a-premium-workspace"></a>프리미엄 작업 영역에 연결

프리미엄 전용 용량에 할당 된 작업 영역에 연결할 수 있습니다. 작업 영역을 전용된 용량에 할당 된 경우 연결 문자열을 URL 형식 

Power BI에서 작업 영역 연결 문자열을 가져오려면 **작업 영역 설정을**의 합니다 **Premium** 탭의 **작업 영역 연결**, 클릭 **복사**.

![작업 영역 연결 문자열](media/service-premium-connect-tools/connect-tools-workspace-connection.png)

Analysis Services 서버 이름을 것 처럼 작업 영역을 해결 하기 위해 다음 URL 형식을 사용 하는 작업 영역 연결 합니다.   
`powerbi://api.powerbi.com/v1.0/[tenant name]/[workspace name]` 

예를 들어 `powerbi://api.powerbi.com/v1.0/contoso.com/Sales Workspace`
> [!NOTE]
> `[workspace name]` 대 소문자를 구분 되며 공백을 포함할 수 있습니다. 

### <a name="to-connect-in-ssms"></a>SSMS에서 연결

**서버에 연결** > **서버 유형**선택 **Analysis Services**합니다. **서버 이름**, URL을 입력 합니다. **인증**를 선택 **Active Directory-MFA 지원을 통한 유니버설**를 선택한 후 **사용자 이름**, 조직 사용자 ID를 입력 

연결 되 면 작업 영역, Analysis Services 서버로 나타나며이 데이터베이스로 작업 영역에서 데이터 집합 표시 됩니다.  

![SSMS](media/service-premium-connect-tools/connect-tools-ssms.png)

### <a name="initial-catalog"></a>초기 카탈로그

지정 해야 SQL Server Profiler와 같은 일부 도구는 *Initial Catalog*합니다. 작업 영역에서 데이터 집합 (데이터베이스)을 지정 합니다. **서버에 연결**, 클릭 **옵션**합니다. 에 **서버에 연결** 대화의 합니다 **연결 속성** 탭의 **데이터베이스에 연결**, 데이터 집합 이름을 입력 합니다.

### <a name="duplicate-workspace-name"></a>작업 영역 이름이 중복 됩니다.

이름이 같은 다른 작업 영역을 사용 하 여 작업 영역에 연결할 때 다음 오류가 표시 될 수 있습니다. **Powerbi://api.powerbi.com/v1.0/ [테 넌 트 이름]에 연결할 수 없습니다 / [작업 영역 이름].**

작업 영역 이름 외에도이 오류를 해결 하려면 URL의 objectID가 작업 영역에서 복사할 수는 ObjectIDGuid를 지정 합니다. 연결 url의 objectID를 추가 합니다. 예를 들어, ' powerbi://api.powerbi.com/v1.0/myorg/Contoso 판매액-9d83d204-82a9-4b36-98f2-a40099093830'

### <a name="duplicate-dataset-name"></a>데이터 집합 이름이 중복 됩니다.

동일한 작업 영역에서 다른 데이터 집합으로 동일한 이름의 데이터 집합에 연결할 때 데이터 집합 이름으로 데이터 집합 guid를 추가 합니다. 두 데이터 집합 이름을 가져올 수 있습니다 *고* SSMS에서 작업 영역에 연결 하는 경우에 guid입니다. 

### <a name="delay-in-datasets-shown"></a>표시 된 데이터 집합의 지연

작업 영역에 연결할 때 새, 삭제 및 이름이 바뀐 데이터 집합에서 변경 내용을 표시 하는 데 5 분까지 걸릴 수 있습니다. 

### <a name="unsupported-datasets"></a>지원 되지 않는 데이터 집합

다음 데이터 집합 XMLA 끝점을 사용 하 여 액세스할 수 없는 합니다. 이러한 데이터 집합 *것입니다* SSMS 또는 다른 도구에서 작업 영역 아래에 나타납니다. 

- Analysis Services 모델에 라이브 연결을 사용 하 여 데이터 집합입니다. 
- REST API를 사용 하 여 데이터 푸시를 사용 하 여 데이터 집합입니다.
- Excel 통합 문서 데이터 집합입니다. 

다음 데이터 집합은 Power BI 서비스에서 지원 되지 않습니다.   

- Power BI 데이터 집합에 라이브 연결을 사용 하 여 데이터 집합입니다.

## <a name="audit-logs"></a>감사 로그 

XMLA 끝점을 통한 액세스의 Power BI 감사 로그에 기록 됩니다 클라이언트 응용 프로그램 및 도구를 작업 영역에 연결 합니다 **GetWorkspaces** 작업 합니다. 자세한 내용은 참조 하세요 [Power BI 감사](service-admin-auditing.md)합니다.

## <a name="see-also"></a>참고 항목

[Analysis Services 참조](https://docs.microsoft.com/bi-reference/#pivot=home&panel=home-all)   
[SQL Server Management Studio](https://docs.microsoft.com/sql/ssms/sql-server-management-studio-ssms)   
[SQL Server Analysis Services 테이블 형식 프로토콜](https://docs.microsoft.com/openspecs/sql_server_protocols/ms-ssas-t/b98ed40e-c27a-4988-ab2d-c9c904fe13cf)   
[동적 관리 뷰 (Dmv)](https://docs.microsoft.com/sql/analysis-services/instances/use-dynamic-management-views-dmvs-to-monitor-analysis-services)   


궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](https://community.powerbi.com/)
