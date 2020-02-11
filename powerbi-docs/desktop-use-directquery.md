---
title: Power BI Desktop에서 DirectQuery 사용
description: Power BI Desktop에서 DirectQuery(라이브 연결이라고도 함) 사용
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/29/2020
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 90721b059958e59cfd74f9ba1d0d25617a7438e6
ms.sourcegitcommit: 8b300151b5c59bc66bfef1ca2ad08593d4d05d6a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/30/2020
ms.locfileid: "76889285"
---
# <a name="use-directquery-in-power-bi-desktop"></a>Power BI Desktop에서 DirectQuery 사용
*Power BI Desktop*을 사용하면 데이터 원본에 연결할 때 항상 데이터의 복사본을 Power BI Desktop으로 가져올 수 있습니다. 일부 데이터 원본의 경우 DirectQuery를 사용하여 데이터 원본에 직접 연결하는 것과 같은 다른 방법을 사용할 수 있습니다.

## <a name="supported-data-sources"></a>지원되는 데이터 원본
DirectQuery를 지원하는 데이터 원본의 전체 목록을 보려면 [DirectQuery에서 지원하는 데이터 원본](power-bi-data-sources.md)을 참조하세요.

## <a name="how-to-connect-using-directquery"></a>DirectQuery를 사용하여 연결하는 방법
**데이터 가져오기**를 사용하여 DirectQuery에서 지원하는 데이터 원본에 연결하는 경우 연결 대화 상자에서 연결할 방법을 선택할 수 있습니다. 예를 들어 Power BI Desktop의 **홈** 리본에서 **데이터 가져오기** > **SQL Server**를 선택합니다. **SQL Server 데이터베이스** 대화 상자의 **데이터 연결 모드**는 **가져오기** 및 **DirectQuery** 옵션을 보여 줍니다.

![가져오기 및 DirectQuery 옵션, SQL Server 데이터베이스 대화 상자, Power BI Desktop](media/desktop-use-directquery/directquery_sqlserverdb.png)

**가져오기**와 **DirectQuery** 선택 간의 차이점은 다음과 같습니다.

- **가져오기**: 선택한 테이블 및 열을 Power BI Desktop에 가져옵니다. 시각화를 만들거나 상호 작용할 때 Power BI Desktop은 가져온 데이터를 사용합니다. 초기 가져오기 또는 최신 새로 고침 이후의 기본 데이터 변경 내용을 확인하려면 데이터를 새로 고쳐 전체 데이터 세트를 다시 가져와야 합니다.

- **DirectQuery**: Power BI Desktop에 데이터를 가져오거나 복사하지 않습니다. 관계형 원본의 경우 선택한 테이블 및 열이 **필드** 목록에 표시됩니다. SAP Business Warehouse와 같은 다차원 원본의 경우 선택한 큐브의 차원 및 측정값이 **필드** 목록에 나타납니다. 시각화를 만들거나 조작하는 경우 Power BI Desktop은 기본 데이터 원본을 쿼리하므로 항상 현재 데이터를 볼 수 있습니다.

여러 데이터 모델링 및 데이터 변환은 몇 가지 제한 사항이 있기는 하지만 DirectQuery를 사용하는 경우 사용 가능합니다. 시각화를 만들거나 조작하는 경우 기본 원본을 쿼리해야 합니다. 시각화를 새로 고치는 데 필요한 시간은 기본 데이터 원본의 성능에 따라 달라집니다. 요청에 서비스를 제공하는 데 필요한 데이터가 최근에 요청된 경우 Power BI Desktop은 최신 데이터를 사용하여 시각화를 표시하는 데 필요한 시간을 줄입니다. **홈** 리본에서 **새로 고침**을 선택하면 모든 시각화가 최신 데이터로 새로 고쳐집니다.

[Power BI 및 DirectQuery](desktop-directquery-about.md) 문서에는 DirectQuery가 자세히 설명되어 있습니다. DirectQuery를 사용하는 경우의 이점과 제한 사항, 중요 고려 사항에 대한 자세한 내용은 다음 섹션을 참조하세요.

## <a name="benefits-of-using-directquery"></a>DirectQuery 사용의 이점
DirectQuery를 사용하는 경우 다음과 같은 몇 가지 이점이 있습니다.

- DirectQuery를 사용하면 매우 큰 데이터 세트에 대한 시각화를 빌드할 수 있습니다. 그렇지 않으면 사전 집계를 사용하여 모든 데이터를 처음 가져오는 작업을 실행할 수 없습니다.
- 기본 데이터 변경에 데이터 새로 고침이 필요할 수 있습니다. 일부 보고서의 경우 현재 데이터를 표시하려면 대용량 데이터 전송이 필요할 수 있습니다. 이 경우 데이터를 다시 가져올 수 없습니다. 이와 반대로 DirectQuery 보고서는 항상 현재 데이터를 사용합니다.
- DirectQuery에는 1GB 데이터 세트 제한이 적용되지 ‘않습니다’. 

## <a name="limitations-of-directquery"></a>DirectQuery의 제한 사항
현재 DirectQuery 사용에는 다음과 같은 몇 가지 제한 사항이 있습니다.

- [복합 모델](desktop-composite-models.md)을 사용하지 않는 한, 모든 테이블은 단일 데이터베이스에서 가져와야 합니다.

- **쿼리 편집기** 쿼리가 너무 복잡하면 오류가 발생합니다. 오류를 수정하려면 **쿼리 편집기**에서 문제가 되는 단계를 삭제하거나 DirectQuery를 사용하지 않고 데이터를 ‘가져옵니다’.  SAP Business Warehouse와 같은 다차원 원본의 경우 **쿼리 편집기**가 없습니다.

- 시간 인텔리전스 기능은 DirectQuery에서 사용할 수 없습니다. 예를 들어 DirectQuery 모드에서는 날짜 열(예: 년, 분기, 월 또는 일)에 대한 특별 작업이 지원되지 않습니다.

- 기본 데이터 원본에 전송된 쿼리의 성능이 적절한지 확인하기 위해 측정값에서 허용되는 DAX 식에 제한 사항이 적용됩니다.

- 프리미엄 용량을 사용하지 않는 한, DirectQuery를 사용할 때 데이터 반환이 100만 행으로 제한됩니다. 이 제한은 DirectQuery를 사용하여 반환되는 데이터 세트를 만드는 데 사용하는 집계나 계산에는 영향을 주지 않습니다. 반환되는 행에만 영향을 줍니다. 프리미엄 용량은 [이 게시물](https://powerbi.microsoft.com/blog/five-new-power-bi-premium-capacity-settings-is-available-on-the-portal-preloaded-with-default-values-admin-can-review-and-override-the-defaults-with-their-preference-to-better-fence-their-capacity/)에 설명된 대로 최대 행 제한을 설정할 수 있습니다. 

    예를 들어 데이터 원본에서 실행되는 쿼리를 사용하여 천만 개의 행을 집계할 수 있습니다. 반환되는 Power BI 데이터의 행이 백만 개 미만인 경우 쿼리는 DirectQuery를 사용하여 정확히 해당 집계의 결과를 Power BI에 반환합니다. DirectQuery에서 100만 개 이상의 행이 반환되는 경우 Power BI가 오류를 반환합니다(프리미엄 용량을 사용하지 않고 행 수가 관리자 설정 제한에 도달한 경우).

## <a name="important-considerations-when-using-directquery"></a>DirectQuery를 사용하는 경우 중요 고려 사항
DirectQuery를 사용하는 경우 다음 세 가지 사항을 고려해야 합니다.

- **성능 및 부하**: 모든 DirectQuery 요청은 원본 데이터베이스로 전송되므로 필요한 시각적 개체 새로 고침 시간은 백 엔드 원본이 해당하는 한 개 또는 여러 개의 쿼리 결과를 응답하는 데 걸리는 시간에 따라 달라집니다. 시각적 개체에 대한 DirectQuery 사용에 권장되는 응답 시간(요청된 데이터를 반환하는 시간 포함)은 5초 이하이며, 최대 권장 시간은 30초입니다. 더 긴 경우 보고서를 사용하는 사용자의 경험은 크게 저하됩니다. 보고서가 Power BI 서비스에 게시되면 몇 분 이상 걸린 모든 쿼리는 제한 시간이 초과되고 사용자는 오류를 받게 됩니다.
  
    원본 데이터베이스에 대한 로드는 게시된 보고서를 사용하는 Power BI 사용자의 수에 따라 고려해야 합니다. **RLS(행 수준 보안)** 사용도 상당한 영향을 미칠 수 있습니다. 여러 사용자가 공유하는 비RLS 대시보드 타일은 데이터베이스에 대해 단일 쿼리를 생성합니다. 하지만 대시보드 타일에서 RLS를 사용하는 것은 일반적으로 타일을 새로 고치는 데 ‘사용자당’ 하나의 쿼리가 필요하므로 원본 데이터베이스의 부하가 크게 증가하고 성능에 영향을 줄 수 있음을 의미합니다. 
  
    Power BI는 최대한 효율적으로 쿼리를 만듭니다. 그러나 특정 상황에서 생성된 쿼리는 효율성이 부족하여 새로 고침 실패를 방지하지 못할 수 있습니다. 이러한 상황의 예로, 생성된 쿼리가 백 엔드 데이터 원본에서 과도하게 많은 수의 행을 검색하는 경우가 있습니다. 이런 경우 다음 오류가 발생합니다.

    ```output
    The resultset of a query to external data source has exceeded
    ```
  
    이 상황은 집계 옵션이 **요약하지 않음**으로 설정된 매우 높은 카디널리티 열을 포함하는 간단한 차트로 발생할 수 있습니다. 시각적 개체에는 카디널리티가 백만 개 미만인 열만 있어야 하거나 적절한 필터가 적용되어야 합니다.

- **보안**: 기본적으로 게시된 보고서를 사용하는 모든 사용자는 Power BI 서비스에 게시 후 입력한 자격 증명을 사용하여 백 엔드 데이터 원본에 연결합니다. 이 프로세스는 가져온 데이터의 경우에도 동일합니다. 모든 사용자는 백 엔드 원본에 정의된 보안 규칙에 관계없이 동일한 데이터를 봅니다.

    DirectQuery 원본을 사용하여 사용자별 보안이 구현되도록 하려는 고객은 RLS를 사용하거나 원본에 대해 Kerberos 제한 인증을 구성해야 합니다. 모든 원본에 대해 Kerberos를 사용할 수는 없습니다. [RLS에 대해 자세히 알아보세요](service-admin-rls.md). [DirectQuery의 Kerberos에 대해 자세히 알아보세요](service-gateway-sso-kerberos.md).

- **지원되는 기능**: Power BI Desktop의 일부 기능은 DirectQuery 모드에서 지원되지 않거나 제한 사항이 있습니다. Power BI 서비스의 일부 기능(예: ‘빠른 인사이트’)도 DirectQuery를 사용하는 데이터 세트에는 사용할 수 없습니다.  DirectQuery 사용 여부를 결정하는 경우 이러한 기능 제한 사항을 고려해야 합니다.

## <a name="publish-to-the-power-bi-service"></a>Power BI 서비스에 게시
DirectQuery를 사용하여 만든 보고서는 Power BI 서비스에 게시할 수 있습니다.

사용되는 데이터 원본에 **온-프레미스 데이터 게이트웨이**(**Azure SQL Database**, **Azure SQL Data Warehouse** 또는 **Redshift**)가 필요하지 않은 경우 자격 증명을 제공해야 게시된 보고서가 Power BI 서비스에 표시됩니다. 다음 지침에 따라 자격 증명을 제공합니다.

1. [Power BI](https://www.powerbi.com/)에 로그인합니다.
2. Power BI 서비스에서 **설정** 톱니 바퀴형 아이콘을 선택하고 **설정** 메뉴 항목을 선택합니다.

    ![설정, Power BI 서비스](media/desktop-use-directquery/directquery_pbiservicesettings.png)

3. Power BI 서비스의 **설정** 페이지에서 **데이터 세트** 탭을 선택하고 DirectQuery를 사용하는 데이터 세트를 선택한 후 **자격 증명 편집**을 선택합니다.

4. 자격 증명을 추가합니다. 그렇지 않으면 게시된 보고서를 열거나 DirectQuery 연결을 사용하여 만든 데이터 세트를 탐색할 때 오류가 발생합니다.

DirectQuery를 사용하는 **Azure SQL Database**, **Azure SQL Data Warehouse** 및 **Redshift** 이외의 데이터 원본에 대해 데이터 연결을 설정하려면 **온-프레미스 데이터 게이트웨이**를 설치하고 데이터 원본을 등록합니다. 자세한 내용은 [온-프레미스 데이터 게이트웨이란?](service-gateway-onprem.md)을 참조하세요.

## <a name="next-steps"></a>다음 단계
DirectQuery에 대한 자세한 내용은 다음 리소스를 참조하세요.

- [Power BI의 DirectQuery 사용](desktop-directquery-about.md)
- [DirectQuery에서 지원하는 데이터 원본](power-bi-data-sources.md)
- [DirectQuery 및 SAP BW(Business Warehouse)](desktop-directquery-sap-bw.md)
- [DirectQuery 및 SAP HANA](desktop-directquery-sap-hana.md)
- [온-프레미스 데이터 게이트웨이란?](service-gateway-onprem.md)
