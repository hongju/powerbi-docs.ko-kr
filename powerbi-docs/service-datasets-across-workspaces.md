---
title: 작업 영역의 데이터 세트 소개(미리 보기)
description: 조직 전체의 사용자와 데이터 세트를 공유하는 방법을 알아봅니다. 그런 다음, 자신의 작업 영역에서 데이터 세트를 기반으로 보고서를 빌드할 수 있습니다.
author: maggiesMSFT
ms.reviewer: chbraun
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 10/01/2019
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: d30a8012161934ada4ff3cb2ce6852fe62f48892
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2019
ms.locfileid: "73877190"
---
# <a name="intro-to-datasets-across-workspaces-preview"></a>작업 영역의 데이터 세트 소개(미리 보기)

비즈니스 인텔리전스는 협력적인 작업입니다. '진실의 원천'이 될 수 있는 표준화된 데이터 세트를 확립하는 것이 중요합니다. 이러한 표준화된 데이터 세트를 발견하고 다시 사용하는 것이 중요합니다. 조직의 전문가 데이터 모델러가 최적화된 데이터 세트를 만들고 공유할 때 보고서 작성자는 이러한 데이터 세트를 시작하여 정확한 보고서를 빌드할 수 있습니다. 그러면 조직은 의사 결정을 위한 일관된 데이터와 정상 데이터 문화를 얻을 수 있습니다.

![공유 데이터 세트 선택](media/service-datasets-across-workspaces/power-bi-select-shared-dataset.png)

Power BI에서 데이터 세트 작성자는 [빌드 권한](service-datasets-build-permissions.md)을 사용하여 해당 데이터에 액세스할 수 있는 사용자를 제어할 수 있습니다. 데이터 세트 작성자는 다른 사람이 데이터 세트를 검색할 수 있도록 데이터 세트를 ‘인증’ 또는 ‘승격’할 수도 있습니다.   이렇게 하면 보고서 작성자는 어느 데이터 세트가 공식적이고 품질이 높은지 알 수 있으며, Power BI에서 보고서를 작성할 때 해당 데이터 세트를 사용할 수 있습니다. 테넌트 관리자는 [작업 영역에서 데이터 세트 사용을 제어](service-datasets-admin-across-workspaces.md)하도록 새 테넌트 설정을 사용합니다.

## <a name="dataset-sharing-and-the-new-workspace-experience"></a>데이터 세트 공유 및 새 작업 영역 환경

여러 작업 영역의 데이터 세트를 기반으로 보고서를 빌드하고 보고서를 다른 작업 영역에 복사하는 작업은 [새 작업 영역 환경](service-create-the-new-workspaces.md)과 밀접하게 결합되어 있습니다.

- 이 서비스의 새 작업 영역 환경에서 데이터 세트 카탈로그를 열면 데이터 세트 카탈로그에 내 작업 영역 및 새 작업 영역 환경 내에 있는 데이터 세트가 표시됩니다. 
- 클래식 작업 영역에서 데이터 세트 카탈로그를 열면 해당 작업 영역의 데이터 세트만 볼 수 있고 다른 작업 영역의 데이터 세트는 표시되지 않습니다.
- Power BI Desktop에서 데이터 세트가 새 환경 작업 영역에 있는 한, Live Connect 보고서를 다른 작업 영역에 게시할 수 있습니다.
- 작업 영역 간에 보고서를 복사할 때 대상 작업 영역은 새 환경 작업 영역이어야 합니다.

## <a name="discover-datasets-preview"></a>데이터 세트 검색(미리 보기)

기존 데이터 세트를 토대로 보고서를 작성하는 경우 첫 번째 단계는 Power BI 서비스 또는 Power BI Desktop에서 해당 데이터 세트에 연결하는 것입니다. [다른 작업 영역에서 데이터 세트 검색(미리 보기)](service-datasets-discover-across-workspaces.md)에 대해 읽어 보세요.

## <a name="copy-a-report"></a>보고서 복사

작업 영역이나 앱에서 원하는 보고서를 찾으면 복사본을 만든 다음, 필요에 맞게 수정할 수 있습니다. 데이터 모델 만들기에 대해 걱정할 필요가 없습니다. 사용자를 위해 이미 생성되어 있습니다. 그리고 기존 보고서를 수정하는 것이 처음부터 시작하는 것보다 훨씬 쉽습니다. [보고서 복사](service-datasets-copy-reports.md)에 대해 자세히 알아봅니다.

## <a name="build-permission-for-datasets"></a>데이터 세트 빌드 권한

데이터 세트 작성자는 빌드 권한 유형을 사용하여 조직에서 데이터 세트를 토대로 새 콘텐츠를 작성할 수 있는 사람을 결정할 수 있습니다. 빌드 권한이 있는 사용자는 Excel에서 분석, XMLA 및 내보내기를 통해 Excel 시트와 같은 Power BI 외부의 데이터 세트를 토대로 새 콘텐츠를 작성할 수도 있습니다. [빌드 권한](service-datasets-build-permissions.md)에 대해 자세히 알아봅니다.

## <a name="promotion-and-certification"></a>승격 및 인증

데이터 세트를 만드는 경우, 다른 사용자가 활용할 수 있는 데이터 세트를 만들 때는 [데이터 세트를 승격](service-datasets-promote.md)하여 데이터 세트의 간편한 검색을 지원할 수 있습니다. 조직의 전문가에게 [데이터 세트를 인증](service-datasets-certify.md)하도록 요청할 수도 있습니다.

## <a name="licensing"></a>라이선싱

공유 데이터 세트 기능을 기반으로 빌드된 특정 기능과 환경은 기존 시나리오에 따라 라이선스가 부여됩니다. 예:

- 일반적으로 공유 데이터 세트를 검색하고 연결하는 기능은 누구나 사용할 수 있습니다. 프리미엄으로 제한되는 기능이 아닙니다.
- Pro 라이선스가 없는 사용자는 해당 데이터 세트가 사용자의 내 작업 영역 또는 프리미엄 지원 작업 영역에 있는 경우 보고서 작성을 위해 작업 영역에서 데이터 세트를 사용할 수 있습니다. Power BI Desktop 또는 Power BI 서비스에서 보고서를 작성하든 관계없이 동일한 라이선스 제한이 적용됩니다.
- 작업 영역 간에 보고서를 복사하려면 Pro 라이선스가 필요합니다.
- 앱에서 보고서를 복사하려면 조직 콘텐츠 팩에 필요한 것과 같은 Pro 라이선스가 필요합니다.
- 데이터 세트를 승격 및 인증하려면 Pro 라이선스가 필요합니다.

## <a name="considerations-and-limitations"></a>고려 사항 및 제한 사항

- 앱 게시자는 대상 그룹이 작업 영역 외부의 데이터 세트에 액세스할 수 있는지 확인해야 합니다. 그렇지 않으면 사용자가 앱과 상호 작용할 때 문제가 발생할 수 있습니다. 데이터 세트 액세스 권한이 없으면 보고서가 열리지 않으며 대시보드 타일이 잠금 상태로 표시됩니다. 또한 탐색의 첫 번째 항목이 데이터 세트 액세스 권한이 없는 보고서인 경우 사용자가 앱을 열 수 없습니다.
- 다른 작업 영역에서 데이터 세트 위에 보고서를 빌드하려면 양 끝에 새 작업 영역 환경이 있어야 합니다. 보고서는 새 작업 영역 환경에 있어야 하고 데이터 세트도 새 작업 영역 환경에 있어야 합니다.
- 클래식 작업 영역에서 데이터 세트 검색 환경은 해당 작업 영역의 데이터 세트만 보여줍니다.
- 의도적으로, 공유 데이터 세트를 기반으로 하는 보고서의 경우 “웹에 게시”가 작동하지 않습니다.
- 두 사람이 공유 데이터 세트에 액세스하는 작업 영역의 멤버인 경우, 둘 중 한명만 작업 영역에서 관련 데이터 세트를 볼 수 있습니다. 데이터 세트에 대한 읽기 이상의 액세스 권한이 있는 사용자만 공유 데이터 세트를 볼 수 있습니다. 

## <a name="next-steps"></a>다음 단계

- [데이터 세트 승격](service-datasets-promote.md)
- [데이터 세트 인증](service-datasets-certify.md)
- [작업 영역에서 데이터 세트 사용 제어](service-datasets-admin-across-workspaces.md)
- 궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](https://community.powerbi.com/)
