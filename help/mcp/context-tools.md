---
title: CX 엔터프라이즈 MCP의 세션 컨텍스트 툴
description: 모든 CX Enterprise MCP 툴 호출에 대한 조직, 샌드박스 및 데이터 보기 컨텍스트를 설정하는 핵심 도구에 대해 알아봅니다.
source-git-commit: 023a4c15ca787c9b110b52914fd18d0e6eecd23d
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 0%

---

# Adobe CX Enterprise MCP의 세션 컨텍스트 도구 {#mcp-core}

Adobe CX Enterprise MCP에는 다른 모든 제품 도구가 내에서 작동하는 Adobe 조직, Adobe Experience Platform 샌드박스 및 Customer Journey Analytics 데이터 보기를 설정하는 세션 컨텍스트 도구 세트가 포함되어 있습니다. 추가 라이선스 또는 활성화가 필요하지 않습니다. 이러한 도구는 [CX 엔터프라이즈 MCP 서버](overview.md)에 연결한 후 모든 인증된 사용자가 사용할 수 있습니다.

## 컨텍스트 작동 방식 {#mcp-core-how}

CX 엔터프라이즈 MCP는 모든 툴 호출을 하나의 활성 Adobe 조직에 대해 지정합니다. 그 외에도 컨텍스트 요구 사항은 제품에 따라 다릅니다.

- **Experience Platform 기반 제품** — [Real-Time CDP](rtcdp-mcp.md), [Experience Platform](aep-mcp.md) 및 [Journey Optimizer](ajo-mcp.md) 도구는 Experience Platform 샌드박스 내에서 작동합니다. `core-set_sandbox`을(를) 사용하여 세션당 한 번씩 샌드박스를 설정합니다. 세 개 모두 샌드박스를 공유합니다.
- **기타 제품** — Experience Platform에 빌드되지 않은 제품은 샌드박스 컨텍스트를 사용하지 않습니다. 예를 들어 [Customer Journey Analytics](cja-mcp.md) 도구는 데이터 보기에 대해 확인되며 [Adobe Analytics](analytics-mcp.md) 도구는 보고서 세트에 대해 확인됩니다.

세션 시작 시 컨텍스트를 한 번 설정합니다. 개별 제품 도구는 세션 중간에 조직, 샌드박스 또는 데이터 보기를 전환하지 않습니다.

## 사용 가능한 도구 {#mcp-core-tools}

| 도구 | 설명 |
| --- | --- |
| `core-list_orgs` | 인증된 사용자가 액세스할 수 있는 Adobe 조직을 나열합니다. 각 조직의 표시 이름과 `@AdobeOrg` 식별자를 반환합니다. `core-switch_org`을(를) 호출하기 전에 조직 ID를 조회하는 데 사용합니다. |
| `core-switch_org` | 세션에 대한 활성 Adobe 조직을 설정합니다. 모든 후속 도구 호출은 세션이 종료되거나 조직이 다시 전환될 때까지 이 조직에 범위가 지정됩니다. |
| `core-list_sandboxes` | 활성 조직에서 사용할 수 있는 Experience Platform 샌드박스를 나열합니다. 각 샌드박스의 이름, 제목, 유형(프로덕션 또는 개발) 및 상태를 반환합니다. `core-set_sandbox`을(를) 호출하기 전에 샌드박스 이름을 조회하는 데 사용합니다. |
| `core-set_sandbox` | 세션에 대한 활성 Experience Platform 샌드박스를 설정합니다. Real-Time CDP, Experience Platform 및 Journey Optimizer 도구는 이 샌드박스로 데이터의 범위를 지정합니다. |
| `core-list_dataviews` | 현재 컨텍스트에서 인증된 사용자가 사용할 수 있는 Customer Journey Analytics 데이터 보기를 나열합니다. 데이터 보기 ID 및 표시 이름을 반환합니다. `core-set_dataview`을(를) 호출하기 전에 데이터 보기를 조회할 때 사용합니다. |
| `core-set_dataview` | 세션에 대한 기본 Customer Journey Analytics 데이터 보기를 설정합니다. 이 설정을 지정하면, 데이터 보기가 필요한 CJA 도구(`findDimensions`, `findMetrics` 및 `runReport` 등)는 개별 도구 호출에 다른 데이터 보기가 지정되지 않는 한 이 값을 자동으로 사용합니다. |

## 일반 세션 설정 {#mcp-core-setup}

제품 도구를 호출하기 전에 세션 시작 시 컨텍스트를 설정합니다.

1. **조직** — `core-list_orgs`을(를) 호출하여 액세스 가능한 조직을 나열한 다음 대상 조직 ID를 사용하여 `core-switch_org`을(를) 나열합니다.
2. **샌드박스** — Real-Time CDP, Experience Platform 또는 Journey Optimizer 도구를 사용하려면 `core-list_sandboxes`을(를) 호출하여 사용 가능한 샌드박스를 나열한 다음 대상 샌드박스 이름으로 `core-set_sandbox`을(를) 나열합니다.
3. **데이터 보기**(CJA 전용) — Customer Journey Analytics 도구를 사용하려면 `core-list_dataviews`을(를) 호출하여 사용 가능한 데이터 보기를 나열한 다음 선택한 데이터 보기로 `core-set_dataview`을(를) 표시하십시오.

MCP 클라이언트에게 단일 자연어 요청으로 이 설정을 완료하도록 요청할 수 있습니다.

> &quot;이 세션에 조직 `1234ABCD@AdobeOrg`, 샌드박스 `prod` 및 데이터 보기 `My Company — Global`을(를) 사용하십시오.&quot;

클라이언트가 적절한 도구를 호출하고 컨텍스트가 설정되면 확인합니다.

>[!TIP]
>
>Adobe 자격 증명이 하나의 조직에만 속하는 경우 `core-list_orgs` 및 `core-switch_org`은(는) 계속 작동하지만 유효한 조직은 상관없이 동일합니다. Real-Time CDP, Experience Platform 또는 Journey Optimizer 도구를 사용하려면 `core-set_sandbox`을(를) 호출하고 Customer Journey Analytics 도구를 사용하려면 `core-set_dataview`을(를) 호출해야 합니다.

## 프롬프트 예 {#mcp-core-examples}

| 목표 | 예제 프롬프트 |
| --- | --- |
| 사용 가능한 조직 살펴보기 | &quot;액세스 권한이 있는 Adobe 조직은 무엇입니까?&quot; |
| 조직 컨텍스트 설정 | &quot;조직 `My Org (1234ABCD@AdobeOrg)`(으)로 전환합니다.&quot; |
| 사용 가능한 샌드박스 검색 | &quot;현재 조직에서 사용할 수 있는 샌드박스를 나열합니다.&quot; |
| 샌드박스 컨텍스트 설정 | &quot;이 세션에 `prod` 샌드박스를 사용하십시오.&quot; |
| 사용 가능한 데이터 보기 검색 | &quot;어떤 Customer Journey Analytics 데이터 보기에 액세스할 수 있습니까?&quot; |
| 데이터 보기 컨텍스트 설정 | &quot;`My Company — Global`을(를) 기본 데이터 보기로 설정합니다.&quot; |
| 전체 세션 설정 | &quot;조직 `1234ABCD@AdobeOrg`, 샌드박스 `prod` 및 데이터 보기 `My Company — Global`을(를) 사용하여 세션을 설정합니다.&quot; |

## 관련 페이지 {#mcp-core-related}

- [Adobe CX Enterprise MCP 설치](install.md) - 제품 컨텍스트 설정 섹션을 포함하여 MCP 클라이언트를 연결하는 방법입니다.
- [CX 엔터프라이즈 MCP 도구에 액세스](access.md) — 제품별 액세스 요구 사항입니다.