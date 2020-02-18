---
title: 판매자 대시보드를 사용하여 AppSource에 Power BI 시각적 개체 제출
description: 판매자 대시보드를 사용하여 AppSource에 Power BI 시각적 개체 제출
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.topic: conceptual
ms.subservice: powerbi-custom-visuals
ms.date: 12/03/2019
ms.openlocfilehash: 73a6a3d16ae2515af41a3232a37579e18876f38b
ms.sourcegitcommit: 8e3d53cf971853c32eff4531d2d3cdb725a199af
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "75223657"
---
# <a name="submit-a-power-bi-visual-to-appsource-using-seller-dashboard"></a>판매자 대시보드를 사용하여 AppSource에 Power BI 시각적 개체 제출

AppSource에 제출하기 전에 **pbiviz** 파일과 **pbix** 파일이 첨부된 이메일을 Power BI 팀에 보내야 합니다. 그러면 Power BI 팀이 해당 파일을 공개 공유 서버에 업로드할 수 있습니다. 그렇지 않으면 스토어에서 파일을 검색할 수 없습니다. 새 Power BI 시각적 개체 제출, 기존 Power BI 시각적 개체 업데이트 및 거부된 제출에 대한 수정 사항이 포함된 파일을 보내야 합니다.

>[!NOTE]
>[판매자 대시보드](https://docs.microsoft.com/office/dev/store/use-the-seller-dashboard-to-submit-to-the-office-store)는 단계적으로 폐지되는 중이며 [파트너 센터](https://docs.microsoft.com/partner-center/)로 대체됩니다. Power BI 시각적 개체 제출을 진행하는 도중인 경우에만 판매자 대시보드를 사용하고 새 Power BI 시각적 개체를 AppSource에 제출하는 경우 [파트너 센터를 통한 방법](office-store.md#submitting-to-appsource)을 사용하세요.

### <a name="seller-dashboard-submission-process"></a>판매자 대시보드 제출 프로세스

[Office 개발자 센터](https://dev.office.com/)에 로그인할 수 있는 유효한 Office 개발자 계정이 있어야 합니다. Office 개발자 계정은 Microsoft 계정 Live ID(예: hotmail.com 또는 outlook.com)여야 합니다.

1. [개발자 센터](https://sellerdashboard.microsoft.com/Application/Summary)로 이동합니다.

2. **새 앱 추가**를 선택합니다.

    ![앱 추가](media/office-store/powerbi-custom-visual-add-an-app.png)

3. **Power BI 사용자 지정 시각적 개체**와 **다음**을 차례로 선택합니다.

4. **앱 패키지** 아래 **+** 를 선택하고 파일 열기 대화 상자에서 Power BI 팀으로부터 받은 앱 패키지 XML 파일을 선택합니다.

    ![앱 패키지](media/office-store/powerbi-custom-visual-apppackage.png)

5. 유효한 Power BI 앱 패키지인 승인을 수신합니다.

    ![승인된 매니페스트](media/office-store/powerbi-custom-visual-manifest-approved.png)

6. **일반 정보** 세부 사항을 작성합니다.

   * ‘제출 제목:’ 개발자 센터에서 제출을 명명할 이름입니다.
   * ‘버전:’ 버전 번호가 추가 기능 앱 패키지에서 자동으로 채워집니다.
   * ‘릴리스 날짜(UTC):’ 앱을 스토어에 릴리스할 날짜를 선택합니다. 미래의 날짜를 선택하면 해당 날짜가 될 때까지 앱이 스토어에 제공되지 않습니다.
   * ‘범주:’ 첫 번째 범주는 “데이터 시각화 + BI”라고 자동 입력됩니다. 이것은 모든 Power BI 시각적 개체에서 태그가 지정되는 방식입니다. 사용자가 시각적 개체를 손쉽게 검색하도록 돕기 위해 추가 범주를 2개까지 제공할 수 있습니다.
   * *테스팅 메모:* 선택 사항, Microsoft의 테스터에 대한 지침을 제공하려는 경우 입력합니다.
   * *앱에서 암호화를 호출, 지원, 포함 또는 사용합니다.* 를 선택되지 않은 상태로 둡니다.
   * *이 추가 기능을 iPad용 Office 추가 기능 카탈로그에서 제공:* 을 선택되지 않은 상태로 둡니다.
7. **앱 로고** 아래 **+** 를 선택하여 시각적 개체의 로고를 업로드합니다. 그런 다음 파일 열기 대화 상자에서 아이콘 파일을 선택합니다. 파일은 .png, .jpg, .jpeg 또는 .gif 형식이어야 합니다. 정확히 300px(너비) x 300px(높이)여야 하고 크기는 512KB를 초과할 수 없습니다.

    ![앱 로고](media/office-store/powerbi-custom-visual-app-logo.png)

8. **지원 문서** 세부 사항을 입력합니다.

   * 지원 문서 링크
   * 개인정보처리방침 링크
   * 비디오 링크
   * 최종 사용자 사용권 계약(EULA)

       EULA 파일을 업로드해야 합니다. 자체 EULA를 사용하거나 Office 스토어 내에 있는 Power BI 시각적 개체에 대한 기본 EULA를 사용할 수 있습니다. 기본 EULA를 사용하려면 판매자 대시보드의 “최종 사용자 사용권 계약” 파일 업로드 대화 상자에 다음 URL을 붙여넣습니다. [https://visuals.azureedge.net/app-store/Power BI - Default Custom Visual EULA.pdf](https://visuals.azureedge.net/app-store/Power%20BI%20-%20Default%20Custom%20Visual%20EULA.pdf).

9. **다음**을 선택하여 **세부 정보** 페이지로 이동합니다.

10. **언어**를 선택하고 목록에서 언어를 선택합니다.

    ![언어](media/office-store/powerbi-custom-visual-language.png)

11. "설명" 세부 정보를 입력합니다.

    * ‘앱 이름(현재 언어용):’ 상점에 표시될 앱의 제목을 입력합니다.
    * 짧은 설명: 상점에 표시될 앱에 대한 최대 100자의 짧은 설명을 입력합니다. 이 설명은 로고와 함께 최상위 페이지에 표시됩니다. pbiviz 패키지의 설명을 사용할 수 있습니다.
    * 긴 설명: 앱 세부 정보 페이지를 통해 고객에게 표시될 앱에 대한 보다 자세한 설명을 입력합니다. 시각적 개체를 오픈 소스로 전환하여 커뮤니티를 통해 향상시키려면 GitHub와 같은 공용 리포지토리에 대한 링크를 여기에 제공합니다.

12. 스크린샷을 하나 이상 업로드합니다. 가능한 형식은 png, .jpg, .jpeg 또는 .gif입니다. 정확히 1366px(너비) x 768px(높이)여야 합니다. 파일 크기는 1024KB를 초과할 수 없습니다. *활용도를 높이려면, 각 스크린샷에 표시되는 주요 기능의 가치 제안을 분명히 전달하기 위한 텍스트 거품을 추가합니다.*

12. 언어를 더 추가하려면 **언어 추가**를 선택하고 10단계와 11단계를 반복합니다. 언어를 더 추가하면 사용자가 자신의 언어로 사용자 지정 시각적 개체의 세부 정보를 보는 데 도움이 됩니다. 목록에 없는 언어는 처음에 선택된 언어로 기본값이 설정됩니다.

13. 언어 추가가 완료되면 **다음**을 선택하여 **액세스 차단** 페이지로 이동합니다.

14. 특정 국가나 지역의 고객이 여러분의 앱을 사용하거나 구매하지 못하도록 하려면 해당 확인란을 선택하고 목록에서 선택합니다.

15. **다음**을 선택하여 **가격 책정** 페이지로 이동합니다.

16. 현재는 *무료* 시각적 개체만 지원되며 시각적 개체 내 추가 구매(앱에서 바로 구매)는 허용되지 않습니다. **이 앱은 무료입니다.** 를 선택합니다.

    > [!NOTE]
    > 무료가 아닌 다른 옵션을 선택하거나 제출된 시각적 개체에 앱에서 바로 구매한 콘텐츠가 있는 경우 제출이 거부됩니다.

17. 지금은 **초안으로 저장**을 선택하고 나중에 제출하거나, **승인을 위해 제출**을 선택하고 Office 스토어에 사용자 지정 시각적 개체를 제출할 수 있습니다.

## <a name="seller-dashboard-certification-submission-process"></a>판매자 대시보드 인증 제출 프로세스

판매자 대시보드에서 인증을 위해 Power BI 시각적 개체를 제출하려면 이 섹션의 지침을 따르세요. 이전에 판매자 대시보드를 사용하여 Power BI 시각적 개체를 AppSource에 제출한 경우 이 방법을 사용합니다.

1. Power BI 시각적 개체 지원 팀(pbicvsupport@microsoft.com)에 이메일을 보냅니다. 전자 메일에는 다음 정보를 포함합니다.
    * 제목: 시각적 개체 인증 요청
    * 사람이 읽을 수 있는 소스 코드가 호스팅되는 GitHub 리포지토리에 연결
    * [요구 사항 준수](power-bi-custom-visuals-certified.md#certification-requirements)
    * 코드 검토 통과

2. Microsoft Power BI 시각적 개체 팀은 Power BI 시각적 개체가 인증되어 [인증된 Power BI 시각적 개체](power-bi-custom-visuals-certified.md#certified-power-bi-visuals) 목록에 추가되거나 수정해야 하는 문제 보고서와 함께 거부되면 사용자에게 알립니다. 개발자는 Microsoft와의 통신을 열어 두고 필요한 경우 인증된 시각적 개체를 업데이트하는 것을 담당합니다.

## <a name="tracking-submission-status-and-usage"></a>제출 상태 및 사용 현황 추적

[유효성 검사 정책](https://dev.office.com/officestore/docs/validation-policies#13-power-bi-custom-visuals)을 검토할 수 있습니다.

제출 후에 [앱 대시보드](https://sellerdashboard.microsoft.com/Application/Summary/)에서 제출 상태를 볼 수 있습니다.

## <a name="certify-your-visual"></a>시각적 개체 인증

시각적 개체를 만든 후 원할 경우 시각적 개체를 [인증](../developer/power-bi-custom-visuals-certified.md)받을 수 있습니다.

## <a name="next-steps"></a>다음 단계

[Power BI 사용자 지정 시각적 개체 개발](visuals/custom-visual-develop-tutorial.md)  
[Power BI의 시각화](../visuals/power-bi-report-visualizations.md)  
[Power BI의 사용자 지정 시각화](../developer/power-bi-custom-visuals.md)  
[Power BI 시각적 개체 인증받기](../developer/power-bi-custom-visuals-certified.md)

궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](https://community.powerbi.com/)
