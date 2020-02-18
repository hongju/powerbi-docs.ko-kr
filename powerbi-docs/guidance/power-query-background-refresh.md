---
title: 파워 쿼리 백그라운드 새로 고침 사용 안 함
description: 파워 쿼리 백그라운드 새로 고침을 사용하지 않도록 설정하는 경우에 대한 지침입니다.
author: peter-myers
manager: asaxton
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 09/26/2019
ms.author: v-pemyer
ms.openlocfilehash: 59cb62a9186da03a265fc3a8711d7275c3772af3
ms.sourcegitcommit: ef9ab7c0d84b926094c33e8aa2765cd43b844314
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/03/2020
ms.locfileid: "75623064"
---
# <a name="disable-power-query-background-refresh"></a>파워 쿼리 백그라운드 새로 고침 사용 안 함

이 문서에서는 Power BI Desktop을 사용하는 가져오기 데이터 모델러를 대상으로 합니다.

기본적으로 파워 쿼리는 데이터를 가져올 때 각 쿼리에 대해 최대 1000행의 미리 보기 데이터를 캐시합니다. 미리 보기 데이터는 원본 데이터 및 각 쿼리 단계의 변환 결과 미리 보기를 빠르게 표시하는 데 도움이 됩니다. Power BI Desktop 파일에 포함되지 않고 디스크에 별도로 저장됩니다.

그러나 Power BI Desktop 파일에 많은 쿼리가 포함된 경우 미리 보기 데이터를 검색하고 저장하면 새로 고침을 완료하는 데 걸리는 시간이 늘어날 수 있습니다.

## <a name="recommendation"></a>권장 사항

‘백그라운드에서’ 미리 보기 캐시를 업데이트하도록 Power BI Desktop 파일을 설정하면 새로 고침 속도가 빨라집니다.  사용하도록 설정하려면 Power BI Desktop에서 ‘파일 > 옵션 및 설정 > 옵션’을 선택하고 ‘데이터 로드’ 페이지를 선택한 다음,   **백그라운드에서 데이터 미리 보기를 다운로드하도록 허용** 옵션을 켭니다. 이 옵션은 현재 파일에 대해서만 설정할 수 있습니다.

![Power BI Desktop 백그라운드 데이터 옵션](media/power-query-background-refresh/power-query-options-background-data.png)

백그라운드 새로 고침을 사용하도록 설정하면 미리 보기 데이터가 만료될 수 있습니다. 만료되면 Power Query 편집기에서 다음 경고를 표시하여 알려줍니다.

![오래된 미리 보기 데이터에 대한 Power Query 편집기 경고](media/power-query-background-refresh/power-query-preview-data-old.png)

언제든지 미리 보기 캐시를 업데이트할 수 있습니다. **미리 보기 새로 고침** 명령을 사용하여 단일 쿼리 또는 모든 쿼리에 대해 업데이트할 수 있습니다. 이 명령은 Power Query 편집기 창의 **홈** 리본에 있습니다.

![미리 보기 데이터를 새로 고치는 Power Query 편집기 명령](media/power-query-background-refresh/power-query-refresh-preview-data.png)

## <a name="next-steps"></a>다음 단계

이 문서와 관련된 보다 자세한 내용을 알아보려면 다음 리소스를 참조하세요.

- [파워 쿼리 문서](/power-query/)
- 궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](https://community.powerbi.com/)
