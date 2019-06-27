---
title: Power BI 서비스에서 페이지를 매긴 보고서의 포함된 데이터 원본
description: 이 문서에서는 Power BI 서비스에서 페이지를 매긴 보고서의 포함된 데이터 원본을 만들고 수정하는 방법을 알아봅니다.
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.date: 06/06/2019
ms.openlocfilehash: 7b687fd67f844e000811ae00a53772ab9403ab90
ms.sourcegitcommit: 797bb40f691384cb1b23dd08c1634f672b4a82bb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/12/2019
ms.locfileid: "66838946"
---
# <a name="create-an-embedded-data-source-for-paginated-reports-in-the-power-bi-service"></a>Power BI 서비스에서 페이지를 매긴 보고서의 포함된 데이터 원본 만들기

이 문서에서는 Power BI 서비스에서 페이지를 매긴 보고서의 포함된 데이터 원본을 만들고 수정하는 방법을 알아봅니다. 단일 보고서에 포함된 데이터 원본을 정의하고 해당 보고서에서만 사용합니다. 현재 Power BI 서비스에 게시된 페이지를 매긴 보고서에는 포함된 데이터 세트 및 포함된 데이터 원본이 필요하며 이 보고서를 다음 데이터 원본에 연결할 수 있습니다.

- Azure SQL Database 및 Data Warehouse
- SQL Server
- SQL Server Analysis Services
- Oracle 
- Teradata 

다음 데이터 원본에 대해 [SQL Server Analysis Services 연결](service-premium-connect-tools.md) 옵션을 사용합니다.

- Azure Analysis Services
- Power BI Premium 데이터 세트

페이지를 매긴 보고서는 [Power BI 게이트웨이](service-gateway-getting-started.md)를 통해 온-프레미스 데이터 원본에 연결됩니다. 보고서를 Power BI 서비스에 게시한 후 게이트웨이를 설정합니다.

자세한 내용은 [Power BI 보고서 작성기의 보고서 데이터](report-builder-data.md)를 참조하세요.

## <a name="create-an-embedded-data-source"></a>포함된 데이터 원본 만들기
  
1. Power BI 보고서 작성기를 엽니다.

1. [보고서 데이터] 창의 도구 모음에서 **새로 만들기** > **데이터 원본**을 선택합니다. **데이터 원본 속성** 대화 상자가 열립니다.

    ![새 데이터 원본](media/paginated-reports-embedded-data-source/power-bi-paginated-new-data-source.png)
  
2.  **이름** 텍스트 상자에 데이터 원본의 이름을 입력하거나 기본값을 그대로 사용합니다.  
  
3.  **내 보고서에 포함된 연결 사용**을 선택합니다.  
  
1.  **연결 유형 선택** 목록에서 데이터 원본 형식을 선택합니다. 

1.  다음 방법 중 하나를 사용하여 연결 문자열을 지정합니다.  
  
    -   **연결 문자열** 텍스트 상자에 직접 연결 문자열을 입력합니다. 
  
    -   식(**fx)** 단추를 선택하여 연결 문자열로 평가되는 식을 만듭니다. **식** 대화 상자의 [식] 창에 식을 입력합니다. **확인**을 선택합니다. 
  
    -   **작성**을 선택하여 2단계에서 선택한 데이터 원본의 **연결 속성** 대화 상자를 엽니다.  
  
        **연결 속성** 대화 상자의 필드를 데이터 원본 형식에 맞게 채웁니다. 연결 속성에는 데이터 원본 형식, 데이터 원본 이름 및 사용할 자격 증명이 포함됩니다. 이 대화 상자에서 값을 지정한 후 **연결 테스트**를 선택하여 데이터 원본이 사용 가능하고 지정한 자격 증명이 올바른지 확인합니다.  
  
4.  **자격 증명**을 선택합니다.  
  
     이 데이터 원본에 사용할 자격 증명을 지정합니다. 데이터 원본의 소유자가 지원되는 자격 증명 유형을 선택합니다. 자세한 내용은 [보고서 데이터 원본에 대한 자격 증명 및 연결 정보 지정](https://docs.microsoft.com/sql/reporting-services/report-data/specify-credential-and-connection-information-for-report-data-sources)을 참조하세요.
  
5.  **확인**을 선택합니다.  
  
     데이터 원본은 [보고서 데이터] 창에 표시됩니다.  

## <a name="next-steps"></a>다음 단계

- [Power BI 서비스에서 페이지를 매긴 보고서의 포함된 데이터 세트 만들기](paginated-reports-create-embedded-dataset.md)
- [Power BI Premium에서 페이지를 매긴 보고서란?](paginated-reports-report-builder-power-bi.md)
