---
title: Experience Cloud 애플리케이션의 AI
description: Experience Cloud 애플리케이션이 생성형 AI(GenAI), AI 어시스턴트 및 에이전틱 AI를 어떻게 사용하는지 알아봅니다.
TQID: https://experienceleague.adobe.com/heALjEZbowNaygG24oOM2HSlHa9oYVI5ViUNZDr19Ds
product_v2: id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: f8a45b24-4be7-4f1b-909b-60d06b483a20id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: c1579802-ddd4-4214-8a91-97b2066abe11id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: d095671a-1355-40aa-8b5f-06c33c68080bid: e1e0219c-f879-479f-8427-888ed2a6e9c2id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: dd7883d8eccab3b0f006d55a850248e1c347d7e7
workflow-type: tm+mt
source-wordcount: 846
ht-degree: 17%

---

# Experience Cloud의 AI

Adobe Experience Cloud 애플리케이션 전반에 걸친 AI 기능에 대한 포괄적인 안내서를 시작합니다. 이 설명서에서는 생성형 AI, AI Assistant 및 Adobe 에이전트를 Experience Cloud 워크플로에 통합하여 생산성을 가속화하고 의사 결정을 향상시키는 방법을 다룹니다.

## 이 안내서에 포함된 사항

### AI 어시스턴트

[AI Assistant](./ai-assistant/ai-assistant-ui.md)는 생산성을 높이고 Adobe Experience Platform 기반 응용 프로그램에서 작업을 재정의하는 지능형 대화식 생성 AI 도구입니다. 사용자는 자연어 프롬프트를 통해 제품 지식을 얻고 문제를 해결하며 운영 통찰력을 찾을 수 있습니다. AI Assistant를 사용하여 Adobe Experience Platform 에이전트 및 기타 AI 기능에 액세스할 수도 있습니다.

**주요 기능:**

- **대화 인터페이스**: 전체 화면과 레일 보기 인터페이스 중에서 워크플로 기본 설정에 맞게 선택할 수 있습니다.
- **검색 프롬프트**: AI Assistant는 학습, 분석 및 최적화와 같은 범주별로 구성된 사전 구성된 프롬프트를 제공합니다.
- **컨텍스트 설정**: 필요에 맞는 응답을 받도록 응용 프로그램, 샌드박스 및 데이터 보기 설정을 구성할 수 있습니다.
- **데이터 시각화**: 이 도구는 대화형 차트 및 그래프를 제공하여 데이터를 통해 통찰력을 얻을 수 있도록 합니다.
- **응답 확인**: 모든 응답에는 원본 인용, AI 추리에 대한 설명 및 피드백을 제공하기 위한 메커니즘이 포함됩니다.


### Agent Orchestrator

[Adobe Experience Platform Agent Orchestrator](./agents/agent-orchestrator.md)은(는) Adobe Experience Platform의 새로운 에이전트 계층입니다. 플랫폼의 풍부한 데이터 및 고객 지식을 활용하도록 설계된 Experience Platform Agent Orchestrator는 목적에 맞게 제작된 전문 Adobe Experience Platform 에이전트의 인텔리전스 및 논리를 강화하여, 사람의 감독 하에 복잡한 의사 결정 및 문제 해결 작업을 빠르고 대규모로 실행할 수 있도록 지원합니다. AI 어시스턴트와 같은 대화형 인터페이스에서 자연어를 통해 질문하거나 도움을 요청하면 Agent Orchestrator가 자동으로 전문 에이전트를 호출하여 정확한 답변을 얻을 수 있습니다. Agent Orchestrator는 대화 기록을 기억하여, 컨텍스트를 반복하지 않고도 이전 질문을 기반으로 자연스럽게 질문을 생성할 수 있게 하고 여러 에이전트의 인사이트를 결합하여 명확하고 통합된 응답을 제공합니다.

**핵심 구성 요소:**

- **추론 엔진**: 단계별 계획을 만들고 필요에 따라 접근 방식을 조정합니다
- **전문 에이전트**: 특정 작업 및 도메인용 특별히 빌드된 에이전트
- **기술 자료**: 비즈니스 인텔리전스 및 문서에 대한 보안 액세스

### 전문 에이전트

#### Audience 에이전트

Audience Agent은 다음을 포함하여 대상에 대한 통찰력을 제공합니다.

- 중요한 대상자 크기 변경 감지
- 중복 대상을 식별합니다.
- 대상 인벤토리를 살펴봅니다.
- 대상 크기를 검색하는 중입니다.

자세한 내용은 [Audience Agent 설명서](./agents/audience.md)를 참조하세요.

#### Data Insights Agent

Available in Customer Journey Analytics, the Data Insights Agent:

- Answers questions about your data using natural language.
- Builds relevant visualizations in Analysis Workspace.
- Uses components from your dataview and actual data.

#### Journey Analyze Agent

The Journey Analyze Agent enables the Adobe Journey Optimizer users to:

- Analyze, and optimize journeys using natural language.
- Detect and resolve schedule or audience conflicts.
- Analyze performance and drop-off points.

Read the [Journey Agent documentation](./agents/ajo-agent.md) for more information.

#### 제품 지원 에이전트

Use the Product Support Agent for self-serve debugging and troubleshooting:

- Troubleshoot Adobe Experience Platform features without leaving workflows.
- Create support tickets with context from AI Assistant interactions.
- Check ticket updates through AI Assistant.

Read the [Product Support Agent documentation](./agents/product-support.md) for more information.

<!--
#### Adobe Marketing Agent for [!DNL Microsoft 365 Copilot]

Use the Adobe Marketing Agent for [!DNL Microsoft 365 Copilot] to retrieve marketing insights from Experience Platform in [!DNL Microsoft 365] apps like [!DNL Teams], [!DNL Word], [!DNL Powerpoint], and [!DNL Excel]. With this agent, you can:

- Make faster, data-driven marketing decisions.
- Reduce time spent switching between tools.
- Simplify access to audience and journey insights across teams.

Read the [Adobe Marketing Agent documentation](./agents/ama-ms.md) for more information.
-->

## 시작

### Access requirements

To use AI Assistant and Experience Platform Agents, your Adobe Admin needs to set up the appropriate permissions:

- To use AI Assistant within Real-Time CDP and Adobe Journey Optimizer, you need the &quot;Enable AI Assistant&quot; permission, as well as the &quot;View Operational Insights&quot; permission to access operational questions.
- Access to AI Assistant in Customer Journey Analytics is managed through Customer Journey Analytics Access Control, which allows you to ask both product knowledge and data insights questions.
- For Adobe Experience Manager, you can access AI Assistant through permissions set in the Adobe Admin Console.

### 개인정보보호 및 보안

AI Assistant is built with privacy, security, and governance at the forefront:

- No personal data is used for training.
- All existing access control policies are honored.
- HIPAA-ready when used with Adobe Experience Platform Healthcare Shield.
- 30-day retention policy for interaction logs.
- 샌드박스별 데이터 격리.

## 모범 사례

AI Assistant 경험을 최대한 활용하려면 다음 모범 사례를 따르십시오.

- AI Assistant에서 타깃팅되고 관련 있는 통찰력을 얻으려면 프롬프트에 **구체적으로**&#x200B;하십시오.
- AI Assistant에서 제공한 소스 인용문과 추론 설명을 검토하여 **응답을 확인**&#x200B;합니다.
- **컨텍스트 설정을 사용**&#x200B;하여 가장 관련성이 높은 데이터 원본이 질문에 사용되었는지 확인하세요.
- **피드백을 제공**&#x200B;하여 시간이 지남에 따라 AI Assistant의 성능과 정확성을 개선하는 데 도움이 됩니다.
- **여러 에이전트의 통찰력을 결합**&#x200B;하여 보다 포괄적이고 종합적인 분석을 수행할 수 있습니다.

## 법적 고려 사항

AI Assistant 사용 시 주요 법적, 실무적 고려 사항을 숙지하는 것이 중요하다. 현재 AI 어시스턴트는 영어로만 응답이 가능하다. 언어 모델이 때때로 실수를 할 수 있으므로 항상 제공된 정보를 확인하도록 주의하십시오. 응답에 포함된 추론 단계 및 설명을 활용하여 받은 답을 보다 잘 이해할 수 있다. 문제가 발생하거나 정확하지 않은 경우 시간이 지남에 따라 AI Assistant를 개선할 수 있도록 피드백을 제출하십시오.
