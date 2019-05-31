---
title: Power BI에서 보기 위해 Excel 통합 문서 크기 줄이기
description: Power BI에서 보기 위해 Excel 통합 문서 크기 줄이기
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 01/10/2019
ms.author: davidi
LocalizationGroup: Data from files
ms.openlocfilehash: 111e38fd37bcdfa2a72986bb08a37d89345bbe69
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "60972615"
---
# <a name="reduce-the-size-of-an-excel-workbook-to-view-it-in-power-bi"></a>Power BI에서 보기 위해 Excel 통합 문서 크기 줄이기
1GB 미만의 Excel 통합 문서를 Power BI에 업로드할 수 있습니다. Excel 통합 문서에는 두 부분이 있습니다. 데이터 모델과, 보고서의 나머지 부분(핵심 워크시트 컨텐츠)입니다. 보고서가 다음 크기 제한에 적합한 경우, **비즈니스용 OneDrive**에 저장하고 Power BI에 연결하여 Excel Online에서 볼 수 있습니다.

* 전체 통합 문서가 최대 1GB.
* 핵심 워크시트 콘텐츠가 최대 30MB.

## <a name="what-makes-core-worksheet-contents-larger-than-30-mb"></a>핵심 워크시트 콘텐츠가 30MB를 넘게 만드는 원인
핵심 워크시트 콘텐츠가 30MB를 넘게 만드는 일부 요소는 다음과 같습니다.

* 이미지.
* 음영 처리 된 셀. [셀 음영 서식을 제거합니다](https://support.office.com/article/Add-or-change-the-background-color-of-cells-ac10f131-b847-428f-b656-d65375fb815e).
* 색이 지정된 워크시트. [시트 배경을 제거합니다](https://support.office.com/article/add-or-remove-a-sheet-background-3577a762-8450-4556-96a2-cc265abc00a8).
* 텍스트 상자.
* 클립 아트.

가급적 이런 요소들을 제거하도록 하십시오. 

보고서에 데이터 모델이 있으면 다른 옵션도 있습니다. 

* Excel 워크시트에서 데이터를 제거하고, 대신 데이터 모델에 저장합니다. 자세한 내용은 아래의 “워크시트에서 데이터 제거”를 참조하십시오. 
* [메모리 효율적인 데이터 모델을 만들어서](https://support.office.com/article/Create-a-memory-efficient-Data-Model-using-Excel-2013-and-the-Power-Pivot-add-in-951c73a9-21c4-46ab-9f5e-14a2833b6a70) 보고서의 전체 크기를 줄입니다.

이런 변경을 하려면 Excel에서 통합 문서를 편집해야 합니다.

자세한 내용은 [SharePoint Online에서 Excel 통합 문서 파일 크기 제한](https://support.office.com/article/File-size-limits-for-workbooks-in-SharePoint-Online-9e5bc6f8-018f-415a-b890-5452687b325e)을 참조합니다.

## <a name="remove-data-from-worksheets"></a>워크시트에서 데이터 제거
Power Query 탭이나 Excel Data 탭에서 Excel로 데이터를 불러온 경우, 통합 문서는 Excel 테이블 및 데이터 모델과 동일한 데이터를 가질 수 있습니다. Excel 워크시트의 대형 테이블은 핵심 워크시트 콘텐츠를 30MB 이상으로 만들 수 있습니다. Excel에서 테이블을 제거하고 데이터를 데이터 모델에 저장하면 보고서의 핵심 워크시트 컨텐츠를 대폭 줄일 수 있습니다. 

Excel로 데이터를 가져올 때는 다음 팁을 따르십시오.

* **파워 쿼리에서**: **워크시트에 로드** 상자의 선택을 취소합니다.
  
  데이터를 데이터 모델에만 가져오고 엑셀 워크시트에는 가져오지 않습니다.
* **Excel Data 탭에서**([가져오기] 마법사에서 **테이블**이 선택되어 있는 경우): **기존 연결**로 이동하고 \> 연결 \> **연결만 만들기**를 클릭합니다. 원본 테이블이나 초기 가져오기 중에 만들어진 테이블을 삭제합니다.
* **Excel Data 탭에서**: **데이터 가져오기** 상자의 **테이블** 선택 상자에 표시하지 마십시오.

## <a name="workbook-size-optimizer"></a>통합 문서 크기 최적화 프로그램
통합 문서가 데이터 모델을 포함하는 경우 통합 문서 크기 최적화 프로그램을 실행하여 통합 문서 크기를 줄일 수 있습니다. [통합 문서 크기 최적화 프로그램을 다운로드](https://www.microsoft.com/download/details.aspx?id=38793)합니다.

## <a name="related-info"></a>관련된 정보
[메모리 효율적인 데이터 모델 만들기](https://support.office.com/article/Create-a-memory-efficient-Data-Model-using-Excel-2013-and-the-Power-Pivot-add-in-951c73a9-21c4-46ab-9f5e-14a2833b6a70)

[Power BI Desktop에서 비즈니스용 OneDrive 링크 사용](desktop-use-onedrive-business-links.md)

