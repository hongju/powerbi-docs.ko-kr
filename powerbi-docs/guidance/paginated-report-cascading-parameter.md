---
title: 페이지를 매긴 보고서에서 연계 매개 변수 사용
description: 연계 매개 변수를 사용하여 페이지를 매긴 보고서를 디자인하기 위한 지침
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.date: 01/14/2020
ms.author: v-pemyer
ms.openlocfilehash: 2a8dca43077fe12e4903585e3926cc67fe864136
ms.sourcegitcommit: 3d6b27e3936e451339d8c11e9af1a72c725a5668
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2020
ms.locfileid: "76162414"
---
# <a name="use-cascading-parameters-in-paginated-reports"></a>페이지를 매긴 보고서에서 연계 매개 변수 사용

이 문서에서는 독자가 Power BI [페이지를 매긴 보고서](../paginated-reports-report-builder-power-bi.md)를 디자인하는 보고서 작성자라고 가정하고, 연계 매개 변수를 디자인하는 시나리오를 제공합니다. 연계 매개 변수는 종속성이 있는 보고서 매개 변수입니다. 보고서 사용자가 선택하는 매개 변수 값은 다른 매개 변수에 사용할 수 있는 값을 설정하는 데 사용됩니다.

> [!NOTE]
> 연계 매개 변수에 대한 소개와 구성 방법은 이 문서에서 다루지 않습니다. 연계 매개 변수에 익숙하지 않다면 먼저 [보고서에 연계 매개 변수 추가(보고서 작성기 및 SSRS)](/sql/reporting-services/report-design/add-cascading-parameters-to-a-report-report-builder-and-ssrs)를 읽어 보는 것이 좋습니다.

## <a name="design-scenarios"></a>디자인 시나리오

연계 매개 변수를 사용하는 두 가지 디자인 시나리오가 있습니다. 다음 경우에 효과적으로 사용할 수 있습니다.

- 항목의 _큰 집합_ 필터링
- _관련_ 항목 제공

### <a name="example-database"></a>예시 데이터베이스

이 문서에 나와 있는 예는 Azure SQL Database을 기반으로 합니다. 이 데이터베이스는 영업 작업을 기록하며, 재판매인, 제품, 판매 주문을 저장하는 다양한 테이블을 포함합니다.

**Reseller**라는 테이블은 재판매인마다 하나의 레코드를 저장하며, 수천 개의 레코드를 포함할 수 있습니다. **Reseller** 테이블에는 다음과 같은 열이 있습니다.

- ResellerCode(정수)
- ResellerName
- Country-Region
- State-Province
- City
- PostalCode

**Sales**라는 테이블도 있습니다. 이 테이블은 판매 주문 레코드를 저장하며, **ResellerCode** 열에서 **Reseller** 테이블에 대한 외래 키 관계를 가집니다.

### <a name="example-requirement"></a>예시 요구 사항

재판매인 프로필 보고서를 개발해야 한다는 요구 사항이 있습니다. 보고서는 단일 재판매인의 정보를 표시하도록 디자인되어야 합니다. 보고서 사용자가 재판매인 코드를 입력하도록 하는 것은 적절하지 않습니다. 코드를 기억하는 경우가 드물기 때문입니다.

## <a name="filter-large-sets-of-items"></a>항목의 큰 집합 필터링

재판매인 등 사용 가능한 항목의 큰 집합을 제한하는 데 도움이 되는 세 가지 예를 살펴보겠습니다. 아래에 이 계정과 키의 예제가 나와 있습니다.

- [관련 열을 기준으로 필터링](#filter-by-related-columns)
- [그룹화 열을 기준으로 필터링](#filter-by-a-grouping-column)
- [검색 패턴을 기준으로 필터링](#filter-by-search-pattern)

### <a name="filter-by-related-columns"></a>관련 열을 기준으로 필터링

이 예에서 보고서 사용자는 다섯 개의 보고서 매개 변수와 상호 작용합니다. 사용자는 국가/지역, 시/도, 구/군/시 및 우편 번호를 선택해야 합니다. 그러면 최종 매개 변수가 해당 지리적 위치에 있는 재판매인을 나열합니다.

![그림이 보여 주는 다섯 가지 보고서 매개 변수는 다음과 같습니다. Country-region, State-province, City, Postal Code, Reseller. 처음 네 매개 변수는 값이 설정되어 있으며, 재판매인 목록은 네 개 항목으로만 필터링됩니다.](media/paginated-report-cascading-parameter/filter-by-related-columns-example.png)

다음은 연계 매개 변수를 개발하는 방법입니다.

1. 다섯 가지 보고서 매개 변수를 올바른 순서로 정렬하여 만듭니다.
2. 다음 쿼리 문을 사용하여 고유한 국가/지역 값을 검색하는 **CountryRegion** 데이터 세트를 만듭니다.

    ```sql
    SELECT DISTINCT
      [Country-Region]
    FROM
      [Reseller]
    ORDER BY
      [Country-Region]
    ```

3. 다음 쿼리 문을 사용하여 선택된 국가/지역의 고유한 시/도 값을 검색하는 **StateProvince** 데이터 세트를 만듭니다.

    ```sql
    SELECT DISTINCT
      [State-Province]
    FROM
      [Reseller]
    WHERE
      [Country-Region] = @CountryRegion
    ORDER BY
      [State-Province]
    ```

4. 다음 쿼리 문을 사용하여 선택된 국가/지역 및 시/도의 고유한 구/군/시 값을 검색하는 **City** 데이터 세트를 만듭니다.

    ```sql
    SELECT DISTINCT
      [City]
    FROM
      [Reseller]
    WHERE
      [Country-Region] = @CountryRegion
      AND [State-Province] = @StateProvince
    ORDER BY
      [City]
    ```

5. 이 패턴을 계속하여 **PostalCode** 데이터 세트를 만듭니다.
6. 다음 쿼리 문을 사용하여 선택된 지리적 값의 모든 재판매인을 검색하는 **Reseller** 데이터 세트를 만듭니다.

    ```sql
    SELECT
      [ResellerCode],
      [ResellerName]
    FROM
      [Reseller]
    WHERE
      [Country-Region] = @CountryRegion
      AND [State-Province] = @StateProvince
      AND [City] = @City
      AND [PostalCode] = @PostalCode
    ORDER BY
      [ResellerName]
    ```

7. 첫 번째 데이터 세트를 제외한 각 데이터 세트의 경우, 쿼리 매개 변수를 해당 보고서 매개 변수에 매핑합니다.

> [!NOTE]
> 이 예에 표시된 모든 쿼리 매개 변수(@ 기호가 접두사로 추가됨)는 SELECT 문 내에 포함되거나 저장 프로시저에 전달될 수 있습니다.
>
> 일반적으로 저장 프로시저가 더 나은 디자인 방법입니다. 쿼리 계획을 캐시하여 더 빨리 실행할 수 있고 필요할 때 더 정교한 논리를 개발할 수 있기 때문입니다. 하지만 SQL Server, Oracle, Teradata 등 게이트웨이 관계형 데이터 원본에서는 현재 지원되지 않습니다.
>
> 마지막으로 효율적인 데이터 검색을 지원하기 위해서는 항상 적절한 인덱스가 있는지 확인해야 합니다. 그렇지 않을 경우, 보고서 매개 변수가 채워지는 속도가 느려지고 데이터베이스에 과도한 부담이 될 수 있습니다. SQL Server 인덱싱에 대한 자세한 내용은 [SQL Server 인덱스 아키텍처 및 디자인 가이드](/sql/relational-databases/sql-server-index-design-guide?view=sql-server-2017)를 참조하세요.

### <a name="filter-by-a-grouping-column"></a>그룹화 열을 기준으로 필터링

이 예에서 보고서 사용자는 보고서 매개 변수와 상호 작용하여 재판매인의 첫 번째 문자를 선택합니다. 그런 다음 두 번째 매개 변수는 선택된 문자로 이름이 시작될 때 재판매인을 나열합니다.

![그림이 보여 주는 두 가지 보고서 매개 변수는 다음과 같습니다. Group, Reseller. 첫 번째 매개 변수 값은 문자 A로 설정되고, 재판매인 목록은 해당 문자로 시작하는 여러 항목으로 필터링됩니다.](media/paginated-report-cascading-parameter/filter-by-grouping-column-example.png)

다음은 연계 매개 변수를 개발하는 방법입니다.

1. **ReportGroup** 및 **Reseller** 보고서 매개 변수를 올바른 순서로 정렬하여 만듭니다.
2. 다음 쿼리 문을 사용하여 모든 재판매인이 사용하는 첫 번째 문자를 검색하는 **ReportGroup** 데이터 세트를 만듭니다.

    ```sql
    SELECT DISTINCT
      LEFT([ResellerName], 1) AS [ReportGroup]
    FROM
      [Reseller]
    ORDER BY
      [ReportGroup]
    ```

3. 다음 쿼리 문을 사용하여 선택한 문자로 시작하는 모든 재판매인을 검색하는 **Reseller** 데이터 세트를 만듭니다.

    ```sql
    SELECT
      [ResellerCode],
      [ResellerName]
    FROM
      [Reseller]
    WHERE
      LEFT([ResellerName], 1) = @ReportGroup
    ORDER BY
      [ResellerName]
    ```

4. **Reseller** 데이터 세트의 쿼리 매개 변수를 해당 보고서 매개 변수에 매핑합니다.

**Reseller** 테이블에 그룹화 열을 추가하는 것이 더 효율적입니다. 지속되고 인덱싱되면 이 방법은 최상의 결과를 제공합니다. 자세한 내용은 [Specify Computed Columns in a Table](/sql/relational-databases/tables/specify-computed-columns-in-a-table)을 참조하세요.

```sql
ALTER TABLE [Reseller]
ADD [ReportGroup] AS LEFT([ResellerName], 1) PERSISTED
```

이 방법은 훨씬 더 큰 잠재력을 제공할 수 있습니다. 새 그룹화 열을 추가하여 _미리 정의된 문자 구간_을 기준으로 재판매인을 필터링하는 다음 스크립트를 생각해 보세요. 이 스크립트는 보고서 매개 변수에 필요한 데이터를 효율적으로 검색하는 인덱스도 만듭니다.

```sql
ALTER TABLE [Reseller]
ADD [ReportGroup2] AS CASE
  WHEN [ResellerName] LIKE '[A-C]%' THEN 'A-C'
  WHEN [ResellerName] LIKE '[D-H]%' THEN 'D-H'
  WHEN [ResellerName] LIKE '[I-M]%' THEN 'I-M'
  WHEN [ResellerName] LIKE '[N-S]%' THEN 'N-S'
  WHEN [ResellerName] LIKE '[T-Z]%' THEN 'T-Z'
  ELSE '[Other]'
END PERSISTED
GO

CREATE NONCLUSTERED INDEX [Reseller_ReportGroup2]
ON [Reseller] ([ReportGroup2]) INCLUDE ([ResellerCode], [ResellerName])
GO
```

### <a name="filter-by-search-pattern"></a>검색 패턴을 기준으로 필터링

이 예에서 보고서 사용자는 보고서 매개 변수와 상호 작용하여 검색 패턴을 입력합니다. 그런 다음 두 번째 매개 변수는 이름에 패턴이 포함될 때 재판매인을 나열합니다.

![그림이 보여 주는 두 가지 보고서 매개 변수는 다음과 같습니다. Search, Reseller. 첫 번째 매개 변수 값은 텍스트 “red”로 설정되고, 재판매인 목록은 해당 텍스트를 포함하는 여러 항목으로 필터링됩니다.](media/paginated-report-cascading-parameter/filter-by-search-pattern-example.png)

다음은 연계 매개 변수를 개발하는 방법입니다.

1. **Search** 및 **Reseller** 보고서 매개 변수를 올바른 순서로 정렬하여 만듭니다.
2. 다음 쿼리 문을 사용하여 검색 텍스트를 포함하는 모든 재판매인을 검색하는 **Reseller** 데이터 세트를 만듭니다.

    ```sql
    SELECT
      [ResellerCode],
      [ResellerName]
    FROM
      [Reseller]
    WHERE
      [ResellerName] LIKE '%' + @Search + '%'
    ORDER BY
      [ResellerName]
    ```

3. **Reseller** 데이터 세트의 쿼리 매개 변수를 해당 보고서 매개 변수에 매핑합니다.

> [!TIP]
> 보고서 사용자가 더 많은 것을 제어할 수 있도록 이 디자인을 개선할 수 있습니다. 이를 통해 보고서 사용자는 자체 패턴 일치 값을 정의할 수 있습니다. 예를 들어 검색 값 "red%"는 이름이 문자 “red”로 _시작_하는 재판매인으로 필터링합니다.
>
> 자세한 내용은 [LIKE(Transact-SQL)](/sql/t-sql/language-elements/like-transact-sql?view=sql-server-ver15#using-the--wildcard-character)를 참조하세요.

보고서 사용자가 자체 패턴을 정의할 수 있도록 하는 방법은 다음과 같습니다.

```sql
WHERE
  [ResellerName] LIKE @Search
```

하지만 데이터베이스 전문가가 아닌 많은 사용자는 백분율 (%) 와일드카드 문자에 대해 모릅니다. 대신 별표(*) 문자에 익숙합니다. WHERE 절을 수정하면 이 사용자들이 이 문자를 사용하도록 할 수 있습니다.

```sql
WHERE
  [ResellerName] LIKE SUBSTITUTE(@Search, '%', '*')
```

## <a name="present-relevant-items"></a>관련 항목 제공

이 시나리오에서는 팩트 데이터를 사용하여 사용 가능한 값을 제한할 수 있습니다. 보고서 사용자에게 활동이 기록된 항목이 표시됩니다.

이 예에서 보고서 사용자는 세 가지 보고서 매개 변수와 상호 작용합니다. 처음 두 개는 판매 주문 날짜의 날짜 범위를 설정합니다. 그러면 세 번째 매개 변수가 해당 기간 동안 주문이 생성된 재판매인을 나열합니다.

![그림이 보여 주는 세 가지 보고서 매개 변수는 다음과 같습니다. Start Order Date, End Order Date, Reseller. 두 날짜 매개 변수는 2020년 1월로 설정되고, 재판매인 목록은 이 달 동안 주문한 재판매인을 나타내는 여러 항목으로 필터링됩니다.](media/paginated-report-cascading-parameter/filter-relevant-items-example.png)

다음은 연계 매개 변수를 개발하는 방법입니다.

1. **OrderDateStart**, **OrderDateEnd**, **Reseller** 보고서 매개 변수를 올바른 순서로 정렬하여 만듭니다.
2. 다음 쿼리 문을 사용하여 날짜 기간에 주문을 생성한 모든 재판매인을 검색하는 **Reseller** 데이터 세트를 만듭니다.

    ```sql
    SELECT DISTINCT
      [r].[ResellerCode],
      [r].[ResellerName]
    FROM
      [Reseller] AS [r]
    INNER JOIN [Sales] AS [s]
      ON [s].[ResellerCode] = [r].[ResellerCode]
    WHERE
      [s].[OrderDate] >= @OrderDateStart
      AND [s].[OrderDate] < DATEADD(DAY, 1, @OrderDateEnd)
    ORDER BY
      [r].[ResellerName]
    ```

## <a name="recommendations"></a>권장 사항

가능하면 항상 연계 매개 변수를 사용하여 보고서를 디자인하는 것이 좋습니다. 그 이유는 다음과 같습니다.

- 보고서 사용자에게 직관적이고 유용한 환경을 제공합니다.
- 검색하는 사용 가능한 값 집합이 작기 때문에 효율적입니다.

다음을 수행하여 데이터 원본을 최적화해야 합니다.

- 가능하다면 항상 저장 프로시저 사용
- 효율적인 데이터 검색을 위해 적절한 인덱스 추가
- 열 값 및 행을 구체화하여 비용이 많이 드는 쿼리 시간 평가 방지

## <a name="next-steps"></a>다음 단계

이 문서와 관련된 보다 자세한 내용을 알아보려면 다음 리소스를 참조하세요.

- [Power BI 보고서 작성기의 보고서 매개 변수](../report-builder-parameters.md)
- [보고서에 연계 매개 변수 추가(보고서 작성기 및 SSRS)](/sql/reporting-services/report-design/add-cascading-parameters-to-a-report-report-builder-and-ssrs)
- 질문이 있으십니까? [Power BI 커뮤니티에 질문하세요.](https://community.powerbi.com/)
- 제안? [Power BI 개선을 위한 아이디어 제공](https://ideas.powerbi.com)
