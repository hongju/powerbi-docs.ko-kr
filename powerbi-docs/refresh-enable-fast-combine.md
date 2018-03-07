---
title: "개인 정보 설정 사용 안함"
description: "개인 게이트웨이 내에서 빠른 결합을 사용하여 새로 고침에 개인 정보 설정을 사용하지 않는 방법입니다."
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: powerbi
ms.date: 02/06/2018
ms.author: davidi
LocalizationGroup: Data refresh
ms.openlocfilehash: 54d5f5ec2db890de0fbcef5ef0633548b90a6079
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/24/2018
---
# <a name="disable-privacy-setting-in-power-bi-gateway---personal"></a>Power BI 게이트웨이의 개인 정보 보호 설정 해제 - 개인
> [!NOTE]
> **온-프레미스 데이터 게이트웨이(개인 모드)**라고 하는 Power BI에 대한 개인 게이트웨이의 새 버전이 있습니다. 다음 문서는 2017년 7월 31일 이후 사용 및 작동이 중지되는 **Power BI Gateway - Personal**이라 불리는 개인 게이트웨이의 이전 버전에 대해 설명합니다. 새 버전의 설치 방법을 비롯한 개인 게이트웨이의 새 버전에 대한 자세한 내용은 [**온-프레미스 데이터 게이트웨이(개인 모드)** 문서](service-gateway-personal-mode.md)를 참조하세요. 빠른 결합은 개인 게이트웨이의 새 버전에서 사용할 수 있으며 해당 문서에 함께 설명되어 있습니다.
> 
> 

개인 게이트웨이를 사용하는 경우 데이터 원본에 대한 개인 정보 설정에 따라 다음 오류가 나타날 수 있습니다.

> *데이터 집합의 데이터를 처리하는 동안 오류가 발생했습니다.*
> 
> *[데이터를 결합할 수 없습니다.] &lt;쿼리 부분&gt;/&lt;…&gt;/&lt;…&gt;이 함께 사용할 수 없는 개인 정보 수준의 데이터 원본에 액세스합니다. 이 데이터 조합을 다시 작성합니다.*
> 
> 

이 오류를 해결하기 위해 **빠른 결합**을 사용할 수 있습니다. **빠른 결합** 은 다양한 데이터 원본이 결합될 수 있도록 개인 정보 설정을 무시합니다.

> [!NOTE]
> 데이터를 결합하는 경우 개인 정보 수준은 고려되지 않습니다. 데이터를 결합할 때 중요한 기밀 데이터를 다른 데이터 원본에 노출할 수 있습니다.
> 
> 

## <a name="what-is-fast-combine"></a>빠른 결합의 정의
개인 정보 수준 및 빠른 결합에 대해 알아보려면 [개인 정보 수준](https://support.office.com/article/Privacy-levels-Power-Query-CC3EDE4D-359E-4B28-BC72-9BEE7900B540)을 볼 수 있습니다. 기본적으로 개인 정보 수준은 위에서 언급한 오류가 발생할 수 있는 비공개로 설정됩니다. 이는 개인 설정이 다른 원본에서 데이터 원본을 분리하기 때문입니다. 어떤 부분이 문제가 될지에 대한 예를 다른 데이터 원본에서 입력을 가져오는 매개 변수가 있는 쿼리에서 찾을 수 있습니다.

빠른 결합을 사용하면 개인 설정을 무시하고 실행되도록 허용합니다.

## <a name="turn-on-fast-combine"></a>빠른 결합 사용
다음 단계를 사용하여 개인 게이트웨이에 빠른 결합을 사용할 수 있습니다. 온-프레미스 데이터 게이트웨이에는 이 설정이 없습니다.

1. **ConnectorConfig.xml**를 엽니다.  컴퓨터에서 다음 두 위치 중 하나에 있을 수 있습니다.  컴퓨터의 관리자인 경우 다음일 것입니다.
   
    <pre><code>C:\Program Files\Power BI Personal Gateway\1.0\Configurator\Connector</code></pre>
   
    컴퓨터의 관리자가 아닌 경우 위치는 다음일 것입니다.
   
    <pre><code>C:\Users\[username]\AppData\Local\Power BI Personal Gateway\1.0\Configurator\Connector</code></pre>
    
2. 구성 파일에 true 값을 가진 **&lt;EnableFastCombine&gt;** 요소를 추가합니다. 이 요소를 추가하면 **빠른 결합**을 사용합니다.
   
   <pre><code>&lt;EnableFastCombine&gt;true&lt;/EnableFastCombine&gt;</code></pre>
   
   ![](media/refresh-enable-fast-combine/configfile.png)
3. 게이트웨이 구성 화면을 종료하고 다시 시작합니다.
4. 빠른 결합을 사용할 수 있다고 알려주는 상태가 표시됩니다.
   
   ![](media/refresh-enable-fast-combine/fastcombineenabled.png)

## <a name="turn-off-fast-combine"></a>빠른 결합 해제
1. **ConnectorConfig.xml**를 엽니다.  컴퓨터에서 다음 두 위치 중 하나에 있을 수 있습니다.  컴퓨터의 관리자인 경우 다음일 것입니다.
   
    <pre><code>C:\Program Files\Power BI Personal Gateway\1.0\Configurator\Connector</code></pre>
   
    컴퓨터의 관리자가 아닌 경우 위치는 다음일 것입니다.
   
    <pre><code>C:\Users\[username]\AppData\Local\Power BI Personal Gateway\1.0\Configurator\Connector</code></pre>

2. 구성 파일에서 **&lt;EnableFastCombine&gt;** 요소를 제거합니다. 이 요소를 제거하면 **빠른 결합**을 해제합니다.
3. 게이트웨이 구성 화면을 종료하고 다시 시작합니다.
4. **빠른 결합**을 더이상 사용할 수 없다고 알려주는 상태가 표시됩니다.

## <a name="next-steps"></a>다음 단계
[온-프레미스 데이터 게이트웨이(개인 모드) - 개인 게이트웨이의 새 버전](service-gateway-personal-mode.md)
[개인 정보 수준](https://support.office.com/article/Privacy-levels-Power-Query-CC3EDE4D-359E-4B28-BC72-9BEE7900B540)  
[Power BI Desktop의 일반적인 쿼리 작업](desktop-common-query-tasks.md)  
궁금한 점이 더 있나요? [Power BI 커뮤니티를 이용하세요.](http://community.powerbi.com/)

