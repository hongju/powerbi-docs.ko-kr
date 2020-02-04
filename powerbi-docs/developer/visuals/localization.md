---
title: Power BI 시각적 개체의 데이터 뷰 매핑 이해
description: 이 문서에서는 시각적 개체에 전달하기 전에 Power BI에서 데이터를 변환하는 방법을 설명합니다.
author: KesemSharabi
ms.author: kesharab
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: ad63a1b97c744e8614e584874c4d896a85598e48
ms.sourcegitcommit: 0cc594ebb78a6d0e88784673ed09f8aefd10c7a7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76819126"
---
# <a name="add-the-locale-in-power-bi-for-custom-visuals"></a>사용자 지정 시각적 개체에 대한 Power BI에 로캘 추가

시각적 개체는 Power BI 로캘을 검색하여 해당 콘텐츠를 관련 언어로 지역화할 수 있습니다.

[Power BI에 지원되는 언어 및 국가/지역](./../../supported-languages-countries-regions.md)에 대해 읽으세요.

예를 들어 샘플 가로 막대형 차트 시각적 개체의 로캘을 가져옵니다.

![샘플 가로 막대형 차트 시각적 개체의 지역화](media/locale-in-samplebarchart.png)

이 가로 막대형 차트는 각각 다른 로캘(영어, 바스크어 및 힌디어)에서 생성되고 도구 설명으로 표시됩니다.

> [!NOTE]
> 시각적 개체의 지역화 관리자는 API 1.10.0 이상에서 지원됩니다.

## <a name="get-the-locale"></a>로캘 가져오기

`locale`는 시각적 개체를 초기화하는 동안 문자열로 전달됩니다. Power BI에서 로캘이 변경되면 새 로캘과 함께 시각적 개체를 다시 생성합니다. SampleBarChart에서 로캘을 사용하여 전체 샘플 코드를 찾을 수 있습니다.

이제 BarChart 생성자에 호스트 로캘 인스턴스를 사용하여 생성자에서 인스턴스화된 로캘 멤버가 있습니다.

```typescript
private locale: string;
...
this.locale = options.host.locale;
```

지원되는 로캘:

로캘 문자열 | 언어
--------------|----------------------
ar-SA | لعربية(아랍어)
bg-BG | български(불가리아어)
ca-ES | català(카탈로니아어)
cs-CZ | čeština(체코)
da-DK | dansk(덴마크어)
de-DE | Deutsche(독일어)
el-GR | ελληνικά(그리스어)
en-US | English(영어)
es-ES | español 서비스(스페인어)
et-EE | eesti(에스토니아어)
eU-ES | Euskal(바스크어)
fi-FI | suomi(핀란드)
fr-FR | français(프랑스어)
gl-ES | galego(갈리시아어)
he-IL | עברית(히브리어)
hi-IN | हिन्दी(힌디어)
hr-HR | hrvatski(크로아티아어)
hu-HU | magyar(헝가리어)
id-ID | Bahasa Indonesia(인도네시아어)
it-IT | italiano(이탈리아어)
ja-JP | 日本の(일본어)
kk-KZ | Қазақ(카자흐어)
ko-KR | 한국의(한국어)
lt-LT | Lietuvos(리투아니아어)
lv-LV | Latvijas(라트비아어)
ms-MY | Bahasa Melayu(말레이시아어)
nb-NO | norsk(노르웨이어)
nl-NL | Nederlands(네덜란드어)
pl-PL | polski(폴란드어)
pt-BR | português(포르투갈어)
pt-PT | português(포르투갈어)
ro-RO | românesc(루마니아어)
ru-RU | русский(러시아어)
sk-SK | slovenský(슬로바키아어)
sl-SI | slovenski(슬로베니아어)
sr-Cyrl-RS | српски(세르비아어)
sr-Latn-RS | srpski(세르비아어)
sv-SE | svenc(스웨덴어)
th-TH | ไ ท ย(태국어)
tr-TR | Türk(터키어)
uk-UA | український(우크라이나어)
vi-VN | t Việt(베트남어)
zh-CN | 中 国(중국어 간체)
zh-TW | 中國(중국어-Tranditional)

> [!NOTE]
> PowerBI Desktop에서 로캘 속성은 설치된 PowerBI Desktop의 언어를 포함합니다.

## <a name="localizing-the-property-pane-for-custom-visuals"></a>사용자 지정 시각적 개체의 속성 창 지역화

속성 창의 필드를 지역화하여 일관된 통합 환경을 제공할 수 있습니다. 이를 통해 사용자 지정 시각적 개체가 다른 Power BI 핵심 시각적 개체처럼 작동합니다.

예를 들어 `pbiviz new` 명령을 사용하여 만든 지역화되지 않은 사용자 지정 시각적 개체는 속성 창에서 다음 필드가 표시됩니다.

![속성 창의 지역화](media/property-pane.png)

범주 데이터와 측정값 데이터는 모두 `displayName`(으)로 capabilities.json 파일에 정의되어 있습니다.

## <a name="how-to-localize-capabilities"></a>기능을 지역화하는 방법

먼저 기능에서 지역화할 모든 표시 이름에 표시 이름 키를 추가합니다. 이 예제에서는 다음이 적용됩니다.

```json
{
    "dataRoles": [
        {
            "displayName": "Category Data",
            "displayNameKey": "VisualCategoryDataNameKey1",
            "name": "category",
            "kind": "Grouping"
        },
        {
            "displayName": "Measure Data",
            "displayNameKey": "VisualMeasureDataNameKey2",
            "name": "measure",
            "kind": "Measure"
        }
    ]
}
```

그런 다음 stringResources라는 디렉터리를 추가합니다. 디렉터리에는 시각적 개체에서 지원하는 로캘에 따라 다른 문자열 리소스 파일이 모두 포함됩니다. 이 디렉터리에서 지원하려는 모든 로캘에 대한 JSON 파일을 추가해야 합니다. 이 파일에는 바꾸려는 모든 displayNameKey의 로캘 정보 및 지역화된 문자열 값이 포함됩니다.

이 예제에서는 아랍어와 히브리어를 지원하려는 경우를 예로 들겠습니다. 다음과 같은 방법으로 두 개의 JSON 파일을 추가해야 합니다.

![문자열 리소스 폴더의 지역화 문자열](media/stringresources-files.png)

모든 JSON 파일은 원하는 표시 이름 키의 문자열 값을 사용하여 단일 로캘(이 파일은 위의 지원되는 목록에 있는 로캘 중 하나여야 함)을 정의합니다. 이 예제에서 히브리어 문자열 리소스 파일은 다음과 같이 표시됩니다.

```json
{
    "locale": "he-IL",
    "values": {
        "VisualCategoryDataNameKey1": "קטגוריה",
        "VisualMeasureDataNameKey2": "יחידות מידה"
    }
}
```

지역화 관리자를 사용하는 데 필요한 모든 단계는 아래에 설명되어 있습니다.

> [!NOTE]
> 현재는, 개발자 시각적 개체 디버깅에 대한 지역화가 지원되지 않습니다.

## <a name="setup-environment"></a>설정 환경

### <a name="desktop"></a>데스크톱

데스크톱 사용의 경우, https://powerbi.microsoft.com 에서 Power BI 데스크톱의 지역화된 버전을 다운로드합니다.

### <a name="web-service"></a>웹 서비스

서비스에서 웹 클라이언트(브라우저)를 사용하는 경우 설정에서 언어를 변경합니다.

![웹 서비스의 지역화](media/webservice-settings.png)

## <a name="resource-file"></a>리소스 파일

stringResources 폴더에서 사용할 로캘로 이름이 지정된 폴더에 resources.resjson 파일을 추가합니다. 이 예제의 경우 en-US 및 ru-RU입니다.

![새 resjson 파일](media/new-resjson.png)

그런 다음, 이전 단계에서 추가한 resources.resjson 파일에 사용할 모든 지역화 문자열을 추가합니다.

```json
{
    ...
    "Role_Legend": "Обозначения",
    "Role_task": "Задача",
    "Role_StartDate": "Дата начала",
    "Role_Duration": "Длительность"
    ...
}
```

이 샘플은 resources.resjson 파일의 en-US 버전입니다.

```json
{
    ...
    "Role_Legend": "Legend",
    "Role_task": "Task",
    "Role_StartDate": "Start date",
    "Role_Duration": "Duration"
    ...
}
```

새 localizationManager 인스턴스는 다음과 같이 시각적 개체의 localizationManager 인스턴스를 만듭니다.

```typescript
private localizationManager: ILocalizationManager;

constructor(options: VisualConstructorOptions) {
    this.localizationManager = options.host.createLocalizationManager();
}
```

## <a name="localizationmanager-usage-sample"></a>localizationManager 사용 샘플

이제 resources.resjson에서 정의한 문자열 키 인수로 지역화 관리자의 getDisplayName 함수를 호출하여 코드 내부에서 필요한 문자열을 가져올 수 있습니다.

```typescript
let legend: string = this.localization.getDisplayName("Role_Legend");
```

en-US의 경우 "Legend"를 반환하고, ru-RU의 경우 "Обозначения"를 반환합니다.

## <a name="next-steps"></a>다음 단계

* [서식 지정 유틸리티을 사용하여 지역화된 형식을 제공하는 방법 읽기](utils-formatting.md)
