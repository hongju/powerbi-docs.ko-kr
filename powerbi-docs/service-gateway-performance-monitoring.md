---
title: 게이트웨이 성능 (공개 미리 보기) 모니터링
description: 이 문서에서는 온-프레미스 데이터 게이트웨이 작업의 성능을 모니터링 하는 방법에 대 한 정보를 제공 합니다.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 05/08/2019
LocalizationGroup: Gateways
ms.openlocfilehash: 8c5f4170383f31ea465ebb7035aebfb53f551982
ms.sourcegitcommit: af2b2238fe77eaa1b2392a19a143a0250b8665cf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "65535370"
---
# <a name="gateway-performance-monitoring-public-preview"></a>게이트웨이 성능 (공개 미리 보기) 모니터링

성능을 모니터링 하려면 게이트웨이 관리자가 일반적으로 수동으로 Windows 성능 모니터 도구를 통해 성능 카운터를 모니터링에 종속 됩니다. 이제 추가 쿼리 로깅 제공 및 [게이트웨이 성능 PBI 템플릿 파일](http://download.microsoft.com/download/D/A/1/DA1FDDB8-6DA8-4F50-B4D0-18019591E182/GatewayPerformanceMonitoring.pbit) 결과 시각화 합니다. 이 기능은 게이트웨이 사용량에 대 한 새 정보를 제공 하 고 느린 성능 쿼리를 해결할 수 있습니다.

> [!NOTE]
> 이 기능은 표준 모드에서 온-프레미스 데이터 게이트웨이에 대해서만 하 고 개인 모드를 대 한 현재 사용할 수 있습니다.

## <a name="enable-performance-logging"></a>성능 로깅 사용

이 기능을 사용 하려면 다음과 같이 변경 하는 *Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll.config* 파일에 "\Program Files\On-프레미스 데이터 게이트웨이" 폴더:

1. 업데이트 **QueryExecutionReportOn** 하 _True_ 게이트웨이 사용 하 여 실행 하는 쿼리에 대 한 추가 로깅을 사용 하도록 설정 합니다. 이 옵션을 사용 하면 쿼리 실행 보고서와 쿼리 실행 집계 보고서 파일을 모두 만듭니다.

   ``` xml
   <setting name="QueryExecutionReportOn" serializeAs="String">
     <value>True</value>
   </setting>
   ```

1. 업데이트 **SystemCounterReportOn** 하 _True_ 메모리 및 CPU 시스템 카운터에 대 한 추가 로깅을 사용 하도록 설정 합니다. 이 옵션을 사용 하면 시스템 카운터 집계 보고서 파일을 만듭니다.

   ```xml
   <setting name="SystemCounterReportOn" serializeAs="String">
     <value>True</value>
   </setting>
   ```

1. 필요에 따라 업데이트할 수 있는 구성 파일에 다른 값이 있습니다.

    - **ReportFilePath**: 3 개의 로그 파일을 저장할 경로 결정 합니다. 기본적으로이 경로 "\Users\PBIEgwService\AppData\Local\Microsoft\On-premises 데이터 gateway\Report" 또는 "Windows\ServiceProfiles\PBIEgwService\AppData\Local\Microsoft\On 온-프레미스 데이터 gateway\Report", OS 버전에 따라 합니다. 하는 경우 서비스 계정을 사용할 게이트웨이에 대 한 이외의 _PBIEgwService_,이 부분에서는 경로 서비스 계정 이름으로 바꿉니다.
    - **ReportFileCount**: 유지할 각 유형의 로그 파일의 수를 결정 합니다. 기본값은 10입니다.
    - **ReportFileSizeInBytes**: 유지 관리 하는 파일의 크기를 결정 합니다. 기본값은 104857600 합니다.
    - **QuerExecutionAggregationTimeInMinutes**: 쿼리 실행 정보를 집계 하는 시간 (분)을 결정 합니다. 기본값은 5입니다.
    - **SystemCounterAggregationTimeInMinutes**: 시스템 카운터를 집계 하는 시간 (분)을 결정 합니다. 기본값은 5입니다.

1. 구성 파일에 변경 내용을 변경한 후 적용 하려면 이러한 구성 값에 대 한 게이트웨이 다시 시작 합니다. 에 대 한 지정 된 위치에서 생성 되는 보고서 파일 표시를 이제 시작 하겠습니다 **ReportFilePath**합니다.

    > [!NOTE]
    > 최대 10 분 정도 걸릴 수 있습니다 및 기간 설정에 대 한 **QuerExecutionAggregationTimeInMinutes** 파일 폴더에 표시 되기 시작 될 때까지 구성 파일에 있습니다.

## <a name="understand-performance-logs"></a>성능 로그 이해

이 기능을 켤 때 3 개의 새 로그 파일 만듭니다.

- 쿼리 실행 보고서
- 쿼리 실행 집계 보고서
- 시스템 카운터 집계 보고서

자세한 쿼리 실행 정보를 포함 하는 쿼리 실행 보고서. 다음 특성을 캡처합니다.

|특성 |설명 |
| ---- | ---- |
|**GatewayObjectId** |게이트웨이에 대 한 고유 식별자입니다. |
|**RequestId** |게이트웨이 요청에 대 한 고유 식별자입니다. 여러 쿼리에 대해 동일한 수 있습니다. |
|**DataSource** |데이터 원본 유형 및 데이터 원본 모두 포함 되어 있습니다. |
|**QueryTrackingId** |쿼리에 대 한 고유 식별자입니다. |  
|**QueryExecutionEndTimeUTC** |쿼리 실행이 완료 되 면 시간입니다. |
|**QueryExecutionDuration**(ms) |쿼리 실행에 대 한 기간입니다. |
|**QueryType** |예를 들어 쿼리-의 형식, 전달 되는 쿼리를 Power BI 새로 고침 DirectQuery 또는 PowerApps 및 Microsoft Flow 쿼리 될 수 있습니다. |
|**DataProcessingEndTimeUTC** |데이터 작업 스풀링, 데이터 검색, 압축, 데이터 처리 및 완료 등과 같은 처리 시간입니다. |
|**DataProcessingDuration**(ms) |데이터 처리 작업 스풀링, 데이터 검색, 압축, 데이터 처리 등의 기간입니다. |
|**성공** |쿼리 성공 또는 실패 여부를 나타냅니다. |
|**ErrorMessage** |쿼리가 실패 하면 오류 메시지를 나타냅니다. |
| | |

쿼리 실행 집계 보고서를 포함 하 여 시간 간격에 대 한 집계 정보를 쿼리할 **GatewayObjectId**, **DataSource**를 **성공**, 및 **QueryType**합니다. 기본값은 5 분, 하지만 아래 설명 된 대로 조정할 수 있습니다. 다음 특성을 캡처합니다.

|특성 |설명 |
| ---- | ---- |
|**GatewayObjectId** |게이트웨이에 대 한 고유 식별자입니다. |
|**AggregationStartTimeUTC** |시작 하는 대 한 쿼리 특성 집계 된 기간입니다. |
|**AggregationEndTimeUTC** |쿼리에 대 한 특성 집계 된 기간의 끝입니다. |
|**DataSource** |데이터 원본 유형 및 데이터 원본 모두 포함 되어 있습니다. |
|**성공** |쿼리 성공 또는 실패 여부를 나타냅니다. |
|**AverageQueryExecutionDuration**(ms) |평균 집계 기간에 대 한 쿼리 실행 시간입니다. |
|**MaxQueryExecutionDuration**(ms) |집계 기간에 대 한 최대 쿼리 실행 시간입니다. |
|**MinQueryExecutionDuration**(ms) |집계 기간에 대 한 최소 쿼리 실행 시간입니다. |
|**QueryType** |예를 들어 쿼리-의 형식, 전달 되는 쿼리를 Power BI 새로 고침 DirectQuery 또는 PowerApps 및 Microsoft Flow 쿼리 될 수 있습니다. |
|**AverageDataProcessingDuration**(ms) |집계 기간에 대해 데이터 검색, 스풀링, 압축, 데이터 처리와 같은 데이터 처리 작업에 대 한 평균 시간입니다. |
|**MaxDataProcessingDuration**(ms) |집계 기간에 대해 스풀링, 데이터 검색, 압축, 데이터 처리 등 데이터 처리 작업에 대 한 최대 시간입니다. |
|**MinDataProcessingDuration**(ms) |집계 기간에 대해 스풀링, 데이터 검색, 압축, 데이터 처리 등 데이터 처리 작업에 대 한 최소 시간입니다. |
|**Count** |쿼리 수입니다. |
| | |

시스템 카운터 집계 보고서는 시간 간격으로 집계 하는 시스템 카운터 값을 포함 합니다. 기본값은 5 분, 하지만 아래 설명 된 대로 조정할 수 있습니다. 다음 특성을 캡처합니다.

|특성 |설명 |
| ---- | ---- |
|**GatewayObjectId** |게이트웨이에 대 한 고유 식별자입니다. |
|**AggregationStartTimeUTC** |시스템 카운터가 집계 된 기간의 시작입니다. |
|**AggregationEndTimeUTC** |집계 된 카운터는 시스템에 대 한 시간 창의 끝입니다. |
|**CounterName** |게이트웨이 매시업 하 여 메모리 및 CPU 사용량 등 전체 컴퓨터에 게이트웨이 호스트 시스템 카운터입니다. |
|**Max** |집계 기간에 대 한 시스템 카운터에 대 한 최대값입니다. |
|**Min** |집계 기간에 대 한 시스템 카운터에 대 한 최소값입니다. |
|**평균** |집계 기간에 대 한 시스템 카운터에 대 한 평균 값입니다. |
| | |

## <a name="visualize-gateway-performance"></a>게이트웨이 성능 시각화

이제 로그 파일에 있는 데이터를 시각화할 수 있습니다.

1. 다운로드 합니다 [게이트웨이 성능 PBI 템플릿](http://download.microsoft.com/download/D/A/1/DA1FDDB8-6DA8-4F50-B4D0-18019591E182/GatewayPerformanceMonitoring.pbit) Power BI desktop을 사용 하 여 엽니다.

1. 열리는 대화 상자에서 폴더 경로에서 값을 일치 하는지 확인 하십시오 **ReportFilePath**합니다.

    ![폴더 경로 대 한 팝업](media/service-gateway-performance-monitoring/gateway-folder-path-pop-up.png)

1. 선택 **부하**, 템플릿 파일을 로그 파일에서 데이터 로드를 시작 합니다. 모든 시각적 개체 다음 채워져야 보고서에서 데이터를 사용 합니다.

1. 필요에 따라 PBIX로이 파일을 저장 하 고 자동 새로 고침에 대 한 서비스에 게시 합니다.

또한 필요에 맞게이 템플릿 파일을 사용자 지정할 수 있습니다. Power BI 템플릿에 대 한 자세한 내용은 참조 [Microsoft Power BI 블로그 게시물](https://powerbi.microsoft.com/en-us/blog/deep-dive-into-query-parameters-and-power-bi-templates/)합니다.