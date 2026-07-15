---
title: Adobe CX Coworker 게이트웨이
description: Adobe CX Coworker Gateway는 Adobe CX Enterprise용 통합 MCP로, MCP 클라이언트에게 지원되는 제품 도구에 대한 단일 연결을 제공합니다.
source-git-commit: 9f654bc1f7282cad51ef54b86167dbea1757364a
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 4%

---

# Adobe CX Coworker 게이트웨이 {#mcp-overview}

Adobe CX Coworker Gateway는 Adobe CX Enterprise용 MCP(Unified Model Context Protocol)입니다. 하나의 연결로 MCP 호환 클라이언트는 조직 및 계정이 사용할 수 있는 Adobe 제품 도구에 액세스할 수 있습니다.

>[!IMPORTANT]
>
>**CX Coworker Gateway** 도구를 사용하려면 먼저 Adobe 조직을 활성화해야 합니다.
>
>조직에 아직 액세스 권한이 없는 경우 [cx-coworker-gateway-support@adobe.com](mailto:cx-coworker-gateway-support@adobe.com)에 전자 메일을 보내 조직에 대한 활성화를 요청하세요.

모든 MCP 클라이언트 설치에 CX Coworker Gateway 엔드포인트 사용:

```
https://cx-coworker-gateway.adobe.io/mcp
```

연결한 후 끝점은 Adobe 조직 및 자격 증명에 사용할 수 있는 도구를 표시합니다. 이 안내서의 제품별 페이지에서는 각 제품 툴이 수행할 수 있는 작업, 액세스할 수 있는 데이터 및 제품별 제한 사항을 설명합니다.

## 모델 컨텍스트 프로토콜이란 무엇입니까? {#mcp-what-is}

MCP(Model Context Protocol)는 AI 애플리케이션을 외부 시스템에 연결하기 위한 오픈 소스 표준입니다. [!DNL Claude], [!DNL ChatGPT], [!DNL Cursor], [!DNL Claude Code], [!DNL Codex] 및 [!DNL VS Code]과(와) 같은 MCP 호환 클라이언트는 이러한 도구를 사용하여 제품 컨텍스트를 검색하고 지원되는 작업을 실행하고 자연어로 답변을 반환할 수 있습니다.

CX Coworker Gateway 는 CX Coworker Gateway 제품 도구에 대한 관리 엔드포인트를 제공합니다. 별도의 제품 서버를 추가하는 대신 엔드포인트에 한 번 연결하고 권한이 부여된 솔루션에 표시된 제품 도구를 사용합니다.

## 사용 가능한 제품 도구 {#available-product-tools}

이 안내서에는 다음 제품 도구가 설명되어 있습니다.


| 제품 도구 | 엔드포인트를 통해 노출되는 항목 | 가용성 | 설명서 |
| ------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------ | ------------ | -------------------------------------------------------------------------------------------------------------------------------------------- |
| **Real-Time CDP** | 대상, 대상, 소스, ID 네임스페이스 및 활성화 상태(읽기 전용) | Beta | [Real-Time CDP 도구](rtcdp-mcp.md) |
| **Experience Platform** | 스키마, 데이터 세트, 데이터 거버넌스, 쿼리 서비스 및 감사 이벤트(읽기 전용) | Beta | [Experience Platform 도구](aep-mcp.md) |
| **Journey Optimizer** | 캠페인 및 채널 구성(읽기 전용) | Beta | [Journey Optimizer 도구](ajo-mcp.md) |
| **Customer Journey Analytics** | 데이터 보기, 차원, 지표, 보고서, 세그먼트, 날짜 범위, 프로젝트 및 대상(읽기 및 쓰기) | 사용 가능 | [Customer Journey Analytics 도구](cja-mcp.md) |
| **Adobe Analytics** | 보고서 세트, 차원, 지표, 보고서, 세그먼트, 날짜 범위 및 작업 영역 프로젝트 (지원되는 구성 요소의 경우 읽기 및 쓰기) | 사용 가능 | [Adobe Analytics 도구](analytics-mcp.md) |
| **Workfront** | 프로젝트, 작업 및 승인 워크플로를 위한 작업 관리 도구 | 미리 보기 | [Workfront MCP 서버](https://experienceleague.adobe.com/ko/docs/workfront/using/basics/workfront-mcp-server/workfront-mcp-server-overview) |


>[!NOTE]
>
>도구 가용성은 제품 라이선스, 조직 활성화, 제품 권한 및 인증에 사용되는 Adobe 자격 증명에 따라 다릅니다. MCP는 조직과 사용자 계정이 액세스할 수 있는 도구만 표시합니다. [CX Coworker 게이트웨이 도구 액세스](access.md)를 참조하십시오.



## 시작하기 {#mcp-get-started}

1. [CX Coworker 게이트웨이 도구 액세스](access.md)를 검토하여 제품의 가용성, 사용 여부 및 사용 권한을 확인하십시오.
2. [CX Coworker Gateway용 Adobe 설치](install.md)를 따라 MCP 클라이언트를 끝점에 연결합니다.
3. 사용하려는 각 제품 도구에 대한 제품 페이지를 검토하십시오.

