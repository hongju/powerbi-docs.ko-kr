---
title: 온-프레미스 데이터 게이트웨이에서 사용자 지정 데이터 커넥터 사용
description: 온-프레미스 데이터 게이트웨이에서 사용자 지정 데이터 커넥터를 사용할 수 있습니다.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 07/15/2019
LocalizationGroup: Gateways
ms.openlocfilehash: 3c0ef172115dba05deb02d724b663742a2e71c13
ms.sourcegitcommit: 9665bdabce3bfc31f68dd8256b135bfd56f60589
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2019
ms.locfileid: "68832536"
---
# <a name="use-custom-data-connectors-with-the-on-premises-data-gateway"></a>온-프레미스 데이터 게이트웨이에서 사용자 지정 데이터 커넥터 사용

[!INCLUDE [gateway-rewrite](includes/gateway-rewrite.md)]

Power BI용 데이터 커넥터를 사용하면 애플리케이션, 서비스 또는 데이터 원본의 데이터에 연결하고 액세스할 수 있습니다. 사용자 지정 데이터 커넥터를 개발하고 Power BI Desktop에서 사용할 수 있습니다.

Power BI용 사용자 지정 데이터 커넥터를 개발하는 방법에 대한 자세한 내용은 [데이터 커넥터 SDK GitHub 페이지](http://aka.ms/dataconnectors)를 참조하세요. 이 사이트에는 Power BI 및 파워 쿼리에 대한 시작 방법을 설명하는 정보와 샘플이 포함되어 있습니다.

사용자 지정 데이터 커넥터를 사용하는 Power BI Desktop에서 보고서를 빌드할 때 온-프레미스 데이터 게이트웨이를 사용하여 Power BI 서비스의 해당 보고서를 새로 고칠 수 있습니다.

## <a name="enable-and-use-this-capability"></a>이 기능 설정 및 사용

온-프레미스 데이터 게이트웨이의 2018년 7월 이상 버전을 설치하는 경우 온-프레미스 데이터 게이트웨이 앱의 **커넥터** 탭이 표시됩니다. **폴더에서 사용자 지정 데이터 커넥터 로드** 상자에서 게이트웨이 서비스를 실행 중인 사용자가 액세스할 수 있는 폴더를 선택합니다. 기본 사용자는 *NT SERVICE\PBIEgwService*입니다. 게이트웨이는 해당 폴더에 있는 사용자 지정 커넥터 파일을 자동으로 로드합니다. 해당 파일이 데이터 커넥터 목록에 표시됩니다.

![사용자 지정 데이터 커넥터](media/service-gateway-custom-connectors/gateway-onprem-customconnector1.png)

온-프레미스 데이터 게이트웨이(개인 모드)를 사용하는 경우 Power BI 서비스에 Power BI 보고서를 업로드하고 게이트웨이를 사용하여 새로 고칠 수 있습니다.

온-프레미스 데이터 게이트웨이인 경우 사용자 지정 커넥터에 대한 데이터 원본을 만들어야 합니다. Power BI 서비스의 게이트웨이 설정 페이지에서 이 클러스터에서 사용자 지정 커넥터를 사용하도록 허용할 게이트웨이 클러스터를 선택하면 옵션이 표시됩니다. 클러스터의 모든 게이트웨이가 이 옵션을 사용할 수 있도록 2018년 7월 이후 업데이트 릴리스를 설치했는지 확인합니다. 이 클러스터에서 사용자 지정 커넥터를 사용하는 해당 옵션을 선택합니다.

![게이트웨이 클러스터 설정 페이지](media/service-gateway-custom-connectors/gateway-onprem-customconnector2.png)

이 옵션을 사용하는 경우 사용자 지정 커넥터를 이 게이트웨이 클러스터에서 만들 수 있는 사용 가능한 데이터 원본으로 표시합니다. 새 사용자 지정 커넥터를 사용하는 데이터 원본을 만든 후 Power BI 서비스에서 사용자 지정 커넥터를 사용하여 Power BI 보고서를 새로 고칠 수 있습니다.

![데이터 원본 설정 페이지](media/service-gateway-custom-connectors/gateway-onprem-customconnector3.png)

## <a name="considerations-and-limitations"></a>고려 사항 및 제한 사항

* 만든 폴더가 백그라운드 게이트웨이 서비스에 액세스할 수 있는지 확인합니다. 일반적으로 사용자의 Windows 폴더 또는 시스템 폴더 아래에 있는 폴더에는 액세스할 수 없습니다. 온-프레미스 데이터 게이트웨이 앱은 폴더에 액세스할 수 없는 경우 메시지를 표시합니다. 이 명령은 온-프레미스 데이터 게이트웨이(개인 모드)에는 적용되지 않습니다.
* 사용자 지정 커넥터를 온-프레미스 데이터 게이트웨이에서 작업하려면 사용자 지정 커넥터의 코드에서 "TestConnection" 섹션을 구현해야 합니다. 이 섹션은 Power BI Desktop에서 사용자 지정 커넥터를 사용하는 경우에는 필요하지 않습니다. 따라서 커넥터가 Power BI Desktop에서는 작동하지만 게이트웨이에서는 작동하지 않을 수 있습니다. TestConnection 섹션을 구현하는 방법에 대한 자세한 내용은 [이 설명서](https://github.com/Microsoft/DataConnectors/blob/master/docs/m-extensions.md#implementing-testconnection-for-gateway-support)를 참조하세요.

## <a name="next-steps"></a>다음 단계

* [데이터 원본 관리 - Analysis Services](service-gateway-enterprise-manage-ssas.md)  
* [데이터 원본 관리 - SAP HANA](service-gateway-enterprise-manage-sap.md)  
* [데이터 원본 관리 - SQL Server](service-gateway-enterprise-manage-sql.md)  
* [데이터 원본 관리 - Oracle](service-gateway-onprem-manage-oracle.md)  
* [데이터 원본 관리 - 가져오기/예약된 새로 고침](service-gateway-enterprise-manage-scheduled-refresh.md)
* [온-프레미스 데이터 게이트웨이에 대한 프록시 설정 구성](/data-integration/gateway/service-gateway-proxy)
* [Power BI에서 온-프레미스 데이터 원본으로 SSO(Single Sign-On)에 대해 Kerberos 사용](service-gateway-sso-kerberos.md)  

궁금한 점이 더 있나요? [Power BI 커뮤니티](http://community.powerbi.com/)에 질문합니다.
