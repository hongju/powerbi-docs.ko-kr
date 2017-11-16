---
title: "Power BI Report Server의 새로운 기능"
description: "Power BI Report Server의 새로운 기능에 대해 알아봅니다. 주요 기능 영역을 설명하고 새 항목이 출시될 때 업데이트됩니다."
services: powerbi
documentationcenter: 
author: guyinacube
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/31/2017
ms.author: asaxton
ms.openlocfilehash: d351a117307e86c7b0750e9bcdf813b08b28bb0f
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2017
---
# <a name="whats-new-in-power-bi-report-server"></a>Power BI Report Server의 새로운 기능
Power BI Report Server의 새로운 기능에 대해 알아봅니다. 주요 기능 영역을 설명하고 새 항목이 출시될 때 업데이트됩니다.

Power BI Report Server 및 Report Server에 최적화된 Power BI Desktop을 다운로드하려면 [Power BI Report Server를 사용하여 온-프레미스 보고](https://powerbi.microsoft.com/report-server/)로 이동합니다.

![팁](media/whats-new/fyi-tip.png "팁") 현재 릴리스 정보는 [Power BI Report Server - 릴리스 정보](release-notes.md)를 참조하세요.

관련된 "새로운 기능"은 다음을 참조하세요.

* [Power BI 서비스의 새로운 기능](../service-whats-new.md)
* [Power BI Desktop의 새로운 기능](../desktop-latest-update.md)
* [Power BI용 모바일 앱의 새로운 기능](../mobile-whats-new-in-the-mobile-apps.md)
* [Power BI 팀 블로그](https://powerbi.microsoft.com/blog/)

## <a name="october-2017-release"></a>2017년 10월 릴리스
### <a name="power-bi-report-data-sources"></a>Power BI 보고서 데이터 원본
Power BI Report Server에서 Power BI 보고서는 다양한 데이터 원본에 연결할 수 있습니다. 데이터를 가져오고, 데이터 새로 고침을 예약하거나 DirectQuery 또는 SQL Server Analysis Services에 대한 라이브 연결을 사용하여 직접 쿼리할 수 있습니다. 예약된 새로 고침을 지원하는 데이터 원본 및 DirectQuery를 지원하는 데이터 원본 목록은 "Power BI Report Server에서 Power BI 보고서 데이터 원본"을 참조하세요.

### <a name="scheduled-data-refresh-for-imported-data"></a>가져온 데이터에 대한 데이터 새로 고침 예약
Power BI Report Server에서 예약된 데이터 새로 고침을 설정하여 라이브 연결 또는 DirectQuery가 아닌 포함된 모델로 Power BI 보고서에서 데이터를 최신 상태로 유지할 수 있습니다. 포함된 모델을 사용하여 데이터를 가져오므로 원래 데이터 원본에서 연결이 끊어집니다. 데이터를 최신 상태로 유지하도록 업데이트되어야 하며 예약된 새로 고침은 이를 수행하는 방법입니다. "Power BI Report Server에서 Power BI 보고서에 대한 예약된 새로 고침"에 대해 자세히 알아봅니다.

### <a name="editing-power-bi-reports-from-the-server"></a>서버에서 Power BI 보고서 편집
서버에서 Power BI 보고서(.pbix) 파일을 열고 편집할 수 있지만 업로드한 원래 파일을 다시 가져옵니다.  즉, **서버에서 데이터를 새로 고친 경우 파일을 처음 열 때 데이터는 새로 고쳐지지 않습니다**. 변경 내용을 확인하려면 수동으로 로컬에서 새로 고쳐야 합니다.

### <a name="large-file-uploaddownload"></a>큰 파일 업로드/다운로드
최대 2GB 크기의 파일을 업로드할 수 있지만 기본적으로 이 제한은 SSMS(SQL Server Management Studio)의 보고서 서버 설정에서 1GB로 설정되어 있습니다.  이러한 파일은 SharePoint에 대해서와 마찬가지로 데이터베이스에 저장되며 SQL Server 카탈로그에 대한 특별한 구성은 필요하지 않습니다.  

### <a name="accessing-shared-datasets-as-odata-feeds"></a>OData 피드로 공유 데이터 집합에 액세스
OData 피드로 Power BI Desktop에서 공유 데이터 집합에 액세스할 수 있습니다. 자세한 내용은 [Power BI Report Server에서 OData 피드로 공유 데이터 집합에 액세스](access-dataset-odata.md)를 참조하세요.

### <a name="scale-out"></a>확장
이 릴리스에서 확장을 지원합니다. 부하 분산 장치를 사용하고 최상의 환경을 위한 서버 선호도를 설정합니다. 시나리오는 확장에 대해 아직 최적화되지 않았으므로 여러 노드에 걸쳐 잠재적으로 복제된 모델을 볼 수 있습니다. 시나리오는 네트워크 Load Balancer 및 고정 세션 없이 작동합니다. 그러나 모델이 N번 로드되므로 노드에 걸쳐 메모리가 과도하게 사용되는 것뿐만 아니라 모델이 요청 사이에서 새 노드에 도달할 때 스트리밍되므로 성능이 연결 사이에서 저하되는 것을 볼 수 있습니다.  

### <a name="administrator-settings"></a>관리자 설정
관리자는 서버 팜에 대한 SSMS 고급 속성에서 다음 속성을 설정할 수 있습니다.

* EnableCustomVisuals: True/False
* EnablePowerBIReportEmbeddedModels: True/False
* EnablePowerBIReportExportData: True/False
* MaxFileSizeMb: 이제 기본값은 1000입니다.
* ModelCleanupCycleMinutes: 메모리에서 모델을 제거하기 위해 확인하는 주기
* ModelExpirationMinutes: 마지막으로 사용된 시간에 따라 모델 만료 및 모델 제거까지 남은 시간
* ScheduleRefreshTimeoutMinutes: 모델에 대해 적용할 수 있는 데이터 새로 고침 기간 기본적으로 2시간입니다.  하드 상한 제한은 없습니다.

**구성 파일 rsreportserver.config**

```
<Configuration>
  <Service>
    <PollingInterval>10</PollingInterval>
    <IsDataModelRefreshService>false</IsDataModelRefreshService>
    <MaxQueueThreads>0</MaxQueueThreads>
  </Service>
</Configuration>
```

### <a name="developer-api"></a>개발자 API
SSRS 2017에 도입된 개발자 API(REST API)는 Excel 파일 및 .pbix 파일 모두와 함께 작동하도록 Power BI Report Server에 대해 확장되었습니다. 하나의 잠재적인 사용 사례는 프로그래밍 방식으로 서버에서 파일을 다운로드하고, 새로 고친 다음 다시 게시하는 것입니다. 예를 들어, PowerPivot 모델로 Excel 통합 문서를 새로 고칠 수 있는 유일한 방법입니다.

Swagger의 Power BI Report Server 버전에서 업데이트될 큰 파일에 대한 별도의 새로운 API가 있습니다. 

### <a name="sql-server-analysis-services-ssas-and-the-power-bi-report-server-memory-footprint"></a>SSAS(SQL Server Analysis Services) 및 Power BI Report Server 메모리 사용 공간
Power BI Report Server는 이제 SSAS(SQL Server Analysis Services)를 내부적으로 호스팅합니다. 예약된 새로 고침과 관련이 없습니다. SSAS 호스팅은 보고서 서버 메모리 사용 공간을 크게 확장합니다. AS.ini 구성 파일을 서버 노드에서 사용할 수 있으므로 SSAS에 익숙한 경우 최대 메모리 제한 및 디스크 캐싱 등을 포함하여 설정을 업데이트할 수 있습니다. 자세한 내용은 [Analysis Services에서 서버 속성](https://docs.microsoft.com/sql/analysis-services/server-properties/server-properties-in-analysis-services)을 참조하세요.

### <a name="viewing-and-interacting-with-excel-workbooks"></a>Excel 통합 문서 보기 및 상호 작용
Excel 및 Power BI에는 업계에서 고유한 도구의 포트폴리오가 포함되어 있습니다. 비즈니스 분석가들이 이를 함께 사용하면 데이터를 더 쉽게 모으고, 셰이프, 분석 및 시각적으로 탐색할 수 있습니다. 웹 포털에서 Power BI 보고서를 보는 것 외에도 비즈니스 사용자는 이제 게시를 위한 단일 위치를 알려주는 Power BI Report Server의 Excel 통합 문서로 동일한 작업을 수행하고, 셀프 서비스 Microsoft BI 콘텐츠를 볼 수 있습니다.

[OOS(Office Online Server)를 Power BI Report Server 미리 보기 환경에 추가하는 방법에 관한 연습](excel-oos.md)을 게시했습니다. 볼륨 라이선스 계정을 사용하는 고객은 볼륨 라이선스 서비스 센터에서 OOS를 무료로 다운로드할 수 있으며, 보기 전용 기능을 확인할 수 있습니다. 구성된 후 사용자는 Excel 통합 문서를 보고 상호 작용할 수 있습니다.

* 외부 데이터 원본 종속성 없음
* 외부 SQL Server Analysis Services 데이터 원본에 대한 라이브 연결
* PowerPivot 데이터 모델 보유

### <a name="support-for-new-table-and-matrix-visuals"></a>새 테이블 및 행렬 시각화 개체에 대한 지원
Power BI Report Server는 이제 새 Power BI 테이블 및 행렬 시각적 개체를 지원합니다. 이러한 시각적 개체를 사용하여 보고서를 작성하려면 2017년 10월 릴리스에 대해 업데이트된 Power BI Desktop 릴리스가 필요합니다. Power BI Desktop(2017년 6월) 릴리스와 함께 설치할 수는 없습니다. Power BI Desktop의 최신 버전은 [Power BI Report Server 다운로드 페이지](https://powerbi.microsoft.com/report-server/)에서 **고급 다운로드 옵션**을 선택합니다.

## <a name="june-2017"></a>2017년 6월
* Power BI Report Server는 GA(일반적으로 사용 가능)합니다.

## <a name="may-2017"></a>2017년 5월
* 사용 가능한 Power BI Report Server 미리 보기
* Power BI 보고서 온-프레미스를 게시하는 기능
  * 사용자 지정 시각적 개체에 대한 지원
  * 앞으로 더 많은 데이터 소스를 사용하여 Analysis Services 라이브 연결에 대해 지원합니다.
  * Power BI Report Server에서 호스팅되는 Power BI 보고서를 표시하도록 업데이트된 Power BI 모바일 앱
* 주석을 사용하여 보고서에서 공동 작업 향상

## <a name="next-steps"></a>다음 단계
[Power BI Report Server 릴리스 정보](release-notes.md)  
[사용자 안내서](user-handbook-overview.md)  
[관리자 안내서](admin-handbook-overview.md)  
[빠른 시작: Power BI Report Server 설치](quickstart-install-report-server.md)  
[보고서 작성기 설치](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder)  
[SSDT(SQL Server Data Tools) 다운로드](http://go.microsoft.com/fwlink/?LinkID=616714)

궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](https://community.powerbi.com/)

