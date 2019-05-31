---
title: Power BI 서비스에서 페이지 매긴된 보고서를 구독합니다
description: 이 문서에서는 Power BI 서비스에서 페이지 매긴된 보고서를 구독 하는 방법에 대 한 고려 사항을 알아봅니다.
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.date: 05/24/2019
ms.openlocfilehash: ccec6658808d94728f2a4f14de67c36da0f51def
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "66222192"
---
# <a name="subscribe-yourself-and-others-to-paginated-reports-in-the-power-bi-service"></a>자신과 다른 사람이 Power BI 서비스에서 페이지 매긴된 보고서를 구독합니다 

이제 Power BI 서비스에서 페이지 매긴된 보고서에 대 한 직접 및 다른 사용자에 대 한 전자 메일 구독을 설정할 수 있습니다. 일반적으로 프로세스는 동일 [Power BI 서비스에서 보고서 및 대시보드 구독](service-report-subscribe.md)합니다. 이 문서에서는 차이점과 고려 사항을 제시 합니다. 

구독을 설정 하면 선택 전자 메일 수신 빈도: 매일, 매주 또는 시간입니다. 선택한 매일 또는 매주, 시간을 선택할 수 있습니다 하려는 경우 구독이 실행 되도록 합니다. 모든에서 모든 보고서에 대 한 일별 최대 24 개의 서로 다른 구독을 설정할 수 있습니다. 

## <a name="considerations-for-paginated-report-subscriptions"></a>페이지 매긴된 보고서 구독에 대 한 고려 사항 

- 대시보드 또는 Power BI 보고서에 대 한 구독을 달리 구독 전체 보고서 출력의 첨부 파일을 포함합니다.  다음 첨부 파일 유형이 지원 됩니다. PDF, PowerPoint 프레젠테이션 (PPTX), Excel 통합 문서 (XLSX), Word 문서 (DOCX), CSV 파일 및 XML입니다.

- 전자 메일 본문에 보고서의 미리 보기 이미지가 없습니다.  선택적 항목으로 보고서의 첫 페이지의 이미지를 할 예정입니다. 

- 최대 보고서 첨부 파일 크기는 25MB입니다. 

- Azure Analysis Services 또는 Power BI 데이터 집합을 포함 하 여 모든 현재 지원 되는 데이터 원본에 연결 되는 페이지 매긴된 보고서에 대 한 다른 사용자가 구독할 수 있습니다. SQL Server Reporting Services는 현재와 마찬가지로 보고서 첨부 파일 사용 권한에 따라 데이터를 반영 염두에 두어야 합니다. 

- 보고서 페이지 구독은 보고서의 이름으로 연결 됩니다.  

- 전자 메일 구독은 보고서의 기본 매개 변수 값을 사용 하 여 전송 됩니다. 

- 방법이 없는 **데이터 새로 고침 후** 페이지 매긴된 보고서를 사용 하 여 빈도 대 한 옵션입니다. 항상 데이터 원본에서 최신 값을 가져옵니다. 

## <a name="next-steps"></a>다음 단계

[자신과 다른 사람이 Power BI 서비스에서 보고서 및 대시보드 구독](service-report-subscribe.md)

[Power BI Premium의 페이지를 매긴 보고서란? (미리 보기)](paginated-reports-report-builder-power-bi.md)
