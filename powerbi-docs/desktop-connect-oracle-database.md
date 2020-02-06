---
title: Oracle 데이터베이스에 연결
description: Oracle을 Power BI Desktop에 연결하는 데 필요한 단계 및 다운로드
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 11/20/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: c2290963db54f150eed8176c2820c59f8f138666
ms.sourcegitcommit: 02b05932a119527f255e1eacc745a257044e392f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/19/2019
ms.locfileid: "75223308"
---
# <a name="connect-to-an-oracle-database"></a>Oracle 데이터베이스에 연결
Power BI Desktop을 사용하여 Oracle 데이터베이스에 연결하려면 Power BI Desktop을 실행하는 컴퓨터에 올바른 Oracle 클라이언트 소프트웨어를 설치해야 합니다. 사용하는 Oracle 클라이언트 소프트웨어는 설치한 Power BI Desktop 버전이 32비트 또는 64비트인지에 따라 다릅니다.

지원되는 Oracle 버전: 
- Oracle 9 이상
- Oracle 클라이언트 소프트웨어 8.1.7 이상

## <a name="determining-which-version-of-power-bi-desktop-is-installed"></a>설치된 Power BI Desktop의 버전 확인
설치된 Power BI Desktop 버전을 확인하려면 **파일** > **도움말** > **정보**를 선택한 다음 **버전** 줄을 확인합니다. 다음 이미지에서 64비트 버전의 Power BI Desktop이 설치되었습니다.

![Power BI Desktop 버전](media/desktop-connect-oracle-database/connect-oracle-database_1.png)

## <a name="installing-the-oracle-client"></a>Oracle 클라이언트 설치
- Power BI Desktop 32비트 버전의 경우 [32비트 Oracle 클라이언트를 다운로드하여 설치](https://www.oracle.com/technetwork/topics/dotnet/utilsoft-086879.html)합니다.

- Power BI Desktop 64비트 버전의 경우 [64비트 Oracle 클라이언트를 다운로드하여 설치](https://www.oracle.com/technetwork/database/windows/downloads/index-090165.html)합니다.

## <a name="connect-to-an-oracle-database"></a>Oracle 데이터베이스에 연결
일치하는 Oracle 클라이언트 드라이버를 설치한 후에 Oracle 데이터베이스에 연결할 수 있습니다. 연결하려면 다음 단계를 수행하세요.

1. **홈** 탭에서 **데이터 가져오기**를 선택합니다. 

2. 표시되는 **데이터 가져오기** 창에서 **자세히**(필요한 경우)를 선택하고 **데이터베이스** > **Oracle 데이터베이스**를 선택한 다음, **연결**을 선택합니다.
   
   ![Oracle 데이터베이스 연결](media/desktop-connect-oracle-database/connect-oracle-database_2.png)
2. 표시되는 **Oracle 데이터베이스** 대화 상자에서 **서버** 이름을 입력하고 **확인**을 선택합니다. SID가 필요한 경우 *ServerName/SID* 형식으로 지정합니다. 여기서 *SID*는 데이터베이스의 고유 이름입니다. *ServerName/SID* 형식이 작동하지 않으면 *ServerName/ServiceName*을 사용합니다. 여기서 *ServiceName*은 연결 시 사용하는 별칭입니다.


   ![Oracle 서버 이름 입력](media/desktop-connect-oracle-database/connect-oracle-database_3.png)

   > [!TIP]
   > 이 단계에서 연결하는 데 문제가 있는 경우 **서버** 필드에 다음 형식을 사용해 보세요. *(DESCRIPTION=(ADDRESS=(PROTOCOL=TCP)(HOST=host_name)(PORT=port_num))(CONNECT_DATA=(SERVICE_NAME=service_name)))*
   
3. 네이티브 데이터베이스 쿼리를 사용하여 데이터를 가져오려는 경우 **Oracle 데이터베이스** 대화 상자의 **고급 옵션** 섹션을 확장할 때 표시되는 **SQL 문** 상자에 쿼리를 넣습니다.
   
   ![고급 옵션 확장](media/desktop-connect-oracle-database/connect-oracle-database_4.png)
4. **Oracle 데이터베이스** 대화 상자에 SID 또는 네이티브 데이터베이스 쿼리와 같은 선택적 정보를 포함하여 Oracle 데이터베이스 정보를 입력한 후에 **확인**을 선택하여 연결합니다.
5. Oracle 데이터베이스에서 데이터베이스 사용자 자격 증명을 요구하는 경우 메시지가 표시되면 대화 상자에서 해당 자격 증명을 입력합니다.


## <a name="troubleshooting"></a>문제 해결

Microsoft Store에서 Power BI Desktop을 다운로드하면 Oracle 드라이버 문제로 인해 Oracle 데이터베이스에 연결할 수 없게 됩니다. 이 문제가 발생하면 ‘개체 참조가 설정되지 않음’ 오류 메시지가 반환됩니다.  문제를 해결하려면 다음 단계 중 하나를 수행합니다.

* Microsoft Store 대신 [다운로드 센터](https://www.microsoft.com/download/details.aspx?id=58494)에서 Power BI Desktop을 다운로드합니다.

* Microsoft Store의 버전을 사용하려면 로컬 컴퓨터에서 _12.X.X\client_X_의 oraons.dll을 _12.X.X\client_X\bin_에 복사합니다. 여기서 _X_는 버전 및 디렉터리 번호를 나타냅니다.

Oracle 데이터베이스에 연결할 때 Power BI Gateway에 ‘개체 참조가 설정되지 않음’ 오류 메시지가 표시되면 [데이터 원본 관리 - Oracle](service-gateway-onprem-manage-oracle.md)의 지침을 따르세요. 
