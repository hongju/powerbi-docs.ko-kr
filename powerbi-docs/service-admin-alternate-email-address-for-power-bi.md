---
title: "대체 메일 주소 사용"
description: "대체 메일 주소 사용"
services: powerbi
documentationcenter: 
author: markingmyname
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
ms.date: 08/09/2017
ms.author: maghan
ms.openlocfilehash: dd9e146b22c95d8c915ea653ee287bb7a51e6b06
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/30/2018
---
# <a name="using-an-alternate-email-address"></a>대체 메일 주소 사용
기본적으로 Power BI 등록에 사용한 메일 주소를 Power BI 활동에 대한 업데이트를 보내는 데 사용합니다.  예를 들어, 누군가 공유 초대를 보내면 이 주소로 전달됩니다.

때때로 원래 Power BI 등록에 사용한 이메일 주소가 아닌 대체 메일 주소로 이 이메일을 전달하고자 할 수 있습니다.

## <a name="updating-through-office-365-personal-info-page"></a>Office 365 개인 정보 페이지를 통해 업데이트
1. [Office 365 개인 정보 페이지](https://portal.office.com/account/#personalinfo)로 이동합니다.  메시지가 표시되면 Power BI 등록에 사용한 메일 주소와 암호를 입력하여 로그인합니다.
2. 연락처 세부 정보 섹션에서 편집 링크를 클릭합니다.  
   
   > [!NOTE]
   > 편집 링크가 표시되지 않으면 해당 메일 주소를 Office 365 관리자가 관리하는 것이며 메일 주소를 업데이트하려면 해당 관리자에게 문의해야 합니다.
   > 
   > 
   
   ![](media/service-admin-alternate-email-address-for-power-bi/contact-details.png)
3. 대체 메일 필드에서 Power BI 업데이트를 보낼 메일 주소를 입력합니다.

> [!NOTE]
> 이 설정의 변경은 서비스 업데이트, 뉴스레터 및 기타 프로모션 정보를 보내는 데 사용하는 메일 주소에는 영향이 없습니다.  해당 항목은 항상 원래 Power BI 등록에 사용한 메일 주소로 전달됩니다.
> 
> 

## <a name="updating-with-powershell"></a>PowerShell을 사용한 업데이트
또는 Azure Active Directory용 PowerShell을 통해 대체 전자 메일 주소를 업데이트할 수 있습니다. [Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser) 명령을 사용하여 수행할 수 있습니다.

```
Set-AzureADUser -ObjectId john@contoso.com -OtherMails "otheremail@somedomain.com"
```

자세한 내용은 [Azure Active Directory PowerShell 버전 2](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2)를 참조하세요.

궁금한 점이 더 있나요? [Power BI 커뮤니티를 이용하세요.](http://community.powerbi.com/)

