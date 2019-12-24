---
title: SAP HANA에 대한 SSO(Single Sign-On)에 Kerberos 사용
description: SAP HANA 서버를 구성하여 Power BI 서비스로부터 SSO를 사용하도록 설정
author: arthiriyer
ms.author: arthii
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 10/10/2019
LocalizationGroup: Gateways
ms.openlocfilehash: 9c2eb554a4e3b3ec90d3fe17145e0ec277298e1b
ms.sourcegitcommit: f77b24a8a588605f005c9bb1fdad864955885718
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2019
ms.locfileid: "74697500"
---
# <a name="use-kerberos-for-single-sign-on-sso-to-sap-hana"></a>SAP HANA에 대한 SSO(Single Sign-On)에 Kerberos 사용

이 문서에서는 Power BI 서비스로부터 SSO를 사용하도록 SAP HANA 데이터 원본을 구성하는 방법을 설명합니다.

> [!NOTE]
> Kerberos SSO를 사용하는 SAP HANA 기반 보고서를 새로 고치기 전에 이 문서의 단계와 [Kerberos SSO 구성](service-gateway-sso-kerberos.md) 단계를 모두 완료합니다.

## <a name="enable-sso-for-sap-hana"></a>SAP HANA에 대해 SSO를 사용하도록 설정

SAP HANA에 SSO를 사용하도록 설정하려면 다음 단계를 수행합니다.

1. SAP HANA 서버가 SAP HANA 서버 플랫폼 수준에 필요한 최소 버전을 실행 중인지 확인합니다.
   - [HANA 2 SPS 01 Rev 012.03](https://launchpad.support.sap.com/#/notes/2557386)
   - [HANA 2 SPS 02 Rev 22](https://launchpad.support.sap.com/#/notes/2547324)
   - [HANA 1 SP 12 Rev 122.13](https://launchpad.support.sap.com/#/notes/2528439)

2. 게이트웨이 머신에 최신 SAP HANA ODBC 드라이버를 설치합니다. 최소 버전은 HANA ODBC 2017년 8월 릴리스된 2.00.020.00 버전입니다.

3. SAP HANA 서버가 Kerberos 기반 SSO에 대해 구성되었는지 확인합니다. Kerberos를 사용하여 SAP HANA를 위한 SSO 설정에 대한 자세한 내용은 SAP HANA 보안 가이드에서 [Kerberos를 사용한 Single Sign-On](https://help.sap.com/viewer/b3ee5778bc2e4a089d3299b82ec762a7/2.0.03/1885fad82df943c2a1974f5da0eed66d.html)을 참조하세요. 또한 해당 페이지에서 특히 SAP Note 1837331 – HANA DBSSO Kerberos/Active Directory 방법 링크를 참조하세요.

또한 약간의 성능 개선 효과를 볼 수 있으므로 다음과 같은 추가 단계를 수행하는 것이 좋습니다.

1. 게이트웨이 설치 디렉터리에서 다음 구성 파일을 찾아서 엽니다. Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll.config.

2. `FullDomainResolutionEnabled` 속성을 찾아서 값을 `True`로 변경합니다.

    ```xml
    <setting name=" FullDomainResolutionEnabled " serializeAs="String">
          <value>True</value>
    </setting>
    ```

이제 [Power BI 보고서를 실행](service-gateway-sso-kerberos.md#run-a-power-bi-report)합니다.

## <a name="next-steps"></a>다음 단계

온-프레미스 데이터 게이트웨이 및 DirectQuery에 대한 자세한 내용은 다음 리소스를 참조하세요.

* [온-프레미스 데이터 게이트웨이란?](/data-integration/gateway/service-gateway-onprem)
* [Power BI의 DirectQuery](desktop-directquery-about.md)
* [DirectQuery에서 지원하는 데이터 원본](desktop-directquery-data-sources.md)
* [DirectQuery 및 SAP BW](desktop-directquery-sap-bw.md)
* [DirectQuery 및 SAP HANA](desktop-directquery-sap-hana.md)
