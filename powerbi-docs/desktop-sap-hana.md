---
title: Power BI Desktop에서 SAP HANA 사용
description: Power BI Desktop에서 SAP HANA 사용
author: davidiseminger
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/15/2020
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 9b205a0ae9b58acf054a9afe43196e77ee404c84
ms.sourcegitcommit: 08f65ea314b547b41b51afef6876e56182190266
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2020
ms.locfileid: "76753115"
---
# <a name="connect-to-sap-hana-databases-in-power-bi-desktop"></a>Power BI Desktop에서 SAP HANA 데이터베이스에 연결

Power BI Desktop을 통해 이제 *SAP HANA* 데이터베이스에 액세스할 수 있습니다. SAP HANA를 사용하려면 Power BI Desktop의 SAP HANA 데이터 연결이 제대로 작동해야 하므로 로컬 클라이언트 컴퓨터에 SAP HANA ODBC 드라이버가 설치되어 있어야 합니다. 필요한 ODBC 드라이버가 들어 있는 [SAP Development Tools](https://tools.hana.ondemand.com/#hanatools)에서 SAP HANA 클라이언트 도구를 다운로드할 수 있습니다. 또는 [SAP 소프트웨어 다운로드 센터](https://support.sap.com/en/my-support/software-downloads.html)에서 다운로드할 수 있습니다. 소프트웨어 포털에서 Windows 컴퓨터용 *SAP HANA CLIENT*를 검색해 보세요. SAP 소프트웨어 다운로드 센터는 구조가 자주 변경되기 때문에 더 구체적인 사이트 탐색 지침은 제공할 수 없습니다.

SAP HANA 데이터베이스에 연결하려면 **데이터 가져오기**를 선택하고 **데이터베이스** > **SAP HANA 데이터베이스**를 선택한 후 **연결**을 선택합니다.

![SAP HANA 데이터베이스, 데이터 대화 상자 가져오기, Power BI Desktop](media/desktop-sap-hana/sap-hana-1.png)

SAP HANA 데이터베이스에 연결할 때 서버 이름을 지정합니다. 그런 다음, 드롭다운 및 입력 상자에서 포트를 지정합니다.

이 릴리스에서는 [DirectQuery](desktop-directquery-sap-hana.md) 모드의 SAP HANA가 Power BI Desktop 및 Power BI 서비스에서 지원됩니다. DirectQuery 모드에서 SAP HANA를 사용하는 보고서를 Power BI 서비스에 게시하고 업로드할 수 있습니다. DirectQuery 모드에서 SAP HANA를 사용하지 않는 경우에도 Power BI 서비스에 보고서를 게시하고 업로드할 수 있습니다.

## <a name="supported-features-for-sap-hana"></a>SAP HANA에 대해 지원되는 기능

이 릴리스에는 다음 목록에 표시된 것처럼 여러 가지 SAP HANA용 기능이 있습니다.

* SAP HANA용 Power BI 커넥터에서는 SAP ODBC 드라이버를 사용하여 가장 적합한 사용자 환경을 제공합니다.

* SAP HANA는 DirectQuery 및 가져오기 옵션을 모두 지원합니다.

* Power BI는 HANA 정보 모델(예: 분석 및 계산 보기)을 지원하고 최적화된 탐색을 제공합니다.

* SAP HANA를 사용하면 직접 SQL 기능을 사용하여 행 및 열 테이블을 연결할 수도 있습니다.

* Power BI에는 HANA 모델에 대해 최적화된 탐색이 포함됩니다.

* Power BI는 SAP HANA 변수 및 입력 매개 변수를 지원합니다.

* Power BI는 HDI 컨테이너 기반 계산 보기를 지원합니다.

  * HDI-컨테이너 기반 계산 뷰에 대한 지원은 Power BI Desktop의 2019년 8월 릴리스에서 공개 미리 보기로 제공됩니다. Power BI에서 HDI-컨테이너 기반 계산 보기에 액세스하려면 Power BI로 사용하는 HANA 데이터베이스 사용자에게 액세스하려는 보기를 저장하는 HDI 런타임 컨테이너에 액세스할 수 있는 권한이 있는지 확인합니다. 이 액세스 권한을 부여하려면 HDI 컨테이너에 액세스할 수 있는 역할을 만듭니다. 그런 다음 Power BI에 사용할 HANA 데이터베이스 사용자에게 역할을 할당합니다. (이 사용자는 평소와 같이 \_SYS\_BI 스키마의 시스템 테이블에서 읽을 수 있는 권한이 있어야 합니다.) 데이터베이스 역할을 만들고 할당하는 방법에 대한 자세한 지침은 공식 SAP 설명서를 참조하세요. [이 SAP 블로그 게시물](https://blogs.sap.com/2018/01/24/the-easy-way-to-make-your-hdi-container-accessible-to-a-classic-database-user/)을 읽는 것이 유용할 수 있습니다.

  * 현재 HDI 기반 계산 보기에 연결된 HANA 변수에 대해서는 몇 가지 제한 사항이 있습니다. 해당 제한 사항은 HANA 쪽의 오류 때문에 발생합니다.
  
    첫째, HDI-컨테이너 기반 계산 보기의 공유 열에 HANA 변수를 적용할 수 없습니다. 이 제한을 해결하려면 HANA 2 버전 37.02 이상으로 업그레이드하거나 HANA 2 버전 42 이상으로 업그레이드하세요. 둘째, 변수 및 매개 변수의 다중 항목 기본값은 현재 Power BI UI에 표시되지 않습니다. SAP HANA의 오류 때문에 이러한 제한이 발생하지만 SAP에서 아직 수정을 발표하지 않았습니다.

## <a name="limitations-of-sap-hana"></a>SAP HANA의 제한 사항

SAP HANA를 사용하는 데는 다음과 같이 몇 가지 제한이 있습니다.

* NVARCHAR 문자열은 최대 4000 유니코드 문자 길이로 잘립니다.
* SMALLDECIMAL은 지원되지 않습니다.
* VARBINARY는 지원되지 않습니다.
* 유효한 날짜는 1899/12/30부터 9999/12/31 사이입니다.

## <a name="next-steps"></a>다음 단계

DirectQuery 및 SAP HANA에 대한 자세한 내용은 다음 리소스를 확인하세요.

* [DirectQuery 및 SAP HANA](desktop-directquery-sap-hana.md)
* [Power BI의 DirectQuery 사용](desktop-directquery-about.md)
* [Power BI 데이터 원본](power-bi-data-sources.md)
* [SAP HANA에 대한 암호화 사용](desktop-sap-hana-encryption.md)
