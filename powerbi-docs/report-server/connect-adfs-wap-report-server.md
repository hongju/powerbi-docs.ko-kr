---
title: 웹 애플리케이션 프록시 및 Active Directory Federated Services 사용 - Power BI Report Server
description: WAP(웹 애플리케이션 프록시) 및 Active Directory Federeated Services(AD FS)를 사용하여 Power BI Report Server 및 SSRS(SQL Server Reporting Service) 2016 이상에 연결하는 방법을 알아봅니다.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 01/14/2020
ms.openlocfilehash: 2caa96aceef90ad1d25a521cbf4a3f699a2a64e0
ms.sourcegitcommit: 0ae9328e7b35799d5d9613a6d79d2f86f53d9ab0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2020
ms.locfileid: "76042443"
---
# <a name="use-web-application-proxy-and-active-directory-federated-services---power-bi-report-server"></a>웹 애플리케이션 프록시 및 Active Directory Federated Services 사용 - Power BI Report Server

이 문서에서는 WAP(웹 애플리케이션 프록시) 및 AD FS(Active Directory Federeated Services)를 사용하여 Power BI Report Server 및 SQL Server Reporting Services(SSRS) 2016 이상에 연결하는 방법을 알아봅니다. 회사 네트워크에서 멀리 떨어진 사용자는 이 통합을 통해 클라이언트 브라우저에서 Power BI Report Server 및 Reporting Services에 액세스하고 AD FS 사전 인증으로 보호될 수 있습니다. Power BI 모바일 앱의 경우, [Power BI Report Server 및 SSRS에 연결하도록 OAuth를 구성](../consumer/mobile/mobile-oauth-ssrs.md)해야 합니다.

## <a name="prerequisites"></a>사전 요구 사항

### <a name="domain-name-services-dns-configuration"></a>DNS(도메인 이름 서비스) 구성

- 사용자가 연결할 공용 URL을 결정합니다. `https://reports.contosolab.com`과 유사합니다.
- 예를 들어 WAP(웹 애플리케이션 프록시) 서버의 공용 IP 주소를 가리키도록 호스트 이름 `reports.contosolab.com`의 DNS 레코드를 구성합니다.
- AD FS 서버의 공용 DNS 레코드를 구성합니다. 예를 들어 다음 URL로 AD FS 서버를 구성했을 수 있습니다. `https://adfs.contosolab.com`.
- WAP(웹 애플리케이션 프록시) 서버의 공용 IP 주소를 가리키도록 DNS 레코드를 구성합니다(예: `adfs.contosolab.com`). 이는 WAP 애플리케이션의 일부로 게시됩니다.

### <a name="certificates"></a>인증서

WAP 애플리케이션 및 AD FS 서버에 대한 인증서를 구성해야 합니다. 이러한 인증서는 둘 다 컴퓨터가 인식하는 유효한 인증 기관의 일부여야 합니다.

## <a name="1-configure-the-report-server"></a>1. 보고서 서버 구성

유효한 SPN(서비스 사용자 이름)이 있는지 확인해야 합니다. 유효한 SPN을 통해 적절한 Kerberos 인증이 수행되고 보고서 서버에서 협상 인증을 사용할 수 있습니다.

### <a name="service-principal-name-spn"></a>SPN(서비스 주체 이름)

SPN은 Kerberos 인증을 사용하는 서비스에 대한 고유한 식별자입니다. 보고서 서버에 대한 적절한 HTTP SPN이 있는지 확인합니다.

보고서 서버에 대한 적절한 SPN(서비스 주체 이름)을 구성하는 방법에 대한 자세한 내용은 [보고서 서버에 SPN(서비스 주체 이름) 등록](https://docs.microsoft.com/sql/reporting-services/report-server/register-a-service-principal-name-spn-for-a-report-server)을 참조하세요.

### <a name="enabling-negotiate-authentication"></a>협상 인증 사용

Kerberos 인증을 사용하는 보고서 서버를 사용하려면 보고서 서버의 인증 유형이 RSWindowsNegotiate이 되도록 구성해야 합니다. rsreportserver.config 파일에서 이를 구성합니다.

```
<AuthenticationTypes>

    <RSWindowsNegotiate />

    <RSWindowsNTLM />

</AuthenticationTypes>
```

자세한 내용은 [Reporting Services 구성 파일 수정](https://docs.microsoft.com/sql/reporting-services/report-server/modify-a-reporting-services-configuration-file-rsreportserver-config) 및 [보고서 서버에서 Windows 인증 구성](https://docs.microsoft.com/sql/reporting-services/security/configure-windows-authentication-on-the-report-server)을 참조하세요.

## <a name="2-configure-active-directory-federation-services-ad-fs"></a>2. Active Directory Federation Services(AD FS) 구성

사용자 환경 내의 Windows 2016 서버에서 AD FS를 구성해야 합니다. [서버 관리자] 및 [관리] 아래의 [역할 및 기능 추가]를 선택하여 이 구성을 수행할 수 있습니다. 자세한 내용은 [Active Directory Federation Services](https://docs.microsoft.com/windows-server/identity/active-directory-federation-services)를 참조하세요.

AD FS 서버에서 AD FS 관리 앱을 사용하여 다음 단계를 완료합니다.

1. 마우스 오른쪽 단추로 **신뢰 당사자 트러스트** > **신뢰 당사자 트러스트 추가**를 클릭합니다.

    ![신뢰 당사자 트러스트 추가](media/connect-adfs-wap-report-server/report-server-adfs-add-relying-party-trust.png)

2. **신뢰 당사자 트러스트 추가** 마법사의 단계를 따릅니다.

    Windows 통합 보안을 인증 메커니즘으로 사용하려면 **클레임 비인식** 옵션을 선택합니다.

    ![신뢰 당사자 트러스트 추가 마법사에 오신 것을 환영합니다](media/connect-adfs-wap-report-server/report-server-adfs-add-relying-party-trust-welcome.png)

    **표시 이름 지정**에 원하는 이름을 입력하고 **다음**을 선택합니다.
    신뢰 당사자 트러스트 식별자 추가: `<ADFS\_URL>/adfs/services/trust`

    예: `https://adfs.contosolab.com/adfs/services/trust`

    ![보고서 서버](media/connect-adfs-wap-report-server/report-server-adfs-configure-identifiers.png)

    조직의 요구 사항에 맞는 **액세스 제어 정책**을 선택하고 **다음**을 선택합니다.

    ![액세스 제어 선택](media/connect-adfs-wap-report-server/report-server-adfs-choose-access-control.png)
    
    **다음**을 선택한 후 **마침**을 선택하여 **신뢰 당사자 트러스트 추가** 마법사를 종료합니다.

    완료되면 신뢰 당사자 트러스트의 속성이 다음과 같이 표시되어야 합니다.

    ![신뢰 당사자 트러스트](media/connect-adfs-wap-report-server/report-server-adfs-relying-party-trusts.png)

## <a name="3-configure-web-application-proxy-wap"></a>3. 웹 애플리케이션 프록시(WAP) 구성

사용자 환경의 서버에서 웹 애플리케이션 프록시(역할) Windows 역할을 사용하도록 설정하려고 합니다. Windows 2016 서버에 있어야 합니다. 자세한 내용은 [Windows Server 2016의 웹 애플리케이션 프록시](https://docs.microsoft.com/windows-server/remote/remote-access/web-application-proxy/web-application-proxy-windows-server) 및 [AD FS 사전 인증을 사용하여 애플리케이션 게시](https://docs.microsoft.com/windows-server/remote/remote-access/web-application-proxy/Publishing-Applications-using-AD-FS-Preauthentication)를 참조하세요.

### <a name="configure-constrained-delegation"></a>제한된 위임 구성

폼 인증에서 Windows 인증으로 전환하기 위해 프로토콜 전환을 포함한 제한된 위임을 사용해야 합니다. 이 단계는 Kerberos 구성의 일부입니다. 이미 보고서 서버 구성 내에서 보고서 서버 SPN을 정의했습니다.

Active Directory 내의 WAP 서버 컴퓨터 계정에서 제한된 위임을 구성해야 합니다. Active Directory에 대한 권한이 없는 경우 도메인 관리자와 함께 작업해야 할 수도 있습니다.

제한된 위임을 구성하려면 다음 단계를 따르세요.

1. Active Directory 도구가 설치되어 있는 컴퓨터에서 **Active Directory 사용자 및 컴퓨터**를 시작합니다.
2. WAP 서버에 대한 컴퓨터 계정을 찾습니다. 기본적으로 **컴퓨터** 컨테이너에 위치합니다.
3. WAP 서버를 마우스 오른쪽 단추로 클릭하고 **속성**으로 이동합니다.
4. **위임** 탭에서 **지정한 서비스에 대해서만 위임용으로 이 컴퓨터 트러스트**를 선택한 다음 **인증 프로토콜 사용**을 선택합니다.

    ![이 컴퓨터 트러스트](media/connect-adfs-wap-report-server/report-server-adfs-delegation-use-any.png)

1. 이 옵션은 이 WAP 서버 컴퓨터 계정의 제한된 위임을 설정합니다. 그런 다음 이 컴퓨터가 위임할 수 있는 서비스를 지정해야 합니다.
2. 서비스 상자에서 **추가**를 선택합니다.

    ![AD FS 트러스트 추가](media/connect-adfs-wap-report-server/report-server-adfs-trust-add.png)

1. **사용자 또는 컴퓨터**를 선택합니다.
2. 보고서 서버에 사용할 서비스 계정을 입력합니다. 이 계정은 이전 [보고서 서버 구성](#1-configure-the-report-server) 섹션에서 HTTP SPN을 추가하는 데 사용한 계정과 동일합니다. 

3. 보고서 서버의 HTTP SPN을 선택한 다음 **확인**을 선택합니다.

    > [!NOTE]
    > NetBIOS SPN만 표시될 수 있습니다. 실제로 NetBIOS와 FQDN SPN이 모두 있는 경우 둘 다 선택됩니다.

1. **확장됨** 확인란을 선택한 경우 결과는 다음 예와 유사해야 합니다.

    ![WAP 속성](media/connect-adfs-wap-report-server/report-server-wap-properties.png)

### <a name="add-wap-application"></a>WAP 애플리케이션 추가

1. 웹 애플리케이션 프록시 서버에서 **원격 액세스 관리** 콘솔을 열고 탐색 창에서 **웹 애플리케이션 프록시**를 선택합니다. 

2. **작업** 창에서 **게시**를 선택합니다.

2. 시작 페이지에서 **다음**을 선택합니다.

    ![게시 시작](media/connect-adfs-wap-report-server/report-server-welcome-publish-new-app-wizard.png)

3. **사전 인증** 페이지에서 **Active Directory Federation Services(AD FS)** 를 선택한 후 **다음**을 선택합니다.

    ![사전 인증](media/connect-adfs-wap-report-server/report-server-preauthentication-new-app-wizard.png)

4. 모바일 앱 액세스가 아닌 보고서 서버에 대한 브라우저 액세스만 설정하므로 **Web 및 MSOFBA** 사전 인증을 선택합니다.

    ![지원되는 클라이언트](media/connect-adfs-wap-report-server/report-server-supported-clients-publish-new-app-wizard.png)

5. 아래 나온 것처럼 AD FS 서버에서 만든 **신뢰 당사자**를 추가한 후 **다음**을 선택합니다.

    ![신뢰 당사자 게시](media/connect-adfs-wap-report-server/report-server-relying-party-publish-new-app-wizard.png)

6. **외부 URL** 섹션에 WAP 서버에서 구성한 공개적으로 액세스 가능한 URL을 입력합니다. 보고서 서버(보고서 서버 구성 관리자)를 사용하여 구성된 URL을 아래 나온 것처럼 **백 엔드 서버 URL** 섹션에 추가합니다. **백 엔드 서버 SPN** 섹션에 보고서 서버의 SPN을 추가합니다.

    ![게시 설정](media/connect-adfs-wap-report-server/report-server-publishing-settings-new-app-wizard.png)

7. **다음**을 선택하고 **게시**를 선택합니다.
8. 다음 PowerShell 명령을 실행하여 WAP 구성의 유효성을 검사합니다.

    ```
    Get-WebApplicationProxyApplication "PBIRSBrowser" | FL
    ```

    ![PowerShell 명령](media/connect-adfs-wap-report-server/report-server-powershell-get-webapplication.png)

## <a name="connect-to-the-report-server-through-the-browser"></a>브라우저를 통해 보고서 서버에 연결

그런 다음 공용 WAP URL에 액세스할 수 있습니다(예: 웹 서비스의 경우 `https://reports.contosolab.com/ReportServer`, 브라우저에서 웹 포털에 액세스하는 경우에는 `https://reports.contosolab.com/Reports`). 성공적으로 인증하면 보고서를 볼 수 있습니다.

![AD FS 로그인](media/connect-adfs-wap-report-server/report-server-adfs-sign-in.png)

## <a name="next-steps"></a>다음 단계

* [Power BI Report Server 및 SSRS에 연결하도록 OAuth 구성](../consumer/mobile/mobile-oauth-ssrs.md)
*[Power BI Report Server란?](get-started.md)  

추가 질문이 있으신가요? [Power BI 커뮤니티에 질문합니다.](https://community.powerbi.com/)

