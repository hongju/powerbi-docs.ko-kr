---
title: 쉼표로 구분된 값(.csv) 파일에서 데이터 가져오기
description: CSV 파일에서 Power BI로 데이터를 가져오는 방법 알아보기
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Data from files
ms.openlocfilehash: 1a150c2cb4eb819b78b2b08a492087eb98bf6363
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "65513328"
---
# <a name="get-data-from-comma-separated-value-csv-files"></a>쉼표로 구분된 값(.csv) 파일에서 데이터 가져오기
![](media/service-comma-separated-value-files/csv_icon.png)

쉼표로 구분된 값 파일(또는 .CSV)은 각 값이 쉼표로 구분되어 있는 데이터 열로 구성된 단순한 텍스트 파일입니다. 이러한 유형의 파일은 상대적으로 적은 파일 크기에 매우 많은 양의 데이터를 포함할 수 있어 Power BI에 적합한 데이터 원본입니다. [여기](http://go.microsoft.com/fwlink/?LinkID=619356)에서 샘플 .CSV 파일을 다운로드할 수 있습니다.

.CSV가 있다면 Power BI 사이트를 사용자가 데이터를 탐색을 시작하고 일부 대시보드를 만들며 다른 사람들과 통찰력을 공유할 수 있는 데이터 세트로 활용할 시간입니다.

>[!TIP]
>많은 조직에서 매일 업데이트된 데이터로 .CSV를 출력하고 있습니다. Power BI에서 데이터 세트가 업데이트된 파일과 동기화를 유지하려면 해당 파일이 같은 이름으로 OneDrive에 저장되어 있어야 합니다.

## <a name="where-your-file-is-saved-makes-a-difference"></a>파일 저장 위치는 중요합니다.
**로컬** - .CSV 파일을 사용자 컴퓨터의 로컬 드라이브 또는 조직의 다른 위치에 저장하는 경우 Power BI에서 파일을 Power BI로 *가져올* 수 있습니다. 파일은 사실 로컬 드라이브에 그대로 남아 있으므로, 전체 파일을 실제로 Power BI로 가져온 것은 아닙니다. 실제로는, 새 데이터 세트가 Power BI에서 만들어지고 .CSV 파일의 데이터가 데이터 세트로 로드되는 것입니다.

**OneDrive - 비즈니스** – 비즈니스용 OneDrive가 있고 Power BI에 로그인하는 같은 계정으로 로그인할 경우 Power BI에서 사용자의 .CSV 파일과 데이터 세트, 보고서, 그리고 대시보드의 동기화를 유지하는 가장 효율적인 방법입니다. Power BI와 OneDrive가 클라우드에 있으므로 Power BI는 매시간 OneDrive의 파일에 연결합니다.  변경 내용이 발견되면 데이터 세트, 보고서 및 대시보드가 Power BI에서 자동으로 업데이트됩니다.

**OneDrive - 개인** – 본인의 OneDrive 계정으로 파일을 저장할 경우 비즈니스용 OneDrive에 제공하는 것과 동일한 많은 혜택을 누릴 수 있습니다. 가장 큰 차이점은 파일에 처음 연결할 때(‘데이터 가져오기’ > ‘파일’ > ‘OneDrive - 개인’ 사용) Microsoft 계정으로 OneDrive에 로그인해야 한다는 점이 가장 큰 차이점이며, 일반적으로 Power BI에 로그인하기 위해 사용하는 것과는 다릅니다. Microsoft 계정으로 OneDrive에 로그인할 경우 로그인 유지 옵션을 선택해야 합니다. 이러한 방식으로 Power BI는 매시간 파일에 연결할 수 있으며 Power BI의 데이터 세트는 동기화를 유지하게 됩니다.

**SharePoint 팀 사이트** – Power BI Desktop 파일을 SharePoint 팀 사이트에 저장하는 것은 비즈니스용 OneDrive에 저장하는 것과 상당히 같습니다. 가장 큰 차이점은 Power BI에서 파일에 연결하는 방법입니다. URL을 지정하거나 루트 폴더에 연결할 수 있습니다.

## <a name="import-or-connect-to-a-csv-file"></a>.CSV 파일 가져오기 또는 연결
>[!IMPORTANT]
>Power BI로 가져올 수는 최대 파일 크기는 1GB입니다.

1. Power BI의 탐색 창에서 **데이터 가져오기**를 클릭합니다.
   
   ![](media/service-comma-separated-value-files/csv_get_data_button.png)
2. **파일**에서 **가져오기**를 클릭합니다.
   
   ![](media/service-comma-separated-value-files/csv_files_get.png)
3. 파일을 찾습니다.
   
   ![](media/service-comma-separated-value-files/csv_find_your_file.png)

## <a name="next-steps"></a>다음 단계
**데이터 탐색** - 파일에서 Power BI로 데이터를 가져오면 이제 살펴볼 차례입니다. 새 데이터 세트를 마우스 오른쪽 단추로 클릭한 다음, **탐색**을 클릭합니다.

**새로 고침 일정** - 파일이 로컬 드라이브에 저장된 경우 Power BI의 데이터 세트 및 보고서가 최신 상태를 유지하도록 예약된 새로 고침을 설정할 수 있습니다. 자세한 내용은 [Power BI에서 데이터 새로 고침](refresh-data.md)을 참조하십시오. 파일이 OneDrive에 저장되면 Power BI는 매시간 자동으로 동기화합니다.

