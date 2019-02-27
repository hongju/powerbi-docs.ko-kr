---
title: 관리자가 Power BI Desktop 로그인 양식을 관리하는 방법
description: Power BI Desktop을 열 때 초기 로그인 양식을 관리하는 방법을 알아봅니다.
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 02/21/2019
ms.author: davidi
ms.openlocfilehash: 9e35bbffec40aa57d3097e122bd038659405dfed
ms.sourcegitcommit: 76772a361e6cd4dd88824b2e4b32af30656e69db
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/27/2019
ms.locfileid: "56892301"
---
# <a name="how-administrators-can-manage-the-power-bi-desktop-sign-in-form"></a>관리자가 Power BI Desktop 로그인 양식을 관리하는 방법
Power BI Desktop이 처음 시작되면 로그인 양식이 표시됩니다. 계속하려면 정보를 입력하거나 Power BI에 로그인합니다. 관리자는 레지스트리 키를 사용하여 이 양식을 관리합니다. 

![Power BI Desktop의 초기 로그인 양식](media/desktop-admin-sign-in-form/sign-in-form.png)

관리자는 다음 레지스트리 키를 사용하여 로그인 양식을 사용하지 않도록 설정합니다. 글로벌 정책을 사용하여 전체 조직에 푸시할 수도 있습니다.

```
Key: HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Microsoft Power BI Desktop
valueName: ShowLeadGenDialog
```

값 0은 대화 상자를 사용하지 않도록 설정합니다.

궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](http://community.powerbi.com/)

