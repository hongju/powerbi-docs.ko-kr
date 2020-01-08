---
title: Power BI Service에서 텍스트로 반환된 중첩 값 문제 해결
description: 잘못된 데이터 원본 개인 정보 설정을 사용할 때 문자열로 변환되는 중첩 값을 수정하는 방법에 대해 알아보기
author: cpopell
ms.reviewer: ''
ms.custom: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: troubleshooting
ms.date: 6/4/2019
ms.author: gepopell
LocalizationGroup: Reports
ms.openlocfilehash: ab40ca9c415dacf52f4d82eb2c157d57aef92f93
ms.sourcegitcommit: 6272c4a0f267708ca7d38a45774f3bedd680f2d6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/06/2020
ms.locfileid: "73871277"
---
# <a name="troubleshooting-nested-values-returned-as-text-in-power-bi-service"></a>Power BI Service에서 텍스트로 반환된 중첩 값 문제 해결

## <a name="cause"></a>원인

이전에는 Power BI 보고서가 데스크톱에서 제대로 새로 고쳐졌지만 “값 "[Table]"을 테이블 형식으로 변환할 수 없습니다”와 같은 오류가 발생하여 Power BI 서비스에서 실패하는 경우가 있었습니다. 이 오류의 원인 중 하나는 데이터 개인 정보 방화벽이 데이터 원본을 버퍼링할 때 중첩된 스칼라가 아닌 값(예: 테이블, 레코드, 목록 및 함수)이 자동으로 텍스트 값(예: “[Table]” 또는 “[Record]”)으로 변환되기 때문입니다.

이제 Power BI 서비스가 개인 정보 수준 설정을 지원하거나 방화벽을 완전히 해제하므로 비프라이빗으로 Power BI 서비스의 [데이터 원본 개인 정보 설정을 구성](https://powerbi.microsoft.com/blog/privacy-levels-for-cloud-data-sources/)하여 이러한 오류를 방지할 수 있습니다.

6월 Power BI부터 방화벽이 중첩된 테이블/레코드/목록/등을 버퍼링할 때 이러한 값을 텍스트로 자동 변환하지 않고 다음과 같은 오류가 발생합니다. 

`We cannot return a value of type Table in this context`

## <a name="effect-on-loadrefresh"></a>로드/새로 고침에 미치는 영향

변경 내용은 방화벽 버퍼링에 의해 동기가 부여되지만 해당 영향은 로드/새로 고침까지 확장됩니다. 방화벽 버퍼링 동작을 해결하기 위해 중첩된 테이블/레코드/등을 Power BI 모델 및 Excel용 PQ의 Excel 데이터 모델로 로드하는 동작도 변경해야 했습니다. 이전에는 중첩된 테이블/레코드/등을 텍스트 값(예: “[Table]” 또는 “[Record]”)으로 로드할 수 있었습니다. 이제는 오류로 처리되어 로드된 테이블에 null 값이 표시되고 로드 결과에는 오류 수가 증가합니다.

이러한 오류는 로드/새로 고침 중에만 발생하므로 파워 쿼리 편집기에 표시되지 않습니다.

### <a name="before"></a>전

- 오류 없이 로드/새로 고침
- 로드된 테이블에는 “[Table]”, “[Record]” 등이 포함되어 있습니다.
 

### <a name="after"></a>후

- 오류와 함께 로드/새로 고침
- 로드된 테이블에는 NULL(“[Table]”, “[Record]” 대신)이 포함되어 있습니다.
 

## <a name="resolution"></a>해결 방법

스칼라가 아닌 값(예: 테이블, 목록, 레코드 등)이 포함된 열을 로드하시겠습니까?
그렇다면 열을 제거하여 오류를 제거할 수 있어야 합니다.
열을 제거할 수 없는 경우 사용자 지정 열을 추가하고 다음 샘플과 같은 논리를 사용하여 이전 동작을 복제할 수 있어야 합니다.

`if [MyColumn] is table then "[Table]" else if [MyColumn] is record then "[Record]" else if [MyColumn] is list then "[List]" else if [MyColumn] is function then "[Function]" else [MyColumn]`

모든 데이터 원본 개인 정보 설정을 프라이빗으로 설정한 경우 Power BI Desktop에서 이 문제가 재현되나요?
이 경우 비프라이빗으로 Power BI 서비스의 [해당 데이터 원본 개인 정보 설정을 구성](https://powerbi.microsoft.com/blog/privacy-levels-for-cloud-data-sources/)하여 오류를 해결할 수 있어야 합니다.
