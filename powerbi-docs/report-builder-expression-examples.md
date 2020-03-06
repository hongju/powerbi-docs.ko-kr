---
title: Power BI 보고서 작성기의 식 예제
description: 식은 Power BI 보고서 작성기의 페이지를 매긴 보고서에 자주 사용되어 보고서의 내용과 모양을 제어합니다.
ms.date: 10/21/2019
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.assetid: 87ddb651-a1d0-4a42-8ea9-04dea3f6afa4
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 48e81c91a4555b4c8ea847ddffb1413058bbb152
ms.sourcegitcommit: df8bcc65f0df69bf1fc1d47eb06575742eac1622
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2020
ms.locfileid: "75953970"
---
# <a name="expression-examples-in-power-bi-report-builder"></a>Power BI 보고서 작성기의 식 예제
식은 Power BI 보고서 작성기의 페이지를 매긴 보고서에 자주 사용되어 보고서의 내용과 모양을 제어합니다. 식은 Microsoft Visual Basic으로 작성되며, 기본 제공 함수, 사용자 지정 코드, 보고서와 그룹 변수 및 사용자 정의 변수를 사용할 수 있습니다. 식은 같은 등호(=)로 시작합니다.   

이 항목에서는 보고서의 일반 작업에 사용할 수 있는 식의 예제를 제공합니다.  
  
-   [Visual Basic 함수](#VisualBasicFunctions) 날짜, 문자열, 변환 및 조건부 Visual Basic 함수의 예제입니다.  
  
-   [보고서 함수](#ReportFunctions) 집계 및 기타 기본 제공 보고서 함수의 예제입니다.  
  
-   [보고서 데이터 모양](#AppearanceofReportData) 보고서의 모양을 변경하는 예제입니다.  
  
-   [속성](#Properties) 컨트롤 서식 또는 표시 유형에 대한 보고서 항목 속성을 설정하는 예제입니다.  
  
-   [매개 변수](#Parameters) 식에서 매개 변수를 사용하는 예제입니다.  
  
-   [사용자 지정 코드](#CustomCode) 포함된 사용자 지정 코드의 예제입니다.  
  
식을 사용할 수 있는 단순 및 복합 식의 기본 사항 식을 사용할 수 있는 위치 및 식에 포함할 수 있는 참조 형식에 대한 자세한 내용은 [Power BI 보고서 작성기의 식](report-builder-expressions.md) 아래의 항목을 참조하세요. 
  
## <a name="functions"></a>Functions  
 보고서의 많은 식에는 함수가 포함되어 있습니다. 이러한 함수를 사용하여 데이터의 형식을 지정하고, 논리를 적용하며, 보고서 메타데이터에 액세스할 수 있습니다. Microsoft Visual Basic 런타임 라이브러리, `xref:System.Convert` 및 `xref:System.Math` 네임스페이스에서 함수를 사용하는 식을 작성할 수 있습니다. 사용자 지정 코드에서 함수에 대한 참조를 추가할 수 있습니다. `xref:System.Text.RegularExpressions`를 포함하여 Microsoft .NET Framework의 클래스를 사용할 수도 있습니다.  
  
##  <a name="VisualBasicFunctions"></a> Visual Basic 함수  
 Visual Basic 함수를 사용하여 텍스트 상자에 표시되거나 보고서의 매개 변수, 속성 또는 다른 영역에 사용되는 데이터를 조작할 수 있습니다. 이 섹션에서는 이러한 함수 중 일부를 보여 주는 예제를 제공합니다. 자세한 내용은 MSDN의 [Visual Basic 런타임 라이브러리 멤버](https://go.microsoft.com/fwlink/?LinkId=198941)를 참조하세요.  
  
 .NET Framework는 특정 날짜 형식과 같은 다양한 사용자 지정 형식 옵션을 제공합니다. 자세한 내용은 [형식 유형](/dotnet/standard/base-types/formatting-types)을 참조하세요.  
  
### <a name="math-functions"></a>수치 연산 함수  
  
-   **Round** 함수는 숫자를 가장 가까운 정수로 반올림하는 데 유용합니다. 다음 식은 1.3을 1로 반올림합니다.  
  
    ```  
    = Round(1.3)  
    ```  
  
     또한 Excel의 **MRound** 함수와 비슷한 방식으로 값을 지정한 배수로 반올림하는 식을 작성할 수도 있습니다. 값과 정수를 만드는 인수를 곱하고, 숫자를 반올림한 다음, 동일한 인수로 나눕니다. 예를 들어 1.3을 가장 가까운 배수인 .2(1.4)로 반올림하려면 다음 식을 사용합니다.  
  
    ```  
    = Round(1.3*5)/5  
    ```  
  
###  <a name="DateFunctions"></a> 날짜 함수  
  
-   **Today** 함수는 현재 날짜를 제공합니다. 이 식은 보고서에 날짜를 표시하는 텍스트 상자 또는 현재 날짜를 기준으로 데이터를 필터링하는 매개 변수에 사용할 수 있습니다.  
  
    ```  
    =Today()  
    ```  
  
-   **DateInterval** 함수는 날짜의 특정 부분을 추출하는 데 사용합니다. 몇 가지 유효한 **DateInterval** 매개 변수는 다음과 같습니다.

    -   DateInterval.Second
    -   DateInterval.Minute
    -   DateInterval.Hour
    -   DateInterval.Weekday
    -   DateInterval.Day
    -   DateInterval.DayOfYear
    -   DateInterval.WeekOfYear
    -   DateInterval.Month
    -   DateInterval.Quarter
    -   DateInterval.Year

    예를 들어 다음 식은 오늘 날짜에 대한 현재 연도의 주 수를 표시합니다.
  
    ```  
    =DatePart(DateInterval.WeekOfYear, today()) 
    ```  
  
-   **DateAdd** 함수는 단일 매개 변수를 기반으로 하여 날짜 범위를 제공하는 데 유용합니다. 다음 식은 *StartDate* 매개 변수의 날짜로부터 6개월 후의 날짜를 제공합니다.  
  
    ```  
    =DateAdd(DateInterval.Month, 6, Parameters!StartDate.Value)  
    ```  
  
-   **Year** 함수는 특정 날짜에 대한 연도를 표시합니다. 이 함수를 사용하여 날짜를 모두 그룹화하거나 연도를 날짜 세트의 레이블로 표시할 수 있습니다. 다음 식은 판매 주문 날짜의 지정된 그룹에 대한 연도를 제공합니다. **Month** 함수 및 다른 함수를 사용하여 날짜를 조작할 수도 있습니다. 자세한 내용은 Visual Basic 설명서를 참조하세요.  
  
    ```  
    =Year(Fields!OrderDate.Value)  
    ```  
  
-   식의 함수를 결합하여 형식을 사용자 지정할 수 있습니다. 다음 식은 날짜 형식을 월-일-연도 형식에서 월-주-주 번호 형식으로 변경합니다. 예를 들어 12/23/2009에서 December Week 3으로 변경합니다.  
  
    ```  
    =Format(Fields!MyDate.Value, "MMMM") & " Week " &   
    (Int(DateDiff("d", DateSerial(Year(Fields!MyDate.Value),   
    Month(Fields!MyDate.Value),1), Fields!FullDateAlternateKey.Value)/7)+1).ToString  
    ```  
  
     데이터 세트에서 계산 필드로 사용되는 경우 차트에서 이 식을 사용하여 값을 각 월의 주 단위로 집계할 수 있습니다.  
  
-   다음 식은 SellStartDate 값을 MMM-YY 형식으로 지정합니다. SellStartDate 필드는 날짜/시간 데이터 형식입니다.  
  
    ```  
    =FORMAT(Fields!SellStartDate.Value, "MMM-yy")  
    ```  
  
-   다음 식은 SellStartDate 값을 dd/MM/yyyy 형식으로 지정합니다. SellStartDate 필드는 날짜/시간 데이터 형식입니다.  
  
    ```  
    =FORMAT(Fields!SellStartDate.Value, "dd/MM/yyyy")  
    ```  
  
-   **CDate** 함수는 값을 날짜로 변환합니다. **Now** 함수는 시스템에 따라 현재 날짜 및 시간이 포함된 날짜 값을 반환합니다. **DateDiff**는 두 Date 값 사이의 시간 간격 수를 지정하는 Long 형식 값을 반환합니다.  
  
     다음 예제에서는 현재 연도의 시작 날짜를 표시합니다.  
  
    ```  
    =DateAdd(DateInterval.Year,DateDiff(DateInterval.Year,CDate("01/01/1900"),Now()),CDate("01/01/1900"))  
    ```  
  
-   다음 예제에서는 현재 월을 기준으로 이전 월의 시작 날짜를 표시합니다.  
  
    ```  
    =DateAdd(DateInterval.Month,DateDiff(DateInterval.Month,CDate("01/01/1900"),Now())-1,CDate("01/01/1900"))  
    ```  
  
-   다음 식은 SellStartDate와 LastReceiptDate 사이의 간격 연도를 생성합니다. 이러한 필드는 서로 다른 두 데이터 세트인 DataSet1과 DataSet2에 있습니다.  
  
    ```  
    =DATEDIFF("yyyy", First(Fields!SellStartDate.Value, "DataSet1"), First(Fields!LastReceiptDate.Value, "DataSet2"))  
    ```  
  
-   **DatePart** 함수는 지정된 Date 값의 지정된 구성 요소가 포함된 정수 값을 반환합니다. 다음 식은 DataSet1에 있는 SellStartDate의 첫 번째 값에 대한 연도를 반환합니다. 보고서에 여러 데이터 세트가 있으므로 데이터 세트 범위가 지정됩니다.  
  
    ```  
    =Datepart("yyyy", First(Fields!SellStartDate.Value, "DataSet1"))  
  
    ```  
  
-   **DateSerial** 함수는 지정된 연도, 월 및 일을 나타내는 Date 값을 반환하고 시간 정보는 자정으로 설정됩니다. 다음 예제에서는 현재 월을 기준으로 이전 월의 종료 날짜를 표시합니다.  
  
    ```  
    =DateSerial(Year(Now()), Month(Now()), "1").AddDays(-1)  
    ```  
  
-   다음 식은 사용자가 선택한 날짜 매개 변수 값을 기준으로 다양한 날짜를 표시합니다.  
  
|예제 설명|예제|  
|-------------------------|-------------|  
|어제|`=DateSerial(Year(Parameters!TodaysDate.Value),Month(Parameters!TodaysDate.Value),Day(Parameters!TodaysDate.Value)-1)`|  
|2일 전|`=DateSerial(Year(Parameters!TodaysDate.Value),Month(Parameters!TodaysDate.Value),Day(Parameters!TodaysDate.Value)-2)`|  
|1개월 전|`=DateSerial(Year(Parameters!TodaysDate.Value),Month(Parameters!TodaysDate.Value)-1,Day(Parameters!TodaysDate.Value))`|  
|2개월 전|`=DateSerial(Year(Parameters!TodaysDate.Value),Month(Parameters!TodaysDate.Value)-2,Day(Parameters!TodaysDate.Value))`|  
|1년 전|`=DateSerial(Year(Parameters!TodaysDate.Value)-1,Month(Parameters!TodaysDate.Value),Day(Parameters!TodaysDate.Value))`|  
|2년 전|`=DateSerial(Year(Parameters!TodaysDate.Value)-2,Month(Parameters!TodaysDate.Value),Day(Parameters!TodaysDate.Value))`|  
  
###  <a name="StringFunctions"></a> 문자열 함수  
  
-   연결 연산자와 Visual Basic 상수를 사용하여 둘 이상의 필드를 결합합니다. 다음 식은 두 필드를 반환하며, 각 필드는 동일한 텍스트 상자의 별도 줄에 있습니다.  
  
    ```  
    =Fields!FirstName.Value & vbCrLf & Fields!LastName.Value   
    ```  
  
-   **Format** 함수는 날짜와 숫자를 문자열 형식으로 지정하는 데 사용합니다. 다음 식은 *StartDate* 및 *EndDate* 매개 변수의 값을 자세한 날짜 형식으로 표시합니다.  
  
    ```  
    =Format(Parameters!StartDate.Value, "D") & " through " &  Format(Parameters!EndDate.Value, "D")    
    ```  
  
     텍스트 상자에 날짜 또는 숫자만 포함되는 경우 텍스트 상자의 Format 속성을 사용하여 텍스트 상자 내의 **Format** 함수 대신 형식을 적용해야 합니다.  
  
-   **Right**, **Len** 및 **InStr** 함수는 하위 문자열을 반환하는 데 유용합니다(예: *DOMAIN*\\*username*을 사용자 이름만으로 잘라내기). 다음 식은 *User* 매개 변수에서 백슬래시(\\) 문자 오른쪽의 문자열 부분을 반환합니다.  
  
    ```  
    =Right(Parameters!User.Value, Len(Parameters!User.Value) - InStr(Parameters!User.Value, "\"))  
    ```  
  
     다음 식은 Visual Basic 함수 대신 `xref:System.String` .NET Framework 클래스의 멤버를 사용하여 이전 식과 동일한 값을 생성합니다.  
  
    ```  
    =Parameters!User.Value.Substring(Parameters!User.Value.IndexOf("\")+1, Parameters!User.Value.Length-Parameters!User.Value.IndexOf("\")-1)  
    ```  
  
-   다중값 매개 변수에서 선택한 값을 표시합니다. 다음 예제에서는 **Join** 함수를 사용하여 *MySelection* 매개 변수의 선택한 값을 보고서 항목의 텍스트 상자 값에 대한 식으로 설정할 수 있는 단일 문자열에 연결합니다.  
  
    ```  
    = Join(Parameters!MySelection.Value)  
    ```  
  
     다음 예제에서는 위의 예제와 동일한 작업을 수행할 뿐만 아니라 텍스트 문자열을 선택한 값 목록 앞에 표시합니다.  
  
    ```  
    ="Report for " & JOIN(Parameters!MySelection.Value, " & ")  
  
    ```  
  
-   .NET Framework `xref:System.Text.RegularExpressions`의 **Regex** 함수는 기존 문자열의 형식(예: 전화 번호 형식 지정)을 변경하는 데 유용합니다. 다음 식은 **Replace** 함수를 사용하여 필드의 10자리 전화 번호 형식을 "*nnn*-*nnn*-*nnnn*"에서 "(*nnn*) *nnn*-*nnnn*"으로 변경합니다.  
  
    ```  
    =System.Text.RegularExpressions.Regex.Replace(Fields!Phone.Value, "(\d{3})[ -.]*(\d{3})[ -.]*(\d{4})", "($1) $2-$3")  
    ```  
  
    > [!NOTE]  
    >  Fields!Phone.Value의 값에 추가 공백이 없고 `xref:System.String` 형식인지 확인합니다.  
  
### <a name="lookup"></a>Lookup  
  
-   키 필드를 지정하면 **Lookup** 함수를 사용하여 일대일 관계(예: 키-값 쌍)에 대한 데이터 세트에서 값을 검색할 수 있습니다. 일치시킬 제품 식별자가 지정되면 다음 식은 데이터 세트의 제품 이름("Product")을 표시합니다.  
  
    ```  
    =Lookup(Fields!PID.Value, Fields!ProductID.Value, Fields.ProductName.Value, "Product")  
    ```  
  
### <a name="lookupset"></a>LookupSet  
  
-   키 필드를 지정하면 **LookupSet** 함수를 사용하여 일대다 관계에 대한 데이터 세트에서 값 세트를 검색할 수 있습니다. 예를 들어 한 사람은 여러 개의 전화 번호를 가질 수 있습니다. 다음 예제에서는 PhoneList 데이터 세트의 각 행에 사람 식별자와 전화 번호가 있다고 가정합니다. **LookupSet**는 값의 배열을 반환합니다. 다음 식은 반환 값을 단일 문자열에 결합하고, ContactID로 지정된 사람의 전화 번호 목록을 표시합니다.  
  
    ```  
    =Join(LookupSet(Fields!ContactID.Value, Fields!PersonID.Value, Fields!PhoneNumber.Value, "PhoneList"),",")  
    ```  
  
###  <a name="ConversionFunctions"></a> 변환 함수  
 Visual Basic 함수를 사용하여 필드를 한 데이터 형식에서 다른 데이터 형식으로 변환할 수 있습니다. 변환 함수는 필드의 기본 데이터 형식을 계산에 필요한 데이터 형식으로 변환하거나 텍스트를 결합하는 데 사용할 수 있습니다.  
  
-   다음 식은 500의 상수를 10진수 형식으로 변환하여 필터 식의 Value 필드에 있는 Transact-SQL money 데이터 형식과 비교합니다.  
  
    ```  
    =CDec(500)  
    ```  
  
-   다음 식은 *MySelection* 다중값 매개 변수에 대해 선택된 값의 수를 표시합니다.  
  
    ```  
    =CStr(Parameters!MySelection.Count)  
    ```  
  
###  <a name="DecisionFunctions"></a> 의사 결정 함수  
  
-   **IIF** 함수는 식이 true인지 여부에 따라 두 값 중 하나를 반환합니다. 다음 식은 **IIF** 함수를 사용하여 `LineTotal` 값이 100을 초과하면 부울 값인 **True**를 반환합니다. 그렇지 않으면 **False**를 반환합니다.  
  
    ```  
    =IIF(Fields!LineTotal.Value > 100, True, False)  
    ```  
  
-   여러 **IIF** 함수("중첩된 IIF"라고도 함)를 사용하여 `PctComplete`의 값에 따라 세 값 중 하나를 반환합니다. 다음 식은 텍스트 상자의 값에 따라 배경색을 변경할 수 있도록 텍스트 상자의 채우기 색에 배치합니다.  
  
    ```  
    =IIF(Fields!PctComplete.Value >= 10, "Green", IIF(Fields!PctComplete.Value >= 1, "Blue", "Red"))  
    ```  
  
     10보다 크거나 같은 값은 녹색 배경, 1에서 9 사이의 값은 파란색 배경, 그리고 1보다 작은 값은 빨간색 배경으로 표시됩니다.  
  
-   동일한 기능을 수행하는 다른 방법으로 **Switch** 함수를 사용합니다. **Switch** 함수는 테스트할 조건이 3개 이상인 경우에 유용합니다. **Switch** 함수는 true로 계산하는 계열의 첫 번째 식과 연결된 값을 반환합니다.  
  
    ```  
    =Switch(Fields!PctComplete.Value >= 10, "Green", Fields!PctComplete.Value >= 1, "Blue", Fields!PctComplete.Value = 1, "Yellow", Fields!PctComplete.Value <= 0, "Red")  
    ```  
  
     10보다 크거나 같은 값은 녹색 배경, 1에서 9 사이의 값은 파란색 배경, 1 값은 노란색 배경, 0보다 작거나 같은 값은 빨간색 배경으로 표시됩니다.  
  
-   `ImportantDate` 필드의 값을 테스트하여 1주일 이상 지난 경우 "빨간색"을 반환하고, 그렇지 않으면 "파란색"을 반환합니다. 이 식은 보고서 항목에 있는 텍스트 상자의 Color 속성을 제어하는 데 사용할 수 있습니다.  
  
    ```  
    =IIF(DateDiff("d",Fields!ImportantDate.Value, Now())>7,"Red","Blue")  
    ```  
  
-   `PhoneNumber` 필드의 값을 테스트하고, **null**(Visual Basic의 **Nothing**)이면 "No Value(값 없음)"를 반환하고, 그렇지 않으면 전화 번호 값을 반환합니다. 이 식은 보고서 항목의 텍스트 상자 값을 제어하는 데 사용할 수 있습니다.  
  
    ```  
    =IIF(Fields!PhoneNumber.Value Is Nothing,"No Value",Fields!PhoneNumber.Value)  
    ```  
  
-   `Department` 필드의 값을 테스트하고, 하위 보고서 이름 또는 **null**(Visual Basic의 **Nothing**)을 반환합니다. 이 식은 조건부 드릴스루 하위 보고서에 사용할 수 있습니다.  
  
    ```  
    =IIF(Fields!Department.Value = "Development", "EmployeeReport", Nothing)  
    ```  
  
-   필드 값이 null인지 여부를 테스트합니다. 이 식은 이미지 보고서 항목의 **Hidden** 속성을 제어하는 데 사용할 수 있습니다. 다음 예제에서는 필드의 값이 null이 아닌 경우에만 [LargePhoto] 필드에서 지정된 이미지를 표시합니다.  
  
    ```  
    =IIF(IsNothing(Fields!LargePhoto.Value),True,False)  
    ```  
  
-   **MonthName** 함수는 지정된 월의 이름이 포함된 문자열 값을 반환합니다. 다음 예제에서는 필드의 값이 0이면 Month 필드에 NA를 표시합니다.  
  
    ```  
    IIF(Fields!Month.Value=0,"NA",MonthName(IIF(Fields!Month.Value=0,1,Fields!Month.Value)))  
  
    ```  
  
##  <a name="ReportFunctions"></a> 보고서 함수  
 식에서 보고서의 데이터를 조작하는 추가 보고서 함수에 대한 참조를 추가할 수 있습니다. 이 섹션에서는 이러한 두 가지 함수에 대한 예제를 제공합니다. 
  
###  <a name="Sum"></a> Sum  
  
-   **Sum** 함수는 그룹 또는 데이터 영역의 값을 합계할 수 있습니다. 이 함수는 그룹의 머리글 또는 바닥글에 유용할 수 있습니다. 다음 식은 Order(주문) 그룹 또는 데이터 영역에 있는 데이터의 합계를 표시합니다.  
  
    ```  
    =Sum(Fields!LineTotal.Value, "Order")  
    ```  
  
-   **Sum** 함수는 조건부 집계 계산에도 사용할 수 있습니다. 예를 들어 다음 식은 데이터 세트에 가능한 값이 Not Started, Started, Finished(시작되지 않음, 시작됨, 마침)인 State(상태)라는 필드가 있으면 그룹 머리글에 배치될 때 Finished 값에 대한 집계 합계만 계산합니다.  
  
    ```  
    =Sum(IIF(Fields!State.Value = "Finished", 1, 0))  
    ```  
  
###  <a name="RowNumber"></a> RowNumber  
  
-   데이터 영역 내의 텍스트 상자에 사용되는 **RowNumber** 함수는 식이 표시되는 텍스트 상자의 각 인스턴스에 대한 행 번호를 표시합니다. 이 함수는 테이블의 행 번호를 매기는 데 유용할 수 있습니다. 또한 행 수에 따라 페이지 나누기를 제공하는 것과 같은 더 복잡한 작업에도 유용할 수 있습니다. 자세한 내용은 이 항목의 [페이지 나누기](#PageBreaks)를 참조하세요.  
  
     **RowNumber**에 지정한 범위는 번호 다시 매기기를 시작하는 시점을 제어합니다. **Nothing** 키워드는 함수가 가장 바깥쪽 데이터 영역의 첫 번째 행에서 개수를 시작함을 나타냅니다. 중첩된 데이터 영역 내에서 개수를 시작하려면 데이터 영역의 이름을 사용합니다. 그룹 내에서 개수를 시작하려면 그룹 이름을 사용합니다.  
  
    ```  
    =RowNumber(Nothing)  
    ```  
  
##  <a name="AppearanceofReportData"></a> 보고서 데이터 모양  
 식을 사용하여 데이터가 보고서에 표시되는 방법을 조작할 수 있습니다. 예를 들어 두 필드의 값을 단일 텍스트 상자에 표시하거나, 보고서에 대한 정보를 표시하거나, 페이지 나누기가 보고서에 삽입되는 방법에 영향을 줄 수 있습니다.  
  
###  <a name="PageHeadersandFooters"></a> 페이지 머리글 및 바닥글  
 보고서를 디자인할 때 보고서 이름과 페이지 번호를 보고서 바닥글에 표시할 수 있습니다. 이렇게 하려면 다음 식을 사용할 수 있습니다.  
  
-   다음 식은 보고서의 이름 및 해당 보고서가 실행된 시간을 제공합니다. 보고서 바닥글의 텍스트 상자 또는 보고서 본문에 배치할 수 있습니다. 시간은 간단한 날짜에 대한 .NET Framework 서식 문자열의 형식으로 지정됩니다.  
  
    ```  
    =Globals.ReportName & ", dated " & Format(Globals.ExecutionTime, "d")  
    ```  
  
-   다음 식은 보고서 바닥글의 텍스트 상자에 배치되면 보고서의 페이지 번호와 총 페이지 수를 제공합니다.  
  
    ```  
    =Globals.PageNumber & " of " & Globals.TotalPages  
    ```  
  
 다음 예제에서는 페이지의 처음 및 마지막 값을 페이지 머리글에 표시하는 방법을 설명하며, 디렉터리 목록에서 찾을 수 있는 것과 비슷합니다. 이 예제에서는 `LastName`이라는 텍스트 상자가 포함된 데이터 영역을 가정합니다.  
  
-   다음 식은 페이지 머리글의 왼쪽에 있는 텍스트 상자에 배치되면 페이지에 있는 `LastName` 텍스트 상자의 첫 번째 값을 제공합니다.  
  
    ```  
    =First(ReportItems("LastName").Value)  
    ```  
  
-   다음 식은 페이지 머리글의 오른쪽에 있는 텍스트 상자에 배치되면 페이지에 있는 `LastName` 텍스트 상자의 마지막 값을 제공합니다.  
  
    ```  
    =Last(ReportItems("LastName").Value)  
    ```  
  
 다음 예제에서는 페이지 합계를 표시하는 방법을 설명합니다. 이 예제에서는 `Cost`라는 텍스트 상자가 포함된 데이터 영역을 가정합니다.  
  
-   다음 식은 페이지 머리글 또는 바닥글에 배치되면 페이지의 `Cost` 텍스트 상자에 있는 값의 합계를 제공합니다.  
  
    ```  
    =Sum(ReportItems("Cost").Value)  
    ```  
  
> [!NOTE]  
>  페이지 머리글 또는 바닥글에서 식당 하나의 보고서 항목만 참조할 수 있습니다. 또한 페이지 머리글 및 바닥글 식에서 텍스트 상자 이름은 참조할 수 있지만, 텍스트 상자 내의 실제 데이터 식은 참조할 수 없습니다.  
  
###  <a name="PageBreaks"></a> 페이지 나누기  
 일부 보고서에서 그룹 또는 보고서 항목 대신 지정된 행 수의 끝에 페이지 나누기를 배치하려고 할 수 있습니다. 이렇게 하려면 원하는 그룹 또는 세부 정보 레코드가 포함된 그룹을 만들고, 페이지 나누기를 그룹에 추가한 다음, 지정된 행 수를 기준으로 그룹화하는 식을 추가합니다.  
  
-   다음 식은 그룹 식에 배치되면 25개 행의 각 세트에 숫자를 할당합니다. 그룹에 대한 페이지 나누기가 정의되면 이 식은 25개 행마다 페이지 나누기를 만듭니다.  
  
    ```  
    =Ceiling(RowNumber(Nothing)/25)  
    ```  
  
     사용자가 페이지당 행 수에 대한 값을 설정할 수 있도록 하려면 다음 식과 같이 `RowsPerPage`라는 매개 변수를 만들고 그룹 식을 매개 변수의 기준으로 지정합니다.  
  
    ```  
    =Ceiling(RowNumber(Nothing)/Parameters!RowsPerPage.Value)  
    ```  
  
##  <a name="Properties"></a> 속성  
 식은 데이터를 텍스트 상자에 표시하는 데만 사용되는 것이 아닙니다. 또한 속성을 보고서 항목에 적용하는 방법을 변경하는 데 사용할 수도 있습니다. 보고서 항목에 대한 스타일 정보를 변경하거나 해당 표시 유형을 변경할 수 있습니다.  
  
###  <a name="Formatting"></a> 서식 지정  
  
-   다음 식은 텍스트 상자의 Color 속성에 사용되면 `Profit` 필드의 값에 따라 텍스트 색을 변경합니다.  
  
    ```  
    =Iif(Fields!Profit.Value < 0, "Red", "Black")  
    ```  
  
     또한 `Me` Visual Basic 개체 변수도 사용할 수 있습니다. 이 변수는 텍스트 상자의 값을 참조하는 또 다른 방법입니다.  
  
     `=Iif(Me.Value < 0, "Red", "Black")`  
  
-   다음 식은 데이터 영역에 있는 보고서 항목의 BackgroundColor 속성에 사용되면 각 행의 배경색을 흐린 녹색과 흰색을 번갈아 표시합니다.  
  
    ```  
    =Iif(RowNumber(Nothing) Mod 2, "PaleGreen", "White")  
    ```  
  
     식을 지정된 범위에서 사용하는 경우 집계 함수에 대한 데이터 세트를 지정해야 할 수 있습니다.  
  
    ```  
    =Iif(RowNumber("Employees") Mod 2, "PaleGreen", "White")  
    ```  
  
> [!NOTE]  
>  사용 가능한 색은 .NET Framework KnownColor 열거형에서 제공합니다.  
  
### <a name="chart-colors"></a>차트 색  
 도형 차트의 색을 지정하려면 사용자 지정 코드를 사용하여 색이 데이터 요소 값에 매핑되는 순서를 제어할 수 있습니다. 이렇게 하면 범주 그룹이 동일한 여러 차트에 일관된 색을 사용할 수 있습니다. 
  
###  <a name="Visibility"></a> 표시 유형  
 보고서 항목에 표시 유형 속성을 사용하여 보고서의 항목을 표시하거나 숨길 수 있습니다. 테이블과 같은 데이터 영역에서 처음에는 식의 값에 따라 세부 정보 행을 숨길 수 있습니다.  
  
-   다음 식은 그룹의 세부 정보 행에 대한 초기 표시 유형에 사용되면 `PctQuota` 필드에서 90%를 초과하는 모든 판매에 대한 세부 정보 행을 표시합니다.  
  
    ```  
    =Iif(Fields!PctQuota.Value>.9, False, True)  
    ```  
  
-   다음 식은 테이블의 Hidden 속성에 설정되면 12개가 넘는 행이 있는 경우에만 테이블을 표시합니다.  
  
    ```  
    =IIF(CountRows()>12,false,true)  
    ```  
  
-   다음 식은 열의 **Hidden** 속성에 설정되면 데이터 원본에서 데이터를 검색한 후에 해당 필드가 보고서 데이터 세트에 있는 경우에만 열을 표시합니다.  
  
    ```  
    =IIF(Fields!Column_1.IsMissing, true, false)  
    ```  
  
###  <a name="Hyperlinks"></a> URL  
 보고서 데이터를 사용하여 URL을 사용자 지정하고, URL이 텍스트 상자에 대한 작업으로 추가되는 여부를 조건부로 제어할 수 있습니다.  
  
-   다음 식은 텍스트 상자에서 작업으로 사용되면 `EmployeeID` 데이터 세트 필드를 URL 매개 변수로 지정하는 사용자 지정 URL을 생성합니다.  
  
    ```  
    ="https://adventure-works/MyInfo?ID=" & Fields!EmployeeID.Value  
    ```  
  
-   다음 식은 URL을 텍스트 상자에 추가하는지 여부를 조건부로 제어합니다. 이 식은 사용자가 활성 URL을 보고서에 포함시킬지 여부를 결정할 수 있도록 하는 `IncludeURLs` 매개 변수에 따라 달라집니다. 이 식은 텍스트 상자에서 작업으로 설정됩니다. 매개 변수를 False로 설정한 후에 보고서를 확인하면 하이퍼링크가 없는 Microsoft Excel 보고서를 내보낼 수 있습니다.  
  
    ```  
    =IIF(Parameters!IncludeURLs.Value,"https://adventure-works.com/productcatalog",Nothing)  
    ```  
  
##  <a name="ReportData"></a> 보고서 데이터  
 식을 사용하여 보고서에 사용되는 데이터를 조작할 수 있습니다. 매개 변수 및 기타 보고서 정보를 참조할 수 있습니다. 보고서의 데이터를 검색하는 데 사용되는 쿼리를 변경할 수도 있습니다.  
  
###  <a name="Parameters"></a> 매개 변수  
 매개 변수에서 식을 사용하여 매개 변수의 기본값을 변경할 수 있습니다. 예를 들어 매개 변수를 사용하여 보고서를 실행하는 데 사용되는 사용자 ID에 기반한 특정 사용자로 데이터를 필터링할 수 있습니다.  
  
-   다음 식은 매개 변수의 기본값으로 사용되면 보고서를 실행하는 사용자의 사용자 ID를 수집합니다.  
  
    ```  
    =User!UserID  
    ```  
  
-   쿼리 매개 변수, 필터 식, 텍스트 상자 또는 보고서의 다른 영역에서 매개 변수를 참조하려면 **Parameters** 글로벌 컬렉션을 사용합니다. 다음 예제에서는 매개 변수의 이름이 *Department*인 것으로 가정합니다.  
  
    ```  
    =Parameters!Department.Value  
    ```  
  
-   매개 변수는 보고서에 만들 수는 있지만 숨김으로 설정됩니다. 보고서가 보고서 서버에서 실행되면 매개 변수가 도구 모음에 표시되지 않으며 보고서 판독기에서 기본값을 변경할 수 없습니다. 기본값으로 설정된 숨겨진 매개 변수 세트는 사용자 지정 상수로 사용할 수 있습니다. 이 값은 필드 식을 포함하여 모든 식에서 사용할 수 있습니다. 다음 식은 *ParameterField* 매개 변수에 대한 기본 매개 변수 값으로 지정된 필드를 식별합니다.  
  
    ```  
    =Fields(Parameters!ParameterField.Value).Value  
    ```  
  
##  <a name="CustomCode"></a> 사용자 지정 코드  
 보고서에 포함된 사용자 지정 코드를 사용할 수 있습니다. 
  
### <a name="using-group-variables-for-custom-aggregation"></a>사용자 지정 집계에 그룹 변수 사용  
 특정 그룹 범위에 대해 로컬인 그룹 변수의 값을 초기화한 다음, 해당 변수에 대한 참조를 식에 포함시킬 수 있습니다. 사용자 지정 코드에 그룹 변수를 사용할 수 있는 방법 중 하나는 사용자 지정 집계를 구현하는 것입니다. 
  
## <a name="suppressing-null-or-zero-values-at-run-time"></a>런타임에 null 또는 0 값 표시 안 함  
 식의 일부 값은 보고서 처리 시간에 null 또는 정의되지 않은 값으로 계산할 수 있습니다. 이렇게 하면 런타임 오류가 만들어져 계산된 식 대신 **#Error**가 텍스트 상자에 표시될 수 있습니다. **IIF** 문의 각 부분이 **true** 또는 **false**를 테스트하는 루틴으로 전달되기 전에 계산되므로(함수 호출 포함) If-Then-Else 문과 달리 **IIF** 함수는 특히 이 동작에 민감합니다. `Fields!Sales.Value`가 NOTHING이면 `=IIF(Fields!Sales.Value is NOTHING, 0, Fields!Sales.Value)` 문은 **#Error**를 렌더링되는 보고서에 생성합니다.  
  
 이 상황을 방지하려면 다음 전략 중 하나를 사용합니다.  
  
-   필드 B의 값이 0이거나 정의되지 않음이면 분자를 0, 분모를 1로 설정합니다. 그렇지 않으면 분자를 필드 A의 값, 분모를 필드 B의 값으로 설정합니다.  
  
    ```  
    =IIF(Field!B.Value=0, 0, Field!A.Value / IIF(Field!B.Value =0, 1, Field!B.Value))  
    ```  
  
-   식 값을 반환하는 사용자 지정 코드 함수를 사용합니다. 다음 예제에서는 현재 값과 이전 값의 백분율 차이를 반환합니다. 이는 두 개의 연속 값 사이의 차이를 계산하는 데 사용할 수 있으며, 첫 번째 비교의 경계 사례(이전 값이 없는 경우)와 이전 값 또는 현재 값 중 하나가 **null**(Visual Basic의 **Nothing**)인지 여부를 처리합니다.  
  
    ```  
    Public Function GetDeltaPercentage(ByVal PreviousValue, ByVal CurrentValue) As Object  
        If IsNothing(PreviousValue) OR IsNothing(CurrentValue) Then  
            Return Nothing  
        Else if PreviousValue = 0 OR CurrentValue = 0 Then  
            Return Nothing  
        Else   
            Return (CurrentValue - PreviousValue) / CurrentValue  
        End If  
    End Function  
    ```  
  
     다음 식은 텍스트 상자에서 "ColumnGroupByYear" 컨테이너(그룹 또는 데이터 영역)에 대해 이 사용자 지정 코드를 호출하는 방법을 보여 줍니다.  
  
    ```  
    =Code.GetDeltaPercentage(Previous(Sum(Fields!Sales.Value),"ColumnGroupByYear"), Sum(Fields!Sales.Value))  
    ```  
  
     이렇게 하면 런타임 예외를 방지할 수 있습니다. 이제 텍스트 상자의 **Color** 속성에서 `=IIF(Me.Value < 0, "red", "black")`와 같은 식을 사용하여 값이 0보다 크거나 작은지 여부에 따라 텍스트를 조건부로 표시할 수 있습니다.  
  
## <a name="next-steps"></a>다음 단계

- [Power BI Premium에서 페이지를 매긴 보고서란?](paginated-reports-report-builder-power-bi.md)
  
