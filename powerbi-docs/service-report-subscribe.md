---
title: Power BI 서비스에서 보고서 및 대시보드 구독
description: 자신과 다른 사람이 Power BI 보고서 및 대시보드의 스냅숏을 구독하는 방법에 대해 알아보세요.
author: mihart
manager: kfile
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 06/04/2018
ms.author: mihart
LocalizationGroup: Common tasks
ms.openlocfilehash: 9436f94add8c8aff4d0378734c83891ef407955d
ms.sourcegitcommit: 7fb0b68203877ff01f29724f0d1761d023075445
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/26/2018
ms.locfileid: "39256081"
---
# <a name="subscribe-to-a-report-or-dashboard-in-power-bi-service-apppowerbicom"></a>Power BI 서비스(app.powerbi.com)에서 보고서 또는 대시보드 구독
가장 중요한 대시보드와 보고서를 최신 상태로 유지하는 것이 결코 쉬운 일은 아닙니다. 사용자 및 동료가 가장 중요한 보고서 페이지와 대시보드를 구독하면 Power BI에서는 스냅숏을 이메일로 받은 편지함에 보냅니다. Power BI에 전자 메일 수신 빈도(예: 하루에 한 번에서 일주일에 한 번)를 알려줍니다. 

메일 및 스냅숏은 Power BI 설정에 설정된 언어를 사용합니다([Power BI에 지원되는 언어 및 국가/지역](supported-languages-countries-regions.md) 참조). 언어가 정의되지 않은 경우 Power BI는 현재 브라우저의 로캘 설정에 따른 언어를 사용합니다. 언어 기본 설정을 보거나 설정하려면 기어 아이콘 ![기어 아이콘](media/service-report-subscribe/power-bi-settings-icon.png) > **설정 > 일반 > 언어**를 선택합니다. 

![언어 드롭다운](media/service-report-subscribe/power-bi-language.png)

구독은 Power BI 서비스에서만 만들 수 있습니다. 받은 이메일에는 "보고서 또는 대시보드로 이동"할 링크가 포함되어 있습니다. Power BI 앱이 설치된 모바일 장치에서 이 링크를 선택하면 앱이 시작됩니다(Power BI 웹 사이트에서 보고서 또는 대시보드를 여는 기본 동작과는 반대).


## <a name="requirements"></a>요구 사항
- 구독 **생성**은 Power BI Pro 기능이며 콘텐츠(대시보드 또는 보고서)에 대해 해당 구독을 만드는 사용 권한을 편집해야 합니다. 
- 데이터 집합을 업데이트하거나 새로 고칠 때에만 구독 이메일이 전송되므로 구독은 업데이트하거나 새로 고치지 않은 데이터 집합에서 작동하지 않습니다.

## <a name="subscribe-to-a-dashboard-or-a-report-page"></a>대시보드 또는 보고서에 대한 구독 페이지
대시보드 또는 보고서를 구독하는지와 관계 없이 프로세스는 유사합니다. 동일한 단추를 사용하면 사용자 및 다른 사용자가 Power BI 서비스 대시보드 및 보고서를 구독할 수 있습니다.
 
![구독 아이콘 선택](media/service-report-subscribe/power-bi-subscribe-orientation.png).

1. 대시보드 또는 보고서를 엽니다.
2. 상단의 메뉴 모음에서 **구독**을 선택하거나 봉투 아이콘 ![구독 아이콘](media/service-report-subscribe/power-bi-icon-envelope.png)을 선택합니다.
   
   ![구독 아이콘](media/service-report-subscribe/power-bi-subscribe-icon.png)

3. 노란색 슬라이더를 사용하여 구독을 설정하거나 해제합니다.  슬라이더를 Off에 설정하면 구독을 삭제하지 않습니다. 구독을 삭제하려면 휴지통 아이콘을 선택합니다.

4. 이메일 메시지 세부 정보를 입력합니다. 이메일이 미리 입력되어 있지만 구독에 다른 사용자를 추가할 수 있습니다. 동일한 도메인의 이메일 주소만을 추가할 수 있습니다(자세한 내용은 아래의 **고려 사항 및 문제 해결** 참조). 보고서 또는 대시보드를 [프리미엄 용량](service-premium.md)에서 호스트하는 경우 개별 이메일 주소 및 그룹 별칭을 사용하여 다른 항목을 구독할 수 있습니다. 보고서 또는 대시보드를 프리미엄 용량에서 호스트하지 않는 경우 해당하는 개별 이메일 주소를 사용하여 다른 항목을 구독할 수 있지만 마찬가지로 Power BI Pro 라이선스가 있어야 합니다.

    아래 스크린샷에서 보고서를 구독할 때 실제 보고서 *페이지*를 구독하는 것을 의미합니다.  보고서에서 여러 페이지를 구독하려면 **다른 구독 추가**를 선택하고, 다른 페이지를 선택합니다. 
      
   ![구독 창](media/service-report-subscribe/power-bi-subscribe2.png)

5. **저장 후 닫기**를 선택하여 구독을 저장합니다. 구독한 사용자는 기본 데이터 집합이 변경될 때마다 대시보드 또는 보고서 페이지의 이메일 및 스냅숏을 수신합니다. 하루에 여러 번 대시보드 및 보고서를 새로 고치더라도 처음 새로 고침 이후에만 이메일이 전달됩니다.  
   
   ![대시보드의 이메일 스냅숏](media/service-report-subscribe/power-bi-dashboard-email.jpg)
   
   > [!TIP]
   > 전자 메일을 지금 바로 보시겠습니까? 대시보드와 연결된 데이터 집합 또는 보고서와 연결된 데이터 집합 중 하나를 새로 고쳐 이메일을 트리거합니다. (데이터 집합에 대한 편집 권한이 없는 경우 이를 수행할 수 있는 권한이 있는 사람에게 요청해야 합니다.) 사용된 데이터 집합을 찾아내려면 **관련 항목 보기** 아이콘 ![관련 항목 보기 아이콘](media/service-report-subscribe/power-bi-view-related.png)을 선택하여 **관련 콘텐츠**를 연 다음, 새로 고침 아이콘 ![새로 고침 아이콘](media/service-report-subscribe/power-bi-refresh.png)을 선택합니다. 
   > 
   > 
   
   ![관련 데이터 집합](media/service-report-subscribe/power-bi-view-related-screen.png)

## <a name="how-the-email-schedule-is-determined"></a>전자 메일 일정을 확인하는 방법
다음 표에서는 전자 메일 수신 빈도를 설명합니다. 이 빈도는 대시보드 또는 보고서의 근거가 되는 데이터 집합의 연결 방법(Power BI로 가져온 DirectQuery, Live 연결 또는 OneDrive 또는 SharePoint Online의 Excel 파일) 및 사용 가능하고 선택한 구독 옵션(매일, 매주 또는 없음)에 따라 다릅니다.

|  | **DirectQuery** | **라이브 연결** | **예약된 새로 고침(가져오기)** | **OneDrive/SharePoint Online의 Excel 파일** |
| --- | --- | --- | --- | --- |
| **보고서/대시보드는 얼마나 자주 새로 고칩니까?** |15분마다 |Power BI에서 매 15분마다 검사하고 데이터 집합이 변경되면 보고서를 새로 고칩니다. |사용자가 없음, 매일 또는 매주를 선택합니다. 일일 최대 8회까지 가능합니다. 매주는 실제로 주간 일정으로 사용자가 일주일에 한 번씩 및 매일 자주 수행하는 새로 고침을 만들고 설정합니다. |매시간 한 번 |
| **사용자가 구독 전자 메일 일정에 대해 어느 정도 제어할 수 있습니까?** |옵션: 매일 또는 매주 |옵션 없음: 보고서를 새로 고치는 경우 사용자에게 전자 메일을 하루에 한 번만 보냅니다. |새로 고침 일정이 매일인 경우 옵션은 매일과 매주입니다.  새로 고침 일정은 매주인 경우 옵션은 매주뿐입니다. |옵션 없음: 데이터 집합을 업데이트할 때마다 사용자에게 전자 메일을 하루에 한 번만 보냅니다. |

## <a name="manage-your-subscriptions"></a>구독 관리
구독을 만든 사용자만이 해당 구독을 관리할 수 있습니다.  두 가지 방법을 통해 구독 관리 화면으로 이동할 수 있습니다.  첫 번째는 **이메일 구독** 대화 상자에서 **모든 구독 관리**를 선택하는 것입니다(위에서 4단계의 스크린샷 참조). 두 번째는 맨 위 메뉴 모음에서 Power BI 톱니바퀴 아이콘 ![기어 아이콘](media/service-report-subscribe/power-bi-settings-icon.png)을 선택하고 **설정**을 선택하는 것입니다.

![설정 선택](media/service-report-subscribe/power-bi-subscribe-settings.png)

표시되는 특정 구독은 현재 어떤 작업 영역이 활성화되었는가에 따라 달라집니다.  모든 작업 영역에 대해 모든 구독을 한 번에 보려면 **내 작업 영역**이 활성화되어 있는지 확인합니다. 작업 영역에 관한 도움말은 [Power BI의 작업 영역](service-create-distribute-apps.md)을 참조하세요.

![내 작업 영역에서 모든 구독 참조](media/service-report-subscribe/power-bi-subscriptions.png)

Pro 라이선스가 만료되거나, 소유자가 대시보드 또는 보고서를 삭제하거나, 구독을 만드는 데 사용된 사용자 계정이 삭제된 경우 구독이 종료됩니다.

## <a name="considerations-and-troubleshooting"></a>고려 사항 및 문제 해결
* 대시보드 이메일 구독의 경우 타일에 RLS(행 수준 보안)이 적용되면 해당 타일은 표시되지 않습니다.  보고서 이메일 구독의 경우 데이터 집합이 RLS를 사용하면 구독을 만들 수 없습니다.
* 보고서 페이지 구독은 보고서 페이지의 이름과 연결됩니다. 보고서 페이지를 구독하고 이름을 바꾸면 구독을 다시 만들어야 합니다.
* 현재 라이브 연결 데이터 집합을 사용하는 보고서/대시 보드의 이메일 구독은 자신 이외의 사용자를 구독하는 경우 지원되지 않습니다.
* 라이브 연결 데이터 집합에 대한 전자 메일 구독의 경우 데이터가 변경될 때만 전자 메일을 받습니다. 따라서 새로 고침이 발생했지만 데이터가 변경되지 않았으면 Power BI에서 전자 메일을 보내지 않습니다.
* 전자 메일 구독은 대부분의 [사용자 지정 시각적 개체](power-bi-custom-visuals.md)를 지원하지 않습니다.  한 가지 예외는 [인증](power-bi-custom-visuals-certified.md)된 사용자 지정 시각적 개체입니다.  
* 이메일 구독은 현재 R 지원 사용자 지정 시각적 개체를 지원하지 않습니다.  
* 대시보드 타일에 RLS(행 수준 보안)이 적용되면 해당 타일은 표시되지 않습니다.
* RLS(행 수준 보안)이 적용되는 보고서에 대한 다른 사용자를 구독할 수 없습니다.
* 전자 메일 구독은 보고서의 기본 필터 및 슬라이서 상태와 함께 보내집니다. 구독한 후에 수행된 기본값에 대한 변경 사항은 이메일에 표시되지 않습니다.    
* 전자 메일 구독은 서비스 기능에 대한 Power BI Desktop 실시간 연결에서 만든 보고서 페이지에서 아직 지원되지 않습니다.    
* 특히 대시보드 구독의 경우, 특정 유형의 타일은 아직 지원되지 않습니다.  여기에는 타일, 비디오 타일, 사용자 지정 웹 콘텐츠 타일의 스트리밍이 포함됩니다.     
* 테넌트 외부의 동료와 대시보드를 공유하는 경우 해당 동료를 위해 구독을 만들 수 없습니다. 따라서 사용자가 aaron@xyz.com인 경우 anyone@ABC.com와 공유할 수 있지만 아직 anyone@ABC.com을 구독할 수 없고 공유 콘텐츠를 구독할 수 없습니다.      
* 전자 메일 크기 제한으로 인해 매우 큰 이미지가 있는 대시보드 또는 보고서의 구독은 실패할 수 있습니다.    
* Power BI는 2개월 이상 방문하지 않은 대시보드 및 보고서와 연결된 데이터 집합의 경우 자동으로 새로 고침을 일시 중지합니다.  그러나 대시보드 또는 보고서에 구독을 추가하면 방문하지 않았더라도 일시 중지되지 않습니다.    
* 구독 전자 메일을 받지 못하면 UPN(사용자 계정 이름)이 전자 메일을 받을 수 있는지 확인합니다. [Power BI 팀이 이 요구 사항을 완화하기 위해 노력하고 있으므로](https://community.powerbi.com/t5/Issues/No-Mail-from-Cloud-Service/idc-p/205918#M10163) 조정된 상태로 유지해 주세요. 
* 대시보드 또는 보고서가 프리미엄 용량인 경우 동료를 한 번에 하나의 이메일 주소로 구독하는 대신 구독에 그룹 이메일 별칭을 사용할 수 있습니다. 별칭은 현재 활성 디렉터리를 기반으로 합니다. 

## <a name="next-steps"></a>다음 단계
* 궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](http://community.powerbi.com/)    
* [블로그 게시물 읽기](https://powerbi.microsoft.com/blog/introducing-dashboard-email-subscriptions-a-360-degree-view-of-your-business-in-your-inbox-every-day/)

