---
title: SharePoint Server에서 iFrame을 사용하여 Power BI Report Server 보고서 포함
description: 이 문서에서는 SharePoint Server의 iFrame에 Power BI Report Server 보고서를 포함하는 방법을 보여 줍니다.
author: maggiesMSFT
ms.author: maggies
ms.date: 08/12/2019
ms.topic: conceptual
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.custom: mvc
ms.openlocfilehash: 4e7616ec3ce6552130848bc0508bf8b9ac8ac965
ms.sourcegitcommit: 97597ff7d9ac2c08c364ecf0c729eab5d59850ce
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2020
ms.locfileid: "75762603"
---
# <a name="embed-a-power-bi-report-server-report-using-an-iframe-in-sharepoint-server"></a>SharePoint Server에서 iFrame을 사용하여 Power BI Report Server 보고서 포함

이 문서에서는 SharePoint 페이지에서 iFrame을 사용하여 Power BI Report Server 보고서를 포함하는 방법을 알아봅니다. SharePoint Online에서 작업하는 경우 Power BI Report Server에 공개적으로 액세스할 수 있어야 합니다. SharePoint Online에서는 Power BI 서비스에서 작동하는 Power BI 웹 파트가 Power BI Report Server에서 작동하지 않습니다.  

![iFrame 샘플](media/quickstart-embed/quickstart_embed_01.png)

## <a name="prerequisites"></a>필수 조건
* [Power BI Report Server](https://powerbi.microsoft.com/report-server/)가 설치 및 구성되어 있습니다.
* [Power BI Report Server에 최적화된 Power BI Desktop](install-powerbi-desktop.md)이 설치되어 있습니다.
* [SharePoint](https://docs.microsoft.com/sharepoint/install/install) 환경이 설치 및 구성되어 있습니다.
* Internet Explorer 11은 문서 모드를 IE11(Edge) 모드로 설정한 경우 또는 SharePoint Online을 사용하는 경우에만 지원됩니다. SharePoint 온-프레미스와 SharePoint Online에서는 다른 지원되는 브라우저를 사용할 수 있습니다.

## <a name="create-the-power-bi-report-url"></a>Power BI 보고서 URL 만들기

1. GitHub에서 샘플을 다운로드합니다. [블로그 데모](https://github.com/Microsoft/powerbi-desktop-samples) **복제 또는 다운로드**를 선택한 다음, **ZIP 다운로드**를 선택합니다.

    ![샘플 PBIX 파일 다운로드](media/quickstart-embed/quickstart_embed_14.png)

2. 파일 압축을 풀고, Power BI Report Server에 최적화된 Power BI Desktop에서 샘플 .pbix 파일을 엽니다.

    ![PBI RS 데스크톱 도구](media/quickstart-embed/quickstart_embed_02.png)

3. 보고서를 **Power BI Report Server**에 저장합니다. 

    ![PBI RS 저장](media/quickstart-embed/quickstart_embed_03.png)

4. Power BI Report Server 웹 포털에서 보고서를 봅니다.

    ![웹 포털](media/quickstart-embed/quickstart_embed_04.png)

### <a name="capture-the-url-parameter"></a>URL 매개 변수 캡처

URL이 있으면 SharePoint 페이지 내에서 보고서를 호스트할 iFrame을 만들 수 있습니다. Power BI Report Server 보고서 URL의 경우 다음 쿼리 문자열 매개 변수를 추가하여 SharePoint iFrame에 보고서를 포함합니다. `?rs:embed=true`

   예:
    ``` 
    https://myserver/reports/powerbi/Sales?rs:embed=true
    ```
## <a name="embed-the-report-in-a-sharepoint-iframe"></a>SharePoint iFrame에 보고서 포함

1. SharePoint **사이트 콘텐츠** 페이지로 이동합니다.

    ![사이트 콘텐츠 페이지](media/quickstart-embed/quickstart_embed_05.png)

2. 보고서를 추가할 페이지를 선택합니다.

    ![사이트 콘텐츠 페이지 앱](media/quickstart-embed/quickstart_embed_06.png)

3. 오른쪽 위에 있는 기어 아이콘을 선택한 다음, **페이지 편집**을 선택합니다.

    ![페이지 편집 옵션](media/quickstart-embed/quickstart_embed_07.png)

4. **웹 파트 추가**를 선택합니다.

5. **범주**에서 **미디어 및 콘텐츠**를 선택합니다. **파트**에서 **콘텐츠 편집기**를 선택한 다음, **추가**를 선택합니다.

    ![콘텐츠 편집기 웹 파트 선택](media/quickstart-embed/quickstart_embed_09.png)

6. **새 콘텐츠를 추가하려면 여기를 클릭**을 선택합니다.

7. 위쪽 메뉴에서 **텍스트 서식**을 선택한 다음, **원본 편집**을 선택합니다.

     ![원본 편집](media/quickstart-embed/quickstart_embed_11.png)

8. **원본 편집** 창에서 iFrame 코드를 **HTML 소스**에 붙여넣고 **확인**을 선택합니다.

    ![iFrame 코드](media/quickstart-embed/quickstart_embed_12.png)

     예:
     ```html
     <iframe width="800" height="600" src="https://myserver/reports/powerbi/Sales?rs:embed=true" frameborder="0" allowFullScreen="true"></iframe>
     ```

9. 위쪽 메뉴에서 **페이지**를 선택한 다음, **편집 중지**를 선택합니다.

    ![편집 중지](media/quickstart-embed/quickstart_embed_13.png)

    보고서가 페이지에 표시됩니다.

    ![iFrame 샘플](media/quickstart-embed/quickstart_embed_01.png)

## <a name="next-steps"></a>다음 단계

- [Power BI Report Server용 Power BI 보고서 만들기](quickstart-create-powerbi-report.md)  
- [Power BI Report Server용 페이지를 매긴 보고서 만들기](quickstart-create-paginated-report.md)  

궁금한 점이 더 있나요? [Power BI 커뮤니티를 이용](https://community.powerbi.com/)하세요. 
