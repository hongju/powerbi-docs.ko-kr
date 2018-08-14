---
title: Power BI URL
description: 엔드포인트는 Power BI를 사용하여 고객에게 연결할 수 있어야 합니다.
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 08/13/2018
ms.openlocfilehash: 8e29fa0c9471bb865619102247f38776208c3d87
ms.sourcegitcommit: 8990028a348b642ba5c96f001fe3a4280f0166ee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/14/2018
ms.locfileid: "40101134"
---
# <a name="power-bi-urls"></a>Power BI URL

Power BI SaaS(Software-as-a-service) 응용 프로그램이라고도 하는 **Power BI 온라인 서비스**는 인터넷에 연결되어 있어야 합니다. 아래 엔드포인트는 Power BI 온라인 서비스를 사용하여 고객에게 연결할 수 있어야 합니다.

Power BI 온라인 서비스를 사용하려면 아래 테이블에 **필수**라고 표시된 엔드포인트 및 연결된 사이트에서 **필수**라고 표시된 엔드포인트에 연결하는 액세스 권한이 있어야 합니다. 외부 사이트에 대한 링크가 특정 섹션을 가리키는 경우 해당 섹션에서 엔드포인트를 검토해야 합니다.

**선택적**이라고 표시된 엔드포인트는 특정 기능이 작동하도록 **허용 목록에 추가**될 수 있습니다.

Power BI 온라인 서비스에서는 TCP 포트 443이 나열된 엔드포인트에 대해 열려야 합니다.

와일드 카드(*)는 루트 도메인 아래에 있는 모든 수준을 나타내고 정보를 사용할 수 없는 경우 해당 없음을 사용합니다. **대상** 열은 FQDN/도메인을 포함하는 목록이며 외부 사이트로 연결됩니다. 여기에는 추가 엔드포인트 정보가 포함됩니다.

>[!Important]
>아래 표의 정보는 **미국 정부 클라우드**, **독일 클라우드** 및 **중국 클라우드**를 나타내지 않습니다.

## <a name="authentication"></a>인증

Power BI는 Office 365 인증 및 ID 섹션에 있는 필수 엔드포인트에 따라 달라집니다. Power BI를 사용하려면 아래 연결된 사이트에 있는 엔드포인트에 연결해야 합니다.

| 행 | 용도 | 대상 | 포트 |
|-----|-------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------|--------------|---------------------------------------------|
| 1 | **필수:** 인증 및 ID | Office 365 허용 목록 사이트에서 [Office 365 인증 및 ID 섹션](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_identity)을 참조하세요. | 해당 없음 |

## <a name="general-site-usage"></a>일반 사이트 사용

Power BI의 일반적인 사용의 경우 아래 테이블 및 연결된 사이트에 있는 엔드포인트에 연결해야 합니다.

| 행 | 용도 | 대상 | 포트 |
|-----|-------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------|--------------|---------------------------------------------|
| 1 | **필수:** 백 엔드 API | *.analysis.windows.net | TCP 443 |
| 2 | **필수:** Office 365 통합 | Office 365 허용 목록에 추가 사이트에서 [Office 365 포털 및 공유 섹션](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_portal-identity)을 참조하세요. | 해당 없음 |
| 3 | **필수:** 포털 | app.powerbi.com | TCP 443 |
| 4 | **필수:** 서비스 원격 분석 | dc.services.visualstudio.com | TCP 443 |
| 5 | **선택 사항:** 정보 메시지 | dynmsg.modpim.com | TCP 443 |
| 6 | **선택 사항:** NPS 설문 조사 | nps.onyx.azure.net | TCP 443 |

## <a name="administration"></a>관리

Power BI 내에서 관리 기능을 수행하려면 아래 연결된 사이트의 엔드포인트에 연결해야 합니다.

| 행 | 용도 | 대상 | 포트 |
|-----|-------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------|--------------|---------------------------------------------|
| 1 | **필수:** 사용자 관리 및 감사 로그 보기의 경우 | Office 365 허용 목록에 추가 사이트에서 [Office 365 포털 및 공유 섹션](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_portal-identity)을 참조하세요. | 해당 없음 |

## <a name="get-data"></a>데이터 가져오기

OneDrive와 같은 특정 데이터 원본에서 데이터를 가져올 수 있으려면 아래 테이블의 엔드포인트에 연결해야 합니다.

| 행 | 용도 | 대상 | 포트 |
|-----|-------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------|--------------|---------------------------------------------|
| 1 | **필수:** AppSource(Power BI의 내부 또는 외부 앱) | appsource.microsoft.com | TCP 443 |
| 2 | **선택 사항:** 개인 OneDrive에서 파일 가져오기 | [OneDrive 사이트에 대한 필수 URL 및 포트](https://support.office.com/en-ie/article/required-urls-and-ports-for-onedrive-ce15d2cc-52ef-42cd-b738-d9c6f9b03f3a)를 참조하세요. | 해당 없음 |
| 3 | **선택 사항:** Power BI(60초 후) 자습서 비디오 | *.doubleclick.net </br> *.ggpht.com </br> *.google.com </br> *.googlevideo.com </br> *.youtube.com </br> *.ytimg.com </br> fonts.gstatic.com | TCP 443 |
| 4 | **선택 사항:** PubNub 스트리밍 데이터 원본 | [PubNub 설명서](https://support.pubnub.com/support/solutions/articles/14000043522)를 참조하세요. | 해당 없음 |

## <a name="dashboard-and-report-integration"></a>대시보드 및 보고서 통합 

Power BI는 특정 엔드포인트에 따라 대시보드 및 보고서를 지원할 수 있습니다. 아래 테이블 및 연결된 사이트에 있는 엔드포인트에 연결해야 합니다.

| 행 | 용도 | 대상 | 포트 |
|-----|-------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------|--------------|---------------------------------------------|
| 1 | **필수:** Excel 통합 | Office 365 허용 목록에 추가 사이트에서 [Office Online 섹션](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_officeonline)을 참조하세요. | 해당 없음 |

## <a name="custom-visuals"></a>사용자 지정 시각적 개체

Power BI는 특정 엔드포인트에 따라 사용자 지정 시각적 개체를 보고 액세스할 수 있습니다. 아래 테이블 및 연결된 사이트에 있는 엔드포인트에 연결해야 합니다.

| 행 | 용도 | 대상 | 포트 |
|-----|-------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------|--------------|---------------------------------------------|
| 1 | **필수:** Marketplace 인터페이스 및 파일에서 사용자 지정 시각적 개체 가져오기 | *.microsoft.com </br> *.bing.com </br> *.msecnd.net </br> *.osi.office.net </br> *.azureedge.net </br> ajax.aspnetcdn.com </br> nexus.ensighten.com </br> store.office.com | TCP 443 |
| 2 | **선택 사항:** Bing Maps | bing.com </br> platform.bing.com </br> *.dynamic.tiles.virtualearth.net </br> *.virtualearth.net | TCP 443 |
| 3 | **선택 사항:** PowerApps | PowerApps 시스템 요구 사항 사이트에서 [필수 서비스 섹션](https://docs.microsoft.com/powerapps/maker/canvas-apps/limits-and-config#required-services)을 참조하세요. | 해당 없음 |
| 4 | **선택 사항:** Visio | Office 365 허용 목록에 추가 사이트에서 [Office Online 섹션](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_officeonline)을 참조하세요. | 해당 없음 |