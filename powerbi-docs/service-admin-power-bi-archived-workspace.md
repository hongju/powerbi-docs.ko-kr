---
title: Power BI 보관 작업 영역
description: Office 365 테넌트를 관리한 후 Power BI 보관 작업 영역
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 06/28/2017
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 8b9fcf1c6121c4aeecfdf948b77493f1f2a7f825
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34293631"
---
# <a name="power-bi-archived-workspace"></a>Power BI 보관 작업 영역
Power BI를 사용하면 누구나 몇 분 안에 서비스에 가입하고 사용을 시작할 수 있습니다.  나중에 조직의 IT 부서가 조직 내 사용자를 위해 Power BI 관리 인계를 선택할 수 있습니다.  이러한 인계가 발생하면 조직 내 사용자 및 권한의 중앙 관리를 통해 혜택을 누릴 수 있고, 조직 내 타 서비스에 사용하는 것과 동일한 사용자 이름과 암호를 사용함으로써 능률적인 가입 절차를 활용할 수 있습니다. 

IT 부서가 Power BI 관리를 시작하기 전에 사용자가 만든 모든 콘텐츠는 Power BI 보관 작업 영역에 배치되며 [Power BI](https://app.powerbi.com)의 왼쪽 탐색을 통해 액세스할 수 있습니다.  조직의 IT 부서에서 보호 및 관리하는 내 작업 영역에서 새 Power BI 콘텐츠를 만들기 시작해야 합니다.    보관 작업 영역은 그대로 존재하지만 보관 작업 영역의 콘텐츠에 대해 수행할 수 있는 작업에는 제한이 있습니다.  이러한 제한 사항을 제거하려면 보관 작업 영역의 콘텐츠를 IT 부서에서 관리하는 내 작업 영역으로 마이그레이션해야 합니다.

## <a name="restrictions-in-your-archived-workspace"></a>보관 작업 영역의 제한 사항
보관 작업 영역에서는 콘텐츠가 삭제되지 않습니다.  계속해서 데이터를 가져오고 보고서와 대시보드를 만들며 데이터 집합을 새로 고칠 수 있습니다.  콘텐츠를 공유하는 기존 사용자도 보관 작업 영역의 콘텐츠를 볼 수 있습니다.

그러나 보관 작업 영역의 콘텐츠에는 몇 가지 제한 사항이 있습니다.

* **비즈니스용 OneDrive.**  더 이상 비즈니스용 OneDrive에서 보관 작업 영역의 데이터 집합에 대해 데이터를 가져오거나 새로 고칠 수 없습니다.  이 원본에 연결을 시도하면 경고가 표시됩니다.
* **대시보드 공유.**  보관 작업 영역에서 대시보드를 다른 사용자와 공유할 수 없습니다.  이미 액세스 권한을 갖고 있는 모든 사용자는 보관 작업 영역 액세스를 통해 공유 대시보드를 볼 수 있습니다.
* **그룹 만들기.**  보관 작업 영역에서 그룹을 만들 수 없습니다.
* **Power BI 모바일 앱에서의 액세스.**  보관 작업 영역에서 웹의 콘텐츠를 볼 수는 있지만 이 콘텐츠가 Power BI 모바일 앱에 더 이상 표시되지 않습니다.

## <a name="migrating-content-in-your-archived-workspace"></a>보관 작업 영역의 콘텐츠 마이그레이션
Power BI를 계속 사용하려면 IT 부서가 관리하는 내 작업 영역에서 새 콘텐츠를 만들어야 합니다.   또한 보관 작업 영역의 모든 콘텐츠를 내 작업 영역으로 마이그레이션할 계획이 필요합니다.  콘텐츠 마이그레이션 방법은 콘텐츠 내용에 따라 다릅니다.

* **Excel 또는 Power BI Desktop 데이터 집합.**  보관 작업 영역에서 내 작업 영역으로 전환하고 "내 데이터" 버튼을 클릭하여 Excel 또는 Power BI Desktop 파일을 다시 업로드함으로써 데이터 집합을 마이그레이션합니다.  예약된 새로 고침을 설정한 경우 내 작업 영역에서 새 데이터 집합에 대한 설정을 재구성해야 합니다.
* **다른 데이터 집합.**  내 작업 영역으로 전환한 다음 데이터 가져오기 단추를 클릭하여 보관 작업 영역에서 만든 다른 데이터 집합에 다시 연결합니다.  보안 또는 연결 정보를 다시 입력해야 할 수 있습니다.
* **보고서.**  Excel 또는 Power BI Desktop에 포함되었던 보고서나 콘텐츠 팩의 일부로 설치된 보고서는, 사용자가 해당 Excel 또는 Power BI Desktop 파일을 다시 업로드하거나 콘텐츠 팩에 다시 연결한 후 자동으로 다시 생성됩니다.  Power BI 서비스를 통해 자체 보고서를 만든 경우 내 작업 영역에서 해당 보고서를 다시 만들어야 합니다.
* **대시보드.**  콘텐츠 팩의 일부로 설치된 대시보드는 내 작업 영역에서 콘텐츠 팩에 다시 연결할 때 자동으로 재생성됩니다.  Power BI 서비스를 통해 자체 대시보드를 만든 경우 내 작업 영역에서 해당 대시보드를 다시 만들어야 합니다.

궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](http://community.powerbi.com/)

