---
title: Power BI 서비스의 페이지를 매긴 보고서 구독
description: 이 문서에서는 Power BI 서비스의 페이지를 매긴 보고서를 구독하는 방법에 대해 고려해야 할 사항을 알아봅니다.
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.date: 05/24/2019
ms.openlocfilehash: 472606fcb3b823cdcb722c9d8d6421d0ec652d24
ms.sourcegitcommit: 797bb40f691384cb1b23dd08c1634f672b4a82bb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/12/2019
ms.locfileid: "66839552"
---
# <a name="subscribe-yourself-and-others-to-paginated-reports-in-the-power-bi-service"></a>Power BI 서비스의 페이지가 매겨진 보고서에 자신과 다른 사용자 구독 

이제 Power BI 서비스에서 페이지를 매긴 보고서에 대한 이메일 구독을 자신과 다른 사용자에게 설정할 수 있습니다. 일반적으로 프로세스는 [Power BI 서비스의 보고서 및 대시보드에 구독하는 것](service-report-subscribe.md)과 같습니다. 이 문서에서는 차이점과 고려 사항을 설명합니다. 

구독 설정 시 이메일 수신 빈도(매일, 매주 또는 매시간)를 선택합니다. 매일 또는 매주를 선택하면 구독을 실행할 시간을 선택할 수 있습니다. 모든 보고서에 대해 하루 최대 24개의 서로 다른 구독을 설정할 수 있습니다. 

## <a name="considerations-for-paginated-report-subscriptions"></a>페이지를 매긴 보고서 구독에 대한 고려 사항 

- 대시보드 또는 Power BI 보고서에 대한 구독과 달리 사용자 구독에는 전체 보고서 출력의 첨부 파일이 포함되어 있습니다.  다음과 같은 첨부 파일 유형이 지원됩니다. PDF, PowerPoint 프레젠테이션(PPTX), Excel 통합 문서(XLSX), Word 문서(DOCX), CSV 파일 및 XML.

- 이메일 본문에는 보고서의 미리 보기 이미지가 없습니다.  보고서 첫 페이지의 이미지를 선택 항목으로 가질 계획입니다. 

- 최대 보고서 첨부 파일 크기는 25MB입니다. 

- Azure Analysis Services 또는 Power BI 데이터 세트를 비롯하여 현재 지원되는 모든 데이터 원본에 연결된 페이지를 매긴 보고서에 대해 다른 사용자도 구독할 수 있습니다. 현재 SQL Server Reporting Services에서와 마찬가지로 보고서 첨부 파일도 사용 권한에 따라 데이터를 반영한다는 점에 유의합니다. 

- 보고서 페이지 구독은 보고서 이름과 연결됩니다.  

- 이메일 구독은 보고서의 기본 매개 변수 값과 함께 보내집니다. 

- 페이지를 매긴 보고서가 있는 빈도에 대한 **데이터 새로 고침 후** 옵션이 없습니다. 기본 데이터 원본에서 항상 최신 값을 가져옵니다. 

## <a name="next-steps"></a>다음 단계

[Power BI 서비스의 보고서 및 대시보드에 자신과 다른 사용자 구독](service-report-subscribe.md)

[Power BI Premium에서 페이지를 매긴 보고서란?](paginated-reports-report-builder-power-bi.md)
