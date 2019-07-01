---
title: Power BI 템플릿 앱이란?
description: 이 문서는 Power BI 템플릿 앱 프로그램의 개요입니다. 코딩이 거의 없거나 전혀 없는 Power BI 앱을 빌드하고 Power BI 고객에게 배포하는 방법을 알아봅니다.
author: teddybercovitz
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 06/24/2019
ms.author: tebercov
ms.openlocfilehash: c05b53a5fd61d348b6d304b17123d5f2497ab647
ms.sourcegitcommit: 58c649ec5fd2447a0f9ca4c4d45a0e9fff2f1b6a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2019
ms.locfileid: "67408206"
---
# <a name="what-are-power-bi-template-apps"></a>Power BI 템플릿 앱이란?

새 Power BI *템플릿 앱*을 사용하면 Power BI 파트너는 코딩이 거의 없거나 전혀 없는 Power BI 앱을 만들고 모든 Power BI 고객에게 배포할 수 있습니다.  이 문서는 Power BI 템플릿 앱 프로그램의 개요입니다.

템플릿 앱은 현재 서비스 콘텐츠 팩을 대체합니다. Power BI 파트너로서 고객이 즉시 사용할 수 있는 콘텐츠 세트를 만들고 직접 게시할 수 있습니다.  

고객이 자신의 계정으로 연결하고 인스턴스화할 수 있는 템플릿 앱을 빌드합니다. 도메인 전문가는 비즈니스 사용자가 쉽게 사용할 수 있는 방식으로 데이터의 잠금을 해제할 수 있습니다.  

템플릿 앱을 Cloud 파트너 포털에 제출합니다. 그런 다음, 이 앱은 Power BI 앱 갤러리(app.powerbi.com/getdata/services) 및 Microsoft AppSource(appsource.microsoft.com)에서 공개적으로 사용할 수 있게 됩니다. 다음은 공용 템플릿 앱 생성 환경을 개괄적으로 살펴봅니다.  

## <a name="process"></a>프로세스
템플릿 앱을 개발하고 제출하는 일반적인 프로세스는 여러 단계로 구성됩니다. 일부 단계는 동시에 둘 이상의 작업을 포함할 수 있습니다.


| 단계 | Power BI Desktop |  |Power BI 서비스  |  |Cloud 파트너 포털  |
|---|--------|--|---------|---------|---------|
| **1개** | .pbix 파일에서 데이터 모델 및 보고서 빌드 |  | 작업 영역을 만듭니다. .pbix 파일을 가져옵니다. 보완 대시보드 만들기  |  | 파트너로 등록 |
| **2개** |  |  | 테스트 패키지 만들기 및 내부 유효성 검사 실행        |  | |
| **3개** | |  | 테스트 패키지를 Power BI 테넌트 외부의 유효성 검사를 위한 사전 프로덕션으로 승격하고 AppSource에 제출합니다.  |  | 사전 프로덕션 패키지를 사용하여 Power BI 템플릿 앱 제안을 만들고 유효성 검사 프로세스를 시작합니다. |
| **4개** | |  | 사전 프로덕션 패키지를 프로덕션으로 승격 |  | 라이브로 전환 |

## <a name="before-you-begin"></a>시작하기 전에

템플릿 앱을 만들려면 템플릿 앱을 만들 수 있는 권한이 있어야 합니다. 자세한 내용은 Power BI 관리 포털, 템플릿 앱 설정을 참조하세요. 

템플릿 앱을 Power BI 서비스 및 AppSource에 게시하려면 [Cloud Marketplace 게시자가 되기](https://docs.microsoft.com/azure/marketplace/become-publisher) 위한 요구 사항을 충족해야 합니다.
 
## <a name="high-level-steps"></a>대략적인 단계

대략적인 단계는 다음과 같습니다. 

1. [요구 사항을 검토](#requirements)하여 충족하는지 확인합니다. 

1. Power BI Desktop에서 보고서를 빌드합니다. 매개 변수를 사용하여 다른 사람이 사용할 수 있는 파일로 저장할 수 있습니다. 

1. Power BI 서비스(app.powerbi.com)에서 테넌트의 템플릿 앱을 위한 작업 영역을 만듭니다. 

1. .pbix 파일을 가져오고 대시보드와 같은 콘텐츠를 앱에 추가합니다. 

1. 조직 내에서 직접 템플릿 앱을 테스트하기 위한 테스트 패키지를 만듭니다. 

1. 테스트 앱을 사전 프로덕션으로 승격하여 AppSource에서 유효성 검사를 위한 앱을 제출하고, 자신의 테넌트 외부에서 테스트합니다. 

1. 게시를 위해 클라우드 파트너 플랫폼에 콘텐츠를 제출합니다. 

1. 제안을 AppSource에서 '라이브'로 이동하고 Power BI에서 앱을 프로덕션으로 이동합니다.
2. 이제 사전 프로덕션의 동일한 작업 영역에서 다음 버전 개발을 시작할 수 있습니다. 

## <a name="requirements"></a>요구 사항

템플릿 앱을 만들려면 템플릿 앱을 만들 수 있는 권한이 있어야 합니다. 자세한 내용은 Power BI [관리 포털, 템플릿 앱 설정](service-admin-portal.md#template-apps-settings)을 참조하세요. 

템플릿 앱을 Power BI 서비스 및 AppSource에 게시하려면 [Cloud Marketplace 게시자가 되기](https://docs.microsoft.com/azure/marketplace/become-publisher) 위한 요구 사항을 충족해야 합니다.
 > [!NOTE] 
 > 템플릿 앱 제출은 [Cloud 파트너 포털](https://cloudpartner.azure.com)에서 관리합니다. 동일한 Microsoft 개발자 센터 등록 계정을 사용하여 로그인합니다. AppSource 제품에는 Microsoft 계정이 하나만 있어야 합니다. 계정은 개별 서비스나 제품에 특정되어서는 안됩니다.

## <a name="tips"></a>팁 

- 클릭 한 번으로 모든 사람이 시작할 수 있도록 앱에 샘플 데이터가 포함되어 있는지 확인합니다. 
- 테넌트 및 보조 테넌트에 설치하여 애플리케이션을 신중하게 검사합니다. 표시한 것만을 고객이 볼 수 있도록 합니다. 
- 온라인 상점으로 AppSource를 사용하여 애플리케이션을 호스트합니다. 이러한 방식으로 Power BI를 사용하는 모든 사용자가 앱을 찾을 수 있습니다. 
- 별도의 고유한 시나리오에 대해 둘 이상의 템플릿 앱을 제공하는 것을 고려하세요. 
- 예를 들어 설치 관리자에 의한 사용자 지정 연결 및 매개 변수 구성을 지원하는 데이터 사용자 지정을 활성화합니다.

자세한 제안 사항은 [Power BI에서 템플릿 앱 작성 팁](service-template-apps-tips.md)을 참조하세요.

## <a name="support"></a>지원
개발 중 지원을 받으려면 [https://powerbi.microsoft.com/support](https://powerbi.microsoft.com/support)를 사용하세요. 이 사이트를 적극적으로 모니터링하고 관리합니다. 고객 인시던트에서 해당 팀에 연락하는 방법을 신속하게 찾을 수 있습니다.

## <a name="next-steps"></a>다음 단계

[템플릿 앱 만들기](service-template-apps-create.md)
