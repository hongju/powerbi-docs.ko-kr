---
title: Power BI Desktop에서 Access 및 .XLS 가져오기 문제 해결
description: Power BI Desktop 및 파워 쿼리에서 Access 데이터베이스 및 .XLS 스프레드시트 가져오기 문제 해결
author: davidiseminger
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 10/21/2019
ms.author: davidi
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 83a3cc769ea9451ffa5320710bd0f04934d51393
ms.sourcegitcommit: 6272c4a0f267708ca7d38a45774f3bedd680f2d6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/06/2020
ms.locfileid: "73878993"
---
# <a name="resolve-issues-importing-access-and-xls-files-in-power-bi-desktop"></a>Power BI Desktop에서 액세스 및 .XLS 파일 가져오기 문제 해결

Power BI Desktop에서 Access 데이터베이스 및 초기 버전의 Excel 통합 문서(Excel 97-2003 형식의 .XLS 파일)는 모두 *‘Access 데이터베이스 엔진’* 을 사용합니다. Access 데이터베이스 엔진이 제대로 작동할 수 없게 하는 세 가지 일반적인 상황이 있습니다.

## <a name="situation-1-no-access-database-engine-is-installed"></a>상황 1: Access 데이터베이스 엔진이 설치되어 있지 않음

Power BI Desktop 오류 메시지에 Access 데이터베이스 엔진이 설치되어 있지 않다고 표시되는 경우, Power BI Desktop 버전과 일치하는 32비트 또는 64비트 Access 데이터베이스 엔진 버전을 설치해야 합니다. [다운로드 페이지](https://www.microsoft.com/download/details.aspx?id=13255)에서 Access 데이터베이스 엔진을 설치할 수 있습니다.

>[!NOTE]
>설치된 Access 데이터베이스 엔진 비트 버전이 Microsoft Office 설치의 비트 버전과 다른 경우 Office 애플리케이션은 Access 데이터베이스 엔진을 사용할 수 없습니다.

## <a name="situation-2-the-access-database-engine-bit-version-32-bit-or-64-bit-is-different-from-your-power-bi-desktop-bit-version"></a>상황 2: Access 데이터베이스 엔진 비트 버전(32비트 또는 64비트)이 Power BI Desktop 비트 버전과 다름

이 상황은 설치된 Microsoft Office 버전이 32비트이고 설치된 Power BI Desktop 버전이 64비트일 때 종종 발생합니다. 반대의 상황도 발생할 수 있으며, 두 경우 모두 비트 버전 불일치가 발생합니다. Office 365 구독을 사용하는 경우, [상황 3](#situation-3-trouble-using-access-or-xls-files-with-an-office-365-subscription)에서 다른 문제와 해결 방법을 참조하세요. 다음 솔루션은 이러한 비트 버전 불일치 오류를 해결할 수 있습니다.

### <a name="solution-1"></a>해결 방법 1

Microsoft Office 설치의 비트 버전과 일치하도록 Power BI Desktop의 버전을 변경합니다. 

1. Power BI Desktop의 비트 버전을 변경하려면 Power BI Desktop을 제거한 다음 Office 설치와 일치하는 Power BI Desktop의 버전을 설치합니다. 

1. Power BI Desktop 버전을 선택하려면 Power BI Desktop 다운로드 페이지에서 **고급 다운로드 옵션**을 선택합니다.
   
   ![Power BI Desktop 다운로드 페이지의 고급 다운로드 옵션](media/desktop-access-database-errors/desktop-access-errors-1.png)
   
1. 표시된 다운로드 페이지에서 언어를 선택한 다음 **다운로드** 단추를 선택합니다. 
 
1. 표시된 화면에서 32비트 버전의 PBIDesktop.msi 또는 64비트 버전의 PBIDesktop_x64.msi 옆에 있는 확인란을 선택합니다. 

   다음 스크린샷에서는 64비트 버전이 선택되었습니다.
   
   ![Power BI Desktop 다운로드 유형 선택](media/desktop-access-database-errors/desktop-access-errors-2.png)
   
   >[!NOTE]
   >Power BI Desktop 32비트 버전을 사용하여 큰 데이터 모델을 만드는 경우 메모리 부족 문제가 발생할 수 있습니다.

### <a name="solution-2"></a>해결 방법 2

Power BI Desktop 설치의 비트 버전과 일치하도록 Microsoft Office의 비트 버전을 변경합니다.

1. Microsoft Office 제거

2. Power BI Desktop 설치와 일치하는 Office 버전을 설치합니다.

### <a name="solution-3"></a>해결 방법 3

.XLS 파일(Excel 97-2003 통합 문서)을 열 때 오류가 발생하는 경우 Excel에서 .XLS 파일을 열고 .XLSX 파일 형식으로 저장하여 Access 데이터베이스 엔진의 사용을 방지할 수 있습니다.

### <a name="solution-4"></a>해결 방법 4

앞의 세 가지 해결 방법을 사용할 수 없는 경우 Access 데이터베이스 엔진의 두 버전을 모두 설치할 수 있습니다. 그러나 이 해결 방법은 권장되지 않습니다. 두 버전을 모두 설치하면 Excel용 파워 쿼리 및 Power BI Desktop에서는 이 문제가 해결되지만, 처음 설치된 Access 데이터베이스 엔진의 비트 버전을 자동으로(기본적으로) 사용하는 애플리케이션에서 오류와 문제가 발생합니다. 

Access 데이터베이스 엔진 비트 버전을 모두 설치하려면 다음 단계를 수행합니다.

1. [다운로드 페이지](https://www.microsoft.com/download/details.aspx?id=13255)에서 Access 데이터베이스 엔진 비트 버전을 모두 설치합니다. 

1. */passive* 스위치를 사용하여 각 버전의 Access 데이터베이스 엔진을 실행합니다. 예:
   
       c:\users\joe\downloads\AccessDatabaseEngine.exe /passive
   
       c:\users\joe\downloads\AccessDatabaseEngine_x64.exe /passive

## <a name="situation-3-trouble-using-access-or-xls-files-with-an-office-365-subscription"></a>상황 3: Office 365 구독으로 액세스 또는 XLS 파일을 사용하는 문제

**Office 2013** 또는 **Office 2016** 중 하나의 Office 365 구독을 사용하는 경우 Access 데이터베이스 엔진 공급자는 ‘오직’ Microsoft Office 프로세스만 액세스할 수 있는 가상 레지스트리 위치에 등록됩니다.  따라서 매시업 엔진(비 Office 365 Excel 및 Power BI Desktop을 실행하고 Office 프로세스가 아님)은 Access 데이터베이스 엔진 공급자를 사용할 수 없습니다.

이 상황을 해결하려면 Power BI Desktop 설치 비트 버전과 일치하는 [Access 데이터베이스 엔진 재배포 가능 패키지를 다운로드하고 설치](https://www.microsoft.com/download/details.aspx?id=13255)합니다. 비트 버전에 대한 자세한 내용은 이 문서의 이전 섹션을 참조하세요.

## <a name="other-situations-that-can-cause-import-issues"></a>가져오기 문제가 발생할 수 있는 기타 상황

Access 또는 .XLS 파일로 할 수 있는 문제를 가능한 한 많이 처리하기 위해 노력합니다. 이 문서에서 설명하지 않은 문제가 발생할 경우, 해당 문제에 대한 질문을 [Power BI 지원](https://powerbi.microsoft.com/support/)에 제출해 주세요. 당사는 많은 고객에 영향을 줄 수 있는 문제를 정기적으로 살펴보고 문서에 포함시키고 있습니다.

