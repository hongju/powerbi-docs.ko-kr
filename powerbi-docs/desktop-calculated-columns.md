---
title: Power BI Desktop의 계산 열 사용
description: Power BI Desktop의 계산 열
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/07/2019
ms.author: davidi
LocalizationGroup: Model your data
ms.openlocfilehash: 805e052a2d5b493705c604d1817fc03c0a8b5376
ms.sourcegitcommit: f05ba39a0e46cb9cb43454772fbc5397089d58b4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/26/2019
ms.locfileid: "68522194"
---
# <a name="using-calculated-columns-in-power-bi-desktop"></a>Power BI Desktop의 계산 열 사용
계산된 열을 사용하면 이미 모델에 있는 표에 새 데이터를 추가할 수 있습니다. 그러나 값을 쿼리하고 데이터 소스에서 새 열로 로드하는 대신 열 값을 정의하는 DAX(Data Analysis Expressions) 수식을 만듭니다. Power BI Desktop에서 보고서 뷰의 새 열 기능을 사용하여 계산된 열이 생성됩니다.

쿼리 편집기에서 사용자 지정 열 추가를 사용하여 쿼리의 일부로 만든 사용자 지정 열과 달리 보고서 뷰 또는 데이터 뷰에서 만든 계산된 열은 이미 모델에 로드한 데이터를 기반으로 합니다. 예를 들어 두 개의 서로 다르지만 관련된 표에 있는 두 열의 값을 연결하거나, 추가를 수행하거나, 하위 문자열을 추출할 수 있습니다.

만든 계산된 열은 다른 필드와 마찬가지로 필드 목록에 나타나지만 해당 값이 수식의 결과임을 표시하는 특수 아이콘이 있습니다. 열에 원하는 대로 이름을 지정하고 다른 필드처럼 보고서 시각화에 추가할 수 있습니다.

![](media/desktop-calculated-columns/calccolinpbid_fields.png)

계산된 열은 Power BI Designer에서와 같이 관계형 데이터 작업에 사용되는 수식 언어인 DAX([Data Analysis Expressions](https://msdn.microsoft.com/library/gg413422.aspx))를 사용하여 결과를 계산합니다. DAX에는 200개가 넘는 함수, 연산자 및 구문 라이브러리가 포함되어 데이터 분석 결과를 계산하는 수식을 만들 때 엄청난 유연성을 제공합니다. DAX에 대한 자세한 내용은 이 문서의 끝에 있는 자세한 정보 섹션을 참조하세요.

DAX 수식은 Excel 수식과 비슷합니다. 실제로 DAX에는 Excel과 동일한 함수가 대부분 포함되어 있습니다. 그러나 DAX 함수는 Power BI Desktop에서처럼 보고서에서 대화형으로 분리되거나 필터링된 데이터에 대한 작업입니다. 표의 각 행에 대해 다른 수식을 사용할 수 있는 Excel과 달리 새 열에 대한 DAX 수식을 만드는 경우 표의 각 행에 대한 결과를 계산합니다. 기본 데이터가 새로 고쳐지고 값이 변경된 경우와 같이 필요에 따라 열 값이 다시 계산됩니다.

## <a name="lets-look-at-an-example"></a>예를 살펴보겠습니다.
Jeff는 Contoso의 배송 관리자이며, 다양한 도시로 배송되는 화물 수를 보여 주는 보고서를 만들려고 합니다. Jeff는 도시와 주의 개별 필드가 포함된 Geography 표가 있습니다. 그러나 Jeff는 보고서에서 City, State를 동일한 행에 단일 값으로 표시하려고 합니다. 지금은 Jeff의 Geography 표에 원하는 필드가 없습니다.

![](media/desktop-calculated-columns/calccolinpbid_cityandstatefields.png)

그러나 계산 열을 사용하여 Jeff는 City 열의 도시와 State 열의 주를 모으거나 연결할 수 있습니다.

Jeff는 Geography 표를 마우스 오른쪽 단추로 클릭한 다음 새 열을 클릭합니다. Jeff는 수식 입력줄에 다음 DAX 수식을 입력합니다.

![](media/desktop-calculated-columns/calccolinpbid_formula.png)

이 수식은 CityState라는 새 열을 만들고, Geography 표의 각 행에 대해 City 열의 값을 가져오고 쉼표와 공백을 추가한 다음 State 열의 값을 연결합니다.

이제 Jeff가 원하는 필드를 얻었습니다.

![](media/desktop-calculated-columns/calccolinpbid_citystatefield.png)

Jeff는 이 필드를 화물 수와 함께 보고서 캔버스에 추가할 수 있습니다. 이제 Jeff는 최소한의 노력으로 신속하게 거의 모든 유형의 시각화에 추가할 수 있는 City, State 필드를 만들었습니다. Jeff는 지도 시각화가 생성된 경우 Power BI Desktop에서 새 열의 City, State 값을 읽는 방법을 이미 알고 있는 것을 확인할 수 있습니다.

![](media/desktop-calculated-columns/calccolinpbid_citystatemap.png)

## <a name="learn-more"></a>자세한 정보
여기서는 계산된 열에 대한 간략한 소개만 제공했습니다. 샘플 파일을 다운로드하여 더 많은 측정값을 만드는 방법에 대한 단계별 학습을 진행할 수 있는 [자습서: Power BI Desktop에서 계산 열 만들기](desktop-tutorial-create-calculated-columns.md) 자습서를 참조해야 합니다. 

DAX에 대한 자세한 내용은 [Power BI Desktop의 DAX 기본 사항](desktop-quickstart-learn-dax-basics.md)을 참조하세요.

쿼리의 일부로 만드는 열에 대한 자세한 내용은 [Power BI Desktop의 일반적인 쿼리 작업](desktop-common-query-tasks.md)의 사용자 지정 열 만들기 섹션을 참조하세요.  

