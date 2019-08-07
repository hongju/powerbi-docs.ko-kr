---
title: 시각적 개체 상호 작용
description: Power BI 시각적 개체에서 시각적 상호 작용을 허용해야 하는지 확인하는 방법
author: shaym83
ms.author: shaym
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 739e59c6da3c1e464e0462a928bc4f33ea0d01f8
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/23/2019
ms.locfileid: "68424496"
---
# <a name="visuals-interactions"></a>시각적 개체 상호 작용

시각적 개체는 시각적 상호 작용을 허용해야 하는지 여부를 나타내는 ‘allowInteractions’ 플래그의 값을 쿼리할 수 있습니다.
예를 들어 보고서를 보거나 편집하는 중에는 시각적 개체가 대화형이지만, 대시보드에서 볼 때는 대화형이 아닙니다.
이러한 상호 작용에는 클릭, 이동, 확대/축소, 선택 등이 있습니다.
이 플래그와 관계없이 모든 시나리오에서 도구 설명을 사용하도록 설정해야 합니다.

‘allowInteractions’ 플래그는 IVisualHost 인터페이스의 멤버로, 시각적 개체를 초기화하는 중에 부울로 전달됩니다.

대화형이 아닌 시각적 개체(예: 대시보드 타일)가 필요한 Power BI 시나리오에서는 ‘allowInteractions’ 플래그가 false로 설정됩니다.
그렇지 않으면(예: 보고서) ‘allowInteractions’가 true로 설정됩니다.

자세한 내용은 [SampleBarChart 시각적 개체 리포지토리](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/59a47935d8f5272ce145fe804193599ddb7e2001)를 참조하세요.

```typescript
   ...
   let allowInteractions = options.host.allowInteractions;
   bars.on('click', function(d) {
       if (allowInteractions) {
           selectionManager.select(d.selectionId);
           ...
       }
   });
```
