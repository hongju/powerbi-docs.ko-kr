---
title: 대체 메일 주소 사용
description: 대체 메일 주소 사용
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 03/08/2018
ms.author: mblythe
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 5013c70e4d3998eb39e0de2a92f890417175fd62
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34240909"
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

## <a name="updating-through-azure-active-directory"></a>Azure Active Directory를 통해 업데이트
Power BI용 AAD(Active Azure Directory) 임베드 토큰을 캡처할 때 세 가지 형식의 이메일을 사용할 수 있습니다. 세 가지 형식은 다음과 같습니다.

* 사용자의 AAD 계정에 연결된 주 이메일 주소
* UPN(UserPrincipalName) 이메일 주소
* "기타" 이메일 주소 배열 특성

Power BI는 다음과 같은 조건에 따라 사용할 이메일을 선택합니다.
1.  AAD 테넌트의 사용자 개체에 메일 특성이 있는 경우, Power BI는 이메일 주소에 해당 메일 특성을 사용합니다.
2.  UPN 이메일이 **\*.onmicrosoft.com** 도메인 이메일 주소("\@" 기호 다음의 정보)가 *아닌* 경우, Power BI는 이메일 주소에 해당 메일 특성을 사용합니다.
3.  AAD 사용자 개체에 "기타" 이메일 배열 특성이 있는 경우, 이 목록에 있는 첫 번째 이메일(이 특성에 이메일 목록이 있을 수 있기 때문에)이 사용됩니다.
4. 위의 조건 중 해당 사항이 없을 경우 UPN 주소가 사용됩니다.

## <a name="updating-with-powershell"></a>PowerShell을 사용한 업데이트
또는 Azure Active Directory용 PowerShell을 통해 대체 전자 메일 주소를 업데이트할 수 있습니다. [Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser) 명령을 사용하여 수행할 수 있습니다.

```
Set-AzureADUser -ObjectId john@contoso.com -OtherMails "otheremail@somedomain.com"
```

자세한 내용은 [Azure Active Directory PowerShell 버전 2](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2)를 참조하세요.

궁금한 점이 더 있나요? [Power BI 커뮤니티를 이용하세요.](http://community.powerbi.com/)

