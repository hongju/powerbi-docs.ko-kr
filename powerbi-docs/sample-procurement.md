---
title: '조달 분석 샘플: 둘러보기'
description: 'Power BI의 조달 분석 샘플: 둘러보기'
author: maggiesMSFT
ms.reviewer: amac
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 07/02/2019
ms.author: maggies
LocalizationGroup: Samples
ms.openlocfilehash: 0998ebec15a4e02262ab54a3b08593a65f37af4e
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2019
ms.locfileid: "73873867"
---
# <a name="procurement-analysis-sample-for-power-bi-take-a-tour"></a>Power BI의 조달 분석 샘플: 둘러보기

조달 분석 샘플 콘텐츠 팩은 범주 및 위치별로 공급업체에 대한 제조 회사의 지출을 분석하는 대시보드, 보고서 및 데이터 세트를 포함합니다. 이 샘플에서는 다음 영역을 탐색합니다.

* 최상위 공급업체
* 가장 많이 지출하는 범주
* 최고 할인을 제공하는 공급업체 및 시기

![조달 분석 샘플 대시보드](media/sample-procurement/procurement1.png)

이 샘플은 비즈니스 중심 데이터, 보고서 및 대시보드가 포함된 Power BI를 사용하는 방법을 보여 주는 시리즈의 일부입니다. [obviEnce](http://www.obvience.com/)에서 익명화된 실제 데이터로 생성되었습니다. 데이터는 콘텐츠 팩, .pbix Power BI Desktop 파일 또는 Excel 통합 문서 등 여러 형식으로 사용할 수 있습니다. [Power BI용 샘플](sample-datasets.md)을 참조하세요. 

이 자습서에서는 Power BI 서비스의 조달 분석 샘플 콘텐츠 팩을 살펴봅니다. Power BI Desktop 및 Power BI 서비스의 보고서 환경은 비슷하므로 Power BI Desktop에서 샘플 .pbix 파일을 사용하여 이 자습서를 따라 해도 좋습니다. 

Power BI 라이선스가 없어도 Power BI Desktop의 샘플을 살펴볼 수 있습니다. Power BI Pro 라이선스가 없다면 샘플을 Power BI 서비스의 내 작업 영역에 저장하면 됩니다. 

## <a name="get-the-sample"></a>샘플 가져오기

이 샘플을 사용하려면 먼저 샘플을 [콘텐츠 팩](#get-the-content-pack-for-this-sample), [.pbix 파일](#get-the-pbix-file-for-this-sample) 또는 [Excel 통합 문서](#get-the-excel-workbook-for-this-sample)로 다운로드해야 합니다.

### <a name="get-the-content-pack-for-this-sample"></a>이 샘플의 콘텐츠 팩 가져오기

1. Power BI 서비스(app.powerbi.com)를 열고 로그인한 다음, 샘플을 저장할 작업 영역을 엽니다. 

    Power BI Pro 라이선스가 없다면 샘플을 내 작업 영역에 저장하면 됩니다.

2. 왼쪽 아래 모서리에서 **데이터 가져오기**를 선택합니다.

    ![데이터 가져오기 선택](media/sample-datasets/power-bi-get-data.png)
3. **데이터 가져오기** 페이지가 표시되면 **샘플**을 선택합니다.

4. **조달 분석 샘플**을 선택한 다음 **연결**을 선택합니다.  
  
   ![샘플에 연결](media/sample-procurement/procurement1a.png)
   
5. Power BI에서 콘텐츠 팩을 가져온 다음, 새 대시보드, 보고서 및 데이터 세트를 현재 작업 영역에 추가합니다.
   
   ![조달 분석 샘플 항목](media/sample-procurement/procurement-entry.png)
  
### <a name="get-the-pbix-file-for-this-sample"></a>이 샘플의 .pbix 파일 가져오기

또는 조달 분석 샘플을 Power BI Desktop에서 사용하도록 구성된 [.pbix 파일](https://download.microsoft.com/download/D/5/3/D5390069-F723-413B-8D27-5888500516EB/Procurement%20Analysis%20Sample%20PBIX.pbix)로서 다운로드할 수도 있습니다. 

### <a name="get-the-excel-workbook-for-this-sample"></a>이 샘플의 Excel 통합 문서 다운로드

이 샘플의 데이터 원본을 보려면 [Excel 통합 문서](https://go.microsoft.com/fwlink/?LinkId=529784)로도 제공됩니다. 통합 문서에는 보고 수정할 수 있는 파워 뷰 시트가 포함됩니다. 원시 데이터를 보려면 데이터 분석 추가 기능을 사용하도록 설정한 다음, **파워 피벗 > 관리**를 선택합니다. 파워 뷰와 파워 피벗 추가 기능을 사용하도록 설정하려면 [내부 Excel 자체에서 Excel 샘플 살펴보기](sample-datasets.md#optional-take-a-look-at-the-excel-samples-from-inside-excel-itself)에서 자세한 내용을 참조하세요.


## <a name="spending-trends"></a>지출 추세
먼저 범주 및 위치별 지출 추세를 살펴보겠습니다.  

1. 샘플을 저장한 작업 영역에서 **대시보드** 탭을 연 다음 **조달 분석 샘플** 대시보드를 찾아서 선택합니다. 
2. **Total Invoice by Country/Region**(국가/지역별 전체 송장) 대시보드 타일을 선택하면 **조달 분석 샘플** 보고서의 **지출 개요** 페이지가 열립니다.

    ![지출 개요 페이지](media/sample-procurement/procurement2.png)

다음 세부 정보를 참고하세요.

* **Total Invoice by Month and Category**(월별 및 범주별 전체 송장) 꺾은선형 차트에서 **직접** 범주의 지출은 일관되며 **물류**는 12월 지출이 가장 높고 **기타**는 2월이 가장 높습니다.
* **Total Invoice by Country/Region**(국가/지역별 전체 송장) 지도에서 지출 대부분이 미국에 속합니다.
* **Total Invoice by Sub Category**(하위 범주별 전체 송장) 세로 막대형 차트에서 **하드웨어** 및 **간접 상품 및 서비스**가 가장 큰 지출 범주입니다.
* **Total Invoice by Tier**(계층별 전체 송장) 막대형 차트에서 대부분 비즈니스는 계층 1(상위 10) 공급업체와 이루어집니다. 이것은 공급업체 관계 관리에 도움이 됩니다.

## <a name="spending-in-mexico"></a>멕시코에서의 지출
멕시코의 지출 영역을 살펴보겠습니다.

1. **Total Invoice by Country/Region**(국가/지역별 전체 송장) 지도에서 **멕시코** 버블을 선택합니다. **Total Invoice by Sub Category**(하위 범주별 전체 송장) 세로 막대형 차트에서 지출 대부분이 **간접 상품 및 서비스** 하위 범주에 속합니다.

   ![지출 개요 페이지에서 멕시코를 선택합니다.](media/sample-procurement/pbi_procsample_spendmexico.png)
2. **Indirect Goods & Services**(간접 상품 및 서비스) 열로 드릴다운합니다.

   * **Total Invoice by Sub Category**(하위 범주별 전체 송장) 차트에서 차트 오른쪽 위에 있는 드릴다운 화살표 ![드릴다운 화살표](media/sample-procurement/pbi_drilldown_icon.png)를 선택합니다.
   * **Indirect Goods & Services**(간접 상품 및 서비스) 열을 선택합니다.

      보시다시피 가장 큰 지출은 **Sales & Marketing**(판매 및 마케팅) 하위 범주에 속합니다.
   * 지도에서 **멕시코** 를 다시 선택합니다.

      멕시코의 경우 가장 큰 지출은 **유지 관리 및 보수** 하위 범주에 속합니다.

      ![멕시코 간접 상품 및 서비스 드릴다운](media/sample-procurement/pbi_procsample_drill_mexico.png)
3. 차트의 왼쪽 위에서 위쪽 화살표를 선택하여 다시 드릴업합니다.
4. 드릴다운 화살표를 다시 선택하면 드릴다운이 해제됩니다.  
5. 맨 위 탐색 창에서 **조달 분석 샘플**을 선택하여 대시보드로 돌아갑니다.

## <a name="evaluate-different-cities"></a>다른 도시 평가
강조 표시를 사용하여 다른 도시를 평가할 수 있습니다.

1. **Total Invoice, Discount % By Month**(전체 송장, 월별 할인 %) 대시보드 타일을 선택하면 **조달 분석 샘플** 보고서의 **할인 분석** 페이지가 열립니다.
2. **Total Invoice by City**(도시별 전체 송장) 트리 맵에서 각 도시를 차례로 선택하여 비교합니다. 거의 모든 마이애미 송장의 출처는 계층 1 공급업체입니다.

   ![도시 vs 계층별 % 할인](media/sample-procurement/pbi_procsample_miamitreemap2.png)

## <a name="vendor-discounts"></a>공급업체 할인
공급업체에서 제공하는 할인과 가장 큰 할인을 받는 시기도 살펴보겠습니다.
* 할인율이 월마다 다른가요, 아니면 매달 동일한가요?
* 일부 도시가 다른 도시보다 할인율이 더 큰가요?

![할인 분석 페이지](media/sample-procurement/procurement4.png)

### <a name="discount-by-month"></a>월별 할인
**Total Invoice and Discount % by Month** (전체 송장 및 월별 할인 %) 콤보 차트를 살펴보면 2월이 가장 바쁜 달이고 9월이 가장 덜 바쁜 달입니다. 

2월과 9월의 할인율을 살펴보면, 규모가 커지면 할인이 줄고 규모가 줄면 할인이 높아집니다. 할인을 더 받을수록 거래는 악화됩니다.

![전체 송장 및 월별 할인 % 차트](media/sample-procurement/procurement5.png)

### <a name="discount-by-city"></a>도시별 할인
살펴볼 또 다른 영역은 도시별 할인입니다. 트리 맵의 각 도시를 차례로 선택하여 다른 차트가 어떻게 변화하는지 확인합니다.

* 세인트루이스는 2월에 전체 송장이 크게 높았으며 4월에는 할인 절약이 크게 떨어졌습니다.
* 멕시코시티가 할인율이 가장 높았고(11.05%) 애틀랜타가 가장 적었습니다(0.08%).

![멕시코시티 할인 그래프](media/sample-procurement/procurement6.png)

### <a name="edit-the-report"></a>보고서 편집
왼쪽 위에서 **보고서 편집**을 선택하고 편집용 보기에서 검색합니다.

* 페이지가 구성되는 방법을 살펴봅니다.
* 동일한 데이터를 기반으로 페이지 및 차트를 추가합니다.
* 차트의 시각화 유형을 변경하세요. 예를 들어 트리 맵을 도넛형 차트로 변경합니다.
* 차트를 대시보드에 고정합니다.

## <a name="next-steps-connect-to-your-data"></a>다음 단계: 데이터에 연결
이 환경은 변경 내용을 저장하지 않도록 선택할 수 있으므로 안전하게 이용할 수 있습니다. 그러나 변경 내용을 저장하면 언제든지 이 샘플의 새 복사본에 대해 **데이터 가져오기**를 선택할 수 있습니다.

이 둘러보기가 Power BI 대시보드, 질문 및 답변, 보고서를 통해 샘플 데이터를 파악하는 방법을 확인하는 데 도움이 되었기를 바랍니다. 이제 사용자 데이터에 연결할 차례입니다. Power BI를 사용하여 다양한 데이터 원본에 연결할 수 있습니다. 더 자세히 알아보려면 [Power BI 서비스 시작하기](service-get-started.md)를 참조하세요.

