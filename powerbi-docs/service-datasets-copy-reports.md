---
title: 다른 작업 영역에서 보고서 복사(미리 보기) - Power BI
description: 조직 전체의 사용자와 데이터 세트를 공유하는 방법을 알아봅니다. 그런 다음, 자신의 작업 영역에서 데이터 세트를 기반으로 보고서를 빌드할 수 있습니다.
author: maggiesMSFT
manager: kfile
ms.reviewer: chbraun
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/31/2019
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: 507af4de9d57d2d54fe3e28bca8b1aff7da5cf30
ms.sourcegitcommit: 7c426a5209d4fdd1360fc3d0442d57991be1984d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/03/2019
ms.locfileid: "66461468"
---
# <a name="copy-reports-from-other-workspaces-preview"></a>다른 작업 영역에서 보고서 복사(미리 보기)

한 작업 영역에서 보고서를 복사하여 다른 작업 영역에 저장하는 방법에 대해 알아봅니다. 그런 다음, 시각적 개체 및 기타 요소를 추가하거나 삭제하여 해당 보고서를 수정할 수 있습니다.

작업 영역이나 앱에서 원하는 보고서를 찾으면 복사본을 만든 다음, 필요에 맞게 수정할 수 있습니다. 데이터 모델 만들기에 대해 걱정할 필요가 없습니다. 사용자를 위해 이미 생성되어 있습니다. 그리고 기존 보고서를 수정하는 것이 처음부터 시작하는 것보다 훨씬 쉽습니다.

## <a name="save-a-copy-of-a-report"></a>보고서 복사본 저장

1. 앱 또는 작업 영역에서 보고서 목록 보기로 이동합니다.

1. **작업**에서 **복사본 저장**을 선택합니다.

    ![보고서 복사본 저장](media/service-datasets-copy-reports/power-bi-dataset-save-report-copy.png)

    보고서가 새 작업 영역에 있고 [빌드 권한**을 가지고 있는 경우에만** 복사본 저장](service-datasets-build-permissions.md#build-permissions-for-shared-datasets) 아이콘이 표시됩니다. 작업 영역에 대한 액세스 권한이 있더라도 데이터 세트에 대한 별도 권한이 있어야 합니다.

3. **이 보고서의 복사본 저장**에서 보고서 이름을 지정하고 대상 작업 영역을 선택합니다.

    ![복사 대화 상자 저장](media/service-datasets-copy-reports/power-bi-dataset-save-report.png)

    보고서를 현재 작업 영역이나 Power BI 서비스의 다른 작업 영역에 저장할 수 있습니다. 자신이 멤버로 있는 새 환경 작업 영역인 작업 영역만 볼 수 있습니다.
  
4. **저장**을 선택합니다.

    보고서 복사본을 저장할 때 데이터 세트에 대한 라이브 연결이 만들어지고 사용 가능한 전체 데이터 세트로 보고서 생성 환경을 열 수 있습니다. 데이터 세트의 복사본을 만들지 않았습니다. 데이터 세트는 여전히 원래 위치에 상주합니다. 데이터 세트의 모든 테이블과 측정값을 사용자 고유의 보고서에서 사용할 수 있습니다. 데이터 세트에 대한 RLS(행 수준 보안) 제한이 적용되므로 RLS 역할에 따라 볼 수 있는 권한이 있는 데이터만 볼 수 있습니다.

    보고서가 작업 영역 외부의 데이터 세트를 기반으로 하는 경우 Power BI는 데이터 세트 목록에 항목을 자동으로 만듭니다. 이 데이터 세트의 아이콘은 작업 영역의 데이터 세트 아이콘과 다릅니다. ![공유 데이터 세트 아이콘](media/service-datasets-discover-across-workspaces/power-bi-shared-dataset-icon.png)


    이렇게 하면 작업 영역의 멤버는 작업 영역 외부에 있는 데이터 세트를 사용하는 보고서와 대시보드를 식별할 수 있습니다. 이 항목에는 데이터 세트에 대한 정보와 몇 가지 선택된 작업이 표시됩니다.

    ![데이터 세트 작업](media/service-datasets-across-workspaces/power-bi-dataset-actions.png)

## <a name="view-related-datasets"></a>관련 데이터 세트 보기

작업 영역에 보고서가 있을 때 기반이 되는 데이터 세트를 알아야 할 수 있습니다.

1. 보고서 목록 보기에서 **관련 항목 보기**를 선택합니다.

    ![상위 메뉴 모음에서 관련 항목 보기 아이콘을](media/service-datasets-copy-reports/power-bi-dataset-view-related.png)

1. **관련 콘텐츠** 대화 상자에 모든 관련 항목이 표시됩니다. 이 목록에서 데이터 세트는 다른 것처럼 보입니다. 다른 작업 영역에 있는지 알 수 없습니다. 이 문제는 알려져 있습니다.
 
    ![관련 콘텐츠 대화 상자](media/service-datasets-copy-reports/power-bi-dataset-related.png)


## <a name="next-steps"></a>다음 단계

- [작업 영역에서 데이터 세트 사용(미리 보기)](service-datasets-across-workspaces.md)
- 궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](http://community.powerbi.com/)
