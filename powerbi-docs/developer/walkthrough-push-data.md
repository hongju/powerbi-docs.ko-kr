---
title: "데이터 집합에 데이터 푸시"
description: "Power BI 데이터 집합에 데이터 푸시"
services: powerbi
documentationcenter: 
author: guyinacube
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/05/2017
ms.author: asaxton
ms.openlocfilehash: aba135a0a790025f732379ecb07157f1150d999c
ms.sourcegitcommit: 7517c068db806f12bb0b953e9a1bd4249ca12da5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/05/2018
---
# <a name="push-data-into-a-power-bi-dataset"></a>Power BI 데이터 집합에 데이터 푸시
Power BI API를 사용하여 데이터를 Power BI 데이터 집합에 푸시할 수 있습니다. 예를 들어 기존 비즈니스 워크플로를 확장하여 키 데이터를 데이터 집합에 푸시하고자 한다고 가정합니다. 여기서는 Product 테이블을 포함하는 Sales Marketing 데이터 집합을 데이터 집합에 푸시하려고 합니다.

데이터 집합에 데이터 푸시를 시작하기 전에 Azure AD(Azure Active Directory) 및 [Power BI 계정](create-an-azure-active-directory-tenant.md)이 필요합니다.

## <a name="steps-to-push-data-into-a-dataset"></a>데이터 집합에 데이터를 푸시하는 단계
* 1단계: [Azure AD에 앱 등록](walkthrough-push-data-register-app-with-azure-ad.md)
* 2단계: [인증 액세스 토큰 가져오기](walkthrough-push-data-get-token.md)
* 3단계: [Power BI에서 데이터 집합 만들기](walkthrough-push-data-create-dataset.md)
* 4단계:[ Power BI 테이블에 행을 추가할 데이터 집합 가져오기](walkthrough-push-data-get-datasets.md)
* 5단계: [Power BI 테이블에 행 추가](walkthrough-push-data-add-rows.md)

다음 섹션에서는 데이터를 푸시하는 Power BI API 작업에 대한 일반적인 내용을 설명합니다.

## <a name="power-bi-api-operations-to-push-data"></a>데이터를 푸시하는 Power BI API 작업
Power BI REST API를 사용하여 데이터 원본을 Power BI로 푸시할 수 있습니다. 앱이 데이터 집합에 행을 추가하면 대시보드의 타일이 업데이트된 데이터와 함께 자동으로 업데이트됩니다. 데이터를 푸시하려면 [데이터 집합 만들기](https://msdn.microsoft.com/library/mt203562.aspx) 작업과 함께 [행 추가](https://msdn.microsoft.com/library/mt203561.aspx) 작업을 사용합니다. 데이터 집합을 찾으려면 [데이터 집합 가져오기](https://msdn.microsoft.com/library/mt203567.aspx) 작업을 사용합니다. 이러한 작업에서는 그룹 ID를 전달하여 그룹으로 작업할 수 있습니다. 그룹 ID 목록을 가져오려면 [그룹 가져오기](https://msdn.microsoft.com/library/mt243842.aspx) 작업을 사용합니다.

데이터 집합에 데이터를 푸시하는 작업은 다음과 같습니다.

* [데이터 집합 만들기](https://msdn.microsoft.com/library/mt203562.aspx)
* [데이터 집합 가져오기](https://msdn.microsoft.com/library/mt203567.aspx)
* [행 추가](https://msdn.microsoft.com/library/mt203561.aspx)
* [그룹 가져오기](https://msdn.microsoft.com/library/mt243842.aspx)

Power BI에서 데이터 집합을 만들려면 Power BI 서비스에 JSON(JavaScript Object Notation) 문자열을 전달합니다. JSON에 대한 자세한 내용은 [JSON 소개](http://json.org/)를 참조하세요.

데이터 집합에 대한 JSON 문자열의 형식은 다음과 같습니다.

**Power BI 데이터 집합 JSON 개체**

    {"name": "dataset_name", "tables":
        [{"name": "", "columns":
            [{ "name": "column_name1", "dataType": "data_type"},
             { "name": "column_name2", "dataType": "data_type"},
             { ... }
            ]
          }
        ]
    }

여기의 Sales Marketing 데이터 집합 예제에서는 아래 예제와 같은 JSON 문자열을 전달합니다. 이 예제에서 **SalesMarketing** 은 데이터 집합의 이름이고 **Product** 는 테이블의 이름입니다. 테이블을 정의한 후 테이블 스키마를 정의합니다. **SalesMarketing** 데이터 집합의 경우 테이블 스키마는 ProductID, Manufacturer, Category, Segment, Product 및 IsCompete 열을 포함합니다.

**예제 데이터 집합 개체 JSON**

    {
        "name": "SalesMarketing",
        "tables": [
            {
                "name": "Product",
                "columns": [
                {
                    "name": "ProductID",
                    "dataType": "int"
                },
                {
                    "name": "Manufacturer",
                    "dataType": "string"
                },
                {
                    "name": "Category",
                    "dataType": "string"
                },
                {
                    "name": "Segment",
                    "dataType": "string"
                },
                {
                    "name": "Product",
                    "dataType": "string"
                },
                {
                    "name": "IsCompete",
                    "dataType": "bool"
                }
                ]
            }
        ]
    }

Power BI 테이블 스키마에는 다음과 같은 데이터 형식을 사용할 수 있습니다.

## <a name="power-bi-table-data-types"></a>Power BI 테이블 데이터 형식
| **데이터 형식** | **제한 사항** |
| --- | --- |
| Int64 |Int64.MaxValue 및 Int64.MinValue는 허용되지 않습니다. |
| Double |Double.MaxValue 및 Double.MinValue 값은 허용되지 않습니다. NaN은 지원되지 않습니다.+Infinity 및 -Infinity는 일부 함수(예: Min, Max)에서 지원되지 않습니다. |
| 부울 값 |없음 |
| 날짜/시간 |데이터 로드 동안 일 분수가 포함된 값을 1/300초(3.33ms)의 배수로 양자화합니다. |
| 문자열 |현재 최대 128K자를 허용합니다. |

## <a name="learn-more-about-pushing-data-into-power-bi"></a>Power BI에 데이터 푸시에 대해 자세히 알아보기
데이터 집합에 데이터 푸시를 시작하려면 왼쪽 탐색 창에서 [1단계: Azure AD에 앱 등록](walkthrough-push-data-register-app-with-azure-ad.md)을 참조하세요.

[다음 단계 >](walkthrough-push-data-register-app-with-azure-ad.md)

## <a name="next-steps"></a>다음 단계
[Power BI에 등록](create-an-azure-active-directory-tenant.md)  
[데이터 집합 만들기](https://msdn.microsoft.com/library/mt203562.aspx)  
[데이터 집합 가져오기](https://msdn.microsoft.com/library/mt203567.aspx)  
[행 추가](https://msdn.microsoft.com/library/mt203561.aspx)  
[그룹 가져오기](https://msdn.microsoft.com/library/mt243842.aspx)  
[JSON 개요](http://json.org/)  
[Power BI REST API 개요](overview-of-power-bi-rest-api.md)  
궁금한 점이 더 있나요? [Power BI 커뮤니티를 이용하세요.](http://community.powerbi.com/)

