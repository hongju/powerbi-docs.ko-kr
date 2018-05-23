---
title: Power BI Desktop을 사용하는 행 수준 보안(RLS) 이해
description: Power BI Desktop 내에서 가져온 데이터 집합 및 DirectQuery에 대한 행 수준 보안을 구성하는 방법입니다.
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 05/03/2018
ms.author: maghan
LocalizationGroup: Create reports
ms.openlocfilehash: 022668737f6bcce987b2923ba7a4416f4a08460a
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/17/2018
---
# <a name="row-level-security-rls-with-power-bi-desktop"></a>Power BI Desktop을 사용하는 행 수준 보안(RLS)
Power BI Desktop을 사용하는 행 수준 보안(RLS)은 지정된 사용자의 데이터 액세스를 제한합니다. 행 수준에서 데이터 제한을 필터링합니다. 역할 내에서 필터를 정의할 수 있습니다.

이제 Power BI Desktop으로 Power BI로 가져온 데이터 모델에 대한 RLS를 구성할 수 있습니다. SQL Server와 같은 DirectQuery를 사용하는 데이터 집합에서 RLS를 구성할 수도 있습니다. 이전에는 Power BI 외부의 온-프레미스 Analysis Services 모델 내에서 RLS를 구현할 수만 있었습니다. Analysis Services 라이브 연결의 경우 온-프레미스 모델에서 행 수준 보안을 구성합니다. 라이브 연결 데이터 집합에는 보안 옵션이 표시되지 않습니다.

> [!IMPORTANT]
> Power BI 서비스 내에서 역할 및 규칙을 정의한 경우 Power BI Desktop 내에서 해당 역할을 다시 만든 다음, 보고서를 서비스에 게시해야 합니다.
> 
> 

[Power BI 서비스 내에서 RLS](service-admin-rls.md)에 대해 자세히 알아보세요.

[!INCLUDE [include-short-name](./includes/rls-desktop-define-roles.md)]

[!INCLUDE [include-short-name](./includes/rls-desktop-view-as-roles.md)]

[!INCLUDE [include-short-name](./includes/rls-limitations.md)]

[!INCLUDE [include-short-name](./includes/rls-faq.md)]

## <a name="next-steps"></a>다음 단계
[Power BI 서비스를 사용하는 행 수준 보안(RLS)](service-admin-rls.md)  

궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](http://community.powerbi.com/)

