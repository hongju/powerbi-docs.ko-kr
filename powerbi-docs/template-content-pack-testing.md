---
title: Power BI용 템플릿 콘텐츠 팩 테스트
description: 템플릿 콘텐츠 팩 테스트
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/09/2017
ms.author: maggies
ms.openlocfilehash: 4f461029ab3f698992128fa4f3f53714ee962b1e
ms.sourcegitcommit: 3a287ae4ab16d1e76caed651bd8ae1a1738831cd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/19/2018
ms.locfileid: "39157549"
---
# <a name="testing-template-content-packs-for-power-bi"></a>Power BI용 템플릿 콘텐츠 팩 테스트
게시를 위해 제출하기 전에 여러 가지 방법으로 콘텐츠 팩을 테스트할 수 있습니다.  

> [!NOTE]
> 콘텐츠 팩이 개발한 사용자 지정 [데이터 커넥터](https://aka.ms/DataConnectors)를 사용하는 경우 아래 설명된 대로 데이터 새로 고침 또는 템플릿 콘텐츠 팩을 테스트할 수 없습니다. 이 경우 콘텐츠 팩 [제출](#submission)을 진행하면 Power BI 팀은 콘텐츠 팩을 테스트합니다.
> 
> 

## <a name="testing-scheduled-data-refresh"></a>예약된 데이터 새로 고침 테스트
템플릿 콘텐츠 팩은 PowerBI.com에서 새로 고침을 활용하여 콘텐츠 팩을 고객의 데이터로 인스턴스화합니다(연결된 경우). 콘텐츠 팩을 공개적으로 제공하기 전에 사용자가 만든 데스크톱 파일로 이 흐름을 테스트할 수 있습니다.

파일을 업로드한 후에는 데이터 집합 옆에 있는 "..."를 선택하고 새로 고침 예약을 선택합니다. 원본에 대한 자격 증명을 구성합니다. 데이터 집합이 성공적으로 새로 고침되었는지 확인하고 "지금 새로 고침"과 "예약 된 새로 고침"을 모두 시도해 봅니다. 새로 고침에서 오류가 발생하면 오류 메시지를 확인하고 쿼리와 최종 시스템의 유효성을 검사합니다.

### <a name="additional-refresh-tips"></a>추가 새로 고침 팁
* 새로 고침을 예약하려고 할 때 하나의 데이터 원본만 검색됩니다.  
* 연결 테스트 시 사용자가 콘텐츠 팩을 로드할 수 있음이 표시됩니다. 그렇지 않은 경우 쿼리에서 추가 오류 사례를 처리하는지 확인합니다.  
* 새로 고침은 적당한 시간 내에 완료되어야 합니다. 5분 이내가 적당합니다.  

![설정](media/template-content-pack-testing/scheduledrefresh.png)

<a name="templates"></a>

## <a name="testing-templates"></a>템플릿 테스트
템플릿 콘텐츠 팩은 데이터 집합에 실제 데이터를 포함하지 않는 것만 제외하고 기존 솔루션과 유사합니다. 대신, 사용자가 템플릿을 사용하거나 인스턴스화할 때 연결할 매개 변수 및 자격 증명을 묻는 메시지가 표시됩니다. 연결되면 대시보드, 보고서 및 데이터 집합에 사용자 고유의 데이터가 표시됩니다. 

사용자가 예정된 새로 고침을 포함하여 데이터 집합 설정에 액세스할 수 있는 콘텐츠 팩을 인스턴스화한 후 데이터 집합에 있는 모든 RLS 설정은 콘텐츠 팩을 사용하여 게시되지 **않습니다**.  

> [!NOTE]
> 템플릿 콘텐츠 팩에는 대시보드 1개, 보고서 1개 및 데이터 집합 1개만 포함할 수 있습니다. [작성](template-content-pack-authoring.md#restrictions) 페이지에서 제한 사항 목록을 참조하세요. 
> 
> 

테넌트에 대한 템플릿 만들기를 활성화하려면 Power BI 관리자로 작업하여 아래 기능 스위치를 활성화합니다. 

![featureswitch](media/template-content-pack-testing/featureswitch.png)

활성화되면 조직에 템플릿 콘텐츠 팩을 게시할 수 있도록 ["콘텐츠 팩 만들기"](https://app.powerbi.com/groups/me/publish-content/) 맨 아래에 확인란이 표시됩니다. 

![확인란](media/template-content-pack-testing/checkbox.png)

### <a name="naming"></a>이름 지정
콘텐츠 팩 전체에 일관되게 대시보드, 보고서 및 데이터 집합의 이름을 지정하는 것이 좋습니다. 이러한 이름은 하드 코딩되며 모든 사용자에 대해 동일하므로 제품/시나리오 이름을 사용하면 고객이 찾기 쉽습니다.

### <a name="additional-template-tips"></a>추가 템플릿 팁
* 쿼리에 지정한 매개 변수가 최종 사용자에게 의미 있도록 합니다.
* 최종 사용자가 예약된 새로 고침을 완료하는 데 얼마나 기다리는지를 고려합니다.

![만들기](media/template-content-pack-testing/createtemplate.png)

<a name="submission"></a>

## <a name="submission"></a>제출
[Microsoft AppSource](https://appsource.microsoft.com/en-us/partners/list-an-app)를 통한 제출 프로세스를 통해 PowerBI.com의 서비스 콘텐츠 팩 갤러리에서 템플릿 콘텐츠 팩을 게시할 뿐만 아니라 [Microsoft AppSource](http://appsource.microsoft.com)에 콘텐츠 팩을 나열합니다.

### <a name="before-submission"></a>제출하기 전에
* 콘텐츠 팩 내에 있는 각 아티팩트에 대해 작성 팁을 검토합니다.
* 다양한 계정 및 데이터 조건으로 테스트 및 연결합니다. (사용자 고유의 사용자 지정 [데이터 커넥터](https://aka.ms/DataConnectors)를 개발한 경우 이 단계를 건너뜁니다.)
* 모든 시각적 개체를 검토하고 철자가 잘못된 항목은 없는지 신중하게 확인합니다.
* 콘텐츠 팩이 Q&A에 대해 잘 응답하는지 확인하고 데이터 모델에 대해 30개 이상의 다양한 질문으로 테스트해보는 것이 좋습니다. (사용자 고유의 사용자 지정 [데이터 커넥터](https://aka.ms/DataConnectors)를 개발한 경우 이 단계를 건너뜁니다.)

### <a name="submission"></a>제출
제출할 준비가 되면 AppSource의 [앱 제출 페이지](https://appsource.microsoft.com/en-us/partners/list-an-app)를 방문하고 정보를 제출합니다. 사용 가능한 제품 목록에서 Power BI가 선택되어 있는지 확인합니다.

Power BI 팀에서 제출을 검토하고 모든 아티팩트가 제출 요구 사항을 충족하는지 확인하도록 연락합니다. 완료하는 것 외에도 응용 프로그램에 설명된 비즈니스 시나리오를 충족하는지 확인하기 위해 제공된 대시보드 및 보고서의 품질도 확인합니다.

### <a name="updates"></a>업데이트
콘텐츠 팩 업데이트는 원래 제출과 유사한 흐름을 따릅니다. 

