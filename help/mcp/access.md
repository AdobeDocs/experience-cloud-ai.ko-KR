---
title: CX Coworker 게이트웨이 도구 액세스
description: Adobe CX Coworker Gateway 도구를 사용하기 전에 제품 가용성, 조직 지원 및 권한을 확인하십시오.
source-git-commit: 9f654bc1f7282cad51ef54b86167dbea1757364a
workflow-type: tm+mt
source-wordcount: '556'
ht-degree: 3%

---

# CX Coworker 게이트웨이 도구 액세스 {#mcp-access}

Adobe CX Enterprise는 단일 MCP를 통해 제품 도구를 제공합니다. 액세스는 제품 도구로 평가됩니다. Adobe 조직은 관련 제품 도구에 대해 활성화되어야 하며, 사용자 계정은 도구가 노출하는 제품 데이터를 보거나 변경하는 데 필요한 제품 권한을 가져야 합니다.

>[!IMPORTANT]
>
>CX Coworker 게이트웨이 도구를 사용하려면 먼저 Adobe 조직이 활성화되어야 합니다. 조직에 아직 액세스 권한이 없는 경우 Adobe 계정 팀에 연락하여 조직에 대한 활성화를 요청하십시오.

## 액세스 요구 사항 {#mcp-requirements}


| 제품 도구 | 가용성 | 액세스 요구 사항 |
| --- | --- | --- |
| Real-Time CDP | Beta | 활성 Real-Time CDP 라이선스, Adobe 조직에 대한 Beta 지원 및 쿼리하는 대상, 대상, 소스, ID 및 활성화 리소스를 볼 수 있는 권한. |
| Experience Platform | Beta | 활성 Experience Platform 라이선스, Adobe 조직에 대한 Beta 지원 및 쿼리하는 스키마, 데이터 세트, 거버넌스, 쿼리 서비스, 감사 및 샌드박스 리소스를 볼 수 있는 권한. |
| Journey Optimizer | Beta | 활성 Journey Optimizer 라이선스, Adobe 조직에 대한 Beta 지원, 캠페인 및 채널 구성을 볼 수 있는 권한. |
| Customer Journey Analytics | 사용 가능 | Active Customer Journey Analytics 라이선스 및 Adobe Admin Console의 **MCP 액세스** 권한 항목을 포함하는 제품 프로필입니다. 제품 권한은 여전히 액세스하거나 수정할 수 있는 데이터 보기, 구성 요소, 보고서, 프로젝트 및 대상을 제어합니다. |
| Adobe Analytics | 사용 가능 | Active Adobe Analytics 라이선스 및 Adobe Admin Console의 **MCP 액세스** 권한 항목을 포함하는 제품 프로필입니다. 제품 권한은 여전히 액세스하거나 수정할 수 있는 보고서 세트, 구성 요소, 보고서, 세그먼트, 날짜 범위 및 프로젝트를 제어합니다. |
| Workfront | 미리 보기 | 활성 Workfront 라이선스 및 Workfront MCP 지원. [Workfront MCP 설명서](https://experienceleague.adobe.com/en/docs/workfront/using/basics/workfront-mcp-server/workfront-mcp-server-overview)를 참조하세요. |


>[!NOTE]
>
>MCP는 귀하의 조직과 자격 증명에 사용할 자격이 있는 도구만 표시합니다. 로그인 후 제품 도구가 누락된 경우 제품 라이선싱, 조직 지원 및 사용자 권한을 확인합니다.

## 액세스 요청 {#mcp-request}

Beta 또는 제한된 릴리스 제품 도구의 경우 Adobe 계정 담당자에게 연락하여 사용할 CX Coworker Gateway용 Adobe 제품 도구를 지정하십시오. 담당자가 제품 활성화를 조정하고 Adobe 조직이 준비되었는지 확인할 수 있습니다.

**MCP 액세스** 권한 항목을 사용하는 일반적으로 사용 가능한 제품 도구의 경우 시스템 또는 제품 관리자에게 MCP 액세스를 포함하는 제품 프로필에 계정을 추가하도록 요청하십시오.

## 제품 내 지원 {#mcp-product-enablement}

일부 제품에는 MCP 액세스 외에 제품 내 지원 또는 제품별 권한이 필요합니다. 예:

- Adobe Analytics 및 Customer Journey Analytics에는 Adobe Admin Console의 **MCP 액세스** 권한 항목이 필요합니다.
- Workfront MCP 도구는 Workfront 설정에서 활성화됩니다.
- Beta 제품 도구는 MCP를 통해 도구가 표시되기 전에 Adobe 조직 활성화가 필요합니다.

제품별 권한, 컨텍스트 요구 사항 및 제한 사항에 사용할 제품 도구의 제품 페이지를 확인하십시오.

## 설치하기 전에 {#mcp-prerequisites}

MCP 클라이언트를 연결하기 전에 다음을 확인하십시오.

- Adobe 조직에서 필요한 제품 도구를 사용할 수 있습니다.
- 사용자 계정에는 사용하려는 데이터 및 작업에 필요한 제품 권한이 있습니다.
- 지원되는 MCP 클라이언트(예: [!DNL Claude], [!DNL ChatGPT], [!DNL Cursor], [!DNL Claude Code], [!DNL Codex] 또는 [!DNL VS Code])에 액세스할 수 있습니다.
- 기업 설치의 경우, 귀하 또는 동료는 MCP 클라이언트의 조직 설정에서 커넥터 또는 사용자 정의 앱을 관리할 수 있습니다.

다음: [Adobe CX Coworker Gateway 설치](install.md).