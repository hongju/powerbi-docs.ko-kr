---
title: Power BI 시각적 개체의 시각적 상호 작용
description: 이 문서에서는 Power BI 시각적 개체가 시각적 상호 작용을 허용해야 하는지 여부를 확인하는 방법을 설명합니다.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: b8b1a1a59ee9fae5a1c248548a14c5f91438edc9
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2019
ms.locfileid: "73875530"
---
# <a name="visual-interactions-in-power-bi-visuals"></a>Power BI 시각적 개체의 시각적 상호 작용

시각적 개체는 시각적 상호 작용을 허용해야 하는지 여부를 나타내는 `allowInteractions` 플래그의 값을 쿼리할 수 있습니다. 예를 들어 보고서를 보거나 편집하는 중에는 시각적 개체가 대화형이지만, 대시보드에서 볼 때는 대화형이 아닙니다. 이러한 상호 작용에는 ‘클릭’, ‘이동’, ’확대/축소’, ’선택’ 등이 있습니다.     

> [!NOTE]
> 표시되는 플래그에 관계없이 모든 시나리오에서 도구 설명을 사용하도록 설정해야 합니다.

`allowInteractions` 플래그는 IVisualHost 인터페이스의 멤버로, 시각적 개체 초기화 중에 부울로 전달됩니다.

대화형이 아닌 시각적 개체(예: 대시보드 타일)가 필요한 Power BI 시나리오에서는 `allowInteractions` 플래그가 `false`로 설정됩니다. 그렇지 않으면(예: 보고서) `allowInteractions`가 `true`로 설정됩니다.

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
