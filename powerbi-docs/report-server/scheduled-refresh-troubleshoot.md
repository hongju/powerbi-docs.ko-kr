---
title: Power BI Report Server에서 예약된 새로 고침 문제 해결
description: 이 문서에서는 Power BI Report Server에서 예약된 새로 고침의 문제 해결에 사용할 수 있는 리소스를 설명합니다.
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 11/01/2017
ms.author: maghan
ms.openlocfilehash: 3aa4047f5a4b0146c534a5734d8d13a42c46fe58
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2019
ms.locfileid: "54287810"
---
# <a name="troubleshoot-scheduled-refresh-in-power-bi-report-server"></a>Power BI Report Server에서 예약된 새로 고침 문제 해결
이 문서에서는 Power BI Report Server에서 예약된 새로 고침의 문제 해결에 사용할 수 있는 리소스를 설명합니다.

문제가 발생하면 이 문서는 도움을 주는 정보로 업데이트됩니다.

## <a name="common-issues"></a>일반적인 문제
보고서에 대한 새로 고침을 예약하려고 할 때 직면하는 보다 일반적인 문제는 다음과 같습니다. 

### <a name="driver-related-problems"></a>드라이버 관련 문제
다른 데이터 원본에 연결하려면 성공적으로 연결하기 위해 설치해야 하는 타사 드라이버가 필요할 수 있습니다. Power BI Desktop을 사용하는 컴퓨터에 설치해야 할 뿐만 아니라 보고서 서버에 드라이버가 설치되었는지도 확인해야 합니다.

드라이버는 32비트 및 64비트로 제공될 수도 있습니다. Power BI Report Server는 64비트이므로 64비트 드라이버를 설치해야 합니다.

타사 드라이버를 설치하고 구성하는 방법에 대한 자세한 내용은 제조업체를 참조하세요.

### <a name="memory-pressure"></a>메모리 부족
보고서에 처리하고 렌더링할 더 많은 메모리가 필요한 경우 메모리 부족이 발생할 수 있습니다. 보고서에서 새로 고침 예약은 컴퓨터에서 많은 양의 메모리를 요구할 수 있습니다. 특히 큰 보고서의 경우에 그렇습니다. 보고서 오류뿐만 아니라 보고서 서버 자체의 잠재적 작동 중단으로 메모리 부족이 발생할 수 있습니다.

메모리 부족이 지속적으로 발생하는 경우 리소스의 부하를 분산시키기 위해 보고서 서버의 확장된 배포를 살펴볼 가치가 있습니다. 지정된 보고서 서버가 rsreportserver.config 내의 `IsDataModelRefreshService` 설정으로 데이터 새로 고침에 대해 사용되는지 정의할 수도 있습니다. 이 설정을 사용하여 하나 이상의 서버를 요청 시 보고서를 처리할 프런트 엔드 서버가 되도록 정의하고 다른 서버 집합을 예약된 새로 고침에만 사용하도록 할 수 있습니다.

Analysis Services 인스턴스를 모니터링하는 방법에 대한 자세한 내용은 [Analysis Services 인스턴스 모니터링](https://docs.microsoft.com/sql/analysis-services/instances/monitor-an-analysis-services-instance)을 참조하세요.

Analysis Services 내의 메모리 설정에 대한 자세한 내용은 [메모리 속성](https://docs.microsoft.com/sql/analysis-services/server-properties/memory-properties)을 참조하세요.

### <a name="kerberos-configuration"></a>Kerberos 구성
Windows 자격 증명으로 데이터 원본에 연결할 때 성공적으로 연결하기 위해 Kerberos 제한된 위임을 구성해야 할 수 있습니다. Kerberos 제한된 위임을 구성하는 방법에 대한 자세한 내용은 [Kerberos를 구성하여 Power BI 보고서 사용](configure-kerberos-powerbi-reports.md)을 참조하세요.

## <a name="known-issues"></a>알려진 문제
알려진 문제에 대한 정보가 사용 가능해질 때 여기에 나열됩니다.

## <a name="configuration-settings"></a>구성 설정
다음 설정은 예약된 새로 고침에 영향을 주는 데 사용할 수 있습니다. SSMS(SQL Server Management Studio) 내에서 설정된 설정은 확장 배포 내의 모든 보고서 서버에 적용됩니다. rsreportserver.config 내에서 구성된 설정은 설정된 특정 서버에 대한 것입니다.

**SSMS 내 설정:**

| 설정 | 설명 |
| --- | --- |
| MaxFileSizeMb |업로드된 보고서에 대한 최대 파일 크기입니다. 기본값은 1000MB(1GB)입니다. 최대값은 2000MB(2GB)입니다. |
| ModelCleanupCycleMinutes |메모리에서 제거하기 위해 모델이 확인되는 빈도를 정의합니다. 기본값은 15분입니다. |
| ModelExpirationMinutes |마지막으로 사용된 시간에 따라 모델 만료 및 모델이 제거될 때까지 남은 시간을 정의합니다. 기본값은 60분입니다. |
| ScheduleRefreshTimeoutMinutes |데이터 새로 고침이 모드에 대해 적용될 수 있는 기간을 정의합니다. 기본값은 120분입니다. 상한 제한은 없습니다. |

**rsreportserver.config 내 설정:**

```
<Configuration>
    <Service>
        <PollingInterval>10</PollingInterval>
        <IsDataModelRefreshService>false</IsDataModelRefreshService>
        <MaxQueueThreads>0</MaxQueueThreads>
    </Service>
</Configuration>
```

## <a name="tools-for-troubleshooting"></a>문제 해결을 위한 도구
### <a name="logs-relevant-for-scheduled-refresh-of-power-bi-reports"></a>Power BI 보고서의 예약된 새로 고침에 관련된 로그
예약된 새로 고침에 대한 정보를 저장하는 로그 파일은 RSPowerBI_ 로그입니다. 보고서 서버 설치 위치의 LogFiles 폴더에 있습니다. 

```
C:\Program Files\Microsoft Power BI Report Server\PBIRS\LogFiles\RSPowerBI_*.log
```

**오류 조건**

```
2017-10-20 02:00:09.5188|ERROR|744|Error Processing Data Model Refresh: SessionId: e960c25e-ddd4-4763-aa78-0e5dceb53472, Status: Error Model can not be refreshed because not all the data sources are embedded, Exception Microsoft.PowerBI.ReportServer.AsServer.InvalidDataSourceException: Model can not be refreshed because not all the data sources are embedde
   at Microsoft.PowerBI.ReportServer.WebHost.EventHandler.AnalysisServicesDataRefresh.CanModelRefresh(IEnumerable`1 dataSources)
   at Microsoft.PowerBI.ReportServer.WebHost.EventHandler.DataRefreshScope.<>c__DisplayClass7.<ExecuteActionWithLogging>b__5()
   at Microsoft.PowerBI.ReportServer.WebHost.EventHandler.DataRefreshScope.<ExecuteFuncWithLogging>d__1`1.MoveNext()
```

***새로 고침 성공***

```
2017-10-25 15:23:41.9370|INFO|6|Handling event with data: TimeEntered: 10/25/2017 8:23:41 PM, Type: Event, SessionId: 46d398db-0b1f-49d8-b7bd-c5461c07ec7a, EventType: DataModelRefresh
2017-10-25 15:23:41.9370|INFO|6|Processing Data Model Refresh: SessionId: 46d398db-0b1f-49d8-b7bd-c5461c07ec7a, Status: Starting Data Refresh.
2017-10-25 15:23:41.9370|INFO|6|Processing Data Model Refresh: SessionId: 46d398db-0b1f-49d8-b7bd-c5461c07ec7a, Status: Starting Retrieving PBIX AsDatabaseInfo.
2017-10-25 15:23:42.7134|INFO|6|Processing Data Model Refresh: SessionId: 46d398db-0b1f-49d8-b7bd-c5461c07ec7a, Status: Starting Verifying all the data sources are embedded.
2017-10-25 15:23:42.7134|INFO|6|Processing Data Model Refresh: SessionId: 46d398db-0b1f-49d8-b7bd-c5461c07ec7a, Status: Starting Verifying connection strings are valid.
2017-10-25 15:23:42.7134|INFO|6|Processing Data Model Refresh: SessionId: 46d398db-0b1f-49d8-b7bd-c5461c07ec7a, Status: Starting Streaming model to Analysis Server.
2017-10-25 15:23:42.7603|INFO|6|Processing Data Model Refresh: SessionId: 46d398db-0b1f-49d8-b7bd-c5461c07ec7a, Status: Starting Refreshing the model.
2017-10-25 15:23:51.5258|INFO|6|Processing Data Model Refresh: SessionId: 46d398db-0b1f-49d8-b7bd-c5461c07ec7a, Status: Starting Removing credentials from the model.
2017-10-25 15:23:51.6508|INFO|6|Processing Data Model Refresh: SessionId: 46d398db-0b1f-49d8-b7bd-c5461c07ec7a, Status: Starting Saving model to the catalog.
```

**잘못된 자격 증명**

```
2017-10-20 08:22:01.5595|INFO|302|Processing Data Model Refresh: SessionId: 22cd9ec3-b21a-4eb1-81ae-15fac8d379ea, Status: Starting Refreshing the model.
2017-10-20 08:22:02.3758|ERROR|302|Error Processing Data Model Refresh: SessionId: 22cd9ec3-b21a-4eb1-81ae-15fac8d379ea, Status: Error Failed to refresh the model, Exception Microsoft.AnalysisServices.OperationException: Failed to save modifications to the server. Error returned: 'The credentials provided for the SQL source are invalid. (Source at rosecatalog;reportserver.). The exception was raised by the IDbCommand interface.
'.
   at Microsoft.AnalysisServices.Tabular.Model.SaveChanges(SaveOptions saveOptions)
   at Microsoft.PowerBI.ReportServer.AsServer.TOMWrapper.RefreshModel(Database database)
   at Microsoft.PowerBI.ReportServer.AsServer.AnalysisServicesServer.RefreshDatabase(String databaseName, IEnumerable`1 dataSources)
   at Microsoft.PowerBI.ReportServer.WebHost.EventHandler.AnalysisServicesDataRefresh.RefreshDatabase(AsDatabaseInfo asDatabaseInfo)
   at Microsoft.PowerBI.ReportServer.WebHost.EventHandler.DataRefreshScope.<>c__DisplayClass7.<ExecuteActionWithLogging>b__5()
   at Microsoft.PowerBI.ReportServer.WebHost.EventHandler.DataRefreshScope.<ExecuteFuncWithLogging>d__1`1.MoveNext()
2017-10-20 08:22:02.4588|ERROR|302|Error Processing Data Model Refresh: SessionId: 22cd9ec3-b21a-4eb1-81ae-15fac8d379ea, Status: Error Failed Data Refresh, Exception Microsoft.AnalysisServices.OperationException: Failed to save modifications to the server. Error returned: 'The credentials provided for the SQL source are invalid. (Source at rosecatalog;reportserver.). The exception was raised by the IDbCommand interface.
'.
   at Microsoft.PowerBI.ReportServer.WebHost.EventHandler.DataRefreshScope.ExecuteActionWithLogging(Action methodToExecute, String description, String localizedDescription, String messageInFailure, RefreshInfo refreshInfo, DataAccessors dataAccessors, ReportEventType operation, Int64 size, Boolean isDataRetrieval, Boolean showInExecutionLog)
   at Microsoft.PowerBI.ReportServer.WebHost.EventHandler.AnalysisServicesDataRefresh.RefreshData(RefreshInfo refreshInfo)
   at Microsoft.PowerBI.ReportServer.WebHost.EventHandler.DataRefreshScope.<>c__DisplayClass7.<ExecuteActionWithLogging>b__5()
   at Microsoft.PowerBI.ReportServer.WebHost.EventHandler.DataRefreshScope.<ExecuteFuncWithLogging>d__1`1.MoveNext()
```

#### <a name="enabling-verbose-logging"></a>자세한 정보 로깅 사용
Power BI Report Server에서 자세한 정보 로깅을 사용하는 것은 SQL Server Reporting Services의 경우와 동일합니다.

1. `<install directory>\PBIRS\ReportServer\bin\ReportingServicesService.exe.config` 엽니다.
2. `<system.diagnostics>` 아래에서 **DefaultTraceSwitch**를 **4**로 변경합니다.
3. `<RStrace>` 아래에서 **구성 요소**를 **모두:4**로 변경합니다. 

### <a name="executionlog"></a>ExecutionLog
Power BI 보고서가 렌더링되거나 새로 고침 예약 계획이 실행될 때마다 새 항목이 데이터베이스의 실행 로그에 추가됩니다. 이 항목은 보고서 서버 카탈로그 데이터베이스 내의 **ExecutionLog3** 보기에서 사용할 수 있습니다.

Power BI 보고서에 대한 실행 로그 항목은 다른 보고서 유형의 항목과 다릅니다.

* TimeRendering 열은 항상 0입니다. Power BI 보고서의 렌더링이 서버에서가 아닌 브라우저에서 발생합니다.
* 2가지 요청 유형 및 후속 항목 작업이 있습니다.
  * **대화형**: 보고서를 볼 때마다
    * **ASModelStream**: 데이터 모델이 카탈로그에서 Analysis Services로 스트림되는 경우
    * **ConceptualSchema**: 사용자가 보고서 보기를 클릭하는 경우
    * **QueryData**: 데이터가 클라이언트에서 요청될 때마다
  * **캐시 새로 고침**: 새로 고침 예약 계획이 실행될 때마다
    * **ASModelStream**: 데이터 모델이 카탈로그에서 Analysis Services로 스트림될 때마다
    * **DataRefresh**: 데이터가 하나 이상의 데이터 원본에서 새로 고쳐질 때마다
    * **SaveToCatalog**: 데이터 모델이 카탈로그로 다시 저장될 때마다

## <a name="analysis-services"></a>Analysis Services
문제 진단을 위해 Analysis Services를 수정하거나 메모리 제한을 조정하려는 경우가 있을 수 있습니다.

> [!IMPORTANT]
> 이러한 설정은 보고서 서버를 업그레이드하는 언제든지 다시 설정됩니다. 변경 내용의 복사본을 유지하고 필요한 경우 다시 적용해야 합니다.
> 
> 

### <a name="install-location"></a>설치 위치
Power BI Report Server 및 Analysis Services에 대한 기본 위치는 다음입니다.

`C:\Program Files\Microsoft Power BI Report Server\PBIRS\ASEngine`

### <a name="configuring-analysis-services-settings-msmdsrvini"></a>Analysis Services 설정 구성(msmdsrv.ini)
`<install directory>\PBIRS\ASEngine` 디렉터리에서 Analysis Services의 서로 다른 설정을 제어하는 데 사용할 수 있는 *msmdsrv.ini* 파일을 찾을 수 있습니다. 이 파일을 열 때 이 파일에 msmdsrv.ini 파일에서 기대하는 모든 설정이 없는 것을 즉시 알게 됩니다. 

이는 Power BI Report Server에서 실행되는 실제 Analysis Services 프로세스가 `<install directory>\PBIRS\ASEngine\workspaces`에서 시작되기 때문입니다. 해당 폴더에서 익숙한 전체 *msmdsrv.ini* 파일을 찾을 수 있습니다. Analysis Services 프로세스가 시작될 때마다 다시 작성되므로 작업 영역 폴더 내의 파일을 수정하지 않는 것은 중요합니다. 설정을 제어하려면 `<install directory>\PBIRS\ASEngine` 디렉터리에서 msmdsrv.ini를 수정하여 수행하세요.

다음 설정은 Analysis Services 프로세스가 시작될 때마다 다시 설정됩니다. 해당 항목에 적용한 변경 내용은 무시됩니다.

* ConfigurationSettings\PrivateProcess
* ConfigurationSettings\DataDir
* ConfigurationSettings\LogDir
* ConfigurationSettings\TempDir
* ConfigurationSettings\BackupDir
* ConfigurationSettings\AllowedBrowsingFolders
* ConfigurationSettings\CrashReportsFolder
* ConfigurationSettings\ExtensionDir
* ConfigurationSettings\Port
* ConfigurationSettings\DeploymentMode
* ConfigurationSettings\ServerLocation
* ConfigurationSettings\TMCompatabilitySKU
* ConfigurationSettings\FlightRecorder\TraceDefinitionFile

### <a name="profiling-the-local-analysis-services-process"></a>로컬 Analysis Services 프로세스 프로파일링
SQL 프로파일러 추적을 진단 용도로 로컬 Analysis Services 프로세스에서 실행할 수 있습니다. 로컬 Analysis Services 인스턴스에 연결하려면 다음을 수행합니다.

SQL Server Profiler 추적은 [SSMS(SQL Server Management Studio) 다운로드](https://docs.microsoft.com/sql/ssms/download-sql-server-management-studio-ssms)와 함께 포함됩니다.

1. 관리자 권한으로 **SQL Server Profiler**를 시작합니다.
2. **새 추적** 단추를 선택합니다.
3. **서버에 연결** 대화 상자에서 **Analysis Services**를 선택하고 서버 이름에 대해 **localhost:5132**를 입력합니다.
4. **추적 속성** 대화 상자에서 캡처하려는 이벤트를 선택하고 **실행**을 선택합니다.

## <a name="lock-pages-in-memory-windows-privilege"></a>메모리의 페이지 잠금 Windows 권한
Power BI 보고서를 렌더링할 수 없다는 것을 알게 된 경우 **메모리의 페이지 잠금** 권한을 Power BI Report Server를 실행 중인 서비스 계정에 할당하는 것은 도움이 될 수 있습니다. **메모리의 페이지 잠금**을 구성하는 방법에 대한 자세한 내용은 [Analysis Services 서비스 계정에 할당된 Windows 권한](https://docs.microsoft.com/sql/analysis-services/instances/configure-service-accounts-analysis-services#bkmk_winpriv)을 참조하세요.

궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](https://community.powerbi.com/)

