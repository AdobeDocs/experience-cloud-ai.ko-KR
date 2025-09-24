---
title: Experience Cloud 애플리케이션의 AI
description: Experience Cloud 애플리케이션이 생성 AI(GenAI), AI Assistant 및 아젠틱 AI를 사용하는 방법을 알아봅니다.
source-git-commit: 860b0f2414dc006c23fedcd7b0e29727fc0641d4
workflow-type: tm+mt
source-wordcount: '651'
ht-degree: 0%

---

# Experience Cloud의 AI

Adobe Experience Cloud 애플리케이션 전반에 걸친 AI 기능에 대한 포괄적인 안내서를 시작합니다. 이 설명서에서는 생성형 AI, AI Assistant 및 Adobe 에이전트를 Experience Cloud 워크플로에 통합하여 생산성을 가속화하고 의사 결정을 향상시키는 방법을 다룹니다.

## 이 안내서에 포함된 사항

### AI Assistant

[AI Assistant](./ai-assistant/ai-assistant-ui.md)는 생산성을 높이고 Adobe Experience Platform 기반 응용 프로그램에서 작업을 재정의하는 지능형 대화식 생성 AI 도구입니다. 사용자는 자연어 프롬프트를 통해 제품 지식을 얻고 문제를 해결하며 운영 통찰력을 찾을 수 있습니다. AI Assistant를 사용하여 Adobe Experience Platform 에이전트 및 기타 AI 기능에 액세스할 수도 있습니다.

**주요 기능:**

- **대화형 인터페이스**: 다양한 워크플로 환경 설정에 대한 전체 화면 및 레일 보기 옵션
- **검색 프롬프트**: 카테고리별로 구성된 사전 구성된 프롬프트(학습, 분석, 최적화)
- **컨텍스트 설정**: 대상 응답에 대한 응용 프로그램, 샌드박스 및 데이터 보기 설정을 구성합니다.
- **데이터 시각화**: 데이터 인사이트에 대한 대화형 차트 및 그래프
- **응답 확인**: Source 인용, 추론 설명 및 피드백 메커니즘

### Agent Orchestrator

[Adobe Experience Platform Agent Orchestrator](./agents/agent-orchestrator.md)은(는) Adobe Experience Platform의 새로운 에이전트 계층입니다. 플랫폼의 풍부한 데이터와 고객 지식을 활용하도록 설계된 Experience Platform Agent Orchestrator은 특별히 설계된 전문 Adobe Experience Platform 에이전트 뒤에 숨겨진 정보와 추론을 강화하여 복잡한 의사 결정 및 문제 해결 작업을 사람의 감독 하에 신속하고 규모에 맞게 실행할 수 있도록 합니다. AI 어시스턴트와 같은 대화 인터페이스에서 자연어를 통해 질문을 하거나 도움을 요청하면 Agent Orchestrator이 전문 에이전트에게 자동으로 전화를 걸어 정확한 답변을 얻을 수 있다. Agent Orchestrator은 대화 기록을 기억하여, 맥락을 반복하지 않고 자연스럽게 이전 질문을 기반으로 할 수 있으며, 여러 에이전트의 통찰력을 결합하여 명확하고 통합된 응답을 제공합니다.

**핵심 구성 요소:**

- **추론 엔진**: 단계별 계획을 만들고 필요에 따라 접근 방식을 조정합니다
- **전문 에이전트**: 특정 작업 및 도메인용 특별히 빌드된 에이전트
- **기술 자료**: 비즈니스 인텔리전스 및 문서에 대한 보안 액세스

### 전문 에이전트

#### Audience Agent

다음과 같은 대상에 대한 통찰력을 제공합니다.

- 중요한 대상자 크기 변경 감지
- 중복 대상자 식별
- 대상자 인벤토리 살펴보기
- 대상 크기 검색

#### Data Insights Agent

Customer Journey Analytics에서 사용할 수 있는 이 에이전트는 다음과 같습니다.

- 자연어를 사용하여 데이터에 대한 질문에 답변합니다.
- Analysis Workspace에서 관련 시각화 구축
- 데이터 보기 및 실제 데이터의 구성 요소 사용

#### Journey Agent

Journey Optimizer 사용자는 다음을 수행할 수 있습니다.

- 자연어를 사용하여 여정 만들기, 분석 및 최적화
- 일정 또는 대상자 충돌 감지 및 해결
- 성능 및 드롭오프 포인트 분석
- 복제에 필요한 최고 성능의 여정 파악

#### 제품 지원 에이전트

셀프서비스 디버깅 및 문제 해결 제공:

- 워크플로우를 종료하지 않고 Adobe Experience Platform 기능 문제 해결
- AI Assistant 상호 작용에서 컨텍스트를 사용하여 지원 티켓 만들기
- AI Assistant를 통해 티켓 업데이트 확인

## 시작

### 액세스 요구 사항

AI Assistant 및 Experience Platform 에이전트를 사용하려면 Adobe 관리자가 적절한 권한을 설정해야 합니다.

- **Real-Time CDP 및 Adobe Journey Optimizer**: 운영 질문에 대해 &quot;AI Assistant 사용&quot; 권한과 &quot;Operational Insights 보기&quot; 권한이 필요합니다.
- **Customer Journey Analytics**: Customer Journey Analytics 액세스 제어를 통해 제품 지식 및 데이터 인사이트 질문에 대한 액세스
- **Adobe Experience Manager**: Adobe Admin Console을 통해 액세스

### 개인 정보 보호 및 보안

AI Assistant는 다음과 같은 기능을 하며 개인 정보 보호, 보안 및 거버넌스를 기반으로 구축됩니다.

- 교육에 개인 데이터가 사용되지 않음
- 기존의 모든 액세스 제어 정책이 적용됩니다.
- Adobe Experience Platform Healthcare Shield와 함께 사용할 경우 HIPAA 지원
- 상호 작용 로그에 대한 30일 보존 정책
- 샌드박스별 데이터 격리

## 우수 사례

- 대상 인사이트를 얻으려면 프롬프트에 **구체적으로 지정**
- 출처 인용과 추론 설명을 사용하여 **응답 확인**
- 관련 데이터 원본을 확인하려면 **컨텍스트 설정을 사용**&#x200B;하세요.
- AI Assistant 성능을 개선하는 데 도움이 되도록 **피드백을 제공**
- 포괄적인 분석을 위해 여러 에이전트의 **통찰력을 결합**

## 법적 고려 사항

- AI Assistant는 현재 영어만 지원합니다
- 언어 모델이 실수를 할 수 있으므로 항상 응답 확인
- 제공된 추론 단계 및 설명을 검토합니다.
- 모든 문제 또는 부정확성에 대한 피드백 제출

이 안내서에서는 기본 상호 작용에서 고급 에이전트 오케스트레이션 및 전문 워크플로우에 이르기까지 Experience Cloud 애플리케이션 전반에서 AI 기능을 효과적으로 사용하는 데 필요한 모든 사항을 제공합니다.

