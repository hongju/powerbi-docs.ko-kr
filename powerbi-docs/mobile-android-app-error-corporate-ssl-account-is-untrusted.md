---
title: "오류: "
corporate: 
ssl: 
certificate: 
is: 
untrusted": 
'-': 
power: 
bi": 
description: "Power BI용 Android 앱에 로그인할 때 \"회사 SSL 인증서를 신뢰할 수 없기 때문에 인증할 수 없습니다.\"라는 메시지가 표시될 수 있습니다."
.": 
services: powerbi
documentationcenter: 
author: maggiesMSFT
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
ms.date: 10/13/2017
ms.author: maggies
ms.openlocfilehash: 4ef29c0cab96e21045f30805d7445aa34d37697a
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2017
---
# <a name="error-corporate-ssl-certificate-is-untrusted---power-bi"></a>오류: "회사 SSL 인증서를 신뢰할 수 없습니다." - Power BI
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

