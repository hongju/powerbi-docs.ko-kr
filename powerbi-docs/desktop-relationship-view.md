---
title: Power BI Desktop의 관계 보기
description: Power BI Desktop의 관계 보기
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Model your data
ms.openlocfilehash: a947b5c0b957336f02d3ec2e27d2bfd36b36c639
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "65514367"
---
# <a name="relationship-view-in-power-bi-desktop"></a>Power BI Desktop의 관계 보기
**관계 보기**는 모델의 모든 테이블, 열 및 관계를 표시합니다. 이는 모델이 여러 테이블 간의 복잡한 관계를 가지고 있는 경우 특히 유용합니다.

직접 살펴보겠습니다.

![](media/desktop-relationship-view/relationshipview_fullscreen.png)

**A.** 관계 보기 아이콘 – 관계 보기에서 모델을 표시하려면 클릭하십시오.

**B.** 관계 – 관계 위에 커서를 올려서 사용되는 열을 표시할 수 있습니다. 관계를 두 번 클릭하면 **관계 편집** 대화 상자가 열립니다. 

위 그림에서는 *StoreKey* 열이 있는 *Stores* 테이블이, 역시 *StoreKey* 열이 있는 *Sales* 테이블과 관련된 것을 볼 수 있습니다. 이것이 *다대일* ( \*:1) 관계임을 알 수 있으며, 선 가운데 있는 아이콘은 *모두*로 설정된 교차 필터 방향을 나타냅니다. 아이콘의 화살표는 필터 컨텍스트 흐름의 방향을 나타냅니다.

관계에 대한 자세한 내용은 [Power BI Desktop에서 관계 만들기 및 관리](desktop-create-and-manage-relationships.md)를 참조하세요.

