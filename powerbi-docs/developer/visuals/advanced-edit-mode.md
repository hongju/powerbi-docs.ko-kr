---
title: 고급 편집 모드
description: 고급 UI 컨트롤이 있는 Power BI 시각적 개체
author: shaym83
ms.author: shaym
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 625105aed773bce5cf70932f092faf60ea001c2c
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/23/2019
ms.locfileid: "68425554"
---
# <a name="advanced-edit-mode"></a>고급 편집 모드

고급 UI 컨트롤이 필요한 시각적 개체는 고급 편집 모드 지원을 선언할 수 있습니다.
지원되는 경우 보고서 편집 모드에서 `Edit` 단추가 시각적 개체의 메뉴에 표시됩니다.
`Edit` 단추를 클릭하면 EditMode가 `Advanced`로 설정됩니다.
시각적 개체는 EditMode 플래그를 사용하여 해당 UI 컨트롤이 표시되도록 결정할 수 있습니다.

기본적으로 시각적 개체는 고급 편집 모드를 지원하지 않습니다.
다른 동작이 필요한 경우 시각적 개체의 `capabilities.json` 파일에서 `advancedEditModeSupport` 속성을 설정하여 명시적으로 지정해야 합니다.

가능한 값은 다음과 같습니다.

- 0 - NotSupported

- 1 - SupportedNoAction

- 2 - SupportedInFocus

## <a name="entering-advanced-edit-mode"></a>고급 편집 모드 시작

다음과 같은 경우 `Edit` 단추가 표시됩니다.

 1 - capabilities.json에서 `advancedEditModeSupport` 속성이 `SupportedNoAction` 또는 `SupportedInFocus`로 설정되었습니다.

 2 - 시각적 개체가 보고서 편집 모드에서 표시되었습니다.

capabilities.json에 `advancedEditModeSupport` 속성이 없거나 `NotSupported`로 설정된 경우에는 ‘Edit’ 단추가 사라집니다.

![편집 모드 시작](./media/edit-mode.png)

사용자가 `Edit`를 클릭하면 시각적 개체는 EditMode가 `Advanced`로 설정된 update() 호출을 가져옵니다.
기능에 설정된 값에 따라 다음 작업이 수행됩니다.

* `SupportedNoAction` - 호스트에서 추가 작업을 수행하지 않습니다.
* `SupportedInFocus` - 호스트에서 시각적 개체를 포커스 모드로 표시합니다.

## <a name="exiting-advanced-edit-mode"></a>고급 편집 모드 종료

다음과 같은 경우 `Back to report` 단추가 표시됩니다.

1 - capabilities.json에서 `advancedEditModeSupport` 속성이 `SupportedInFocus`로 설정되었습니다.
