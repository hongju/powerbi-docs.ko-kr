---
title: Power BI 서비스에 페이지를 매긴 보고서 게시
description: 이 자습서에서는 페이지를 매긴 보고서를 로컬 컴퓨터에서 업로드하여 Power BI 서비스에 게시하는 방법을 알아봅니다.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.date: 01/03/2020
ms.openlocfilehash: 5f77e17eccf4c99e7a391ea310a34848c604e01d
ms.sourcegitcommit: b68a47b1854588a319a5a2d5d6a79bba2da3a4e6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "75732087"
---
# <a name="publish-a-paginated-report-to-the-power-bi-service"></a>Power BI 서비스에 페이지를 매긴 보고서 게시

이 문서에서는 페이지를 매긴 보고서를 로컬 컴퓨터에서 업로드하여 Power BI 서비스에 게시하는 방법을 알아봅니다. 작업 영역이 프리미엄 용량에 포함된 경우 내 작업 영역 또는 다른 작업 영역에 페이지를 매긴 보고서를 업로드할 수 있습니다. 작업 영역 이름 옆의 다이아몬드 아이콘 ![Power BI Premium 용량 다이아몬드 아이콘](media/paginated-reports-save-to-power-bi-service/premium-diamond.png) 을 찾으세요. 

보고서 데이터 원본이 온-프레미스에 있는 경우 보고서를 업로드한 후 게이트웨이를 만들어야 합니다. 이 문서의 뒷부분에 있는 [게이트웨이 만들기](#create-a-gateway) 섹션을 참조하세요.

## <a name="add-a-workspace-to-a-premium-capacity"></a>프리미엄 용량에 작업 영역 추가

작업 영역의 이름 옆에 다이아몬드 아이콘 ![Power BI Premium 용량 다이아몬드 아이콘](media/paginated-reports-save-to-power-bi-service/premium-diamond.png) 이 없는 경우 작업 영역을 프리미엄 용량에 추가해야 합니다. 

1. **작업 영역**을 선택하고 작업 영역 이름 옆의 줄임표( **...** ), **작업 영역 편집**을 차례로 선택합니다.

    ![작업 영역 편집 선택](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-edit-workspace.png)

1. **작업 영역 편집** 대화 상자에서 **고급**을 확장하고 **전용 용량**을 **설정**으로 변경합니다.

    ![전용 용량 선택](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-edit-workspace-dialog.png)

   이 설정을 변경할 수 없는 경우도 있습니다. 변경할 수 없는 경우 Power BI Premium 용량 관리자에게 문의하여 프리미엄 용량에 작업 영역을 추가할 수 있는 할당 권한을 받으세요.

## <a name="from-report-builder-publish-a-paginated-report"></a>Report Builder에서 페이지를 매긴 보고서 게시

1. 보고서 작성기에서 페이지를 매긴 보고서를 만들어 로컬 컴퓨터에 저장합니다.

1. Report Builder **파일** 메뉴에서 **다른 이름으로 저장**을 선택합니다.

    ![파일 메뉴 > 저장 > 다른 이름으로 저장](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-save-as.png)

    Power BI에 아직 로그인하지 않은 경우 지금 로그인하거나 계정을 만들어야 합니다. Report Builder의 오른쪽 위에서 **로그인**을 선택하고 단계를 완료합니다.

2. 왼쪽의 작업 영역 목록에서 해당 이름 옆에 다이아몬드 아이콘(![Power BI Premium Capacity 다이아몬드 아이콘](media/paginated-reports-save-to-power-bi-service/premium-diamond.png))이 있는 작업 영역을 선택합니다. 상자에 **파일 이름**을 입력하고 > **저장**합니다. 

    ![Premium 작업 영역 선택](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-select-workspace.png)

4. 브라우저에서 Power BI 서비스를 열고 페이지를 매긴 보고서를 게시한 Premium 작업 영역을 찾습니다. **보고서** 탭에 보고서가 표시됩니다.

    ![보고서 목록의 페이지를 매긴 보고서](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-wwi-report.png)

5. 페이지를 매긴 보고서를 선택하여 Power BI 서비스에서 엽니다. 매개 변수가 있는 경우 보고서를 보려면 먼저 매개 변수를 선택해야 합니다.

    ![매개 변수 선택](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-select-parameters.png)

6. 보고서 데이터 원본이 온-프레미스에 있는 경우 이 문서에서 [게이트웨이 만들기](#create-a-gateway) 방법을 참조하여 데이터 원본에 액세스합니다.

## <a name="from-the-power-bi-service-upload-a-paginated-report"></a>Power BI 서비스에서 페이지를 매긴 보고서 업로드

Power BI 서비스에서 시작하여 페이지를 매긴 보고서를 업로드할 수도 있습니다.

1. 보고서 작성기에서 페이지를 매긴 보고서를 만들어 로컬 컴퓨터에 저장합니다.

1. 브라우저에서 Power BI 서비스를 열고 보고서를 게시할 Power BI Premium 작업 영역을 찾습니다. 이름 옆의 다이아몬드 아이콘 ![Power BI Premium 용량 다이아몬드 아이콘](media/paginated-reports-save-to-power-bi-service/premium-diamond.png) 에 유의하세요. 

1. **데이터 가져오기**를 선택합니다.

    ![Power BI 데이터 가져오기](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-get-data.png)

1. **파일** 상자에서 **가져오기**를 선택합니다.

    ![Power BI 파일 가져오기](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-files-get.png)

1. **로컬 파일** > [페이지를 매긴 보고서 찾아보기] > **열기**를 선택합니다.

    ![로컬 파일 선택](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-local-file.png)

1. **계속** > **자격 증명 편집**을 선택합니다.

    ![자격 증명 편집 선택](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-select-edit-credentials.png)

1. 자격 증명 > **로그인**을 구성합니다.

    ![자격 증명 편집](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-credentials.png)

   **보고서** 탭에 보고서가 표시됩니다.

    ![보고서 목록의 페이지를 매긴 보고서](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-wwi-report.png)

1. 보고서를 선택하여 Power BI 서비스에서 엽니다. 매개 변수가 있는 경우 보고서를 보려면 먼저 매개 변수를 선택해야 합니다.
 
    ![매개 변수 선택](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-select-parameters.png)

6. 보고서 데이터 원본이 온-프레미스에 있는 경우 이 문서에서 [게이트웨이 만들기](#create-a-gateway) 방법을 참조하여 데이터 원본에 액세스합니다.

## <a name="create-a-gateway"></a>게이트웨이 만들기

다른 Power BI 보고서와 마찬가지로 보고서 데이터 원본이 온-프레미스에 있는 경우 데이터에 액세스하려면 게이트웨이를 만들거나 연결해야 합니다.

1. 보고서 이름 옆에 있는 **관리**를 선택합니다.

   ![페이지를 매긴 보고서 관리](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-manage.png)

1. 자세한 내용 및 다음 단계를 보려면 Power BI 서비스 문서 [온-프레미스 데이터 게이트웨이란?](service-gateway-onprem.md)을 참조하세요.

### <a name="gateway-limitations"></a>게이트웨이 제한 사항

현재 게이트웨이는 다중값 매개 변수를 지원하지 않습니다.


## <a name="next-steps"></a>다음 단계

- [Power BI 서비스에서 페이지를 매긴 보고서 보기](consumer/paginated-reports-view-power-bi-service.md)
- [Power BI Premium에서 페이지를 매긴 보고서란?](paginated-reports-report-builder-power-bi.md)
- [자습서: 고객을 위해 애플리케이션에 페이지를 매긴 Power BI 보고서 포함](developer/embed-paginated-reports-customers.md)

