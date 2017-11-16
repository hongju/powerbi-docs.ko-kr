---
title: "Power BI Desktop에서 이진 파일 결합"
description: "Power BI Desktop에서 이진 데이터 원본과 손쉽게 결합"
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
ms.date: 09/06/2017
ms.author: davidi
ms.openlocfilehash: 0909056569bb353a720ddd4e8563a37542b90cca
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2017
---
# <a name="combine-binaries-in-power-bi-desktop"></a>Power BI Desktop에서 이진 파일 결합
**Power BI Desktop**에 데이터를 가져오기 위한 한 가지 강력한 접근 방식은 동일한 스키마의 여러 파일을 단일 논리 테이블로 결합하는 것입니다. 이 문서에서 설명한 대로 **Power BI Desktop**의 2016년 11월 릴리스(와 이후 버전)는 편리하며, 일반적인 접근 방식이 보다 편리해지고 확장되었습니다.

동일한 폴더에서 이진 파일을 결합하는 프로세스를 시작하려면 **데이터 가져오기 > 파일 > 폴더**를 선택합니다.

![](media/desktop-combine-binaries/combine-binaries_1.png)

## <a name="previous-combine-binaries-behavior"></a>이전 이진 파일 결합 동작
**Power BI Desktop**의 2016년 11월 버전 이전에는 특정 파일을 **이진 파일 결합** 변환과 결합할 수 있었지만 다음과 같은 제한 사항이 있었습니다.

* 파일을 단일 테이블에 결합하기 전에는 각 개별 파일에 대해 변환을 고려하지 않았습니다. 따라서 편집 과정의 하나로 자주 파일을 결합하고 행을 필터링하여 헤더 값을 필터링해야 합니다.
* **이진 파일 결합** 변환은 *텍스트* 또는 *CSV* 파일에서만 가능하고 Excel 통합 문서, JSON 파일 등 지원되는 다른 파일 형식에서는 불가능합니다.

**이진 파일 결합** 작업의 보다 직관적인 작업에 대한 고객의 요구에 따라 변환은 향상되었습니다.

## <a name="current-combine-binaries-behavior"></a>이전 이진 파일 결합 동작
**Power BI Desktop**은 이제 **이진 파일 결합**을 보다 효과적으로 처리합니다. **쿼리 편집기**의 **홈** 리본 탭에서 또는 자체 열에서 **이진 파일 결합**을 선택하여 시작합니다.

![](media/desktop-combine-binaries/combine-binaries_2a.png)

**이진 파일 결합** 변환은 이제 다음과 같이 동작합니다.

* **이진 파일 결합** 변환에서는 입력된 각각의 파일을 분석하고 *텍스트*, *Excel 통합 문서* 또는 *JSON* 파일 등 사용할 올바른 파일 형식을 결정합니다.
* 변환을 사용하면 첫째 파일, 예를 들어 추출할 Excel 통합 문서에서 특정 개체를 선택할 수 있습니다.
  
  ![](media/desktop-combine-binaries/combine-binaries_3.png)
* 그런 다음 **이진 파일 결합**은 다음 작업을 자동으로 수행합니다.
  
  * 단일 파일에 모든 필수 추출 단계를 수행하는 예제 쿼리를 만듭니다.
  * exemplar 쿼리에 파일/이진 파일 입력을 매개 변수화하는 함수 쿼리를 만듭니다. Exemplar 쿼리 및 함수 쿼리는 연결되어 exemplar 쿼리 변경 내용이 함수 쿼리에 반영됩니다.
  * 입력 이진 파일(예: *폴더* 쿼리)로 함수 쿼리를 원래 쿼리에 적용하면 이진 파일 입력에 대한 함수 쿼리를 각 행에 적용한 후 결과 데이터 추출을 최상위 열로 확장합니다.
    
    ![](media/desktop-combine-binaries/combine-binaries_4.png)

**이진 파일 결합**의 새 동작으로 같은 파일 형식 및 구조(예: 동일한 열에서)를 가지고 있다면 지정된 폴더 내의 모든 이진 파일을 쉽게 결합할 수 있습니다.

또한 추가 *함수 쿼리* 단계를 수정하거나 만들 걱정을 하지 않고도 자동으로 생성된exemplar 쿼리를 수정하여 추가 변환이나 추출 단계를 손쉽게 적용할 수 있습니다. 따라서 exemplar 쿼리의 모든 변경 사항은 연결된 함수 쿼리에서 자동으로 생성됩니다.

## <a name="next-steps"></a>다음 단계
Power BI Desktop을 사용하여 연결할 수 있는 모든 종류의 데이터가 있습니다. 데이터 원본에 대한 자세한 내용은 다음 리소스를 확인하세요.

* [Power BI Desktop 시작](desktop-getting-started.md)
* [Power BI Desktop의 데이터 원본](desktop-data-sources.md)
* [Power BI Desktop에서 데이터 셰이핑 및 결합](desktop-shape-and-combine-data.md)
* [Power BI Desktop에서 CSV 파일에 연결](desktop-connect-csv.md)   
* [Power BI Desktop에 데이터 직접 연결](desktop-enter-data-directly-into-desktop.md)   

