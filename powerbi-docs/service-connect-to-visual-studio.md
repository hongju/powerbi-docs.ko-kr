---
title: "Power BI로 Visual Studio Team Services에 연결"
description: "Power BI용 Visual Studio Team Services"
services: powerbi
documentationcenter: 
author: joeshoukry
manager: kfile
backup: maggiesMSFT
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/16/2017
ms.author: yshoukry
ms.openlocfilehash: 20ea9117cf1eee3d7b05be21e5964226349a58c1
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2017
---
# <a name="connect-to-visual-studio-team-services-with-power-bi"></a>Power BI로 Visual Studio Team Services에 연결
Power BI용 Visual Studio Team Services 콘텐츠 팩을 사용하여 Git 및 TFVC 팀 프로젝트를 파악합니다. 연결하면 데이터가 자동으로 대시보드 및 보고서에 표시됩니다. 

[Visual Studio Team Services 콘텐츠 팩](https://app.powerbi.com/getdata/services/visual-studio-online)에 연결하거나 Power BI와의 [Visual Studio Team Services 통합](https://powerbi.microsoft.com/integrations/visual_studio_online)에 대해 자세히 알아보세요.

>[!NOTE]
>이 콘텐츠 팩을 사용하려면 OAuth가 설정된 계정에 대한 액세스 권한이 필요합니다. 요구 사항에 대한 자세한 내용은 아래에 나와 있습니다.

## <a name="how-to-connect"></a>연결 방법
1. 왼쪽 탐색 창의 맨 아래에 있는 **데이터 가져오기** 를 선택합니다.  
   ![](media/service-connect-to-visual-studio/pbi_getdata.png) 
2. **서비스** 상자에서 **가져오기**를 선택합니다.  
   ![](media/service-connect-to-visual-studio/pbi_getservices.png) 
3. **Visual Studio Team Services** 콘텐츠 팩을 선택하고 **가져오기**를 클릭합니다.     
   ![](media/service-connect-to-visual-studio/vsts.png)
4. Visual Studio Team Services 계정에 대한 정보를 입력합니다. 아래에서 [해당 매개 변수 찾기](#FindingParams)에 대한 세부 정보를 참조하세요.
   
   ![](media/service-connect-to-visual-studio/pbi_vsosignin.png)
   
   계정 이름은 visualstudio.com에 대한 URL의 앞부분입니다.    
   ![](media/service-connect-to-visual-studio/urlimage.png)
   
   프로젝트 이름은 Visual Studio Team Services에서 모든 페이지의 맨 위에 표시되는 이름입니다.  
   ![](media/service-connect-to-visual-studio/projectimage.png)
5. oAuth2를 사용하여 Visual Studio Team Services에 인증합니다. 그 결과로 VSTS 로그인 대화 상자가 표시될 수도 있습니다. 
   
   > [!IMPORTANT]
   > 일부 Visual Studio Team Services 배포에서는 oAuth2를 지원하지 않습니다.  로그인에 실패하는 경우 문제 해결 섹션의 지침을 따르세요.
   > 
   > 
   
   ![](media/service-connect-to-visual-studio/pbi_vsosignin2.png)
6. Visual Studio Team Services 인증 화면에 따라 Power BI용 Visual Studio 콘텐츠 팩에 팀 프로젝트 데이터에 대한 권한을 부여합니다.   
   ![](media/service-connect-to-visual-studio/vsoauthorizeapp450.png)
7. Visual Studio Team Services 프로젝트에 연결하면 왼쪽 탐색 창에 새 대시보드, 보고서 및 데이터 집합이 표시됩니다. 새 항목은 노란색 별표 \*로 표시됩니다.  
   ![](media/service-connect-to-visual-studio/visualstudioonline800px.png) 

**다음 단계**

* 대시보드 맨 위에 있는 [질문 및 답변 상자에 질문](service-q-and-a.md)합니다.
* 대시보드에서 [타일을 변경](service-dashboard-edit-tile.md)합니다.
* [타일을 선택](service-dashboard-tiles.md)하여 원본 보고서를 엽니다.
* 데이터 집합을 매일 새로 고치도록 예약하는 경우 새로 고침 일정을 변경하거나 **지금 새로 고침**을 사용하여 필요할 때 새로 고칠 수 있습니다.

## <a name="whats-included"></a>포함된 내용
Power BI의 Visual Studio Team Services는 보고에 필요한 다양한 테이블 및 필드를 제공합니다. 콘텐츠 팩에 포함된 항목의 전체 목록은 여기에서 찾을 수 있습니다. <https://www.visualstudio.com/get-started/report/vso-pbi-whats-available-vs>

## <a name="system-requirements"></a>시스템 요구 사항
* REST API를 사용하여 데이터를 수집할 수 있는 권한이 있는 Visual Studio Team Services 계정에 액세스합니다.  
* 초기 연결 중에 "Power BI" 응용 프로그램에 대한 권한이 부여되었습니다. Power BI를 분리하고 Visual Studio Team Services 계정에 액세스하는 권한 부여를 제거하기 위해 Visual Studio Team Services에서 액세스 권한을 해지할 수 있습니다. <https://www.visualstudio.com/get-started/setup/change-application-access-policies-vs>를 참조하세요.  

자세한 내용은 <https://www.visualstudio.com/en-us/get-started/report/connect-vso-pbi-vs>에서 찾을 수 있습니다.

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>매개 변수 찾기
계정 이름은 visualstudio.com에 대한 URL의 앞부분입니다.    
    ![](media/service-connect-to-visual-studio/urlimage.png)

프로젝트 이름은 VSTS에서 모든 페이지의 맨 위에 표시되는 이름입니다.  
    ![](media/service-connect-to-visual-studio/projectimage.png)

와일드카드를 사용하여 여러 프로젝트를 선택할 수도 있습니다. 예를 들어 "\*"만 입력하여 모든 프로젝트를 선택하거나 "Azure\*"를 입력하여 "Azure"로 시작하는 모든 프로젝트를 선택할 수 있습니다.

## <a name="troubleshooting"></a>문제 해결
Visual Studio Team Services에 로그인할 때 로그인 실패 메시지가 나타날 수 있습니다.

성공적으로 인증할 수 없는 두 가지 일반적인 이유는 다음과 같습니다.

1) 회사 또는 학교 계정이 아니라 개인 계정으로 로그인했습니다.  

2) Visual Studio Team Services 배포에서 oAuth를 지원하지 않습니다. 

**회사 또는 학교 계정을 사용하여 로그인**  
이 문제가 표시되는 경우 데이터를 로드하려는 계정이 아닌 다른 계정으로 Visual Studio Team Services에 이미 인증되었음을 의미할 수 있습니다. 예를 들어 개인 Microsoft 계정으로 Visual Studio Team Services에 연결하고 회사 또는 학교 계정으로 PowerBI에 연결한 경우일 수 있습니다.

이 문제를 해결하려면  

* 구성 대화 상자를 취소합니다.  
* 개인 계정을 사용한 Visual Studio Team Services에서 로그아웃합니다.  
* 회사 또는 학교 계정을 사용하여 Visual Studio Online에 로그인합니다.  
* 위의 "데이터 가져오기" 프로세스를 다시 시작합니다. 

회사 또는 학교 계정을 사용하여 연결(Azure Active Directory/AAD):  
    ![](media/service-connect-to-visual-studio/vsologinscreen.png)

이 대화 상자가 표시되고 회사 또는 학교 계정(Azure Active Directory)을 사용하여 연결하려는 경우 왼쪽에 있는 링크를 클릭하여 해당 계정으로 로그인해야 합니다. Microsoft 계정(개인 계정)이 필요한 오른쪽에서 AAD 자격 증명을 제공하지 마세요.

**oAuth2를 지원하지 않는 Visual Studio Team Services 배포**  
VSTS 관리자가 Visual Studio Team Services 배포에 대해 oAuth를 사용하지 않도록 설정했을 수 있습니다.  이 경우 지금은 Power BI용 Visual Studio 콘텐츠 팩을 사용할 수 없습니다. 

![](media/service-connect-to-visual-studio/oauth.png)

## <a name="next-steps"></a>다음 단계
* [Power BI 시작](service-get-started.md)
* [데이터 가져오기](service-get-data.md)

