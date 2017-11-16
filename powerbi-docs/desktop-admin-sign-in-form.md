---
title: "관리자가 Power BI Desktop 로그인 양식을 관리하는 방법"
description: "Power BI Desktop을 열 때 초기 로그인 양식을 관리하는 방법을 알아봅니다."
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/17/2017
ms.author: davidi
ms.openlocfilehash: eabb59b32234fce1ba5669b95abb41c4f7e04aa2
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2017
---
# <a name="how-administrators-can-manage-the-power-bi-desktop-sign-in-form"></a>관리자가 Power BI Desktop 로그인 양식을 관리하는 방법
Power BI Desktop이 처음 시작되면 로그인 양식이 표시됩니다. 계속하려면 정보를 입력하거나 Power BI에 로그인하십시오. 관리자는 레지스트리 키를 사용하여 이 양식을 관리 할 수 있습니다. 

![Power BI Desktop의 초기 로그인 양식](media/desktop-admin-sign-in-form/sign-in-form.png)

관리자는 다음 레지스트리 키를 사용하여 로그인 양식을 사용하지 않도록 설정할 수 있습니다. 글로벌 정책을 사용하여 전체 조직에 밀어넣을 수도 있습니다.

```
Key: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Power BI Desktop
valueName: ShowLeadGenDialog
```

값 0은 대화 상자를 사용하지 않도록 설정합니다.

궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](http://community.powerbi.com/)

