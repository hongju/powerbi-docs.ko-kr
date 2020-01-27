---
ms.openlocfilehash: 3e89344ef1298864b485f465b28c56397a7e1511
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "61194092"
---
## <a name="using-the-username-or-userprincipalname-dax-function"></a>username() 또는 userprincipalname() DAX 함수 사용
데이터 세트 내에서 DAX 함수 *username()* 또는 *userprincipalname()* 을 사용할 수 있습니다. Power BI Desktop의 식 내에서 사용할 수 있습니다. 모델을 게시하면 Power BI 서비스 내에서 사용됩니다.

Power BI Desktop 내에서 *username()* 은 사용자를 *DOMAIN\User* 형식으로 반환하며, *userprincipalname()* 은 사용자를 <em>user@contoso.com</em> 형식으로 반환합니다.

Power BI 서비스 내에서 *username()* 및 *userprincipalname()* 은 모두 사용자의 UPN(사용자 계정 이름)을 반환합니다. 형태는 전자 메일 주소와 유사합니다.

