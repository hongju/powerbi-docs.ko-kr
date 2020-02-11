---
title: 페이지를 매긴 보고서의 URL 매개 변수 - Power BI 보고서 작성기
description: 이 토픽에서는 Power BI 보고서 작성기 보고서 매개 변수의 일반적인 용도와 설정할 수 있는 속성 등에 대해 설명합니다.
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
author: maggiesMSFT
ms.author: maggies
ms.reviewer: cfinlan
ms.custom: ''
ms.date: 09/10/2019
ms.openlocfilehash: 35df214da19d5f35130408ce8128643f52682428
ms.sourcegitcommit: df8bcc65f0df69bf1fc1d47eb06575742eac1622
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2020
ms.locfileid: "75953785"
---
# <a name="url-parameters-in-paginated-reports-in-power-bi"></a>Power BI에서 페이지를 매긴 보고서의 URL 매개 변수

URL에 매개 변수를 추가하여 Power BI에서 페이지를 매긴 보고서에 명령을 보낼 수 있습니다. 예를 들어, 특정 보고서 매개 변수 값을 사용하여 보고서를 보았을 수 있습니다. 미리 정의된 URL 액세스 매개 변수를 사용하여 이 정보를 URL에 캡슐화합니다. 형식을 렌더링하거나 보고서 도구 모음의 모양과 느낌을 바꾸기 위한 매개 변수를 포함하여 Power BI에서 보고서를 처리하는 방법을 추가로 사용자 지정할 수 있습니다. 그런 다음, 이 URL을 메일이나 웹 페이지에 직접 붙여넣어 다른 사용자의 브라우저에서도 같은 방식으로 보고서를 표시할 수 있습니다. 

URL 액세스 매개 변수를 통해 수행할 수 있는 작업은 다음과 같습니다. 

- 보고서에 보고서 매개 변수를 보냅니다. 
- 지원되는 파일 형식으로 보고서 내용을 내보내기 시작합니다. 
- 매개 변수 창을 숨기거나 표시합니다. 
- DeviceInfo 설정을 지정합니다. 

URL 액세스를 통해 사용할 수 있는 명령 및 설정의 전체 목록은 이 문서 뒷부분에 나오는  [URL 액세스 매개 변수 참조](#url-access-parameter-reference)를 참조하세요. 

## <a name="url-access-concepts"></a>URL 액세스 개념 

Power BI에 대한 URL 요청은 서비스에서 처리하는 매개 변수를 포함합니다. 서비스에서 URL 요청을 처리하는 방법은 매개 변수, 매개 변수 접두사, URL에 포함된 항목의 형식에 따라 달라집니다. 페이지를 매긴 보고서 URL 기능은 표준 URL 주소 지정을 지원하는 대부분의 브라우저 및 애플리케이션과 호환됩니다. 

## <a name="url-access-syntax"></a>URL 액세스 구문 

URL 요청에는 임의의 순서로 나열된 여러 매개 변수가 포함될 수 있습니다. 매개 변수는 앰퍼샌드(&)로 구분됩니다. 이름 및 값 쌍은 등호(=)로 구분됩니다. 다음은 그 예입니다.

```
powerbiserviceurl?rp:parametervalueh&rdl:parameter=value  
```

## <a name="syntax-description"></a>구문 설명 

### <a name="powerbiserviceurl"></a>powerbiserviceurl 

Power BI 테넌트의 웹 서비스 URL입니다. 다음은 그 예입니다. 

**&** URL 액세스 매개 변수의 이름 및 값 쌍을 구분하는 데 사용됩니다.

**prefix** Power BI 서비스의 동작을 지정하는 URL 매개 변수의 접두사(예:  rp: or rdl:)입니다. 

> [!NOTE]
> 보고서 매개 변수는 매개 변수 접두사가 필요하며 대/소문자를 구분합니다. 

**parameter** 매개 변수 이름입니다. 

### <a name="value"></a>value 

사용 중인 매개 변수의 값에 해당하는 URL 텍스트입니다. 

URL에 보고서 매개 변수를 전달하는 예는  [URL에 보고서 매개 변수 전달](report-builder-url-pass-parameters.md)을 참조하세요.

## <a name="url-access-parameter-reference"></a>URL 액세스 매개 변수 참조

다음 매개 변수를 URL의 일부로 사용하여 Power BI에서 페이지를 매긴 보고서의 모양과 느낌을 구성할 수 있습니다. 가장 일반적인 매개 변수는 이 섹션에 나와 있습니다. 매개 변수는 대/소문자를 구분하지 않고 출력 형식과 연관된 매개 변수 prefix `rdl:` if로 시작됩니다.  

### <a name="report-commands-rdl"></a>보고서 명령(`rdl:`) 

**내보내기 형식** 보고서를 렌더링하고 내보낼 형식을 지정합니다. 사용 가능한 값은 다음과 같습니다.
 
- PPTX(PowerPoint)
- MHTML 
- IMAGE 
- EXCELOPENXML(EXCEL) 
- WORDOPENXML(WORD) 
- CSV 
- PDF 
- XML 

**장치 정보** 다음 내보내기 형식에 대한 추가 출력 매개 변수를 지정할 수 있습니다. 

PDF:

- rdl:AccessiblePDF=true/false
- rdl:Columns=integer
- rdl:ColumnSpacing=decimal(in)
- rdl:DpiX=integer
- rdl:DpiY=integer
- rdl:EndPage=integer
- rdl:HumanReadablePDF=true/false
- rdl:MarginBottom=decimal(in)
- rdl:MarginLeft=decimal(in)
- rdl:MarginRight=decimal(in)
- rdl:MarginTop=decimal(in)
- rdl:PageHeight=decimal(in)
- rdl:PageWidth=decimal(in)
    - rdl:StartPage=integer
    
CSV:

- rdl:Encoding=string
- rdl:ExcelMode=true/false
- rdl:FieldDelimiter=string
- rdl:FileExtension=string
- rdl:NoHeader=true/false
- rdl:Qualifier=string
- rdl:RecordDelimiter=string
- rdl:SuppressLineBreaks=true/false
    - rdl:UseFormattedValues=true/false
    
WORDOPENXML (WORD):

- rdl:AutoFit=string -> True/False/Never/Default
- rdl:ExpandToggles=true/false
- rdl:FixedPageWidth=true/false
- rdl:OmitHyperlinks=true/false
- rdl:OmitDrillthroughs=true/false

EXCELOPENXML (EXCEL):

- rdl:OmitDocumentMap=true/false
- rdl:OmitFormulas=true/false
    - rdl:SimplePageHeaders=true/false
    
PPTX (PowerPoint):
 
- rdl:Columns=integer
- rdl:ColumnSpacing=decimal(in)
- rdl:DpiX=integer
- rdl:DpiY=integer
- rdl:EndPage=integer
- rdl:MarginBottom=decimal(in)
- rdl:MarginLeft=decimal(in)
- rdl:MarginRight=decimal(in)
- rdl:MarginTop=decimal(in)
- rdl:PageHeight=decimal(in)
- rdl:PageWidth=decimal(in)
- rdl:StartPage=integer
    - rdl:UseReportPageSize=true/false

XML:

- rdl:XSLT=string
- rdl:MIMEType=string
- rdl:UseFormattedValues=true/false
- rdl:Indented=true/false
- rdl:OmitNamespace=true/false
- rdl:OmitSchema=true/false
- rdl:Encoding=string
- rdl:FileExtension=string
- rdl:Schema=true/false

## <a name="next-steps"></a>다음 단계

- [Power BI에서 페이지를 매긴 보고서에 대한 URL에 보고서 매개 변수 전달](report-builder-url-pass-parameters.md)
- [Power BI Premium에서 페이지를 매긴 보고서란?](paginated-reports-report-builder-power-bi.md)
