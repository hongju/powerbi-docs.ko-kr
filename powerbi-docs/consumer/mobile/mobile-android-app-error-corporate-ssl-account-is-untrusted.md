---
title: “회사 SSL 인증서를 신뢰할 수 없습니다” 수정
description: Power BI용 Android 앱에 로그인할 때 "회사 SSL 인증서를 신뢰할 수 없기 때문에 인증할 수 없습니다."라는 메시지가 표시될 수 있습니다.
.": ''
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-mobile
ms.topic: conceptual
ms.date: 05/18/2018
ms.author: maggies
ms.openlocfilehash: 494e148a62675aab1a6e799c4e4b61f022483d9f
ms.sourcegitcommit: 67336b077668ab332e04fa670b0e9afd0a0c6489
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2018
ms.locfileid: "44743102"
---
# <a name="fixing-corporate-ssl-certificate-is-untrusted---power-bi"></a>“회사 SSL 인증서를 신뢰할 수 없습니다.” 수정 - Power BI
Microsoft Power BI용 Android 모바일 앱에 로그인할 때 "이 장치에서 회사 SSL 인증서를 신뢰할 수 없기 때문에 인증할 수 없습니다."라는 메시지가 표시될 수 있습니다. 회사 IT 관리자에게 문의하세요." 

일반적으로 필요한 작업은 Android 장치의 운영 체제에 따라 다르지만 이 오류가 발생할 수 있는 몇 가지 다른 문제가 있습니다.

## <a name="on-android-7-or-later"></a>Android 7 이상
**Chrome** 앱의 업데이트를 찾아 설치합니다.

## <a name="on-android-6-and-earlier"></a>Android 6 이하
장치에 업데이트된 버전의 System Webview가 필요할 수 있습니다. 장치에 설치되어 있을 수 있으므로 **업데이트**를 클릭만 하면 됩니다.

장치에 System Webview가 설치되어 있지 않은 경우

1. Android 장치에서 Power BI를 닫습니다.
2. Google Play 스토어를 열고 Google Inc.의 **System Webview**를 검색합니다.
3. 설치합니다.
4. Power BI 앱을 다시 시작하고 로그인합니다.

## <a name="time-zone-settings"></a>표준 시간대 설정
장치의 시간대 설정이 잘못되었을 수 있습니다. 

**설정** > **시스템** > **날짜 및 시간**으로 이동하여 확인합니다.

## <a name="custom-authentication-server"></a>사용자 지정 인증 서버
사용자 지정 인증 서버를 사용하는 경우 회사 인증 서버의 SSL 인증서가 유효하지 않을 수 있습니다. 도움을 받으려면 조직의 IT 관리자에게 문의하세요.

## <a name="next-steps"></a>다음 단계
* Android 앱 스토어에서 [Android 앱 다운로드](http://go.microsoft.com/fwlink/?LinkID=544867)
* 궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](http://community.powerbi.com/)

