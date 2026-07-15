---
title: Adobe CX Coworker Gateway의 Customer Journey Analytics 툴
description: Adobe CX Coworker Gateway를 통해 사용할 수 있는 Adobe Customer Journey Analytics 도구에 대해 알아봅니다.
source-git-commit: adb72f43865bee5b2b151a5a75994c5f3939c2d9
workflow-type: tm+mt
source-wordcount: '674'
ht-degree: 3%

---


# Adobe CX Coworker Gateway의 Customer Journey Analytics 툴 {#cja-mcp}

Customer Journey Analytics 제품 도구를 사용하여 데이터 보기를 탐색하고 차원 및 지표를 검색하며 보고서를 실행하고 MCP 호환 클라이언트에서 선택한 Analytics 구성 요소를 관리합니다. 이러한 도구는 계정에 필요한 Customer Journey Analytics 라이선스 및 권한이 있는 경우 [CX Coworker Gateway](overview.md)를 통해 사용할 수 있습니다.

>[!AVAILABILITY]
>
>Customer Journey Analytics 도구는 Customer Journey Analytics 라이선스를 가진 고객이 사용할 수 있습니다. 액세스는 Adobe Admin Console의 **MCP 액세스** 권한에 의해 제어됩니다. [CX Coworker 게이트웨이 도구 액세스](access.md)를 참조하십시오.

## 주요 기능 {#mcp-capabilities}

Customer Journey Analytics 도구는 MCP 클라이언트에서 관리 분석 워크플로를 지원합니다. 다음을 수행할 수 있습니다.

* 데이터 보기를 검색하고 구성 방법을 검사합니다.
* 차원, 지표, 계산된 지표, 세그먼트, 날짜 범위, 대상자 및 프로젝트를 찾습니다.
* 차원, 지표, 날짜 범위 및 세그먼트 필터를 사용하여 등급 및 트렌드 보고서를 실행합니다.
* 구성 요소 정의 및 구성 요소 사용을 검사합니다.
* 선택한 분석 구성 요소 및 작업 공간 프로젝트를 만들거나 업데이트합니다.

>[!IMPORTANT]
>
>읽기 전용 [Real-Time CDP](rtcdp-mcp.md), [Experience Platform](aep-mcp.md) 및 [Journey Optimizer](ajo-mcp.md) 제품 도구와 달리 Customer Journey Analytics 도구에는 쓰기 작업이 포함됩니다. 세그먼트, 계산된 지표, 날짜 범위, 프로젝트 및 대상을 만들고 업데이트할 수 있습니다. MCP에서 시작한 모든 변경 사항을 신뢰하기 전에 검토하고 확인합니다.

## 사용 가능한 도구 {#mcp-tools}

| 영역 | 도구 | 설명 |
| --- | --- | --- |
| 설정 및 안내서 | `describeCja` | 도구, 차원, 지표, 세그먼트, 계산된 지표 및 프로젝트 구조에 대한 참조 안내서를 반환합니다. |
| 설정 및 안내서 | `setDefaultSessionDataViewId` | 후속 도구 호출에 대한 세션 수준 기본 데이터 보기를 구성합니다. |
| 검색 | `findDimensions` | 의미 체계 검색 지원을 통해 사용 가능한 차원을 찾습니다. |
| 검색 | `findMetrics` | 계산된 지표를 제외한 표준 및 사용자 지정 지표를 검색합니다. |
| 검색 | `findCalculatedMetrics` | 사용자가 만들고 공유한 계산된 지표를 탐색합니다. |
| 검색 | `findSegments` | 현재 사용자가 액세스할 수 있는 세그먼트를 나열합니다. |
| 검색 | `findDateRanges` | 저장된 날짜 범위 구성 요소를 검색합니다. |
| 검색 | `findDataViews` | 사용 가능한 데이터 보기를 검색합니다. |
| 검색 | `findProjects` | 작업 공간 프로젝트를 찾습니다. |
| 검색 | `findAudiences` | 사용 가능한 대상 구성 요소를 나열합니다. |
| 보고 및 분석 | `runReport` | 차원, 지표, 날짜 범위 및 선택적 세그먼트 필터로 등급 보고서를 실행합니다. |
| 보고 및 분석 | `searchDimensionItems` | 분류 보고서에 필요한 차원 값을 검색합니다. |
| 구성 요소 세부 정보 | `describeDimension` | 특정 차원에 대한 세부 메타데이터를 표시합니다. |
| 구성 요소 세부 정보 | `describeMetric` | 지표 메타데이터 및 측정 세부 정보를 반환합니다. |
| 구성 요소 세부 정보 | `describeSegment` | 세그먼트의 정의 및 호환성 정보를 표시합니다. |
| 구성 요소 세부 정보 | `describeCalculatedMetric` | 사용된 공식 및 기본 지표를 표시합니다. |
| 구성 요소 세부 정보 | `describeProject` | 작업 영역 프로젝트의 구성에 대해 자세히 설명합니다. |
| 구성 요소 세부 정보 | `describeAudience` | 대상 메타데이터 및 게시 상태를 반환합니다. |
| 구성 요소 사용 | `listComponentUsage` | 사용 빈도별로 구성 요소의 등급을 지정합니다. |
| 구성 요소 사용 | `listFrequentlyUsedWith` | 는 일반적으로 함께 쌍을 이루는 구성 요소를 식별합니다. |
| 구성 요소 사용 | `listSimilarTo` | 유사한 목적을 제공하는 대체 구성 요소를 찾습니다. |
| 만들기 및 업데이트 | `upsertSegment` | 새 세그먼트를 만들거나 기존 세그먼트를 수정합니다. |
| 만들기 및 업데이트 | `upsertCalculatedMetric` | 새 계산된 지표를 만들거나 기존 계산된 지표를 수정합니다. |
| 만들기 및 업데이트 | `createDateRange` | 재사용 가능한 날짜 범위 구성 요소를 만듭니다. |
| 만들기 및 업데이트 | `upsertProject` | 새 작업 영역 프로젝트를 만들거나 기존 작업 영역 프로젝트를 수정합니다. |
| 만들기 및 업데이트 | `upsertAudience` | 새 대상 정의를 만들거나 기존 대상 정의를 수정합니다. |

## 프롬프트 예 {#mcp-use-cases}

| 목표 | 예제 프롬프트 |
| --- | --- |
| 목록 데이터 보기 | &quot;Customer Journey Analytics에서 사용할 수 있는 데이터 보기를 나열합니다.&quot; |
| 구성 요소 검색 | &quot;데이터 보기 `[data view name]`에서 매출과 관련된 지표를 찾으십시오.&quot; |
| 보고서 실행 | &quot;지난 분기의 월별 주문 트렌드 보고서를 실행합니다.&quot; |
| 지표 분류 | &quot;장치 유형별로 분류된 방문 횟수별로 상위 10개 마케팅 채널을 보여 주십시오.&quot; |
| 구성 요소 검사 | &quot;`[segment name]` 세그먼트를 설명하고 해당 정의를 표시합니다.&quot; |
| 감사 사용 | &quot;내 프로젝트에서 가장 자주 사용되는 차원은 무엇입니까?&quot; |
| 세그먼트 만들기 | &quot;지난 30일 동안 가격 페이지를 본 사용자를 위한 세그먼트를 만듭니다.&quot; |

## 제품 컨텍스트 및 권한 {#mcp-context}

귀하의 계정은 Customer Journey Analytics의 시스템 또는 제품 관리자가 부여한 **MCP 액세스** 권한 항목을 포함하는 Adobe Admin Console 제품 프로필에 속해 있어야 합니다.

제품 권한은 계속 적용됩니다. 계정은 쿼리하는 데이터 보기, 구성 요소, 프로젝트 및 대상을 볼 수 있어야 하며 세그먼트, 계산된 지표, 날짜 범위, 프로젝트 또는 대상 만들기 또는 업데이트와 같은 쓰기 작업에 적절한 제품 사용 권한이 있어야 합니다.

## 실제 시청 {#mcp-videos}

**개요**

>[!VIDEO](https://video.tv.adobe.com/v/3486321/?captions=kor&learn=on&enablevpops)

**작업 중**

>[!VIDEO](https://video.tv.adobe.com/v/3486332/?captions=kor&learn=on&enablevpops)

## 추가 정보 {#mcp-more}

전체 도구 참조 및 시작 안내서는 [Customer Journey Analytics MCP 설명서](https://developer.adobe.com/analytics-mcp/docs/cja/){target="_blank"}를 참조하세요.