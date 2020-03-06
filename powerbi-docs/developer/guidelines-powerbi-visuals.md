---
title: Power BI 시각적 개체에 대한 지침
description: 다른 사용자가 구매를 통해 검색하고 사용할 수 있도록 사용자 지정 시각적 개체를 Microsoft AppSource에 게시하는 방법을 알아봅니다.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.topic: conceptual
ms.subservice: powerbi-custom-visuals
ms.date: 07/16/2019
ms.openlocfilehash: 6bf7610a010a72248a3d2fdd96718eea513a68da
ms.sourcegitcommit: 8e3d53cf971853c32eff4531d2d3cdb725a199af
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "75000092"
---
# <a name="guidelines-for-power-bi-visuals"></a>Power BI 시각적 개체에 대한 지침
다른 사용자가 검색하고 사용하도록 Microsoft AppSource에 Power BI 시각적 개체를 [게시](https://docs.microsoft.com/power-bi/developer/office-store)하기 전에 지침에 따라 사용자에게 적합한 환경을 만들어야 합니다.

## <a name="power-bi-visuals-with-additional-purchases"></a>추가 구매 조건이 있는 Power BI 시각적 개체

Marketplace(Microsoft AppSource)에 무료로 제공되는 Power BI 시각적 개체를 제출할 수 있습니다. "추가 구매가 필요할 수도 있음" 가격표가 있는 Microsoft AppSource Power BI 시각적 개체에 제출할 수도 있습니다. “추가 구매가 필요할 수도 있음” Power BI 시각적 개체는 Office 스토어의 IAP(앱에서 바로 구매) 추가 기능과 유사합니다. 

무료 Power BI 시각적 개체와 마찬가지로, IAP Power BI 시각적 개체도 인증할 수 있습니다. 인증을 위해 IAP Power BI 시각적 개체를 제출하기 전에 [인증 요구 사항](../power-bi-custom-visuals-certified.md)을 준수하는지 확인합니다. 

### <a name="what-is-a-power-bi-visual-with-iap-features"></a>IAP 기능이 포함된 Power BI 시각적 개체란?

IAP Power BI 시각적 개체는 *무료 기능*을 제공하는 *무료* 시각적 개체입니다. 추가 요금이 부과될 수 있는 일부 고급 기능도 포함되어 있습니다. Power BI 시각적 개체의 설명에서 개발자는 작동을 위해 추가 구매가 필요한 기능이 있으면 사용자에게 알려야 합니다. 현재 Microsoft는 앱 및 추가 기능 구매를 지원하는 네이티브 API를 제공하지 않습니다.

개발자는 이러한 구매를 위해 타사 결제 시스템을 사용할 수 있습니다. 자세한 내용은 [our store policy](https://docs.microsoft.com/office/dev/store/validation-policies#2-apps-or-add-ins-can-display-certain-ads)(스토어 정책)를 참조하세요.


>[!IMPORTANT]  
> 무료 Power BI 시각적 개체를 "추가 구매가 필요할 수 있음"으로 업데이트하는 경우, 사용자는 업데이트 전과 동일한 수준의 무료 기능을 받아야 합니다. 기존 무료 기능 외에도 선택적 고급 유료 기능을 추가할 수 있습니다.

### <a name="watermarks"></a>워터마크

고객이 비용을 지불하지 않고 IAP 고급 기능을 계속 사용하도록 워터마크를 사용할 수 있습니다. 

워터마크는 구매하기 전에 Power BI 시각적 개체의 전체 기능을 보여주기 위해 사용할 수 있습니다. 

* 워터마크는 유효한 라이선스 없이 사용되는 유료 기능에만 사용할 수 있습니다.
* *무료* 가격표가 있는 Power BI 시각적 개체에는 워터마크를 사용할 수 없습니다.
* 사용자가 무료 기능을 사용하는 경우 IAP 시각적 개체에는 워터마크를 사용할 수 없습니다. 

### <a name="pop-up-window"></a>팝업 창

Power BI IAP 시각적 개체에서 잘못된(또는 만료된) 라이선스를 사용하는 경우, 팝업 창을 사용하여 라이선스를 구매하는 방법을 설명할 수 있습니다.

### <a name="submission-process"></a>제출 프로세스

[제출 프로세스](office-store.md#submitting-to-appsource)를 수행한 후 *제품 설정* 탭으로 이동하여 *내 제품에 서비스 구매가 필요합니다* 확인란을 선택합니다.

Power BI 시각적 개체가 유효성이 검사되고 승인되면 IAP Power BI 시각적 개체의 Microsoft AppSource 목록이 가격 옵션 아래에 "추가 구매가 필요할 수도 있음"이라고 표시됩니다.

>[!NOTE]
>이미 [판매자 대시보드](https://docs.microsoft.com/office/dev/store/use-the-seller-dashboard-to-submit-to-the-office-store)를 사용하여 Power BI 시각적 개체를 제출한 상태에서 IAP 기능을 추가하려는 경우 판매자 대시보드 메모에 "앱 내 구매 조건이 있는 시각적 개체"를 작성해야 합니다. 또한 유효성 검사 팀이 IAP 기능의 유효성을 검사할 수 있도록 라이선스 키 또는 토큰을 제공해야 합니다.

## <a name="context-menu"></a>상황에 맞는 메뉴
상황에 맞는 메뉴는 사용자가 시각적 개체를 가리킬 때 표시되는 마우스 오른쪽 클릭 메뉴입니다.
모든 Power BI 시각적 개체를 통해 상황에 맞는 메뉴에서 통합된 환경을 제공할 수 있습니다. 상황에 맞는 메뉴를 추가하는 방법에 대해 알아보려면 [이 문서](https://github.com/Microsoft/PowerBI-visuals/blob/gh-pages/tutorials/building-bar-chart/adding-context-menu-to-the-bar.md)를 확인하세요.

## <a name="commercial-logo"></a>상업용 로고
이 섹션에서는 상업용 로고를 Power BI 시각적 개체에 추가하는 방법을 설명합니다. 상업용 로고는 필수가 아닙니다. 추가된 경우 다음 지침을 따라야 합니다.

> [!NOTE]
> * 이 문서에서 ‘상업용 로고’는 아래 그림에 설명된 대로 영리 회사 아이콘을 나타냅니다.
> * 이 문서에서는 Microsoft 상업용 로고는 예제로만 사용됩니다. Power BI 시각적 개체와 함께 자체 상업용 로고를 사용합니다.

> [!IMPORTANT]
> 상업용 로고는 *편집 모드에서만* 허용됩니다. 보기 모드에서는 상업용 로고를 표시할 수 *없습니다*.

### <a name="commercial-logo-type"></a>상업용 로고 유형

상업용 로고에는 다음 세 가지 유형이 있습니다.
* **로고** - 로고는 함께 사용되는 두 요소인 아이콘 및 이름으로 구성됩니다.

    ![Microsoft 로고](media/guidelines-powerbi-visuals/microsoft-logo.png)

* **기호** - 텍스트가 없는 그래픽입니다.

    ![Microsoft 기호](media/guidelines-powerbi-visuals/microsoft-symbol.png)

* **로고 형식** - 텍스트로만 구성되고 아이콘이 없는 로고입니다.

    ![Microsoft 기호](media/guidelines-powerbi-visuals/microsoft-logotype.png)

### <a name="commercial-logo-color"></a>상업용 로고 색상

상업용 로고를 사용하는 경우, 로고 색상은 회색(16진수 색 #C8C8C8)이어야 합니다. 그라데이션 같은 효과를 상업용 로고에 추가하지 마세요.

* **로고**

    ![Microsoft 기호](media/guidelines-powerbi-visuals/grey-microsoft-logo.png)

* **기호** - 텍스트가 없는 그래픽입니다.

    ![Microsoft 기호](media/guidelines-powerbi-visuals/grey-microsoft-symbol.png)

* **로고 형식** - 텍스트로만 구성되고 아이콘이 없는 로고입니다.

    ![Microsoft 기호](media/guidelines-powerbi-visuals/grey-microsoft-logotype.png)

> [!TIP]
> * Power BI 시각적 개체에 그래픽이 포함되어 있는 경우 로고에 10px 여백이 있는 흰색 배경을 추가하는 것이 좋습니다.
> * 로고에 DropShadow(30% 불투명 검정)를 추가하는 것이 좋습니다.

### <a name="commercial-logo-size"></a>상업용 로고 크기

Power BI 시각적 개체에는 큰 타일과 작은 타일을 위한 두 개의 상업용 로고가 필요합니다. 위쪽 또는 아래쪽 오른쪽 모서리에 있는 경계 상자 내에 4px 여백을 사용하여 로고를 배치합니다.

다음 표에서는 Power BI 시각적 개체의 크기에 대한 고려 사항을 설명합니다.

|  |소형 Power BI 시각적 개체  |대형 Power BI 시각적 개체  |
|---------|---------|---------|
|*로고 너비*    |최대 240px         |240px보다 큼         |
|*로고 높이*     |최대 160px         |160px보다 큼         |
|*경계 상자 크기*     |40 x 15px         |101 x 30px         |
|*상업용 로고 예제*     |![Microsoft 기호](media/guidelines-powerbi-visuals/grey-microsoft-symbol.png)         |![Microsoft 로고](media/guidelines-powerbi-visuals/grey-microsoft-logo.png)         |
|*경계 상자 예*    |![작은 로고 예제](media/guidelines-powerbi-visuals/small-logo-box.png)         |![큰 로고 예제](media/guidelines-powerbi-visuals/big-logo-box.png)         |
|    |         |         |

### <a name="commercial-logo-behavior"></a>상업용 로고 동작

상업용 로고는 편집 모드에서만 허용됩니다. 이 단추를 클릭하면 상업용 로고에 다음 기능만 포함할 수 있습니다.

* 상업용 로고를 클릭하면 웹 사이트로 리디렉션됩니다.

* 상업용 로고를 클릭하면 추가 정보를 포함하는 팝업 창이 열립니다. 팝업 창은 다음과 같은 두 개의 섹션으로 구분되어야 합니다.
    * 상업용 로고, 시각적 개체 및 시장 등급을 포함할 수 있는 마케팅 영역입니다.
    * 정보 및 링크를 포함할 수 있는 정보 영역입니다.    


### <a name="things-to-avoid"></a>피해야 할 사항

* 보기 모드에서는 상업용 로고를 표시할 수 없습니다.

* 애니메이션 효과가 있는 상업용 로고는 최대 5초 동안 애니메이션을 표시할 수 있습니다.

* Power BI 시각적 개체에 읽기 모드로 정보 아이콘(i)을 포함하는 경우, 위에 설명된 대로 상업용 로고의 색, 크기 및 위치를 준수해야 합니다.

* 컬러 또는 검정 상용 로고를 사용하지 마세요. 상업용 로고는 회색(16진수 색 #C8C8C8)이어야 합니다.

    ![인증되지 않은 컬러 로고](media/guidelines-powerbi-visuals/no-color-logo.png) ![인증되지 않은 검정 로고](media/guidelines-powerbi-visuals/black-logo.png)

* 그라데이션 또는 진한 그림자와 같은 효과가 적용된 상업용 로고입니다.

    ![인증되지 않은 로고 스타일](media/guidelines-powerbi-visuals/no-style-logo.png)

## <a name="best-practices"></a>모범 사례

Power BI 시각적 개체를 게시할 때 사용자에게 뛰어난 환경을 제공하기 위해 다음 권장 사항을 고려하세요.

### <a name="visual-landing-page"></a>시각적 개체 방문 페이지

방문 페이지를 사용하여 Power BI 시각적 개체를 사용할 수 있는 방법과 라이선스를 구매할 위치를 명확하게 표시합니다. 자동으로 트리거되는 비디오는 포함하지 마세요. 라이선스 구매 세부 사항에 관한 정보 또는 링크, IAP 기능을 사용하는 방법과 같이 사용자의 환경을 개선하는 데 도움이 되는 자료만 추가합니다.

### <a name="license-key-and-token"></a>라이선스 키 및 토큰

사용자 편의를 위해 형식 창의 맨 위에 있는 라이선스 키 또는 토큰 관련 필드를 추가합니다.

## <a name="faq"></a>FAQ

Power BI 시각적 개체에 대한 자세한 내용은 [Power BI 시각적 개체에 관한 자주 묻는 질문](https://docs.microsoft.com/power-bi/power-bi-custom-visuals-faq#visuals-with-additional-purchases)을 참조하세요.

## <a name="next-steps"></a>다음 단계

다른 사람이 검색하고 사용할 수 있도록 Power BI 시각적 개체를 [Microsoft AppSource](office-store.md)에 게시하는 방법을 알아봅니다.