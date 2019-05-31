---
title: 추가적인 진단 정보 캡처
description: 이 지침에서는 Power BI 웹 클라이언트에서 추가적인 진단 정보를 수동으로 수집하기 위한 두 가지 가능한 옵션을 제공합니다.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/25/2019
ms.author: mblythe
ms.custom: seodec18
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 710fb4cdcf9efb051434966d47c2eaced17ac9ba
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "65100198"
---
# <a name="capture-additional-diagnostic-information-for-power-bi"></a>Power BI에 대 한 추가 진단 정보 캡처

이 문서에서는 수동으로 Power BI 웹 클라이언트에서 추가적인 진단 정보를 수집 하기 위한 지침을 제공 합니다.

1. 이동할 [Power BI](https://app.powerbi.com) Microsoft Edge 또는 Internet Explorer를 사용 하 여 합니다.

1. 키를 눌러 **F12** Microsoft Edge 개발자 도구를 엽니다.

   ![Microsoft Edge 개발자 스크린 샷 도구 요소 탭입니다.](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-developer-tools.png)

1. **네트워크** 탭을 선택합니다. 이미 캡처한 트래픽을 나열합니다.

   ![Microsoft Edge 개발자 스크린 샷 도구 네트워크 탭입니다.](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab.png)

    다음을 할 수 있습니다.

    * 창 내에서 찾아 발생할 수 있는 문제를 재현 합니다.

    * 표시 / 숨기기 개발자 도구 창 세션 중 언제 든 지 F12 키를 눌러 합니다.

1. 세션 프로 파일링을 중지 하려면에 빨간색 사각형을 선택할 수는 **네트워크** 개발자 탭 도구 영역입니다.

   ![중지 단추에서 호출 하 여 Microsoft Edge 개발자 스크린 샷 도구 네트워크 탭 합니다.](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab-stop.png)

1. HTTP 보관 (HAR) 파일로 데이터를 내보내려면 디스켓 아이콘을 선택 합니다.

   ![디스켓 아이콘의 설명선이 있는 Microsoft Edge 개발자 스크린 샷 도구 네트워크 탭 합니다.](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab-save.png)

1. 파일 이름을 제공하고 HAR 파일을 저장합니다.

    HAR 파일 브라우저 창과 Power BI 포함 사이의 네트워크 요청에 대 한 모든 정보가 포함 됩니다.

    * 각 요청에 대 한 작업 Id입니다.

    * 각 요청에 대 한 정확한 타임 스탬프입니다.

    * 오류 정보가 클라이언트에 반환 합니다.

    이 추적에는 화면에 표시되는 시각 효과를 입력하기 위해 사용된 데이터도 포함됩니다.

1. HAR 파일을 제공하여 검토를 지원할 수 있습니다.

궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](http://community.powerbi.com/)
