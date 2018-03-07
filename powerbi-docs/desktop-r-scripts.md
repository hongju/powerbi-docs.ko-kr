---
title: "Power BI Desktop에서 R 스크립트 실행"
description: "Power BI Desktop에서 R 스크립트 실행"
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
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 1b8b6dc3932ec4bc1eddd24c91a81a0eaafae479
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/24/2018
---
# <a name="run-r-scripts-in-power-bi-desktop"></a>Power BI Desktop에서 R 스크립트 실행
**Power BI Desktop**에서 직접 R 스크립트를 실행하고 결과 데이터 집합을 Power BI Desktop 데이터 모델로 가져올 수 있습니다.

## <a name="install-r"></a>R 설치
Power BI Desktop에서 R 스크립트를 실행하려면 로컬 컴퓨터에 **R** 을 설치해야 합니다. 여러 위치에서 무료로 [Revolution Open 다운로드 페이지](https://mran.revolutionanalytics.com/download/) 및 [CRAN 리포지토리](https://cran.r-project.org/bin/windows/base/)를 포함하는 **R**을 다운로드 및 설치할 수 있습니다. Power BI Desktop의 현재 R 스크립팅 릴리스는 설치 경로에서 유니코드 문자뿐만 아니라 공백(빈 문자)을 지원합니다.

## <a name="run-r-scripts"></a>R 스크립트 실행
Power BI Desktop의 몇 단계를 사용하여 보고서를 만드는 위치에서 R 스크립트를 실행하고 데이터 모델을 만들며 Power BI 서비스에서 공유할 수 있습니다. 이제 Power BI Desktop의 R 스크립팅은 10진수(.) 및 쉼표(,)를 포함하는 숫자 형식을 지원합니다.

### <a name="prepare-an-r-script"></a>R 스크립트 준비
Power BI Desktop에서 R 스크립트를 실행하려면 로컬 R 개발 환경에서 스크립트를 만들고 성공적으로 실행되도록 합니다.

Power BI Desktop에서 스크립트를 실행하려면 새로 수정되지 않은 작업 영역에서 스크립트를 성공적으로 실행해야 합니다. 즉, 패키지 및 종속성이 명시적으로 로드되고 실행되어야 합니다. *source()* 를 사용하여 종속 스크립트를 실행할 수 있습니다.

Power BI Desktop에서 R 스크립트를 준비하고 실행하는 경우 몇 가지 제한 사항이 있습니다.

* 데이터 프레임만 가져와서 Power BI로 가져오려는 데이터가 데이터 프레임에 표시되는지 확인
* 복합 및 벡터로 입력된 열을 가져오지 않고 만든 테이블의 오류 값으로 대체됩니다.
* N/A가 Power BI Desktop의 NULL 값으로 변환된 값
* 30분 이상 실행하는 R 스크립트는 시간이 초과됨
* 사용자 입력을 기다리는 등의 R 스크립트의 대화형 호출은 스크립트의 실행을 중지함
* R 스크립트 내에서 작업 디렉터리를 설정할 때 작업 디렉터리에 대해 상대 경로가 아닌 전체 경로를 정의 *해야* 합니다.

### <a name="run-your-r-script-and-import-data"></a>R 스크립트 실행 및 데이터 가져오기
1. Power BI Desktop에서 R 스크립트 데이터 커넥터는 **데이터 가져오기**에 위치합니다. R 스크립트를 실행하려면 다음 이미지에서 보여주듯이 **데이터 가져오기 &gt; 더 보기...**를 선택한 다음 **다른 &gt; R 스크립트**를 선택합니다.
   
   ![](media/desktop-r-scripts/r-scripts-1.png)
2. R이 로컬 컴퓨터에 설치되면 최신 설치된 버전은 R 엔진으로 선택됩니다. 단순히 스크립트 창에 스크립트를 복사하고 **확인**을 선택합니다.
   
   ![](media/desktop-r-scripts/r-scripts-2.png)
3. R 설치되어 있지 않거나 식별되지 않은 경우 또는 로컬 컴퓨터에 여러 가지 설치가 존재하는 경우 R 스크립트를 실행하려면 **R 설치 설정** 을 확장하여 설치 옵션을 표시하거나 수행하려는 설치를 선택합니다.
   
   ![](media/desktop-r-scripts/r-scripts-3.png)
   
   R가 설치되어 있지만 식별되지 않는 경우 **R 설치 설정**을 확장할 때 제공된 텍스트 상자에 명시적으로 위치를 제공할 수 있습니다. 위의 그림에서 *C:\Program Files\R\R-3.2.0* 경로는 텍스트 상자에 명시적으로 제공됩니다.
   
   R 설치 설정은 옵션 대화 상자의 R 스크립팅 섹션 중앙에 있습니다. R 설치 설정을 지정하려면 **파일 > 옵션 및 설정**, **옵션 > R 스크립팅**을 차례로 선택합니다. 여러 개의 R을 설치할 수 있는 경우 사용할 설치를 선택할 수 있는 드롭다운 메뉴가 나타납니다.
   
   ![](media/desktop-r-scripts/r-scripts-4.png)
4. **확인** 을 선택하여 R 스크립트를 실행합니다. 이 스크립트를 성공적으로 실행하는 경우 결과 데이터 프레임을 선택하여 Power BI 모델에 추가할 수 있습니다.

### <a name="refresh"></a>새로 고침
Power BI Desktop에서 R 스크립트를 새로 고칠 수 있습니다. R 스크립트를 새로 고칠 때 Power BI Desktop은 Power BI Desktop 환경에서 R 스크립트를 다시 실행합니다.

## <a name="next-steps"></a>다음 단계
Power BI의 R에 대한 자세한 내용은 다음을 참조하세요.

* [Power BI Desktop에서 R 시각적 개체 만들기](desktop-r-visuals.md)
* [Power BI로 외부 R IDE 사용](desktop-r-ide.md)

