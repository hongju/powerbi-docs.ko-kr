---
title: Power BI Report Server에서 항상 암호화
description: 이 문서에서는 Microsoft SQL Server 및 Microsoft Azure SQL Database와 같은 데이터 원본 유형을 사용할 때 Power BI Report Server에서 제공하는 Always Encrypted 지원에 대해 설명합니다.
author: maggiesMSFT
ms.reviewer: cfinlan
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 01/22/2020
ms.author: maggies
ms.openlocfilehash: f8d711bba8dc7570f2d470554fd1d971639bbb7b
ms.sourcegitcommit: a1409030a1616027b138128695b80f6843258168
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76710209"
---
# <a name="always-encrypted-in-power-bi-report-server"></a>Power BI Report Server에서 항상 암호화

이 문서에서는 Microsoft SQL Server 및 Microsoft Azure SQL Database와 같은 데이터 원본 유형을 사용할 때 Power BI Report Server에서 제공하는 Always Encrypted 지원에 대해 설명합니다. SQL Server의 Always Encrypted 기능에 대한 자세한 내용은 [Always Encrypted](https://docs.microsoft.com/sql/relational-databases/security/encryption/always-encrypted-database-engine) 문서를 참조하세요.

## <a name="always-encrypted-user-isolation"></a>Always Encrypted 사용자 격리

현재 Power BI Report Server는 사용자가 보고서에 액세스할 수 있는 경우 보고서의 Always Encrypted 열에 대한 액세스를 제한하지 않습니다.  따라서 서버에 열 마스터 키를 통해 열 암호화 키에 대한 액세스 권한이 부여된 경우, 사용자는 액세스할 수 있는 보고서의 모든 열에 액세스할 수 있습니다.

## <a name="always-encrypted-column-usage"></a>Always Encrypted 열 사용

### <a name="key-storage-strategies"></a>키 스토리지 전략

|스토리지  |지원됨  |
|---------|---------|
|Windows 인증서 저장소 | 예 |
|Azure Key Vault | 아니요 |
| CNG(cryptography Next Generation) | 아니요 |

### <a name="certificate-storage-and-access"></a>인증서 스토리지 및 액세스

인증서에 액세스해야 하는 계정은 서비스 계정입니다. 인증서는 로컬 컴퓨터 인증서 저장소에 저장해야 합니다. 자세한 내용은 다음을 참조하세요.

- [보고서 서버 서비스 계정 구성](https://docs.microsoft.com/sql/reporting-services/install-windows/configure-the-report-server-service-account-ssrs-configuration-manager)(구성 관리자)
- SQL Server 문서 “Always Encrypted용 열 마스터 키 생성 및 저장”의 [애플리케이션 및 사용자가 인증서를 사용할 수 있도록 설정](https://docs.microsoft.com/sql/relational-databases/security/encryption/create-and-store-column-master-keys-always-encrypted#making-certificates-available-to-applications-and-users) 섹션입니다.

### <a name="column-encryption-strategy"></a>열 암호화 전략

Power BI Report Server에서 열 암호화 전략은 *결정적*이거나 *임의*일 수 있습니다. 다음 테이블에서는 사용하는 전략에 따른 차이점을 비교합니다.

|사용  |결정적  |임의  |
|---------|---------|---------|
|쿼리 결과에서 있는 그대로 읽을 수 있습니다(예: SELECT 문). | 예  | 예  |
|쿼리 내에서 Group By 엔터티로 사용할 수 있습니다. | 예 | 아니요 |
|COUNT와 DISTINCT를 제외하고 집계 필드로 사용할 수 있습니다. | COUNT와 DISTINCT를 제외하고 아닙니다. | 아니요 |
|보고서 매개 변수로 사용할 수 있습니다. | 예 | 아니요 |

[결정적 및 임의 암호화](https://docs.microsoft.com/sql/relational-databases/security/encryption/always-encrypted-database-engine#selecting--deterministic-or-randomized-encryption)에 대해 자세히 알아보세요.

### <a name="parameter-usage"></a>매개 변수 사용

매개 변수 사용은 결정적 암호화에만 적용됩니다.

**단일 값 매개 변수**입니다.  Always Encrypted 열에 대해 단일 값 매개 변수를 사용할 수 있습니다.

**다중 값 매개 변수**입니다. Always Encrypted 열에 대해 둘 이상의 값이 있는 다중 값 매개 변수를 사용할 수 없습니다.

**연계 매개 변수** 다음 *모두*가 참이라면 Always Encrypted와 함께 연계 매개 변수를 사용할 수 있습니다.

- 모든 Always Encrypted 열은 결정적 전략을 사용하여 항상 암호화되어야 합니다.
- Always Encrypted 열에 사용되는 모든 매개 변수는 단일 값 매개 변수입니다.
- 모든 SQL 비교는 Equals(=) 연산자를 사용합니다.

## <a name="datatype-support"></a>데이터 형식 지원

| SQL 데이터 형식 | 읽기 필드 지원 | Group By 요소로 사용 지원 | 지원되는 집계(COUNT, DISTINCT, MAX, MIN, SUM 등) | 매개 변수를 사용하여 같음 필터링 지원 | 참고 |
| --- | --- | --- | --- | --- | --- |
| int | 예 | 예 | COUNT, DISTINCT | 예, 정수로 |   |
| float | 예 | 예 | COUNT, DISTINCT | 예, 부동으로 |   |
| nvarchar | 예 | 예 | COUNT, DISTINCT | 예, 텍스트로 | 결정적 암호화에서는 문자 열에 대해 binary2 정렬 순서를 적용하는 열 데이터 정렬을 사용해야 합니다. 자세한 내용은 SQL Server의 [Always Encrypted](https://docs.microsoft.com/sql/relational-databases/security/encryption/always-encrypted-database-engine#selecting--deterministic-or-randomized-encryption) 문서를 참조하세요.  |
| varchar | 예 | 예 | COUNT, DISTINCT | 아니요 |   |
| decimal | 예 | 예 | COUNT, DISTINCT | 아니요 |   |
| numeric | 예 | 예 | COUNT, DISTINCT | 아니요 |   |
| datetime | 예 | 예 | COUNT, DISTINCT | 아니요 |   |
| datetime2 | 예 | 예 | COUNT, DISTINCT | 예, 날짜/시간으로 | 열에 밀리초 정밀도가 없는 경우(즉, datetime2 (0)) 지원됩니다. |

## <a name="aggregation-alternatives"></a>집계 대안

현재 결정론적 Always Encrypted 열에 대해 현재 지원되는 유일한 집계는 등호(=) 연산자를 직접 사용하는 집계입니다. 이 SQL Server 제한은 Always Encrypted 열의 특성 때문입니다. 사용자는 데이터베이스 대신 보고서 내에서 집계해야 합니다.

## <a name="always-encrypted-in-connection-strings"></a>연결 문자열에서 항상 암호화

SQL Server 데이터 원본에 대한 연결 문자열에서 Always Encrypted를 사용하도록 설정해야 합니다. [애플리케이션 쿼리에서 Always Encrypted를 사용하도록 설정](https://docs.microsoft.com/sql/relational-databases/security/encryption/develop-using-always-encrypted-with-net-framework-data-provider#enabling-always-encrypted-for-application-queries)하는 방법에 대해 자세히 알아보세요.

## <a name="next-steps"></a>다음 단계

SQL Server 및 Azure SQL Database의 [Always Encrypted](https://docs.microsoft.com/sql/relational-databases/security/encryption/always-encrypted-database-engine)

궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](https://community.powerbi.com/)

