---
title: "자습서: Power BI Desktop에서 Excel 및 OData 피드의 판매 데이터 분석"
description: "자습서: Excel 및 OData 피드의 판매 데이터 분석"
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/24/2018
ms.author: davidi
LocalizationGroup: Learn more
ms.openlocfilehash: 4cab3ed114d03d42c6acf1bf62f70e7d920e16b2
ms.sourcegitcommit: d91b7bf18d5c504037134f375886633379f28ede
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/27/2018
---
# <a name="tutorial-analyzing-sales-data-from-excel-and-an-odata-feed"></a>자습서: Excel 및 OData 피드의 판매 데이터 분석
**Power BI Desktop**을 사용하면 모든 종류의 다양한 데이터 원본에 연결한 다음 흥미롭고 눈에 띄는 데이터 분석과 시각화를 쉽게 수행할 수 있는 방식으로 이러한 데이터 원본을 결합 및 셰이핑할 수 있습니다. 이 자습서에서는 두 데이터 소스의 데이터를 결합하는 방법을 배웁니다. 

한 데이터베이스에 제품 정보가 있고 다른 데이터베이스에 판매 정보가 있는 경우와 같이 데이터가 여러 데이터 소스에 분산되어 있는 것이 일반적입니다. 이 문서에서 배울 게 될 기술에는 Excel 통합 문서와 OData 피드가 포함되지만 이러한 기술은 SQL Server 쿼리, CSV 파일 또는 Power BI Desktop의 모든 데이터 소스와 같은 다른 데이터 소스에도 적용할 수 있습니다.

이 자습서에서는 Excel의 데이터(제품 정보 포함)와 OData 피드의 데이터(주문 데이터 포함)를 가져옵니다. 변환 및 집계 단계를 수행하고 두 소스의 데이터를 결합하여 대화형 시각화를 포함하는 **제품 및 연도별 총 판매액** 보고서를 생성합니다. 

최종 보고서의 모양은 다음과 같습니다.

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/18.png)

이 자습서의 단계를 따르려면 다운로드할 수 있는 제품 통합 문서가 필요합니다.**[여기를 클릭하여 Products.xlsx를 다운로드합니다.](http://download.microsoft.com/download/1/4/E/14EDED28-6C58-4055-A65C-23B4DA81C4DE/Products.xlsx)**

**다른 이름으로 저장** 대화 상자에서 파일 이름을 **Products.xlsx**로 지정합니다.

## <a name="task-1-get-product-data-from-an-excel-workbook"></a>작업 1: Excel 통합 문서에서 제품 데이터 가져오기
이 작업에서는 Products.xlsx 파일의 제품을 Power BI Desktop으로 가져옵니다.

### <a name="step-1-connect-to-an-excel-workbook"></a>1단계: Excel 통합 문서에 연결
1. Power BI Desktop을 시작합니다.
2. 홈 리본에서 **데이터 가져오기**를 선택합니다. Excel은 **가장 일반적인** 데이터 연결 중 하나이므로 **데이터 가져오기** 메뉴에서 직접 선택할 수 있습니다.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_1.png)
3. 직접 데이터 가져오기 단추를 선택하는 경우 **파일 \>Excel**을 선택하고**연결**을 선택할 수도 있습니다.
4. **파일 열기** 대화 상자에서 **Products.xlsx** 파일을 선택합니다.
5. **탐색기** 창에서 **Products** 테이블을 선택한 다음 **편집**을 선택합니다.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_2.png)

### <a name="step-2-remove-other-columns-to-only-display-columns-of-interest"></a>2단계: 다른 열을 제거하여 관심 있는 열만 표시
이 단계에서는 **ProductID**, **ProductName**, **UnitsInStock**및 **QuantityPerUnit**를 제외한 모든 열을 제거합니다. Power BI Desktop에는 일반적으로 동일한 작업을 수행하는 몇 가지 방법이 있습니다. 예를 들어 리본에 있는 많은 단추는 열 또는 셀에서 메뉴를 마우스 오른쪽 단추로 클릭하여 사용할 수도 있습니다.

Power BI Desktop에는 데이터 연결을 셰이핑 및 변환하는 쿼리 편집기가 포함되어 있습니다. 쿼리 편집기는 **탐색기** 에서 **편집**을 선택하면 자동으로 열립니다. Power BI Desktop의 **홈** 리본에서 **쿼리 편집** 을 선택하여 쿼리 편집기를 열 수도 있습니다. 쿼리 편집기에서 다음 단계를 수행합니다.

1. 쿼리 편집기에서 **ProductID**, **ProductName**, **QuantityPerUnit**및 **UnitsInStock** 열을 선택합니다(둘 이상의 열을 선택하려면 **Ctrl+클릭** 을 사용하고, 서로 붙어 있는 열을 선택하려면 **Shift+클릭** 을 사용).
2. 리본에서 **열 제거** \> **다른 열 제거**를 선택하거나 열 머리글을 마우스 오른쪽 단추로 클릭하고 **다른 열 제거**를 클릭합니다.

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/anlayzingsalesdata_removeothercolumns.png)

### <a name="step-3-change-the-data-type-of-the-unitsinstock-column"></a>3단계: UnitsInStock 열의 데이터 형식 변경
쿼리 편집기가 데이터에 연결되면 각 필드를 검토하고 최적의 데이터 형식을 결정합니다. Excel 통합 문서의 경우 재고 제품은 항상 정수이므로 이 단계에서 **UnitsInStock** 열의 데이터 형식이 정수인지 확인합니다.

1. **UnitsInStock** 열을 선택합니다.
2. **홈** 리본에서 **데이터 형식** 드롭다운 단추를 선택합니다.
3. 아직 정수가 아니면 드롭다운에서 데이터 형식으로 **정수** 를 선택합니다( **데이터 형식:** 단추도 현재 선택에 대한 데이터 형식을 표시함).
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/anlayzingsalesdata_wholenumber.png)      

### <a name="power-bi-desktop-steps-created"></a>만들어진 Power BI Desktop 단계
쿼리 편집기에서 쿼리 작업을 수행하면 쿼리 단계가 만들어지고 **쿼리 설정** 창의 **적용된 단계** 목록에 나열됩니다. 각 쿼리 단계에 해당하는 수식("M" 언어라고도 함)이 있습니다. "M" 수식 언어에 대한 자세한 내용은 [Power BI 수식에 대한 자세한 정보](https://support.office.com/Article/Learn-about-Power-Query-formulas-6bc50988-022b-4799-a709-f8aafdee2b2f)를 참조하세요.

| 작업 | 쿼리 단계 | 수식 |
| --- | --- | --- |
| Excel 통합 문서에 연결 |소스 |Source{[Name="Products"]}[Data] |
| 첫 행을 테이블 열 머리글로 승격 |FirstRowAsHeader |[Table.PromoteHeaders](https://support.office.com/Article/TablePromoteHeaders-b8eaeb95-042a-42e1-9164-6d3c646acadc "Table.PromoteHeaders") <br /> (Products) |
| 다른 열을 제거하여 관심 있는 열만 표시 |RemovedOtherColumns |[Table.SelectColumns](https://support.office.com/Article/TableSelectColumns-20bb9e28-9fd3-4cd2-a21b-97972c82ec22 "Table.SelectColumns")  <br />(FirstRowAsHeader,{"ProductID", "ProductName", "QuantityPerUnit", "UnitsInStock"}) |
| 데이터 형식 변경 |변경된 형식 |Table.TransformColumnTypes(\#"Removed Other Columns",{{"UnitsInStock", Int64.Type}}) |

## <a name="task-2-import-order-data-from-an-odata-feed"></a>작업 2: OData 피드에서 주문 데이터 가져오기
이 작업에서는 주문 데이터를 가져옵니다. 이 단계는 판매 시스템에 대한 연결을 나타냅니다. 다음 URL(아래 단계에서 복사하여 붙여넣을 수 있음)에서 샘플 Northwind OData 피드에서 Power BI Desktop으로 데이터를 가져옵니다. <http://services.odata.org/V3/Northwind/Northwind.svc/> 

### <a name="step-1-connect-to-an-odata-feed"></a>1단계: OData 피드에 연결
1. 쿼리 편집기의 **홈** 리본 탭에서 **데이터 가져오기**를 선택합니다.
2. **OData 피드** 데이터 소스로 이동합니다.
3. **OData 피드** 대화 상자에서 Northwind OData 피드의 **URL** 을 붙여넣습니다.
4. **확인**을 선택합니다.
5. **탐색기** 창에서 **Orders** 테이블을 선택한 다음 **편집**을 선택합니다.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/anlayzingsalesdata_odatafeed.png)

>[!NOTE]
>미리 보기를 보려면 확인란을 선택하지 않고 테이블 이름을 클릭하면 됩니다.

### <a name="step-2-expand-the-orderdetails-table"></a>2단계: Order\_Details 테이블 확장
**Orders** 테이블에는 **Details** 테이블에 대한 참조가 포함되어 있습니다. Details 테이블에는 각 주문에 포함된 개별 제품이 포함되어 있습니다. 여러 테이블이 포함된 데이터 소스(예: 관계형 데이터베이스)에 연결하는 경우 이러한 참조를 사용하여 쿼리를 작성할 수 있습니다. 

이 단계에서는 **Orders** 테이블과 관련된 **Order\_Details** 테이블을 확장하여 **Order\_Details**의 **ProductID**, **UnitPrice** 및 **Quantity** 열을 **Orders** 테이블에 결합합니다. 다음은 이러한 테이블의 데이터를 표현한 것입니다.

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/orderdetails.png)

**확장** 작업에서는 관련 테이블의 열을 제목 테이블에 결합합니다. 쿼리를 실행하면 관련 테이블(**Order\_Details**)의 행이 제목 테이블(**Orders**)의 행에 결합됩니다.

**Order\_Details** 테이블을 확장하고 나면 중첩 또는 관련 테이블의 각 행에 대해 하나씩, 3개의 새 열과 추가 행이 **Orders** 테이블에 추가됩니다.

1. **쿼리 뷰**에서 **Order\_Details** 열로 스크롤합니다.
2. **Order\_Details** 열에서 확장 아이콘(![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/expand.png))을 선택합니다.
3. **확장** 드롭다운에서 다음을 수행합니다.
   1. **(모든 열 선택)** 을 선택하여 모든 열을 선택 취소합니다.
   2. **ProductID**, **UnitPrice**및 **Quantity**를 선택합니다.
   3. **확인**을 클릭합니다.
      ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/7.png)

### <a name="step-3-remove-other-columns-to-only-display-columns-of-interest"></a>3단계: 다른 열을 제거하여 관심 있는 열만 표시
이 단계에서는 **OrderDate, ShipCity**, **ShipCountry**, **Order\_Details.ProductID**, **Order\_Details.UnitPrice**, **Order\_Details.Quantity** 열을 제외한 모든 열을 제거합니다. 이전 작업에서는 **다른 열 제거**를 사용했습니다. 이 작업에서는 선택한 열을 제거합니다.

1. **쿼리 뷰**에서 a.와 b.를 완료하여 모든 열을 선택합니다.
   1. 첫 번째 열(**OrderID**)을 클릭합니다.
   2. 마지막 열(**Shipper**)을 Shift+클릭합니다.
   3. 모든 열을 선택했으므로 Ctrl+클릭을 사용하여 **OrderDate**, **ShipCity**, **ShipCountry**, **Order\_Details.ProductID**, **Order\_Details.UnitPrice**, **Order\_Details.Quantity** 열을 선택 취소합니다.
2. 이제 제거할 열만 선택했으므로 선택한 열 머리글을 마우스 오른쪽 단추로 클릭하고 **열 제거**를 클릭합니다.

### <a name="step-4-calculate-the-line-total-for-each-orderdetails-row"></a>4단계: 각 Order\_Details 행에 대한 라인 합계 계산
Power BI Desktop을 사용하면 가져오는 열에 따라 계산을 만들어 연결하는 데이터를 보강할 수 있습니다. 이 단계에서는 **사용자 지정 열**을 만들어 각 **Order\_Details** 행에 대한 라인 합계를 계산합니다.

각 **Order\_Details** 행에 대한 라인 합계 계산:

1. **열 추가** 리본 탭에서 **사용자 지정** **열 추가**를 클릭합니다.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_4.png)
2. **사용자 지정 열 추가** 대화 상자의 **사용자 지정 열 수식** 텍스트 상자에 **[Order\_Details.UnitPrice] \* [Order\_Details.Quantity]**를 입력합니다.
3. **새 열 이름** 텍스트 상자에 **LineTotal**을 입력합니다.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/8.png)
4. **확인**을 클릭합니다.

### <a name="step-5-set-the-datatype-of-the-linetotal-field"></a>5단계: LineTotal 필드의 데이터 형식 설정
1. **LineTotal** 열을 마우스 오른쪽 단추로 클릭합니다.
2. **형식 변경**을 선택하고 **10진수**를 선택합니다.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/9.png)

### <a name="step-6-rename-and-reorder-columns-in-the-query"></a>6단계: 쿼리에서 열 이름 및 순서 바꾸기
이 단계에서는 최종 열의 이름을 바꾸고 순서를 변경하여 보고서를 만들 때 모델을 쉽게 사용할 수 있도록 하는 작업을 마칩니다.

1. **쿼리 편집기**에서 **LineTotal** 열을 왼쪽의 **ShipCountry**뒤로 끕니다.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/10.png)
2. *Order\_Details* 를 제거합니다. 각 열 머리글을 두 번 클릭한 다음 열 이름에서 해당 텍스트를 삭제하여 **Order\_Details.ProductID**, **Order\_Details.UnitPrice**, **Order\_Details.Quantity** 열에서 접두사를 제거합니다.

### <a name="power-bi-desktop-steps-created"></a>만들어진 Power BI Desktop 단계
쿼리 편집기에서 쿼리 작업을 수행하면 쿼리 단계가 만들어지고 **쿼리 설정** 창의 **적용된 단계** 목록에 나열됩니다. 각 쿼리 단계에는 "M" 언어라고도 하는 해당 파워 쿼리 수식이 있습니다. 이 수식 언어에 대한 자세한 내용은 [Power BI에 대한 자세한 정보](https://support.office.com/Article/Learn-about-Power-Query-formulas-6bc50988-022b-4799-a709-f8aafdee2b2f "파워 쿼리 수식에 대한 자세한 정보")를 참조하세요.

| 작업 | 쿼리 단계 | 수식 |
| --- | --- | --- |
| OData 피드에 연결 |소스 |Source{[Name="Orders"]}[Data] |
| Order\_Details 테이블 확장 |Order\_Details 확장 |[Table.ExpandTableColumn](https://support.office.com/Article/TableExpandTableColumn-54903f25-75a2-4a44-a9a3-52a9d895ee98 "Table.ExpandTableColumn") <br /> (Orders, "Order\_Details", {"ProductID", "UnitPrice", "Quantity"}, {"Order\_Details.ProductID", "Order\_Details.UnitPrice", "Order\_Details.Quantity"}) |
| 다른 열을 제거하여 관심 있는 열만 표시 |RemovedColumns |[Table.RemoveColumns](https://support.office.com/Article/TableRemoveColumns-6265190e-2f58-4300-85b8-df88fc1a67d3 "Table.RemoveColumns") <br />(\#"Expand Order\_Details",{"OrderID", "CustomerID", "EmployeeID", "RequiredDate", "ShippedDate", "ShipVia", "Freight", "ShipName", "ShipAddress", "ShipCity", "ShipRegion", "ShipPostalCode", "ShipCountry", "Customer", "Employee", "Shipper"}) |
| 각 Order\_Details 행에 대한 라인 합계 계산 |InsertedColumn |[Table.AddColumn](https://support.office.com/Article/TableAddColumn-6c64d0a5-9654-4d15-bfb6-9cc380aaf3c0 "Table.AddColumn") <br /> (RemovedColumns, "Custom", each [Order\_Details.UnitPrice] \* [Order\_Details.Quantity]) |

## <a name="task-3-combine-the-products-and-total-sales-queries"></a>작업 3: 제품 및 총 판매액 쿼리 결합
Power BI Desktop에서는 보고하는 쿼리를 결합할 필요가 없습니다. 대신 데이터 집합 간에 **관계** 를 만들 수 있습니다. 데이터 집합에 공통된 모든 열에 이러한 관계를 만들 수 있습니다. 자세한 내용은 [관계 만들기 및 관리](desktop-create-and-manage-relationships.md)를 참조하세요.

이 자습서에서는 공통 'ProductID' 필드를 공유하는 주문 및 제품 데이터를 사용하므로, Power BI Desktop에서 사용하는 모델에 이러한 두 데이터 간의 관계가 있어야 합니다. Power BI Desktop에서 각 테이블의 열이 관련되도록(즉, 같은 값을 가지는 열) 지정하면 됩니다. Power BI Desktop은 관계의 방향 및 카디널리티를 처리합니다. 관계를 자동으로 검색하는 경우도 있습니다.

이 작업에서는 Power BI Desktop에서 **제품** 쿼리와 **총 판매액** 쿼리 간에 관계가 설정되었음을 확인합니다.

### <a name="step-1-confirm-the-relationship-between-products-and-total-sales"></a>1단계: 제품 및 총 판매액 간의 관계 확인
1. 먼저 쿼리 편집기에서 만든 모델을 Power BI Desktop으로 로드해야 합니다. 쿼리 편집기의 **홈** 리본에서 **Close & Load(닫기 및 로드)**를 선택합니다.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_4.png)
2. Power BI Desktop이 두 쿼리에서 데이터를 로드합니다.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/11.png)      
3. 데이터가 로드되면 **홈** 리본에서 **관계 관리** 단추를 선택합니다.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_5.png)
4. **새로 만들기...** 단추를 선택합니다.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_6.png)
5. 관계를 만들려고 하면 관계 하나가 이미 있는 것을 볼 수 있습니다! **관계 만들기** 대화 상자에 표시된 것처럼(음영 처리된 열) 각 쿼리의 **ProductsID** 필드에 이미 설정된 관계가 있습니다.
   
    ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/12.png)
6. Power BI Desktop에서 **취소**를 선택한 다음 **관계** 보기를 선택합니다.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_7.png)
7. 쿼리 간의 관계를 시각화하는 다음과 같은 모습을 볼 수 있습니다.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_8.png)
8. 쿼리에 연결되는 줄에 있는 화살표를 두 번 클릭하면 **관계 편집** 대화 상자가 나타납니다.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_9.png)
9. **취소** 를 선택하여 **관계 편집** 대화 상자를 닫을 것이므로 아무것도 변경할 필요가 없습니다.

## <a name="task-4-build-visuals-using-your-data"></a>작업 4: 데이터를 사용하여 시각적 개체 만들기
Power BI Desktop을 사용하면 다양한 시각화를 만들어 데이터를 파악할 수 있습니다. 여러 페이지로 보고서를 작성할 수 있으며, 각 페이지에 여러 시각 효과가 포함될 수 있습니다. 데이터를 분석하고 이해하는 데 도움이 되도록 시각화를 조작할 수 있습니다. 보고서를 편집하는 방법에 대한 자세한 내용은 [보고서 편집](service-interact-with-a-report-in-editing-view.md)을 참조하세요.

이 작업에서는 이전에 로드한 데이터를 기반으로 하여 보고서를 만듭니다. 필드 창을 사용하여 시각화를 만들 열을 선택합니다.

### <a name="step-1-create-charts-showing-units-in-stock-by-product-and-total-sales-by-year"></a>1단계: 제품별 재고 단위 및 연도별 총 판매액을 보여 주는 차트 만들기
필드 창(필드 창은 화면 오른쪽에 있음)에서 **UnitsInStock** 을 캔버스의 빈 공간으로 끕니다. 테이블 시각화가 만들어집니다. 이제 ProductName을 축 상자(시각화 창의 아래쪽에 있음)로 끕니다. 그런 다음 시각화의 오른쪽 상단 모서리에 있는 스키틀을 사용하여 **정렬 기준 \> UnitsInStock**을 선택합니다.

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/14.png)

**OrderDate** 를 첫 번째 차트 아래의 캔버스로 끈 다음 LineTotal(다시 필드 창에서)을 시각적 개체로 끌고 꺾은선형 차트를 선택합니다. 다음 시각화가 만들어집니다.

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/15.png)

 이제 **ShipCountry**를 캔버스의 오른쪽 위에 있는 공간으로 끕니다. 지리 필드를 선택했기 때문에 지도가 자동으로 만들어졌습니다. 이제 **LineTotal**을 **값** 필드로 끕니다. 지도에서 각 국가를 나타내는 원의 크기가 이제 해당 국가로 배송된 주문의 **LineTotal**을 기준으로 합니다.

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/17.png)

### <a name="step-2-interact-with-your-report-visuals-to-analyze-further"></a>2단계: 추가 분석을 위해 보고서 시각 효과 조작
Power BI Desktop을 사용하면 상호 강조 표시하고 서로를 필터링하여 추가 추세를 표시하는 시각적 개체를 조작할 수 있습니다. 자세한 내용은 [보고서에서 필터링 및 강조 표시](power-bi-reports-filters-and-highlighting.md)를 참조하세요.

1. **Canad****a 가운데에 있는 밝은 파란색 원을 클릭합니다.** 캐나다에 대한 재고(**ShipCountry**) 및 총 주문(**LineTotal**)만 표시하는 다른 시각 효과가 어떻게 필터링되는지 확인합니다.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/18.png)

## <a name="complete-sales-analysis-report"></a>판매 분석 보고서 완료
이러한 모든 단계를 수행하고 나면 Products.xlsx 파일 및 Northwind OData 피드의 데이터를 결합하는 영업 보고서가 작성됩니다. 보고서는 여러 국가의 판매 정보를 분석하는 데 도움이 되는 시각 효과를 보여 줍니다. [여기](http://download.microsoft.com/download/1/4/E/14EDED28-6C58-4055-A65C-23B4DA81C4DE/Analyzing_Sales_Data.pbix)서 이 자습서에 대해 완료된 Power BI Desktop 파일을 다운로드할 수 있습니다.

## <a name="next-steps"></a>다음 단계
* [다른 Power BI Desktop 자습서 참고](http://go.microsoft.com/fwlink/?LinkID=521937)
* [Power BI Desktop 동영상 시청](http://go.microsoft.com/fwlink/?LinkID=519322)
* [Power BI 포럼 방문](http://go.microsoft.com/fwlink/?LinkID=519326)
* [Power BI 블로그 참고](http://go.microsoft.com/fwlink/?LinkID=519327)


