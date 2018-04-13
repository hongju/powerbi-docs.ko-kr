---
title: 모바일 앱용 Power BI Desktop에서 바코드 필드 태그
description: Power BI Desktop에서 모델의 바코드 필드에 태그를 지정하면 iPhone의 Power BI 앱에서 바코드에 대한 데이터를 자동으로 필터링할 수 있습니다.
services: powerbi
documentationcenter: ''
author: maggiesMSFT
manager: kfile
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/16/2018
ms.author: maggies
LocalizationGroup: Model your data
ms.openlocfilehash: 45cca153bbc65c5bad6c0f2ba8d41fbec4682ca5
ms.sourcegitcommit: c80fbf5b12754ce217cb47a17cb5400b1036a8f2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/06/2018
---
# <a name="tag-barcodes-in-power-bi-desktop-for-the-mobile-apps"></a>모바일 앱용 Power BI Desktop에서 바코드 태그
Power BI Desktop에서는 열의 [데이터 범주](desktop-data-categorization.md)를 지정하여 보고서의 시각적 개체에서 해당 값을 처리하는 방식을 Power BI Desktop에 알려줄 수 있습니다. 또한 열의 범주를 **바코드**로 지정할 수도 있습니다. 사용자 또는 사용자의 동료가 iPhone의 [Power BI 앱이 있는 제품에서 바코드를 스캔](mobile-apps-scan-barcode-iphone.md)하면 해당 바코드를 포함하는 모든 보고서가 표시됩니다. 모바일 앱에서 보고서를 열면 Power BI가 보고서를 바코드와 관련된 데이터로 자동으로 필터링합니다.

1. Power BI Desktop에서 데이터 보기로 전환합니다.
2. 바코드 데이터가 있는 열을 선택합니다. 아래 [지원되는 바코드 형식](#supported-barcode-formats) 목록을 참조하세요.
3. **모델링** 탭에서 **데이터 범주** > **바코드**를 선택합니다.
   
    ![데이터 범주 목록](media/desktop-mobile-barcodes/power-bi-desktop-barcode.png)
4. 보고서 보기에서 바코드로 필터링하려는 시각적 개체에 이 필드를 추가합니다.
5. 보고서를 저장하고 Power BI 서비스에 게시합니다.

이제 [iPhone용 Power BI 앱](mobile-ios-ipad-iphone-apps.md)에서 스캐너를 열고 바코드를 스캔하면 이 보고서가 보고서 목록에 표시됩니다. 보고서를 열면 해당하는 시각적 개체가 스캔한 제품 바코드로 필터링됩니다.

## <a name="supported-barcode-formats"></a>지원되는 바코드 형식
다음은 Power BI 보고서에서 태그를 지정한 경우 Power BI가 인식하는 바코드입니다. 

* UPCECode 
* Code39Code  
* A39Mod43Code 
* EAN13Code 
* EAN8Code  
* 93Code  
* 128Code 
* PDF417Code 
* Interleaved2of5Code 
* ITF14Code 

## <a name="next-steps"></a>다음 단계
* [iPhone에서 Power BI 앱의 바코드 스캔](mobile-apps-scan-barcode-iphone.md)
* [iPhone에서 바코드 스캔 문제](mobile-apps-scan-barcode-iphone.md#issues-with-scanning-a-barcode)
* [Power BI Desktop의 데이터 분류](desktop-data-categorization.md)  
* 궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](http://community.powerbi.com/)

