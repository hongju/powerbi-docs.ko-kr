---
title: SSL 인증서를 만드는 중
description: 개발자 서버용 인증서를 수동으로 만들기 위한 해결 방법 지침
author: zBritva
ms.author: v-ilgali
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: tutorial
ms.date: 06/18/2019
ms.openlocfilehash: 3287e8a7eb1c36c3f0d8a1fc24faa0442de2dddf
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/23/2019
ms.locfileid: "68425439"
---
# <a name="creating-ssl-certificate"></a>SSL 인증서를 만드는 중

다음 명령을 실행하여 Windows 8 이상의 powershell New-SelfSignedCertificate cmdlet을 통해 인증서를 생성합니다.

도구를 사용하려면 **Windows** **7**용 OpenSSL을 설치해야 합니다. 명령줄에서 `openssll` 유틸리티를 사용할 수 있어야 합니다.

OpenSSL을 설치하려면 [https://www.openssl.org](https://www.openssl.org) 또는 [https://wiki.openssl.org/index.php/Binaries](https://wiki.openssl.org/index.php/Binaries)를 방문하세요.

```cmd
pbiviz --create-cert
```

## <a name="create-certificate-mac-os-x"></a>인증서 만들기(Mac OS X)

일반적으로 OpenSSL 유틸리티는 Linux 또는 Mac OS X 운영 체제에서 제공됩니다.

또는 다음에서 설치할 수 있습니다.

*Brew* 패키지 관리자

```cmd
brew install openssl
brew link openssl --force
```

또는 *MacPorts*

```cmd
sudo port install openssl
```

OpenSSL을 설치한 후 새 인증서 호출을 생성하려면 다음을 실행합니다.

```cmd
pbiviz --create-cert
```

## <a name="create-certificate-linux"></a>인증서 만들기(Linux)

사용 중인 Linux 운영 체제에서 OpenSSL 유틸리티가 제공되지 않는 경우 다음 명령을 사용하여 설치할 수 있습니다.

*APT* 패키지 관리자의 경우:

```cmd
sudo apt-get install openssl
```

*Yellowdog Updater*의 경우:

```cmd
yum install openssl
```

*Redhat Package Manager*의 경우:

```cmd
rpm install openssl
```

운영 체제 호출에서 OpenSSL을 이미 사용할 수 있는 경우 다음 명령을 실행합니다.

```cmd
pbiviz --create-cert
```

새 인증서가 생성됩니다.

또는 [https://www.openssl.org](https://www.openssl.org) 또는 [https://wiki.openssl.org/index.php/Binaries](https://wiki.openssl.org/index.php/Binaries)에서 가져옵니다.

## <a name="generate-certificate-manually"></a>수동으로 인증서 생성

모든 도구에서 생성된 인증서를 지정할 수 있습니다.

시스템에 OpenSSL이 설치되어 있는 경우 다음 명령을 실행하여 새 인증서를 생성할 수 있습니다.

```cmd
openssl req -x509 -newkey rsa:4096 -keyout PowerBICustomVisualTest_private.key -out PowerBICustomVisualTest_public.crt -days 365
```

일반적으로 PowerBI-visuals-tools 웹 서버 인증서는 다음 위치에 있습니다.

```cmd
%appdata%\npm\node_modules\PowerBI-visuals-tools\certs
```

위 경로에는 도구의 전역 인스턴스 인증서가 있습니다.

또는

```cmd
<custom visual project root>\node_modules\PowerBI-visuals-tools\certs
```

위 경로에는 도구의 로컬 인스턴스 인증서가 있습니다.

PEM 형식을 사용하는 경우 cert 파일을 `PowerBICustomVisualTest_public.cer`로 저장하고, privatekey를 `PowerBICustomVisualTest_public.key`로 저장해야 합니다.
PFX 형식을 사용하는 경우 cert 파일을 `PowerBICustomVisualTest_public.pfx`로 저장합니다.

PFX cert 파일에 암호가 필요한 경우 서버 섹션에 있는 다음 파일에서 지정해야 합니다.

```cmd
\PowerBI-visuals-tools\config.json
```

위 파일에서 다음과 같이 지정합니다.

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
