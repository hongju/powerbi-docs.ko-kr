---
title: '자습서: Power BI Desktop에서 Excel 및 OData 피드의 데이터 결합'
description: '자습서: Excel 및 OData 피드의 데이터 결합'
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: tutorial
ms.date: 05/21/2018
ms.author: v-thepet
LocalizationGroup: Learn more
ms.openlocfilehash: 94e40681d065591db008f8a9062d851e0bd83f61
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2019
ms.locfileid: "54285763"
---
# <a name="tutorial-combine-sales-data-from-excel-and-an-odata-feed"></a>자습서: Excel 및 OData 피드의 판매 데이터 결합

한 데이터베이스에 제품 정보가 있고 다른 데이터베이스에 판매 정보가 있는 경우와 같이 데이터가 여러 데이터 원본에 분산되어 있는 것이 일반적입니다. **Power BI Desktop**을 사용하면 서로 다른 원본의 데이터를 결합하여 흥미롭고 매력적인 데이터 분석 및 시각화를 만들 수 있습니다. 

이 자습서에서는 두 가지 데이터 원본(제품 정보가 포함된 Excel 통합 문서 및 주문 데이터가 포함된 OData 피드)의 데이터를 결합하는 방법을 알아봅니다. 각 데이터 세트를 가져와서 변환 및 집계 단계를 수행한 후 두 원본의 데이터를 모두 사용하여 대화형 시각화가 포함된 판매 분석 보고서를 생성합니다. 이러한 방법은 SQL Server 쿼리, CSV 파일 및 Power BI Desktop의 다른 데이터 원본에도 적용할 수 있습니다.

>[!NOTE]
>Power BI Desktop에는 일반적으로 작업을 수행하는 몇 가지 방법이 있습니다. 예를 들어 마우스 오른쪽 단추를 클릭하거나 열 또는 셀에 있는 **추가 옵션** 메뉴를 사용하여 많은 리본을 선택할 수 있습니다. 몇 가지 대체 방법은 아래 단계에 설명되어 있습니다. 

## <a name="import-the-product-data-from-excel"></a>Excel에서 제품 데이터 가져오기

먼저 Excel Products.xlsx 통합 문서에서 Power BI Desktop으로 제품 데이터를 가져옵니다.

1. [Products.xlsx Excel 통합 문서를 다운로드](http://download.microsoft.com/download/1/4/E/14EDED28-6C58-4055-A65C-23B4DA81C4DE/Products.xlsx)하여 **Products.xlsx**로 저장합니다.
   
2. Power BI Desktop 리본의 **홈** 탭에서 **데이터 가져오기** 옆에 있는 드롭다운 화살표를 선택한 다음, **가장 일반적** 드롭다운에서 **Excel**을 선택합니다. 
   
   ![데이터 가져오기](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_1.png)
   
   >[!NOTE]
   >**데이터 가져오기** 항목 자체를 선택하거나 Power BI **시작** 대화 상자에서 **데이터 가져오기**를 선택한 다음, **데이터 가져오기** 대화 상자에서 **Excel** 또는 **파일** > **Excel**을 선택하고 **연결**을 선택할 수도 있습니다.
   
3. **열기** 대화 상자에서 **Products.xlsx** 파일로 이동하여 파일을 선택한 다음, **열기**를 선택합니다.
   
4. **탐색기** 창에서 **Products** 테이블을 선택한 다음 **편집**을 선택합니다.
   
   ![Excel용 탐색기 창](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_2.png)
   
테이블의 미리 보기가 **파워 쿼리 편집기**에서 열리고, 여기에서 변환을 적용하여 데이터를 정리할 수 있습니다. 
   
![파워 쿼리 편집기](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_3.png)
   
>[!NOTE]
>Power BI Desktop의 리본 메뉴 **홈**리본에서 **쿼리 편집**  >  **쿼리 편집**을 선택하거나, **보고서 보기**에서 쿼리 옆에 있는 **추가 옵션**을 마우스 오른쪽 단추로 클릭하거나 선택하고 **쿼리 편집**을 선택하여 **파워 쿼리 편집기**를 열 수도 있습니다.

## <a name="clean-up-the-products-columns"></a>제품 열 정리

결합된 보고서는 Excel 통합 문서의 **ProductID**, **ProductName**, **QuantityPerUnit** 및 **UnitsInStock** 열만 사용하므로 다른 열을 제거할 수 있습니다. 

1. **파워 쿼리 편집기**에서 **ProductID**, **ProductName**, **QuantityPerUnit** 및 **UnitsInStock** 열을 선택합니다(둘 이상의 열을 선택하려면 **Ctrl**+**클릭**을 사용하고, 나란히 있는 열을 선택하려면 **Shift**+**클릭**을 사용).
   
2. 선택한 머리글을 마우스 오른쪽 단추로 클릭하고 드롭다운에서 **다른 열 제거**를 선택하여 테이블에서 선택한 열을 제외한 모든 열을 제거합니다. 
   **홈** 리본 탭의 **열 관리** 그룹에서 **열 제거** > **다른 열 제거**를 선택할 수도 있습니다. 
   
   ![다른 열 제거](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/analyzingsalesdata_removeothercolumns.png)

## <a name="import-the-order-data-from-an-odata-feed"></a>OData 피드에서 주문 데이터 가져오기

그런 다음, 샘플 Northwind 판매 시스템 OData 피드에서 주문 데이터를 가져옵니다. 

1. **파워 쿼리 편집기**에서 **새 원본**을 선택한 다음, **가장 일반적** 드롭다운에서 **OData 피드**를 선택합니다. 
   
   ![OData 가져오기](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/get_odata.png)
   
2. **OData 피드** 대화 상자에 Northwind OData 피드의 URL `http://services.odata.org/V3/Northwind/Northwind.svc/`를 붙여넣고 **확인**을 선택합니다.
   
   ![OData 피드 대화 상자](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/get_odata2.png)
   
3. **탐색기** 창에서 **Orders** 테이블을 선택한 다음, **확인**을 선택하여 데이터를 **파워 쿼리 편집기**로 로드합니다.
   
   ![OData의 탐색기 창](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/analyzingsalesdata_odatafeed.png)
   
   >[!NOTE]
   >**탐색기**에서 확인란을 선택하지 않고 테이블 이름을 선택하여 미리 보기를 표시할 수 있습니다.

## <a name="expand-the-order-data"></a>주문 데이터 확장

관계형 데이터베이스 또는 Northwind OData 피드와 같은 여러 테이블이 있는 데이터 원본에 연결할 때 테이블 간에 참조를 사용하여 쿼리를 빌드할 수 있습니다. **Orders** 테이블에는 여러 관련 테이블에 대한 참조가 있습니다. **확장** 작업을 사용하여 관련 **Order_Details** 테이블의 **ProductID**, **UnitPrice** 및 **Quantity** 열을 대상(**Orders**) 테이블에 추가할 수 있습니다. 

1. **Order_Details** 열을 볼 수 있을 때까지 **Orders** 테이블에서 오른쪽으로 스크롤합니다. 이 열에는 데이터가 아닌 다른 테이블에 대한 참조가 포함되어 있습니다.
   
   ![Order_Details 열](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/7.png)
   
2. **Order_Details** 열 머리글에서 **확장** 아이콘(![확장 아이콘](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/expand.png))을 선택합니다. 
   
3. **확장** 드롭다운에서 다음을 수행합니다.
   
   1. **(모든 열 선택)** 을 선택하여 모든 열을 선택 취소합니다.
      
   2. **ProductID**, **UnitPrice** 및 **Quantity**를 선택한 다음, **확인**을 선택합니다.
      
      ![확장 대화 상자](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/8.png)

**Order_Details** 테이블을 확장한 후 **Order_Details** 열은 중첩 테이블에 있는 세 개의 새로운 열로 바뀌고, 테이블에는 서로 추가된 데이터에 대한 새로운 행이 포함됩니다. 

![확장된 열](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/9.png)

## <a name="create-a-custom-calculated-column"></a>사용자 지정 계산 열 만들기

파워 쿼리 편집기를 사용하면 계산 및 사용자 지정 필드를 만들어 데이터를 보강할 수 있습니다. 단가에 항목 수량을 곱하여 주문의 각 라인 항목에 대한 총 가격을 계산하는 사용자 지정 열을 만듭니다.

1. 파워 쿼리 편집기의 **열 추가** 리본 탭에서 **사용자 지정 열**을 선택합니다.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/10.png)
   
2. **사용자 지정 열** 대화 상자의 **새 열 이름** 필드에 **LineTotal**을 입력합니다.

3. **=** 뒤의 **사용자 지정 열 수식** 필드에 **[Order_Details.UnitPrice]** \* **[Order_Details.Quantity]** 를 입력합니다. (**사용 가능한 열** 스크롤 상자에서 필드 이름을 선택하고 입력하는 대신 **<< 삽입**을 선택할 수도 있습니다.) 
3. **확인**을 선택합니다.
   
   ![사용자 지정 열 대화 상자](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/11.png)

새 **LineTotal** 필드가 **Orders** 테이블의 마지막 열로 나타납니다.

## <a name="set-the-data-type-for-the-new-field"></a>새 필드의 데이터 형식 설정

파워 쿼리 편집기가 데이터에 연결되면 각 필드에 대한 가장 적합한 데이터 형식을 결정하고 그에 따라 데이터를 표시합니다. 머리글에 있는 아이콘으로, 또는 **홈** 리본 탭의 **변환** 그룹에 있는 **데이터 형식** 아래에서 필드에 할당된 데이터 형식을 확인할 수 있습니다. 

새 **LineTotal** 열의 데이터 형식은 **임의**이지만 해당 값은 통화입니다. 데이터 형식을 할당하려면 **LineTotal** 열 머리글을 마우스 오른쪽 단추로 클릭하고, 드롭다운에서 **데이터 형식 변경**을 선택한 다음, **고정 10진수**를 선택합니다. 

![데이터 형식 변경](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/12.png)

>[!NOTE]
>**LineTotal** 열을 선택한 다음, **홈** 리본 탭의 **변환** 영역에서 **데이터 형식** 옆에 있는 드롭다운 화살표를 선택하고, **고정 10진수**를 선택할 수도 있습니다.

## <a name="clean-up-the-orders-columns"></a>주문 열 정리

보고서에서 모델을 더 쉽게 작업할 수 있도록 일부 열을 삭제하고, 이름을 바꾸고, 다시 정렬할 수 있습니다.

보고서에는 **OrderDate**, **ShipCity**, **ShipCountry**, **Order_Details.ProductID**, **Order_Details.UnitPrice** 및 **Order_Details.Quantity** 열만 사용됩니다. 이들 열을 선택하고 Excel 데이터에서 사용한 것처럼 **다른 열 제거**를 사용하거나, 나열된 열을 제외한 모든 열을 선택하고 선택한 열 중 하나를 마우스 오른쪽 단추로 클릭한 다음, **열 제거**를 선택하여 선택한 열을 모두 제거할 수 있습니다. 

열 이름에서 *Order_Details.* 접두사를 제거하면 **Order_Details.ProductID**, **Order_Details.UnitPrice** 및 **Order_Details.Quantity** 열을 더 쉽게 식별할 수 있습니다. 열 이름을 각각 **ProductID**, **UnitPrice** 및 **Quantity**로 바꾸려면:

1. 각 열 머리글을 두 번 클릭하거나 길게 탭하거나, 열 머리글을 마우스 오른쪽 단추로 클릭하고 드롭다운에서 **이름 바꾸기**를 선택합니다. 
2. 각 이름에서 *Order_Details.* 를 삭제한 다음, **Enter** 키를 누릅니다.

마지막으로 **LineTotal** 열에 더 쉽게 액세스할 수 있도록 열을 왼쪽으로 끌어서 **ShipCountry** 열의 바로 오른쪽에 놓습니다.

![정리된 테이블](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/14.png)

## <a name="review-the-query-steps"></a>쿼리 단계 검토

파워 쿼리 편집기에서 데이터를 셰이핑하고 변환할 때 각 단계가 파워 쿼리 편집기의 오른쪽에 있는 **쿼리 설정** 창의 **적용된 단계** 영역에 기록되었습니다. 적용된 단계를 통해 이전 단계로 돌아가서 변경한 내용을 검토하고, 필요한 경우 변경 내용을 편집, 삭제 또는 다시 정렬할 수 있습니다(단, 이전 단계를 변경하면 이후 단계가 중단될 수 있으므로 이 작업은 위험할 수 있음). 

파워 쿼리 편집기의 왼쪽에 있는 **쿼리** 목록에서 각 쿼리를 선택하고 **쿼리 설정**에서 **적용된 단계**를 검토합니다. 이전 데이터 변환을 적용한 후 두 개의 쿼리에 대한 적용된 단계는 다음과 같이 표시됩니다.

![제품 쿼리 적용된 단계](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/15.png) &nbsp;&nbsp; ![주문 쿼리 적용된 단계](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/17.png)

>[!TIP]
>적용된 단계의 기초는 **M** 언어라고도 하는 **파워 쿼리 언어**로 작성된 수식입니다. 수식을 보고 편집하려면 리본 메뉴의 [홈] 탭에 있는 **쿼리** 그룹에서 **고급 편집기**를 선택합니다. 

## <a name="import-the-transformed-queries"></a>변환된 데이터 가져오기

변환된 데이터에 만족하면 **홈** 리본 탭의 **닫기** 그룹에서 **닫기 및 적용** > **닫기 및 적용**을 선택하여 데이터를 Power BI Desktop 보고서 보기로 가져옵니다. 

![닫기 및 적용](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_4.png)

데이터가 로드되면 해당 쿼리가 Power BI Desktop 보고서 보기의 **필드** 목록에 나타납니다.

![필드 목록의 쿼리](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/18.png)

## <a name="manage-the-relationship-between-the-datasets"></a>데이터 세트 간의 관계 관리

Power BI Desktop에서는 보고하는 쿼리를 결합할 필요가 없습니다. 그러나 공통적인 필드를 기반으로 데이터 세트 간의 관계를 사용하여 보고서를 확장하고 보강할 수 있습니다. Power BI Desktop에서 관계를 자동으로 검색하거나, 사용자가 Power BI Desktop **관계 관리** 대화 상자에서 관계를 만들 수 있습니다. Power BI Desktop의 관계에 대한 자세한 내용은 [관계 만들기 및 관리](desktop-create-and-manage-relationships.md)를 참조하세요.

이 자습서의 주문 및 제품 데이터 세트는 공통 *ProductID* 필드를 공유하므로 해당 열을 기반으로 데이터 세트 간에 관계가 있습니다. 

1. Power BI Desktop 보고서 보기에서 **홈** 리본 탭의 **관계** 영역에 있는 **관계 관리**를 선택합니다.
   
   ![관계 관리 리본](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_5.png)
   
2. **관계 관리** 대화 상자에서 Power BI Desktop이 Products 및 Orders 테이블 간의 활성 관계를 이미 검색하여 나열했음을 알 수 있습니다. 관계를 보려면 **편집**을 선택합니다. 
   
   ![관계 관리 대화 상자](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_6.png)
   
   관계에 대한 세부 정보를 표시하는 **관계 편집** 대화 상자가 열립니다.  
   
   ![관계 편집 대화 상자](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_7.png)
   
3. Power BI Desktop이 관계를 올바르게 자동 검색했으므로 **취소**, **닫기**를 차례로 선택하여 관계 대화 상자를 종료할 수 있습니다.

Power BI Desktop 창의 왼쪽에 있는 **관계** 보기를 선택하여 쿼리 간의 관계를 보고 관리할 수도 있습니다. 두 개의 쿼리를 연결하는 선에서 화살표를 두 번 클릭하여 **관계 편집** 대화 상자를 열고 관계를 보거나 변경합니다. 

![관계 보기](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_8.png)

관계 보기에서 보고서 보기로 돌아가려면 **보고서 보기** 아이콘을 선택합니다. 

![보고서 보기 아이콘](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_9.png)

## <a name="create-visualizations-using-your-data"></a>데이터를 사용하여 시각화 만들기

Power BI Desktop 보고서 보기에서 다양한 시각화를 만들어 데이터 인사이트를 파악할 수 있습니다. 여러 페이지로 보고서를 빌드할 수 있으며, 각 페이지에 여러 시각 효과가 포함될 수 있습니다. 본인과 다른 사용자가 데이터를 분석하고 이해하는 데 도움이 되도록 시각화를 조작할 수 있습니다. Power BI 서비스(사이트)에서 보고서를 보고 편집하는 방법에 대한 자세한 내용은 [보고서 편집](service-interact-with-a-report-in-editing-view.md)을 참조하세요.

데이터 집합 및 데이터 집합 간의 관계를 둘 다 사용하여 판매 데이터를 시각화하고 분석할 수 있습니다. 

먼저 두 쿼리의 필드를 사용하여 주문한 각 제품의 수량을 표시하는 누적 세로 막대형 차트를 만듭니다. 

1. 오른쪽의 **필드** 창에 있는 **Orders**에서 **Qunatity** 필드를 선택하거나 캔버스의 빈 공간으로 끌어옵니다. 그러면 주문한 모든 제품의 총 수량을 표시하는 누적 세로 막대형 차트가 만들어집니다. 
   
2. **필드** 창의 **Products**에서 **ProductName**을 선택하거나 차트로 끌어오면 주문한 각 제품의 수량이 표시됩니다. 
   
3. 가장 많은 주문부터 가장 적은 주문 순서로 제품을 정렬하려면 시각화의 오른쪽 위에 있는 **추가 옵션** 줄임표(**...**)를 선택한 다음, **내림차순 정렬, 정렬기준 &gt; Quantity**를 선택합니다.
   
4. 차트의 모서리에 있는 핸들을 사용하여 더 많은 제품 이름이 표시되도록 차트를 확대합니다. 
   
   ![ProductName별 수량 가로 막대형 차트](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/19.png)

다음으로는 시간(**OrderDate**)에 따라 주문 금액(**LineTotal**)을 보여주는 차트를 만듭니다. 

1. 캔버스에서 아무것도 선택하지 않은 상태로 **필드** 창의 **Orders**에서 **LineTotal**을 선택하거나 캔버스의 빈 공간으로 끌어옵니다. 누적 세로 막대형 차트에 모든 주문의 총 금액이 표시됩니다. 
   
2. 차트를 선택한 상태에서 **Orders**에서 **OrderDate**를 선택하거나 차트로 끌어옵니다. 이제 차트에 각 주문 날짜의 라인 합계가 표시됩니다. 
   
3. 더 많은 데이터를 보려면 모서리를 끌어 시각화 크기를 조정합니다. 
   
   ![OrderDate 꺾은선형 차트별 LineTotal](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/20.png)
   
   >[!TIP]
   >차트에서 연도만(세 개의 데이터 요소만) 보이면 **시각화** 창의 **축** 필드에서 **OrderDate** 옆의 화살표를 드롭다운하고 **날짜 계층** 대신 **OrderDate**를 선택합니다. 

마지막으로 각 국가의 주문 금액을 표시하는 맵 시각화를 만듭니다. 

1. 캔버스에서 아무것도 선택하지 않은 상태로 **필드** 창의 **Orders**에서 **ShipCountry**를 선택하거나 캔버스의 빈 공간으로 끌어옵니다. Power BI Desktop은 데이터가 국가 이름인지 검색하고 주문이 있던 각 국가에 대한 데이터 요소를 포함하는 맵 시각화를 자동으로 만듭니다. 
   
2. 데이터 요소의 크기에 각 국가의 주문 금액을 반영하려면 **LineTotal** 필드를 맵으로 끌어오거나, **시각화** 창의 아래쪽 절반에 있는 **크기** 아래 **데이터 필드를 여기에 끌어오기**로 필드를 끌어옵니다. 이제 맵에 있는 원 크기에 각 국가의 주문 금액이 반영됩니다. 
   
   ![ShipCountry 맵 시각화에 의한 LineTotal](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/21.png)

## <a name="interact-with-your-report-visuals-to-analyze-further"></a>추가 분석을 위해 보고서 시각적 개체 조작

Power BI Desktop을 사용하면 상호 강조 표시하고 서로를 필터링하는 시각적 개체를 조작하여 추가 추세를 표시할 수 있습니다. 자세한 내용은 [보고서에서 필터링 및 강조 표시](power-bi-reports-filters-and-highlighting.md)를 참조하세요. 

쿼리 간의 관계로 인해 하나의 시각화 조작은 페이지의 다른 모든 시각화에 영향을 줍니다. 

맵 시각화에서 **캐나다** 가운데에 있는 원을 선택합니다. 다른 두 개의 시각화는 캐나다의 라인 합계 및 주문 수량을 강조 표시하도록 필터링됩니다.

![캐나다에 대해 필터링된 판매 데이터](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/22.png)

**ProductName별 수량** 차트에서 제품 중 하나를 선택하면 맵 및 날짜 차트가 해당 제품의 데이터를 반영하도록 필터링되고, **OrderDate별 LineTotal** 차트에서 날짜 중 하나를 선택하면 맵 및 제품 차트가 해당 날짜의 데이터를 표시하도록 필터링됩니다. 
>[!TIP]
>선택을 취소하려면 다시 선택하거나 다른 시각화 중 하나를 선택합니다. 

## <a name="complete-the-sales-analysis-report"></a>판매 분석 보고서 완료

완료된 보고서는 서로 다른 국가, 시간 프레임 및 제품에 대한 주문 정보를 분석하는 데 도움이 되는 시각적 개체의 Northwind OData 피드 및 Products.xlsx Excel 파일의 데이터를 결합합니다. 보고서가 준비되면 [Power BI 서비스에 업로드](desktop-upload-desktop-files.md)하여 다른 Power BI 사용자와 공유할 수 있습니다.

## <a name="next-steps"></a>다음 단계
* [다른 Power BI Desktop 자습서 참고](http://go.microsoft.com/fwlink/?LinkID=521937)
* [Power BI Desktop 동영상 시청](http://go.microsoft.com/fwlink/?LinkID=519322)
* [Power BI 포럼 방문](http://go.microsoft.com/fwlink/?LinkID=519326)
* [Power BI 블로그 참고](http://go.microsoft.com/fwlink/?LinkID=519327)