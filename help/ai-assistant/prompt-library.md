---
title: AI Assistant 프롬프트 라이브러리
description: AI Assistant를 쿼리할 때 사용할 수 있는 다양한 종류의 프롬프트 및 프롬프트 패턴에 대해 알아봅니다.
source-git-commit: 860b0f2414dc006c23fedcd7b0e29727fc0641d4
workflow-type: tm+mt
source-wordcount: '811'
ht-degree: 0%

---

# AI Assistant 프롬프트 라이브러리

AI Assistant에서 사용할 수 있는 다양한 유형의 프롬프트에 대해서는 이 안내서를 참조하십시오.

## Audience Agent

다음 섹션에서는 Audience Agent과 함께 사용하여 대상을 탐색 및 분석할 수 있는 예제 프롬프트를 제공합니다. 여기에는 대상 특성을 조사하고, 중복 대상을 감지하고, 대상 크기를 검색하고, 시간에 따른 대상 크기의 중요한 변화를 모니터링하는 방법이 포함됩니다. 이러한 프롬프트를 사용하여 보다 심층적인 통찰력을 얻고 대상 데이터의 품질을 유지하십시오.

### 대화 대상자 탐색

- &quot;부유한 구매자를 위한 필드를 보여 주세요.&quot;
- &quot;지난 30일 동안 어떤 대상자가 캠페인에서 활성화되거나 사용되지 않았습니까?&quot;
- &quot;지난 3개월 동안 새 대상에 매핑된 모든 대상을 나열합니다.&quot;

### 중복 대상자 감지

- &quot;동일하거나 유사한 설명을 가진 대상이 있습니까?&quot;
- &quot;규칙은 동일하지만 이름이 다른 대상자를 식별합니다.&quot;
- &quot;규칙은 같지만 활성화 대상이 다른 모든 대상을 표시합니다.&quot;

### 대상 크기 검색

- &quot;내 대상 &quot;Gold-star Members in California_f153e1&quot;의 현재 크기는 얼마입니까?&quot;
- &quot;나의 가장 큰 청중은 무엇인가?&quot;

### 대상자 크기의 중요한 변경 사항 감지

- &quot;지난 주에 20% 이상 증가한 대상은 무엇입니까?&quot;
- &quot;지난 달에 15% 이상 크기가 감소한 대상은 무엇입니까?&quot;
- &quot;가장 빠르게 성장하는 대상은 무엇입니까?&quot;

## Data Insights Agent

다음 예제 프롬프트는 Data Insights Agent과 함께 사용하여 데이터를 분석하고, 트렌드를 식별하며, 실행 가능한 통찰력을 발견할 수 있습니다.

### 데이터 시각화

- &quot;9월에 수익을 보여주세요.&quot;
- &quot;9월 주문 트렌드&quot;
- &quot;9월 지역별 매출액 표시&quot;
- &quot;제품 범주별 매출 점유율&quot;
- &quot;1월부터 5월까지 요일별 주문&quot;
- &quot;3월부터 6월까지 성별 주문을 표시합니다.&quot;
- &quot;2월부터 5월까지 SKU에서 발생하는 이익은 무엇입니까?&quot;
- &quot;9월 매장 이름별 매출&quot;
- &quot;9월 이익별 상위 10개 SKU는 무엇입니까?&quot;
- &quot;연간 월별 구매 비율&quot;
- &quot;9월의 총 이익.&quot;

## Journey Agent

다음 예제 프롬프트는 Journey Agent과 함께 사용하여 여정 라이프사이클을 분석하고, 여정 리소스를 관리하고, 대상 및 여정 관계에 대한 통찰력을 얻고, 여정 간의 충돌을 감지하는 데 도움이 될 수 있습니다. 이러한 프롬프트를 사용하여 여정 오케스트레이션을 최적화하고 문제를 효율적으로 해결하십시오.

### 여정 라이프사이클 질문

- &quot;{JOURNEY_NAME}은(는) 언제 게시되었습니까?&quot;
- &quot;{JOURNEY_NAME}이(가) 언제 중지되었습니까?&quot;
- &quot;현재 테스트 모드에 있는 모든 여정 나열&quot;

### 여정 리소스 질문

- &quot;보유한 라이브 여정은 몇 개입니까?&quot;
- &quot;모든 예약된 반복 여정 및 예상 실행 시간 목록을 제공합니다.&quot;

### 대상 및 여정 통찰력

- &quot;X개 이상의 여정에서 사용되는 대상자는 무엇입니까?&quot;
- &quot;{AUDIENCE_NAME} 대상을 사용하는 모든 여정을 나열합니다.&quot;

### 충돌 분석 프롬프트

이러한 프롬프트를 사용하여 예약 및 대상 중복을 포함하여 여정 간 잠재적 충돌을 분석하십시오.

+++목록을 보려면 선택

- &quot;충돌 유형(예약/대상) 정보가 있는 여정 {JOURNEY_NAME}에 대한 충돌을 실시간/실행 여정과 함께 포괄적으로 분석할 수 있습니까?&quot;
- &quot;충돌 유형 정보를 사용하여 {JOURNEY_NAME} 여정에 대한 일정 충돌 분석을 수행하세요.&quot;
- &quot;충돌 유형 정보가 있는 여정 {JOURNEY_NAME}에 대해 대상 중복 분석을 수행하세요.&quot;
- &quot;{JOURNEY_NAME} 여정에 대해 일정 충돌이 있습니까?&quot;
- &quot;{JOURNEY_NAME} 여정에 대한 대상 겹침 충돌을 표시합니다.&quot;
- &quot;다른 실시간 여정과의 {JOURNEY_NAME} 여정에 대한 모든 충돌을 분석하십시오.&quot;
- &quot;{JOURNEY_NAME} 여정에 대한 현재 충돌은 무엇입니까?&quot;
- &quot;{JOURNEY_NAME} 여정에 다른 여정과 대상 충돌이 있는지 확인하십시오.&quot;
- &quot;여정 {JOURNEY_NAME}과(와) 관련된 일정 충돌을 확인하십시오.&quot;
- &quot;{JOURNEY_NAME}에 대한 모든 여정 충돌에 대해 알고 싶습니다.&quot;
- &quot;일정 또는 대상별로 {JOURNEY_NAME}과(와) 일치하는 라이브 여정이 있습니까?&quot;
- &quot;실행 중인 여정과 비교하여 {JOURNEY_NAME} 여정에 대한 충돌 유형을 식별합니다.&quot;
- &quot;{JOURNEY_NAME} 여정 및 다른 여정에 대해 겹치는 대상을 표시합니다.&quot;
- &quot;여정 {JOURNEY_NAME}과(와) 라이브 여정 사이에 겹치는 일정을 강조 표시합니다.&quot;
- &quot;{JOURNEY_NAME} 여정이 다른 여정과 충돌하여 실행되고 있습니까?&quot;
- &quot;{JOURNEY_NAME}에 대한 충돌을 감지하고 나열하십시오.&quot;
- &quot;{JOURNEY_NAME} 여정에 대한 모든 유형의 충돌을 보고합니다.&quot;
- &quot;{JOURNEY_NAME}에 대한 충돌 분석(예약 및 대상)을 제공합니다.&quot;
- &quot;성능에 영향을 줄 수 있는 충돌이 {JOURNEY_NAME}에 있습니까?&quot;
- &quot;{JOURNEY_NAME}에 영향을 주는 활성 충돌이 있습니까?&quot;
- &quot;{JOURNEY_NAME}과(와) 충돌하는 여정을 일정 또는 대상별로 나열합니다.&quot;
- &quot;{JOURNEY_NAME} 여정이 충돌 알림을 트리거했습니까?&quot;
- &quot;{JOURNEY_NAME} 여정에 대해 잠재적인 대상 충돌을 찾습니다.&quot;
- &quot;{JOURNEY_NAME} 여정에 대한 충돌 위험을 분석합니다.&quot;
- &quot;{JOURNEY_NAME}에 대한 충돌 진단을 제공합니다.&quot;

+++

## 제품 지원 에이전트

제품 지원 에이전트는 문제를 해결하고, 지원 사례를 만들고, 지원 티켓의 상태를 추적하는 데 도움이 됩니다. 다음 예제 프롬프트를 사용하여 지원을 받으십시오.

### 문제 해결 도움말

- &quot;라이선스 사용 대시보드와 Experience Platform 홈 페이지에서 프로필 수가 다른 이유는 무엇입니까?&quot;
- &quot;여정이 트리거되지 않는 이유는 무엇입니까?&quot;
- &quot;Adobe Experience Platform은 어떻게 실시간 경험을 생성합니까?&quot;
- &quot;Adobe Experience Platform에서 경고를 구성하고 사용하려면 어떻게 합니까?&quot;
- &quot;Adobe Experience Platform 활성화에서 배치 세분화 작업의 제한은 얼마입니까?&quot;
- &quot;Adobe Experience Platform 활성화의 평균 프로필 풍부성 제한은 얼마입니까?&quot;

### 지원 사례 만들기

- &quot;지원 티켓을 만듭니다.&quot;
- &quot;지원 티켓을 만드는 것을 도와줄 수 있습니까?&quot;

### 사례 진행 추적

- &quot;내 사건 E-12345에 대한 최신 소식은 무엇입니까?&quot;
- &quot;티켓 E-67890에 대한 최신 정보는 무엇입니까?&quot;