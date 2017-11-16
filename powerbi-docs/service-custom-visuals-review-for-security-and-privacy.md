---
title: "보안 및 개인 정보에 대한 사용자 지정 시각적 개체 검토"
description: "사용자 지정 시각적 개체를 사용하기 전에 보안 및 개인 정보에 대한 사용자 지정 시각적 개체를 검토하여 조직의 표준에 적합한지 확인해야 합니다."
services: powerbi
documentationcenter: 
author: guyinacube
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
ms.date: 09/05/2017
ms.author: asaxton
ms.openlocfilehash: 40c2c713615f6e9e5378d36b6b228dc864bcb57c
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2017
---
# <a name="review-custom-visuals-for-security-and-privacy"></a>보안 및 개인 정보에 대한 사용자 지정 시각적 개체 검토
사용자 지정 시각적 개체를 사용하기 전에 보안 및 개인 정보에 대한 사용자 지정 시각적 개체를 검토하여 조직의 표준에 적합한지 확인해야 합니다.

## <a name="enable-a-custom-visual"></a>사용자 지정 시각적 개체 사용
<a name="enable"></a>보고서에서 사용자 지정 시각적 개체는 아래와 같이 **사용자 지정 시각적 개체 사용**을 선택할 때까지 사용할 수 없습니다.  

![](media/service-custom-visuals-review-for-security-and-privacy/emptyvisual.png)

## <a name="considerations-before-you-enable-a-custom-visual"></a>사용자 지정 시각적 개체를 사용하기 전에 고려할 사항
<a name="considerations"></a>

> [!WARNING]
> 사용자 지정 시각적 개체는 보안 또는 개인 정보 위험을 가진 코드를 포함할 수 있습니다. 따라서 보고서의 사용자 지정 시각적 개체는 사용자 지정 시각적 개체 사용을 선택할 때까지 사용되지 않습니다. 다음은 사용자 지정 시각적 개체를 사용할지 여부를 결정할 때 고려 사항입니다.
> 
> 

1. 보고서에 사용되는 사용자 지정 시각적 개체의 작성자 및 원본을 신뢰해야 합니다.
2. 수행할 작업이 확실하지 않은 경우 IT 팀에 연락하여 확인할 보고서에 사용자 지정 시각적 개체를 사용해야 하는지 여부를 알아봅니다.
3. 사용자 지정 시각적 개체를 포함하는 보고서를 다른 사용자와 공유하는 경우 가까운 동료이더라도 사용자 지정 시각적 개체를 사용할 의무가 있다고 생각하지 마세요. 수행할 작업에 필수적인지 다시 돌아가서 생각해도 됩니다. 사용자 지정 시각적 개체에 대해 확신이 없는 경우 사용자 지정 시각적 개체 없이 보고서를 제공할지 물어도 됩니다.

## <a name="security-best-practices-for-it-professionals-to-enable-a-custom-visual"></a>사용자 지정 시각적 개체를 사용하기 위한 IT 전문가를 위한 보안 모범 사례
<a name="security"></a>

> [!WARNING]
> 사용자 지정 시각적 개체는 보안 또는 개인 정보 위험을 가진 코드를 포함할 수 있습니다. 따라서 보고서의 사용자 지정 시각적 개체는 사용자 지정 시각적 개체 사용을 선택할 때까지 사용되지 않습니다. 보안 및 개인 정보에 대한 사용자 지정 시각적 개체를 평가하기 위해 따를 수 있는 몇 가지 모범 사례가 있습니다.
> 
> 

1. 조직 내에서 사용자 지정 시각적 개체에 대한 심사 프로세스를 구현합니다. 심사된 사용자 지정 시각적 개체는 SharePoint 문서 라이브러리 또는 OneNote 문서 등 내부 웹 사이트를 통해 내부 사용자와 공유합니다.
2. 사용자 지정 시각적 개체를 사용하는 비즈니스 사용자에 대한 지침 및 보안 및 개인 정보 질문을 보낼 비즈니스 사용자에 대한 전자 메일 그룹을 제공합니다.
3. 사용자 지정 시각적 pbiviz 파일의 JavaScript 코드를 평가합니다.

**사용자 지정 시각적 개체의 JavaScript 코드를 평가하려면**

사용자 지정 시각적 개체는 JavaScript를 사용하고 따라서 보안 또는 개인 정보 위험을 포함할 수 있습니다. 알 수 없는 원본의 사용자 지정 시각적 개체를 사용하여 사용자 지정 시각적 개체 또는 pbix 파일을 수신하는 경우 안전한지 확인하기 위해 JavaScript를 보는 것이 좋습니다.

사용자 지정 시각적 개체의 JavaScript 코드를 평가하려면 사용자 지정 시각적 코드를 추출합니다. 코드를 추출하는 방법은 다음과 같습니다.  

1. .pbiviz 파일을 폴더에 저장합니다.
2. 파일의 이름을 .zip 파일로 바꿉니다.
3. zip 파일을 로컬 폴더에 추출합니다.

## <a name="custom-visual-file-contents"></a>사용자 지정 시각적 파일 내용
다음은 pbiviz 파일의 내용입니다.

| **파일** | **설명** |
|:--- |:--- |
| ./package.json |사용자 지정 시각적 개체에 대한 로드될 파일을 나타내는 매니페스트 파일입니다. |
| ./resources |사용자 지정 시각적 개체에서 사용하는 CSS, TypeScript 및 JavaScript를 포함합니다. |
| ./resources/&lt;name&gt; |&lt;name&gt;은 사용자 지정 시각적 개체의 이름입니다. |
| ./resources/&lt;이름&gt;.css |사용자 지정 시각적 개체에 대한 css 리소스 파일입니다. |
| ./resources/&lt;이름&gt;.js |사용자가 사용자 지정 시각적 개체를 클릭할 때 또는 사용자 지정 시각적 개체를 가져온 후에 실행하는 코드입니다. JavaScript 코드를 경고하는 작업은 보안 또는 개인 정보 위험을 포함할 수 있습니다. |
| ./resources/&lt;이름&gt;.ts |TypeScript 형식에서 시각적 개체에 대한 JavaScript 원본 코드입니다. JavaScript 또는 TypeScript 코드를 경고하는 작업은 보안 또는 개인 정보 위험을 포함할 수 있습니다. |
| ./resources/&lt;이름&gt;.png |시각적 개체를 사용자에게 표시하는 아이콘입니다. |

pbiviz 파일을 추출한 후에 코드를 평가할 수 있습니다. 다음은 찾아봐야 할 몇 가지 모범 사례 및 위협입니다.

## <a name="best-practices-to-evaluate-the-javascript-or-typescript-code"></a>JavaScript 또는 TypeScript 코드를 평가하는 모범 사례
**JavaScript** 또는 **TypeScript** 코드는 보안 또는 개인 정보 위험을 포함할 수 있습니다. 다음은 찾아봐야 할 몇 가지 모범 사례 및 위협입니다.

### <a name="best-practices-to-evaluate-javascript-code"></a>JavaScript 코드를 평가하는 모범 사례
* 항상 .js 파일의 내용을 평가합니다. 실제로 실행되는 코드입니다. .ts 파일의 내용은 사용자 지정 시각적 개체에 포함된 .js 파일에 컴파일되지 않을 수 있습니다.
* 항상 .ts 파일의 내용을 평가합니다. .ts 파일을 **개발자 도구**에 로드하고 시각적 개체를 내보내며 새로 만든 .pbiviz 파일에서 결과인 .js 파일을 시각적 개체에 포함된 원래의 .js 파일과 비교할 수 있습니다.
* 사용자 지정 시각적 개체에 대한 아이콘이 사용자가 익숙한 다른 시각적 개체와 너무 유사하지 않도록 합니다.
* 항상 최소 권한을 가지고 중요한 데이터에 액세스할 수 없는 테스트 계정에서 시각적 개체를 평가합니다. 이상적인 테스트 계정은 Power BI 이외의 서비스에 로그인 정보가 없는 로컬 계정입니다.

### <a name="threats-to-look-for-in-javascript-code"></a>JavaScript 코드에서 찾아볼 위협
* 편집 및 보기 모드에서 시각적 개체를 사용하는 경우 네트워크 활동을 확인합니다. 생성되는 요청을 사용하여 만족하도록 합니다. 시각적 작성자가 앞서 통신하지 않는 한 Power BI 도메인 외부의 리소스에 대한 요청은 확인해서는 안됩니다.
* Power BI 도메인을 남겨둘 경우 표시되는 데이터는 '일반적인' 사용에 대한 예상과 일치해야 합니다. 예를 들어 시각적 개체가 다른 사이트에서 비디오를 보기 위해 iFrame을 사용하는 비디오 플레이어를 구현하는 경우 일부 정보는 비디오를 올바르게 렌더링하는 IFrame 요청으로 이동해야 합니다. 그러나 네트워크를 통해 전송되는 전체 데이터 집합을 표시하는 경우 필요하면 자세히 조사할 수 있습니다.
* 개인적으로 식별할 수 있는 데이터가 사용자 지정 시각적 개체에 의해 전송되거나 저장되는지 확인합니다.
* 사용자 지정 시각적 개체가 디스크에 파일 쓰기 또는 쿠키 액세스와 같은 로컬 컴퓨터 리소스에 액세스하려고 하는지 확인합니다.
* 사용자 지정 시각적 개체가 난독 처리된 코드 또는 명확한 용도가 없는 코드로 표시되는지 확인합니다.
* 이전에 검토된 각 시각적 개체의 복사본을 저장합니다.
* 이전에 검토한 시각적 개체에 대한 업데이트를 검토하는 경우 변경 내용을 확인해야 합니다. 검토를 위해 시각적 개체를 처음으로 받은 경우 수행한 것처럼 업데이트하는 데 항상 같은 어려움이 있습니다.
* 의심스럽거나 모호한 부분이 있으면 도와드리겠습니다. 문의하세요.

## <a name="next-steps"></a>다음 단계
[Power BI의 시각화](power-bi-report-visualizations.md)  
[Power BI의 사용자 지정 시각화](power-bi-custom-visuals.md)  
[Office 스토어에서 사용자 지정 시각적 개체 다운로드 및 사용](service-custom-visuals-office-store.md)  
[보고서에 사용자 지정 시각화 추가(Power BI Desktop)](power-bi-custom-visuals-use.md)  
[보고서에 사용자 지정 시각화 추가(Power BI Service)](power-bi-report-add-custom-visual.md)  
[사용자 지정 시각적 개체를 Office 스토어에 게시](developer/office-store.md)  
[사용자 지정 시각적 개체 개발자 도구 시작하기](service-custom-visuals-getting-started-with-developer-tools.md)  
[사용자 지정 시각적 개체를 인증하는 방법](power-bi-custom-visuals-certified.md)    
[비디오: Sachin Patney 및 Nico Cristache와 Power BI에 대한 사용자 지정 시각화 만들기](https://www.youtube.com/watch?v=kULc2VbwjCc)  

궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문하기](http://community.powerbi.com/)

