---
title: 관리자가 Power BI Desktop 로그인 양식을 관리하는 방법
description: Power BI Desktop을 열 때 초기 로그인 양식을 관리하는 방법을 알아봅니다.
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/15/2019
ms.author: davidi
ms.openlocfilehash: 5c31277b640b16882bef5c5f2cd9c56b441ede82
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "61329899"
---
# <a name="how-administrators-can-manage-the-power-bi-desktop-sign-in-form"></a>관리자가 Power BI Desktop 로그인 양식을 관리하는 방법
Power BI Desktop이 처음 시작되면 로그인 양식이 표시됩니다. 계속하려면 정보를 입력하거나 Power BI에 로그인합니다. 관리자는 레지스트리 키를 사용하여 이 양식을 관리합니다. 

![Power BI Desktop의 초기 로그인 양식](media/desktop-admin-sign-in-form/sign-in-form.png)

관리자는 다음 레지스트리 키를 사용하여 로그인 양식을 사용하지 않도록 설정합니다. 글로벌 정책을 사용하여 전체 조직에 푸시할 수도 있습니다.

```
Key: HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Microsoft Power BI Desktop
valueName: ShowLeadGenDialog
```
또한 일부 고객의 해당 구성에 따라 성공적으로 실행 되었는지 하는 다음 키를 시도할 수 있습니다.

```
Key: HKEY_CURRENT_USER\SOFTWARE\Microsoft\Microsoft Power BI Desktop
valueName: ShowLeadGenDialog
```

값 0은 대화 상자를 사용하지 않도록 설정합니다.




궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](http://community.powerbi.com/)

