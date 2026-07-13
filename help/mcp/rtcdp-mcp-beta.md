---
solution: Real-Time Customer Data Platform
title: Real-Time CDP MCP(Beta)
description: MCP 서버를 사용하여 Adobe Real-Time CDP을 MCP 클라이언트에 연결하는 방법에 대해 알아봅니다.
feature: Integrations
topic: Content Management, Artificial Intelligence
badge: label="Beta" type="Informative"
role: User, Developer
level: Beginner, Intermediate
hide: true
hidefromtoc: true
index: false
source-git-commit: baab2a961192305bd00ecaae076af277421be210
workflow-type: tm+mt
source-wordcount: '2634'
ht-degree: 0%

---

# Real-Time CDP MCP(Beta) {#rtcdp-mcp}

API 호출을 작성하거나 제품 화면을 탐색하지 않고도 Adobe Real-Time CDP MCP 통합을 사용하여 일반 언어 프롬프트를 사용하여 대상, 대상 및 활성화 상태를 쿼리할 수 있습니다. 이 통합은 Adobe Real-Time CDP 및 Adobe Real-Time CDP B2B edition 고객 모두에게 제공되며, MCP 호환 클라이언트에서 지원되는 Real-Time CDP 데이터 및 워크플로를 검사할 수 있는 대화형 방법을 제공합니다. 통합 작동 방법, 통합 기능으로 수행할 수 있는 작업 및 시작 방법을 알아보려면 이 안내서를 참조하십시오.

>[!AVAILABILITY]
>
>Real-Time CDP MCP는 Beta에 있습니다. 기능 및 설명서는 변경될 수 있습니다. Real-Time CDP MCP 서버는 사용자가 지원되는 MCP 클라이언트 및 앱 플랫폼(예: [!DNL Claude], [!DNL ChatGPT], [!DNL Claude Code], [!DNL Codex], [!DNL Cursor] 또는 [!DNL VS Code])에서 설치하고 구성하는 **원격 HTTP 전송 서버**(으)로 배포됩니다. 인증은 **브라우저 기반 로그인 흐름**&#x200B;을 통해 처리됩니다. — 클라이언트가 처음 서버에 연결되면 기본 브라우저가 열리고 Adobe 자격 증명으로 로그인하고 액세스 권한을 부여할 수 있습니다. 이 Beta 프로그램에 액세스하려면 Adobe 담당자에게 문의하십시오.

## Beta, 보안 및 법적 고지 사항 {#mcp-notices}

**Beta 설명서 알림:** 이 설명서는 Beta 기능을 다루고 있으며 최종 설명서를 구성하지 않습니다. 여기에 설명된 콘텐츠는 Beta 릴리스와 관련되며, 일반 공급 이전에 변경될 수 있습니다. Adobe은 이 설명서의 완벽성이나 정확성에 대해 어떠한 표현도 하지 않습니다.

Adobe Real-Time CDP MCP 서버(Beta)(&quot;Beta&quot;)를 사용하면 Beta이 어떠한 종류의 보증도 없이 **&quot;있는 그대로&quot; 제공된다는 것을 인정합니다**. Adobe은 Beta을 유지, 수정, 업데이트, 변경, 수정 또는 지원할 의무가 없습니다. 이러한 Beta 및/또는 동봉된 자료의 올바른 기능이나 성능에 어떤 식으로든 의존하지 말고 주의하는 것이 좋습니다. Beta은 Adobe의 기밀 정보로 간주됩니다. 귀하가 Adobe에 제공한 &quot;피드백&quot;(Beta 사용 중 발생하는 문제 또는 결함, 제안, 개선 사항 및 권장 사항을 포함하되 이에 제한되지 않는 Beta 관련 정보)은 해당 피드백에 대한 모든 권한, 제목 및 관심을 포함하여 Adobe에 할당됩니다.

>[!WARNING]
>
>MCP(Model Context Protocol)는 새로운 오픈 소스 표준이며 보안 또는 신뢰성 위험을 제시할 수 있습니다. Adobe MCP 서버 통합 및 관련 설명서는 어떠한 종류의 보증도 없이 &quot;있는 그대로&quot; 제공됩니다.
>
>MCP 클라이언트 또는 서버를 Adobe 제품에 연결하는 것은 고객이 선택한 구성입니다. 고객은 MCP 통합의 보안 및 적합성을 평가할 책임이 있습니다. Adobe은 잘못된 구성, MCP 오용, 서드파티 구현의 취약점 또는 MCP 지원 워크플로우를 통해 수행된 의도하지 않은 작업으로 인해 발생하는 문제에 대해 책임을 지지 않습니다.
>
>위험을 줄이기 위해 Adobe에서는 생산적 사용을 시작하기 전에 샌드박스 환경에서 통합을 테스트하고, 이를 확인하거나 의존하기 전에 모든 MCP에서 시작한 작업과 응답을 주의 깊게 검토하고 유효성을 검사하는 것을 권장합니다.

## 모델 컨텍스트 프로토콜이란 무엇입니까? {#mcp-overview}

마케팅, 데이터 및 고객 경험 팀은 일상적인 작업을 간소화하기 위해 Anthropic Claude, OpenAI ChatGPT, Cursor 및 Microsoft Copilot Studio와 같은 채팅 기반 애플리케이션과 개발자 도구에 점점 더 의존하고 있습니다. 이러한 응용 프로그램은 응용 프로그램이 백엔드 도구를 대형 언어 모델(LLM)에 균일한 방식으로 노출할 수 있도록 해주는 개방형 표준인 **MCP(Model Context Protocol)**&#x200B;을 지원합니다.

Real-Time CDP은 이제 모든 MCP 호환 애플리케이션 내에서 직접 대상자, 대상 및 활성화 작업을 표시하는 MCP 서버를 제공합니다. Real-Time CDP MCP 통합을 통해 서로 다른 가상 사용자가 Adobe Experience Platform REST API에 대한 쿼리를 작성하거나 여러 UI 화면을 탐색하지 않고도 동일한 세분화 및 활성화 데이터에 대해 공동 작업을 수행할 수 있습니다. 고객은 대화식으로 자신의 의도를 설명하고 LLM이 적절한 MCP 도구를 호출하도록 할 수 있다.

## 주요 기능 {#mcp-capabilities}

Real-Time CDP MCP 서버는 **읽기 전용** 모니터링 및 분류 표면입니다. 쿼리를 작성하거나 제품 화면을 탐색하지 않고 대상, 대상, 소스, ID 및 프로필 확인 전반에 걸쳐 검색 API를 AI 도우미 내의 일반 언어 답변으로 노출합니다. 어떤 데이터도 MCP 서버를 통해 생성, 수정, 삭제할 수 없다.

>[!IMPORTANT]
>
>현재 Beta의 모든 도구는 **읽기 전용**&#x200B;입니다. 대상, 대상 또는 데이터 흐름을 만들거나, 활성화하거나, 업데이트하거나, 삭제하는 등의 쓰기 작업은 지원되지 않습니다.

Beta 릴리스에는 다음 18개의 도구가 포함되어 있습니다.

| 도구 | 설명 |
| --- | --- |
| `search_audiences` | 이름, 엔티티 유형, 라이프사이클 상태, ID 네임스페이스 또는 원본별로 대상을 나열하고 조회합니다. |
| `preview_audience_membership` | 대상자로 저장하기 전에 PQL 또는 SDD 세그먼트 표현식의 크기를 예측합니다. |
| `inspect_audience_evaluation_jobs` | 세그먼트 평가 작업 레코드를 검색하여 일괄 처리 대상이 새로 고침되지 않는 이유를 진단하거나 최근 평가 내역을 확인합니다. |
| `inspect_audience_export_jobs` | 대상자 내보내기 작업 레코드를 검색하여 내보내기가 완료되었는지 확인하거나 실패 세부 정보를 표시합니다. |
| `search_destination_connectors` | 플랫폼에서 사용할 수 있는 대상 커넥터 유형을 나열합니다(예: [!DNL Amazon S3], [!DNL Google Ads], [!DNL Salesforce] CRM). |
| `search_destination_accounts` | 인증된 대상 계정 나열 — 대상 커넥터 유형의 구성된 인스턴스. |
| `search_destination_input_connections` | 대상 흐름의 Experience Platform 측 입력 검색 - 내보내는 대상 또는 데이터 세트. |
| `search_destination_output_connections` | 대상 흐름의 외부 끝점(대상 경로, 파일 형식 및 게재 구성)을 검색합니다. |
| `search_destination_flows` | 상태, 매핑 및 일정을 포함하여 구성된 대상 활성화 플로우를 나열하고 검사합니다. |
| `inspect_flow_runs` | 소스 및 대상 플로우(실행당 상태, 타이밍, 레코드 카운트 및 실패 세부 정보)에 대한 실행 내역을 검색합니다. |
| `search_source_connectors` | 플랫폼에서 사용할 수 있는 소스 커넥터 유형을 나열합니다. |
| `search_source_accounts` | 인증된 소스 계정 나열 — 소스 커넥터 유형의 구성된 인스턴스. |
| `search_source_input_connections` | 계정에서 가져오는 소스 흐름의 데이터 선택 레이어를 검색합니다. |
| `search_source_output_connections` | 수집된 데이터가 저장되는 소스 흐름의 Experience Platform 데이터 세트 대상을 검색합니다. |
| `search_source_flows` | 상태, 매핑 및 일정을 포함하여 구성된 소스 수집 파이프라인을 나열하고 검사합니다. |
| `search_identity_namespaces` | 샌드박스의 ID 네임스페이스 정의 나열 - Adobe 표준 및 사용자 정의 네임스페이스. |
| `search_merge_policies` | 프로필 조각에서 실시간 고객 프로필을 조합하는 방법을 제어하는 병합 정책 레코드를 나열합니다. |
| `search_organizations` | 인증된 사용자가 액세스할 수 있는 Adobe 조직을 나열합니다. |

## 사용 사례 {#mcp-use-cases}

Real-Time CDP MCP 서버는 **모니터링 및 분류**&#x200B;용으로 설계되었습니다. 서버는 이름이 아닌 ID로 작동하므로 일반적인 워크플로는 목록으로 시작합니다. Claude에게 사용 가능한 항목을 보여 달라고 요청하고, 원하는 항목을 선택한 다음, 반환된 ID를 사용하여 후속 질문을 합니다.

| 목표 | 예제 프롬프트 |
| --- | --- |
| **대상자 나열** | &quot;`prod` 샌드박스에 내 대상을 나열합니다.&quot; |
| **특정 대상 검사** | &quot;대상 ID `abc123`에 대한 세부 정보와 라이프사이클 상태를 표시합니다.&quot; |
| **평가 실패 진단** | &quot;가장 최근 평가 작업을 표시하고 모든 실패에 플래그를 지정합니다.&quot; |
| **내보내기 작업 확인** | &quot;최근 대상자 내보내기 작업을 나열하고 각 작업의 상태를 표시합니다.&quot; |
| **대상 크기 예상** | &quot;저장하기 전에 이 PQL 식의 크기를 예상하십시오. `homeAddress.country = 'US'`.&quot; |
| **대상 커넥터 유형 나열** | &quot;내 샌드박스에서 사용할 수 있는 대상 커넥터 유형은 무엇입니까?&quot; |
| **구성된 대상 계정 나열** | &quot;내 대상 계정 및 연결 상태를 나열합니다.&quot; |
| **대상 흐름 나열** | &quot;대상 활성화 흐름을 나열하고 활성화 또는 비활성화 여부를 표시합니다.&quot; |
| **대상 흐름 검사** | &quot;대상 흐름 ID `xyz789`에 대한 전체 구성을 표시합니다.&quot; |
| **대상 계정 상태 확인** | &quot;내 대상 계정을 나열하고 오류 상태에 있는 모든 계정을 플래그 지정합니다.&quot; |
| **최근 활성화 실행 모니터링** | &quot;지난 24시간 동안의 흐름 실행을 표시하고 모든 오류에 플래그를 지정합니다.&quot; |
| **실패한 실행 조사** | &quot;흐름 ID `xyz789`에 대한 실행 기록을 표시하고 오류를 요약합니다.&quot; |
| **소스 흐름 나열** | &quot;내 소스 수집 흐름을 나열하고 현재 상태를 표시합니다.&quot; |
| **소스 흐름 검사** | &quot;소스 흐름 ID `src456`에 대한 구성 표시 — 수집 중인 내용과 도착하는 위치&quot; |
| **수집 실행 상태 확인** | &quot;원본 흐름 ID `src456`에 대한 최근 실행 기록 및 플래그 오류를 표시합니다.&quot; |
| **ID 네임스페이스 나열** | &quot;내 샌드박스에 어떤 ID 네임스페이스가 구성됩니까?&quot; |
| **병합 정책 나열** | &quot;내 병합 정책을 나열하고 기본 병합 정책을 표시합니다.&quot; |
| **조직 ID 찾기** | &quot;액세스 권한이 있는 Adobe 조직을 나열합니다.&quot; |

## 액세스 및 지원 {#mcp-access}

>[!AVAILABILITY]
>
>Real-Time CDP MCP 서버는 Beta에 있으며 셀프 서비스 등록을 위해 열려 있지 않습니다. 액세스는 초대를 통해서만 가능하며 연결하기 전에 Adobe 조직을 명시적으로 허용 목록에추가된으로 설정해야 합니다.

액세스 권한을 요청하려면:

1. Adobe 계정 담당자(고객 성공 관리자, 기술 계정 관리자 또는 계정 담당자)에게 연락하여 Real-Time CDP MCP Beta 프로그램에 대한 관심을 표현하십시오.
2. Adobe 담당자는 제품 팀과 협력하여 자격을 평가하고 조직 ID를 활성화합니다.
3. 활성화하면 Adobe 담당자가 액세스를 확인하고 추가 온보딩 자료를 제공합니다.

>[!NOTE]
>
>명시적으로 활성화한 조직만 Real-Time CDP MCP 서버에 연결할 수 있습니다. 활성화하기 전에 연결을 시도하면 인증 오류가 발생합니다.

## 사전 요구 사항 {#mcp-prerequisites}

Real-Time CDP MCP 서버를 MCP 클라이언트에 연결하기 전에 다음 사항을 확인하십시오.

* 활성 Real-Time CDP 라이선스가 있습니다.
* Adobe 담당자가 Adobe 조직에 Beta 프로그램을 사용하도록 설정했습니다([액세스 및 사용](#mcp-access) 참조).
* 지원되는 MCP 클라이언트(예: [!DNL Claude], [!DNL ChatGPT], [!DNL Claude Code], [!DNL Codex], [!DNL Cursor] 또는 [!DNL VS Code])에 액세스할 수 있습니다.
* 조회할 조직 ID와 샌드박스의 이름이 있습니다.
* Adobe Experience Platform에서 대상자, 대상 및 흐름 서비스 엔티티를 보는 데 필요한 권한이 있습니다.

## Real-Time CDP MCP 서버 연결 {#mcp-connect}

Real-Time CDP MCP 서버 엔드포인트는 다음과 같습니다.

```
https://rtcdp-mcp.adobe.io/mcp
```

서버에서 **브라우저 기반 Adobe 로그인 흐름**&#x200B;과 함께 **원격 HTTP(스트리밍 가능 HTTP) 전송**&#x200B;을 사용합니다. 모든 클라이언트에서 설정 패턴은 동일합니다.

1. 서버 URL 추가: `https://rtcdp-mcp.adobe.io/mcp`
2. 연결을 저장하거나 활성화합니다.
3. 클라이언트가 도구를 처음 호출할 때 **브라우저 기반 Adobe 로그인**&#x200B;을 완료합니다.
4. 각 세션이 시작될 때 `imsOrgId` 및 `sandboxName`을(를) 제공하십시오.

### 일반 JSON 구성 {#mcp-connect-json}

클라우드 데스크톱(`claude_desktop_config.json`), VS 코드 또는 `mcp.json` 파일을 읽는 클라이언트와 같이 JSON 기반 MCP 서버 구성을 허용하는 클라이언트의 경우 클라이언트가 기본 원격 HTTP를 지원하는지 또는 로컬 브리지를 필요로 하는지에 따라 다음 형식 중 하나를 사용합니다.

**`mcp-remote` 브리지(로컬 브리지가 필요한 클라우드 데스크톱 및 기타 클라이언트)를 통해**

```json
{
  "mcpServers": {
    "rtcdp": {
      "command": "npx",
      "args": [
        "mcp-remote",
        "https://rtcdp-mcp.adobe.io/mcp"
      ]
    }
  }
}
```

**기본 원격 HTTP(직접 지원하는 클라이언트)**

```json
{
  "mcpServers": {
    "rtcdp": {
      "url": "https://rtcdp-mcp.adobe.io/mcp",
      "transport": "http"
    }
  }
}
```

>[!NOTE]
>
>구성에 API 키, 전달자 토큰 또는 추가 헤더가 필요하지 않습니다. 인증은 처음 사용할 때 브라우저 기반 Adobe 로그인 흐름을 통해 완전히 처리됩니다.

### UI 기반 클라이언트에 설치 {#mcp-connect-ui}

#### 클로드

`claude.ai` 및 Cloud Desktop의 경우 서버 URL `https://rtcdp-mcp.adobe.io/mcp`을(를) 사용하여 Real-Time CDP MCP 서버를 **사용자 지정 커넥터**(으)로 추가하십시오.

* **개별 계획** — 클라우드에서 **→ 커넥터 사용자 지정**&#x200B;으로 이동하고 **커넥터 추가**&#x200B;를 선택한 다음 서버 URL을 입력합니다.
* **팀 및 엔터프라이즈 플랜** — 작업 영역 **소유자** 또는 **기본 소유자**&#x200B;가 **조직 설정 → 커넥터**&#x200B;에 커넥터를 추가합니다. 추가되면 각 사용자는 자체 클라우드 설정에서 활성화합니다.

커넥터가 추가되면 대화에서 활성화하고 처음 사용 시 Adobe 브라우저 로그인을 완료합니다. Claude는 Adobe 인증 서버를 자동으로 검색합니다. 클라이언트 ID 또는 클라이언트 암호가 필요하지 않습니다.

#### ChatGPT

[!DNL ChatGPT]에서 Real-Time CDP MCP 서버를 **사용자 지정 커넥터**(으)로 추가합니다.

1. **커넥터→ 설정**(또는 플랜에 따라 **앱 및 커넥터→ 설정**)으로 이동합니다.
2. **커넥터 추가**&#x200B;를 선택하고 `https://rtcdp-mcp.adobe.io/mcp`을(를) 서버 URL로 입력하십시오.
3. 커넥터를 저장합니다. [!DNL ChatGPT] 계획에 따라 이 단계에는 **개발자 모드** 또는 작업 영역 관리자 승인이 필요할 수 있습니다.
4. 커넥터가 활성화되면 처음 사용 시 메시지가 표시되면 Adobe 브라우저 로그인을 통해 인증합니다.

#### 커서

커서에서 Real-Time CDP MCP 서버를 원격 MCP 서버로 추가합니다.

1. **MCP→ 설정**&#x200B;을 엽니다.
2. **새 서버 추가**&#x200B;를 선택하고 `https://rtcdp-mcp.adobe.io/mcp`을(를) 서버 URL로 입력하십시오.
3. 브라우저 기반 Adobe 로그인을 트리거하고 인증하려면 **연결**&#x200B;을(를) 선택하십시오.

연결되면 Cursor의 Composer 및 Agent 모드에서 Real-Time CDP 도구를 사용할 수 있습니다.

#### 기타 UI 기반 클라이언트

VS 코드 또는 원격 MCP를 지원하는 기타 데스크톱 및 웹 응용 프로그램과 같은 클라이언트의 경우 `https://rtcdp-mcp.adobe.io/mcp`을(를) 사용하여 Real-Time CDP MCP 서버를 **원격 HTTP** 서버로 추가합니다. 클라이언트가 선택적 헤더 또는 전달자 토큰을 지원하는 경우 비워 두십시오. 인증은 처음 사용할 때 브라우저 기반 Adobe 로그인 플로우를 통해 처리됩니다.

### 기술 클라이언트에 설치 {#mcp-connect-technical}

#### 클로드 코드

터미널에서 서버를 추가합니다.

```bash
claude mcp add --transport http rtcdp https://rtcdp-mcp.adobe.io/mcp
```

그런 다음 클라우드 코드를 시작하고 다음을 실행합니다.

```text
/mcp
```

`rtcdp` 서버를 선택하고 브라우저에서 Adobe 로그인 흐름을 완료합니다. `claude.ai`에 서버를 이미 추가한 경우 둘 다 동일한 계정에 로그인하면 클라우드 코드에 자동으로 표시될 수 있습니다.

#### 코덱스

터미널에서 서버를 추가합니다.

```bash
codex mcp add rtcdp --url https://rtcdp-mcp.adobe.io/mcp
```

서버 인증:

```bash
codex mcp login rtcdp
```

구성을 확인합니다.

```bash
codex mcp list
```

서버를 `~/.codex/config.toml`에 직접 추가할 수도 있습니다.

```toml
[mcp_servers.rtcdp]
url = "https://rtcdp-mcp.adobe.io/mcp"
```

### 필수 요청 매개 변수 {#mcp-connect-params}

모든 도구 호출에는 Adobe Experience Platform 테넌트에 대한 요청의 범위를 지정하는 두 개의 매개 변수가 필요합니다.

* `imsOrgId` — 다운스트림 Experience Platform API 호출의 `x-gw-ims-org-id` 헤더에 매핑된 조직 ID.
* `sandboxName` — `x-sandbox-name` 헤더에 매핑된 Experience Platform 샌드박스 이름입니다.

각 세션을 시작할 때 제공합니다. 예:

> &quot;이 세션에 조직 `1234ABCD@AdobeOrg`과(와) 샌드박스 `prod`을(를) 사용하십시오.&quot;

조직 ID를 모를 경우 AI 도우미에게 `search_organizations`에 전화하도록 요청하십시오. 그러면 Adobe 자격 증명에서 액세스할 수 있는 모든 조직이 반환됩니다.

## 알려진 제한 사항(Beta) {#mcp-limitations}

다음 제한 사항은 [!DNL Adobe Real-Time CDP] MCP 서버의 현재 Beta 릴리스에 적용됩니다.

| 제한 사항 | 설명 | 해결 방법 |
| --- | --- | --- |
| **읽기 전용 표면** | MCP 서버는 검색 API만 노출합니다. 대상, 대상 또는 데이터 흐름을 만들거나, 업데이트하거나, 활성화하거나, 삭제할 수 없습니다. | 쓰기 작업에는 Real-Time CDP UI 또는 Experience Platform REST API를 사용하십시오. |
| **참여 또는 게재 지표 없음** | MCP 서버는 대상 플랫폼에서 다운스트림 게재 통계, 참여 또는 전환 지표를 반환하지 않습니다. | 참여 및 전환 데이터에 대상 플랫폼의 자체 보고, Customer Journey Analytics MCP 또는 Adobe Analytics MCP를 사용합니다. |
| **세그먼트 쿼리는 외부에서 작성해야 합니다** | `Preview Audience Membership`은(는) 올바른 PQL 또는 SDD 식을 입력해야 합니다. MCP 서버가 쿼리를 작성하지 않습니다. | 세그먼트 빌더 UI나 세그먼테이션 서비스 API를 통해 PQL/SDD 표현식을 작성한 다음 MCP 프롬프트에 붙여넣습니다. |
| **연속 토큰을 통한 페이지 매김** | 목록 도구는 페이지가 매겨진 결과를 반환합니다. 매우 큰 샌드박스에서 전체 열거형을 사용하려면 `continuationToken` 호출을 체인 처리해야 합니다. | 전체 목록을 열거하지 않고 필터(이름, 상태, 연결 사양, 시간 범위)를 사용하여 쿼리 범위를 좁힙니다. |
| **활성화 실행 필터링은 시간을 기반으로 합니다** | `Inspect Activation Runs`은(는) 상태 및 완료 타임스탬프(epoch ms UTC)별 필터링을 지원하지만 오류 유형 또는 대상 플랫폼별로는 지원하지 않습니다. | `List Configured Destinations`에서 가져온 `flowId`을(를) 기준으로 특정 대상에 대한 범위 실행을 필터링합니다. |
| **세션 시작 시 조직 ID 필요** | 모든 도구 호출(`search_organizations` 제외)에는 명시적 매개 변수로 `imsOrgId` 및 `sandboxName`이(가) 필요합니다. 이러한 매개 변수가 제공되지 않으면 도구 호출이 실패합니다. | 각 세션이 시작될 때 AI 도우미에게 &quot;이 세션에 대해 조직 `<YOUR_ORG_ID>` 및 샌드박스 `<SANDBOX_NAME>`을(를) 사용하십시오.&quot;라고 알려 주십시오. 조직 ID를 모를 경우 먼저 `search_organizations`을(를) 호출하십시오. 자격 증명이 액세스할 수 있는 조직이 반환됩니다. |

## 자주 묻는 질문 {#mcp-faq}

+++지원되는 MCP 클라이언트는 무엇입니까?

Real-Time CDP MCP 서버는 [!DNL Claude], [!DNL ChatGPT], [!DNL Claude Code], [!DNL Codex], [!DNL Cursor] 및 [!DNL VS Code]을(를) 포함하여 원격 MCP 서버 또는 사용자 지정 커넥터를 지원하는 모든 클라이언트에서 작동합니다. 설정 플로우는 클라이언트에 따라 다릅니다. 일반적으로 UI 기반 클라이언트는 설정 또는 커넥터 패널에서 서버를 추가하는 반면, 클라우드 코드 및 코드 등의 기술 클라이언트는 명령줄 또는 구성 파일에서 추가할 수 있습니다.
+++

+++액세스 권한을 어떻게 얻습니까?

Beta 중에만 초대를 통해 액세스할 수 있습니다. 등록을 요청하려면 Adobe 계정 담당자(고객 성공 관리자, 기술 계정 관리자 또는 계정 담당자)에게 문의하십시오. Adobe 담당자는 조직을 활성화하기 위해 제품 팀과 조정합니다. 자세한 내용은 [액세스 및 사용](#mcp-access)을 참조하세요.
+++

+++인증은 어떻게 작동합니까?

인증은 **브라우저 기반 로그인**&#x200B;을 통해 처리됩니다. MCP 클라이언트가 도구를 처음 호출하면 기본 브라우저에서 Adobe 로그인 페이지가 열립니다. 클라이언트를 인증하고 권한을 부여하면 세션이 설정되고 후속 도구 호출이 재사용됩니다. 클라이언트 구성에 API 키 또는 장기 자격 증명을 저장할 필요가 없습니다.
+++

+++MCP를 통해 액세스할 수 있는 Real-Time CDP 오브젝트는 무엇입니까?

대상자, 대상 유형, 구성된 대상 계정, 대상 데이터 흐름, 소스 및 타겟 연결, 활성화 실행 기록에 액세스할 수 있습니다. 작업은 읽기 전용(API 검색)이며 쓰기 작업은 현재 릴리스에서 지원되지 않습니다.
+++

+++Real-Time CDP MCP 서버를 사용하려면 개발자 액세스 권한이 필요합니까?

아니요. MCP 서버는 마케팅 및 기술 담당자 모두를 위해 설계되었습니다. 마케터는 지원되는 모든 MCP 클라이언트에서 자연어 프롬프트를 사용하여 상호 작용할 수 있으며, 데이터 엔지니어 및 개발자는 MCP를 지원하는 개발자 도구에서 사용할 수 있습니다.
+++
