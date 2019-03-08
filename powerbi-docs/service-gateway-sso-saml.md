---
title: 온-프레미스 데이터 원본의 SSO(Single Sign-On)에 SAML 사용
description: SAML(Security Assertion Markup Language)을 사용하여 Power BI에서 온-프레미스 데이터 원본으로 SSO(Single Sign-On)를 사용하도록 게이트웨이를 구성합니다.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 03/05/2019
LocalizationGroup: Gateways
ms.openlocfilehash: c1ca797efa2e40bf74384a1e9f2362acd26c6f8f
ms.sourcegitcommit: 883a58f63e4978770db8bb1cc4630e7ff9caea9a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/07/2019
ms.locfileid: "57555656"
---
# <a name="use-security-assertion-markup-language-saml-for-single-sign-on-sso-from-power-bi-to-on-premises-data-sources"></a>Power BI에서 온-프레미스 데이터 원본으로 SSO(Single Sign-On)에 SAML(Security Assertion Markup Language)을 사용합니다.

SAML([Security Assertion Markup Language](https://www.onelogin.com/pages/saml))을 사용하여 원활한 Single Sign-On 연결을 구현합니다. SSO를 사용하도록 설정하면 Power BI 보고서 및 대시보드가 온-프레미스 원본의 데이터를 손쉽게 새로 고칠 수 있습니다.

## <a name="supported-data-sources"></a>지원되는 데이터 원본

현재 SAML을 사용하는 SAP HANA가 지원됩니다. SAML을 사용하는 SAP HANA에 Single Sign-On을 설정하고 구성하는 방법에 대한 자세한 내용은 SAP HANA 설명서의 [BI 플랫폼에서 HANA로 SAML SSO 연결](https://wiki.scn.sap.com/wiki/display/SAPHANA/SAML+SSO+for+BI+Platform+to+HANA) 항목을 참조하세요.

[Kerberos](service-gateway-sso-kerberos.md)에 추가 데이터 원본이 지원됩니다.

## <a name="configuring-the-gateway-and-data-source"></a>게이트웨이 및 데이터 원본 구성

SAML을 사용하려면 먼저 SAML ID 공급자의 인증서를 생성한 다음, Power BI 사용자를 ID에 매핑합니다.

1. 인증서를 생성합니다. *일반 이름*을 작성할 때 SAP HANA 서버의 FQDN을 사용하세요. 인증서는 365일 후 만료됩니다.

    ```
    openssl req -newkey rsa:2048 -nodes -keyout samltest.key -x509 -days 365 -out samltest.crt
    ```

1. SAP HANA Studio에서 SAP HANA 서버를 마우스 오른쪽 단추로 클릭한 다음, **보안** > **보안 콘솔 열기** > **SAML ID 공급자** > **OpenSSL 암호화 라이브러리**로 이동합니다.

    OpenSSL 대신 SAP 암호화 라이브러리(CommonCryptoLib 또는 sapcrypto라고도 함)를 사용하여 이러한 설정 단계를 완료할 수도 있습니다. 자세한 내용은 공식 SAP 설명서를 참조하세요.

1. **가져오기**를 선택하고 samltest.crt로 이동하여 가져옵니다.

    ![ID 공급자](media/service-gateway-sso-saml/identity-providers.png)

1. SAP HANA Studio에서 **보안** 폴더를 선택합니다.

    ![보안 폴더](media/service-gateway-sso-saml/security-folder.png)

1. **사용자**를 확장한 다음, Power BI 사용자를 매핑하려는 사용자를 선택합니다.

1. **SAML**을 선택한 다음, **구성**을 선택합니다.

    ![SAML 구성](media/service-gateway-sso-saml/configure-saml.png)

1. 2단계에서 만든 ID 공급자를 선택합니다. **외부 ID**에 Power BI 사용자의 UPN을 입력한 다음, **추가**를 선택합니다.

    ![ID 공급자 선택](media/service-gateway-sso-saml/select-identity-provider.png)

인증서와 ID가 구성되었으므로 인증서를 pfx 형식으로 변환하고 인증서를 사용하도록 게이트웨이 머신을 구성합니다.

1. 다음 명령을 실행하여 인증서를 pfx 형식으로 변환합니다.

    ```
    openssl pkcs12 -inkey samltest.key -in samltest.crt -export -out samltest.pfx
    ```

1. 게이트웨이 머신에 pfx 파일을 복사합니다.

    1. samltest.pfx를 두 번 클릭한 다음, **로컬 머신** > **다음**을 선택합니다.

    1. 암호를 입력한 후 **다음**을 선택합니다.

    1. **모든 인증서를 다음 저장소에 저장**, **찾아보기** > **개인** > **확인**을 차례로 선택합니다.

    1. **다음**을 선택한 다음, **마침**을 선택합니다.

    ![인증서 가져오기](media/service-gateway-sso-saml/import-certificate.png)

1. 인증서의 개인 키에 게이트웨이 서비스 계정 액세스 권한을 부여합니다.

    1. 게이트웨이 머신에서 MMC(Microsoft Management Console)를 실행합니다.

        ![MMC 실행](media/service-gateway-sso-saml/run-mmc.png)

    1. **파일** 아래에서 **스냅인 추가/제거**를 선택합니다.

        ![스냅인 추가](media/service-gateway-sso-saml/add-snap-in.png)

    1. **인증서** > **추가**를 선택한 후 **컴퓨터 계정** > **다음**을 선택합니다.

    1. **로컬 컴퓨터** > **마침** > **확인**을 선택합니다.

    1. **인증서** > **개인** > **인증서**를 확장하고 인증서를 찾습니다.

    1. 인증서를 마우스 오른쪽 단추로 클릭하고 **모든 작업** > **개인 키 관리**로 이동합니다.

        ![개인 키 관리](media/service-gateway-sso-saml/manage-private-keys.png)

    1. 게이트웨이 서비스 계정을 목록에 추가합니다. 기본적으로 이 계정은 **NT SERVICE\PBIEgwService**입니다. **services.msc**를 실행하여 실행 중인 게이트웨이 서비스를 확인하고, **온-프레미스 데이터 게이트웨이 서비스**를 찾을 수 있습니다.

        ![게이트웨이 서비스](media/service-gateway-sso-saml/gateway-service.png)

마지막으로, 다음 단계를 수행하여 게이트웨이 구성에 인증서 지문을 추가합니다.

1. 다음 PowerShell 명령을 실행하여 머신의 인증서를 나열합니다.

    ```powershell
    Get-ChildItem -path cert:\LocalMachine\My
    ```
1. 만든 인증서의 지문을 복사합니다.

1. 게이트웨이 디렉터리(기본값: C:\Program Files\On-premises data gateway)로 이동합니다.

1. PowerBI.DataMovement.Pipeline.GatewayCore.dll.config를 열고 \*SapHanaSAMLCertThumbprint\* 섹션을 찾습니다. 복사한 지문에 붙여 넣습니다.

1. 게이트웨이 서비스를 다시 시작합니다.

## <a name="running-a-power-bi-report"></a>Power BI 보고서 실행

이제 Power BI에서 **게이트웨이 관리** 페이지를 사용하여 데이터 원본을 구성하고, **고급 설정**에서 SSO를 사용하도록 설정할 수 있습니다. 그런 다음, 해당 데이터 원본에 보고서 및 데이터 세트 바인딩을 게시할 수 있습니다.

![고급 설정](media/service-gateway-sso-saml/advanced-settings.png)

## <a name="troubleshooting"></a>문제 해결

SSO를 구성한 후 Power BI 포털에 다음 오류가 표시될 수 있습니다. "제공된 자격 증명을 SapHana 원본에 사용할 수 없습니다." 이 오류는 SAML 자격 증명이 SAP HANA에 의해 거부되었음을 나타냅니다.

인증 추적은 SAP HANA의 자격 증명 문제를 해결하기 위한 자세한 정보를 제공합니다. 다음 단계에 따라 SAP HANA 서버에 대한 추적을 구성합니다.

1. SAP HANA 서버에서 다음 쿼리를 실행하여 인증 추적을 켭니다.

    ```
    ALTER SYSTEM ALTER CONFIGURATION ('indexserver.ini', 'SYSTEM') set ('trace', 'authentication') = 'debug' with reconfigure 
    ```

1. 직면한 문제를 재현합니다.

1. HANA Studio에서 관리 콘솔을 열고 **진단 파일** 탭으로 이동합니다.

1. 최신 indexserver 추적을 열고 SAMLAuthenticator.cpp를 검색합니다.

    다음 예제와 같은 근본 원인을 나타내는 자세한 오류 메시지를 찾아야 합니다.

    ```
    [3957]{-1}[-1/-1] 2018-09-11 21:40:23.815797 d Authentication   SAMLAuthenticator.cpp(00091) : Element '{urn:oasis:names:tc:SAML:2.0:assertion}Assertion', attribute 'ID': '123123123123123' is not a valid value of the atomic type 'xs:ID'.
    [3957]{-1}[-1/-1] 2018-09-11 21:40:23.815914 i Authentication   SAMLAuthenticator.cpp(00403) : No valid SAML Assertion or SAML Protocol detected
    ```

1. 문제 해결이 완료되면 다음 쿼리를 실행하여 인증 추적을 끕니다.

    ```
    ALTER SYSTEM ALTER CONFIGURATION ('indexserver.ini', 'SYSTEM') UNSET ('trace', 'authentication');
    ```

## <a name="next-steps"></a>다음 단계

**온-프레미스 데이터 게이트웨이** 및 **DirectQuery**에 대한 자세한 내용은 다음 리소스를 확인하세요.

* [온-프레미스 데이터 게이트웨이](service-gateway-onprem.md)
* [Power BI의 DirectQuery](desktop-directquery-about.md)
* [DirectQuery에서 지원하는 데이터 원본](desktop-directquery-data-sources.md)
* [DirectQuery 및 SAP BW](desktop-directquery-sap-bw.md)
* [DirectQuery 및 SAP HANA](desktop-directquery-sap-hana.md)
