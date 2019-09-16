---
title: Power BI Desktop에서 CSV 파일에 연결
description: Power BI Desktop에서 CSV 파일 데이터에 쉽게 연결하고 사용
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 08/29/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 8eecbfdaa948163ab6d0623a70f237d479fcdb88
ms.sourcegitcommit: a00fe5fb545c3df13b7cd13a701fd6a2b2521a17
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/31/2019
ms.locfileid: "70200938"
---
# <a name="connect-to-csv-files-in-power-bi-desktop"></a>Power BI Desktop에서 CSV 파일에 연결
Power BI Desktop에서 쉼표로 구분된 값(*CSV*) 파일에 연결하는 것은 Excel 통합 문서에 연결하는 것과 매우 유사합니다. 둘 다 간편하며 이 문서에서는 액세스 권한이 있는 CSV 파일에 연결하는 방법을 단계별로 안내합니다.

시작하려면 Power BI Desktop의 **홈** 리본에서 **데이터 가져오기 > CSV**를 선택합니다.

![](media/desktop-connect-csv/connect-to-csv_1.png)

나타나는 **열기** 대화 상자에서 CSV 파일을 선택합니다.

![](media/desktop-connect-csv/connect-to-csv_2.png)

**열기**를 선택하면 Power BI Desktop이 파일에 액세스하고 특정 파일 특성(예: 파일 원본, 구분 기호 형식, 파일에서 데이터 형식을 검색하는 데 사용해야 하는 행 수)을 확인합니다.

이러한 파일 특성 및 옵션은 다음과 같이 **CSV 가져오기** 대화 상자 창 맨 위에 드롭다운 선택 항목으로 표시됩니다. 이러한 검색된 설정은 드롭다운 선택기 중에서 다른 옵션을 선택하여 수동으로 변경할 수 있습니다.

![](media/desktop-connect-csv/connect-to-csv_3.png)

선택 항목에 만족하는 경우 **로드**를 선택하여 파일을 Power BI Desktop으로 가져오거나 **편집**을 선택하여 **쿼리 편집기**를 열고 데이터를 가져오기 전에 모양을 지정하거나 변환할 수도 있습니다.

데이터를 Power BI Desktop에 로드하면 Power BI Desktop의 보고서 보기 오른쪽을 따라 테이블 및 해당 열(Power BI Desktop에 필드로 표시됨)이 **필드** 창에 표시됩니다.

![](media/desktop-connect-csv/connect-to-csv_4.png)

작업이 다 끝났습니다. 이제 CSV 파일의 데이터가 Power BI Desktop에 들어가 있습니다.

Power BI Desktop에서 해당 데이터를 사용하여 시각적 개체, 보고서를 만들거나 Excel 통합 문서, 데이터베이스 또는 기타 데이터 원본처럼 연결 및 가져오려는 다른 모든 데이터를 조작할 수 있습니다.

> [!IMPORTANT]
> CSV 파일을 가져올 때 Power BI Desktop은 *columns=x*(여기서 *x*는 초기 가져오기 동안 CSV 파일의 열 수)를 파워 쿼리 편집기의 단계로 생성합니다. 나중에 더 많은 열을 추가하고 데이터 원본을 새로 고치도록 설정한 경우에는 초기 *x* 열 수를 초과하는 열이 새로 고쳐지지 않습니다. 


## <a name="next-steps"></a>다음 단계
Power BI Desktop을 사용하여 연결할 수 있는 모든 종류의 데이터가 있습니다. 데이터 원본에 대한 자세한 내용은 다음 리소스를 확인하세요.

* [Power BI Desktop이란?](desktop-what-is-desktop.md)
* [Power BI Desktop의 데이터 원본](desktop-data-sources.md)
* [Power BI Desktop에서 데이터 셰이핑 및 결합](desktop-shape-and-combine-data.md)
* [Power BI Desktop에서 Excel 통합 문서에 연결](desktop-connect-excel.md)   
* [Power BI Desktop에 데이터 직접 연결](desktop-enter-data-directly-into-desktop.md)   

