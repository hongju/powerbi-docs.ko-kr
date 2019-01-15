---
title: 데이터 원본 관리 - 가져오기/예약된 새로 고침
description: 해당 게이트웨이에 속한 온-프레미스 데이터 게이트웨이 및 데이터 원본을 관리하는 방법입니다. 이 문서는 가져오기/예약된 새로 고침에서 사용할 수 있는 데이터 원본과 관련된 내용을 제공합니다.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 12/06/2017
ms.author: mblythe
LocalizationGroup: Gateways
ms.openlocfilehash: 8f45fbed0b2c4e5de62f8ef18ee9a552bf05486b
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2019
ms.locfileid: "54293780"
---
# <a name="manage-your-data-source---importscheduled-refresh"></a>데이터 원본 관리 - 가져오기/예약된 새로 고침
온-프레미스 데이터 게이트웨이를 설치한 후에는 게이트웨이와 함께 사용할 수 있는 데이터 원본을 추가해야 합니다. 이 문서에서는 DirectQuery 또는 라이브 연결과 다르게 예약된 새로 고침에 사용되는 게이트웨이 및 데이터 원본으로 작업하는 방법을 살펴봅니다.

## <a name="download-and-install-the-gateway"></a>게이트웨이 다운로드 및 설치
Power BI 서비스에서 게이트웨이를 다운로드할 수 있습니다. **다운로드** > **데이터 게이트웨이**를 선택하거나 [게이트웨이 다운로드 페이지](https://go.microsoft.com/fwlink/?LinkId=698861)로 이동합니다.

![](media/service-gateway-enterprise-manage-scheduled-refresh/powerbi-download-data-gateway.png)

## <a name="add-a-gateway"></a>게이트웨이 추가
게이트웨이를 추가하려면 해당 환경의 서버에 엔터프라이즈 게이트웨이를 [다운로드](https://go.microsoft.com/fwlink/?LinkId=698863)하여 설치하기만 하면 됩니다. 게이트웨이를 설치하면 **게이트웨이 관리**아래의 게이트웨이 목록에 표시됩니다.

> [!NOTE]
> 하나 이상의 게이트웨이에 대한 관리자가 아닌 경우 **게이트웨이 관리**가 표시되지 않습니다. 이를 위해서는 관리자로 추가되거나 게이트웨이를 설치 및 구성해야 합니다.
> 
> 

## <a name="remove-a-gateway"></a>게이트웨이 제거
게이트웨이를 제거하면 해당 게이트웨이에 속한 모든 데이터 원본도 삭제됩니다.  또한 이러한 데이터 소스를 사용하는 모든 대시보드 및 보고서와의 연결도 끊어집니다.

1. 오른쪽 위 모퉁이에서 기어 아이콘 ![](media/service-gateway-enterprise-manage-scheduled-refresh/pbi_gearicon.png) > **게이트웨이 관리**를 선택합니다.
2. 게이트웨이 > **제거**
   
   ![](media/service-gateway-enterprise-manage-scheduled-refresh/datasourcesettings7.png)

## <a name="add-a-data-source"></a>데이터 소스 추가
게이트웨이를 선택하고 **데이터 소스 추가**를 클릭하거나 게이트웨이 > **데이터 소스 추가**로 이동하여 데이터 소스를 추가할 수 있습니다.

![](media/service-gateway-enterprise-manage-scheduled-refresh/datasourcesettings1.png)

그런 다음 목록에서 **데이터 소스 형식** 을 선택합니다. 나열된 모든 데이터 원본을 엔터프라이즈 게이트웨이와 함께 예정된 새로 고침에 사용할 수 있습니다. Analysis Services, SQL Server 및 SAP HANA는 예정된 새로 고침 또는 DirectQuery/라이브 연결에 사용될 수 있습니다.

![](media/service-gateway-enterprise-manage-scheduled-refresh/datasourcesettings2.png)

그런 다음 데이터 원본에 액세스하는 데 사용되는 원본 정보 및 자격 증명을 포함하는 데이터 원본에 대한 정보를 입력합니다.

> [!NOTE]
> 데이터 소스에 대한 모든 쿼리는 이러한 자격 증명을 사용하여 실행됩니다. 자세한 내용은 기본 온-프레미스 데이터 게이트웨이 문서를 참조하여 [자격 증명](service-gateway-onprem.md#credentials)이 저장되는 방식에 대해 자세히 알아보세요.
> 
> 

![](media/service-gateway-enterprise-manage-scheduled-refresh/datasourcesettings3-oracle.png)

모든 항목을 입력한 다음 **추가**를 클릭합니다.  이제 온-프레미스 데이터에 대한 예정된 새로 고침에 이 데이터 원본을 사용할 수 있습니다. 성공한 경우 *연결 성공* 이 표시됩니다.

![](media/service-gateway-enterprise-manage-scheduled-refresh/datasourcesettings4.png)

<!-- Shared Install steps Include -->
[!INCLUDE [gateway-onprem-datasources-include](./includes/gateway-onprem-datasources-include.md)]

### <a name="advanced-settings"></a>고급 설정
데이터 원본에 대한 개인 정보 보호 수준을 구성할 수 있습니다. 데이터가 조합되는 방식을 제어합니다. 예정된 새로 고침에만 사용됩니다. [자세히 알아보기](https://support.office.com/article/Privacy-levels-Power-Query-CC3EDE4D-359E-4B28-BC72-9BEE7900B540)

![](media/service-gateway-enterprise-manage-scheduled-refresh/datasourcesettings9.png)

## <a name="remove-a-data-source"></a>데이터 원본 제거
데이터 원본을 제거하면 지정된 데이터 원본을 사용하는 모든 대시보드 또는 보고서와의 연결이 끊어집니다.  

데이터 원본을 제거하려면 데이터 원본 > **제거**로 이동합니다.

![](media/service-gateway-enterprise-manage-scheduled-refresh/datasourcesettings6.png)

## <a name="manage-administrators"></a>관리자 관리
관리자 탭에서 게이트웨이에 대해 게이트웨이를 관리할 수 있는 사용자를 추가 및 제거할 수 있습니다. 이 시점에서는 사용자만 추가할 수 있습니다. 보안 그룹은 추가할 수 없습니다.

![](media/service-gateway-enterprise-manage-scheduled-refresh/datasourcesettings8.png)

## <a name="manage-users"></a>사용자 관리
사용자 탭에서 데이터 원본에 대해 이 데이터 원본을 사용할 수 있는 사용자 또는 보안 그룹을 추가 및 제거할 수 있습니다.

> [!NOTE]
> 사용자 목록은 보고서를 게시할 수 있는 사용자를 제어합니다. 보고서 소유자는 대시보드 또는 콘텐츠 팩을 만들 수 있으며 이를 다른 사용자와 공유합니다.
> 
> 

![](media/service-gateway-enterprise-manage-scheduled-refresh/datasourcesettings5.png)

## <a name="using-the-data-source-for-scheduled-refresh"></a>예약된 새로 고침에 데이터 원본 사용
데이터 원본을 만든 후 DirectQuery 연결 또는 예약된 새로 고침을 통해 사용할 수 있습니다.

> [!NOTE]
> 서버 및 데이터베이스 이름은 온-프레미스 데이터 게이트웨이 내에서 Power BI Desktop 및 데이터 원본 간에 일치해야 합니다.
> 
> 

게이트웨이 내에서 데이터 세트 및 데이터 원본 간의 링크는 서버 이름 및 데이터베이스 이름을 기반으로 합니다. 이는 일치해야 합니다. 예를 들어 Power BI Desktop 내에서 서버 이름에 대한 IP 주소를 제공하는 경우 게이트웨이 구성 내에서 데이터 원본에 대한 IP 주소를 사용해야 합니다. Power BI Desktop에서 *서버\인스턴스*를 사용하는 경우 게이트웨이에 대해 구성된 데이터 원본 내에서 동일한 것을 사용해야 합니다.

게이트웨이 내에서 구성된 데이터 원본의 **사용자** 탭에 나열되고 서버 및 데이터베이스 이름이 일치하는 경우 예약된 새로 고침으로 사용하기 위한 옵션으로 게이트웨이가 표시됩니다.

![](media/service-gateway-enterprise-manage-scheduled-refresh/powerbi-gateway-enterprise-schedule-refresh.png)

> [!WARNING]
> 데이터 세트에 여러 데이터 원본이 포함된 경우 각 데이터 원본을 게이트웨이 내부에 추가해야 합니다. 게이트웨이에 하나 이상의 데이터 원본을 추가하지 않으면 예정된 새로 고침에 사용 가능한 게이트웨이가 표시되지 않습니다.
> 
> 

## <a name="limitations"></a>제한 사항
* OAuth는 온-프레미스 데이터 게이트웨이와 함께 지원되는 인증 체계가 아닙니다. OAuth가 필요한 데이터 원본을 추가할 수 없습니다. OAuth가 필요한 데이터 원본이 데이터 세트에 있으면 예정된 새로 고침에 게이트웨이를 사용할 수 없습니다.

## <a name="next-steps"></a>다음 단계
[온-프레미스 데이터 게이트웨이](service-gateway-onprem.md)  
[온-프레미스 데이터 게이트웨이 심층 분석](service-gateway-onprem-indepth.md)  
[온-프레미스 데이터 게이트웨이 문제 해결](service-gateway-onprem-tshoot.md)  
궁금한 점이 더 있나요? [Power BI 커뮤니티를 이용하세요.](http://community.powerbi.com/)

