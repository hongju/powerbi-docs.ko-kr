---
title: '빠른 시작: Power BI Desktop에서 데이터에 연결'
description: Power BI Desktop에서 사용할 수 있는 데이터 원본에 연결하는 방법
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: quickstart
ms.date: 01/10/2020
ms.author: davidi
LocalizationGroup: quickstart
ms.openlocfilehash: 5aed52ec232d3e603d69bfe93640187401279ff6
ms.sourcegitcommit: 801d2baa944469a5b79cf591eb8afd18ca4e00b1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/11/2020
ms.locfileid: "75885231"
---
# <a name="quickstart-connect-to-data-in-power-bi-desktop"></a>빠른 시작: Power BI Desktop에서 데이터에 연결

이 빠른 시작에서는 데이터 모델을 빌드하고 보고서를 만드는 첫 번째 단계로서 Power BI Desktop을 사용하여 데이터에 연결합니다.

![Power BI Desktop](media/desktop-what-is-desktop/what-is-desktop_01.png)

아직 Power BI에 등록하지 않은 경우 시작하기 전에 [평가판에 등록합니다](https://app.powerbi.com/signupredirect?pbi_source=web).

## <a name="prerequisites"></a>필수 조건

이 문서의 단계를 완료하려면 다음 리소스가 필요합니다.

* 사용자의 로컬 컴퓨터에서 실행되는 무료 애플리케이션인 Power BI Desktop을 다운로드 및 설치합니다. 직접 [Power BI Desktop을 다운로드](https://powerbi.microsoft.com/desktop)하거나 [Microsoft Store](https://aka.ms/pbidesktopstore)에서 받을 수 있습니다.
* [이 샘플 Excel 통합 문서를 다운로드](https://go.microsoft.com/fwlink/?LinkID=521962)하고 Excel 파일을 저장할 수 있는 *C:\PBID-qs*라는 폴더를 만듭니다. 이 빠른 시작의 나중 단계에서는 이 폴더가 다운로드한 Excel 통합 문서의 파일 위치라고 가정합니다.
* Power BI Desktop의 여러 데이터 커넥터에서는 인증을 위해 Internet Explorer 10(또는 그 이상)이 필요합니다.

## <a name="launch-power-bi-desktop"></a>Power BI Desktop 시작

Power BI Desktop을 설치한 후 로컬 컴퓨터에서 실행되도록 애플리케이션을 시작합니다. Power BI 자습서가 제공됩니다. 자습서를 따라 하거나 대화 상자를 닫고 빈 캔버스를 시작합니다. 캔버스는 데이터에서 시각적 개체와 보고서를 만드는 곳입니다.

![빈 캔버스가 표시된 Power BI Desktop](media/desktop-quickstart-connect-to-data/qs-connect-data_01.png)

## <a name="connect-to-data"></a>데이터에 연결

Power BI Desktop을 사용하면 다양한 형식의 데이터에 연결할 수 있습니다. 이러한 원본에는 Microsoft Excel 파일과 같은 기본적인 데이터 원본도 있습니다. Salesforce, Microsoft Dynamics, Azure Blob Storage 등의 모든 데이터 종류를 포함하는 온라인 서비스에도 연결할 수 있습니다.

데이터에 연결하려면 리본 메뉴 **홈** 탭에서 **데이터 가져오기**를 선택합니다.

![홈 리본에서 데이터 가져오기](media/desktop-quickstart-connect-to-data/qs-connect-data_02.png)

**데이터 가져오기** 창이 표시됩니다. Power BI Desktop에서 연결할 수 있는 다양한 데이터 원본 중 하나를 선택할 수 있습니다. 이 빠른 시작에서는 [필수 구성 요소](#prerequisites) 섹션에서 다운로드한 Excel 통합 문서를 사용합니다.

![데이터 가져오기 모든 원본](media/desktop-quickstart-connect-to-data/qs-connect-data_03.png)

이 데이터 원본은 Excel 파일이므로 **데이터 가져오기** 창에서 **Excel**을 선택한 다음, **연결** 단추를 선택합니다.

연결할 Excel 파일의 위치를 제공하라는 메시지가 표시됩니다. 다운로드한 파일의 이름은 *Financial Sample*입니다. 이 파일을 선택하고 **열기**를 선택합니다.

![Financial Sample의 데이터 가져오기](media/desktop-quickstart-connect-to-data/qs-connect-data_04.png)

Power BI Desktop은 통합 문서를 로드하여 해당 내용을 읽고, **탐색기** 창을 사용하여 파일의 데이터를 표시합니다. 탐색기 창에서는 Power BI Desktop으로 어떤 데이터를 로드할지 선택할 수 있습니다. 가져올 각 테이블 옆의 확인란을 선택하여 테이블을 선택합니다. 테이블 두 개를 모두 가져옵니다.

![탐색기 창에서 데이터 선택](media/desktop-quickstart-connect-to-data/qs-connect-data_05.png)

선택한 후에 **로드**를 선택하여 데이터를 Power BI Desktop으로 가져옵니다.

## <a name="view-data-in-the-fields-pane"></a>필드 창에서 데이터 보기

테이블을 로드하면 **필드** 창에 데이터가 표시됩니다. 이름 옆의 화살표를 선택하여 각 테이블을 확장할 수 있습니다. 다음 이미지에서는 각 필드를 표시하는 *financials* 테이블이 확장됩니다.

![데이터 가져오기](media/desktop-quickstart-connect-to-data/qs-connect-data_06.png)

이것으로 끝입니다! Power BI Desktop에서 데이터에 연결하고 데이터를 로드했습니다. 이제 테이블에 있는 모든 필드를 볼 수 있습니다.

## <a name="next-steps"></a>다음 단계

데이터에 연결한 후에는 Power BI Desktop으로 다양한 작업을 수행할 수 있습니다. 일례로 시각적 개체와 보고서를 만들 수 있습니다. 시작하려면 다음 리소스를 살펴봅니다.

* [Power BI Desktop 시작](desktop-getting-started.md)
