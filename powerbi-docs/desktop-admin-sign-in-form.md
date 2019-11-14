---
title: 관리자가 Power BI Desktop 로그인 양식을 관리하는 방법
description: Power BI Desktop을 열 때 초기 로그인 양식을 관리하는 방법을 알아봅니다.
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/15/2019
ms.author: davidi
ms.openlocfilehash: b1ab5188ba8f5ccf54589d359f6f8ced1ada3060
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2019
ms.locfileid: "73878853"
---
# <a name="how-administrators-can-manage-the-power-bi-desktop-sign-in-form"></a>관리자가 Power BI Desktop 로그인 양식을 관리하는 방법
Power BI Desktop이 처음 시작되면 로그인 양식이 표시됩니다. 계속하려면 정보를 입력하거나 Power BI에 로그인합니다. 관리자는 레지스트리 키를 사용하여 이 양식을 관리합니다. 

![Power BI Desktop의 초기 로그인 양식](media/desktop-admin-sign-in-form/sign-in-form.png)

관리자는 다음 레지스트리 키를 사용하여 로그인 양식을 사용하지 않도록 설정합니다. 글로벌 정책을 사용하여 전체 조직에 푸시할 수도 있습니다.

```
Key: HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Microsoft Power BI Desktop
valueName: ShowLeadGenDialog
```
구성에 따라 일부 고객에게 성공한 다음 키를 사용해 볼 수도 있습니다.

```
Key: HKEY_CURRENT_USER\SOFTWARE\Microsoft\Microsoft Power BI Desktop
valueName: ShowLeadGenDialog
```

값 0은 대화 상자를 사용하지 않도록 설정합니다.




궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](https://community.powerbi.com/)

