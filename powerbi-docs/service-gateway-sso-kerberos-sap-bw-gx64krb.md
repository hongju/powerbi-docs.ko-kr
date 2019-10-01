---
title: gx64krb5를 사용하는 SAP BW로의 SSO(Single Sign-On)에 Kerberos 사용
description: gx64krb5를 사용하여 Power BI 서비스에서 SSO를 사용하도록 SAP BW 서버 구성
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 08/01/2019
LocalizationGroup: Gateways
ms.openlocfilehash: 5dd31dc4333dc03100370100e16eadab6012c1f0
ms.sourcegitcommit: 7a0ce2eec5bc7ac8ef94fa94434ee12a9a07705b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/18/2019
ms.locfileid: "71106334"
---
# <a name="use-kerberos-for-single-sign-on-sso-to-sap-bw-using-gx64krb5"></a>gx64krb5를 사용하는 SAP BW로의 SSO(Single Sign-On)에 Kerberos 사용

이 문서에서는 gx64krb5를 사용하여 Power BI 서비스로부터 SSO를 사용하도록 SAP BW 서버를 구성하는 방법을 설명합니다.

> [!NOTE]
> Power BI 서비스에서 Kerberos SSO를 사용하는 SAP BW 애플리케이션 서버 기반 보고서에 대한 새로 고침을 사용하도록 설정하려면 [Kerberos SSO 구성](service-gateway-sso-kerberos.md)의 단계 이외에 이 문서의 단계를 완료할 수 있습니다. 그러나 Microsoft는 SNC 라이브러리로 CommonCryptoLib을 사용할 것을 권장합니다. SAP가 더 이상 gx64krb5에 대한 지원을 제공하지 않으며 게이트웨이에서 사용하도록 구성하는 데 필요한 단계는 CommonCryptoLib에 비해 훨씬 복잡합니다. CommonCryptoLib를 사용하여 SSO를 구성하는 방법에 대해서는 [CommonCryptoLib을 사용하여 SSO에 대해 SAP BW 구성](service-gateway-sso-kerberos-sap-bw-commoncryptolib.md)을 참조하세요. CommonCryptoLib _또는_ gx64krb5의 구성을 완료해야 합니다. 두 라이브러리에 대한 구성 단계를 모두 완료하지 마세요.

### <a name="set-up-gx64krb5gsskrb5-on-gateway-machine-and-the-sap-bw-server"></a>게이트웨이 머신 및 SAP BW 서버에서 gx64krb5/gsskrb5 설정

> [!NOTE]
> `gx64krb5` 및 `gsskrb5`는 SAP에서 더 이상 적극적으로 지원되지 않습니다. 자세한 내용은 [SAP 참고 352295](https://launchpad.support.sap.com/#/notes/352295)를 참조하세요. 또한 `gx64krb5`는 데이터 게이트웨이에서 SAP BW Message Server로의 SSO 연결을 허용하지 않습니다. SAP BW Application Server에 대한 연결만 가능합니다. 이 애플리케이션 서버 전용 제한은 SNC 라이브러리로 [CommonCryptoLib](service-gateway-sso-kerberos-sap-bw-commoncryptolib.md)을 사용하는 경우에는 해당하지 않습니다. 다른 SNC 라이브러리도 BW SSO에 사용할 수 있지만 Microsoft에서 공식적으로 지원하지는 않습니다.

`gx64krb5` \ `gsskrb5`는 클라이언트와 서버 모두에서 게이트웨이를 통해 SSO 연결을 완료하는 데 사용해야 합니다. 즉, 클라이언트와 서버가 모두 동일한 SNC 라이브러리를 사용해야 합니다.

1. [SAP 노트 2115486](https://launchpad.support.sap.com/)에서 `gx64krb5`를 다운로드합니다(SAP s-user 필요). 1\.0.11.x 버전 이상이 있는지 확인합니다. 게이트웨이를 통해 SSO 연결을 시도하기 전에 SAP GUI에서 SSO 연결을 테스트하려는 경우에도 `gsskrb5`(라이브러리의 32 비트 버전)을 다운로드합니다(권장). SAP GUI는 32비트에서만 사용할 수 있으므로 SAP GUI를 사용하여 테스트하려면 32비트 버전이 필요 합니다.

1. 게이트웨이 서비스 사용자가 액세스할 수 있는(SAP 로그온을 사용하여 SSO 연결을 테스트하려는 경우 SAP GUI에서도 액세스 가능) 게이트웨이 머신의 특정 위치에 `gx64krb5`를 저장합니다. 서비스 사용자가 가장할 게이트웨이 서비스 사용자와 AD(Active Directory) 사용자 모두에게 .dll에 대한 읽기 및 실행 권한이 있어야 합니다. 인증된 사용자 그룹에 .dll에 대한 권한을 부여하는 것이 좋습니다. 게이트웨이 서비스 사용자와 테스트하는 데 사용할 Active Directory 사용자 모두에게 이러한 사용 권한을 명시적으로 부여할 수도 있습니다.

1. BW 서버가 아직 gx64krb5/gsskrb5를 사용하여 SSO에 대해 구성되지 않은 경우 SAP BW 서버에서 액세스할 수 있는 위치에서 SAP BW 서버 머신에 다른 복사본을 배치합니다. 

1. 클라이언트 및 서버 머신에서 `SNC_LIB` 또는 `SNC_LIB_64` 환경 변수를 설정합니다. gsskrb5를 사용하는 경우 `SNC_LIB` 변수를 gsskrb5.dll의 절대 경로로 설정합니다. gx64krb5를 사용하는 경우 `SNC_LIB_64` 변수를 gx64krb5.dll의 절대 경로로 설정합니다.

### <a name="configure-an-sap-bw-service-user-and-enable-snc-communication"></a>SAP BW 서비스 사용자 구성 및 SNC 통신 활성화

아직 gx64krb5/gsskrb5를 사용하여 SNC 통신(예: SSO)에 대해 SAP BW 서버를 구성하지 않은 경우 이 섹션을 완료합니다.

> [!NOTE]
> 이 섹션에서는 이미 BW에 대한 서비스 사용자를 만들고 적절한 SPN(예: `SAP/`으로 시작하는 항목)을 바인딩했다고 가정합니다.

1. 서비스 사용자에게 SAP BW 애플리케이션 서버에 대한 액세스 권한을 부여합니다.

    1. SAP BW 서버 머신에서 로컬 관리자 그룹에 서비스 사용자를 추가합니다. 컴퓨터 관리 프로그램을 열고 서버에 대한 로컬 관리자 그룹을 두 번 클릭합니다.

        ![컴퓨터 관리 프로그램의 스크린샷](media/service-gateway-sso-kerberos/computer-management.png)

    1. 로컬 관리자 그룹을 두 번 클릭하고, **추가**를 선택하여 그룹에 서비스 사용자를 추가합니다. 이름을 올바르게 입력되었는지 확인하려면 **이름 확인**을 선택합니다. **확인**을 선택합니다.

1. SAP BW 서버의 서비스 사용자를 SAP BW 서버 머신에서 SAP BW 서버 서비스를 시작하는 사용자로 설정합니다.

    1. **실행**을 열고 “Services.msc”를 입력합니다. SAP BW 애플리케이션 서버 인스턴스에 해당하는 서비스를 찾습니다. 이를 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.

        ![속성이 강조 표시된 서비스의 스크린샷](media/service-gateway-sso-kerberos/server-properties.png)

    1. **로그온** 탭으로 전환하고, 사용자를 자신의 SAP BW 서비스 사용자로 변경합니다. 사용자의 암호를 입력하고 **확인**을 선택합니다.

1. SAP 로그온의 서버에 로그인하고 RZ10 트랜잭션을 사용하여 다음 프로필 매개 변수를 설정합니다.

    1. snc/identity/as 프로필 매개 변수를 p:\<자신이 만든 SAP BW 서비스 사용자\>(예: p:BWServiceUser@MYDOMAIN.COM)로 설정합니다. 서비스 사용자의 UPN 앞에 오는 p:에 유의하세요. p:CN=이 아닙니다. 공용 암호화 라이브러리가 SNC 라이브러리로 사용될 때처럼 p:CN=이 아닙니다.

    1. snc/gssapi\_lib 프로필 매개 변수를 \<BW 서버 머신의 gsskrb5.dll/gx64krb5.dll 경로(OS 비트 수에 따라 사용하는 라이브러리가 달라짐)\>로 설정합니다. 라이브러리는 SAP BW 애플리케이션 서버가 액세스할 수 있는 위치에 배치해야 합니다.

    1. 또한 다음 추가 프로필 매개 변수를 설정하고 필요에 맞게 값을 변경합니다. 마지막 5개 옵션은 클라이언트가 SNC를 구성하지 않고 SAP 로그온을 사용하여 SAP BW 서버에 연결할 수 있게 해줍니다.

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

    1. property snc/enable을 1로 설정합니다.

1. 이러한 프로필 매개 변수를 설정한 후 서버 머신에서 SAP 관리 콘솔을 열고 SAP BW 인스턴스를 다시 시작합니다. 서버가 시작되지 않으면 프로필 매개 변수를 올바르게 설정했는지 확인합니다. 프로필 매개 변수 설정에 자세한 내용은 [SAP 설명서](https://help.sap.com/saphelp_nw70ehp1/helpdata/en/e6/56f466e99a11d1a5b00000e835363f/frameset.htm)를 참조하세요. 또한 문제가 발생할 경우 이 섹션의 뒷부분에서 문제 해결 정보를 참조할 수 있습니다.

### <a name="map-a-sap-bw-user-to-an-active-directory-user"></a>SAP BW 사용자를 Active Directory 사용자에 매핑

아직 완료하지 않은 경우 SAP BW 애플리케이션 서버 사용자에 Active Directory 사용자를 매핑하고 SAP 로그온의 SSO 연결을 테스트합니다.

1. SAP 로그온을 사용하여 SAP BW 서버에 로그인합니다. 트랜잭션 SU01을 실행합니다.

1. **사용자**에 SSO 연결을 사용하도록 설정하려는 SAP BW 사용자를 입력합니다(위의 스크린샷에서는 BIUSER의 사용 권한 설정). SAP 로그온 창의 왼쪽 상단 근처에서 **편집** 아이콘(펜 이미지)을 선택합니다.

    ![SAP BW 사용자 유지 관리 화면의 스크린샷](media/service-gateway-sso-kerberos/user-maintenance.png)

1. **SNC** 탭을 선택합니다. SNC 이름 입력란에 p:\<Active Directory 사용자\>@\<도메인\>을 입력합니다. Active Directory 사용자의 UPN 앞에 와야 하는 p:라는 필수 항목에 유의하세요. 지정하는 Active Directory 사용자는 SAP BW 애플리케이션 서버에 대한 SSO 액세스를 활성화하려는 개인이나 조직에 속해 있어야 합니다. 예를 들어 사용자 testuser\@TESTDOMAIN.COM에 대해 SSO 액세스를 사용하도록 설정하려면 p:testuser@TESTDOMAIN.COM을 입력합니다.

    ![SAP BW 유지 관리 사용자 화면의 스크린샷](media/service-gateway-sso-kerberos/maintain-users.png)

1. 화면 왼쪽 상단에서 **저장** 아이콘(플로피 디스크 이미지)을 선택합니다.

### <a name="test-sign-in-by-using-sso"></a>SSO를 사용하여 로그인 테스트

SAP 로그온을 사용하여 SSO를 통해 방금 전에 SSO 액세스를 허용한 Active Directory 사용자로 서버에 로그인할 수 있는지 확인합니다.

1. SAP 로그온이 설치된 머신에 방금 SSO 액세스를 활성화한 Active Directory 사용자로 로그인합니다. SAP 로그온을 시작하고 새 연결을 만듭니다.

1. **새 시스템 항목 만들기** 화면에서 **사용자 지정 시스템** > **다음**을 선택합니다.

    ![새 시스템 항목 만들기 화면의 스크린샷](media/service-gateway-sso-kerberos/new-system-entry.png)

1. 다음 화면에서 애플리케이션 서버, 인스턴스 번호 및 시스템 ID를 비롯한 적절한 세부 정보를 입력합니다. **마침**을 선택합니다.

1. 새 연결을 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다. **네트워크** 탭을 선택합니다. **SNC 이름** 텍스트 상자에서 p:\<SAP BW 서비스 사용자의 UPN\>(예: p:BWServiceUser@MYDOMAIN.COM)을 입력합니다. 그런 다음, **확인**을 선택합니다.

    ![시스템 항목 속성 화면의 스크린샷](media/service-gateway-sso-kerberos/system-entry-properties.png)

1. 방금 만든 연결을 두 번 클릭하여 SAP BW 서버와의 SSO 연결을 시도합니다. 이 연결에 성공하면 다음 단계를 진행합니다. 또는 이 문서의 이전 단계를 검토하여 올바르게 완료되었는지 확인하거나 아래의 문제 해결 섹션을 검토하세요. 이 컨텍스트에서 SSO를 통해 SAP BW 서버에 연결할 수 없는 경우 게이트웨이 컨텍스트에서 SSO를 사용하여 SAP BW 서버에 연결할 수 없게 됩니다.

### <a name="add-registry-entries-to-the-gateway-machine"></a>게이트웨이 머신에 레지스트리 항목 추가

Power BI Desktop에서 연결하려는 머신 및 게이트웨이가 설치된 머신의 레지스트리에 필요한 레지스트리 항목을 추가합니다. 실행할 명령은 다음과 같습니다.

1. REG ADD HKLM\SOFTWARE\Wow6432Node\SAP\gsskrb5 /v ForceIniCredOK /t REG\_DWORD /d 1 /f

1. REG ADD HKLM\SOFTWARE\SAP\gsskrb5 /v ForceIniCredOK /t REG\_DWORD /d 1 /f

### <a name="add-a-new-sap-bw-application-server-data-source-to-the-power-bi-service-or-edit-an-existing-one"></a>Power BI 서비스에 새 SAP BW 애플리케이션 서버 데이터 원본 추가 또는 기존 데이터 원본 편집

1. Power BI Desktop에서 SAP BW 서버에 로그인할 때 입력하는 애플리케이션 서버의 **호스트 이름**, **시스템 번호** 및 **클라이언트 ID**를 데이터 원본 구성 창에 입력합니다.

1. **SNC 파트너 이름** 필드에 p: \<SAP BW 서비스 사용자에 매핑한 SPN\>을 입력합니다. 예를 들어 SPN이 SAP/BWServiceUser@MYDOMAIN.COM인 경우 **SNC 파트너 이름** 필드에 p:SAP/BWServiceUser@MYDOMAIN.COM을 입력해야 합니다.

1. SNC 라이브러리의 경우 **SNC_LIB** 또는 **SNC_LIB_64**를 선택합니다. 게이트웨이 머신의 SNC_LIB_64가 gx64krb5.dll을 가리키는지 확인합니다. 또는 "사용자 지정" 옵션을 선택하고 게이트웨이 머신에서 gx64krb5.dll에 대한 절대 경로를 제공할 수 있습니다.

1. **DirectQuery 쿼리에 Kerberos를 통해 SSO 사용** 상자를 선택하고 **적용**을 선택합니다. 테스트 연결이 실패할 경우 이전의 설정 및 구성 단계가 올바르게 완료되었는지 확인합니다.

1. [Power BI 보고서 실행](service-gateway-sso-kerberos.md#run-a-power-bi-report)

## <a name="troubleshooting"></a>문제 해결

### <a name="troubleshoot-gx64krb5gsskrb5-configuration"></a>gx64krb5/gsskrb5 구성 문제 해결

문제가 발생하는 경우 다음 단계를 따라 SAP 로그온에서 gx64krb5/gsskrb5 설치 및 SSO 연결 문제를 해결하세요.

* 서버 로그(서버 머신의 …work\dev\_w0)를 보면 gx64krb5/gsskrb5 설정 단계를 완료할 때 발생하는 오류를 해결하는 데 도움이 될 수 있습니다. 특히 프로필 매개 변수가 변경된 후 SAP BW 서버가 시작되지 않을 경우 유용합니다.

* 로그온 실패로 인해 SAP BW 서비스를 시작할 수 없는 경우 SAP BW “start-as” 사용자를 설정할 때 잘못된 암호를 제공한 것일 수 있습니다. Active Directory 환경의 머신에 SAP BW 서비스 사용자로 로그인하여 암호를 확인합니다.

* 서버 시작을 방해하는 SQL 자격 증명 관련 오류가 표시되면 서비스 사용자에게 SAP BW 데이터베이스에 대한 액세스 권한을 부여했는지 확인하세요.

* “(GSS-API) 알 수 없거나 연결할 수 없는 대상이 지정되었습니다.”라는 메시지가 표시될 수도 있습니다. 이는 일반적으로 잘못된 SNC 이름을 지정했음을 의미합니다. 클라이언트 애플리케이션에서는 서비스 사용자의 UPN보다는 “p:CN=”이 아닌 “p:”만 사용해야 합니다.

* “(GSS-API) 잘못된 이름이 제공되었습니다.”라는 메시지가 표시될 수도 있습니다. 서버의 SNC ID 프로필 매개 변수 값에 “p:”가 있는지 확인합니다.

* “(SNC 오류) 지정된 모듈을 찾지 못했습니다.”라는 메시지가 표시될 수도 있습니다. 이는 일반적으로 액세스하는 데 높은 권한(관리자 권한)이 필요한 위치에 `gsskrb5.dll/gx64krb5.dll`을 배치한 것이 원인입니다.

### <a name="troubleshoot-gateway-connectivity-issues"></a>게이트웨이 연결 문제 해결

1. 게이트웨이 로그를 확인합니다. 게이트웨이 구성 애플리케이션을 열고 **진단** > **로그 내보내기**를 선택합니다. 가장 최근의 오류는 검사한 로그 파일의 맨 아래에 있습니다.

    ![진단이 강조 표시된 온-프레미스 데이터 게이트웨이 애플리케이션의 스크린샷](media/service-gateway-sso-kerberos/gateway-diagnostics.png)

1. SAP BW 추적을 켜고 생성된 로그 파일을 살펴봅니다. 사용할 수 있는 SAP BW 추적에는 몇 가지 유형이 있습니다. 자세한 내용은 SAP 설명서를 참조하세요.

## <a name="next-steps"></a>다음 단계

**온-프레미스 데이터 게이트웨이** 및 **DirectQuery**에 대한 자세한 내용은 다음 리소스를 확인하세요.

* [온-프레미스 데이터 게이트웨이란?](/data-integration/gateway/service-gateway-getting-started)
* [Power BI의 DirectQuery](desktop-directquery-about.md)
* [DirectQuery에서 지원하는 데이터 원본](desktop-directquery-data-sources.md)
* [DirectQuery 및 SAP BW](desktop-directquery-sap-bw.md)
* [DirectQuery 및 SAP HANA](desktop-directquery-sap-hana.md)
