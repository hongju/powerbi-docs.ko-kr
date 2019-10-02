---
title: '자습서:  Power BI에서 기계 학습 모델 빌드(미리 보기)'
description: 이 자습서에서는 Power BI에서 기계 학습 모델을 빌드합니다.
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.custom: connect-to-services
ms.topic: tutorial
ms.date: 03/29/2019
ms.author: davidi
LocalizationGroup: Connect to services
ms.openlocfilehash: 611d6f6c923e6cb68af94840c4266a0b6dee7651
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "61407201"
---
# <a name="tutorial-build-a-machine-learning-model-in-power-bi-preview"></a>자습서:  Power BI에서 기계 학습 모델 빌드(미리 보기)

이 자습서 문서에서는 **자동화된 Machine Learning**을 사용하여 Power BI에서 이진 예측 모델을 만들고 적용합니다. 자습서에는 Power BI 데이터 흐름을 만들기 위한 지침과 데이터 흐름에 정의된 엔터티를 사용하여 Power BI에서 직접 기계 학습 모델을 학습하고 유효성을 검사하는 지침이 포함되어 있습니다. 그런 다음 점수 매기기에 해당 모델을 사용하여 예측을 생성합니다.

먼저, 이진 예측 기계 학습 모델을 만들어 온라인 세션 특성 집합을 기반으로 하는 온라인 쇼핑객의 구매 의도를 예측합니다. 이 연습에 벤치 마크 기계 학습 데이터 세트가 사용됩니다. 모델을 학습한 후에는 Power BI에서 모델 결과를 설명하는 유효성 검사 보고서를 자동으로 생성합니다. 그런 다음 유효성 검사 보고서를 검토하고 데이터에 모델을 적용하여 점수를 매길 수 있습니다.

이 자습서는 다음 단계로 구성됩니다.

> [!div class="checklist"]
> * 입력 데이터를 사용하여 데이터 흐름 만들기
> * 기계 학습 모델 만들기 및 학습
> * 모델 유효성 검사 보고서 검토
> * 데이터 흐름 엔터티에 모델 적용
> * Power BI 보고서에서 모델의 점수가 매겨진 출력 사용

## <a name="create-a-dataflow-with-the-input-data"></a>입력 데이터를 사용하여 데이터 흐름 만들기

이 자습서의 첫 번째 부분에서는 입력 데이터를 사용하여 데이터 흐름을 만듭니다. 다음 섹션에 표시된 것 처럼 이 프로세스는 데이터 가져오기부터 시작하여 몇 가지 단계를 수행합니다.

### <a name="get-data"></a>데이터 가져오기

데이터 흐름을 만드는 첫 번째 단계는 데이터 원본을 준비하는 것입니다. 이 경우 온라인 세션 집합에서 기계 학습 데이터 세트를 사용하며, 이 중 일부는 구매로 이어집니다. 데이터 세트에는 모델을 학습하는 데 사용할 해당 세션에 대한 특성 집합이 포함되어 있습니다.

데이터 세트는 UC Irvine 웹 사이트에서 다운로드할 수 있습니다.  또한 이 자습서의 목적을 위해 다음 링크에서도 이를 사용할 수 있습니다. [online_shoppers_intention.csv](https://raw.githubusercontent.com/santoshc1/PowerBI-AI-samples/master/Tutorial_AutomatedML/online_shoppers_intention.csv).

### <a name="create-the-entities"></a>엔터티 만들기

데이터 흐름에 엔터티를 만들려면 Power BI 서비스에 로그인하고, 사용하도록 설정된 AI 미리 보기가 있는 전용 용량의 작업 영역으로 이동합니다.

작업 영역이 아직 없는 경우 Power BI 서비스의 왼쪽 탐색 메뉴에서 **작업 영역**을 선택하여 작업 영역을 만든 다음, 표시되는 패널의 맨 아래에 있는 **앱 작업 영역 만들기**를 선택합니다. 오른쪽에 작업 영역 세부 정보를 입력하는 패널이 열립니다. 작업 영역 이름을 입력하고 **고급**을 선택합니다. 작업 영역에서 라디오 단추를 사용하여 전용 용량을 사용하는지 확인하고 AI 미리 보기가 설정된 전용 용량 인스턴스에 할당되었는지 확인합니다. 그런 다음, **저장**을 선택합니다.

![작업 영역 만들기](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-01.png)

작업 영역을 만든 후에는 다음 그림에 표시된 것처럼 시작 화면의 오른쪽 아래에서 **건너뛰기**를 선택할 수 있습니다.

![작업 영역이 있는 경우 건너뛰기](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-02.png)

**데이터 흐름(미리 보기)** 탭을 선택합니다. 작업 영역의 오른쪽 위에 있는 **만들기** 단추를 선택하고 **데이터 흐름**을 선택합니다.

![데이터 흐름 만들기](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-03.png)

**새 엔터티 추가**를 선택합니다. 그러면 브라우저에서 **파워 쿼리** 편집기가 시작됩니다.

![새 엔터티 추가](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-04.png)

다음 그림에 표시된 것처럼 **텍스트/CSV 파일**을 데이터 원본으로 선택합니다.

![텍스트/CSF 파일이 선택됨](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-05.png)

다음에 표시되는 **데이터 원본에 연결**에서 *online_shoppers_intention.csv*에 대한 다음 링크를 **파일 경로 또는 URL** 상자에 붙여넣은 후 **다음**을 선택합니다.

`https://raw.githubusercontent.com/santoshc1/PowerBI-AI-samples/master/Tutorial_AutomatedML/online_shoppers_intention.csv`

![파일 경로](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-06.png)

파워 쿼리 편집기는 CSV 파일의 데이터에 대한 미리 보기를 보여 줍니다. 명령 리본에서 **테이블 변환**을 선택하고 표시되는 메뉴에서 **첫 행을 머리글로 사용**을 선택합니다. 화면 오른쪽의 **적용된 단계** 섹션에 _승격된 머리글_ 쿼리 단계가 추가됩니다. 오른쪽 창에 있는 **이름** 상자의 값을 변경하여 쿼리 이름을 보다 친숙한 이름으로 바꿀 수 있습니다. 예를 들어 쿼리 이름을 _Online Visitor_로 변경할 수 있습니다.

![친숙한 이름으로 변경](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-07.png)

이 데이터 세트에 있는 특성 데이터 형식 중 일부는 _숫자_ 또는 _부울_이지만 이는 **파워 쿼리**에 의해 문자열로 해석될 수 있습니다. 각 열 머리글의 맨 위에 있는 특성 유형 아이콘을 선택하여 아래 나열된 열을 다음 유형으로 변경합니다.

* **10진수:** Administrative_Duration; Informational_Duration; ProductRelated_Duration; BounceRates; ExitRates; PageValues; SpecialDay
* **True/False:** Weekend; Revenue

![데이터 형식 변경](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-08.png)

학습할 **이진 예측** 모델은 과거 관찰로부터 결과를 식별하는 레이블로 부울 필드가 필요합니다. 이 데이터 세트에서 _수익_ 특성은 구매를 나타내며 이 특성은 이미 부울로 사용할 수 있습니다. 따라서 레이블에 대해 계산 열을 추가할 필요가 없습니다. 다른 데이터 세트에서는 기존 레이블 특성을 부울 열로 변환해야 할 수 있습니다.

**완료** 단추를 선택하여 파워 쿼리 편집기를 닫습니다. 그러면 _온라인 방문자_ 데이터가 추가된 엔터티 목록이 표시됩니다. 다음 그림에 표시된 것처럼 오른쪽 위 모서리에서 **저장**을 선택하고 데이터 흐름의 이름을 제공한 다음 대화 상자에서 **저장**을 선택 합니다.

![데이터 흐름 저장](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-09.png)

### <a name="refresh-the-dataflow"></a>데이터 흐름 새로 고침

데이터 흐름을 저장하면 데이터 흐름을 저장했음을 나타내는 알림이 표시됩니다. **지금 새로 고침**을 선택하여 원본에서 데이터 흐름으로 데이터를 수집합니다.

![지금 새로 고침](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-10.png)

오른쪽 위 모서리의 **닫기**를 선택하고 데이터 흐름 새로 고침이 완료될 때까지 기다립니다.

**작업** 명령을 사용하여 데이터 흐름을 새로 고칠 수도 있습니다. 데이터 흐름은 새로 고침이 완료된 타임스탬프를 보여 줍니다.

![새로 고침 타임스탬프](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-11.png)

## <a name="create-and-train-a-machine-learning-model"></a>기계 학습 모델 만들기 및 학습

새로 고침이 완료된 후 데이터 흐름을 선택합니다. 기계 학습 모델을 추가하려면 학습 데이터와 레이블 정보를 포함하는 기본 엔터티에 대한 **작업** 목록에서 **ML 모델 적용** 단추를 선택하고 **기계 학습 모델 추가**를 선택합니다.

![기계 학습 모델 추가](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-12.png)

기계 학습 모델을 만드는 첫 번째 단계는 예측하려는 레이블 필드를 포함하여 기록 데이터를 식별하는 것입니다. 이 데이터를 학습하여 모델을 만듭니다.

우리가 사용하는 데이터 세트의 경우 **수익** 필드입니다. '기록 결과 필드' 값으로 **수익**을 선택하고 **다음**을 선택합니다.

![기록 데이터 선택](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-13.png)

다음으로 만들 기계 학습 모델의 유형을 선택해야 합니다. Power BI는 사용자가 식별한 기록 결과 필드의 값을 분석하고 해당 필드를 예측하기 위해 만들 수 있는 기계 학습 모델의 유형을 제안합니다.

이 경우 사용자가 구매할지 여부를 판단하는 이진 결과를 예측하기 때문에 모델 유형으로 **이진 예측**을 선택하고 다음을 선택합니다.

![이진 예측이 선택됨](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-14.png)

그런 다음 Power BI에서 데이터의 예비 검색을 수행하고 모델에서 사용할 수 있는 입력을 제안합니다. 모델에 사용되는 입력 필드를 사용자 지정할 수 있습니다. 큐레이팅된 데이터 세트에서 모든 필드를 선택하려면 엔터티 이름 옆에 있는 확인란을 선택합니다. 입력을 수락하려면 **다음**을 선택합니다.

![다음 확인란 선택](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-15.png)

마지막 단계에서는 모델의 이름을 지정하고 모델 유효성 검사 결과를 요약하는 자동 생성된 보고서에 사용할 결과에 대한 친숙한 레이블을 제공해야 합니다. 다음으로 모델의 이름을 _Purchase Intent Prediction_으로 지정하고, true 및 false 레이블을 _Purchase_ 및 _No-Purchase_로 지정합니다. 그런 다음, **저장**을 선택합니다.

![모델 저장](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-16.png)

이제 기계 학습 모델을 학습할 준비가 완료되었습니다. 모델 학습을 시작하려면 **지금 새로 고침**을 선택합니다.

![지금 새로 고침](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-17.png)

학습 프로세스는 기록 데이터를 샘플링 및 정규화하고 데이터 세트를 다음과 같은 두 개의 새 엔터티로 분할하는 것으로 시작됩니다. *Purchase Intent Prediction Training Data* 및 *Purchase Intent Prediction Testing Data*.

학습 프로세스는 데이터 세트의 크기에 따라 몇 분에서 몇 시간까지 걸릴 수 있습니다. 이 시점에서 데이터 흐름의 **기계 학습 모델** 탭에서 모델을 볼 수 있습니다. _준비_ 상태는 모델이 학습을 위해 큐에 대기 중이거나 학습 중에 있음을 나타냅니다.

![학습 준비](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-18.png)

모델을 학습하는 동안에는 데이터 흐름을 보거나 편집할 수 없습니다. 데이터 흐름의 상태를 통해 모델이 학습되고 유효성이 검사되는지 확인할 수 있습니다. 이는 작업 영역의 **데이터 흐름** 탭에서 데이터 새로 고침 처리 중으로 표시됩니다.

![처리 중](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-19.png)

모델 학습이 완료되면 데이터 흐름은 업데이트된 새로 고침 시간을 표시합니다. 데이터 흐름의 **기계 학습 모델** 탭으로 이동하여 모델이 학습되었는지 확인할 수 있습니다. 이제 만든 모델이 **학습됨**으로 상태를 표시하고 **마지막 학습 날짜** 시간이 업데이트되어야 합니다.

![마지막 학습 날짜](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-20.png)

## <a name="review-the-model-validation-report"></a>모델 유효성 검사 보고서 검토

모델 유효성 검사 보고서를 검토하려면 **기계 학습 모델**에서 모델의 **작업** 열에서 **성능 보고서 보기 및 모델 적용** 단추를 선택합니다. 이 보고서는 기계 학습 모델의 잠재적 성능을 설명합니다.

보고서의 **모델 성능** 페이지에서 **주요 영향 요인**을 선택하여 모델에 대한 상위 예측 변수를 확인합니다. 예측 변수 중 하나를 선택하여 결과 분포를 해당 예측에 연결하는 방법을 확인할 수 있습니다.

![모델 성능](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-21.png)

모델 성능 페이지에서 **확률 임계값** 슬라이서를 사용하여 모델의 정밀도 및 재현율에 대한 영향을 검사할 수 있습니다.

![확률 임계값](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-22.png)

보고서의 다른 페이지는 모델의 통계 성능 메트릭을 설명합니다.

이 보고서에는 실행된 여러 반복, 입력에서 기능을 추출하는 방법, 사용된 최종 모델 하이퍼 매개 변수를 설명하는 학습 세부 정보 페이지도 포함됩니다.

## <a name="apply-the-model-to-a-dataflow-entity"></a>데이터 흐름 엔터티에 모델 적용

데이터 흐름을 새로 고칠 때 보고서 맨 위에 있는 **모델 적용** 단추를 선택하여 이 모델을 호출합니다. **적용** 대화 상자에서 모델을 적용할 원본 데이터가 포함된 대상 엔터티를 지정할 수 있습니다.

![모델 적용](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-23.png)

메시지가 표시되면 데이터 흐름을 **새로 고침**하여 모델 결과를 미리 보아야 합니다.

모델을 적용하면 **enriched <model_name>** 접미사를 사용하여 새 엔터티가 생성되고, 이 엔터티는 모델을 적용한 엔터티에 추가됩니다. 이 경우 **OnlineShoppers** 엔터티에 모델을 적용하면 모델의 예측된 출력을 포함하는 **OnlineShoppers enriched Purchase Intent Prediction**이 생성됩니다.

이진 예측 모델을 적용하면 예측 결과, 확률 점수 및 예측에 대한 상위 레코드별 영향 요인(각각 지정된 열 이름을 접두사로 사용)이 포함된 세 개의 열이 추가됩니다.

![세 개의 결과 열](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-24.png)

알려진 문제로 인해 보강 엔터티의 점수가 매겨진 출력 열은 Power BI Desktop에서만 액세스할 수 있습니다. 서비스에서 이를 미리 보려면 특수한 미리 보기 엔터티를 사용해야 합니다.

데이터 흐름 새로 고침이 완료되면 **OnlineShoppers enriched Purchase Intent Prediction Preview** 엔터티를 선택하여 결과를 볼 수 있습니다.

![결과 보기](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-25.png)

## <a name="using-the-scored-output-from-the-model-in-a-power-bi-report"></a>Power BI 보고서에서 모델의 점수가 매겨진 출력 사용

기계 학습 모델의 점수가 매겨진 출력을 사용하려면 데이터 흐름 커넥터를 사용하여 Power BI Desktop에서 데이터 흐름에 연결할 수 있습니다. 이제 **OnlineShoppers enriched Purchase Intent Prediction** 엔터티를 사용하여 모델의 예측을 Power BI 보고서에 통합할 수 있습니다.

## <a name="next-steps"></a>다음 단계

이 자습서에서는 다음 단계를 사용하여 Power BI에서 이진 예측 모델을 만들고 적용했습니다.

* 입력 데이터를 사용하여 데이터 흐름 만들기
* 기계 학습 모델 만들기 및 학습
* 모델 유효성 검사 보고서 검토
* 데이터 흐름 엔터티에 모델 적용
* Power BI 보고서에서 모델의 점수가 매겨진 출력 사용

Power BI에서 기계 학습 자동화에 대한 자세한 내용은 [Power BI의 자동화된 Machine Learning(미리 보기)](service-machine-learning-automated.md)을 참조하세요.
