---
title: SSL 인증서 만들기
description: 개발자 서버용 인증서를 수동으로 만들기 위한 해결 방법 지침
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: tutorial
ms.date: 06/18/2019
ms.openlocfilehash: 224b6db8fa04a471a1ce7d1fff2b34a838d6fb9d
ms.sourcegitcommit: f7b28ecbad3e51f410eff7ee4051de3652e360e8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74060345"
---
# <a name="create-an-ssl-certificate"></a>SSL 인증서 만들기

이 문서에서는 SSL 인증서를 만드는 방법을 설명합니다.

Windows 8 이상에서 PowerShell `New-SelfSignedCertificate` cmdlet을 사용하여 인증서를 생성하려면 다음 명령을 실행합니다.

```cmd
pbiviz --install-cert
```

이 도구를 사용하려면 Windows 7용 OpenSSL을 설치해야 합니다. 명령줄에서 OpenSSL 유틸리티를 사용할 수 있어야 합니다.

OpenSSL을 설치하려면 [OpenSSL](https://www.openssl.org) 또는 [OpenSSL Binaries](https://wiki.openssl.org/index.php/Binaries)(OpenSSL 이진) 사이트로 이동합니다.

## <a name="create-a-certificate-mac-os-x"></a>인증서 만들기(Mac OS X)

일반적으로 OpenSSL 유틸리티는 Linux 또는 Mac OS X 운영 체제에서 사용할 수 있습니다.

다음 명령 중 하나를 실행하여 유틸리티를 설치할 수도 있습니다.

* *Brew* 패키지 관리자를 사용하는 경우:

    ```cmd
    brew install openssl
    brew link openssl --force
    ```

* *MacPorts*를 사용하는 경우:

    ```cmd
    sudo port install openssl
    ```

OpenSSL 유틸리티를 설치한 후에 새 인증서를 생성하려면 다음 명령을 실행합니다.

```cmd
pbiviz --install-cert
```

## <a name="create-a-certificate-linux"></a>인증서 만들기(Linux)

사용 중인 Linux 운영 체제에서 OpenSSL 유틸리티가 제공되지 않는 경우 다음 명령 중 하나를 사용하여 설치할 수 있습니다.

* *APT* 패키지 관리자의 경우:

    ```cmd
    sudo apt-get install openssl
    ```

* *Yellowdog Updater*의 경우:

    ```cmd
    yum install openssl
    ```

* *Redhat Package Manager*의 경우:

    ```cmd
    rpm install openssl
    ```

사용 중인 Linux 운영 체제에서 이미 OpenSSL 유틸리티가 제공되는 경우에는 다음 명령을 실행하여 새 인증서를 생성합니다.

```cmd
pbiviz --install-cert
```

또는 [OpenSSL](https://www.openssl.org) 또는 [OpenSSL Binaries](https://wiki.openssl.org/index.php/Binaries)(OpenSSL 이진) 사이트로 이동하여 OpenSSL 유틸리티를 가져올 수 있습니다.

## <a name="generate-the-certificate-manually"></a>수동으로 인증서 생성

모든 도구에서 인증서가 생성되도록 지정할 수 있습니다.

OpenSSL 유틸리티가 시스템에 이미 설치되어 있으면, 다음 명령을 실행하여 새 인증서를 생성합니다.

```cmd
openssl req -x509 -newkey rsa:4096 -keyout PowerBICustomVisualTest_private.key -out PowerBICustomVisualTest_public.crt -days 365
```

일반적으로 다음 중 하나를 실행하여 Power BI 시각적 개체 도구의 웹 서버 인증서를 찾을 수 있습니다.

* 전역 도구 인스턴스의 경우:

    ```cmd
    %appdata%\npm\node_modules\PowerBI-visuals-tools\certs
    ```

* 로컬 도구 인스턴스의 경우:

    ```cmd
    <custom visual project root>\node_modules\PowerBI-visuals-tools\certs
    ```

PEM 형식을 사용하는 경우에는 인증서 파일을 *PowerBICustomVisualTest_public.crt*로 저장하고, privateKey를 *PowerBICustomVisualTest_public.key*로 저장합니다.

PFX 형식을 사용하는 경우에는 인증서 파일을 *PowerBICustomVisualTest_public.pfx*로 저장합니다.

PFX 인증서 파일에 암호가 필요한 경우, 다음을 수행합니다.
1. 구성 파일에서 다음을 지정합니다.

    ```cmd
    \PowerBI-visuals-tools\config.json
    ```

1. `server` 섹션에서 “*YOUR PASSPHRASE*” 자리 표시자를 바꿔 암호를 지정합니다.

    ```cmd
    "server":{
        "root":"webRoot",
        "assetsRoute":"/assets",
        "privateKey":"certs/PowerBICustomVisualTest_private.key",
        "certificate":"certs/PowerBICustomVisualTest_public.crt",
        "pfx":"certs/PowerBICustomVisualTest_public.pfx",
        "port":"8080",
        "passphrase":"YOUR PASSPHRASE"
    }
    ```