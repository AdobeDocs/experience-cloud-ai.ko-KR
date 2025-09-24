---
title: Adobe Experience Platform Agent Orchestrator
description: Adobe Experience Platform Agent Orchestrator에 대해 알아봅니다.
source-git-commit: 860b0f2414dc006c23fedcd7b0e29727fc0641d4
workflow-type: tm+mt
source-wordcount: '916'
ht-degree: 0%

---

# Adobe Experience Platform Agent Orchestrator

Adobe Experience Platform Agent Orchestrator은 Adobe Experience Platform의 새로운 에이전트 계층입니다. 플랫폼의 풍부한 데이터와 고객 지식을 활용하도록 설계된 Experience Platform Agent Orchestrator은 특별히 설계된 전문 Adobe Experience Platform 에이전트 뒤에 숨겨진 정보와 추론을 강화하여 복잡한 의사 결정 및 문제 해결 작업을 사람의 감독 하에 신속하고 규모에 맞게 실행할 수 있도록 합니다. AI 어시스턴트와 같은 대화 인터페이스에서 자연어를 통해 질문을 하거나 도움을 요청하면 Agent Orchestrator이 전문 에이전트에게 자동으로 전화를 걸어 정확한 답변을 얻을 수 있다. Agent Orchestrator은 대화 기록을 기억하여, 맥락을 반복하지 않고 자연스럽게 이전 질문을 기반으로 할 수 있으며, 여러 에이전트의 통찰력을 결합하여 명확하고 통합된 응답을 제공합니다.

어떤 에이전트가 백그라운드에서 작동하는지 알 필요 없이 직관적인 대화 인터페이스를 통해 복잡한 통합 워크플로우를 완료할 수 있습니다. 시스템은 목표를 이해하고 단계별 계획을 수립하며, 피드백에 따라 필요에 따라 접근 방식을 조정합니다. 추론 패널을 탐색하여 단계별 사고 프로세스를 보고 요청이 처리되는 방식을 더 잘 이해할 수 있습니다. Agent Orchestrator을 사용하면 복잡한 워크플로우를 해결하고 Adobe Experience Cloud 애플리케이션 전반에 걸쳐 전략을 최적화할 수 있습니다.

Agent Orchestrator에 대해 알아보려면 이 문서를 참조하십시오.

## Agent Orchestrator 구성 요소 {#components}

Agent Orchestrator은 AI Assistant 대화 인터페이스, 의사 결정 및 계획을 위한 추론 엔진, 전문 Adobe Experience Platform 에이전트 및 관련 정보에 대한 액세스를 제공하는 기술 자료 등 여러 핵심 요소로 구성됩니다.

![Agent Orchestrator의 마케팅 아키텍처입니다.](./images/agent-orchestrator/agentic-architecture.png)

### AI Assistant 대화 인터페이스 {#ai-assistant}

AI Assistant는 Adobe 애플리케이션에서 워크플로를 가속화하는 데 사용할 수 있는 대화형 경험입니다. AI Assistant를 사용하여 제품 지식을 보다 잘 이해하고, 문제를 해결하거나, 정보를 검색하고, 운영 통찰력을 찾을 수 있습니다. AI Assistant는 Experience Platform, Real-Time Customer Data Platform, Adobe Journey Optimizer 및 Customer Journey Analytics을 지원합니다. AI Assistant를 사용하여 Experience Platform 에이전트 및 기타 AI 기능에 액세스할 수 있습니다.

자세한 내용은 [AI Assistant UI 안내서](../ai-assistant/ai-assistant-ui.md)를 참조하십시오.

### 추론 엔진 {#reasoning-engine}

추론 엔진은 자연어 프롬프트에 따라 목표를 해석하고, 제한이나 요구 사항을 확인하고, 목표를 달성하는 데 도움이 되는 단계별 계획을 만듭니다. 단순 문답 시스템과 달리 사물이 바뀌면서 계획을 조정할 수 있고, 필요한 경우 뒤로 돌아가 다른 접근을 시도할 수 있다. AI 비서 대화 인터페이스에서 만든 플랜이 사용자에게 표시되므로 프로세스를 보고 따라갈 수 있을 뿐만 아니라 필요한 경우 개입할 수 있습니다.

### Adobe Experience Platform 에이전트 {#agents}

| 에이전트 | 세부 사항 | 지원되는 애플리케이션 |
| --- | --- | --- |
| [Audience Agent](audience.md) | Audience Agent을 사용하면 중요한 대상 크기 변경 감지, 중복 대상 감지, 대상 인벤토리 탐색 및 대상 크기 검색을 포함하여 대상에 대한 인사이트를 볼 수 있습니다. | <ul><li>Real-Time CDP</li><li>Adobe Journey Optimizer</li></ul> |
| [Data Insights Agent](https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-overview/cja-b2c-overview/data-analysis-ai) | Customer Journey Analytics의 AI Assistant에서 액세스할 수 있는 Data Insights Agent은 데이터에 대한 질문에 빠르고 효율적으로 답변할 수 있는 생성 AI 대화 에이전트입니다. 데이터 보기의 구성 요소를 사용하고 실제 데이터를 사용하여 Analysis Workspace에서 관련 시각화를 구축합니다. | Customer Journey Analytics |
| 실험용 에이전트 | 실험 에이전트는 실험 결과를 분석하고, 영향을 예측하고, 새로운 실험을 제안하여 팀이 더 빠르게 학습할 수 있도록 돕습니다. 과거 및 활성 실험을 중앙 집중화하여 이미 학습한 내용을 기반으로 하며, 차이를 파악하고, 다음에 테스트할 내용을 우선 지정할 수 있습니다. | Adobe Journey Optimizer Experimentation Accelerator |
| [Journey Agent](./ajo-agent-analyze.md) | Journey Agent을 사용하면 Adobe Journey Optimizer 사용자가 자연어 인터페이스를 사용하여 여정을 만들고, 분석하고, 최적화할 수 있습니다. Journey Agent을 사용하면 여정을 신속하게 구축하고, 일정 또는 대상 충돌을 감지하고 해결하고, 성과 및 중단점을 분석하고, 향후 캠페인을 위해 복제할 최고 성능의 여정을 식별할 수 있습니다. 데이터 중심의 의사 결정을 내리고, 고객 참여를 개선하며, 여정 오케스트레이션을 간소화할 수 있습니다. | Adobe Journey Optimizer |
| [제품 지원 에이전트](https://experienceleague.adobe.com/ko/docs/experience-platform/ai-assistant/new-features/customer-support) | 제품 지원 에이전트는 워크플로우를 종료하지 않고 Adobe Experience Platform 기능 및 응용 프로그램의 문제를 해결하는 데 도움이 되는 셀프서비스 디버깅 및 문제 해결 기능입니다. 지원 관리자는 AI Assistant 상호 작용의 컨텍스트가 있는 고객 지원 티켓을 생성할 수 있으며 AI Assistant를 통해 티켓 업데이트를 확인할 수 있습니다. | <ul><li>Adobe Experience Platform</li><li>Real-Time CDP</li><li>Adobe Journey Optimizer</li><li>Adobe Journey Optimizer B2B edition</li><li>Customer Journey Analytics</li><li>Adobe Experience Manager</li></ul> |

### 기술 자료 {#knowledge-base}

이 기술 자료에서는 Adobe 제품 설명서, 비즈니스 객체에 대한 고객 메타데이터 및 분석 데이터를 포함하여 정형 및 비정형 데이터 소스를 통해 상담원이 고객 비즈니스 인텔리전스에 안전하게 액세스할 수 있도록 합니다.

## 액세스 {#access}

AI Assistant 요청은 Adobe Identity Management Services를 사용하여 인증됩니다. 권한은 Adobe Experience Platform 액세스 제어 및 Customer Journey Analytics 액세스 제어에 의해 시행됩니다.

AI Assistant 대화 인터페이스에 액세스하고 하나 이상의 Experience Platform 에이전트를 사용하려면 Adobe 관리자가 권한 UI 또는 Adobe Admin Console에서 관련 권한을 부여해야 합니다.

* **Real-Time CDP** 및 **Adobe Journey Optimizer**: 관리자가 AI Assistant에 액세스할 수 있도록 **AI Assistant 사용** 권한을 부여해야 합니다. 또한 관리자는 사용자가 AI Assistant에서 Operational Insights 질문을 할 수 있도록 **View Operational Insights** 권한을 부여해야 합니다. 두 권한은 모두 관리자가 권한 UI에서 설정합니다.

* **Customer Journey Analytics**: 관리자가 [Customer Journey Analytics 액세스 제어](https://experienceleague.adobe.com/ko/docs/analytics-platform/using/technotes/access-control)를 통해 AI Assistant에 액세스할 수 있는 권한을 부여해야 합니다. 이를 통해 제품 지식 및 데이터 통찰력에 대한 질문을 할 수 있습니다.

>[!NOTE]
>
>Customer Journey Analytics에서는 Operational Insights 질문을 사용할 수 없으므로 추가 권한이 적용되지 않습니다.

* **Adobe Experience Manager**: 관리자가 [Adobe Admin Console](https://helpx.adobe.com/kr/enterprise/using/admin-console.html)을 통해 AI Assistant에 액세스할 수 있는 권한을 부여해야 합니다.


