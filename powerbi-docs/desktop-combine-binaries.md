---
title: Power BI Desktop에서 파일(이진) 병합
description: Power BI Desktop에서 손쉽게 파일(이진) 데이터 원본 병합
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/13/2020
ms.author: davidi
LocalizationGroup: Transform and shape data
ms.openlocfilehash: 07381461375ea7b9707b91c807e92cdb85c1d440
ms.sourcegitcommit: 3d6b27e3936e451339d8c11e9af1a72c725a5668
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2020
ms.locfileid: "76161119"
---
# <a name="combine-files-binaries-in-power-bi-desktop"></a>Power BI Desktop에서 파일(이진) 병합

다음은 **Power BI Desktop**으로 데이터를 가져오는 강력한 방법입니다. 스키마가 동일한 파일이 여러 개 있는 경우, 단일한 논리적 테이블로 결합합니다. 인기 있는 이 방법은 더욱 편리해지고 사용 범위가 확장되었습니다.

동일한 폴더에서 파일을 결합하는 프로세스를 시작하려면 **데이터 가져오기**를 선택하고 **파일** > **폴더**를 선택한 다음 **연결**을 선택합니다.

![폴더 파일에 연결, 데이터 가져오기 대화 상자, Power BI Desktop](media/desktop-combine-binaries/combine-binaries_1.png)

폴더 경로를 입력하고 **확인**을 선택한 다음 **데이터 변환**을 선택하여 Power Query 편집기에서 폴더의 파일을 확인합니다.

## <a name="combine-files-behavior"></a>파일 병합 동작

Power Query 편집기에서 이진 파일을 결합하려면 **콘텐츠**(첫 번째 열 레이블)를 선택하고 **홈** > **파일 결합**을 선택합니다. 또는 **콘텐츠** 옆에 있는 **파일 결합** 아이콘을 선택해도 됩니다.

![파일 결합 명령, Power Query 편집기, Power BI Desktop](media/desktop-combine-binaries/combine-binaries_2a.png)

*파일 병합* 변환은 다음과 같이 동작합니다.

* 파일 결합 변환에서는 각 입력 파일을 분석하여 *텍스트*, *Excel 통합 문서* 또는 *JSON 파일* 등 사용할 올바른 파일 형식을 결정합니다.
* 변환을 사용하면 Excel 통합 문서와 같은 첫 번째 파일에서 추출할 특정 개체를 선택할 수 있습니다.
  
  ![파일 결합 대화 상자, Power Query 편집기, Power BI Desktop](media/desktop-combine-binaries/combine-binaries_3.png)
* 그런 다음 파일 결합 변환은 자동으로 다음 작업을 수행합니다.
  
  * 단일 파일에 모든 필수 추출 단계를 수행하는 예제 쿼리를 만듭니다.
  * exemplar 쿼리에 파일/이진 파일 입력을 매개 변수화하는 함수 쿼리를 만듭니다.   Exemplar 쿼리 및 함수 쿼리는 연결되어 exemplar 쿼리 변경 내용이 함수 쿼리에 반영됩니다.
  * *폴더* 쿼리와 같은 입력 이진 파일을 사용하여 원래 쿼리에 *함수 쿼리*를 적용합니다. 각 행에서 이진 입력 파일의 함수 쿼리를 적용한 다음 결과 데이터 추출을 최상위 열로 확장합니다.

    ![파일 결합 변환 결과, Power Query 편집기, Power BI Desktop](media/desktop-combine-binaries/combine-binaries_4.png)

> [!NOTE]
> Excel 통합 문서의 선택 범위는 병합된 바이너리의 동작에 영향을 줍니다. 예를 들어, 특정 워크시트를 선택하여 해당 워크시트를 병합하거나 루트를 선택하여 전체 파일을 병합할 수 있습니다. 폴더를 선택하면 해당 폴더에 있는 파일들이 병합됩니다. 

파일 결합 동작을 사용하면 지정된 폴더 내 모든 파일의 파일 형식 및 구조가 동일(예: 동일한 열)한 경우 해당 파일을 쉽게 결합할 수 있습니다.

또한 추가 함수 쿼리 단계를 수정하거나 만들 걱정을 하지 않고도 자동으로 생성된 exemplar 쿼리를 수정하여 추가 변환이나 추출 단계를 손쉽게 적용할 수 있습니다. exemplar 쿼리의 모든 변경 내용은 연결된 함수 쿼리에서 자동으로 생성됩니다.

## <a name="next-steps"></a>다음 단계

Power BI Desktop을 사용하여 모든 종류의 데이터에 연결할 수 있습니다. 데이터 원본에 대한 자세한 내용은 다음 리소스를 참조하세요.

* [Power BI Desktop이란?](desktop-what-is-desktop.md)
* [Power BI Desktop의 데이터 원본](desktop-data-sources.md)
* [Power BI Desktop에서 데이터 셰이핑 및 결합](desktop-shape-and-combine-data.md)
* [Power BI Desktop에서 CSV 파일에 연결](desktop-connect-csv.md)
* [Power BI Desktop에 데이터 직접 연결](desktop-enter-data-directly-into-desktop.md)
