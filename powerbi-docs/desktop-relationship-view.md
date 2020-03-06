---
title: Power BI Desktop의 모델 보기
description: Power BI Desktop의 모델 보기
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/17/2020
ms.author: davidi
LocalizationGroup: Model your data
ms.openlocfilehash: ea568c061142e66e79351de8a6c0f0603a46f775
ms.sourcegitcommit: 08f65ea314b547b41b51afef6876e56182190266
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2020
ms.locfileid: "76753231"
---
# <a name="work-with-model-view-in-power-bi-desktop"></a>Power BI Desktop의 모델 보기 작업

*모델 보기*는 모델의 모든 테이블, 열 및 관계를 표시합니다. 이 보기는 모델이 여러 테이블 간의 복잡한 관계를 가지고 있는 경우 특히 유용합니다.

창 옆에 있는 **모델** 아이콘을 선택하여 기존 모델의 보기를 표시합니다. 사용되는 열을 표시하려면 관계 선 위로 커서를 올려놓습니다.

![모델 보기, Power BI Desktop](media/desktop-relationship-view/model-view-full-screen.png)

그림에서는 *StoreKey* 열이 있는 *Stores* 테이블이, 역시 *StoreKey* 열이 있는 *Sales* 테이블과 관련된 것을 볼 수 있습니다. 두 테이블에는 *다 대 일*(\*: 1) 관계가 있습니다. 선 가운데에 있는 화살표는 필터 컨텍스트 흐름의 방향을 표시합니다. 이중 화살표는 교차 필터 방향이 *양쪽*으로 설정되었음을 의미합니다.

관계를 두 번 클릭하여 **관계 편집** 대화 상자를 열 수 있습니다. 관계에 대한 자세한 내용은 [Power BI Desktop에서 관계 만들기 및 관리](desktop-create-and-manage-relationships.md)를 참조하세요.
