---
title: Adobe CX Enterprise MCP 설치
description: MCP 호환 클라이언트를 Adobe CX 엔터프라이즈 MCP에 연결하는 방법에 대해 알아봅니다.
source-git-commit: 6c73b4d2e452a82597565d71279df2dba605a977
workflow-type: tm+mt
source-wordcount: '995'
ht-degree: 0%

---

# Adobe CX Enterprise MCP 설치 {#mcp-install}

MCP 호환 클라이언트를 Adobe CX Enterprise에 연결하는 방법은 이 안내서를 참조하십시오. CX Enterprise 는 문서화된 모든 제품 툴에 대해 하나의 엔드포인트를 사용합니다.

```
https://cx-enterprise.adobe.io/mcp
```

설치하기 전에 조직 및 사용자 계정이 필요한 제품 도구에 액세스할 수 있는지 확인하십시오. [CX 엔터프라이즈 MCP 도구 액세스](access.md)를 참조하십시오.

## 설치 작동 방식 {#mcp-install-how}

CX 엔터프라이즈 MCP 는 브라우저 기반 Adobe 로그인 흐름과 함께 원격 HTTP 전송을 사용합니다. 지원되는 모든 클라이언트에서는 설정 패턴이 동일합니다.

1. 끝점 URL `https://cx-enterprise.adobe.io/mcp`을(를) 추가합니다.
2. 연결을 저장하거나 활성화합니다.
3. 클라이언트가 도구를 처음 호출할 때 브라우저 기반 Adobe 로그인을 완료합니다.
4. 도구에서 필요로 하는 경우 세션에 대한 제품 컨텍스트(모든 제품에 대한 조직, Experience Platform 기반 도구에 대한 샌드박스 및 Customer Journey Analytics에 대한 데이터 보기)를 설정합니다. 도구 호출에 대한 [제품 컨텍스트](#mcp-connect-params)를 참조하세요.

>[!NOTE]
>
>MCP 클라이언트 구성에는 API 키, 전달자 토큰, 클라이언트 암호 또는 추가 헤더가 필요하지 않습니다. 인증은 처음 사용할 때 Adobe 로그인 흐름을 통해 처리됩니다.

## 엔터프라이즈 설치(관리자 관리) {#mcp-install-enterprise}

대부분의 팀 및 엔터프라이즈 MCP 클라이언트 플랜에서는 관리자가 조직에 대한 사용자 정의 커넥터를 추가해야 합니다. 이러한 환경에서 설치에는 두 단계가 있습니다.

1. 관리자가 조직에 대해 CX 엔터프라이즈 엔드포인트를 한 번 추가합니다.
2. 각 사용자는 커넥터를 활성화하고 자체 Adobe 자격 증명으로 로그인합니다.

### 1단계: 관리자가 엔드포인트를 추가합니다. {#mcp-install-enterprise-admin}

관리자는 `https://cx-enterprise.adobe.io/mcp`을(를) 클라이언트의 조직 설정에서 사용자 지정 커넥터 또는 원격 MCP 서버로 추가합니다. 정확한 위치는 클라이언트에 따라 다릅니다.

#### 클라우드 팀 및 엔터프라이즈 {#mcp-install-enterprise-claude}

[!DNL Claude] 팀 및 엔터프라이즈 계획에서 조직 수준 커넥터는 작업 영역 **소유자** 또는 **기본 소유자**&#x200B;에 의해 관리됩니다.

1. **소유자** 또는 **기본 소유자**(으)로 [!DNL Claude]에 로그인합니다.
2. **설정** > **관리** > **커넥터**(으)로 이동합니다. 일부 플랜에서는 **조직 설정** > **커넥터**&#x200B;로 표시됩니다.
3. **사용자 지정 커넥터 추가**&#x200B;를 선택합니다.
4. `https://cx-enterprise.adobe.io/mcp`을(를) 서버 URL로 입력하고 &quot;Adobe for CX Enterprise&quot;와 같이 인식할 수 있는 이름을 사용합니다.
5. 커넥터를 저장합니다.

#### ChatGPT 팀 및 엔터프라이즈 {#mcp-install-enterprise-chatgpt}

[!DNL ChatGPT] Team 및 Enterprise 작업 영역에서 작업 영역 관리자가 커넥터를 추가합니다.

1. 작업 영역 관리자로 [!DNL ChatGPT]에 로그인합니다.
2. **설정** > **커넥터**(으)로 이동합니다. 일부 플랜에서는 **설정** > **앱 및 커넥터**&#x200B;로 표시됩니다.
3. **커넥터 추가**&#x200B;를 선택합니다.
4. 서버 URL로 `https://cx-enterprise.adobe.io/mcp`을(를) 입력하십시오.
5. 커넥터를 저장합니다. 작업 영역 구성에 따라 이 단계에는 개발자 모드를 활성화하거나 작업 영역 수준의 승인을 부여해야 할 수 있습니다.

#### 기타 조직 관리 클라이언트 {#mcp-install-enterprise-other}

조직 관리 원격 커넥터를 지원하는 다른 클라이언트의 경우 `https://cx-enterprise.adobe.io/mcp`을(를) 사용하여 CX Enterprise를 원격 HTTP MCP 서버로 추가합니다. 클라이언트가 자리 표시자 값을 필요로 하지 않는 한 선택적 헤더, 전달자 토큰 필드, 클라이언트 ID 필드 및 클라이언트 암호 필드를 비워 둡니다.

### 2단계: 사용자가 커넥터 활성화 {#mcp-install-enterprise-user}

관리자가 CX Enterprise 를 추가한 후 각 사용자는 자신의 계정에 대해 CX Enterprise 를 활성화합니다.

1. 클라이언트에서 개인 커넥터, 앱 또는 MCP 설정을 엽니다.
2. CX 엔터프라이즈 커넥터를 찾아 활성화합니다.
3. 대화를 시작하고 Adobe 도구 중 하나를 호출한 다음 메시지가 표시되면 브라우저 기반 Adobe 로그인을 완료합니다.
4. 도구에서 필요로 하는 경우 세션에 대한 제품 컨텍스트(모든 제품에 대한 조직, Experience Platform 기반 도구에 대한 샌드박스 및 Customer Journey Analytics에 대한 데이터 보기)를 설정합니다. 도구 호출에 대한 [제품 컨텍스트](#mcp-connect-params)를 참조하세요.

관리자가 조직에 대한 커넥터를 이미 추가한 경우 사용자가 URL을 직접 입력할 필요가 없습니다.

## 개별 설치(셀프서비스) {#mcp-install-individual}

개별 계획, 로컬로 구성된 개발자 클라이언트 또는 구성원이 자체 커넥터를 추가할 수 있도록 하는 조직을 사용하는 경우 자체 클라이언트 설정에서 직접 엔드포인트를 추가합니다.

### 클로드 개인 {#mcp-install-individual-claude}

개별 플랜의 `claude.ai` 및 [!DNL Claude] 데스크톱의 경우:

1. **설정** > **커넥터**&#x200B;를 엽니다.
2. **사용자 지정 커넥터 추가**&#x200B;를 선택합니다.
3. 서버 URL로 `https://cx-enterprise.adobe.io/mcp`을(를) 입력하십시오.
4. 커넥터를 저장하고 활성화한 다음 처음 사용할 때 Adobe 로그인 흐름을 완료합니다.

### ChatGPT 개인 {#mcp-install-individual-chatgpt}

1. **설정** > **커넥터**&#x200B;를 엽니다. 일부 플랜에서는 **설정** > **앱 및 커넥터**&#x200B;로 표시됩니다.
2. **커넥터 추가**&#x200B;를 선택합니다.
3. 서버 URL로 `https://cx-enterprise.adobe.io/mcp`을(를) 입력하십시오.
4. 커넥터를 저장하고 활성화한 다음 처음 사용할 때 Adobe 로그인 흐름을 완료합니다.

### 커서 {#mcp-install-individual-cursor}

1. **설정** > **MCP**&#x200B;을 엽니다.
2. **새 서버 추가**&#x200B;를 선택합니다.
3. 서버 URL로 `https://cx-enterprise.adobe.io/mcp`을(를) 입력하십시오.
4. **연결**&#x200B;을 선택하고 Adobe 로그인 흐름을 완료합니다.

연결 후 Cursor&#39;s Composer 및 Agent 모드에서 CX Enterprise용 Adobe 툴이라는 제목이 제공됩니다.

### 클로드 코드 {#mcp-install-individual-claude-code}

터미널에서 끝점을 추가합니다.

```bash
claude mcp add --transport http cx-enterprise https://cx-enterprise.adobe.io/mcp
```

그런 다음 [!DNL Claude Code]을(를) 시작하고 다음을 실행합니다.

```text
/mcp
```

`cx-enterprise` 서버를 선택하고 브라우저에서 Adobe 로그인 흐름을 완료합니다.

### 코덱스 {#mcp-install-individual-codex}

터미널에서 끝점을 추가합니다.

```bash
codex mcp add cx-enterprise --url https://cx-enterprise.adobe.io/mcp
```

인증:

```bash
codex mcp login cx-enterprise
```

구성을 확인합니다.

```bash
codex mcp list
```

끝점을 `~/.codex/config.toml`에 바로 추가할 수도 있습니다.

```toml
[mcp_servers.cx-enterprise]
url = "https://cx-enterprise.adobe.io/mcp"
```

### 일반 JSON 구성 {#mcp-install-individual-json}

JSON 기반 MCP 서버 구성을 허용하는 클라이언트의 경우, 클라이언트가 기본 원격 HTTP를 지원하는지 또는 로컬 브리지를 필요로 하는지에 따라 다음 형식 중 하나를 사용합니다.

**브리지 `mcp-remote`을(를) 통해**

```json
{
  "mcpServers": {
    "cx-enterprise": {
      "command": "npx",
      "args": [
        "mcp-remote",
        "https://cx-enterprise.adobe.io/mcp"
      ]
    }
  }
}
```

**기본 원격 HTTP**

```json
{
  "mcpServers": {
    "cx-enterprise": {
      "url": "https://cx-enterprise.adobe.io/mcp",
      "transport": "http"
    }
  }
}
```

### 기타 클라이언트 {#mcp-install-individual-other}

원격 MCP를 지원하는 다른 데스크톱 또는 웹 클라이언트의 경우 `https://cx-enterprise.adobe.io/mcp`을(를) 사용하여 CX Enterprise용 Adobe을 원격 HTTP 서버로 추가합니다. 클라이언트가 자리 표시자 값을 필요로 하지 않는 한 선택적 헤더, 전달자 토큰 필드, 클라이언트 ID 필드 및 클라이언트 암호 필드를 비워 둡니다.

## 도구 호출에 대한 제품 컨텍스트 {#mcp-connect-params}

MCP는 모든 도구 호출의 범위를 활성 Adobe 조직 하나로 지정합니다. 그 외에도 컨텍스트 요구 사항은 제품에 따라 다릅니다.

- **Experience Platform 기반 제품** — Real-Time CDP, Experience Platform 및 Journey Optimizer 도구는 Experience Platform 샌드박스 내에서 작동합니다. 세션당 한 번 샌드박스를 설정합니다. 세 개 모두 샌드박스를 공유합니다.
- **기타 제품** — Experience Platform에 빌드되지 않은 제품은 샌드박스 컨텍스트를 사용하지 않습니다. Adobe Analytics, Customer Journey Analytics, Workfront, Marketo 및 Target 도구는 자체 제품 리소스(예: Customer Journey Analytics의 데이터 보기 및 Adobe Analytics의 보고서 세트)에 대해 해결합니다.

세션 시작 시 컨텍스트를 한 번 설정합니다. 개별 제품 도구는 세션 중간에 조직, 샌드박스 또는 데이터 보기를 전환하지 않습니다. 조직, 샌드박스 및 데이터 보기 컨텍스트를 설정하는 도구는 [세션 컨텍스트 도구](context-tools.md)를 참조하십시오.

예:

> &quot;이 세션에 조직 `1234ABCD@AdobeOrg`, 샌드박스 `prod` 및 데이터 보기 `My Company — Global`을(를) 사용하십시오.&quot;

필요한 값을 모를 경우 MCP 클라이언트에 요청하여 Adobe 자격 증명에 사용할 수 있는 조직, 샌드박스 또는 데이터 보기를 나열합니다.