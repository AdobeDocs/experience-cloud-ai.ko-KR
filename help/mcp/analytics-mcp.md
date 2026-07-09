---
title: Adobe CX Enterprise MCP의 Adobe Analytics 도구
description: Adobe CX Enterprise MCP를 통해 사용할 수 있는 Adobe Analytics 도구에 대해 알아봅니다.
source-git-commit: df05761a8555950366fcaa201ce9c0fd47bb0802
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 4%

---

# Adobe CX Enterprise MCP의 Adobe Analytics 도구 {#aa-mcp}

Adobe Analytics 도구를 사용하여 보고서 세트를 탐색하고, 차원과 지표를 검색하고, 보고서를 실행하고, MCP 호환 클라이언트에서 선택한 Analytics 구성 요소를 관리할 수 있습니다. 이러한 도구는 계정에 필요한 Adobe Analytics 라이선스 및 권한이 있는 경우 통합 [Adobe CX Enterprise MCP](overview.md)를 통해 사용할 수 있습니다.

>[!AVAILABILITY]
>
>Analytics 도구는 Adobe Analytics 라이선스가 있는 고객이 사용할 수 있습니다. 액세스는 Adobe Admin Console의 **MCP 액세스** 권한에 의해 제어됩니다. 자세한 내용은 [CX 엔터프라이즈 MCP 도구 액세스](access.md)를 참조하십시오.

## 주요 기능 {#mcp-capabilities}

Adobe Analytics 도구는 MCP 클라이언트에서 분석 검색 및 보고 워크플로우를 지원합니다. 다음을 수행할 수 있습니다.

- 보고서 세트를 검색하고 보고서 세트가 구성되는 방식을 검사합니다.
- 차원, 지표, 계산된 지표, 세그먼트, 날짜 범위 및 작업 공간 프로젝트를 찾습니다.
- 차원, 지표, 날짜 범위 및 세그먼트 필터를 사용하여 등급 및 트렌드 보고서를 실행합니다.
- 세그먼트 및 날짜 범위와 같은 선택한 재사용 가능한 구성 요소를 만들고 업데이트합니다.
- 자연어를 사용하여 Adobe Analytics 데이터에서 통찰력을 생성합니다.

>[!IMPORTANT]
>
>일부 Adobe Analytics 도구는 분석 구성 요소를 만들거나 업데이트할 수 있습니다. MCP에서 시작한 모든 변경 사항을 신뢰하기 전에 검토하고 확인합니다.

## 도구 범위 {#mcp-tools}

| 영역 | 수행 가능한 작업 |
| --- | --- |
| 보고서 세트 | 계정에서 사용할 수 있는 보고서 세트를 검색하고 구성 세부 사항을 검사합니다. |
| 구성 요소 | 차원, 지표, 계산된 지표, 세그먼트 및 날짜 범위를 찾고 설명합니다. |
| 보고 | 선택한 차원, 지표, 날짜 범위 및 세그먼트 필터를 사용하여 등급 및 트렌드 보고서를 실행합니다. |
| 세그먼트 및 날짜 범위 | 제품 권한이 허용하는 재사용 가능한 세그먼트 및 날짜 범위를 만들고 업데이트합니다. |
| Workspace 프로젝트 | Analysis Workspace 프로젝트를 살펴보고 설명합니다. |

전체 최신 도구 목록은 [Adobe Analytics MCP 도구 참조](https://developer.adobe.com/analytics-mcp/docs/aa/reference){target="_blank"}를 참조하십시오.

## 프롬프트 예 {#mcp-use-cases}

| 목표 | 예제 프롬프트 |
| --- | --- |
| 보고서 세트 살펴보기 | &quot;액세스할 수 있는 보고서 세트를 나열합니다.&quot; |
| 구성 요소 찾기 | &quot;매출과 관련된 지표를 찾습니다.&quot; |
| 보고서 실행 | &quot;지난 7일 동안 페이지별 페이지 보기에 대한 등급 보고서를 실행합니다.&quot; |
| 세그먼트 검사 | &quot;`[segment name]` 세그먼트를 설명하고 해당 정의를 표시합니다.&quot; |
| 프로젝트 탐색 | &quot;획득과 관련된 내 Analysis Workspace 프로젝트를 나열합니다.&quot; |

## 제품 컨텍스트 및 권한 {#mcp-context}

귀하의 계정은 Adobe Analytics의 시스템 또는 제품 관리자가 부여한 **MCP 액세스** 권한 항목을 포함하는 Adobe Admin Console 제품 프로필에 속해 있어야 합니다.

제품 권한은 계속 적용됩니다. 사용자 계정은 쿼리하는 보고서 세트, 구성 요소, 보고서 및 프로젝트를 볼 수 있어야 하며 재사용 가능한 구성 요소 만들기 또는 업데이트와 같은 쓰기 작업에 적절한 제품 권한이 있어야 합니다.

## 추가 정보 {#mcp-more}

전체 도구 참조 및 시작 안내서는 [Adobe Analytics MCP 설명서](https://developer.adobe.com/analytics-mcp/docs/aa/){target="_blank"}를 참조하세요.