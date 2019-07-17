---
title: 다른 작업 영역의 데이터 세트를 기반으로 보고서 생성(미리 보기) - Power BI
description: 조직 전체의 사용자와 데이터 세트를 공유하는 방법을 알아봅니다. 그런 다음, 자신의 작업 영역에서 데이터 세트를 기반으로 보고서를 빌드할 수 있습니다.
author: maggiesMSFT
manager: kfile
ms.reviewer: chbraun
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 07/03/2019
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: f8229c74a233d8bc44370380bf635527506194f0
ms.sourcegitcommit: b439ded53bfbbb58be27ecedf93d618f5158df33
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/04/2019
ms.locfileid: "67567452"
---
# <a name="create-reports-based-on-datasets-from-different-workspaces-preview"></a>다른 작업 영역의 데이터 세트를 기반으로 보고서 생성(미리 보기)

다른 작업 영역의 데이터 세트를 기반으로 사용자 고유의 작업 영역에서 보고서를 만드는 방법을 알아봅니다. 기존 데이터 세트 위에 보고서를 빌드하기 위해 Power BI Desktop 또는 Power BI 서비스, 내 작업 영역 또는 [새 작업 영역 환경](service-create-the-new-workspaces.md)에서 시작할 수 있습니다.

- Power BI 서비스에서 다음을 수행합니다. **데이터 가져오기** > **게시된 데이터 세트**.
- Power BI Desktop에서 다음을 수행합니다. **데이터 가져오기** > **Power BI 데이터 세트**.

    ![기존 데이터 세트에 연결](media/service-datasets-across-workspaces/power-bi-connect-dataset-pk.png)
   
두 경우 모두 데이터 세트 검색 환경은 **데이터 세트를 선택하여 보고서 만들기** 대화 상자에서 시작됩니다. 위치에 관계없이 액세스할 수 있는 모든 데이터 세트가 표시됩니다.

![데이터 세트 선택](media/service-datasets-across-workspaces/power-bi-select-dataset.png)

첫 번째 레이블이 **승격**으로 지정됩니다. 이 문서의 뒤부분에 [보증된 데이터 세트 찾기](#find-an-endorsed-dataset)에서 가져올 수 있습니다.

이 목록에 표시된 데이터 세트가 다음 조건 중 하나 이상을 충족하는지 확인합니다.

- 데이터 세트는 새 작업 영역 환경 작업 영역 중 하나이며 사용자는 해당 작업 영역의 멤버입니다. [고려 사항 및 제한 사항](service-datasets-across-workspaces.md#considerations-and-limitations)을 참조하세요.
- 새 작업 영역 환경 작업 영역에 있는 데이터 세트에 대한 빌드 권한이 있습니다.
- 데이터 세트가 내 작업 영역에 있습니다.

> [!NOTE]
> 무료 사용자인 경우 내 작업 영역의 데이터 세트 또는 프리미엄 용량 작업 영역에 있는 빌드 권한이 있는 데이터 세트만 볼 수 있습니다.

**만들기**를 클릭하면 데이터 세트에 대한 라이브 연결이 만들어지고 전체 데이터 세트가 사용 가능한 상태로 보고서 생성 환경이 열립니다. 데이터 세트의 복사본을 만들지 않았습니다. 데이터 세트는 여전히 원래 위치에 상주합니다. 데이터 세트의 모든 테이블과 측정값을 사용하여 사용자 고유의 보고서를 빌드할 수 있습니다. 데이터 세트에 대한 RLS(행 수준 보안) 제한이 적용되므로 RLS 역할에 따라 볼 수 있는 권한이 있는 데이터만 볼 수 있습니다.

보고서를 Power BI 서비스의 현재 작업 영역에 저장하거나 Power BI Desktop에서 작업 영역에 게시할 수 있습니다. 보고서가 작업 영역 외부의 데이터 세트를 기반으로 하는 경우 Power BI는 데이터 세트 목록에 항목을 자동으로 만듭니다. 이 데이터 세트의 아이콘은 작업 영역의 데이터 세트 아이콘과 다릅니다. ![공유 데이터 세트 아이콘](media/service-datasets-discover-across-workspaces/power-bi-shared-dataset-icon.png)

이렇게 하면 작업 영역의 멤버는 작업 영역 외부에 있는 데이터 세트를 사용하는 보고서와 대시보드를 식별할 수 있습니다. 이 항목에는 데이터 세트에 대한 정보와 몇 가지 선택된 작업이 표시됩니다.

![데이터 세트 작업](media/service-datasets-across-workspaces/power-bi-dataset-actions.png)

## <a name="find-an-endorsed-dataset"></a>보증된 데이터 세트 찾기

두 가지 종류의 보증된 데이터 세트가 있습니다. 데이터 세트 소유자는 사용자에게 권장하는 데이터 세트를 *승격*할 수 있습니다. Power BI 테넌트 관리자는 모든 사용자가 사용할 수 있도록 데이터 세트를 *인증*할 수 있는 조직의 전문가를 지정할 수 있습니다. 승격되고 인증된 데이터 세트는 모두 데이터 세트를 찾을 때 작업 영역의 데이터 세트 목록에서 볼 수 있는 *배지*를 표시합니다. 데이터 세트 검색 중에 데이터 세트를 인증한 사용자의 이름이 도구 설명에 표시됩니다. **인증됨** 레이블 위에 마우스를 갖다 대면 이름을 확인할 수 있습니다.

- Power BI 서비스에서 다음을 수행합니다. **데이터 가져오기** > **게시된 데이터 세트**.
- Power BI Desktop에서 다음을 수행합니다. **데이터 가져오기** > **Power BI 데이터 세트**.

    **데이터 세트 선택** 대화 상자에서 보증된 데이터 세트가 기본적으로 목록 상단에 있습니다. 

    ![승격된 데이터 세트](media/service-datasets-certify-promote/power-bi-dataset-promoted.png)

## <a name="next-steps"></a>다음 단계

- [작업 영역에서 데이터 세트 사용(미리 보기)](service-datasets-across-workspaces.md)
- 궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](http://community.powerbi.com/)
