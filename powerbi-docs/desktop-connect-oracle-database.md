---
title: "Oracle 데이터베이스에 연결"
description: "Oracle을 Power BI Desktop에 연결하는 데 필요한 단계 및 다운로드"
services: powerbi
documentationcenter: 
author: davidiseminger
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
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 4126a5f4fc7b8a398d39cad7c14e87e179ab3175
ms.sourcegitcommit: 4217430c3419046c3a90819c34f133ec7905b6e7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2018
---
# <a name="connect-to-an-oracle-database"></a>Oracle 데이터베이스에 연결
**Power BI Desktop**을 사용하여 Oracle 데이터베이스에 연결하기 위해 Power BI Desktop을 실행하는 컴퓨터에 올바른 Oracle 클라이언트 소프트웨어를 설치해야 합니다. 사용하는 Oracle 클라이언트 소프트웨어는 설치한 Power BI Desktop의 버전(**32비트** 버전 또는 **64비트** 버전)에 따라 달라집니다.

**지원 되는 버전**: Oracle 9 이상, Oracle 클라이언트 소프트웨어 8.1.7 이상.

## <a name="determining-which-version-of-power-bi-desktop-is-installed"></a>설치된 Power BI Desktop의 버전 확인
설치된 Power BI Desktop의 버전을 확인하려면 **파일 > 도움말 > 정보**를 선택한 다음, **버전:** 줄을 확인합니다. 다음 이미지에서 64비트 버전의 Power BI Desktop이 설치되었습니다.

![](media/desktop-connect-oracle-database/connect-oracle-database_1.png)

## <a name="installing-the-oracle-client"></a>Oracle 클라이언트 설치
**32비트** 버전의 Power BI Desktop의 경우 다음 링크를 사용하여 **32비트** Oracle 클라이언트를 다운로드 및 설치합니다.

* [Visual Studio(12.1.0.2.4)용 Oracle 개발자 도구와 32비트 ODAC(Oracle Data Access Components)](http://www.oracle.com/technetwork/topics/dotnet/utilsoft-086879.html)

**64비트** 버전의 Power BI Desktop의 경우 다음 링크를 사용하여 **64비트** Oracle 클라이언트를 다운로드 및 설치합니다.

* [Windows x64용 64비트 ODAC 12c 릴리스 4(12.1.0.2.4)](http://www.oracle.com/technetwork/database/windows/downloads/index-090165.html)

## <a name="connect-to-an-oracle-database"></a>Oracle 데이터베이스에 연결
일치하는 Oracle 클라이언트 드라이버를 설치한 후에 Oracle 데이터베이스에 연결할 수 있습니다. 연결하려면 다음 단계를 수행하세요.

1. 데이터 가져오기 창에서 **데이터베이스 > Oracle 데이터베이스**를 선택합니다.
   
   ![](media/desktop-connect-oracle-database/connect-oracle-database_2.png)
2. 나타나는 **Oracle 데이터베이스** 대화 상자에서 서버 이름을 제공하고 **연결**을 선택합니다. SID가 필요한 경우 형식 *ServerName/SID*를 사용하여 지정할 수 있습니다.
   
   ![](media/desktop-connect-oracle-database/connect-oracle-database_3.png)
3. 네이티브 데이터베이스 쿼리를 사용하여 데이터를 가져오려는 경우 **Oracle 데이터베이스** 대화 상자의 **고급 옵션** 섹션을 확장하여 사용할 수 있는 **SQL 문** 상자에서 쿼리를 넣을 수 있습니다.
   
   ![](media/desktop-connect-oracle-database/connect-oracle-database_4.png)
4. Oracle 데이터베이스 정보가 Oracle 데이터베이스 대화 상자에 입력되면(SID 또는 네이티브 데이터베이스 쿼리 등의 선택적 정보 포함) **확인**을 선택하여 연결합니다.
5. Oracle 데이터베이스에서 데이터베이스 사용자 자격 증명을 요구하는 경우 메시지가 표시되면 대화 상자에서 해당 자격 증명을 입력합니다.

