---
title: Power BI Q&A에서 질문하기 위한 팁과 요령
description: Power BI Q&A에서 질문하기 위한 팁과 요령
author: mihart
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 01/18/2018
ms.author: jastru
LocalizationGroup: Ask questions of your data
ms.openlocfilehash: 0165eb7161e9ba931c336300f73316d215b1c88d
ms.sourcegitcommit: fbb7924603f8915d07b5e6fc8f4d0c7f70c1a1e1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/02/2018
ms.locfileid: "34247073"
---
# <a name="tips-for-asking-questions-in-power-bi-qa"></a>Power BI Q&A에서 질문하기 위한 팁
## <a name="words-and-terminology-that-qa-recognizes"></a>Q&A에서 인식하는 단어 및 용어
이 키워드 목록은 완전하지 않습니다.  Power BI가 키워드를 인식하는지 확인하는 가장 좋은 방법은 질문 상자에 입력하여 테스트하는 것입니다.  단어 또는 용어가 회색으로 표시되는 경우 Power BI가 인식하지 않거나 현재 컨텍스트에서 인식하지 않는 것입니다.

아래 목록은 현재 시제를 사용하지만 대부분의 경우에서 모든 시제가 인식됩니다. 예를 들어 "is"는 are, was, were, will be, have, has, had, will have, has got, do, does, did를 포함합니다.  그리고 “sort”는 sorted와 sorting을 포함합니다.  또한 PowerBI는 단어의 단수 및 복수 버전을 인식하고 포함합니다. 예를 들어 Power BI는 “year" 및 “years”를 인식합니다.

> [!NOTE]
> Q&A는 [iPads, iPhones, iPod Touch 장치에서 iOS용 Microsoft Power BI 앱](mobile-apps-ios-qna.md)에서도 사용할 수 있습니다.
> 
> 

데이터 집합의 소유자인 경우 고객에 대한 Q&A 결과를 향상시키기 위해 구와 동의어를 추가합니다.

**집계**: total, sum, amount, number, quantity, count, average, most, least, fewest, largest, smallest, highest, biggest, maximum, max, greatest, lowest, littlest, minimum, min

**관사**: a, an, the

**공란 및 부울**: blank, empty, null, “non” 또는 “non-“의 접두사, empty string, empty text, true, t, false, f

**비교**: vs, versus, compared to, compared with

**접속사**: and, or, each of, with, versus, &, and, but, nor, along with, in addition to

**축약**: 질문과 대답은 거의 모든 축약을 인식합니다. 사용해 보세요.  몇 가지 예: didn’t, haven’t, he’d, he’s, isn’t, it’s, she’ll, they’d, weren’t, where’ll, who’s, won’t, wouldn’t

**날짜**: Power BI는 대부분의 날짜 용어(day, week, month, year, quarter, decade 등) 및 다른 여러 형식(아래 참조)으로 작성된 날짜를 인식합니다. Power BI는 다음 키워드 MonthName, Days 1-31, decade를 인식합니다.

예: January 3rd of 1995, January 3rd 1995, jan 03 1995, 3 Jan 1995, the 3rd of January, January 1995, 1995 January, 1995-01, 01/1995, 달의 이름

**상대 날짜**: today, right now, current time, yesterday, tomorrow, the current, next, the coming, last, previous, ago, before now, sooner than, after, later than, from, at, on, from now, after now, in the future, past, last, previous, within, in, over, N days ago, N days from now, next, once, twice

예: 지난 6일간의 주문 수입니다.

**같음(범위)**: in, equal to, =, after, is more than, in, between, before

예: 주문 해는 2012년 전입니까? 가격은 10과 20 사이와 같습니까? John의 나이는 40보다 큽니까? 200-300의 총 판매액은?

**같음(값)**: is, equal, equal to, in, of, for, within, is in, is on

예: 어떤 제품이 녹색입니까? 주문 날짜는 2012년과 같습니다. John의 나이는 40입니까? 200과 같지 않은 총 판매액은? 2016년 1월 1일의 주문 날짜입니다. 가격에서 10입니까? 색은 녹색입니까? 가격에서 10입니까?

**이름**: 데이터 집합의 열에 "이름" 구(예: EmployeeName)가 포함되어 있으면 Q&A는 해당 열의 값이 이름임을 이해하며 "robert라는 이름을 가진 직원은 누구인가요"라는 질문을 할 수 있습니다.

**대명사**: he, him, himself, his, she, herself, her, hers, it, itself, its, they, their, them, themselves, theirs, this, these, that, those

**쿼리 명령**: sorted, sort by, direction, group, group by, by, show, list, display, give me, name, just, only, arrange, rank, compare, to, with, against, alphabetically, ascending, descending, order

**범위**: greater, more, larger, above, over, >, less, smaller, fewer, below, under, <, at least, no less than, >=, at most, no more than, <=, in, between, in the range of, from, later, earlier, sooner, after, on, at, later than, after, since, starting with, starting from, ending with

**시간**: am, pm, o'clock, noon, midnight, hour, minute, second, hh:mm:ss

예: 10 pm, 10:35 pm, 10:35:15 pm, 10 oclock, noon, midnight, hour, minute, second

**상위 N개**(순서, 순위): top, bottom, highest, lowest, first, last, next, earliest, newest, oldest, latest, most recent, next

**시각적 개체 형식**: 모든 시각적 개체 형식은 Power BI에 고유합니다.  시각화 창에서 옵션인 경우 질문에 포함할 수 있습니다.  이에 대한 예외는 시각화 창에 수동으로 추가한 [사용자 지정 시각적 개체](power-bi-custom-visuals.md)입니다.

예: 가로 막대형 차트로 월별 및 총 판매액별 구역 보기

**Wh(관계, 정규화된)**: when, where, which, who, whom, how many, how much, how many times, how often, how frequently, amount, number, quantity, how long, what

## <a name="qa-helps-you-phrase-the-question"></a>Q&A를 통해 질문 구 작성
Q&A는 질문 내용이 답변에 정확하게 반영되도록 합니다. 이 작업을 위해 여러 가지 방법이 사용됩니다. 이러한 모든 방법에서 작업을 전체 또는 부분적으로 적용하거나 적용하지 않을 수 있습니다. 질문을 입력할 때 Q&A는 다음을 수행합니다.

* 자동으로 단어와 질문을 완성합니다. 인식할 수 있는 단어 자동 완성, 기본 통합 문서에 대한 일반적인 질문 및 유효한 응답을 반환한 이전에 사용된 질문을 포함하여 다양한 전략이 사용됩니다. 둘 이상의 자동 완성 옵션을 사용할 수 있는 경우 드롭다운 목록에 표시됩니다.
* 철자를 수정합니다.
* 시각화 형태로 답변의 미리 보기를 제공합니다. 질문을 입력 및 편집하면 시각화가 업데이트됩니다(Enter 키를 누를 때까지 기다리지 않음).
* 커서를 다시 질문 상자로 이동할 때 기본 데이터 집합의 대체 용어를 자동으로 추천합니다.
* 기본 데이터 집합의 데이터를 기반으로 하여 질문을 다시 작성합니다. 이렇게 하면 Q&A가 사용된 단어를 기본 데이터 집합의 동의어로 바꾸기 때문에 Q&A에서 질문을 이해하는 데 도움이 됩니다.
* 이해할 수 없는 경우 단어를 흐리게 표시합니다.

## <a name="dont-stop-now"></a>추가 기능
Q&A가 결과를 표시한 후에도 계속 대화를 진행하세요. 시각화 및 Q&A의 대화형 기능을 사용하여 더 많은 정보를 얻을 수 있습니다.

## <a name="next-steps"></a>다음 단계
[Power BI의 Q&A](power-bi-q-and-a.md)로 돌아가기  

[Power BI - 기본 개념](service-basic-concepts.md)  

궁금한 점이 더 있나요? [Power BI 커뮤니티를 이용하세요.](http://community.powerbi.com/)

