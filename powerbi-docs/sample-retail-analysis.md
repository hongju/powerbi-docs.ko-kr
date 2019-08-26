---
title: 'Power BI의 소매점 분석 샘플: 둘러보기'
description: 'Power BI의 소매점 분석 샘플: 둘러보기'
author: maggiesMSFT
manager: kfile
ms.reviewer: amac
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 07/02/2019
ms.author: maggies
LocalizationGroup: Samples
ms.openlocfilehash: b3adcf3ba97e83875187a11116fdb7b642e5560b
ms.sourcegitcommit: 0e50ebfa8762e19286566432870ef16d242ac78f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/13/2019
ms.locfileid: "68962229"
---
# <a name="retail-analysis-sample-for-power-bi-take-a-tour"></a>Power BI의 소매점 분석 샘플: 둘러보기

소매점 분석 샘플 콘텐츠는 여러 매장과 구역에서 판매된 항목의 소매점 판매 데이터를 분석하는 대시보드, 보고서 및 데이터 세트를 포함합니다. 메트릭은 신규 매장 분석과 함께 올해 성과를 작년의 판매액, 판매 대수, 메츨 총이익 및 차이 면에서 비교합니다. 

![소매점 분석 샘플 대시보드](media/sample-retail-analysis/retail1.png)

이 샘플은 비즈니스 중심 데이터, 보고서 및 대시보드가 포함된 Power BI를 사용하는 방법을 보여 주는 시리즈의 일부입니다. [obviEnce](http://www.obvience.com/)에서 익명화된 실제 데이터로 생성되었습니다. 데이터는 콘텐츠 팩, .pbix Power BI Desktop 파일 또는 Excel 통합 문서 등 여러 형식으로 사용할 수 있습니다. [Power BI용 샘플](sample-datasets.md)을 참조하세요. 

이 자습서에서는 Power BI 서비스의 소매점 분석 샘플 콘텐츠 팩을 살펴봅니다. Power BI Desktop 및 Power BI 서비스의 보고서 환경은 비슷하므로 Power BI Desktop에서 샘플 .pbix 파일을 사용하여 이 자습서를 따라 해도 좋습니다. 

Power BI 라이선스가 없어도 Power BI Desktop의 샘플을 살펴볼 수 있습니다. Power BI Pro 라이선스가 없다면 샘플을 Power BI 서비스의 내 작업 영역에 저장하면 됩니다. 

## <a name="get-the-sample"></a>샘플 가져오기

 이 샘플을 사용하려면 먼저 샘플을 [콘텐츠 팩](#get-the-content-pack-for-this-sample), [.pbix 파일](#get-the-pbix-file-for-this-sample) 또는 [Excel 통합 문서](#get-the-excel-workbook-for-this-sample)로 다운로드해야 합니다.

### <a name="get-the-content-pack-for-this-sample"></a>이 샘플의 콘텐츠 팩 가져오기

1. Power BI 서비스(app.powerbi.com)를 열고 로그인한 다음, 샘플을 저장할 작업 영역을 엽니다. 

    Power BI Pro 라이선스가 없다면 샘플을 내 작업 영역에 저장하면 됩니다.

2. 왼쪽 아래 모서리에서 **데이터 가져오기**를 선택합니다.

    ![데이터 가져오기 선택](media/sample-datasets/power-bi-get-data.png)
3. **데이터 가져오기** 페이지가 표시되면 **샘플**을 선택합니다.
   
4. **소매점 분석 샘플**을 선택한 다음 **연결**을 선택합니다.  
  
   ![샘플에 연결](media/sample-retail-analysis/retail16.png)
   
5. Power BI에서 콘텐츠 팩을 가져온 다음, 새 대시보드, 보고서 및 데이터 세트를 현재 작업 영역에 추가합니다.
   
   ![소매점 분석 샘플 항목](media/sample-retail-analysis/retail-entry.png)
  
### <a name="get-the-pbix-file-for-this-sample"></a>이 샘플의 .pbix 파일 가져오기

또는 소매점 분석 샘플을 Power BI Desktop에서 사용하도록 구성된 [.pbix 파일](http://download.microsoft.com/download/9/6/D/96DDC2FF-2568-491D-AAFA-AFDD6F763AE3/Retail%20Analysis%20Sample%20PBIX.pbix)로서 다운로드할 수도 있습니다. 

### <a name="get-the-excel-workbook-for-this-sample"></a>이 샘플의 Excel 통합 문서 다운로드

이 샘플의 데이터 원본을 보려면 [Excel 통합 문서](http://go.microsoft.com/fwlink/?LinkId=529778)로도 제공됩니다. 통합 문서에는 보고 수정할 수 있는 파워 뷰 시트가 포함됩니다. 원시 데이터를 보려면 데이터 분석 추가 기능을 사용하도록 설정한 다음, **파워 피벗 > 관리**를 선택합니다. 파워 뷰와 파워 피벗 추가 기능을 사용하도록 설정하려면 [내부 Excel 자체에서 Excel 샘플 살펴보기](sample-datasets.md#optional-take-a-look-at-the-excel-samples-from-inside-excel-itself)에서 자세한 내용을 참조하세요.

## <a name="start-on-the-dashboard-and-open-the-report"></a>대시보드 시작 및 보고서 열기

1. 샘플을 저장한 작업 영역에서 **대시보드** 탭을 연 다음 **소매점 분석 샘플** 대시보드를 찾아서 선택합니다. 
2. 대시보드에서 **Total Stores New & Existing Stores**(총 신규 매장 및 기존 매장) 타일을 선택하여 소매점 분석 샘플 보고서에서 **Store Sales Overview**(매장 판매액 개요) 페이지를 엽니다. 

   ![전체 매장 타일](media/sample-retail-analysis/retail-analysis-7.png)  

   이 보고서 페이지에서 총 104개의 매장이 있으며 그중 10개가 신규 매장인 것을 볼 수 있습니다. Fashions Direct 및 Lindseys라는 두 개의 체인이 있습니다. Fashions Direct 매장은 평균적으로 더 큽니다.
3. **This Year Sales by Chain**(체인별 올해 판매액) 원형 차트에서 **Fashions Direct**를 선택합니다.

   ![체인별 올해 판매액 차트](media/sample-retail-analysis/retail3.png)  

   **Total Sales Variance %**(총 판매액 차이 %) 거품형 차트의 결과를 확인합니다.

   ![총 판매액 차이 % 차트](media/sample-retail-analysis/pbi_sample_retanlbubbles.png)  

   **FD-01** 구역은 평균 **제곱 피트당 판매량**이 가장 높고, FD-02는 작년 대비 **총 판매액 차이**가 가장 낮고, FD-03과 FD-04는 전반적으로 실적이 가장 부진합니다.
4. 개별 거품형 차트 또는 다른 차트를 선택하여 선택 항목의 영향을 보여 주는 교차 강조 표시를 확인합니다.
5. 대시보드로 돌아가려면 맨 위 탐색 모음에서 **소매점 분석 샘플**을 선택합니다.

   ![탐색 모음](media/sample-retail-analysis/power-bi-breadcrumbs.png)
6. 대시보드에서 **This Year's Sales New & Existing Stores**(총 신규 매장 및 기존 매장) 타일을 선택합니다. 이 동작은 질문 및 답변 상자에 *This year sales*를 입력하는 것과 같습니다.

   ![올해 판매액 타일](media/sample-retail-analysis/pbi_sample_retanlthisyrsales.png)

   질문 및 답변 결과가 표시됩니다.

   ![질문 및 답변의 올해 판매액](media/sample-retail-analysis/retail7.png)

## <a name="review-a-tile-created-with-power-bi-qa"></a>Power BI 질문 및 답변을 사용하여 만든 타일 검토
보다 자세히 살펴보겠습니다.

1. 질문을 ‘**구역별** 올해 판매액’으로 변경합니다. 결과를 확인합니다. 질문 및 답변이 답변을 가로 막대형 차트에 자동으로 배치하며 다른 구를 제안합니다.

   ![질문 및 답변의 구역별 올해 판매액](media/sample-retail-analysis/retail8.png)
2. 이번에는 질문을 ‘**우편 번호 및 체인별** 올해 판매액’으로 변경합니다.

   질문을 입력함에 따라 Power BI가 질문에 답변하고 적절한 차트를 표시하는 것을 볼 수 있습니다.
3. 더 많은 질문을 입력하여 어떤 결과를 얻을 수 있는지 살펴봅니다.
4. 준비가 되면 대시보드로 돌아갑니다.

## <a name="dive-deeper-into-the-data"></a>데이터를 심층적으로 알아보기
이제 보다 자세한 수준에서 구역의 실적을 살펴보겠습니다.

1. 대시보드에서 **This Year's Sales, Last Year's Sales**(올해 판매액, 작년 판매액) 타일을 선택하면 보고서의 **District Monthly Sales**(구역 월별 판매액) 페이지가 열립니다.

   ![올해 판매액, 작년 판매액 타일](media/sample-retail-analysis/pbi_sample_retanlareacht.png)

   **Total Sales Variance % by Fiscal Month**(회계 월별 총 판매액 차이 %) 차트에서 작년과 비교했을 때 차이 %의 편차가 큰 것을 확인할 수 있으며, 1월, 4월, 7월의 실적이 특히 안 좋은 것을 알 수 있습니다.

   ![회계 월별 총 판매액 차이 % 차트](media/sample-retail-analysis/pbi_sample_retanlsalesvarcol.png)

   문제가 발생할 수 있는 위치의 범위를 좁힐 수 있는지 살펴보겠습니다.
2. 거품형 차트에서 **020-Mens**(020-남성복) 버블을 선택합니다.

   ![020-Mens (020-남성복) 선택](media/sample-retail-analysis/retail11.png)  

   4월에는 남성복 범주가 전체 비즈니스만큼 심각하게 영향을 받지 않았지만, 1월과 7월은 여전히 심각한 달임을 알 수 있습니다.
1. **010-Womens**(010-여성복) 버블을 선택합니다.

   ![010-Womens(010-여성복) 선택](media/sample-retail-analysis/retail12.png)

   여성복 범주는 모든 달에 걸쳐 전체 비즈니스보다 훨씬 부진하며, 전년도보다 거의 모든 달에서 훨씬 부진함을 알 수 있습니다.
1. 다시 거품을 선택하여 필터를 지웁니다.

## <a name="try-out-the-slicer"></a>슬라이서 사용해 보기
특정 구역에서는 어떻게 수행되는지 살펴보겠습니다.

1. 왼쪽 위에 있는 **District Manager**(구역 관리자) 슬라이서에서 **Allan Guinot**을 선택합니다.

   ![Allan Guinot 선택](media/sample-retail-analysis/retail13.png)

   Allan의 구역은 작년보다 3월과 6월의 실적이 우수합니다.
2. **Allan Guinot**이 선택된 상태에서, 거품형 차트에서 **Womens-10**(여성복-10) 버블을 선택합니다.

   ![Allan Guinot 및 Womens-10(여성복-10)이 선택됨](media/sample-retail-analysis/power-bi-allan.png)

   여성복-10 범주의 경우, Allan의 구역이 작년 물량보다 떨어진 것을 볼 수 있습니다.
3. 다른 구역 관리자 및 범주를 살펴봅니다. 또 어떤 인사이트를 찾을 수 있을까요?
4. 준비되면 대시보드로 돌아갑니다.

## <a name="what-the-data-says-about-sales-growth-this-year"></a>데이터는 올해 매출 증가에 대해 어떤 정보를 알려주나요?
마지막으로 살펴볼 영역은 성장입니다. 이번에는 올해에 개업한 신규 매장을 살펴보겠습니다.

1. **Stores Opened This Year by Open Month, Chain**(개업 월, 체인별 올해에 개업한 매장) 타일을 선택하면 보고서의 **New Stores Analysis**(신규 매장 분석) 페이지가 열립니다.

   ![신규 매장 분석 페이지](media/sample-retail-analysis/retail15.png)

   타일에서 알 수 있듯이 올해에는 Lindseys 매장보다 Fashions Direct 매장이 더 많이 개업했습니다.
2. **Sales Per Sq Ft by Name**(이름별 제곱 피트당 판매액) 차트를 살펴봅니다.

   ![이름별 제곱 피트당 판매액 차트](media/sample-retail-analysis/retail14.png)

    신규 매장 간에 제곱 피트당 평균 판매액이 차이가 나는 것을 알 수 있습니다.
3. 오른쪽 위에 있는 **Open Store Count by Open Month and Chain**(개업 월별 및 체인별 개업 매장 수) 차트에서 **Fashions Direct** 범례 항목을 선택합니다. 동일한 체인의 경우에도 최고 매장(Winchester Fashions Direct)과 최하위 매장(Cincinnati 2 Fashions Direct)의 실적이 각각 $21.22 대 $12.86로 최고 매장이 현저하게 우수함을 확인할 수 있습니다.

   ![Fashions Direct가 선택됨](media/sample-retail-analysis/power-bi-lindseys.png)
4. **이름** 슬라이서에서 **Winchester Fashions Direct**를 선택하고 꺾은선형 차트를 살펴봅니다. 첫 번째 판매 수치가 2월에 보고되었습니다.
5. 슬라이서에서 **Cincinnati 2 Fashions Direct**를 클릭합니다. 꺾은선형 차트에서 이 매장은 6월에 개업했으며 실적이 최악인 매장으로 보인다는 사실을 알 수 있습니다.
6. 전체 차트에서 막대형, 꺾은선형 및 거품형 차트를 살펴보며 어떤 인사이트를 발견할 수 있는지 확인합니다.

## <a name="next-steps-connect-to-your-data"></a>다음 단계: 데이터에 연결
이 환경은 변경 내용을 저장하지 않도록 선택할 수 있으므로 안전하게 이용할 수 있습니다. 그러나 변경 내용을 저장하면 언제든지 이 샘플의 새 복사본에 대해 **데이터 가져오기**를 선택할 수 있습니다.

이 둘러보기가 Power BI 대시보드, 질문 및 답변, 보고서를 통해 샘플 데이터를 파악하는 방법을 확인하는 데 도움이 되었기를 바랍니다. 이제 사용자 데이터에 연결할 차례입니다. Power BI를 사용하여 다양한 데이터 원본에 연결할 수 있습니다. 더 자세히 알아보려면 [Power BI 서비스 시작하기](service-get-started.md)를 참조하세요.
