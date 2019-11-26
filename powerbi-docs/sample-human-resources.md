---
title: '인적 자원 샘플: 둘러보기'
description: Power BI용 인적 자원 샘플 둘러보기
author: maggiesMSFT
ms.reviewer: amac
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 07/05/2019
ms.author: maggies
LocalizationGroup: Samples
ms.openlocfilehash: 3f0c95673bd6a9a5af2a828869f38d32440b617a
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2019
ms.locfileid: "73858856"
---
# <a name="human-resources-sample-for-power-bi-take-a-tour"></a>Power BI용 인적 자원 샘플 둘러보기

인적 자원 샘플 콘텐츠 팩에는 인사 관리 부서용 대시보드, 보고서 및 데이터 세트가 포함되어 있습니다. 이 샘플에서 인사 관리 부서는 업종이나 규모가 다른 경우에도 여러 회사에서 동일한 보고 모델을 갖습니다. 이 샘플에서는 신규 채용자, 근무 중인 직원, 퇴사 직원을 살펴봅니다. 채용 전략의 추세를 파악하기 위해 노력합니다. 주요 목표는 다음을 이해하는 것입니다.

* 채용자
* 채용 전략의 편향
* 자발적 이직의 추세

![인적 자원 샘플의 대시보드](media/sample-human-resources/hr1.png)

이 샘플은 비즈니스 중심 데이터, 보고서 및 대시보드가 포함된 Power BI를 사용하는 방법을 보여 주는 시리즈의 일부입니다. [obviEnce](http://www.obvience.com/)에서 익명화된 실제 데이터로 생성되었습니다. 데이터는 콘텐츠 팩, .pbix Power BI Desktop 파일 또는 Excel 통합 문서 등 여러 형식으로 사용할 수 있습니다. [Power BI용 샘플](sample-datasets.md)을 참조하세요. 

이 자습서에서는 Power BI 서비스의 인적 자원 샘플 콘텐츠 팩을 살펴봅니다. Power BI Desktop 및 Power BI 서비스의 보고서 환경은 비슷하므로 Power BI Desktop에서 샘플 .pbix 파일을 사용하여 이 자습서를 따라 해도 좋습니다. 

Power BI 라이선스가 없어도 Power BI Desktop의 샘플을 살펴볼 수 있습니다. Power BI Pro 라이선스가 없다면 샘플을 Power BI 서비스의 내 작업 영역에 저장하면 됩니다. 

## <a name="get-the-sample"></a>샘플 가져오기

이 샘플을 사용하려면 먼저 샘플을 [콘텐츠 팩](#get-the-content-pack-for-this-sample), [.pbix 파일](#get-the-pbix-file-for-this-sample) 또는 [Excel 통합 문서](#get-the-excel-workbook-for-this-sample)로 다운로드해야 합니다.

### <a name="get-the-content-pack-for-this-sample"></a>이 샘플의 콘텐츠 팩 가져오기

1. Power BI 서비스(app.powerbi.com)를 열고 로그인한 다음, 샘플을 저장할 작업 영역을 엽니다.

   Power BI Pro 라이선스가 없다면 샘플을 내 작업 영역에 저장하면 됩니다.

2. 왼쪽 아래 모서리에서 **데이터 가져오기**를 선택합니다.
   
   ![데이터 가져오기 선택](media/sample-datasets/power-bi-get-data.png)
3. **데이터 가져오기** 페이지가 표시되면 **샘플**을 선택합니다.
   
4. **인적 자원 샘플**을 선택한 다음, **연결**을 선택합니다.  
   
   ![샘플에 연결](media/sample-human-resources/pbi_hr_sample_connect.png)

5. Power BI에서 콘텐츠 팩을 가져온 다음, 새 대시보드, 보고서 및 데이터 세트를 현재 작업 영역에 추가합니다.
   
   ![인적 자원 샘플 항목](media/sample-human-resources/hr-sample-entry.png)
  
### <a name="get-the-pbix-file-for-this-sample"></a>이 샘플의 .pbix 파일 가져오기

또는 Power BI Desktop에 사용하도록 설계된 [.pbix 파일](https://download.microsoft.com/download/6/9/5/69503155-05A5-483E-829A-F7B5F3DD5D27/Human%20Resources%20Sample%20PBIX.pbix)로 인적 자원 샘플을 다운로드할 수 있습니다.

### <a name="get-the-excel-workbook-for-this-sample"></a>이 샘플의 Excel 통합 문서 다운로드

이 샘플의 데이터 원본을 보려면 [Excel 통합 문서](https://go.microsoft.com/fwlink/?LinkId=529780)로도 제공됩니다. 통합 문서에는 보고 수정할 수 있는 파워 뷰 시트가 포함됩니다. 원시 데이터를 보려면 데이터 분석 추가 기능을 사용하도록 설정한 다음, **파워 피벗 > 관리**를 선택합니다. 파워 뷰와 파워 피벗 추가 기능을 사용하도록 설정하려면 [내부 Excel 자체에서 Excel 샘플 살펴보기](sample-datasets.md#optional-take-a-look-at-the-excel-samples-from-inside-excel-itself)에서 자세한 내용을 참조하세요.

## <a name="new-hires"></a>신입
먼저 신규 채용자를 살펴보겠습니다.

1. 작업 영역에서 **대시보드** 탭을 선택하고 **인적 자원 샘플** 대시보드를 엽니다.
2. 대시보드에서 **월별 신규 채용자 수, 작년의 같은 기간 신규 채용자 수, 근무 중인 YoY 변경 비율** 타일을 선택합니다.  

   ![신규 채용자 수 타일](media/sample-human-resources/hr2.png)  

   인적 자원 샘플 보고서가 **신규 채용자** 페이지에 열립니다.  

   ![신규 채용자 페이지](media/sample-human-resources/hr3.png)

3. 관심 있는 항목을 살펴봅니다.

    * **월별 신규 채용자 수, 신규 채용자 SPLY 및 근무 중인 YoY 변경 비율** 콤보 차트는 작년에 비해 올해 매달 더 많은 직원을 고용했습니다. 일부 월의 직원이 상당히 더 많습니다.
    * **지역 및 민족별 신규 채용자 수와 근무 중인 직원 수**콤보 차트에서 **동부** 지역의 사람을 거의 채용하지 않았음을 알았습니다.
    * **연령대별 신규 채용자 수 YoY Var** 폭포 차트에서는 주로 젊은 직원을 채용하고 있음을 알 수 있습니다. 이 추세는 업무가 대체로 파트타임이기 때문입니다.
    * **성별 신규 채용자 수** 원형 차트는 대체로 균등하게 나뉘어 있음을 보여 줍니다.

    더 많은 인사이트를 알 수 있나요? 예를 들어 성비가 고르지 않은 지역을 확인해 봅니다. 

4. 연령, 성별, 지역 및 인종 그룹 간 관계를 살펴보려면 차트에서 다른 연령대 그룹과 성별을 선택하세요.

5. 맨 위 탐색 창에서 **인적 자원 샘플**을 선택하여 대시보드로 돌아갑니다.

   ![대시보드로 돌아가기](media/sample-human-resources/power-bi-breadcrumbs.png)

## <a name="compare-currently-active-and-former-employees"></a>현재 근무 중인 직원과 전 직원 비교
현재 근무 중인 직원과 회사를 떠난 직원의 데이터를 살펴보겠습니다.

1. 대시보드에서 **연령대별 근무 중인 직원 수** 타일을 선택합니다.

   ![연령대별 근무 직원 수 타일](media/sample-human-resources/pbi_hr_sample_activepie.png)

   인적 자원 샘플 보고서가 **Active Employees vs. Separations**(근무 중인 직원 수와 퇴사한 직원 수 비교) 페이지에 열립니다.  

   ![근무 중인 직원 수와 퇴사한 직원 수 비교 페이지](media/sample-human-resources/hr5.png)

 2. 관심 있는 항목을 살펴봅니다.

    * 왼쪽의 두 콤보 차트는 근무 중인 직원과 퇴사한 직원의 연도별 변화를 나타냅니다. 올해 급속한 채용으로 근무 중인 직원이 더 많지만 지난해보다 퇴사한 직원도 더 많습니다.
    * 8월에는 다른 달에 비해 더 많은 퇴사자가 있었습니다. 다른 연령대, 성별 또는 지역을 선택하면 이상 값을 확인할 수 있습니다.
    * 원형 차트를 보면 성별과 연령대별로 근무 중인 직원이 고르게 나뉜 것을 알 수 있습니다. 연령대별로 다른 성별 구분을 확인하려면 다른 연령대를 선택합니다. 모든 연령대에서 성별이 고르게 분포되어 있습니까?

## <a name="reasons-for-separation"></a>퇴사 사유
편집용 보기에서 보고서를 살펴보겠습니다. 근무 중인 직원 데이터 대신 퇴사한 직원 데이터를 표시하도록 원형 차트를 변경할 수 있습니다.

1. 왼쪽 위에서 **보고서 편집** 을 선택합니다.

2. **연령대별 근무 중인 직원 수** 원형 차트를 선택합니다.

3. **필드**에서 **직원**을 선택하여 **직원** 테이블을 확장합니다. **근무 중인 직원 수**를 선택 취소하여 해당 필드를 제거합니다.

4. **직원** 테이블에서 **퇴사 수**를 선택하여 **필드** 영역의 **값** 상자에 추가합니다.

5. 보고서 캔버스에서 **퇴사 이유** 막대형 차트에서 **자발적** 막대를 선택합니다. 

   이 막대에는 보고서에서 자발적으로 남아 있는 직원 수가 다른 시각적 개체로 강조 표시됩니다.

6. **연령대별 퇴사 직원 수** 원형 차트에서 50+ 조각을 선택합니다.

7. 오른쪽 아래에서 꺾은선형 차트를 살펴봅니다. 이 차트가 필터링되어 자발적 퇴사를 표시합니다.  

   ![퇴사한 직원 50명 초과](media/sample-human-resources/pbi_hr_sample_sepsover50.png)

   50+ 연령대의 추세를 확인합니다. 올해 하반기에는 자발적으로 퇴사한 50세 이상 직원이 더 많습니다. 이 추세에 대해서는 추가적인 데이터 조사가 필요합니다.

8. **성별 근무 중인 직원 수** 원형 차트에 대해서도 동일한 단계를 따라 근무 중인 직원 대신 퇴사로 변경할 수 있습니다. 다른 상세 정보를 파악하기 위해 성별별 자발적 퇴사 데이터를 살펴봅니다.

9. 맨 위 탐색 창에서 **인적 자원 샘플**을 선택하여 대시보드로 돌아갑니다. 보고서에 대한 변경 사항을 저장할 수 있습니다.

## <a name="bad-hires"></a>잘못된 채용
마지막으로 살펴볼 영역은 잘못된 채용입니다. 잘모된 채용은 60일 이상 근무하지 않은 직원으로 정의합니다. 신속하게 채용하고 있지만, 적절한 후보를 채용하고 있을까요?

1. **Bad Hires as % of Actives by Age Group** (연령대별 근무 중인 직원 중 잘못된 채용 %) 대시보드 타일을 선택합니다. 이 보고서는 세 번째 탭인 **잘못된 고용** 탭으로 열립니다.

   ![연령대별 근무 중인 직원 중 잘못된 채용 % 타일](media/sample-human-resources/hr7.png)  
2. 왼쪽에 있는 **지역** 슬라이서에서 **북서부**를 선택하고 **성별에 따른 잘못된 채용** 도넛형 차트에서 **남성** 조각을 선택합니다. **잘못된 채용** 페이지에서 다른 차트를 살펴봅니다. 잘못된 채용은 여성보다 남성에서 많으며 그룹 A 잘못된 채용이 많습니다.

   ![북서부 잘못된 채용](media/sample-human-resources/pbi_hr_sample_badhirespage.png)  

3. **성별 잘못된 채용 수** 도넛형 차트를 살펴보고 **지역** 슬라이서에서 서로 다른 지역을 선택하면, 동부 지역이 남성보다 여성 잘못된 채용이 더 많은 유일한 지역임을 알 수 있습니다.  

4. 맨 위 탐색 창에서 대시보드의 이름을 선택하여 대시보드로 돌아갑니다.

## <a name="ask-a-question-in-the-dashboard-qa-box"></a>대시보드 질문 및 답변 상자에서 질문하기
대시보드의 [질문 및 답변 질문 상자](power-bi-tutorial-q-and-a.md)에서 자연어를 사용하여 데이터에 대한 질문을 할 수 있습니다. 질문 및 답변에서 사용자가 입력한 단어를 인식하고 답변이 있는 데이터 세트의 위치를 찾아냅니다.

1. 질문과 대답 질문 상자를 선택합니다. 입력을 시작하기 전에도 질문 및 답변이 제안과 함께 질문 형성을 돕습니다.

   ![질문 및 답변 상자 제안](media/sample-human-resources/pbi_hr_sample_qabox.png)

2. 이러한 제안 사항 중 하나를 선택하거나 다음을 입력할 수 있습니다. *지역이 동부인 연령 그룹, 성별 및 잘못된 용 SPLY 표시*  

   ![질문 및 답변 상자 답변](media/sample-human-resources/pbi_hr_sample_qa_answer.png)

   잘못된 여성 채용의 대부분이 30세 미만임을 알 수 있습니다.

## <a name="next-steps-connect-to-your-data"></a>다음 단계: 데이터에 연결
이 환경은 변경 내용을 저장하지 않도록 선택할 수 있으므로 안전하게 이용할 수 있습니다. 그러나 변경 내용을 저장하면 언제든지 이 샘플의 새 복사본에 대해 **데이터 가져오기**를 선택할 수 있습니다.

이 둘러보기가 Power BI 대시보드, 질문 및 답변, 보고서를 통해 샘플 데이터를 파악하는 방법을 확인하는 데 도움이 되었기를 바랍니다. 이제 사용자 데이터에 연결할 차례입니다. Power BI를 사용하여 다양한 데이터 원본에 연결할 수 있습니다. 더 자세히 알아보려면 [Power BI 서비스 시작하기](service-get-started.md)를 참조하세요.
