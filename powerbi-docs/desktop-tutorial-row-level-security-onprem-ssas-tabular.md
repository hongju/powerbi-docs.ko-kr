---
title: Analysis Services 테이블 형식 모델을 사용하여 동적 행 수준 보안
description: Analysis Services 테이블 형식 모델을 사용하여 동적 행 수준 보안
author: davidiseminger
ms.reviewer: davidi
editor: davidi
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: tutorial
ms.date: 01/17/2020
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 1b90357aa6d8f66612857e8247a8b48dc2c2c369
ms.sourcegitcommit: 02342150eeab52b13a37b7725900eaf84de912bc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2020
ms.locfileid: "76539627"
---
# <a name="implement-row-level-security-in-an-analysis-services-tabular-model"></a>Analysis Services 테이블 형식 모델에서 행 수준 보안 구현

샘플 데이터 세트를 사용하여 아래 단계를 진행하기 위해 이 자습서는 *Analysis Services 테이블 형식 모델*에서 [**행 수준 보안**](service-admin-rls.md)을 구현하고 Power BI 보고서에서 사용하는 방법을 보여줍니다.

* [AdventureworksDW2012 데이터베이스](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)에서 새 보안 테이블 만들기
* 필요한 팩트 및 차원 테이블을 사용하여 테이블 형식 모델 빌드
* 사용자 역할 및 사용 권한 정의
* *Analysis Services 테이블 형식* 인스턴스에 모델 배포
* 보고서에 액세스하는 사용자에게 맞는 데이터를 표시하는 Power BI Desktop 보고서 작성
* *Power BI 서비스*에 보고서 배포
* 보고서를 기반으로 새 대시보드 만들기
* 동료와 대시보드 공유

이 자습서에는 [AdventureworksDW2012 데이터베이스](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)가 필요합니다.

## <a name="task-1-create-the-user-security-table-and-define-data-relationship"></a>작업 1: 사용자 보안 테이블 만들기 및 데이터 관계 정의

*SSAS(SQL Server Analysis Services) 테이블 형식* 모델을 사용하여 행 수준 동적 보안을 정의하는 방법을 설명하는 여러 문서를 찾을 수 있습니다. 예제에서는 [행 필터를 사용하여 동적 보안 구현](/analysis-services/tutorial-tabular-1200/supplemental-lesson-implement-dynamic-security-by-using-row-filters)을 사용합니다.

여기의 단계에서는 AdventureworksDW2012 관계형 데이터베이스를 사용해야 합니다.

1. AdventureworksDW2012에서 아래와 같이 `DimUserSecurity` 테이블을 만듭니다. [SSMS(SQL Server Management Studio)](/sql/ssms/download-sql-server-management-studio-ssms)를 사용하여 테이블을 만들 수 있습니다.

   ![DimUserSecurity 테이블 만들기](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/createusersecuritytable.png)

1. 테이블을 만들고 저장한 후에는 아래와 같이 `DimUserSecurity` 테이블의 `SalesTerritoryID` 열과 `DimSalesTerritory` 테이블의 `SalesTerritoryKey` 열 간의 관계를 설정해야 합니다.

   SSMS에서 **DimUserSecurity**를 마우스 오른쪽 단추로 클릭하고 **디자인**을 선택합니다. 그런 다음 **테이블 디자이너** > **관계...** 를 선택합니다. 완료되면 테이블을 저장합니다.

   ![외래 키 관계](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/createusersecuritytable_keys.png)

1. 테이블에 사용자를 추가하세요. **DimUserSecurity**를 마우스 오른쪽 단추로 클릭하고 **상위 200개의 행 편집**을 선택합니다. 사용자를 추가하면 `DimUserSecurity` 테이블은 다음 예제와 유사하게 표시됩니다.

   ![예제 사용자를 포함한 DimUserSecurity 테이블](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/createusersecuritytable_users.png)

   이후 작업에서 이러한 사용자를 볼 수 있습니다.

1. 다음으로 사용자 관련 지역 세부 정보를 보여 주는 `DimSalesTerritory` 테이블을 사용하여 *내부 조인*을 수행합니다. 여기에서 SQL 코드는 내부 조인을 수행하고, 이미지는 테이블이 나타나는 방법을 보여줍니다.

    ```sql
    select b.SalesTerritoryCountry, b.SalesTerritoryRegion, a.EmployeeID, a.FirstName, a.LastName, a.UserName from [dbo].[DimUserSecurity] as a join [dbo].[DimSalesTerritory] as b on a.[SalesTerritoryID] = b.[SalesTerritoryKey]
    ```

   조인된 테이블은 2단계에서 만든 관계 덕분에 각 영업 영역에 대한 책임이 있는 사람을 보여 줍니다. 예를 들어 *Rita Santos*가 *오스트레일리아* 담당임을 알 수 있습니다.

## <a name="task-2-create-the-tabular-model-with-facts-and-dimension-tables"></a>작업 2: 팩트 및 차원 테이블을 사용하여 테이블 형식 모델 만들기

관계형 데이터 웨어하우스가 준비되면 테이블 형식 모델을 정의해야 합니다. [SSDT(SQL Server Data Tools)](/sql/ssdt/sql-server-data-tools)를 사용하여 모델을 만들 수 있습니다. 자세한 내용은 [새 테이블 형식 모델 프로젝트 만들기](/sql/analysis-services/lesson-1-create-a-new-tabular-model-project)를 참조하세요.

1. 아래와 같이 필요한 모든 테이블을 모델로 가져옵니다.

    ![데이터 도구와 함께 사용하기 위해 가져온 SQL Server](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/ssdt_model.png)

1. 필요한 테이블을 가져오면 읽기 권한으로 *SalesTerritoryUsers*라는 역할을 정의해야 합니다. SQL Server Data Tools에서 **모델** 메뉴를 선택한 다음, **역할**을 선택합니다. **역할 관리자**에서 **새로 만들기**를 선택합니다.

1. **역할 관리자** 안의 **멤버**에서 [작업 1단계](#task-1-create-the-user-security-table-and-define-data-relationship)의 `DimUserSecurity` 테이블에서 정의한 사용자를 추가합니다.

    ![역할 관리자에서 사용자 추가](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/rolemanager.png)

1. 그런 다음 **행 필터** 탭에 나와있는 것처럼 `DimSalesTerritory` 및 `DimUserSecurity` 테이블 모두에 적절한 함수를 추가합니다.

    ![행 필터에 함수 추가](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/rolemanager_complete.png)

1. `LOOKUPVALUE` 함수는 Windows 사용자 이름이 `USERNAME` 함수가 반환하는 사용자 이름과 일치하는 열에 대한 값을 반환합니다. 그런 다음, `LOOKUPVALUE` 반환된 값이 동일한 또는 관련 테이블의 값과 일치하도록 쿼리를 제한할 수 있습니다. **DAX 필터** 열에서 다음 수식을 입력합니다.

    ```sql
        =DimSalesTerritory[SalesTerritoryKey]=LOOKUPVALUE(DimUserSecurity[SalesTerritoryID], DimUserSecurity[UserName], USERNAME(), DimUserSecurity[SalesTerritoryID], DimSalesTerritory[SalesTerritoryKey])
    ```

    이 수식에서 `LOOKUPVALUE` 함수는 `DimUserSecurity[SalesTerritoryID]` 열의 모든 값을 반환합니다. 여기서 `DimUserSecurity[UserName]`은 현재 로그인한 Windows 사용자 이름과 같으며 `DimUserSecurity[SalesTerritoryID]`는 `DimSalesTerritory[SalesTerritoryKey]`와 동일합니다.

    > [!IMPORTANT]
    > 행 수준 보안을 사용하는 경우 DAX 함수 [USERELATIONSHIP](/dax/userelationship-function-dax)은 지원되지 않습니다.

   그러면 판매 `SalesTerritoryKey`의 `LOOKUPVALUE` 반환된 세트는 `DimSalesTerritory`에 표시된 행을 제한하는 데 사용됩니다. `SalesTerritoryKey` 값이 `LOOKUPVALUE` 함수가 반환하는 ID에 있는 행만 표시됩니다.

1. `DimUserSecurity` 테이블의 경우 **DAX 필터** 열에서 다음 수식을 추가합니다.

    ```sql
        =FALSE()
    ```

    이 수식은 모든 열이 `false`로 해결되도록 지정합니다. 즉 `DimUserSecurity` 테이블 열은 쿼리될 수 없습니다.

이제 모델을 처리하고 배포해야 합니다. 자세한 내용은 [배포](/sql/analysis-services/lesson-13-deploy)를 참조하세요.

## <a name="task-3-add-data-sources-within-your-on-premises-data-gateway"></a>작업 3: 온-프레미스 데이터 게이트웨이 내에서 데이터 원본 추가

테이블 형식 모델이 배포되고 사용 준비가 되면 온-프레미스 Analysis Services 테이블 형식 서버에 데이터 원본 연결을 추가해야 합니다.

1. 온-프레미스 분석 서비스에 대한 Power BI 서비스 액세스를 허용하려면 사용자 환경에 [온-프레미스 데이터 게이트웨이](service-gateway-onprem.md)를 설치하고 구성해야 합니다.

1. 게이트웨이가 올바르게 구성되었으면 *Analysis Services* 테이블 형식 인스턴스에 대한 데이터 원본 연결을 만들어야 합니다. 자세한 내용은 [데이터 원본 관리 - Analysis Services](service-gateway-enterprise-manage-ssas.md)를 참조하세요.

   ![데이터 원본 연결을 만드세요.](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/pbi_gateway.png)

이 프로시저를 완료하여 게이트웨이가 구성되고 온-프레미스 Analysis Services 데이터 원본과 상호 작용할 준비가 되었습니다.

## <a name="task-4-create-report-based-on-analysis-services-tabular-model-using-power-bi-desktop"></a>작업 4: Power BI Desktop을 사용하여 Analysis Services 테이블 형식 모델 기반 보고서 만들기

1. Power BI Desktop을 시작하고, **데이터 가져오기** > **데이터베이스**를 선택합니다.

1. 데이터 원본 목록에서 **SQL Server Analysis Services 데이터베이스**를 선택하고 **연결**을 선택합니다.

   ![SQL Server Analysis Services 데이터베이스에 연결](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/getdata.png)

1. Analysis Services 테이블 형식 인스턴스 세부 정보를 입력하고 **라이브 연결**을 선택합니다. 그런 다음, **확인**을 선택합니다.
  
   ![Analysis Services 세부 정보](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/getdata_connectlive.png)

   Power BI에서 동적 보안은 라이브 연결만을 사용하여 작동합니다.

1. Analysis Services 인스턴스에 배포된 모델이 표시됩니다. 해당 모델을 선택한 다음, **확인**을 선택합니다.

   Power BI Desktop은 이제 **필드** 창의 캔버스 오른쪽에 사용할 수 있는 모든 필드를 표시합니다.

1. **필드** 창에서 **FactInternetSales** 테이블의 **SalesAmount** 측정 및 **SalesTerritory** 테이블의 **SalesTerritoryRegion** 차원을 선택합니다.

1. 이 보고서를 간단하게 유지하기 위해 지금 더 많은 열을 추가하지 않습니다. 좀 더 의미 있는 데이터 표현을 위해 시각화를 **도넛형 차트**로 변경합니다.

   ![도넛형 차트 시각화](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/donut_chart.png)

1. 보고서가 준비되면 Power BI 포털에 직접 게시할 수 있습니다. Power BI Desktop의 리본 메뉴 **홈** 탭에서 **게시**를 선택합니다.

## <a name="task-5-create-and-share-a-dashboard"></a>작업 5: 대시보드 만들기 및 공유

보고서를 만들고 **Power BI** 서비스에 게시했습니다. 이제 이전 단계에서 만든 예제를 사용하여 모델 보안 시나리오를 보여 줄 수 있습니다.

*판매 관리자*역할의 사용자 Grace는 다른 모든 판매 지역의 데이터를 볼 수 있습니다. Grace가 이 보고서를 만들고 Power BI 서비스에 게시합니다. 이 보고서는 이전 작업에서 만들었습니다.

Grace가 보고서를 게시한 후 다음 단계는 해당 보고서를 기준으로 Power BI 서비스에서 *TabularDynamicSec*라는 대시보드를 만드는 것입니다. 다음 그림에서 Grace는 모든 판매 지역에 해당하는 데이터를 볼 수 있습니다.

   ![Power BI 서비스 대시보드](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/donut_chart_1.png)

이제 Grace는 오스트레일리아 지역의 판매 담당인 동료 Rita와 대시보드를 공유합니다.

   ![Power BI 대시보드 공유](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/pbi_dashboard.png)

Rita가 Power BI 서비스에 로그인하여 Grace가 만든 공유 대시보드를 보면 오스트레일리아 지역의 판매량만 표시됩니다.

축하합니다! Power BI 서비스는 온-프레미스 Analysis Services 테이블 형식 모델에 정의된 동적 행 수준 보안을 보여줍니다. Power BI는 `EffectiveUserName` 속성을 사용하여 쿼리를 실행하도록 현재 Power BI 사용자 자격 증명을 온-프레미스 데이터 원본에 전송합니다.

## <a name="task-6-understand-what-happens-behind-the-scenes"></a>작업 6: 내부적으로 수행되는 작업 이해

이 작업은 온-프레미스 SSAS 테이블 형식 인스턴스에서 SQL Server 프로파일러 추적을 캡처해야 하므로 [SQL Server Profiler](/sql/tools/sql-server-profiler/sql-server-profiler)와 익숙하다고 가정합니다.

세션은 사용자(Rita)가 Power BI 서비스의 대시보드에 액세스하는 즉시 초기화됩니다. **salesterritoryusers** 역할이 **<EffectiveUserName>rita@contoso.com</EffectiveUserName>** 의 유효 사용자 이름으로 즉시 적용되는 것을 볼 수 있습니다.

       <PropertyList><Catalog>DefinedSalesTabular</Catalog><Timeout>600</Timeout><Content>SchemaData</Content><Format>Tabular</Format><AxisFormat>TupleFormat</AxisFormat><BeginRange>-1</BeginRange><EndRange>-1</EndRange><ShowHiddenCubes>false</ShowHiddenCubes><VisualMode>0</VisualMode><DbpropMsmdFlattened2>true</DbpropMsmdFlattened2><SspropInitAppName>PowerBI</SspropInitAppName><SecuredCellValue>0</SecuredCellValue><ImpactAnalysis>false</ImpactAnalysis><SQLQueryMode>Calculated</SQLQueryMode><ClientProcessID>6408</ClientProcessID><Cube>Model</Cube><ReturnCellProperties>true</ReturnCellProperties><CommitTimeout>0</CommitTimeout><ForceCommitTimeout>0</ForceCommitTimeout><ExecutionMode>Execute</ExecutionMode><RealTimeOlap>false</RealTimeOlap><MdxMissingMemberMode>Default</MdxMissingMemberMode><DisablePrefetchFacts>false</DisablePrefetchFacts><UpdateIsolationLevel>2</UpdateIsolationLevel><DbpropMsmdOptimizeResponse>0</DbpropMsmdOptimizeResponse><ResponseEncoding>Default</ResponseEncoding><DirectQueryMode>Default</DirectQueryMode><DbpropMsmdActivityID>4ea2a372-dd2f-4edd-a8ca-1b909b4165b5</DbpropMsmdActivityID><DbpropMsmdRequestID>2313cf77-b881-015d-e6da-eda9846d42db</DbpropMsmdRequestID><LocaleIdentifier>1033</LocaleIdentifier><EffectiveUserName>rita@contoso.com</EffectiveUserName></PropertyList>

유효한 사용자 이름 요청에 따라 Analysis Services는 로컬 Active Directory를 쿼리한 후 요청을 실제 `contoso\rita` 자격 증명으로 변환합니다. Analysis Services가 자격 증명을 가져오면 Analysis Services는 사용자가 보고 액세스할 수 있는 권한이 있는 데이터를 반환합니다.

대시보드에서 더 많은 작업이 발생하는 경우, SQL 프로파일러를 사용하여 특정 쿼리가 Analysis Services 테이블 형식 모델에 DAX 쿼리로 돌아오는 것을 볼 수 있습니다. 예를 들어 Rita가 대시보드에서 기본 보고서로 이동하는 경우 다음 쿼리가 발생합니다.

   ![DAX 쿼리가 Analysis Services 모델로 돌아갑니다.](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/profiler1.png)

또한 아래에서 DAX 쿼리가 실행되어 보고서 데이터를 채우는 것을 볼 수 있습니다.
   
   ```sql
   EVALUATE
     ROW(
       "SumEmployeeKey", CALCULATE(SUM(Employee[EmployeeKey]))
     )
   
   <PropertyList xmlns="urn:schemas-microsoft-com:xml-analysis">``
             <Catalog>DefinedSalesTabular</Catalog>
             <Cube>Model</Cube>
             <SspropInitAppName>PowerBI</SspropInitAppName>
             <EffectiveUserName>rita@contoso.com</EffectiveUserName>
             <LocaleIdentifier>1033</LocaleIdentifier>
             <ClientProcessID>6408</ClientProcessID>
             <Format>Tabular</Format>
             <Content>SchemaData</Content>
             <Timeout>600</Timeout>
             <DbpropMsmdRequestID>8510d758-f07b-a025-8fb3-a0540189ff79</DbpropMsmdRequestID>
             <DbPropMsmdActivityID>f2dbe8a3-ef51-4d70-a879-5f02a502b2c3</DbPropMsmdActivityID>
             <ReturnCellProperties>true</ReturnCellProperties>
             <DbpropMsmdFlattened2>true</DbpropMsmdFlattened2>
             <DbpropMsmdActivityID>f2dbe8a3-ef51-4d70-a879-5f02a502b2c3</DbpropMsmdActivityID>
           </PropertyList>
   ```

## <a name="considerations"></a>고려 사항

* Power BI와 온-프레미스 행 수준 보안은 라이브 연결로만 제공됩니다.

* 모델 처리 후 데이터의 변경 내용은 사용자가 Power BI 서비스에서 라이브 연결로 보고서에 액세스하는 데 즉시 사용할 수 있습니다.

