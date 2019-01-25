---
title: Power BI 보고서 서버에 대한 변경 로그
description: Power BI 보고서 서버에 대한 이 변경 로그는 각 릴리스 빌드에 대한 버그 픽스와 새 항목을 나열합니다.
author: jtarquino
manager: kfile
ms.reviewer: maggies
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 03/31/2018
ms.author: jtarquino
ms.openlocfilehash: 18a2d6833f0013f95ac0a5dea5f1930e5b666dd6
ms.sourcegitcommit: 2c49a7cee9c77f46830ddfa59fdedbf30186d389
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54488871"
---
# <a name="changelog-for-power-bi-report-server"></a>Power BI 보고서 서버에 대한 변경 로그

Power BI 보고서 서버에 대한 이 변경 로그는 각 릴리스 빌드에 대한 버그 픽스와 새 항목을 나열합니다.

새로운 기능에 대한 자세한 내용은 [Power BI 보고서 서버의 새로운 기능](whats-new.md)을 참조하세요. 

## <a name="january-2019"></a>2019년 1월
- **Power BI Report Server**            
    - *버전 1.4.6960.38798(빌드 15.0.1102.222), 릴리스 날짜: 2019년 1월 22일*
        - 기능
            - Power BI 보고서 
                - 행 수준 보안 지원
                - 행렬 행 머리글의 확장 및 축소
                - .pbix 파일 간에 복사 및 붙여넣기
                - 스마트 맞춤 가이드
                - SAP BW 2.0 커넥터 지원
            - 관리자
                - 보고서 서버에 업로드할 수 있는 리소스 확장을 제한하는 기능
                - 지원되는 하이퍼링크 구성표를 제한하는 기능
        - 버그 픽스
            - HTML 삽입 취약성
            - PDF로 내보내기가 유로 기호를 표시하지 않습니다.
            - Power BI 보고서에 여러 데이터 원본이 있는 암호를 저장하면 변경되지 않은 암호가 무효화됨
            - 유휴 상태 후 시각적 개체가 Power BI 모바일 앱의 문제 표시

- **Power BI Desktop(Power BI Report Server에 최적화됨)**
    - *버전: 2.65.5313.1421(2019년 1월) 릴리스 날짜: 2019년 1월 22일*
        - Power BI Report Server에서 연결에 필요한 변경 내용 포함(2019년 1월)  

## <a name="august-2018"></a>2018년 8월
- **Power BI Report Server**
    - ‘버전 1.3.6816.37243(빌드 15.0.2.557), 릴리스 날짜: 2018년 8월 30일’
        - 버그 수정
            - 바인딩 리디렉션이 업데이트되지 않은 이전 버전의 PBI 보고서 서버에서 서버가 업그레이드될 때 다음이 표시되는 문제가 수정되었습니다.      
            *`
            Failed to load expression host assembly. Details: Could not load file or assembly 'Microsoft.ReportingServices.ProcessingObjectModel, Version=2018.7.0.0, Culture=neutral, PublicKeyToken=89845dcd8080cc91' or one of its dependencies. The located assembly's manifest definition does not match the assembly reference. (Exception from HRESULT: 0x80131040) (rsErrorLoadingExprHostAssembly)
             `*
             
            - 데이터 레이블 투명도에 대한 버그가 이제 수정되었습니다.
            
    - ‘버전 1.3.6801.38816(빌드 15.0.2.540), 릴리스 날짜: 2018년 8월 15일’
        - 기능
            - SAP HANA SSO 직접 쿼리는 Power BI 보고서에 대해 지금 사용할 수 있는 Kerberos에서 지원됩니다.
            - 릴리스 버전 1.13.0에서 사용자 지정 시각적 개체 API
            - 사용자 지정 시각적 개체는 현재 버전(있는 경우)의 서버 API와 호환 가능한 이전 버전으로 대체합니다.

- **Power BI Desktop(Power BI Report Server에 최적화됨)**
    - ‘버전: 2.61.5192.641(2018년 8월), 릴리스 날짜: 2018년 8월 15일’
        - Power BI Report Server에서 연결에 필요한 변경 내용 포함(2018년 8월)         
        
## <a name="march-2018"></a>2018년 3월
- **Power BI Report Server**
    - ‘버전 1.2.6690.34729(빌드 15.0.2.402), 릴리스 날짜: 2018년 4월 27일’
        - 버그 수정
            - SQL Server Reporting Services 2017 카탈로그의 마이그레이션 사용
            - Power BI 보고서(PBIX)의 경우
                - 서버가 사용자 지정 인증을 사용하도록 구성된 경우 보고서를 새로 고칠 수 있습니다.
                - 보고서의 속성을 수정해도 데이터 원본 자격 증명이 초기화되지 않습니다.
            - 페이지를 매긴 보고서(RDL)의 경우
                - RDL Expresssions에서 `Lookup()` 또는 파생 함수(예: `LookupSet()` 및 `MultiLookup()`)를 사용해도 더 이상 `#Error`가 생성되지 않습니다.
                - 연결된 보고서가 인쇄 시 대상 보고서의 페이지 크기를 유지합니다.
                - 연계 매개 변수를 사용하는 연결된 보고서에 대한 구독을 만들 수 있습니다.
                - IE11을 사용하는 경우 다중값 매개 변수 기본값을 수정할 수 있습니다.
                - 데이터 기반 구독 전송 옵션은 편집할 수 있습니다.
                - 구독을 실행하는 동안 구독을 보고 편집할 수 있습니다.
                - 데이터 원본 자격 증명을 설정해도 식 기반 연결 문자열이 제거되지 않습니다.
            - KPI의 경우
                - 데이터가 업데이트될 때 추세선이 새로 고침됩니다.
            - 일반 안정성 향상

    - ‘버전 1.2.6660.39920(빌드 15.0.2.389), 릴리스 날짜: 2018년 3월 28일’
        - 버그 수정
            - Power BI 보고서(PBIX)의 경우 Power BI 시각적 개체에서 작동하지 않는 데이터 내보내기에 대한 수정
            - Power BI 보고서(PBIX)의 경우 작동하지 않는 URL 필터에 대한 수정
            - 페이지를 매긴 보고서(RDL)의 경우 Power BI Report Server 3월 릴리스로 업그레이드한 후 IE11에서 올바르게 표시되지 않는 이미지에 대한 수정

    - ‘버전 1.2.6648.38132(빌드 15.0.2.378), 릴리스 날짜: 2018년 3월 19일’
        - 보안 업데이트
        - 내게 필요한 옵션 기능 향상
        - 버그 수정
            - 페이지를 매긴 보고서(RDL)의 경우 해당 속성을 편집한 후에 되돌릴 링크된 보고서에서 매개 변수 표시 여부에 대한 수정
            - 슬라이딩 만료 쿠키를 무시하는 사용자 지정 양식 인증이 포함된 웹 포털에 대한 수정
            - 행 콘텐츠가 비어 있는 경우 행 높이가 동일하지 않게 되는 Word로 내보내기에 대한 수정
            - 페이지를 매긴 보고서(RDL)의 경우 데이터 원본의 자격 증명을 변경할 때 삭제된 식 기반 연결 문자열에 대한 수정
            - 텍스트 값으로 KPI를 사용하는 기능에 대한 수정
            - 페이지를 매긴 보고서(RDL)의 경우 새 데이터 세트를 기존 페이지를 매긴 보고서(RDL)에 할당하는 기능 수정
            - 기타 안정성 및 유용성 수정

- **Power BI Desktop(Power BI Report Server에 최적화됨)**
    - 버전: 2.56.5023.1043(2018년 3월), 릴리스 날짜: 2018년 3월 19일
        - Power BI Report Server로 연결에 필요한 변경 내용 포함(2018년 3월)

## <a name="october-2017"></a>2017년 10월

- **Power BI Report Server**
    - ‘버전 1.1.6582.41691(빌드 14.0.600.442), 릴리스 날짜: 2018년 1월 10일’
        - 보안 업데이트
        - 버그 픽스
            - 400을 반환하는 Model.GetParameters 수정
            - 공유 데이터 집합을 기존의 페이지를 매긴 보고서(RDL)로 설정하는 문제 수정
            - 다른 매개 변수 값을 사용한 보고서를 PDF로 내보낼 때 ExecutionNotFoundException 수정

    - ‘버전 1.1.6551.5155(빌드 14.0.600.438), 릴리스 날짜: 2017년 12월 11일’
        - 버그 픽스
            - 특정 Power BI Desktop 보고서를 새로 고친 후 데이터가 저장되지 않습니다.

    - ‘버전 1.1.6530.30789(빌드 14.0.600.437), 릴리스 날짜: 2017년 11월 17일’
        - 버그 픽스
            - 기본 인증 시나리오에 대한 수정 
            - 포털의 구독, 캐시 새로 고침 계획 및 기록 스냅 샷의 일정 페이지에서 평일을 수정할 수 없는 문제 해결
            - 페이지가 매겨진 보고서(RDL)의 경우 CanGrow 속성이 false로 설정된 텍스트 상자에 식이 있는 경우 색상과 글꼴이 제대로 표시되지 않는 값이 생기는 문제 해결
            - PBIX(Power BI 보고서)의 경우 꺾은선형 차트에 범례를 추가하면 빈 시각적 개체가 렌더링되는 문제 해결

    - ‘버전 1.1.6514.9163(빌드 14.0.600.434), 릴리스 날짜: 2017년 11월 1일’
        - 버그 픽스
            - 500MB 초과 PBIX 보고서의 업로드 안정성 문제 해결
            - 1GB 초과 PBIX 보고서의 데이터 로드 문제 해결

    - ‘버전 1.1.6513.3500(빌드 14.0.600.433), 릴리스 날짜: 2017년 10월 31일’
        - 기능
            - 포함된 데이터 모델 지원
            - Excel 통합 문서 보기(Office Online Server 통합 사용)
            - 예약된 데이터 새로 고침(PBIX)
            - 직접 쿼리 지원
            - 큰 파일 지원(최대 2GB)
            - 공용 REST API
            - Power BI Desktop에서 공유 데이터 세트 지원(oData를 통해)
            - PBIX 파일에 대한 URL 매개 변수 지원
            - 내게 필요한 옵션 기능 향

- **Power BI Desktop(Power BI Report Server에 최적화됨)**
    - ‘버전: 2.51.4885.3981(2017년 10월), 릴리스 날짜: 2018년 4월 10일’
        - 보안 업데이트

    - ‘버전: 2.51.4885.2501(2017년 10월), 릴리스 날짜: 2018년 1월 10일’
        - 보안 업데이트

    - ‘버전: 2.51.4885.1423(2017년 10월), 릴리스 날짜: 2017년 11월 17일’
        - 버그 픽스
            - x86 OS에서 32비트 Power BI Desktop이 실행되지 않는 문제 해결
            - PBIX(Power BI Reports)의 경우 x 축 눈금선 표시 수정
            - 기타 사소한 버그 수정

    - ‘버전: 2.51.4885.1041(2017년 10월), 릴리스 날짜: 2017년 10월 31일’
        - 기능
            - Power BI Report Server로 연결에 필요한 변경 내용 포함(2017년 10월)

## <a name="june-2017"></a>2017년 6월

- **Power BI Report Server**
    - ‘빌드 14.0.600.309, 릴리스 날짜: 2018년 1월 10일’
        - 보안 업데이트

    - ‘빌드 14.0.600.305, 릴리스 날짜: 2017년 9월 19일’  
        - 버그 픽스
            - 최신 [Bing Maps 웹 컨트롤](https://msdn.microsoft.com/library/mt712542.aspx)로 업데이트

    - ‘빌드 14.0.600.301, 릴리스 날짜: 2017년 7월 11일’
        - 버그 픽스
            - Power BI 보고서에서 보고서를 실행한 사용자 대신 `{{UserId}}` 태그가 저장된 자격 증명으로 확인됩니다.
            - Power BI Server 보고서에서 일부 이미지가 렌더링되지 않습니다.
            - Power BI 보고서 서버에서 Power BI 보고서의 이름을 변경할 수 없습니다.
            - Power BI 모바일 애플리케이션에서 사용자 지정 시각적 개체를 로드할 수 없습니다(로컬 캐시 정리를 위해 모바일 앱을 다시 설치해야 함).

    - ‘빌드 14.0.600.271, 릴리스 날짜: 2017년 6월 12일’
        - Power BI Report Server 초기 릴리스

- **Power BI Desktop(Power BI Report Server에 최적화됨)**
    - ‘버전: 2.47.4766.4901(2017년 6월), 릴리스 날짜: 2018년 1월 10일’
        - 보안 업데이트

## <a name="next-steps"></a>다음 단계

[Power BI Report Server란?](get-started.md)
[관리자 개요](admin-handbook-overview.md)  
[Power BI Report Server 설치](install-report-server.md)  
[보고서 작성기 다운로드](https://www.microsoft.com/download/details.aspx?id=53613)  
[SSDT(SQL Server Data Tools) 다운로드](http://go.microsoft.com/fwlink/?LinkID=616714)

궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](https://community.powerbi.com/)
