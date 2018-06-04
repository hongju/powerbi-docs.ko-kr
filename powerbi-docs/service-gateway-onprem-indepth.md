---
title: 온-프레미스 데이터 게이트웨이 심층 분석
description: 이 문서에서는 온-프레미스 게이트웨이에 대해 자세히 살펴봅니다. Analysis Services로 작업 시 서비스가 Azure Active Directory 및 로컬 Active Directory에서 작동하는 방식을 살펴봅니다.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-gateways
ms.topic: conceptual
ms.date: 12/06/2017
ms.author: mblythe
LocalizationGroup: Gateways
ms.openlocfilehash: 8b0121dbfe633eca9c438dfd272d3aeb56fd59a4
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34298576"
---
# <a name="on-premises-data-gateway-in-depth"></a>온-프레미스 데이터 게이트웨이 심층 분석
조직의 사용자는 온-프레미스 데이터(이미 액세스 권한이 있는)에 액세스할 수 있지만 그러한 사용자가 온-프레미스 데이터 원본에 연결할 수 있기 전에 온-프레미스 데이터 게이트웨이를 설치하고 구성해야 합니다. 게이트웨이를 사용하면 클라우드의 사용자로부터 온-프레미스 데이터 원본으로, 다시 클라우드로 빠르고 안전하게 백그라운드에서 통신할 수 있습니다.

게이트웨이 설치 및 구성은 일반적으로 관리자가 수행합니다. 온-프레미스 서버에 대한 전문 지식이 있어야 하며 일부 경우에 서버 관리자 권한이 필요할 수 있습니다.

이 문서에서는 게이트웨이를 설치하고 구성하는 방법에 대한 단계별 지침을 제공하지 않습니다. 이 경우에 [온-프레미스 데이터 게이트웨이](service-gateway-onprem.md)를 참조하도록 합니다. 이 문서에서는 게이트웨이의 작동 방식을 깊이 있게 이해할 수 있습니다. 또한 Azure Active Directory 및 Analysis Services의 사용자 이름 및 보안, 클라우드 서비스에서 사용자가 로그인하는 데 사용하는 메일 주소, 게이트웨이 및 Active Directory를 사용하여 온-프레미스 데이터에 안전하게 연결하고 쿼리하는 방법에 대해 자세히 살펴봅니다.

<!-- Shared Requirements Include -->
[!INCLUDE [gateway-onprem-requirements-include](./includes/gateway-onprem-how-it-works-include.md)]

<!-- Shared Install steps Include -->
[!INCLUDE [gateway-onprem-datasources-include](./includes/gateway-onprem-datasources-include.md)]

## <a name="sign-in-account"></a>로그인 계정
사용자는 회사 또는 학교 계정으로 로그인합니다. 조직 계정입니다. Office 365 제품에 등록하고 실제 회사 전자 메일을 제공하지 않은 경우 nancy@contoso.onmicrosoft.com처럼 보일 수 있습니다. 클라우드 서비스 내의 계정은 AAD(Azure Active Directory)의 테넌트 내에 저장됩니다. 대부분의 경우에서 AAD 계정의 UPN은 전자 메일 주소와 일치합니다.

## <a name="authentication-to-on-premises-data-sources"></a>온-프레미스 데이터 원본에 대한 인증
Analysis Services를 제외하고 게이트웨이에서 온-프레미스 데이터 원본으로 연결하는 데 저장된 자격 증명이 사용됩니다. 게이트웨이는 개별 사용자에 관계없이 연결에 저장된 자격 증명을 사용합니다.

## <a name="authentication-to-a-live-analysis-services-data-source"></a>라이브 Analysis Services 데이터 원본에 대한 인증
사용자가 Analysis Services와 상호 작용할 때마다 유효 사용자 이름은 게이트웨이에 전달된 다음 온-프레미스 Analysis Services 서버에 전달됩니다. 클라우드에 로그인하는 UPN(사용자 계정 이름)은 일반적으로 전자 메일 주소이며 유효한 사용자로 Analysis Services에 통과됩니다. UPN은 연결 속성 EffectiveUserName에 전달됩니다. 이 전자 메일 주소는 로컬 Active Directory 도메인 내에서 정의된 UPN과 일치해야 합니다. UPN은 Active Directory 계정의 속성입니다. 그런 다음 해당 Windows 계정은 서버에 액세스할 수 있도록 Analysis Services 역할에 있어야 합니다. Active Directory에 일치하는 항목이 없는 경우 로그인이 성공적으로 수행되지 않습니다.

Analysis Services에서도 이 계정에 따라 필터링을 제공할 수 있습니다. 보안 또는 행 수준 보안에 따라 한 쪽 역할에 필터링이 발생할 수 있습니다.

## <a name="role-based-security"></a>역할 기반 보안
모델은 사용자 역할 기반 보안을 제공합니다. 역할은 SSDT-BI(SQL Server Data Tools – Business Intelligence)에서 작성하는 동안이나 모델이 배포된 후 SSMS(SQL Server Management Studio)를 사용하여 특정 모델 프로젝트에 대해 정의됩니다. 역할에는 Windows 사용자 이름 또는 Windows 그룹별로 멤버가 포함됩니다. 역할은 사용자가 모델에서 쿼리하거나 작업을 수행하는 데 필요한 권한을 정의합니다. 대부분의 사용자는 읽기 권한을 가진 역할에 속합니다. 다른 역할은 항목 처리, 데이터베이스 함수 관리, 기타 역할 관리 등을 수행할 권한이 있는 관리자를 위한 것입니다.

## <a name="row-level-security"></a>행 수준 보안
행 수준 보안은 Analysis Services 행 수준 보안과 관련됩니다. 모델은 동적 행 수준 보안을 제공할 수 있습니다. 사용자가 속한 역할이 하나 이상 있어야 하는 것과 달리 동적 보안은 일부 테이블 형식 모델에 필요하지 않습니다. 상위 수준의 동적 보안은 데이터에 대한 사용자의 읽기 권한을 특정 테이블에 있는 특정 행 바로 아래로 정의합니다. 역할과 마찬가지로 동적 행 수준 보안에서는 사용자의 Windows 사용자 이름을 사용합니다.

모델 데이터를 쿼리하고 보는 사용자 권한이 Windows 사용자 계정이 멤버인 역할에 의해 먼저 결정된 다음 동적 행 수준 보안(구성된 경우)에 의해 두 번째로 결정됩니다.

모델에서 역할 및 동적 행 수준 보안을 구현하는 작업은 이 문서의 범위를 벗어납니다.  MSDN에서 [역할(SSAS 테이블 형식)](https://msdn.microsoft.com/library/hh213165.aspx) 및 [보안 역할(Analysis Services - 다차원 데이터)](https://msdn.microsoft.com/library/ms174840.aspx)을 자세히 알아볼 수 있습니다. 테이블 형식 모델 보안을 가장 깊이 있게 이해하려면 [테이블 형식 BI 의미 체계 모델 보안 설정](https://msdn.microsoft.com/library/jj127437.aspx)(영문) 백서를 다운로드하여 읽어 보세요.

## <a name="what-about-azure-active-directory"></a>Azure Active Directory의 경우
Microsoft 클라우드 서비스는 [Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-whatis/)를 사용하여 사용자 인증을 수행합니다. Azure Active Directory는 사용자 이름 및 보안 그룹을 포함하는 테넌트입니다. 일반적으로 사용자가 로그인하는 전자 메일 주소는 계정의 UPN과 같습니다.

내 로컬 Active Directory의 역할이란?

Analysis Services에서 연결되어 있는 사용자가 데이터 읽기 권한이 있는 역할에 속하는지 확인하려면 서버가 AAD에서 전달된 유효 사용자 이름을 게이트웨이로 변환한 다음 Analysis Services 서버로 변환해야 합니다. Analysis Services 서버는 유효 사용자 이름을 Windows Active Directory 도메인 컨트롤러(DC)에 전달합니다. 그러면 Active Directory DC에서 유효 사용자 이름이 유효한 UPN인지를 검사하고 로컬 계정에서 해당 사용자의 Windows 사용자 이름을 Analysis Services 서버에 다시 반환합니다.

도메인에 조인되지 않은 Analysis Services 서버에서는 EffectiveUserName을 사용할 수 없습니다. 로그인 오류를 피하기 위해 Analysis Services 서버는 도메인에 조인되어야 합니다.

## <a name="how-do-i-tell-what-my-upn-is"></a>내 UPN이 무엇인지 어떻게 확인합니까?
사용자 UPN이 무엇인지 알 수 없으며 도메인 관리자가 되지 못할 수도 있습니다. 워크스테이션에서 다음 명령을 사용하여 계정에 대한 UPN을 알아볼 수 있습니다.

    whoami /upn

결과는 전자 메일 주소와 유사하지만 로컬 도메인 계정에 있는 UPN입니다. 라이브 연결을 위해 Analysis Services 데이터 원본을 사용하는 경우 게이트웨이에서 EffectiveUserName에 전달된 것과 일치해야 합니다.

## <a name="mapping-usernames-for-analysis-services-data-sources"></a>Analysis Services 데이터 원본의 사용자 이름 매핑
Power BI에서는 Analysis Services 데이터 원본의 사용자 이름 매핑이 허용됩니다. Analysis Services 연결에서 EffectiveUserName에 대해 전달되는 이름에 Power BI를 사용하여 로그인된 사용자 이름을 매핑하는 규칙을 구성할 수 있습니다. 사용자 이름 매핑 기능은 AAD에 대한 사용자 이름이 로컬 Active Directory의 UPN과 일치하지 않는 경우 문제를 해결하는 좋은 방법입니다. 예를 들어 전자 메일 주소가 nancy@contoso.onmicrsoft.com인 경우 nancy@contoso.com에 매핑할 수 있으며 이 값을 게이트웨이에 전달합니다. [사용자 이름을 매핑하는 방법](service-gateway-enterprise-manage-ssas.md#map-user-names)에 대해 자세히 알아볼 수 있습니다.

## <a name="synchronize-an-on-premises-active-directory-with-azure-active-directory"></a>Azure Active Directory와 온-프레미스 Active Directory 동기화
Analysis Services 라이브 연결을 사용할 예정인 경우 로컬 Active Directory 계정을 Azure Active Directory에 일치시키려 할 수 있습니다. 계정 간에 UPN을 일치시켜야 하기 때문입니다.

클라우드 서비스만 Azure Active Directory 내의 계정에 대해 알고 있습니다. 로컬 Active Directory에서 계정을 추가했는지 여부는 중요하지 않으며 AAD에 존재하지 않는 경우 사용할 수 없습니다. 로컬 Active Directory 계정을 Azure Active Directory와 일치시킬 수 있는 다양한 방법이 있습니다.

1. Azure Active Directory에 계정을 수동으로 추가할 수 있습니다.
   
   Azure 포털 또는 Office 365 관리 포털 내에 계정을 만들 수 있으며 계정 이름은 로컬 Active Directory 계정의 UPN과 일치합니다.
2. [Azure AD Connect](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/) 도구를 사용하여 로컬 계정을 Azure Active Directory 테넌트와 동기화할 수 있습니다.
   
   Azure AD Connect 도구는 암호 해시 동기화, 통과 인증 및 페더레이션을 비롯한 인증 설정 및 디렉터리 동기화를 위한 옵션을 제공합니다. 테넌트 관리자 또는 로컬 도메인 관리자가 아닌 경우 IT 관리자에게 이 내용이 구성되었는지 문의해야 합니다.

Azure AD Connect를 사용하면 UPN이 AAD와 로컬 Active Directory 간에 일치하도록 할 수 있습니다.

> [!NOTE]
> 계정을 Azure AD Connect 도구와 동기화하면 AAD 테넌트 내에 새 계정이 만들어집니다.
> 
> 

## <a name="now-this-is-where-the-gateway-comes-in"></a>이제 게이트웨이가 들어오는 위치입니다.
게이트웨이는 클라우드와 온-프레미스 서버 사이의 브리지 역할을 합니다. 클라우드와 게이트웨이 간의 데이터 전송은 [Azure Service Bus](https://azure.microsoft.com/documentation/services/service-bus/)를 통해 보안이 설정됩니다. Service Bus는 아웃바운드 연결을 통해 게이트웨이에서 클라우드와 온-프레미스 서버 사이에 보안 채널을 만듭니다.  온-프레미스 방화벽에서 열어야 하는 인바운드 연결이 없습니다.

Analysis Services 데이터 원본이 있으면 Analysis Services 서버와 동일한 포리스트/도메인에 조인된 컴퓨터에 게이트웨이를 설치해야 합니다.

게이트웨이가 서버에 가까울수록 더 빠르게 연결됩니다. 데이터 원본과 같은 서버에서 게이트웨이 얻을 수 있는 경우 게이트웨이와 서버 간의 네트워크 대기 시간을 방지하는 것이 가장 좋습니다.

## <a name="what-to-do-next"></a>다음을 수행하려면 어떻게 합니까?
게이트웨이가 설치된 후 해당 게이트웨이에 대한 데이터 소스를 만들려고 합니다. **게이트웨이 관리** 화면 내에 데이터 소스를 추가할 수 있습니다. 자세한 내용은 데이터 소스 관리 문서를 참조하세요.

[데이터 원본 관리 - Analysis Services](service-gateway-enterprise-manage-ssas.md)  
[데이터 원본 관리 - SAP HANA](service-gateway-enterprise-manage-sap.md)  
[데이터 원본 관리 - SQL Server](service-gateway-enterprise-manage-sql.md)  
[데이터 원본 관리 - Oracle](service-gateway-onprem-manage-oracle.md)  
[데이터 원본 관리 - 가져오기/예약된 새로 고침](service-gateway-enterprise-manage-scheduled-refresh.md)  

## <a name="where-things-can-go-wrong"></a>문제가 발생할 수 있는 경우
경우에 따라 게이트웨이가 설치되지 않을 수 있습니다. 또는 게이트웨이가 설치된 것으로 보이는데 서비스로 작업을 수행할 수 없는 경우가 있습니다. 대부분의 경우 게이트웨이가 데이터 원본에 로그인하는 데 사용하는 자격 증명에 대한 암호와 같은 간단한 원인 때문입니다.

경우에 따라 사용자가 로그인하는 데 사용하는 메일 주소의 형식 문제 또는 Analysis Services에서 유효 사용자 이름을 확인할 수 없는 문제일 수 있습니다. 트러스트 관계가 있는 여러 도메인이 있고 한 도메인에는 게이트웨이, 다른 한 도메인에는 Analysis Services가 있는 경우 몇 가지 문제가 발생할 수 있습니다.

여기에서 게이트웨이 문제 해결을 살펴보는 대신 다른 [온-프레미스 데이터 게이트웨이 문제 해결](service-gateway-onprem-tshoot.md) 문서를 통해 일련의 문제 해결 단계를 제공했습니다. 다행히 문제가 없을 수 있습니다. 그러나 문제가 있을 경우 작동 방식 이해 및 문제 해결 문서가 도움이 될 수 있습니다.

<!-- Account and Port information -->
[!INCLUDE [gateway-onprem-accounts-ports-more](./includes/gateway-onprem-accounts-ports-more.md)]

## <a name="next-steps"></a>다음 단계
[온-프레미스 데이터 게이트웨이 문제 해결](service-gateway-onprem-tshoot.md)  
[Azure Service Bus](https://azure.microsoft.com/documentation/services/service-bus/)  
[Azure AD Connect](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/)  
궁금한 점이 더 있나요? [Power BI 커뮤니티를 이용하세요.](http://community.powerbi.com/)

