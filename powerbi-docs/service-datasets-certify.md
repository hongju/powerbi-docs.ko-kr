---
title: 데이터 세트 인증(미리 보기) - Power BI 인증
description: 엔터프라이즈 사용자를 신뢰할 수 있는 고품질 데이터 세트로 안내하는 방법을 알아봅니다.
author: maggiesMSFT
manager: kfile
ms.reviewer: chbraun
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/31/2019
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: e790afee5b57b73a756ca3c1afd564b00e778186
ms.sourcegitcommit: 7c426a5209d4fdd1360fc3d0442d57991be1984d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/03/2019
ms.locfileid: "66461330"
---
# <a name="certify-datasets-preview"></a>데이터 세트 인증(미리 보기)

조직은 중요한 정보의 신뢰할 수 있는 소스인 데이터 세트를 인증할 수 있습니다. 이러한 데이터 세트는 보고서 디자이너가 보고서를 작성하고 신뢰할 수 있는 데이터를 찾기 시작할 때 두드러지게 나타납니다. 인증은 가장 중요한 데이터 세트만 인증 받을 수 있는 매우 선택적인 프로세스일 수 있습니다. Power BI 테넌트 관리자는 새로운 설정을 통해 데이터 세트를 인증할 수 있는 사용자를 엄격하게 제어할 수 있습니다. 따라서 관리자는 데이터 세트 인증을 통해 조직 전반에 걸쳐 사용할 수 있도록 설계된 진정으로 안정적이고 신뢰할 수 있는 데이터 세트를 만들 수 있습니다.

이제 Power BI 사용자는 다양한 데이터 세트에 액세스할 수 있으므로 엔터프라이즈는 신뢰할 수 있는 고품질 데이터 세트로 안내해야 합니다. Power BI에서는 데이터 세트를 *보증*하는 두 가지 방법을 제공합니다.

- **프로모션**: 데이터 세트 소유자는 광범위한 사용 준비가 되면 자신의 데이터 세트를 승격할 수 있습니다. 세부 정보는 [데이터 세트 승격](service-datasets-promote.md)을 참조하세요. 
- **인증**: 데이터 세트 소유자는 승격된 데이터 세트의 인증을 요청할 수 있습니다. **데이터 세트 인증** 테넌트 관리자 설정에 정의된 선택된 사용자 그룹이 인증할 데이터 세트를 결정합니다.

## <a name="certify-a-dataset"></a>데이터 세트 인증

테넌트 관리자는 **Endorsement** 설정 페이지에서 **자세히 알아보기** 링크에 대한 URL을 제공할 수 있습니다.  인증 프로세스에 대한 설명서에 연결할 수 있습니다. **자세히 알아보기** 링크의 대상을 제공하지 않은 경우 기본적으로 이 문서를 가리킵니다.

![데이터 세트 인증 자세히 알아보기](media/service-datasets-certify-promote/power-bi-dataset-learn-more-certification.png)

데이터 세트를 인증할 수 있는 사람을 지명하는 것은 분명히 큰 책임입니다. 데이터 세트 작성자가 데이터 세트 인증에 대해 연락하는 경우 이는 검색 프로세스의 시작입니다. 데이터 세트의 인증이 만족스러우면 마지막 단계를 따릅니다.

1. 데이터 세트 소유자는 데이터 세트가 있는 작업 영역에 대한 멤버 권한을 제공해야 합니다.
1. 테넌트 관리자가 데이터 세트를 인증할 수 사람으로 지명한 경우 데이터 세트에 대한 **설정**의 **Endorsement** 섹션에 있는 **인증** 옵션을 사용할 수 있습니다. **인증**을 선택합니다.
1. **적용**을 선택합니다.

테넌트 관리자 [작업 영역에서 데이터 세트 사용을 제어](service-datasets-admin-across-workspaces.md)하는 방법에 대해 자세히 알아봅니다.

## <a name="next-steps"></a>다음 단계

* [작업 영역에서 데이터 세트 사용](service-datasets-across-workspaces.md)에 대해 읽어보세요.
* 궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](http://community.powerbi.com/)
