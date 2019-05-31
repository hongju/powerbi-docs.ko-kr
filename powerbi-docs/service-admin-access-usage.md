---
title: 로그인한 Power BI 사용자 찾기
description: 테 넌 트 관리자는 Power BI에 로그인 하는 확인 하려면 하는 경우 한 가시성을 얻고 Azure Active Directory 액세스 및 사용 보고서를 사용할 수 있습니다.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 04/23/2019
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: e513607dd89aee15f10145cf62bd461621cc12c0
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "64906742"
---
# <a name="find-power-bi-users-that-have-signed-in"></a>로그인한 Power BI 사용자 찾기

테 넌 트 관리자를 사용 하 여 Power BI에 로그인 하는 보려는 경우 합니다 [Azure Active Directory 액세스 및 사용 보고서](/azure/active-directory/reports-monitoring/concept-sign-ins) 가시성을 얻고 있습니다.

<iframe width="640" height="360" src="https://www.youtube.com/embed/1AVgh9w9VM8?showinfo=0" frameborder="0" allowfullscreen></iframe>

> [!NOTE]
> 합니다 **로그인** 보고서는 유용한 정보를 제공 하지만 형식의 각 사용자에 게 라이선스를 식별 하지 않습니다. 라이선스를 보려면 Microsoft 365 관리 센터를 사용합니다.

## <a name="requirements"></a>요구 사항

모든 사용자(비관리자 포함)는 자신의 로그인에 대한 보고서를 볼 수 있지만, 모든 사용자에 대한 보고서를 보려면 다음 요구 사항을 충족해야 합니다.

* 테 넌 트에 연결 된 Azure Active Directory Premium 라이선스가 있어야 합니다.

* 다음 역할 중 하나여야 합니다. 전역 관리자, 보안 관리자 또는 보안 읽기 권한자.

## <a name="use-the-azure-portal-to-view-sign-ins"></a>Azure Portal을 사용하여 로그인 보기

로그인 활동을 보려면 다음 단계를 수행합니다.

1. **Azure Portal**에서 **Azure Active Directory**를 선택합니다.

1. **모니터링**에서 **로그인**을 선택합니다.
   
    ![강조 표시 된 Azure Active Directory 및 로그인 옵션을 사용 하 여 Azure UI의 스크린샷.](media/service-admin-access-usage/azure-portal-sign-ins.png)

1. **Microsoft Power BI** 또는 **Power BI Gateway** 중 하나로 애플리케이션을 필터링하고 **적용**을 선택합니다.

    **Microsoft Power BI** 반면 로그인 활동에 대 한 필터는 서비스와 관련 **Power BI Gateway** 로그인 활동에 특정 한 온-프레미스 데이터 게이트웨이 필터입니다.
   
    ![강조 표시 하는 응용 프로그램 필드를 사용 하 여 로그인 필터 스크린샷.](media/service-admin-access-usage/sign-in-filter.png)

## <a name="export-the-data"></a>데이터 내보내기

할 수 있습니다 [로그인 보고서 다운로드](/azure/active-directory/reports-monitoring/quickstart-download-sign-in-report) 두 형식 중 하나로: CSV 파일 또는 JSON 파일입니다.

![다운로드 단추 스크린샷입니다.](media/service-admin-access-usage/download-sign-in-data-csv.png)

맨 위에 있는 **로그인** 보고서를 선택 **다운로드** 다음 옵션 중 하나를 선택 합니다.

* **CSV** 현재 필터링된 된 데이터에 대 한 CSV 파일을 다운로드 합니다.

* **JSON** 현재 필터링된 된 데이터에 대 한 JSON 파일을 다운로드 합니다.

## <a name="data-retention"></a>데이터 보존

로그인 관련 데이터는 최대 30일 동안 사용할 수 있습니다. 자세한 내용은 참조 하세요. [Azure Active Directory 보고서 보존 정책](/azure/active-directory/reports-monitoring/reference-reports-data-retention)합니다.

## <a name="next-steps"></a>다음 단계

[조직 내에서 감사 사용](service-admin-auditing.md)

궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](https://community.powerbi.com/)