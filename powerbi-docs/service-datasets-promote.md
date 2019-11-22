---
title: 데이터 세트 승격(미리 보기) - Power BI
description: 데이터 세트를 승격하고 엔터프라이즈 사용자를 신뢰할 수 있는 고품질 데이터 세트로 안내하는 방법을 알아봅니다.
author: maggiesMSFT
ms.reviewer: chbraun
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 07/03/2019
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: 379249ac50f61df07c4adaffe53e0df29a311086
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2019
ms.locfileid: "73877125"
---
# <a name="promote-your-dataset-preview"></a>데이터 세트 승격(미리 보기)

이제 Power BI 보고서 작성자는 다양한 데이터 세트에 액세스할 수 있으므로 엔터프라이즈는 신뢰할 수 있는 고품질 데이터 세트로 안내해야 합니다. Power BI에서는 데이터 세트를 *보증*하는 두 가지 방법을 제공합니다.

- **승격**: 데이터 세트 소유자는 광범위한 사용 준비가 되면 사용자 고유의 데이터 세트를 승격할 수 있습니다. 쓰기 권한이 있는 모든 작업 영역 멤버는 데이터 세트를 승격할 수 있습니다. 데이터 세트를 승격할 수 있는 사용자에 대한 제한은 없습니다. 승격은 조직 내에서 데이터 세트의 협업 확산을 지원합니다. 이 문서는 데이터 세트를 승격하는 방법에 대한 것입니다.
- **인증**: 승격된 데이터 세트에 대한 인증을 요청할 수 있습니다. **데이터 세트 인증** 테넌트 관리자 설정에 정의된 선택된 사용자 그룹이 인증할 데이터 세트를 결정합니다. 세부 정보는 [데이터 세트 인증(미리 보기)](service-datasets-certify.md)을 참조하세요.

## <a name="promote-a-dataset"></a>데이터 세트 승격

승격할 준비가 되면 데이터 세트는 Power BI 서비스의 새 작업 영역 환경 작업 영역에 있어야 합니다.

1. 작업 영역의 데이터 세트 목록으로 이동합니다.
 
1. **추가 옵션**(...)을 선택한 다음, **설정**을 선택합니다.

    ![데이터 세트별로 줄임표를 선택합니다.](media/service-datasets-certify-promote/power-bi-dataset-settings.png)

1. **보증**을 확장하여 > **승격됨**을 선택합니다.

    ![승격 및 적용 선택](media/service-datasets-certify-promote/power-bi-dataset-promoted-endorsement.png)

1. **적용**을 선택합니다.

## <a name="request-dataset-certification"></a>데이터 세트 인증 요청

테넌트 관리자가 데이터 세트를 인증할 수 있는 조직의 사용자를 식별했습니다. 데이터 세트를 인증하도록 요청할 수 있습니다.

1. 데이터 세트가 있는 작업 영역에 대한 인증자 멤버 권한을 제공해야 합니다.

1. **설정**의 **보증** 섹션에서 **인증됨**이 회색으로 표시됩니다.

1. **자세히 알아보기** 링크를 선택합니다.

    Power BI 테넌트 관리자는 **자세히 알아보기** 링크를 구성하여 테넌트의 인증 프로세스에 대한 세부 정보가 포함된 지정된 위치로 이동할 수 있습니다.   **자세히 알아보기** 링크를 사용자 지정하지 않은 경우 기본적으로 [데이터 세트 인증](service-datasets-certify.md) 문서를 가리킵니다.

## <a name="next-steps"></a>다음 단계

* [작업 영역에서 데이터 세트 사용](service-datasets-across-workspaces.md)에 대해 읽어보세요.
* 궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](https://community.powerbi.com/)
