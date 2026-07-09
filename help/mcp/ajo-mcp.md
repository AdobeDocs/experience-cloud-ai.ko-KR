---
title: CX 엔터프라이즈 MCP의 Adobe Journey Optimizer 툴
description: CX Enterprise MCP를 통해 사용 가능한 Adobe Journey Optimizer 툴에 대해 알아봅니다.
source-git-commit: 6c73b4d2e452a82597565d71279df2dba605a977
workflow-type: tm+mt
source-wordcount: '534'
ht-degree: 3%

---

# CX 엔터프라이즈 MCP의 Adobe Journey Optimizer 툴 {#ajo-mcp}

Adobe Journey Optimizer 제품 도구를 사용하여 MCP 호환 클라이언트로부터 캠페인 및 채널 구성을 검사합니다. 이러한 도구는 조직이 활성화되고 사용자 계정에 필요한 Journey Optimizer 권한이 있는 경우 [CX Enterprise MCP](overview.md)를 통해 사용할 수 있습니다.

>[!AVAILABILITY]
>
>Journey Optimizer 제품 도구는 Beta에 있습니다. 액세스는 초대를 통해서만 가능하며 Adobe 조직 활성화가 필요합니다. [CX 엔터프라이즈 MCP 도구 액세스](access.md)를 참조하십시오.

## 주요 기능 {#mcp-capabilities}

Journey Optimizer 도구는 캠페인 및 채널 구성 검토를 위한 읽기 전용 화면을 제공합니다. 다음을 수행할 수 있습니다.

- Journey Optimizer 캠페인을 나열하고 상태별로 필터링합니다.
- 타겟팅, 예약, 채널 및 콘텐츠 구성 메타데이터를 포함한 캠페인 세부 정보를 검색합니다.
- 이메일, SMS, 푸시 및 WhatsApp 채널에 대한 채널 구성을 나열합니다.
- 제품 화면을 탐색하지 않고 자연어로 캠페인 및 채널 설정을 검토합니다.

>[!IMPORTANT]
>
>현재 Beta의 모든 Journey Optimizer 도구는 읽기 전용입니다. 캠페인 만들기, 업데이트, 삭제, 시작, 중지 또는 게시는 지원되지 않습니다.

## 사용 가능한 도구 {#mcp-tools}

| 도구 | 설명 |
| --- | --- |
| `ajo_campaign_list` | Journey Optimizer 마케팅 캠페인을 살펴봅니다. `DRAFT`, `LIVE`, `STOPPED`, `COMPLETED` 등 상태별 필터링을 지원합니다. |
| `ajo_campaign_get` | 대상 타깃팅, 일정, 채널 및 콘텐츠 설정 메타데이터를 포함하여, ID별로 특정 캠페인에 대한 세부 정보 및 구성을 가져옵니다. |
| `ajo_channel_configuration_list`, `ajo_channel_configuration_get` | 이메일, SMS, 푸시 또는 [!DNL WhatsApp] 채널에 대한 표면 사전 설정 및 브랜딩 설정을 봅니다. |

## 프롬프트 예 {#mcp-use-cases}

| 목표 | 예제 프롬프트 |
| --- | --- |
| 캠페인 개요 | &quot;내 Journey Optimizer 캠페인 모두 표시&quot; |
| 상태 감사 | &quot;현재 어떤 캠페인이 라이브됩니까?&quot; |
| 캠페인 세부 정보 | &quot;`[campaign ID]` 캠페인에 대한 전체 세부 정보를 가져옵니다.&quot; |
| 대상자 및 타기팅 | &quot;`[campaign ID]` 캠페인에서 타깃팅된 대상은 무엇입니까?&quot; |
| 일정 및 시간 | &quot;`[campaign ID]` 캠페인은 언제 실행되도록 예약됩니까?&quot; |
| 문제 해결 | &quot;`[campaign ID]` 캠페인의 설정을 검토하고 가능한 문제에 플래그를 지정합니다.&quot; |
| 채널 구성 | &quot;어떤 이메일 채널 구성을 사용할 수 있습니까?&quot; |
| 채널 감사 | &quot;누락되었거나 불완전한 채널 구성은 무엇입니까?&quot; |

## 제품 컨텍스트 및 권한 {#mcp-context}

쿼리하는 Journey Optimizer 캠페인 및 채널 구성을 볼 수 있는 권한이 사용자 계정에 있어야 합니다. MCP는 제품 권한을 무시하지 않습니다.

조직에서 여러 샌드박스를 사용하는 경우 특정 샌드박스의 결과가 필요한 경우 프롬프트에 샌드박스 또는 환경 컨텍스트를 지정합니다.

## 알려진 제한 사항 {#mcp-limitations}

| 제한 사항 | 설명 | 해결 방법 |
| --- | --- | --- |
| 읽기 전용 표면 | Journey Optimizer 도구는 검색 작업만 표시합니다. 캠페인을 생성, 업데이트, 삭제, 시작, 중지 또는 게시할 수 없습니다. | 쓰기 작업에 Journey Optimizer UI 또는 API를 사용합니다. |
| 참여 또는 성능 지표 없음 | 도구는 노출 횟수, 클릭스루 비율, 전환 또는 게재 통계와 같은 보고 데이터를 반환하지 않습니다. | 성능 지표에 Journey Optimizer 보고, Customer Journey Analytics 도구 또는 Adobe Analytics 도구를 사용합니다. |
| 캠페인 목록 페이지 매김이 제한됨 | 캠페인 목록은 결과의 첫 페이지를 반환하며, 최대 50개의 캠페인이 알파벳순으로 정렬됩니다. 오프셋 및 제한 값은 적용되지 않습니다. | 캠페인 ID가 알려진 경우 `Get Campaign`을(를) 바로 사용합니다. 전체 탐색 및 필터링에는 Journey Optimizer UI를 사용하십시오. |
| 날짜, 채널 또는 예약별 서버측 필터링 없음 | 캠페인 목록은 상태 필터링을 지원하지만, 게시 날짜, 예약 날짜, 채널 또는 캠페인 유형 필터링은 지원하지 않습니다. | 기본 날짜 및 채널 필터링에는 Journey Optimizer UI 캠페인 목록을 사용하십시오. |
| 메시지 콘텐츠 검색을 사용할 수 없음 | 현재 도구를 통해서는 메시지 HTML, 제목 줄, 개인화 토큰 및 오퍼 콘텐츠를 사용할 수 없습니다. | Journey Optimizer UI에서 직접 메시지 콘텐츠 및 개인화를 볼 수 있습니다. |