---
title: Power BI에 대한 사용자 고유의 암호화 키 가져오기(미리 보기)
description: Power BI Premium에서 자신의 암호화 키를 사용하는 방법을 알아봅니다.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 06/18/2019
LocalizationGroup: Premium
ms.openlocfilehash: 39c6dc8a60be67f8f9e99e01ae1c7249166c5ddb
ms.sourcegitcommit: 6a44cb5b0328b60ebe7710378287f1e20bc55a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2019
ms.locfileid: "70877735"
---
# <a name="bring-your-own-encryption-keys-for-power-bi-preview"></a>Power BI에 대한 사용자 고유의 암호화 키 가져오기(미리 보기)

Power BI는 미사용(_at-rest_) 및 처리 중(_in process_)인 데이터를 암호화합니다. 기본적으로 Power BI는 Microsoft 관리형 키를 사용하여 데이터를 암호화합니다. Power BI Premium에서는 데이터 세트로 가져온 미사용 데이터에 대해 자신의 키를 사용할 수도 있습니다. (자세한 내용은 [데이터 원본 및 스토리지 고려 사항](#data-source-and-storage-considerations)을 참조하세요.) 이러한 방식은 BYOK(_bring your own key_)라고 하는 경우가 많습니다.

## <a name="why-use-byok"></a>BYOK를 사용하는 이유?

BYOK를 사용하면 클라우드 서비스 공급자(이 경우 Microsoft)와의 키 정렬을 지정하는 규정 준수 요구 사항을 더 쉽게 충족할 수 있습니다. BYOK를 사용하면 애플리케이션 수준에서 Power BI 미사용 데이터에 대한 암호화 키를 제공하고 제어할 수 있습니다. 결과적으로, 서비스를 종료하기로 결정한 경우, 조직의 키를 제어하고 철회할 수 있습니다. 키를 취소하면 서버스에서 데이터를 읽을 수 없습니다.

## <a name="data-source-and-storage-considerations"></a>데이터 원본 및 스토리지 고려 사항

BYOK를 사용하려면 Power BI Desktop(PBIX) 파일에서 Power BI 서비스에 데이터를 업로드해야 합니다. 다음 시나리오에서는 BYOK를 사용할 수 없습니다.

- Analysis Services 라이브 연결
- Excel 통합 문서(데이터를 Power BI Desktop으로 먼저 가져오는 경우 제외)
- 푸시 데이터 세트

BYOK는 PBIX 파일과 연결된 데이터 세트에만 적용되며 타일 및 시각적 개체에 대한 쿼리 결과 캐시는 적용되지 않습니다.

## <a name="configure-azure-key-vault"></a>Azure Key Vault 구성

이 섹션에서는 암호화 키와 같은 비밀을 안전하게 저장하고 액세스하는 도구인 Azure Key Vault를 구성하는 방법을 알아봅니다. 기존 키 자격 증명 모음을 사용하여 암호화 키를 저장하거나 Power BI에만 사용할 키 자격 증명 모음을 새로 만들 수 있습니다.

이 섹션의 지침에서는 Azure Key Vault에 대한 기본 지식이 있다고 가정합니다. 자세한 내용은 [Azure Key Vault란?](/azure/key-vault/key-vault-whatis)을 참조하세요. 키 자격 증명 모음은 다음과 같은 방식으로 구성합니다.

1. Power BI 서비스를 래핑 및 래핑 해제 권한이 있는 키 자격 증명 모음의 서비스 주체로 추가합니다.

1. 래핑 및 래핑 해제 권한이 있는 4096비트 길이의 RSA 키를 만듭니다(또는 같은 형식의 기존 키를 사용).

    > [!IMPORTANT]
    > Power BI BYOK는 4096비트 길이의 RSA 키만 지원합니다.

1. 권장: 키 자격 증명 모음에 일시 삭제(_soft delete_) 옵션을 사용하도록 설정되어 있는지 확인합니다.

### <a name="add-the-service-principal"></a>서비스 주체 추가

1. Azure Portal 키 자격 증명 모음의 **액세스 정책**에서 **새로 추가**를 선택합니다.

1. **주체 선택**에서 Microsoft.Azure.AnalysisServices를 검색하여 선택합니다.

    > [!NOTE]
    > “Microsoft.Azure.AnalysisServices”를 찾을 수 없는 경우 Azure Key Vault와 연결된 Azure 구독에 Power BI 리소스가 연결되지 않았을 수 있습니다. 대신, 다음 문자열을 검색해 보세요. 00000009-0000-0000-c000-000000000000.

1. **키 권한**에서 **키 래핑 해제**와 **키 래핑**을 선택합니다.

    ![PBIX 파일 구성 요소](media/service-encryption-byok/service-principal.png)

1. **확인**과 **저장**을 차례로 선택합니다.

> [!NOTE]
> Futurem의 데이터에 대한 Power BI 액세스를 취소하려면 Azure Key Vault에서 이 서비스 사용자에 대한 액세스 권한을 제거합니다.

### <a name="create-an-rsa-key"></a>RSA 키 만들기

1. 키 자격 증명 모음의 **키**에서 **생성/가져오기**를 선택합니다.

1. **키 유형**은 RSA를 선택하고 **RSA 키 크기**는 4096을 선택합니다.

    ![PBIX 파일 구성 요소](media/service-encryption-byok/create-rsa-key.png)

1. **만들기**를 선택합니다.

1. **키**에서 직접 만든 키를 선택합니다.

1. 키의 **현재 버전**에 대한 GUID를 선택합니다.

1. **키 래핑**과 **키 래핑 해제**가 둘 다 선택되어 있는지 확인합니다. Power BI에서 BYOK를 사용하도록 설정할 때 사용할 **키 식별자**를 복사합니다.

    ![PBIX 파일 구성 요소](media/service-encryption-byok/key-properties.png)

### <a name="soft-delete-option"></a>일시 삭제 옵션

키(또는 키 자격 증명 모음)가 실수로 삭제되는 경우 데이터가 손실되는 것을 방지하기 위해 키 자격 증명 모음에 [일시 삭제](/azure/key-vault/key-vault-ovw-soft-delete)를 사용하도록 설정하는 것이 좋습니다. 이 옵션은 Azure Portal에서 아직 사용할 수 없기 때문에 [PowerShell을 사용하여 키 자격 증명 모음에서 "일시 삭제" 속성을 사용하도록 설정](/azure/key-vault/key-vault-soft-delete-powershell)해야 합니다.

Azure Key Vault가 제대로 구성되면 테넌트에서 BYOK를 사용하도록 설정할 준비가 완료됩니다.

## <a name="enable-byok-on-your-tenant"></a>테넌트에서 BYOK를 사용하도록 설정

Azure Key Vault에서 만들고 저장한 암호화 키를 Power BI 테넌트에 처음 도입하는 방식으로, [PowerShell](https://www.powershellgallery.com/packages/MicrosoftPowerBIMgmt.Admin)을 사용하여 테넌트 수준에서 BYOK를 사용하도록 설정합니다. 그런 다음, 용량 콘텐츠 암호화를 위한 프리미엄 용량 단위 암호화 키를 할당합니다.

### <a name="important-considerations"></a>중요 고려 사항

BYOK를 사용하도록 설정하기 전에, 다음 사항을 고려해야 합니다.

- 지금은 BYOK를 사용하도록 설정한 후에 BYOK를 사용하지 않도록 설정할 수 없습니다. `Add-PowerBIEncryptionKey`에 대한 매개 변수를 지정하는 방법에 따라, 하나 이상의 용량에 BYOK를 사용하는 방법을 제어할 수 있습니다. 하지만 테넌트에 대한 키 도입을 취소할 수는 없습니다. 자세한 내용은 [BYOK를 사용하도록 설정](#enable-byok)을 참조하세요.

- BYOK를 사용하는 작업 영역을 Power BI Premium의 전용 용량에서 공유 용량으로 직접 이동할 수 없습니다.  먼저 작업 영역을 BYOK가 사용되지 않는 전용 용량으로 이동해야 합니다.

### <a name="enable-byok"></a>BYOK를 사용하도록 설정

BYOK를 사용하려면 `Connect-PowerBIServiceAccount` cmdlet을 사용하여 로그인한 Power BI 서비스의 테넌트 관리자여야 합니다. 그런 다음, [`Add-PowerBIEncryptionKey`](/powershell/module/microsoftpowerbimgmt.admin/Add-PowerBIEncryptionKey)를 사용하여 아래 예제와 같이 BYOK를 사용하도록 설정합니다.

```powershell
Add-PowerBIEncryptionKey -Name'Contoso Sales' -KeyVaultKeyUri'https://contoso-vault2.vault.azure.net/keys/ContosoKeyVault/b2ab4ba1c7b341eea5ecaaa2wb54c4d2'
```

여러 키를 추가하려면 `-Name` 및 `-KeyVaultKeyUri`에 대해 다른 값으로 `Add-PowerBIEncryptionKey`를 실행합니다. 

cmdlet은 현재 및 미래 용량에 대한 암호화에 영향을 미치는 두 가지 스위치 매개 변수를 허용합니다. 기본적으로 스위치는 모두 설정되지 않습니다.

- `-Activate`: 이 키가 아직 암호화되지 않은 테넌트의 모든 기존 용량에 사용됨을 나타냅니다.

- `-Default`: 키가 현재 전체 테넌트의 기본값이라는 것을 나타냅니다. 새 용량을 만드는 경우 용량이 이 키를 상속합니다.

> [!IMPORTANT]
> `-Default`를 지정하면 이 지점부터 테넌트에 생성된 모든 용량이 지정한 키(또는 업데이트된 기본 키)를 사용하여 암호화됩니다. 기본 작업의 실행을 취소할 수 없기 때문에 BYOK를 사용하지 않는 테넌트에 프리미엄 용량을 생성할 수 없게 됩니다.

테넌트에서 BYOK를 사용하도록 설정한 후 하나 이상의 Power BI 용량에 대한 암호화 키를 설정합니다.

1. [`Get-PowerBICapacity`](/powershell/module/microsoftpowerbimgmt.capacities/get-powerbicapacity)를 사용하여 다음 단계에 필요한 용량 ID를 가져옵니다.

    ```powershell
    Get-PowerBICapacity -Scope Individual
    ```

    이 cmdlet은 다음 출력과 유사한 출력을 반환합니다.

    ```
    Id              : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
    DisplayName     : Test Capacity
    Admins          : adam@sometestdomain.com
    Sku             : P1
    State           : Active
    UserAccessRight : Admin
    Region          : North Central US
    ```

1. [`Set-PowerBICapacityEncryptionKey`](/powershell/module/microsoftpowerbimgmt.admin/set-powerbicapacityencryptionkey)를 사용하여 암호화 키를 설정합니다.

    ```powershell
    Set-PowerBICapacityEncryptionKey-CapacityId xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx -KeyName 'Contoso Sales'
    ```

테넌트 전체에서 BYOK를 사용하는 방법을 제어할 수 있습니다. 예를 들어, 단일 용량을 암호화하려면 `-Activate` 또는 `-Default` 없이 `Add-PowerBIEncryptionKey`를 호출합니다. 그런 다음, BYOK를 사용하도록 설정하려는 용량에 대해 `Set-PowerBICapacityEncryptionKey`를 호출합니다.

## <a name="manage-byok"></a>BYOK 관리

Power BI는 테넌트에서 BYOK를 관리할 수 있는 추가 cmdlet을 제공합니다.

- [`Get-PowerBICapacity`](/powershell/module/microsoftpowerbimgmt.capacities/get-powerbicapacity)를 사용하면 용량이 현재 사용 중인 키를 가져올 수 있습니다.

    ```powershell
    Get-PowerBICapacity -Scope Organization -ShowEncryptionKey
    ```

- [`Get-PowerBIEncryptionKey`](/powershell/module/microsoftpowerbimgmt.admin/get-powerbiencryptionkey)를 사용하면 테넌트가 현재 사용 중인 키를 가져올 수 있습니다.

    ```powershell
    Get-PowerBIEncryptionKey
    ```

- [`Get-PowerBIWorkspaceEncryptionStatus`](/powershell/module/microsoftpowerbimgmt.admin/get-powerbiworkspaceencryptionstatus)를 사용하면 작업 영역의 데이터 세트가 암호화되어 있는지 여부와 암호화 상태가 작업 영역과 동기화되어 있는지 여부를 볼 수 있습니다.

    ```powershell
    Get-PowerBIWorkspaceEncryptionStatus -Name'Contoso Sales'
    ```

    암호화는 용량 수준에서 사용하도록 설정되지만 암호화 상태는 지정된 작업 영역에 대한 데이터 세트 수준에서 가져옵니다.

- 암화화에 사용되는 키 버전을 전환(또는 _회전_)하려면 [`Switch-PowerBIEncryptionKey`](/powershell/module/microsoftpowerbimgmt.admin/switch-powerbiencryptionkey)를 사용합니다. cmdlet은 단지 키 `-Name`에 대한 `-KeyVaultKeyUri`를 업데이트합니다.

    ```powershell
    Switch-PowerBIEncryptionKey -Name'Contoso Sales' -KeyVaultKeyUri'https://contoso-vault2.vault.azure.net/keys/ContosoKeyVault/b2ab4ba1c7b341eea5ecaaa2wb54c4d2'
    ```
