---
title: 작업 영역에서 데이터 세트 사용 제어(미리 보기) - Power BI
description: Power BI 테넌트의 정보 흐름을 제한하는 방법을 알아봅니다.
author: maggiesMSFT
manager: kfile
ms.reviewer: chbraun
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/31/2019
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: 363bf9b107722b3993ed7ac43138c73da03f410a
ms.sourcegitcommit: 7c426a5209d4fdd1360fc3d0442d57991be1984d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/03/2019
ms.locfileid: "66461790"
---
# <a name="control-the-use-of-datasets-across-workspaces-preview"></a>작업 영역에서 데이터 세트 사용 제어(미리 보기)

작업 영역에서 데이터 세트를 사용하는 것은 조직 내에서 데이터 문화 및 데이터 민주화를 촉진하는 강력한 방법입니다. 그래도 Power BI 관리자라면 Power BI 테넌트 내의 정보 흐름을 제한하려는 경우가 있습니다. **작업 영역에서 데이터 사용** 테넌트 설정을 통해 보안 그룹별로 전체 또는 부분적으로 데이터 세트 재사용을 제한할 수 있습니다.

![Power BI 관리자 작업 영역 설정](media/service-datasets-admin-across-workspaces/power-bi-admin-workspace-settings.png)

이 설정을 해제하면 보고서 작성자에 미치는 영향은 다음과 같습니다.

- 작업 영역에서 보고서를 복사하는 단추를 사용할 수 없습니다. 
- 공유 데이터 세트를 기반으로 하는 보고서에서는 **보고서 편집** 단추를 사용할 수 없습니다.
- Power BI 서비스에서 검색 환경은 현재 작업 영역의 데이터 세트만 표시합니다.
- Power BI Desktop에서 검색 환경은 사용자가 멤버인 작업 영역의 데이터 세트만 표시합니다.
- Power BI Desktop에서 사용자가 멤버인 작업 영역 외부의 데이터 세트에 라이브 연결로 .pbix 파일을 열면 다른 데이터 세트에 연결하라는 오류 메시지가 나타납니다.

## <a name="provide-a-link-for-the-certification-process"></a>인증 프로세스에 대한 링크 제한

테넌트 관리자로서 **보증** 설정 페이지에서 **자세한 정보** 링크에 대한 URL을 제공할 수 있습니다.  이 링크는 인증 프로세스에 대한 설명서로 이동할 수 있습니다. **자세한 정보** 링크의 대상을 제공하지 않은 경우 기본적으로 [데이터 세트 인증](service-datasets-certify.md) 문서를 가리킵니다.

![데이터 세트 인증 자세히 알아보기](media/service-datasets-certify-promote/power-bi-dataset-learn-more-certification.png)

## <a name="next-steps"></a>다음 단계

- [작업 영역에서 데이터 세트 사용(미리 보기)](service-datasets-across-workspaces.md)
- 궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](http://community.powerbi.com/)
