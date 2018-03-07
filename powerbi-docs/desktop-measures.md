---
title: "Power BI Desktop의 측정값 사용"
description: "Power BI Desktop의 측정값"
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
LocalizationGroup: Model your data
ms.openlocfilehash: 2e1aed189f858bee3b1d110df5b91caed88f479b
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/24/2018
---
# <a name="measures-in-power-bi-desktop"></a>Power BI Desktop의 측정값
**Power BI Desktop**에서는 몇 번의 클릭만으로 데이터에 대한 정보를 만들 수 있습니다. 그러나 가장 중요한 질문에 답변하는 데 필요한 모든 정보가 해당 데이터에 포함되지 않은 경우도 있습니다. 이러한 경우 측정값을 사용하면 도움이 될 수 있습니다.

측정값은 합계, 평균, 최소값/최대값, 개수 또는 DAX 수식을 사용하여 사용자가 직접 만든 고급 계산 등 가장 일반적인 데이터 분석에서 사용됩니다. 측정값의 계산된 결과는 보고서 조작에 대한 응답으로 항상 변경되어 빠른 동적 임시 데이터 탐색이 가능합니다. 측정값에 대해 좀 더 자세히 살펴보겠습니다.

## <a name="understanding-measures"></a>측정값 이해
**Power BI Desktop**에서 측정값은 **보고서 뷰** 또는 **데이터 보기**에서 만들고 사용합니다. 사용자가 직접 만든 측정값은 계산기 아이콘과 함께 필드 목록에 나타납니다. 측정값에 원하는 대로 이름을 지정하고 다른 모든 필드처럼 새 시각화나 기존 시각화에 추가할 수 있습니다.

![](media/desktop-measures/measuresinpbid_measinfieldlist.png)

> [!NOTE]
> 대화 상자에서 선택할 수 있는 이미 작성된 측정인 **빠른 측정**에도 관심이 있을 수 있습니다. 자동으로 생성된 DAX 수식을 검토할 수 있으므로 측정을 신속하게 작성하고 DAX 구문을 학습할 수 있는 좋은 방법입니다. [빠른 측정](desktop-quick-measures.md) 문서를 확인하세요.
> 
> 

## <a name="data-analysis-expressions"></a>Data Analysis Expressions
측정값은 수식의 결과를 계산합니다. 고유한 측정값을 만드는 경우 [DAX(Data Analysis Expressions)](https://msdn.microsoft.com/library/gg413422.aspx) 수식 언어를 사용합니다. DAX에는 200개가 넘는 함수, 연산자 및 구문 라이브러리가 포함되어 데이터 분석 결과를 계산하는 측정값을 만들 때 엄청난 유연성을 제공합니다.

DAX 수식은 Excel 수식과 매우 유사합니다. DAX에는 DATE, SUM 및 LEFT와 같이 동일한 함수도 많습니다. 그러나 DAX의 함수는 Power BI Desktop에서처럼 관계형 데이터에서 작동합니다.

## <a name="lets-look-at-an-example"></a>예를 살펴보겠습니다.
Jan은 Contoso의 판매 관리자입니다. Jan은 다음 회계 연도의 대리점 판매 예상액을 제공해달라는 요청을 받았습니다. 따라서 작년의 판매액을 기준으로 예측하기로 결정하고 다음 6개월 동안 예정된 다양한 판촉 활동의 결과로 판매액이 연간 6% 증가할 것으로 판단합니다.

Jan은 예상액을 보고하기 위해 작년의 판매 데이터를 Power BI Desktop으로 가져옵니다. Reseller Sales 테이블에서SalesAmount 필드를 찾습니다. 가져온 데이터에는 작년의 판매액만 포함되어 있으므로 SalesAmount 필드의 이름을 Last Years Sales로 바꿉니다. 그런 다음 Last Years Sales를 보고서 캔버스 위로 끕니다. 해당 필드가 차트 시각화에서 작년의 모든 대리점 판매액의 합계인 단일 값으로 나타납니다.

Jan은 계산을 직접 지정하지 않은 경우에도 자동으로 제공된다는 것을 알게 됩니다. Power BI Desktop에서 Last Years Sales의 값을 모두 합하여 측정값을 직접 만들었습니다.

그러나 Jan은 내년의 판매 예상액을 계산하는 측정값이 필요하며, 이 값은 6% 예상 증가를 고려하여 작년의 판매액에 1.06을 곱한 값을 기준으로 합니다. 이 계산을 위해 직접 측정값을 만듭니다. 새 측정값 기능을 사용하여 새 측정값을 만들고 다음과 같은 DAX 수식을 입력합니다.

    Projected Sales = SUM('Sales'[Last Years Sales])*1.06

그런 다음 새로운 Projected Sales 측정값을 차트로 끌어 놓습니다.

![](media/desktop-measures/measuresinpbid_lastyearsales.png)

이제 Jan은 최소한의 노력으로 매우 신속하게 예상 판매량을 계산하는 측정값을 얻었습니다. 이제 특정 대리점을 필터링하거나 다른 필드를 보고서에 추가하여 예상액을 추가로 분석할 수 있습니다.

## <a name="learn-more"></a>자세히 알아보기
여기서는 측정값에 대해 간략하게 소개만 했지만 직접 만드는 방법을 알아보는 데 도움이 되는 추가 정보가 제공됩니다. [자습서: Power BI Desktop에서 고유한 측정값 만들기](desktop-tutorial-create-measures.md)를 참조하세요. 이 자습서에서는 샘플 파일을 다운로드하여 더 많은 측정값을 만드는 방법에 대한 단계별 학습을 진행할 수 있습니다.  

DAX에 대해 더 자세히 알아보려면 [Power BI Desktop의 DAX 기본 사항](desktop-quickstart-learn-dax-basics.md)을 확인하세요. [DAX(Data Analysis Expressions) 참조](https://msdn.microsoft.com/library/gg413422.aspx)에서는 각 함수, 구문, 연산자 및 명명 규칙에 대한 자세한 문서를 제공합니다. DAX는 Excel 및 SQL Server Analysis Services의 파워 피벗에서 여러 해 동안 사용되었으므로 여러 가지 유용한 리소스도 사용할 수 있습니다. BI 커뮤니티의 영향력 있는 멤버가 DAX에 대한 지식을 공유하는 [DAX 리소스 센터 Wiki](http://social.technet.microsoft.com/wiki/contents/articles/1088.dax-resource-center.aspx)(영문)를 확인하세요.



