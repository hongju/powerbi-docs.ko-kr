---
title: 자격 증명 암호화
description: 연습 - 온-프레미스 게이트웨이 데이터 원본에 대한 자격 증명 암호화
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 01/08/2020
ms.openlocfilehash: b1fc4a505aa993c606743eefb6e8fb8c0379317d
ms.sourcegitcommit: 4b926ab5f09592680627dca1f0ba016b07a86ec0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2020
ms.locfileid: "75836620"
---
# <a name="encrypt-credentials"></a>자격 증명 암호화

[Power BI Rest API](https://docs.microsoft.com/rest/api/power-bi/)를 사용하여 **엔터프라이즈 온-프레미스 게이트웨이**에서 [데이터 원본 만들기](https://docs.microsoft.com/rest/api/power-bi/gateways/createdatasource) 또는 [데이터 원본 업데이트](https://docs.microsoft.com/rest/api/power-bi/gateways/updatedatasource)를 호출할 때, 자격 증명 값이 게이트웨이의 공개 키를 사용하여 암호화해야 합니다.

아래 코드 예제에서 .NET의 자격 증명을 암호화하는 방법을 참조하세요.

아래 EncodeCredentials 메서드에 제공된 자격 증명은 자격 증명 유형에 따라 다음 형식 중 하나여야 합니다.

**Basic / Windows 자격 증명**

```csharp
var credentials = "{\"credentialData\":[{\"name\":\"username\", \"value\":\"john\"},{\"name\":\"password\", \"value\":\"*****\"}]}";
```

**키 자격 증명**

```csharp
var credentials = "{\"credentialData\":[{\"name\":\"key\", \"value\":\"ec....LA=\"}]}";
```

**OAuth2 자격 증명**

```csharp
var credentials = "{\"credentialData\":[{\"name\":\"accessToken\", \"value\":\"eyJ0....fwtQ\"}]}";
```

**익명 자격 증명**

```csharp
var credentials = "{\"credentialData\":\"\"}";
```

**자격 증명 암호화**

게이트웨이의 공개 키를 사용하여 자격 증명 값을 암호화합니다. 게이트웨이 버전에 따라 공개 키 크기가 서로 다를 수 있습니다.

PowerBI-CSharp GitHub 리포지토리([PowerBI-CSharp/sdk/PowerBI.Api/Extensions/V2/](https://github.com/microsoft/PowerBI-CSharp/tree/master/sdk/PowerBI.Api/Extensions/V2))에 있는 SDK 코드의 예제를 참조하세요.

- [AsymmetricKeyEncryptor.cs](https://github.com/microsoft/PowerBI-CSharp/blob/master/sdk/PowerBI.Api/Extensions/V2/AsymmetricKeyEncryptor.cs)
- [Asymmetric1024KeyEncryptionHelper.cs](https://github.com/microsoft/PowerBI-CSharp/blob/master/sdk/PowerBI.Api/Extensions/V2/Asymmetric1024KeyEncryptionHelper.cs)
- [AsymmetricHigherKeyEncryptionHelper.cs](https://github.com/microsoft/PowerBI-CSharp/blob/master/sdk/PowerBI.Api/Extensions/V2/AsymmetricHigherKeyEncryptionHelper.cs)
- [AuthenticatedEncryption.cs](https://github.com/microsoft/PowerBI-CSharp/blob/master/sdk/PowerBI.Api/Extensions/V2/AuthenticatedEncryption.cs)