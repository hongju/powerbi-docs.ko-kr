---
title: '자습서: Power BI (미리 보기)에서 Machine Learning 모델 빌드'
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
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "61407201"
---
# <a name="tutorial-build-a-machine-learning-model-in-power-bi-preview"></a>자습서: Power BI (미리 보기)에서 Machine Learning 모델 빌드

이 자습서에서는 사용 하 여 **Machine Learning 자동화 된** 를 만들고 Power BI에서 이진 예측 모델을 적용 합니다. 자습서는 Power BI 데이터 흐름을 만들기 위한 지침을 포함 하 고 학습 하 고 기계 학습 모델을 Power BI에서 직접 유효성을 검사 하는 데이터 흐름에 정의 된 엔터티를 사용 하 여 합니다. 점수 매기기에 모델 예측을 생성 사용 합니다.

먼저 이진 예측 기계 학습 온라인 세션 특성의 집합을 기반으로 하는 온라인 구매자의 구매 의도 예측 모델을 만들어야 합니다. 벤치 마크 machine learning 데이터 집합은이 연습에 사용 됩니다. 모델이 학습 되 면 Power BI 모델 결과 설명 하는 유효성 검사 보고서를 자동으로 생성 됩니다. 그런 다음 유효성 검사 보고서를 검토 하 고 모델 점수 매기기에 대 한 데이터에 적용할 수 있습니다.

이 자습서의 다음 단계 구성:

> [!div class="checklist"]
> * 입력된 데이터를 사용 하 여 데이터 흐름 만들기
> * 기계 학습 모델을 학습 합니다.
> * 모델 유효성 검사 보고서를 검토 합니다.
> * 모델 엔터티를 데이터 흐름을 적용
> * Power BI 보고서에서 모델의 점수가 매겨진된 출력을 사용 하 여

## <a name="create-a-dataflow-with-the-input-data"></a>입력된 데이터를 사용 하 여 데이터 흐름 만들기

이 자습서의 첫 번째 부분은 입력된 데이터를 사용 하 여 데이터 흐름을 만들려고 합니다. 데이터를 가져오는 부터는 다음 섹션에 표시 된 대로 몇 가지 단계를 수행 하는 프로세스입니다.

### <a name="get-data"></a>데이터 가져오기

데이터 흐름을 만드는 첫 번째 단계는 데이터 소스를 준비 하는 것입니다. 여기서에서는 일부 구매에 culminated 온라인 세션 집합에서 기계 학습 데이터 집합을 사용 합니다. 데이터 집합에는 모델 학습에 사용 하 여 이러한 세션에 대 한 특성 집합을 포함 합니다.

데이터 집합에서는 UC Irvine 웹 사이트에서 다운로드할 수 있습니다.  도이 자습서에서는 다음 링크에서이 사용할 수 있습니다: [online_shoppers_intention.csv](https://raw.githubusercontent.com/santoshc1/PowerBI-AI-samples/master/Tutorial_AutomatedML/online_shoppers_intention.csv)합니다.

### <a name="create-the-entities"></a>엔터티 만들기

데이터 흐름에 엔터티를 만들려면 Power BI 서비스에 로그인하고, 사용하도록 설정된 AI 미리 보기가 있는 전용 용량의 작업 영역으로 이동합니다.

작업 영역에 아직 없는 경우 선택 하 여 하나를 만들 수 있습니다 **작업 영역** 선택한 Power BI 서비스 왼쪽된 탐색 메뉴에서 **앱 작업 영역 만들기** 패널의 맨 아래에 표시 됩니다. 작업 영역 정보를 입력 하려면 오른쪽에 패널이 열립니다. 작업 영역 이름을 입력 하 고 선택 **고급**합니다. 작업 영역 라디오 단추를 사용 하는 전용 용량을 사용 하는 고 켜져 AI 미리 보기에는 전용된 용량 인스턴스를에 할당 되어 있는지 확인 합니다. 그런 다음, **저장**을 선택합니다.

![작업 영역 만들기](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-01.png)

선택할 수 있습니다 작업 영역이 만들어지면 **Skip** 다음 그림에 나와 있는 것 처럼 시작 화면의 오른쪽 아래에 있습니다.

![작업 영역을 만든 경우 건너뛸](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-02.png)

선택 된 **데이터 흐름 (미리 보기)** 탭 합니다. 선택 된 **만들기** 작업 영역의 오른쪽 선택한 후 맨 위에 있는 단추 **데이터 흐름**합니다.

![데이터 흐름 만들기](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-03.png)

**새 엔터티 추가**를 선택합니다. 그러면를 **파워 쿼리** 브라우저에서 편집기입니다.

![새 엔터티 추가](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-04.png)

선택 **Text/CSV 파일** 다음 그림과에서 같이 데이터 원본으로 합니다.

![선택한 텍스트/CSF 파일](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-05.png)

에 **데이터 원본에 연결** 다음 표시 되는, 다음 링크를 붙여 넣습니다 합니다 *online_shoppers_intention.csv* 에 **파일 경로 또는 URL** 상자를 선택한 다음  **다음**합니다.

`https://raw.githubusercontent.com/santoshc1/PowerBI-AI-samples/master/Tutorial_AutomatedML/online_shoppers_intention.csv`

![파일 경로](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-06.png)

파워 쿼리 편집기는 CSV 파일에서 데이터의 미리 보기를 표시 합니다. 선택 **변환 표** 명령은 리본 메뉴에서 선택 **사용 하 여 첫 번째 행을 머리글로** 나타나는 메뉴에서. 추가 합니다 _헤더를 승격_ 쿼리 단계에는 **적용 된 단계** 화면 오른쪽의 섹션입니다. 쿼리 값을 변경 하 여 이름 이름을 바꿀 수는 **이름을** 상자 오른쪽 창에서 찾을 수 있습니다. 예를 들어 쿼리 이름을 변경할 수 있습니다 _온라인 방문자_합니다.

![친숙 한 이름 변경](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-07.png)

이 데이터 집합에서 특성 데이터 형식 중 일부가 _숫자_ 하거나 _부울_되지만 이러한에서 문자열로 해석 될 수 있습니다 **파워 쿼리**합니다. 다음 형식으로 아래에 나열 된 열을 변경 하려면 각 열 머리글의 맨 위에 있는 특성 형식 아이콘을 선택 합니다.

* **10 진수:** Administrative_Duration; Informational_Duration; ProductRelated_Duration; BounceRates; ExitRates; PageValues; SpecialDay
* **True/False.** 주말; 수익

![데이터 형식 변경](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-08.png)

합니다 **이진 예측** 학습할 과거 관찰의 결과 식별 하는 레이블로 부울 필드가 필요 합니다. 이 데이터 집합에는 _수익_ 특성 구매를 나타내며이 특성은 이미 부울 값으로 사용할 수 있습니다. 따라서 레이블에 대 한 계산된 열을 추가할 필요가 있습니다. 다른 데이터 집합의 레이블 특성 기존 부울 열을 변환 해야 합니다.

선택 된 **수행** 파워 쿼리 편집기를 닫으려면 단추를 합니다. 사용 하 여 엔터티 목록을 표시 합니다.이 _온라인 방문자_ 데이터를 추가 했습니다. 선택 **저장할** 오른쪽 위 모서리에 있는 데이터 흐름에 대 한 이름을 제공 하 고 선택한 **저장** 대화 상자에서 다음 그림과에서 같이 합니다.

![데이터 흐름 저장](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-09.png)

### <a name="refresh-the-dataflow"></a>데이터 흐름 새로 고침

알림이 표시 되 고 데이터 흐름 결과 저장 하는 중 데이터 흐름 저장 된 내용의 합니다. 선택 **지금 새로 고침** 데이터 흐름에 원본에서 데이터를 수집 합니다.

![지금 새로 고침](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-10.png)

오른쪽 위 모서리의 **닫기**를 선택하고 데이터 흐름 새로 고침이 완료될 때까지 기다립니다.

사용 하 여 데이터 흐름을 새로 고칠 수도 있습니다는 **작업** 명령입니다. 데이터 흐름에서는 새로 고침이 완료 되 면 타임 스탬프를 보여 줍니다.

![새로 고침의 타임 스탬프](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-11.png)

## <a name="create-and-train-a-machine-learning-model"></a>기계 학습 모델을 학습 합니다.

새로 고침 완료 된 후 데이터 흐름을 선택 합니다. Machine learning 모델을 추가 하려면 선택 합니다 **적용 기계 학습 모델** 단추를 **작업** 고 학습 데이터와 레이블 정보를 포함 하는 기본 엔터티에 대 한 목록 및 선택한 **추가 기계 학습 모델**합니다.

![기계 학습 모델 추가](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-12.png)

Machine learning 모델을 만들기 위한 첫 번째 단계를 예측 하려는 레이블 필드를 포함 하는 기록 데이터를 식별 하는 것입니다. 모델 학습 데이터에서에 의해 생성 됩니다.

이것이 바로 우리가 사용할 데이터 집합의 경우는 **수익** 필드입니다. 선택 **수익** '기록 결과 필드' 값과 선택 **다음**합니다.

![기록 데이터를 선택 합니다.](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-13.png)

다음으로, 기계 학습 모델을 만들려는 형식의 선택 해야 합니다. Power BI를 확인 하는 기록 결과 필드의 값을 분석 하 고 해당 필드를 예측을 만들 수 있는 기계 학습 모델 유형의 제안 합니다.

이 경우 구매 여부 사용자가 인지 하는 이진 결과 예측 하는 것을 선택 **이진 예측** 모델 유형 및 선택한 후 다음에 대 한 합니다.

![선택한 이진 예측](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-14.png)

다음으로, Power BI는 데이터의 예비 검색을 수행 하 고 모델을 사용할 수 있는 입력을 제안 합니다. 모델에 사용 되는 입력된 필드를 사용자 지정 하는 옵션이 있습니다. 여기서는 큐 레이트 데이터 집합에서 모든 필드를 선택 하려면 엔터티 이름 옆의 확인란을 선택 합니다. 선택 **다음** 입력을 수락 하도록 합니다.

![다음 확인란을 선택 합니다.](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-15.png)

마지막 단계에서이 모델에 대 한 이름 및 모델 유효성 검사의 결과 요약 하는 자동으로 생성 된 보고서에 사용할 결과 대 한 친숙 한 레이블을 제공 해야 합니다. 모델 이름을 다음 엔 _구매 의도 예측_, 및와 같이 true 및 false 레이블을 _구매_ 및 _아니요 구매_합니다. 그런 다음, **저장**을 선택합니다.

![모델 저장](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-16.png)

이제 machine learning 모델 학습에 대 한 준비가 되었습니다. 선택 **지금 새로 고침** 모델 학습을 시작 합니다.

![지금 새로 고침](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-17.png)

샘플링 및 기록 데이터를 정규화 하 고, 두 개의 새 엔터티를 데이터 집합을 분할 하 여 학습 프로세스가 시작 됩니다 *구매 의도 예측 학습 데이터* 고 *구매 의도 예측 테스트 데이터*입니다.

데이터 집합의 크기에 따라 학습 프로세스 걸릴 수 있습니다 어디서 나 몇 분에서 몇 시간. 이 시점에서 모델을 볼 수 있습니다 합니다 **기계 학습 모델** 데이터 흐름 탭 합니다. 합니다 _준비_ 모델 학습에 대 한 큐에 대기 되었습니다 또는 교육의 상태를 나타냅니다.

![학습을 위한 준비](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-18.png)

학습 모델을 사용 하는 동안에를 보거나 데이터 흐름을 편집할 수 없습니다. 모델 중임을 확인할 수 있습니다 학습 및 데이터 흐름의 상태를 통해 유효성을 검사 합니다. 데이터 새로 고침 진행 중으로 표시 됨을 **데이터 흐름** 영역의 탭 합니다.

![프로세스에서](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-19.png)

모델 학습 완료 되 면 데이터 흐름에는 업데이트 된 새로 고침 시간을 표시 합니다. 로 이동 하 여 모델을 학습을 확인할 수 있습니다 합니다 **기계 학습 모델** 데이터 흐름에 대 한 탭 합니다. 만든 모델 상태를 표시 해야 **Trained** 하며 **마지막 학습** 시간 이제 업데이트 됩니다.

![마지막으로 학습](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-20.png)

## <a name="review-the-model-validation-report"></a>모델 유효성 검사 보고서를 검토 합니다.

모델 유효성 검사 보고서를 검토 하는 **기계 학습 모델, s** 선택 합니다 **성능 보고서 보기 및 모델을 적용** 단추를 **작업** 모델 열 . 이 보고서는 기계 학습 모델 수행 하는 방법을 설명 합니다.

에 **모델 성능을** 선택 된 보고서의 페이지 **주요 영향 요인** 모델에 대 한 상위 예측을 보려는 합니다. 해당 예측을 사용 하 여 결과 배포에 연결 하는 방법을 보려면 예측 중 하나를 선택할 수 있습니다.

![모델 성능](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-21.png)

사용할 수는 **확률 임계값** 모델의 정확도 재현 율에 미치는 영향을 검사할 모델 성능 페이지에서 슬라이서입니다.

![확률 임계값](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-22.png)

보고서의 나머지 페이지는 모델에 대 한 통계 성능 메트릭에 대해 설명합니다.

보고서에는 입력 데이터 및 사용 된 최종 모델에 대 한 하이퍼 매개 변수에서 기능 추출 된 방법을 실행 된 다른 반복을 설명 하는 교육 세부 정보 페이지도를 포함 됩니다.

## <a name="apply-the-model-to-a-dataflow-entity"></a>모델 엔터티를 데이터 흐름을 적용

선택 된 **적용 모델** 데이터 흐름은 새로 고칠 때이 모델을 호출 하는 보고서의 맨 위에 있는 단추입니다. 에 **적용** 대화 상자에서 원본 데이터가 모델을 적용할 수 있는 대상 엔터티를 지정할 수 있습니다.

![모델 적용](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-23.png)

메시지가 표시 되 면 해야 **새로 고침** 모델의 결과를 미리 볼 데이터 흐름입니다.

접미사를 사용 하 여 새 엔터티를 만들기는 모델 적용 **보강 < 모델 이름 >** 모델을 적용할 엔터티를 추가 합니다. 경우에 모델을 적용 합니다 **OnlineShoppers** 엔터티를 만듭니다 **OnlineShoppers 보강 구매 의도 예측**, 모델의 예측 된 출력을 포함 하는 합니다.

지정 된 열 이름을 접두사로 각, 예측 된 결과, 확률 점수 및 예측에 대 한 상위 레코드별 영향 요인의 세 열 추가 이진 예측 모델을 적용 합니다.

![결과의 세 열](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-24.png)

알려진된 문제로 인해 풍부한 엔터티에서 점수가 매겨진된 출력 열은 Power BI Desktop에서 액세스할 수 있습니다. 이러한 서비스에서를 미리 보려면 특별 미리 보기 엔터티를 사용 해야 합니다.

데이터 흐름 새로 고침이 완료 되 면 선택할 수 있습니다 합니다 **OnlineShoppers 구매 의도 예측 미리 보기를 보강 한** 결과 보려면 엔터티.

![결과 보기](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-25.png)

## <a name="using-the-scored-output-from-the-model-in-a-power-bi-report"></a>Power BI 보고서에서 모델의 점수가 매겨진된 출력을 사용 하 여

기계 학습 모델의에서 점수가 매겨진된 출력을 사용 하려면 연결할 수 있습니다 데이터 흐름에 Power BI desktop에서 데이터 흐름이 커넥터를 사용 하 여. 합니다 **OnlineShoppers 보강 구매 의도 예측** Power BI 보고서에서 모델의 예측을 통합 하기 위해 엔터티 이제 사용할 수 있습니다.

## <a name="next-steps"></a>다음 단계

이 자습서에서는 생성 하 고이 단계를 사용 하 여 Power BI에서 이진 예측 모델을 적용 합니다.

* 입력된 데이터를 사용 하 여 데이터 흐름 만들기
* 기계 학습 모델을 학습 합니다.
* 모델 유효성 검사 보고서를 검토 합니다.
* 모델 엔터티를 데이터 흐름을 적용
* Power BI 보고서에서 모델의 점수가 매겨진된 출력을 사용 하 여

Power BI에서 Machine Learning 자동화에 대 한 자세한 내용은 참조 하세요. [Power BI (미리 보기)에서 Machine Learning 자동화 된](service-machine-learning-automated.md)합니다.
