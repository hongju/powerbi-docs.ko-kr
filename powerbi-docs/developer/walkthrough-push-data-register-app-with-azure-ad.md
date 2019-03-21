---
title: Azure AD에 앱 등록
description: 연습 - 데이터 세트에 데이터 푸시 - Azure AD에 앱 등록
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: madia
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 02/05/2019
ms.openlocfilehash: a3154a7b74d196f3c0aa2969e7c25bf56000a662
ms.sourcegitcommit: 0abcbc7898463adfa6e50b348747256c4b94e360
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2019
ms.locfileid: "55762033"
---
# <a name="step-1-register-an-app-with-azure-ad"></a>1단계: Azure AD에 앱 등록

이 문서는 [데이터 세트에 데이터를 푸시](walkthrough-push-data.md)하는 단계별 연습의 일부입니다.

Power BI 데이터 세트에 데이터를 푸시하는 첫 번째 단계는 Azure AD에 앱을 등록하는 것입니다. 먼저 이렇게 해야만 Azure AD에서 앱을 식별하는 **응용 프로그램 ID** 를 얻을 수 있습니다. **응용 프로그램 ID**가 없으면 Azure AD에서 앱을 인증할 수 없습니다.

> **참고**: Power BI에 앱을 등록하기 전에, [Power BI에 가입](create-an-azure-active-directory-tenant.md)해야 합니다.

Azure AD에 앱을 등록하는 단계는 다음과 같습니다.

## <a name="register-an-app-in-azure-ad"></a>Azure AD에 앱 등록

1. dev.powerbi.com/apps로 이동합니다.
2. **기존 계정으로 로그인** 을 클릭하고 Power BI 계정에 로그인합니다.
3. **앱 이름**을 "Sample push data app"과 같이 입력합니다.
4. **앱 유형**에서 **네이티브 앱**을 선택합니다.

5. **액세스할 API 선택**에서 **모든 데이터 세트 읽기 및 쓰기**를 선택합니다. 모든 Power BI 앱 사용 권한은 [Power BI 사용 권한](power-bi-permissions.md)을 참조하세요.
6. **앱 등록**을 클릭하고 생성된 **응용 프로그램 ID** 를 저장합니다. **응용 프로그램 ID** 는 Azure AD의 앱을 식별합니다.

**Power BI에 응용 프로그램 등록** 페이지가 다음과 같이 표시됩니다.

![앱 등록](media/walkthrough-push-data-register-app-with-azure-ad/powerbi-developer-sample-register-app.png)

다음 단계에서는 [인증 액세스 토큰을 가져오는](walkthrough-push-data-get-token.md) 방법을 보여 줍니다.

[다음 단계 >](walkthrough-push-data-get-token.md)

## <a name="next-steps"></a>다음 단계

[Power BI에 등록](create-an-azure-active-directory-tenant.md)  
[인증 액세스 토큰 가져오기](walkthrough-push-data-get-token.md)  
[연습: 데이터 세트에 데이터 푸시](walkthrough-push-data.md)  
[애플리케이션 등록](register-app.md)  
[Power BI REST API 개요](overview-of-power-bi-rest-api.md)  

궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](http://community.powerbi.com/)
