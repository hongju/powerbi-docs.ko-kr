---
title: 포함 파일
description: 포함 파일
services: powerbi
author: mgblythe
ms.service: powerbi
ms.topic: include
ms.date: 05/31/2019
ms.author: mblythe
ms.openlocfilehash: 94b6959b6bcbf250e54a353e8b725b6c9e5a2e30
ms.sourcegitcommit: c539726c9c180e899a8a34443e3fda2b9848beb2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/31/2019
ms.locfileid: "66448374"
---
## <a name="single-sign-on"></a>Single Sign-On

서비스에 Azure SQL DirectQuery 데이터 세트를 게시한 후 Azure AD(Azure Active Directory) OAuth2를 통해 최종 사용자의 SSO(Single Sign-On)를 활성화할 수 있습니다.

SSO를 활성화하려면 데이터 세트에 대한 설정으로 이동하여 **데이터 원본** 탭을 열고 SSO 확인란을 선택합니다.

![Azure SQL DQ 대화 상자 구성](media/direct-query-sso/sso-dialog.png)

SSO 옵션이 활성화되어 있고 사용자가 데이터 원본을 기반으로 빌드된 보고서에 액세스하면 Power BI가 Azure SQL 데이터베이스 또는 데이터 웨어하우스 쿼리에 인증된 Azure AD 자격 증명을 보냅니다. 그러면 Power BI가 데이터 원본 수준에서 구성된 보안 설정을 준수할 수 있습니다.

SSO 옵션은 이 데이터 원본을 사용하는 모든 데이터 세트에 적용됩니다. 가져오기 시나리오에 사용되는 인증 방법에는 영향을 주지 않습니다.

> [!Note]
> Azure MFA(Multi-Factor Authentication)는 지원되지 않습니다. Azure SQL DirectQuery와 함께 SSO를 사용하려는 사용자는 MFA에서 제외해야 합니다.