---
title: Power BI 보고서 작성기의 식
description: 식은 Power BI 페이지를 매긴 보고서 작성기 페이지를 매긴 보고서에서 데이터에 대한 검색, 계산, 표시, 그룹화, 정렬, 필터링, 매개 변수화 및 형식을 지정하는 데 널리 사용됩니다.
ms.date: 06/06/2019
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.assetid: 76d3ac86-650c-46fe-8086-8b3edcea3882
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: d3a72fd967eeb24cfa1093d16c4434447d5fc89d
ms.sourcegitcommit: 797bb40f691384cb1b23dd08c1634f672b4a82bb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/12/2019
ms.locfileid: "66840628"
---
# <a name="expressions-in-power-bi-report-builder"></a>Power BI 보고서 작성기의 식
  식은 Power BI 페이지를 매긴 보고서 작성기 페이지를 매긴 보고서에서 데이터에 대한 검색, 계산, 표시, 그룹화, 정렬, 필터링, 매개 변수화 및 형식을 지정하는 데 널리 사용됩니다. 
  
  많은 보고서 항목 속성을 식으로 설정할 수 있습니다. 식을 통해 보고서의 콘텐츠, 디자인 및 대화형 작업을 제어할 수 있습니다. 식은 Microsoft Visual Basic으로 작성되고 보고서 정의에 저장되며 보고서를 실행할 때 보고서 처리기에서 평가됩니다.  
  
 워크시트에서 데이터를 직접 사용하는 Microsoft Office Excel과 같은 애플리케이션과 달리 보고서에서는 데이터에 대한 자리 표시자인 식을 사용합니다. 평가된 식의 실제 데이터를 보려면 보고서를 미리봐야 합니다. 보고서를 실행하면 보고서 처리기는 보고서 데이터와 테이블 및 차트와 같은 보고서 레이아웃 요소를 결합하여 각각의 식을 평가합니다.  
  
 보고서를 디자인할 때 보고서 항목에 대해 많은 식이 설정되어 있습니다. 예를 들어, 필드를 데이터 창에서 보고서 디자인 화면의 테이블 셀로 끌어오면 텍스트 상자 값이 필드에 대한 단순 식으로 설정됩니다. 다음 그림의 보고서 데이터 창에는 데이터 세트 필드 ID, Name, SalesTerritory, Code 및 Sales가 보입니다. 테이블에 [Name], [Code] 및 [Sales]라는 세 가지 필드가 추가되었습니다. 디자인 화면의 [Name] 표기는 기본 식 `=Fields!Name.Value`를 나타냅니다.  
  
![보고서 작성기 디자인 뷰](media/report-builder-expressions/report-builder-data-design-preview.png)
  
 보고서를 미리 보는 경우, 보고서 처리기는 테이블 데이터 영역과 데이터 연결의 실제 데이터를 결합하고 결과 집합의 모든 행에 대해 테이블의 행을 표시합니다.  
  
 식을 수동으로 입력하려면 디자인 화면에서 항목을 선택하고 바로 가기 메뉴와 대화 상자를 사용하여 항목에 대한 속성을 설정합니다. 드롭다운 목록에 `<Expression>` 값이나 ***(fx)*** 단추가 보이면 속성을 식으로 설정할 수 있습니다. 
  
##  <a name="Types"></a> 단순 및 복합 식 이해  
 식은 등호(=)로 시작하며 Microsoft Visual Basic으로 작성됩니다. 식에는 상수, 연산자 및 기본 제공 값(필드, 컬렉션 및 함수)과 외부 또는 사용자 지정 코드에 대한 참조가 포함될 수 있습니다.  
  
 식을 사용하여 여러 보고서 항목 속성 값을 지정할 수 있습니다. 가장 일반적인 속성은 텍스트 상자 및 자리 표시자 텍스트에 대한 값입니다. 일반적으로 텍스트 상자에 식이 하나만 있으면 해당 식은 텍스트 상자 속성의 값입니다. 텍스트 상자에 여러 식이 있으면 각 식은 텍스트 상자의 자리 표시자 텍스트에 대한 값입니다.  
  
 기본적으로 식은 보고서 디자인 화면에 *단순* 또는 *복합 식*으로 나타납니다.  
  
-   **단순** 단순 식은 데이터 세트 필드, 매개 변수 또는 기본 제공 필드와 같은 기본 제공 컬렉션의 단일 항목에 대한 참조를 포함합니다. 디자인 화면에서 단순 식은 대괄호 안에 있습니다. 예를 들어, `[FieldName]`은 기본 식 `=Fields!FieldName.Value`에 해당합니다. 기본 식은 보고서 레이아웃을 만들고 보고서 데이터 창에서 디자인 화면으로 항목을 끌어서 놓으면 자동으로 생성됩니다. 다양한 기본 제공 컬렉션을 나타내는 기호에 대한 자세한 내용은 [단순 식에 대한 접두사 기호 이해](#DisplayText)를 참조하세요.  
  
-   **복합** 복합 식은 기본 제공되는 여러 참조, 연산자 및 함수 호출에 대한 참조를 포함합니다. 복합 식은 식 값에 단순 참조 이상이 포함되면 <\<Expr>>로 나타납니다. 식을 보려면 마우스로 식을 가리키고 툴팁을 사용합니다. 식을 편집하려면 **식** 대화 상자에서 엽니다.  
  
 다음 그림은 텍스트 상자와 자리 표시자 텍스트에 대한 전형적인 단순 및 복합 식을 보여줍니다.  
  
![보고서 작성기 식 기본 형식](media/report-builder-expressions/report-builder-expression-default-format.png) 
  
 식에 텍스트 대신 샘플 값을 표시하려면 텍스트 상자 또는 자리 표시자 텍스트에 서식을 적용합니다. 다음 그림은 샘플 값을 표시하도록 전환된 보고서 디자인 화면을 보여줍니다.  
  
![보고서 작성기 식 샘플 형식](media/report-builder-expressions/report-builder-expression-sample-values-format.png)  


## <a name="DisplayText"></a> 단순 식의 접두사 기호 이해  

단순 식은 기호를 사용하여 참조가 필드인지, 매개 변수인지, 기본 제공 컬렉션인지 또는 보고서 항목 컬렉션인지를 나타냅니다. 다음 표에는 표시 텍스트 및 식 텍스트의 예가 나와 있습니다.  
  
|항목|표시 텍스트 예|식 텍스트 예|  
|----------|--------------------------|-----------------------------|  
|데이터 세트 필드|`[Sales]`<br /><br /> `[SUM(Sales)]`<br /><br /> `[FIRST(Store)]`|`=Fields!Sales.Value`<br /><br /> `=Sum(Fields!Sales.Value)`<br /><br /> `=First(Fields!Store.Value)`|  
|보고서 매개 변수|`[@Param]`<br /><br /> `[@Param.Label]`|`=Parameters!Param.Value`<br /><br /> `=Parameters!Param.Label`|  
|기본 제공 필드|`[&ReportName]`|`=Globals!ReportName.Value`|  
|표시 텍스트에 사용되는 리터럴 문자|`\[Sales\]`|`[Sales]`|  
  
##  <a name="References"></a> 복합 식 작성  
 식에는 함수, 연산자, 상수, 필드, 매개 변수, 기본 제공 컬렉션의 항목에 대한 참조 및 포함된 사용자 지정 코드 또는 사용자 지정 어셈블리에 대한 참조가 포함될 수 있습니다.  
  
 다음 표에는 식에 포함할 수 있는 참조의 종류가 나와 있습니다.  
  
|참조|설명|예제|  
|----------------|-----------------|-------------|  
|상수|글꼴 색과 같은 상수 값이 필요한 속성에 대화형으로 액세스할 수 있는 상수를 말합니다.|`="Blue"`|  
|연산자|식에서 참조를 결합하는 데 사용할 수 있는 연산자를 말합니다. 예를 들어 **&** 연산자는 문자열을 연결하는 데 사용됩니다.|`="The report ran at: " & Globals!ExecutionTime & "."`|  
|기본 제공 컬렉션|`Fields`, `Parameters`, `Variables`과 같은 식에 포함할 수 있는 기본 제공 컬렉션을 말합니다.|`=Fields!Sales.Value`<br /><br /> `=Parameters!Store.Value`<br /><br /> `=Variables!MyCalculation.Value`|  
|기본 제공 보고서 및 집계 함수|식에서 액세스할 수 있는 `Sum` 또는 `Previous`와 같은 기본 제공 함수를 말합니다.|`=Previous(Sum(Fields!Sales.Value))`|  
|보고서 작성기 식의 사용자 지정 코드 및 어셈블리 참조 |기본 제공 CLR 클래스 `xref:System.Math` 및 `xref:System.Convert`, 기타 CLR 클래스, Visual Basic 런타임 라이브러리 함수 또는 외부 어셈블리의 메서드에 액세스하는 방법을 설명합니다.<br /><br /> 보고서에 포함된 사용자 지정 코드에 액세스하는 방법 또는 보고서 클라이언트와 보고서 서버 모두에서 사용자 지정 어셈블리로 컴파일 및 설치하는 사용자 지정 코드에 액세스하는 방법을 설명합니다.|`=Sum(Fields!Sales.Value)`<br /><br /> `=CDate(Fields!SalesDate.Value)`<br /><br /> `=DateAdd("d",3,Fields!BirthDate.Value)`<br /><br /> `=Code.ToUSD(Fields!StandardCost.Value)`|  
   
##  <a name="Valid"></a> 식 유효성 검사  
 특정 보고서 항목 속성에 대한 식을 만들 때 식에 포함할 수 있는 참조는 보고서 항목 속성을 받아들일 수 있는 값과 속성이 평가되는 범위에 따라 달라 집니다. 예:  
  
-   기본적으로 [Sum] 식은 식이 평가될 때 범위 내에 있는 데이터의 합계를 계산합니다. 테이블 셀에 대한 범위는 행 및 열 그룹 멤버 자격에 따라 달라집니다. 
  
-   Font 속성의 값은 글꼴의 이름으로 평가되어야 합니다.  
  
-   식 구문은 디자인 타임에 유효성이 검사됩니다. 식 범위 유효성 검사는 보고서를 게시할 때 발생합니다. 실제 데이터에 의존하는 유효성 검사는 런타임 시에만 오류가 감지될 수 있습니다. 이러한 식 중 일부는 렌더링된 보고서에서 오류 메시지로 #Error를 생성합니다. 

## <a name="next-steps"></a>다음 단계

- [Power BI Premium에서 페이지를 매긴 보고서란?](paginated-reports-report-builder-power-bi.md)
