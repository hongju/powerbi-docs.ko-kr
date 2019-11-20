---
title: 동적 바인딩
description: 동적 바인딩을 사용하여 보고서를 포함하는 방법을 알아봅니다.
author: KesemSharabi
ms.author: kesharab
manager: rkarlin
ms.topic: conceptual
ms.service: powerbi
ms.subservice: powerbi-developer
ms.date: 09/25/2019
ms.openlocfilehash: 8b42b397f726e492eda80a99eb730c215eb17ccb
ms.sourcegitcommit: 23ad768020a9daf129f69a462a2d46d59d2349d2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72776240"
---
# <a name="dynamic-binding"></a>동적 바인딩

동적 바인딩을 사용하면 보고서를 포함하는 동안 데이터 세트를 동적으로 선택할 수 있습니다. 보고서와 데이터 세트가 동일한 작업 영역에 있지 않아도 됩니다. 선택한 데이터 세트에 따라 최종 사용자에게 다른 결과가 표시됩니다.

두 작업 영역(보고서가 포함된 작업 영역과 데이터 세트가 포함된 작업 영역)을 용량에 모두 할당해야 합니다.

동적 바인딩을 사용하여 보고서를 포함하는 과정은 다음 두 단계로 이루어집니다.
1. 토큰 생성
2. 구성 개체 조정

## <a name="generating-a-token"></a>토큰 생성
토큰을 생성하려면 [여러 항목의 포함 토큰을 생성하기 위한 API](embed-sample-for-customers.md#multiEmbedToken)를 사용합니다.

동적 바인딩은 ‘조직에 대해 포함’ 및 ‘고객에 대해 포함’의 두 가지 포함 시나리오에서 모두 지원됩니다.

| 솔루션                   | 토큰                               | 요구 사항                                                                                                                                                  |
|---------------------------------|-------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ‘조직에 대해 포함’ | Power BI 사용자의 액세스 토큰     | 사용하는 Azure AD 토큰의 사용자에게 모든 아티팩트에 대한 적절한 권한이 있어야 합니다.                                                                    |
| ‘고객에 대해 포함’    | 비 Power BI 사용자의 액세스 토큰 | 보고서와 동적으로 바인딩된 데이터 세트에 대한 사용 권한을 모두 포함해야 합니다. 새 API를 사용하여 여러 아티팩트를 지원하는 포함 토큰을 생성합니다. |

## <a name="adjusting-the-config-object"></a>구성 개체 조정
구성 개체에 `datasetBinding`을 추가합니다. 페이지 맨 아래에 있는 예제를 참조로 사용합니다.

Power BI의 포함 기능을 처음 사용하는 경우, 다음 자습서를 검토하여 Power BI 콘텐츠를 포함하는 방법을 알아보세요.
* [고객의 애플리케이션에 Power BI 콘텐츠 포함](embed-sample-for-customers.md)
* [자습서: 조직의 애플리케이션에 Power BI 콘텐츠 포함](embed-sample-for-your-organization.md)

 ### <a name="example"></a>예제
```javascript
var config = {
    type: 'report',
    tokenType: models.TokenType.Embed,
    accessToken: accessToken,
    embedUrl: embedUrl,
    id: "reportId", // The wanted report id
    permissions: permissions,

    /////////////////////////////////////////////
    // Adjustment required for dynamic binding //
    datasetBinding: {
        datasetId: "notOriginalDatasetId",  // </The wanted dataset id
    }
    // End of dynamic binding adjustment            //
    /////////////////////////////////////////////
};

// Get a reference to the embedded report HTML element
var embedContainer = $('#embedContainer')[0];

// Embed the report and display it within the div container
var report = powerbi.embed(embedContainer, config);
```