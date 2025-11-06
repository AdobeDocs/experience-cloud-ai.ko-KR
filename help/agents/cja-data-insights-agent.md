---
description: Customer Journey Analytics에서 Data Insights Agent을 사용하여 데이터를 시각화하는 방법 알아보기
title: Customer Journey Analytics에서 Data Insights Agent을 사용하여 데이터 시각화
role: User, Admin
solution: Customer Journey Analytics
source-git-commit: 539ca6244b7de61275af53e993b59310767aa825
workflow-type: tm+mt
source-wordcount: '2502'
ht-degree: 1%

---

# Data Insights Agent을 사용하여 데이터 시각화

>[!AVAILABILITY]
>
>Data Insights Agent은 제한된 기간 동안 적격 고객이 사용할 수 있습니다. Data Insights Agent에 대한 액세스는 2026년 2월 28일까지 가능합니다. 이 날짜 이후에도 중단 없이 Data Insights Agent을 계속 사용하려면 Adobe 계정 담당자에게 문의하여 Adobe Experience Platform Agent Orchestrator 라이선스에 대해 자세히 알아보십시오.

Customer Journey Analytics의 [AI Assistant](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2c-overview/ai-assistant)에서 액세스할 수 있는 Data Insights Agent은 데이터에 대한 질문에 빠르고 효율적으로 답변할 수 있는 생성 AI 대화 에이전트입니다. 데이터 보기의 구성 요소를 사용하고 실제 데이터를 사용하여 Analysis Workspace에서 관련 시각화를 구축합니다.

Data Insights Agent을 사용하여 Analysis Workspace의 데이터 중심 질문에 답변하면 Analysis Workspace에서 시각화를 수동으로 구축하고 데이터 보기 구성 요소에 익숙해지는 데 드는 시간을 크게 절약할 수 있습니다.

AI Assistant의 ![Data Insights Agent](images/cja-agent//cja-ai-asst-da.gif)

## 범위 내 및 범위 외 기능

| 기능 | 범위 내 | 범위를 벗어남 |
| --- | --- | --- |
| **시각화 유형** | <ul><li>선</li><li>다중 라인</li><li>자유 형식 테이블</li><li>막대</li><li>도넛</li><li>요약 번호</li></ul> | <ul><li>흐름</li><li>폴아웃</li><li>집단 테이블</li><li>영역, 스택 영역</li><li>스택 막대</li><li>글머리 기호</li><li>콤보</li><li>막대 그래프</li><li>가로 막대, 스택 가로 막대</li><li>주요 지표 요약</li><li>분산</li><li>요약 변경</li><li>텍스트</li><li>트리맵</li><li>벤</li><li>가이드 분석: 활성 증가, 전환 트렌드, 참여, 첫 번째 사용 영향, 빈도, Funnel, 순 성장, 릴리스 영향, 유지, 타임라인, 트렌드</li></ul> |
| **Workspace 작업 및 에이전트 기능** | <ul><li>시각화 작성 및 업데이트<p>자유 형식 테이블 및 관련 시각화(예: 선, 막대, 도넛 등)를 생성합니다.<p>예를 들어, *2월부터 5월까지 SKU의 이익은 무엇입니까?*</p></li><li>후속 질문<p>이전 프롬프트에서 컨텍스트에 있는 프롬프트에 응답합니다. 예:</p> <ul><li>프롬프트 1: *3월의 트렌드 이벤트*</li><li>프롬프트 2: *대신 3월에서 4월까지의 데이터 표시*</li></ul> </li><li>범위를 벗어난 프롬프트 감지<p>*이 프로젝트 내보내기*&#x200B;와 같이 범위를 벗어난 프롬프트를 제출하는 경우 Data Insights Agent은 질문이 범위를 벗어났음을 알리는 방식으로 응답합니다.</p></li></ul> | <ul><li>공유</li><li>내보내기</li><li>다운로드</li><li>사용자 환경 설정 관리</li><li>데이터 보기 관리</li><li>Analytics 대시보드 앱</li><li>기여도</li><li>인라인 요약 또는 응답<p>Data Insights Agent은 사용자 프롬프트의 요약 답변으로 채팅 레일에서 인라인으로 응답할 수 없습니다. 범위를 벗어나는 프롬프트의 예로는 *마지막 프롬프트에서 인사이트에 대한 요약을 제공합니다* 및 *선 시각화에서 하이라이트를 요약합니다*.</p></li></ul> |
| **명확한 질문** | Data Insights Agent이 답변할 수 있는 충분한 컨텍스트가 없는 질문을 하거나 너무 일반적인 질문을 하는 경우 Data Insights Agent은 명확한 질문이나 제안된 옵션으로 응답합니다. <p>구성 요소 관련 질문의 예는 다음 명확화 질문입니다.</p><ul><li>지표: *어떤 &quot;매출&quot; 지표를 의미했습니까?*</li><li>Dimension: *아래 &quot;지역&quot; 중 어떤 것에 집중하시겠습니까?*</li><li>세그먼트: *어떤 &quot;계정&quot; 세그먼트를 적용하시겠습니까?*</li><li>날짜 범위: *지난 달, 마지막 전체 달 또는 마지막 30일을 의미합니까?*</li></ul><p>다음 명확화 질문은 차원 항목과 관련된 질문의 예입니다.</p> <ul><li>어떤 &quot;가게 이름&quot;을 말씀하시는 건가요? (예: 스토어 #5274, 스토어 #2949 등)</li></ul> | 질문을 명확히 하는 것은 구성 요소 및 차원 항목으로 제한됩니다. Data Insights Agent에서는 데이터 보기, 시각화, 데이터 세부기간, 비교 및 범위와 같은 항목을 명확하게 할 수 없습니다. 명확한 질문을 사용할 수 없는 경우, 에이전트는 사용자가 요청할 가능성이 가장 큰 질문을 기본값으로 설정합니다. 예기치 않은 시각화 또는 데이터 세부기간을 반환하는 경우 후속 질문을 하거나 시각화 및 데이터를 조정할 수 있습니다. |
| **데이터 확인 및 수정** | 생성된 자유 형식 테이블 조회 및 데이터 시각화를 통해 데이터 검증성 및 정확성을 확인할 수 있다. <p>예를 들어 Data Insights Agent에 *지난 달의 트렌드 주문*&#x200B;을(를) 요청하면 새로 생성된 패널, 데이터 시각화 및 자유 형식 테이블에서 올바른 지표(&quot;주문&quot;) 및 날짜 범위(&quot;지난 달&quot;)가 선택되었는지 확인할 수 있습니다. | Data Insights Agent은 추가된 구성 요소 또는 시각화를 알려 주지 않습니다.</p> |
| **피드백 메커니즘** | <ul><li>엄지 손가락 위로</li><li>엄지 손가락 아래로</li><li>플래그</li></ul> |  |


## Data Insights Agent 액세스 관리 {#manage-access}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-enable-data-insights-data-view"
>title="Data Insights Agent에 사용"
>abstract="이 옵션을 사용하면 Data Insights Agent에서 사용할 수 있도록 이 데이터 보기를 사용할 수 있습니다. Data Insights Agent은 Customer Journey Analytics의 AI Assistant에서 액세스할 수 있는 생성 AI 대화 에이전트입니다. 텍스트 프롬프트를 통해 데이터를 빠르게 분석하는 데 도움이 됩니다. 데이터 보기의 구성 요소를 사용하고 실제 데이터를 사용하여 Analysis Workspace에서 관련 시각화를 구축합니다."

<!-- markdownlint-enable MD034 -->

다음 매개 변수는 Customer Journey Analytics에서 Data Insights Agent에 대한 액세스를 제어합니다.

* **솔루션 액세스**: Data Insights Agent은 2025년 11월 30일까지 제한된 액세스 프로그램의 일부로 모든 Customer Journey Analytics 고객이 사용할 수 있습니다. Adobe Analytics에서는 사용할 수 없습니다.

* **계약 액세스**: AI Assistant에서 Data Insights Agent을 사용할 수 없는 경우 조직의 관리자 또는 Adobe 계정 팀에 문의하십시오. 조직에서 Data Insights Agent을 사용하려면 먼저 생성 AI와 관련된 특정 법률 용어에 동의해야 합니다.

* **권한**: 사용자가 Data Insights Agent에 액세스하려면 [!UICONTROL Adobe Admin Console]에서 필요한 권한을 부여해야 합니다.

  권한을 부여하려면 [제품 프로필 관리자](https://helpx.adobe.com/enterprise/using/manage-product-profiles.html)가 [!UICONTROL Admin Console]에서 다음 단계를 완료해야 합니다.

   1. **[!UICONTROL Admin Console]**&#x200B;에서 **[!UICONTROL 제품]** 탭을 선택하여 **[!UICONTROL 모든 제품 및 서비스]** 페이지를 봅니다.
   1. **[!UICONTROL Customer Journey Analytics]**&#x200B;을(를) 선택합니다.
   1. **[!UICONTROL 제품 프로필]** 탭에서 [!UICONTROL AI Assistant: 제품 기술 자료]에 대한 액세스 권한을 제공할 제품 프로필의 제목을 선택합니다.
   1. 특정 제품 프로필에서 **[!UICONTROL 권한]** 탭을 선택합니다.

      Admin Console의 ![사용 권한 탭](images/cja-agent/ai-assistant-permissions-tab.png)

   1. 제공된 테이블의 **[!UICONTROL 보고 도구]** 행에서 편집 아이콘 ![편집](images/cja-agent/Edit.svg)을 선택합니다.
   1. **[!UICONTROL AI Assistant: 제품 정보]**(으)로 스크롤하거나 검색한 다음 이 권한 옆에 있는 더하기 아이콘 ![AddCircle](images/cja-agent/AddCircle.svg)을(를) 선택합니다.
   1. **[!UICONTROL Data Insights Agent]**(으)로 스크롤하거나 검색한 다음 이 권한 옆에 있는 더하기 아이콘 ![AddCircle](images/cja-agent/AddCircle.svg)을(를) 선택합니다.

      **[!UICONTROL AI 도우미: 제품 정보]** 권한과 **[!UICONTROL Data Insights Agent]** 권한이 **[!UICONTROL 포함된 권한 항목]** 열에 추가됩니다.

      ![권한 추가](images/cja-agent/ai-assistant-permissions.png).

   1. **[!UICONTROL 저장]**&#x200B;을 선택하여 권한을 저장합니다.

  액세스 제어에 대한 자세한 내용은 [액세스 제어](https://experienceleague.adobe.com/en/docs/analytics-platform/using/technotes/access-control#access-control)를 참조하십시오.

* **데이터 보기 액세스**: Data Insights Agent에 대해 데이터 보기를 사용하도록 설정해야 합니다.

  >[!IMPORTANT]
  >
  >데이터 보기를 활성화할 때 다음 사항을 고려하십시오.
  >* IMS 조직당 최대 50개의 데이터 보기를 활성화할 수 있습니다. 주어진 조직에 대해 모든 제품 프로필에서 50개 이상의 데이터 보기를 활성화하면 Data Insights Agent에서 가장 많이 사용되는 50개의 데이터 보기를 사용합니다.
  >* Data Insights Agent은 포함된 데이터 보기를 활성화한 같은 날 중에 참조할 수 있습니다.

  Data Insights Agent에 대한 데이터 보기를 활성화하려면 다음을 수행하십시오.

   1. Customer Journey Analytics에서 **[!UICONTROL 데이터 관리]** > **[!UICONTROL 데이터 보기]**&#x200B;를 선택합니다.
   1. Data Insights Agent에 사용할 데이터 보기를 하나 이상 선택한 다음 **[!UICONTROL Data Insights Agent에 사용]**&#x200B;을 선택합니다.

      ![Data Insights Agent에 대한 데이터 보기 사용](images/cja-agent/data-view-enable-dia.png)

  IMS 조직에서 Data Insights Agent에 대해 활성화된 데이터 보기 수를 보려면 다음을 수행하십시오.

   1. Customer Journey Analytics에서 **[!UICONTROL 데이터 관리]** > **[!UICONTROL 데이터 보기]**&#x200B;를 선택합니다.
   1. **[!UICONTROL Data Insights Agent]** 열 맨 위에 있는 정보 아이콘을 선택합니다.

      ![Data Insights Agent 정보 아이콘](images/cja-agent/data-insights-agent-tooltip.png)

## AI Assistant에서 Data Insights Agent 액세스

1. [experience.adobe.com](https://experience.adobe.com/)&#x200B;(으)로 이동하여 Adobe ID으로 로그인합니다.
1. Experience Cloud 홈에서 **Customer Journey Analytics**&#x200B;을(를) 선택합니다.
1. 새 빈 프로젝트를 열려면 프로젝트 페이지 상단의 배너에서 **[!UICONTROL 빈 프로젝트]**&#x200B;을(를) 선택하십시오.
1. 패널에 대해 선택한 데이터 보기가 [Customer Journey Analytics에서 Data Insights Agent에 대한 액세스 관리](#manage-access-to-data-insights-agent-in-customer-journey-analytics)에 설명된 대로 Data Insights Agent에서 사용할 수 있도록 설정된 데이터 보기인지 확인하십시오.
1. 페이지의 오른쪽 상단 영역에서 AI Assistant 채팅 아이콘을 선택합니다.

   채팅 아이콘이 보이지 않는 경우 관리자에게 문의하여 Admin Console에서 다음 기능을 활성화하십시오.

   * 보고 도구: **[!UICONTROL AI 길잡이: 제품 지식]**
   * 데이터 보기 도구: **[!UICONTROL Data Insights Agent]**

   자세한 내용은 [Customer Journey Analytics에서 Data Insights Agent 액세스 관리](#manage-access-to-data-insights-agent-in-customer-journey-analytics)를 참조하십시오.

   ![AI 길잡이 아이콘](images/cja-agent/ai-asst-icon.png)

1. 페이지 하단의 **[!UICONTROL Customer Journey Analytics에 대해 묻기]** 대화 상자에서 Data Insights Agent을 사용하여 데이터 시각화 질문을 합니다.

   자세한 내용은 다음 예를 참조하십시오.

### 예제 1

예를 들어 7월에 받은 주문에 관심이 있다고 가정해 보겠습니다.

**프롬프트:** *&quot;7월의 트렌드 주문&quot;* 입력

![AI 프롬프트](images/cja-agent/ai-asst-prompt1.png)

**응답:** Data Insights Agent은 데이터 보기에서 지표 및 구성 요소를 포함한 데이터를 확인하여 통찰력을 수집합니다. 프롬프트가 데이터 범위 내에서 올바른 차원 및 지표로 변환됩니다.

보시다시피 7월 주문을 표시하기 위해 선 그래프와 자유 형식 테이블을 자동으로 생성했습니다.

![프롬프트에 응답 - 선 그래프 및 자유 형식 테이블](images/cja-agent/ai-asst-result.png)

### 예제 2

다음으로, 지역별로 매출이 어떻게 비교되는지 확인하려고 합니다.

**프롬프트:** 프롬프트 창에서 *&quot;지역별 매출액 표시&quot;*&#x200B;를 입력하십시오.

**응답:** Data Insights Agent은 &quot;지역&quot;별로 &quot;고객 지역&quot;을 의미한다는 것을 지능적으로 이해합니다. 지역별 매출을 가장 잘 보여주는 막대 차트를 생성합니다.

![막대 차트](images/cja-agent/ai-asst-result2.png)

### 예제 3

다음으로 지역별 매출을 이해하는 것 외에도 지역별 수익 데이터를 확인할 수 있습니다. 이전 프롬프트를 반복하는 대신 Data Insights Agent에 최신 시각화 및 자유 형식 테이블을 업데이트하도록 요청할 수 있습니다.

**프롬프트:** 프롬프트 창에서 *&quot;이익 추가&quot;를 입력하십시오.*

**응답:** **[!UICONTROL 막대]** 차트는 여전히 가장 간결한 답변을 제공하지만 이익 지표가 자유 형식 테이블의 열로 추가되었습니다.

![막대 차트](images/cja-agent/ai-asst-result4.png)

### 예제 4

마지막으로, 제품 범주별 매출액을 살펴보자.

**프롬프트:** 프롬프트 창에 *&quot;제품 범주별 매출액 비율&quot;을 입력하십시오.*

**응답:** Data Insights Agent은 질문에 답변할 수 있도록 가장 적절한 시각화(이 경우 **[!UICONTROL 도넛]** 시각화)를 선택합니다.

![도넛](images/cja-agent/ai-asst-result3.png)

## Experience Cloud 애플리케이션에서 Data Insights Agent 액세스

Adobe Experience Platform Agent Orchestrator을 사용하면 Adobe Journey Optimizer 및 Real-Time CDP과 같은 여러 Adobe Experience Cloud 애플리케이션에서 Data Insights Agent의 기능에 액세스할 수 있습니다.

Agent Orchestrator은 요청을 해석하고 필요한 전문 에이전트를 결정하고 올바른 응답을 제공하도록 조정합니다. 다중 전환 상호 작용 간의 컨텍스트를 추적하므로 자연스럽게 이전 쿼리를 빌드할 수 있습니다.

자세한 내용은 [Adobe Experience Platform Agent Orchestrator](/help/agents/agent-orchestrator.md)을 참조하세요.

## 예제 데이터 시각화 프롬프트

다음은 일반적인 프롬프트 및 Data Insights Agent에서 이러한 프롬프트에 응답하는 데 사용한 시각화의 몇 가지 예입니다.

| 예제 프롬프트 | 예상 시각화 |
| --- | --- |
| [개월]에 이익 표시 | 선<p>기본적으로 특정 시간 범위 내에서 트렌드 또는 지표를 요청하면 라인 시각화가 반환됩니다. |
| [개월]의 주문 트렌드 | 선 |
| [개월]에 지역별 수입 표시 | 막대 |
| 제품 범주별 매출 점유율 | 도넛 |
| 1월부터 5월까지 요일별 주문 | 막대 |
| 3월부터 6월까지 성별 주문 표시 | 막대 |
| 2월부터 5월까지 SKU의 이익은 얼마입니까 | 막대 |
| [월]의 저장소 이름별 수익 | 막대 |
| [월]에 수익별 상위 10개 SKU는 무엇입니까? | 막대 |
| 연간 월별 구매 비율 | 도넛 |
| [개월]의 총 이익 | 요약 번호<p>특정 시간 범위 동안 지표의 &quot;합계&quot;를 요청하려면 요약 번호 시각화를 반환해야 합니다. |

## 프롬프트 우수 사례

Data Insights Agent은 각 사용자 프롬프트에서 제공하는 컨텍스트를 처리하고 자유 형식 테이블에서 가장 적절한 시각화 및 구성 요소로 지능적으로 응답하려고 합니다.

프롬프트에 사용된 특정 단어와 구에 따라 응답이 다를 수 있으며, 언어가 약간 변경되면 다른 결과가 나타날 수 있습니다.

최상의 결과를 얻으려면 다음 지침을 고려하십시오.

* **구체적으로 지정:** 응답 범위를 좁히려면 정확한 용어를 포함하십시오. 다음은 특정 프롬프트의 예입니다. &quot;Last month&#39;s sales in California&quot;

* **명확한 지표, 차원 및 세그먼트 사용:** 특정 지표(예: &quot;매출&quot;), 차원(예: &quot;웹 사이트 이름&quot;), 세그먼트(예: &quot;iPhone 사용자&quot;) 및 날짜 범위(예: &quot;최근 3개월&quot;)를 추가하면 Data Insights Agent이 올바른 데이터에 집중할 수 있습니다.

* **직접 질문하기:** 직접 질문을 표현하면 Data Insights Agent에서 명확하고 관련성 있는 통찰력을 쉽게 제공할 수 있습니다. 다음은 &quot;올해 제품 범주별 평균 매출은 무엇입니까?&quot;라는 질문을 즉석에서 던진 예입니다.

예상할 수 있는 응답 유형과 함께 Data Insights Agent을 사용하여 프롬프트에 사용할 수 있는 다음 예시 용어 표를 검토하십시오.

이러한 예제는 특정 단어나 구조가 데이터 Insight 에이전트의 출력에 어떤 영향을 미칠 수 있는지 파악하여 보다 정확하고 중요한 통찰력을 보장하는 데 도움이 되도록 설계되었습니다. Data Insights Agent은 생성 AI를 사용하므로 시각화 또는 선택한 데이터가 유사한 프롬프트에 따라 약간 다를 수 있습니다.

| 원하는 결과 | 용어와 구 예시 |
| --- | --- |
| 요약 번호 시각화 | <ul><li>합계</li></ul> |
| 구성 요소 비교 | <ul><li>비교</li><li>및</li><li>대비</li><li>주별</li><li>월정액</li><li>사분기</li><li>해가 거듭되어</li></ul> |
| 도넛 시각화 | <ul><li>비율</li><li>공유</li><li>배포</li><li>백분율</li><li>기여도</li><li>부분</li><li>부분</li></ul> |
| 선 시각화 | <ul><li>트렌드</li><li>[시간 범위]의 [지표]</li></ul> |
| 막대 시각화 | <ul><li>[Dimension]의 [지표]</li></ul> |

<!--

## Beta testing expectations and requested feedback

After posing each question, carefully review the assistant's provided answer. It's crucial to evaluate the generated visualizations comprehensively before providing feedback. 

Consider the following when evaluating a response from Data Insights Agent: 

* Chat rail response or template: Evaluate the textual response provided. Is the response appropriate given the context of your prompt? 

* Visualization/chart: Evaluate the visualization. Is it the appropriate or expected visualization for your question, or would you have expected a different visualization?  

* Freeform table: Evaluate the freeform table. Is the freeform table data correct? Is it breaking down data where requested? Are the applied segments those that you requested or expected? 

* Error Message / Out-of-Scope: If a generic error message is given stating the question is out of scope, provide feedback on whether you think the out-of-scope message is appropriate, given your prompt. Was your prompt actually in scope? 

**For every response, give a thumbs up or thumbs down, based on the response.**

Following the thumbs up or thumbs down selection, please make a selection for the relevant multi-select feedback boxes. If you want to provide additional feedback, add notes in the open text box.

## Questions and Contact

* Send questions and feedback in the Beta Slack channel: #data-insights-agent-in-cja-beta

-->


## 구성 모범 사례

다음은 Data Insights Agent에서 추가 정보를 묻는 메시지를 표시하지 않고 올바른 구성 요소를 찾아 더 깔끔한 답변을 반환할 수 있도록 Customer Journey Analytics 구성(데이터 보기, 계산된 지표, 세그먼트 등)에 대한 모범 사례입니다.

* **필요한 구성 요소의 균형을 맞춥니다**. 데이터 세트의 모든 필드를 지표 또는 차원 구성 요소로 데이터 보기에 추가하지 마십시오. 특히 분석에 사용하지 않을 것이 가장 확실합니다. 반면, 분석에 필요한 것으로 예상하는 필드로만 자신을 엄격히 제한하지 마십시오. 너무 제한된 데이터 보기는 분석 및 Data Insights Agent 기능의 유연성을 제한합니다.
* **항상 친숙한 표시 이름을 사용하십시오**. 데이터 보기에서 정의하는 모든 필드(지표 또는 차원 구성 요소)에 친숙한 구성 요소 이름이 있는지 확인합니다. 친숙한 이름으로 필드 이름을 바꾸는 프로세스는 특히 Adobe Analytics 소스 커넥터 데이터 세트의 필드와 관련이 있습니다. 이러한 필드에는 종종 `eVar41` 또는 `prop25`과(와) 같이 식별되지 않는 이름이 있습니다.
* **고유한 이름을 사용합니다**. 구별되는 이름은 데이터 보기에서 지표 및 차원 구성 요소와 동일한 필드를 사용할 때 특히 관련이 있습니다. 또는 동일한 유형의 여러 구성 요소에서 필드를 사용할 때(예: 두 개의 다른 지표에서) 각각 구성 요소 설정이 다릅니다.
* **구성 요소 명명 규칙을 사용합니다**. 구성 요소 이름 지정 규칙을 사용하여 구성 요소를 그룹화할 수 있습니다. 예: **[!UICONTROL 개 주문 | 제품]** 및 **[!UICONTROL 주문 | Customer]**&#x200B;은(는) 데이터에 있을 수 있는 서로 다른 주문 지표를 구분할 수 있습니다.
* **데이터 사전 사용**. 데이터 사전에 구성 요소에 대한 설명 및 기타 관련 데이터를 추가합니다. 데이터 Insight 에이전트는 현재 데이터 사전의 설명 및 태그를 사용하지 않지만 향후 사용할 수 있습니다.
* **승인된 계산된 지표를 사용**&#x200B;합니다. 승인된 계산된 지표만 데이터 보기의 구성 요소로 사용하는 프로세스에 동의하고 실험적인 계산된 지표를 사용하지 마십시오.
* **필요한 세그먼트 공유**. 세그먼트를 공유하고 Data Insights Agent 프롬프트에 필요한 세그먼트를 표시해야 합니다.
* **데이터 보기 간에 구성 요소 이름을 표준화합니다**. 여러 데이터 보기에서 동일한 필드를 구성 요소로 사용하는 경우 해당 구성 요소에 대해 하나의 친숙한 이름 및 단일 식별자를 사용해야 합니다. Data Insights Agent은 단일 이름과 식별자를 사용하여 컨텍스트를 손실하지 않고 데이터 보기를 전환할 수 있습니다.

>[!MORELIKETHIS]
>
>[구성 요소 설정](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/component-settings/overview)
>[데이터 사전](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/data-dictionary/data-dictionary-overview)
>[계산된 지표 승인](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/cja-calcmetrics/cm-workflow/cm-approving)
>[세그먼트 공유](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/segments/seg-share)
