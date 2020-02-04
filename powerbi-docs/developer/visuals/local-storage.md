---
title: Power BI 시각적 개체의 로컬 스토리지 API
description: 이 문서에서는 Power BI 시각적 개체 API를 사용하여 브라우저 로컬 스토리지에 액세스하는 방법을 설명합니다.
author: uve
ms.author: v-grniki
ms.reviewer: KesemSharabi
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 01/21/2019
ms.openlocfilehash: 85517fcd7ec773f947135614c94c0c4e4638ea48
ms.sourcegitcommit: 02342150eeab52b13a37b7725900eaf84de912bc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2020
ms.locfileid: "76539328"
---
# <a name="local-storage-api"></a>로컬 스토리지 API

로컬 스토리지 API는 사용자 지정 시각적 개체가 디바이스 스토리지에서 데이터를 로드하거나 저장하도록 호스트에 요청하는 데 사용할 수 있는 API입니다. 이 API는 서로 다른 시각적 개체 유형 간에 스토리지 액세스가 구분된다는 점에서 격리되어 있습니다.

## <a name="sample"></a>샘플

업데이트 메서드를 호출할 때마다 사용자 지정 시각적 개체가 일부 카운터를 늘려야 하지만, 시각적 개체를 시작할 때마다 카운터 값이 초기화되지 않고 유지되어야 하는 경우의 코드는 다음과 같습니다.

```typescript
export class Visual implements IVisual {
        // ...
        private updateCountName: string = 'updateCount';
        private updateCount: number;
        private storage: ILocalVisualStorageService;
        // ...

        constructor(options: VisualConstructorOptions) {
            // ...
            this.storage = options.host.storageService;
            // ...

            this.storage.get(this.updateCountName).then(count =>
            {
                this.updateCount = +count;
            })
            .catch(() =>
            {
                this.updateCount = 0;
                this.storage.set(this.updateCountName, this.updateCount.toString());
            });
            // ...
        }

        public update(options: VisualUpdateOptions) {
            // ...
            this.updateCount++;
            this.storage.set(this.updateCountName, this.updateCount.toString());
            // ...
        }
}
```

## <a name="known-limitations-and-issues"></a>알려진 제한 사항 및 문제

로컬 스토리지 API는 사용자 지정 시각적 개체에 대해 기본적으로 활성화되지 않습니다. 사용자 지정 시각적 개체에 대해 활성화하려면 Power BI 사용자 지정 시각적 개체 지원(`pbicvsupport@microsoft.com`)에 요청을 보내세요.  
**시각적 개체는 [AppSource](https://appsource.microsoft.com/en-us/marketplace/apps?product=power-bi-visuals)에서 사용할 수 있어야 하며 [인증](https://powerbi.microsoft.com/en-us/documentation/powerbi-custom-visuals-certified/)되어야 합니다.**
