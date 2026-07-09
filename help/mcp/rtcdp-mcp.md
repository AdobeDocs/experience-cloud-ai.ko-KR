---
title: Real-Time CDP MCP(Beta)
description: MCP 서버를 사용하여 Adobe Real-Time CDP을 MCP 클라이언트에 연결하는 방법에 대해 알아봅니다.
source-git-commit: 3e8651b12f4769a819ebb49ddca9d6a158f98e6d
workflow-type: tm+mt
source-wordcount: '786'
ht-degree: 3%

---

# CX 엔터프라이즈 MCP의 Real-Time CDP 툴 {#rtcdp-mcp}

Real-Time CDP MCP 제품 도구를 사용하여 MCP 호환 클라이언트에서 대상, 대상, 소스, ID 네임스페이스 및 활성화 상태를 검사할 수 있습니다. 이러한 도구는 조직이 활성화되고 사용자 계정에 필요한 Real-Time CDP 권한이 있는 경우 통합 [CX Enterprise MCP 게이트웨이](overview.md)를 통해 사용할 수 있습니다.

>[!AVAILABILITY]
>
>Real-Time CDP 제품 도구는 Beta에 있습니다. 액세스는 초대를 통해서만 가능하며 Adobe 조직 활성화가 필요합니다. [CX 엔터프라이즈 MCP 도구 액세스](access.md)를 참조하십시오.

## 주요 기능 {#mcp-capabilities}

Real-Time CDP 도구는 읽기 전용 모니터링 및 분류 표면을 제공합니다. 다음을 수행할 수 있습니다.

* 라이프사이클 상태, 원본 및 ID 네임스페이스를 포함한 대상을 나열하고 검사합니다.
* 대상 평가 및 내보내기 작업을 검토하여 최근 실패를 식별합니다.
* 구성된 대상 계정, 대상 플로우 및 활성화 실행 기록을 검사합니다.
* 소스 커넥터, 계정, 플로우 및 수집 실행 내역을 검사합니다.
* ID 네임스페이스 및 병합 정책을 나열합니다.

>[!IMPORTANT]
>
>현재 Beta의 모든 Real-Time CDP 도구는 읽기 전용입니다. 대상, 대상, 소스 또는 데이터 흐름을 만들거나, 업데이트하거나, 활성화하거나, 삭제할 수 없습니다.

## 사용 가능한 도구 {#mcp-tools}

| 영역 | 도구 | 설명 |
| --- | --- | --- |
| 대상자 | `search_audiences` | 이름, 엔티티 유형, 라이프사이클 상태, ID 네임스페이스 또는 원본별로 대상을 나열하고 조회합니다. |
| 대상자 | `preview_audience_membership` | 대상자로 저장하기 전에 PQL 또는 SDD 세그먼트 표현식의 크기를 예측합니다. |
| 대상자 | `inspect_audience_evaluation_jobs` | 세그먼트 평가 작업 레코드를 검색하여 대상자 새로 고침 문제를 진단하거나 최근 평가 내역을 확인합니다. |
| 대상자 | `inspect_audience_export_jobs` | 대상자 내보내기 작업 레코드를 검색하여 내보내기 완료 또는 표면 실패 세부 사항을 확인합니다. |
| 대상 | `search_destination_connectors` | 플랫폼에서 사용할 수 있는 대상 커넥터 유형을 나열합니다. |
| 대상 | `search_destination_accounts` | 인증된 대상 계정을 나열합니다. |
| 대상 | `search_destination_input_connections` | 대상 흐름의 Experience Platform 측 입력을 검색합니다. |
| 대상 | `search_destination_output_connections` | 대상 경로, 파일 형식 및 게재 구성을 포함한 대상 흐름의 외부 끝점을 검색합니다. |
| 대상 | `search_destination_flows` | 상태, 매핑 및 일정을 포함하여 구성된 대상 활성화 흐름을 나열하고 검사합니다. |
| 대상 및 소스 | `inspect_flow_runs` | 상태, 시간, 레코드 카운트 및 실패 세부 정보를 포함하여 소스 및 대상 플로우 실행 기록을 검색합니다. |
| 소스 | `search_source_connectors` | 플랫폼에서 사용할 수 있는 소스 커넥터 유형을 나열합니다. |
| 소스 | `search_source_accounts` | 인증된 소스 계정을 나열합니다. |
| 소스 | `search_source_input_connections` | 소스 흐름이 계정에서 가져오는 내용을 검색합니다. |
| 소스 | `search_source_output_connections` | 소스 흐름에 대한 Experience Platform 데이터 세트 대상을 검색합니다. |
| 소스 | `search_source_flows` | 상태, 매핑 및 일정을 포함하여 구성된 소스 수집 파이프라인을 나열하고 검사합니다. |
| ID | `search_identity_namespaces` | 샌드박스의 ID 네임스페이스 정의를 나열합니다. |
| ID | `search_merge_policies` | 실시간 고객 프로필을 조합하는 방법을 제어하는 병합 정책 레코드를 나열합니다. |

## 프롬프트 예 {#mcp-use-cases}

| 목표 | 예제 프롬프트 |
| --- | --- |
| 대상자 나열 | &quot;`prod` 샌드박스에 내 대상을 나열합니다.&quot; |
| 대상자 검사 | &quot;대상 ID `abc123`에 대한 세부 정보와 라이프사이클 상태를 표시합니다.&quot; |
| 평가 문제 진단 | &quot;가장 최근의 대상자 평가 작업 및 플래그 오류를 표시합니다.&quot; |
| 내보내기 작업 확인 | &quot;최근 대상자 내보내기 작업을 나열하고 각 작업의 상태를 표시합니다.&quot; |
| 대상 크기 예상 | &quot;저장하기 전에 이 PQL 식의 크기를 예상하십시오. `homeAddress.country = 'US'`.&quot; |
| 대상 설정 검토 | &quot;대상 활성화 흐름을 나열하고 활성화 또는 비활성화 여부를 표시합니다.&quot; |
| 실패한 활성화 실행 조사 | &quot;흐름 ID `xyz789`에 대한 실행 기록을 표시하고 오류를 요약합니다.&quot; |
| 소스 수집 검토 | &quot;원본 흐름 ID `src456`에 대한 최근 실행 기록 및 플래그 오류를 표시합니다.&quot; |
| ID 구성 검사 | &quot;내 샌드박스에 어떤 ID 네임스페이스가 구성됩니까?&quot; |

## 권한 {#mcp-context}

Adobe 조직 및 샌드박스 컨텍스트는 게이트웨이 연결 수준에서 한 번 설정되고 모든 도구 제품군에 적용되므로 Real-Time CDP 도구에서 조직 또는 샌드박스를 전환하지 않습니다. 세션에 대해 해당 컨텍스트를 설정하려면 [도구 호출에 대한 제품 컨텍스트](install.md#mcp-connect-params)를 참조하십시오.

쿼리하는 Real-Time CDP 리소스를 보려면 사용자 계정에 권한이 있어야 합니다. 게이트웨이는 제품 권한을 무시하지 않습니다.

## 알려진 제한 사항 {#mcp-limitations}

| 제한 사항 | 설명 | 해결 방법 |
| --- | --- | --- |
| 읽기 전용 표면 | Real-Time CDP 도구는 검색 API만 표시합니다. 대상, 대상, 소스 또는 데이터 흐름을 만들거나, 업데이트하거나, 활성화하거나, 삭제할 수 없습니다. | 쓰기 작업에는 Real-Time CDP UI 또는 Experience Platform API를 사용하십시오. |
| 참여 또는 게재 지표 없음 | 도구는 대상 플랫폼에서 다운스트림 게재 통계, 참여 또는 전환 지표를 반환하지 않습니다. | 참여 및 전환 데이터에 대상 플랫폼의 보고, Customer Journey Analytics 도구 또는 Adobe Analytics 도구를 사용합니다. |
| 세그먼트 쿼리는 외부에서 작성해야 합니다. | `preview_audience_membership`에는 올바른 PQL 또는 SDD 식이 필요합니다. 이 도구는 쿼리를 자동으로 작성하지 않습니다. | 세그먼트 빌더 또는 세그먼테이션 서비스 API에서 표현식을 작성한 다음 프롬프트에 붙여넣습니다. |
| 연속 토큰을 통한 페이지 매김 | 목록 도구는 페이지가 매겨진 결과를 반환합니다. 매우 큰 샌드박스에서 전체 열거를 수행하려면 체인 연속 토큰이 필요합니다. | 이름, 상태, 연결 사양 또는 시간 범위와 같은 필터를 사용하여 쿼리 범위를 좁힙니다. |
| 활성화 실행 필터링은 시간만 기반 | 활성화 실행 검사는 상태 및 완료 타임스탬프별로 필터링을 지원하지만, 오류 유형이나 대상 플랫폼별로는 지원하지 않습니다. | 특정 대상 흐름에 대한 범위 실행을 먼저 `flowId`(으)로 필터링합니다. |

