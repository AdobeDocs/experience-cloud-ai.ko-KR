---
title: Experience Cloud 애플리케이션의 AI
description: Experience Cloud 애플리케이션이 생성형 AI(GenAI), AI 어시스턴트 및 에이전틱 AI를 어떻게 사용하는지 알아봅니다.
source-git-commit: 8c05562121071874002afd6d248f16186616da55
workflow-type: tm+mt
source-wordcount: '830'
ht-degree: 13%

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

[Adobe Experience Platform Agent Orchestrator](./agents/agent-orchestrator.md)은(는) Adobe Experience Platform의 새로운 에이전트 계층입니다. 플랫폼의 풍부한 데이터 및 고객 지식을 활용하도록 설계된 Experience Platform Agent Orchestrator는 목적에 맞게 제작된 전문 Adobe Experience Platform 에이전트의 인텔리전스 및 논리를 강화하여, 사람의 감독 하에 복잡한 의사 결정 및 문제 해결 작업을 빠르고 대규모로 실행할 수 있도록 지원합니다. AI 어시스턴트와 같은 대화형 인터페이스에서 자연어를 통해 질문하거나 도움을 요청하면 Agent Orchestrator가 자동으로 전문 에이전트를 호출하여 정확한 답변을 얻을 수 있습니다. Agent Orchestrator은 대화 기록을 기억하여, 맥락을 반복하지 않고 자연스럽게 이전 질문을 기반으로 할 수 있으며, 여러 에이전트의 통찰력을 결합하여 명확하고 통합된 응답을 제공합니다.

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

Customer Journey Analytics, Data Insights Agent에서 사용할 수 있습니다.

- 자연어를 사용하여 데이터에 대한 질문에 답변합니다.
- Analysis Workspace에서 관련 시각화를 구축합니다.
- 데이터 보기 및 실제 데이터의 구성 요소를 사용합니다.

#### 여정 분석 에이전트

여정 분석 에이전트를 사용하면 Adobe Journey Optimizer 사용자는 다음과 같은 작업을 수행할 수 있습니다.

- 자연어를 사용하여 여정을 분석하고 최적화합니다.
- 일정 또는 대상자 충돌을 감지하고 해결합니다.
- 성능 및 드롭오프 지점을 분석합니다.

자세한 내용은 [여정 분석 에이전트 설명서](./agents/ajo-agent-analyze.md)를 참조하십시오.

#### 제품 지원 에이전트

셀프서비스 디버깅 및 문제 해결을 위해 제품 지원 에이전트를 사용합니다.

- 워크플로우를 종료하지 않고 Adobe Experience Platform 기능 문제를 해결합니다.
- AI Assistant 상호 작용에서 컨텍스트가 있는 지원 티켓을 만듭니다.
- AI Assistant를 통해 티켓 업데이트를 확인합니다.

자세한 내용은 [제품 지원 에이전트 설명서](./agents/product-support.md)를 참조하세요.

## 시작

### 액세스 요구 사항

AI Assistant 및 Experience Platform 에이전트를 사용하려면 Adobe 관리자가 적절한 권한을 설정해야 합니다.

- Real-Time CDP 및 Adobe Journey Optimizer 내에서 AI Assistant를 사용하려면 운영 질문에 액세스할 수 있는 &quot;AI Assistant 활성화&quot; 권한과 &quot;운영 인사이트 보기&quot; 권한이 필요합니다.
- Customer Journey Analytics의 AI Assistant에 대한 액세스는 Customer Journey Analytics 액세스 제어를 통해 관리되며, 이를 통해 제품 지식과 데이터 인사이트 질문을 모두 할 수 있습니다.
- Adobe Experience Manager의 경우 Adobe Admin Console에 설정된 권한을 통해 AI Assistant에 액세스할 수 있습니다.

### 개인정보보호 및 보안

AI Assistant는 다음과 같은 기능을 하며 개인 정보 보호, 보안 및 거버넌스를 기반으로 구축됩니다.

- 교육에 사용되는 개인 데이터가 없습니다.
- 기존의 모든 액세스 제어 정책이 적용됩니다.
- Adobe Experience Platform Healthcare Shield와 함께 사용할 경우 HIPAA 지원.
- 상호 작용 로그에 대한 30일 보존 정책.
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
