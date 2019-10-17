---
title: 다른 작업 영역에서 보고서 복사(미리 보기) - Power BI
description: 조직 전체의 사용자와 데이터 세트를 공유하는 방법을 알아봅니다. 그런 다음, 자신의 작업 영역에서 데이터 세트를 기반으로 보고서를 빌드할 수 있습니다.
author: maggiesMSFT
manager: kfile
ms.reviewer: chbraun
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 08/12/2019
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: c60c3c29bbf87d7a5e18838dac0baa6157de6437
ms.sourcegitcommit: 5e277dae93832d10033defb2a9e85ecaa8ffb8ec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2019
ms.locfileid: "72020832"
---
# <a name="copy-reports-from-other-workspaces-preview"></a>다른 작업 영역에서 보고서 복사(미리 보기)

작업 영역이나 앱에서 원하는 보고서를 찾은 경우, 복사본을 만들고 다른 작업 영역에 저장할 수 있습니다. 그런 다음, 시각적 개체 및 기타 요소를 추가하거나 삭제하여 보고서의 복사본을 수정할 수 있습니다. 데이터 모델 만들기에 대해 걱정할 필요가 없습니다. 사용자를 위해 이미 생성되어 있습니다. 그리고 기존 보고서를 수정하는 것이 처음부터 시작하는 것보다 훨씬 쉽습니다. 그러나 새 작업 영역에서 앱을 만들 때 앱에 보고서 복사본을 게시할 수 없는 경우도 있습니다. 자세한 내용은 [“작업 영역에서 데이터 세트 사용” 문서의 고려 사항 및 제한 사항](service-datasets-across-workspaces.md#considerations-and-limitations)을 참조하세요.

> [!NOTE]
> 복사본을 만들려면, 원본 보고서가 프리미엄 용량의 작업 영역에 있는 경우에도 Pro 라이선스가 필요합니다.

## <a name="save-a-copy-of-a-report"></a>보고서 복사본 저장

1. 앱 또는 작업 영역에서 보고서 목록 보기로 이동합니다.

1. **작업**에서 **복사본 저장**을 선택합니다.

    ![보고서 복사본 저장](media/service-datasets-copy-reports/power-bi-dataset-save-report-copy.png)

    보고서가 새 환경 작업 영역에 있고 [빌드 권한](service-datasets-build-permissions.md)을 가지고 있는 경우에만 **복사본 저장** 아이콘이 표시됩니다. 작업 영역에 대한 액세스 권한이 있더라도 데이터 세트에 대한 빌드 권한이 있어야 합니다.

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

## <a name="delete-a-report-and-its-shared-dataset"></a>보고서 및 관련 공유 데이터 세트 삭제

작업 영역에서 보고서와 관련 공유 데이터 세트가 더 이상 필요하지 않아질 수 있습니다.

1. 보고서를 삭제합니다. 작업 영역의 보고서 목록에서 **삭제** 아이콘을 선택합니다.

    ![보고서 삭제 아이콘](media/service-datasets-across-workspaces/power-bi-datasets-delete-report.png)

2. 데이터 세트 목록에서, 공유 데이터 세트에 **삭제** 아이콘이 없는 것을 볼 수 있습니다. 페이지를 새로 고치거나 다른 페이지로 이동한 다음 다시 돌아옵니다. 이렇게 하면 데이터 세트가 사라진 것을 볼 수 있습니다. 사라지지 않았다면 **관련 항목 보기**를 확인합니다. 데이터 세트가 작업 영역의 다른 테이블과 관련이 있을 수 있습니다.

    ![상위 메뉴 모음에서 관련 항목 보기 아이콘을](media/service-datasets-across-workspaces/power-bi-dataset-view-related-icon.png)

    > [!NOTE]
    > 이 작업 영역에서 공유 데이터 세트를 삭제하면 데이터 세트 자체가 삭제되는 것이 아니라 데이터 세트에 대한 참조가 삭제되는 것입니다.


## <a name="next-steps"></a>다음 단계

- [작업 영역에서 데이터 세트 사용(미리 보기)](service-datasets-across-workspaces.md)
- 궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](http://community.powerbi.com/)
