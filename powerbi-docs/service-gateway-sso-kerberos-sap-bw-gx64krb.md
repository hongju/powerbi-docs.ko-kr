---
title: gx64krb5를 사용하는 SAP BW로의 SSO(Single Sign-On)에 Kerberos 사용
description: gx64krb5를 사용하여 Power BI 서비스에서 SSO를 사용하도록 SAP BW 서버 구성
author: arthiriyer
ms.author: arthii
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 10/10/2019
LocalizationGroup: Gateways
ms.openlocfilehash: 6c8b62cf798d2fbbd09dab0603d216448d04487c
ms.sourcegitcommit: 6272c4a0f267708ca7d38a45774f3bedd680f2d6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/06/2020
ms.locfileid: "75000138"
---
# <a name="use-kerberos-for-single-sign-on-sso-to-sap-bw-using-gx64krb5"></a>gx64krb5를 사용하는 SAP BW로의 SSO(Single Sign-On)에 Kerberos 사용

이 문서에서는 gx64krb5를 사용하여 Power BI 서비스에서 SSO를 사용하도록 SAP BW 데이터 원본을 구성하는 방법을 설명합니다.

> [!NOTE]
> Power BI 서비스에서 SAP BW 애플리케이션 서버 기반 보고서에 대한 SSO 기반 새로 고침을 사용하도록 설정하려면 [Kerberos SSO 구성](service-gateway-sso-kerberos.md)의 단계 이외에 이 문서의 단계를 완료할 수 있습니다. 그러나 Microsoft는 gx64krb5가 아닌 SNC 라이브러리로 CommonCryptoLib을 사용할 것을 권장합니다. SAP는 더 이상 gx64krb5를 지원하지 않으며, 게이트웨이에 구성하는 데 필요한 단계는 CommonCryptoLib에 비해 훨씬 더 복잡합니다. CommonCryptoLib를 사용하여 SSO를 구성하는 방법에 대한 자세한 내용은 [CommonCryptoLib를 사용하여 SSO에 대해 SAP BW 구성](service-gateway-sso-kerberos-sap-bw-commoncryptolib.md)을 참조하세요. CommonCryptoLib _또는_ gx64krb5를 SNC 라이브러리로 사용해야 합니다. 두 라이브러리에 대한 구성 단계를 모두 완료하지 마세요.

이 가이드는 포괄적입니다. 설명된 단계 중 일부를 이미 완료한 경우에는 건너뛰어도 됩니다. 예를 들어 gx64krb5를 사용하여 SSO에 대한 SAP BW 서버를 이미 구성했을 수 있습니다.

## <a name="set-up-gx64krb5-on-the-gateway-machine-and-the-sap-bw-server"></a>게이트웨이 컴퓨터 및 SAP BW 서버에서 gx64krb5 설정

> [!NOTE]
> gx64krb5 라이브러리는 SAP에서 더 이상 지원되지 않습니다. 자세한 내용은 [SAP 참고 352295](https://launchpad.support.sap.com/#/notes/352295)를 참조하세요. gx64krb5는 데이터 게이트웨이에서 SAP BW 메시지 서버로의 SSO 연결을 허용하지 않습니다. SAP BW 애플리케이션에 대한 연결만 가능합니다. [CommonCryptoLib](service-gateway-sso-kerberos-sap-bw-commoncryptolib.md)를 SNC 라이브러리로 사용하는 경우에는 이 제한이 적용되지 않습니다. 다른 SNC 라이브러리도 BW SSO에 사용할 수 있지만 Microsoft에서 공식적으로 지원하지는 않습니다.

게이트웨이를 통해 SSO 연결을 완료하려면 클라이언트와 서버에서 모두 gx64krb5 라이브러리를 사용해야 합니다. 즉, 클라이언트와 서버가 동일한 SNC 라이브러리를 사용해야 합니다.

1. [SAP Note 2115486](https://launchpad.support.sap.com/)(SAP s-user 필요)에서 gx64krb5.dll을 다운로드합니다. 1\.0.11.x 버전 이상이 있는지 확인합니다. 게이트웨이를 통해 SSO 연결을 시도하기 전에 SAP GUI에서 SSO 연결을 테스트하려는 경우, gsskrb5.dll(라이브러리의 32비트 버전)도 다운로드합니다(권장). SAP GUI는 32비트 전용이므로, SAP GUI를 사용해서 테스트하려면 32비트 버전이 필요합니다.

1. 게이트웨이 서비스 사용자가 액세스할 수 있는 게이트웨이 머신의 위치에 gx64krb5.dll을 저장합니다. SAP GUI를 사용하여 SSO 연결을 테스트하려는 경우, 머신에 gsskrb5.dll의 복사본을 저장하고 해당 위치를 가리키도록 **SNC_LIB** 환경 변수를 설정합니다. 서비스 사용자가 가장하는 게이트웨이 서비스 사용자와 AD(Active Directory) 사용자에게 모두, gx64krb5.dll의 복사본에 대한 읽기 및 실행 권한이 있어야 합니다. 인증된 사용자 그룹에 .dll에 대한 권한을 부여하는 것이 좋습니다. 테스트에 사용할 게이트웨이 서비스 사용자와 Active Directory 사용자 둘 다에게 이러한 사용 권한을 명시적으로 부여할 수도 있습니다.

1. gx64krb5.dll을 사용하여 SSO에 대해 BW 서버를 구성하지 않은 경우에는 SAP BW 서버가 액세스할 수 있는 SAP BW 서버 머신의 위치에 .dll의 다른 복사본을 저장합니다. 

    SAP BW 서버에서 사용하도록 gx64krb5.dll을 구성하는 방법에 대한 자세한 내용은 [SAP 설명서](https://launchpad.support.sap.com/#/notes/2115486)(SAP s-user 필요)를 참조하세요.

1. 클라이언트 및 서버 머신에서 **SNC_LIB** 및 **SNC_LIB_64** 환경 변수를 설정합니다. 
    - gsskrb5.dll을 사용하는 경우 **SNC_LIB** 변수를 절대 경로로 설정합니다. 
    - gx64krb5.dll을 사용하는 경우 **SNC_LIB_64** 변수를 절대 경로로 설정합니다.

## <a name="configure-an-sap-bw-service-user-and-enable-snc-communication-on-the-bw-server"></a>BW 서버에서 SAP BW 서비스 사용자 구성 및 SNC 통신 활성화

gx64krb5를 사용하여 SNC 통신(예: SSO)에 대해 SAP BW 서버를 구성하지 않은 경우에는 이 섹션을 완료합니다.

> [!NOTE]
> 이 섹션에서는 이미 BW의 서비스 사용자를 만들었으며, 적절한 SPN(즉, *SAP/* 로 시작하는 이름)을 바인딩했다고 가정합니다.

1. 서비스 사용자에게 SAP BW 애플리케이션 서버에 대한 액세스 권한을 부여합니다.

    1. SAP BW 서버 머신에서 로컬 관리자 그룹에 서비스 사용자를 추가합니다. **컴퓨터 관리** 프로그램을 열고 서버의 로컬 관리자 그룹을 확인합니다. 

        ![컴퓨터 관리 프로그램](media/service-gateway-sso-kerberos/computer-management.png)

    1. 로컬 관리자 그룹을 두 번 클릭하고, **추가**를 선택하여 그룹에 서비스 사용자를 추가합니다. 

    1. **이름 확인**을 선택하여 이름을 올바르게 입력했는지 확인하고 **확인**을 선택합니다.

1. SAP BW 서버의 서비스 사용자를 SAP BW 서버 머신에서 SAP BW 서버 서비스를 시작하는 사용자로 설정합니다.

    1. **실행**을 열고 **Services.msc**를 입력합니다. 

    1. SAP BW 애플리케이션 서버 인스턴스에 해당하는 서비스를 찾아서 마우스 오른쪽 단추로 클릭한 다음, **속성**을 선택합니다.

        ![속성이 강조 표시된 서비스의 스크린샷](media/service-gateway-sso-kerberos/server-properties.png)

    1. **로그온** 탭으로 전환하고, 사용자를 자신의 SAP BW 서비스 사용자로 변경합니다. 

    1. 사용자의 암호를 입력하고 **확인**을 선택합니다.

1. SAP 로그온에서 서버에 로그인한 다음, RZ10 트랜잭션을 사용하여 다음 프로필 매개 변수를 설정합니다.

    1. **snc/identity/as** 프로필 매개 변수를 *p:&lt;직접 만든 SAP BW 서비스 사용자&gt;* 로 설정합니다. 예를 들어 *p:BWServiceUser\@MYDOMAIN.COM*으로 설정합니다. CommonCryptoLib를 SNC 라이브러리로 사용할 때는 UPN 앞에 *p:CN=* 이 오는 것과 달리, 서비스 사용자의 UPN 앞에 *p:* 가 옵니다.

    1. **snc/gssapi\_lib** 프로필 매개 변수를 *&lt;BW 서버의 gx64krb5.dll 경로&gt;* 로 설정합니다. SAP BW 애플리케이션 서버가 액세스할 수 있는 위치에 라이브러리를 저장합니다.

    1. 다음과 같은 추가 프로필 매개 변수를 설정하고 요구 사항에 맞게 값을 적절하게 변경합니다. 마지막 5개 옵션은 클라이언트가 SNC를 구성하지 않고도 SAP 로그온을 사용하여 SAP BW 서버에 연결할 수 있게 해줍니다.

        | **설정** | **값** |
        | --- | --- |
        | snc/data\_protection/max | 3 |
        | snc/data\_protection/min | 1 |
        | snc/data\_protection/use | 9 |
        | snc/accept\_insecure\_cpic | 1 |
        | snc/accept\_insecure\_gui | 1 |
        | snc/accept\_insecure\_r3int\_rfc | 1 |
        | snc/accept\_insecure\_rfc | 1 |
        | snc/permit\_insecure\_start | 1 |

    1. **snc/enable** 속성을 1로 설정합니다.

1. 이러한 프로필 매개 변수를 설정한 후에 서버 머신에서 SAP 관리 콘솔을 열고 SAP BW 인스턴스를 다시 시작합니다. 

   서버가 시작되지 않으면 프로필 매개 변수를 올바르게 설정했는지 확인합니다. 프로필 매개 변수 설정에 대한 자세한 내용은 [SAP 설명서](https://help.sap.com/saphelp_nw70ehp1/helpdata/en/e6/56f466e99a11d1a5b00000e835363f/frameset.htm)를 참조하세요. 이 문서의 [문제 해결](#troubleshooting) 섹션도 참조할 수 있습니다.

## <a name="map-an-sap-bw-user-to-an-active-directory-user"></a>SAP BW 사용자를 Active Directory 사용자에 매핑

아직 수행하지 않은 경우 Active Directory 사용자를 SAP BW 애플리케이션 서버 사용자에 매핑하고 SAP 로그온에서 SSO 연결을 테스트합니다.

1. SAP 로그온을 사용하여 SAP BW 서버에 로그인합니다. 트랜잭션 SU01을 실행합니다.

1. **사용자**에 SSO 연결을 사용하도록 설정할 SAP BW 사용자를 입력합니다. SAP 로그온 창의 왼쪽 위에 있는 **편집** 아이콘(펜 이미지)을 선택합니다.

    ![SAP BW 사용자 유지 관리 화면](media/service-gateway-sso-kerberos/user-maintenance.png)

1. **SNC** 탭을 선택합니다. SNC 이름 입력란에 *p:&lt;Active Directory 사용자&gt;@&lt;도메인&gt;* 을 입력합니다. SNC 이름의 경우 Active Directory 사용자의 UPN 앞에 *p:* 가 와야 합니다. UPN은 대/소문자를 구분합니다.

   지정하는 Active Directory 사용자는 SAP BW 애플리케이션 서버에 대한 SSO 액세스를 활성화하려는 개인이나 조직에 속해 있어야 합니다. 예를 들어 testuser\@TESTDOMAIN.COM 사용자에 대해 SSO 액세스를 사용하도록 설정하려면 *p:testuser\@TESTDOMAIN.COM*을 입력합니다.

    ![SAP BW 유지 관리 사용자 화면](media/service-gateway-sso-kerberos/maintain-users.png)

1. 화면 왼쪽 위에 있는 **저장** 아이콘(플로피 디스크 이미지)을 선택합니다.

## <a name="test-sign-in-via-sso"></a>SSO를 통한 로그인 테스트

SSO 액세스를 사용하도록 설정한 Active Directory 사용자로, SSO를 통한 SAP 로그온을 사용하여 서버에 로그인할 수 있는지 확인합니다.

1. 방금 SSO 액세스를 사용하도록 설정한 Active Directory 사용자로, SAP 로그온이 설치된 도메인의 머신에 로그인합니다. SAP 로그온을 시작하고 새 연결을 만듭니다.

1. 이전에 다운로드한 gsskrb5.dll 파일을 로그인한 머신의 위치에 복사합니다. **SNC_LIB** 환경 변수를 이 위치의 절대 경로로 설정합니다.

1. SAP 로그온을 시작하고 새 연결을 만듭니다.

1. **새 시스템 항목 만들기** 화면에서 **사용자 지정 시스템**을 선택하고 **다음**을 선택합니다.

    ![새 시스템 항목 만들기 화면](media/service-gateway-sso-kerberos/new-system-entry.png)

1. 다음 화면에서 애플리케이션 서버, 인스턴스 번호 및 시스템 ID를 비롯한 적절한 세부 정보를 입력합니다. **마침**을 선택합니다.

1. 새 연결을 마우스 오른쪽 단추로 클릭하고 **속성**을 선택한 다음, **네트워크** 탭을 선택합니다. 

1. **SNC 이름** 상자에 *p:&lt;SAP BW 서비스 사용자의 UPN&gt;* 을 입력합니다. 예를 들어 *p:BWServiceUser\@MYDOMAIN.COM*으로 설정합니다. **확인**을 선택합니다.

    ![시스템 항목 속성 화면](media/service-gateway-sso-kerberos/system-entry-properties.png)

1. 방금 만든 연결을 두 번 클릭하여 SAP BW 서버와의 SSO 연결을 시도합니다. 

   이 연결이 성공하면 다음 섹션을 계속 진행합니다. 또는 이 문서의 이전 단계를 검토하여 올바르게 완료되었는지 확인하거나, [문제 해결](#troubleshooting) 섹션을 검토합니다. 이 컨텍스트에서 SSO를 통해 SAP BW 서버에 연결할 수 없는 경우에는 게이트웨이 컨텍스트에서 SSO를 사용하여 SAP BW 서버에 연결할 수 없습니다.

## <a name="add-registry-entries-to-the-gateway-machine"></a>게이트웨이 머신에 레지스트리 항목 추가

Power BI Desktop에서 연결하려는 머신 및 게이트웨이가 설치된 머신의 레지스트리에 필요한 레지스트리 항목을 추가합니다. 이 레지스트리 항목을 추가하려면 다음 명령을 실행합니다.

- ```REG ADD HKLM\SOFTWARE\Wow6432Node\SAP\gsskrb5 /v ForceIniCredOK /t REG_DWORD /d 1 /f```

- ```REG ADD HKLM\SOFTWARE\SAP\gsskrb5 /v ForceIniCredOK /t REG_DWORD /d 1 /f```

## <a name="add-a-new-sap-bw-application-server-data-source-to-the-power-bi-service-or-edit-an-existing-one"></a>Power BI 서비스에 새 SAP BW 애플리케이션 서버 데이터 원본 추가 또는 기존 데이터 원본 편집

1. Power BI Desktop에서 SAP BW 서버에 로그인할 때와 마찬가지로, SAP BW 애플리케이션 서버의 **호스트 이름**, **시스템 번호** 및 **클라이언트 ID**를 데이터 원본 구성 창에 입력합니다.

1. **SNC 파트너 이름** 필드에 *p:&lt;SAP BW 서비스 사용자에 매핑한 SPN&gt;* 을 입력합니다. 예를 들어 SPN이 SAP/BWServiceUser\@MYDOMAIN.COM인 경우 **SNC 파트너 이름** 필드에 *p:SAP/BWServiceUser\@MYDOMAIN.COM*을 입력합니다.

1. SNC 라이브러리의 경우 **SNC\_LIB** 또는 **SNC\_LIB\_64**를 선택합니다. 게이트웨이 컴퓨터의 **SNC\_LIB\_64**가 gx64krb5.dll을 가리키는지 확인합니다. 또는 **사용자 지정** 옵션을 선택하고 게이트웨이 머신에 있는 gx64krb5.dll의 절대 경로를 입력할 수 있습니다.

1. **DirectQuery 쿼리에 Kerberos를 통한 SSO 사용**을 선택한 다음, **적용**을 선택합니다. 테스트 연결이 실패할 경우 이전의 설정 및 구성 단계가 올바르게 완료되었는지 확인합니다.

1. [Power BI 보고서 실행](service-gateway-sso-kerberos.md#run-a-power-bi-report)

## <a name="troubleshooting"></a>문제 해결

### <a name="troubleshoot-gx64krb5-configuration"></a>gx64krb5 구성 문제 해결

다음과 같은 문제가 발생할 경우, 아래 단계에 따라 gx64krb5 설치 및 SSO 연결 문제를 해결합니다.

* gx64krb5 설정 단계를 완료하면 오류가 발생합니다. 예를 들어 프로필 매개 변수를 변경한 후에 SAP BW 서버가 시작되지 않습니다. 서버 로그(서버 머신의 …work\dev\_w0)를 살펴보고 해당 오류를 수정합니다. 

* 로그온 실패로 인해 SAP BW 서비스를 시작할 수 없습니다. SAP BW *start-as* 사용자를 설정할 때 잘못된 암호를 입력했을 수 있습니다. Active Directory 환경의 머신에 SAP BW 서비스 사용자로 로그인하여 암호를 확인합니다.

* 서버가 시작되지 않도록 하는 기본 데이터 원본 자격 증명(예: SQL Server) 관련 오류가 표시되면 서비스 사용자에게 SAP BW 데이터베이스에 대한 액세스 권한을 부여했는지 확인합니다.

* 다음과 같은 메시지가 표시됩니다. *‘(GSS-API) 지정한 대상을 알 수 없거나 연결할 수 없습니다.’* 이 오류는 일반적으로 잘못된 SNC 이름을 지정했음을 의미합니다. 클라이언트 애플리케이션에서는 서비스 사용자의 UPN 앞에 *p:CN=* 이 아닌 *p:* 만 와야 합니다.

* 다음과 같은 메시지가 표시됩니다. *‘(GSS-API) 입력한 이름이 잘못되었습니다.’* 서버의 SNC ID 프로필 매개 변수 값에 *p:* 가 있는지 확인합니다.

* 다음과 같은 메시지가 표시됩니다. *‘(SNC 오류) 지정한 모듈을 찾을 수 없습니다.’* 이 오류는 대체로 높은 권한(관리자 권한)으로 액세스해야 하는 위치에 gx64krb5를 저장할 경우에 발생합니다.

### <a name="troubleshoot-gateway-connectivity-issues"></a>게이트웨이 연결 문제 해결

1. 게이트웨이 로그를 확인합니다. 게이트웨이 구성 애플리케이션을 열고 **진단**, **로그 내보내기**를 차례로 선택합니다. 가장 최근 오류는 검사하는 로그 파일의 끝에 있습니다.

    ![진단이 강조 표시된 온-프레미스 데이터 게이트웨이 애플리케이션](media/service-gateway-sso-kerberos/gateway-diagnostics.png)

1. SAP BW 추적을 켜고 생성된 로그 파일을 살펴봅니다. 사용할 수 있는 SAP BW 추적(예: CPIC 추적)에는 몇 가지 유형이 있습니다.

   a. CPIC 추적을 사용하도록 설정하려면 두 가지 환경 변수 **CPIC\_TRACE** 및 **CPIC\_TRACE\_DIR**을 설정합니다.

      첫 번째 변수는 추적 수준을 설정하고, 두 번째 변수는 추적 파일 디렉터리를 설정합니다. 이 디렉터리는 인증된 사용자 그룹의 구성원이 쓸 수 있는 위치여야 합니다. 
 
    b. **CPIC\_TRACE**를 *3*으로 설정하고, **CPIC\_TRACE\_DIR**을 추적하려는 파일이 기록된 디렉터리로 설정합니다. 예:

      ![CPIC 추적](media/service-gateway-sso-kerberos/cpic-tracing.png)

    c. 문제를 재현하고, **CPIC\_TRACE\_DIR**에 추적 파일이 있는지 확인합니다. 
    
    d. 추적 파일의 내용을 검사하여 차단 문제를 확인합니다. 예를 들어 gx64krb5.dll이 제대로 로드되지 않았거나 예상하지 않은 Active Directory 사용자가 SSO 연결 시도를 시작한 것을 확인할 수 있습니다.

## <a name="next-steps"></a>다음 단계

온-프레미스 데이터 게이트웨이 및 DirectQuery에 대한 자세한 내용은 다음 리소스를 참조하세요.

* [온-프레미스 데이터 게이트웨이란?](/data-integration/gateway/service-gateway-onprem)
* [Power BI의 DirectQuery](desktop-directquery-about.md)
* [DirectQuery에서 지원하는 데이터 원본](desktop-directquery-data-sources.md)
* [DirectQuery 및 SAP BW](desktop-directquery-sap-bw.md)
* [DirectQuery 및 SAP HANA](desktop-directquery-sap-hana.md)
