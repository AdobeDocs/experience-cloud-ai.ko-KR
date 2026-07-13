---
title: Adobe Analytics에서 Customer Journey Analytics으로 업그레이드할 때 Coworker를 사용하여 데이터 유효성 검사
description: Analytics 관리자가 CX Enterprise Coworker 데이터 유효성 검사 기술을 사용하여 업그레이드 중에 Adobe Analytics 및 Customer Journey Analytics 데이터를 비교하는 방법에 대해 알아봅니다.
hide: true
source-git-commit: 1a93f2afc1e8d33f8d42b24018758d51916dd61d
workflow-type: tm+mt
source-wordcount: '1542'
ht-degree: 0%

---

# Adobe Analytics에서 Customer Journey Analytics으로 업그레이드할 때 Coworker를 사용하여 데이터 유효성 검사

>[!NOTE]
> 
>이전의 모든 업그레이드 단계를 완료한 후에만 이 페이지의 단계를 따르십시오. 대부분의 조직에 권장되는 업그레이드 단계를 따르거나(권장) Customer Journey Analytics 업그레이드 안내서를 사용하여 조직에 대해 동적으로 생성되는 단계를 따를 수 있습니다. <ul><li>**권장 업그레이드 단계**(대부분의 조직에 권장)<p>이상적인 Customer Journey Analytics 구현으로 이어지는 일련의 단계입니다.</p><p>자세한 내용은 [Adobe Analytics에서 Customer Journey Analytics으로 업그레이드](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/cja-upgrade-recommendations)를 참조하십시오.</p></li><li>**Customer Journey Analytics 업그레이드 안내서**(조직의 특정 요구 사항에 맞는 사용자 지정 단계)<p>조직 및 고유한 환경에 맞게 조정된 업그레이드 단계를 동적으로 생성하는 새로운 업그레이드 가이드를 사용할 수 있습니다.</p><p>Customer Journey Analytics에서 가이드에 액세스하려면 **[!UICONTROL Workspace]** 탭을 선택한 다음 왼쪽 패널에서 **[!UICONTROL Customer Journey Analytics으로 업그레이드]**&#x200B;를 선택합니다. 화면에 표시되는 안내를 따릅니다.</p></li></ul>

CX Enterprise Coworker에는 Adobe Analytics에서 Customer Journey Analytics으로 업그레이드할 때 데이터의 유효성을 검사할 수 있는 유효성 검사 기술이 포함되어 있습니다. 데이터 유효성 검사는 단일 대화 내에서 완료됩니다.

이 스킬은 다음을 자동으로 비교합니다.

* 각 차원, 지표 및 트렌드는 구현 간에 개별적으로 표시됩니다.

* 모든 Adobe Analytics 데이터 보기에 대한 모든 Customer Journey Analytics 보고서 세트입니다.

이러한 비교를 수행한 후 이 기술은 Customer Journey Analytics으로 쉽게 업그레이드할 수 있도록 구현할 수 있는 AI 기반 인사이트와 권장 사항을 생성합니다.

## 시작하기에 앞서



업그레이드의 일부로 데이터의 유효성을 검사하려면 다음을 수행해야 합니다.

* 유효성을 검사할 Adobe Analytics 보고서 세트입니다.

* 동일한 데이터가 포함된 Customer Journey Analytics 데이터 보기.

구현이 어떻게 설계되었는지 알 필요가 없습니다. 이 기술은 Customer Journey Analytics 구현에서 Analytics Source 커넥터를 사용하는지 또는 Experience Platform Web SDK의 새 구현을 사용하는지 자동으로 감지합니다.

## 유효성 검사 세션 시작

1. CX Enterprise Coworker에 로그인합니다.

1. [!UICONTROL **새 채팅**]&#x200B;을 선택하세요.

1. 텍스트 필드에서 에이전트에 Adobe Analytics에서 Customer Journey Analytics으로 업그레이드했는지 확인하는 메시지를 표시합니다.

   **프롬프트**

   > 회사의 Adobe Analytics에서 Customer Journey Analytics으로의 업그레이드를 확인하는 데 도움이 됩니다.

   요청이 데이터 유효성 검사 기술로 라우팅되어 대화형 설정 프로세스가 시작됩니다.

1. 설정 프로세스에는 아래 표의 질문이 포함되어 있습니다. 각 질문에 대한 답변을 선택한 다음 [!UICONTROL **제출**]&#x200B;을 선택합니다.

   >[!NOTE]
   >
   >이러한 선택 항목은 나중에 같은 대화에서 변경할 수 있습니다. 예를 들어, 에이전트에게 보고서 세트나 데이터 보기를 변경하도록 요청하면 에이전트는 전체 설정 프로세스를 다시 시작하지 않고 해당 선택을 업데이트하는 데 필요한 단계만 반복합니다.

   | 질문 | 추가 컨텍스트 |
   |---------|----------|
   | [!UICONTROL **Analytics 회사 선택**] | Adobe Analytics 로그인 회사입니다. |
   | [!UICONTROL **보고서 세트 선택**] <!--In the UI, recommend change to "Select your Adobe Analytics report suite"--> | Customer Journey Analytics 데이터에 대해 확인하려는 데이터가 포함된 Adobe Analytics의 보고서 세트입니다. |
   | [!UICONTROL **Customer Journey Analytics 데이터 보기 선택**] | 선택한 Adobe Analytics 보고서 세트와 동일한 데이터를 포함하는 Customer Journey Analytics의 데이터 보기입니다. |

1. 계속하기 전에 설정 요약을 검토하여 올바른 데이터의 유효성을 검사하고 있는지 확인하십시오. 요약에는 각 시스템의 상위 지표 및 차원에 대한 미리 보기와 함께 선택한 회사, 보고서 세트 및 데이터 보기가 포함됩니다.

1. 다음 섹션을 계속합니다. [확인할 데이터를 선택하십시오](#choose-the-data-to-validate).

## 확인할 데이터 선택

개별 지표 또는 차원의 유효성을 검사하거나 보고서 세트 및 데이터 보기에 포함된 모든 지표 및 차원의 유효성을 검사할 수 있습니다.

1. 다음 옵션 중에서 선택합니다.

   | 유효성 검사 옵션 | 설명 |
   |---------|----------|
   | [!UICONTROL **단일 지표 비교**] | Adobe Analytics과 Customer Journey Analytics 간의 한 지표의 트렌드를 비교합니다. 페이지 보기 수 또는 방문 수와 같은 특정 지표에 대해 빠른 검사를 원하는 경우 사용하십시오. |
   | [!UICONTROL **단일 차원 비교**] | Adobe Analytics과 Customer Journey Analytics 간의 단일 차원 분류를 비교합니다. 특정 차원에 대한 매핑 또는 분류 차이가 의심되는 경우 사용합니다. |
   | [!UICONTROL **전체 보고서 세트 및 데이터 보기 감사**] | 한 번의 실행으로 최대 40개의 Adobe Analytics 지표 및 20개의 차원을 Customer Journey Analytics의 해당 차원과 비교합니다. 업그레이드의 전체 상태를 종합적으로 보려는 경우 사용하십시오. |

1. 다음 섹션을 계속합니다. [분석을 검토합니다](#review-the-analysis).

## 분석 검토

1. [!UICONTROL **전체 일치율**] 탭을 선택하여 Adobe Analytics 보고서 세트의 데이터가 Customer Journey Analytics 데이터 보기의 데이터와 얼마나 가깝게 일치하는지 나타내는 백분율을 확인합니다. 이 점수는 항상 다른 결과보다 먼저 나타납니다. 페이지 보기 수와 같은 대량 지표가 점수를 왜곡하지 않도록 비교되는 모든 지표와 차원의 가중치를 동일하게 부여합니다.

   다음 척도를 사용하여 점수를 해석합니다.

   | 점수 | 등급 | 의미 |
   |---------|----------|----------|
   | 97%-100% | ![녹색 사각형](./images/data-validation-aa-cja/excellent-square.svg) [!UICONTROL 훌륭함] | 모든 속성은 고도로 정렬되어 있습니다. 필요한 작업이 없습니다. |
   | 90%-96% | ![노란색 원](./images/data-validation-aa-cja/good-circle.svg) [!UICONTROL 양호] | 약간의 간격이 있습니다. 트렌드를 모니터링하고 감소 여부를 조사합니다. |
   | 75%-89% | ![주황색 원](./images/data-validation-aa-cja/review-circle.svg) [!UICONTROL 검토] | 의미 있는 격차가 존재합니다. Customer Journey Analytics 데이터에 의존하기 전에 근본 원인을 조사합니다. |
   | 75% 미만 | ![빨간색 원](./images/data-validation-aa-cja/critical-circle.svg) [!UICONTROL 부족] | 심각한 오정렬. Customer Journey Analytics 데이터를 사용하기 전에 즉각적인 조치를 취하십시오. |

1. 분석 결과 하나를 한 문장으로 요약한 짧은 콜아웃 상자를 2~4개 보려면 [!UICONTROL **주요 인사이트**] 탭을 선택하십시오. 설명선은 심각도별로 색상 코딩되므로 가장 중요한 결과를 먼저 발견할 수 있습니다.

1. [!UICONTROL **요약**] 탭을 선택하여 Adobe Analytics 합계, Customer Journey Analytics 합계, 총 차이, 합격 일수 및 중요 일수를 확인합니다. 여기서 합격 일수 및 중요 일수는 날짜 범위의 며칠이 아래 설명된 [!UICONTROL **합격**] 및 [!UICONTROL **중요**] 분산 상태에 해당하는지 반영합니다.

1. (조건부) 단일 차원 비교 또는 단일 지표 비교를 수행할 때 [!UICONTROL **일별 트렌드**] 탭에서 Adobe Analytics 데이터와 Customer Journey Analytics 데이터의 병렬 비교를 볼 수 있습니다.

   지표의 경우 일별 트렌드를 비교하는 선 차트입니다.

   ![꺾은선형 차트를 표시하는 일별 트렌드 탭](./images/data-validation-aa-cja/trend-line.png)

   차원의 경우 상위 값을 비교하는 막대 차트입니다.

   ![가로 막대형 차트를 표시하는 일별 트렌드 탭](./images/data-validation-aa-cja/trend-bar.png)

1. (조건부) 단일 차원 비교 또는 단일 지표 비교를 수행할 때 [!UICONTROL **날짜 세부 정보**] 탭에서 행 수준 세부 정보를 볼 수 있습니다. 이 표에는 비교된 각 지표 또는 차원 값에 대한 날짜, Adobe Analytics 값, Customer Journey Analytics 값, 차이 백분율 및 상태 배지가 나열되어 있습니다.

   ![변량 백분율 및 상태 배지 테이블을 표시하는 날짜 세부 정보 탭](./images/data-validation-aa-cja/date-detail.png)

   차이 및 상태 열에는 다음 배율이 사용됩니다.

   | 분산 | 상태 | 의미 |
   |---------|----------|----------|
   | 3% 미만 | ![녹색 확인 표시](./images/data-validation-aa-cja/pass-check.svg) [!UICONTROL 통과] | 데이터가 잘 정렬되어 있습니다. 필요한 작업이 없습니다. |
   | 3%-10% | ![노란색 경고 삼각형](./images/data-validation-aa-cja/flagged-warning.svg) [!UICONTROL 플래그] | 차이를 모니터링하고 지속되거나 악화되는지 조사합니다. |
   | 10% 이상 | ![빨간색 원](./images/data-validation-aa-cja/critical-circle.svg) [!UICONTROL 중요] | 즉시 조사하라 이는 일반적으로 스키마, 수집 또는 매핑 문제를 가리킵니다. |

1. (조건부) 전체 보고서 세트 및 데이터 보기 감사를 실행할 때 [!UICONTROL **일별 트렌드**] 및 [!UICONTROL **일별 세부 정보**] 탭은 합격, 플래그 지정 및 중요 카운트를 표시하는 스코어카드와 함께 가장 일치하는 상위 5개 지표 및 가장 일치하는 상위 5개 지표 및 차원을 나열하는 별도의 테이블로 바뀝니다.

1. 분석에서 아래로 스크롤하여 추가 패턴 및 분석 중에 발견된 문제, 이러한 패턴의 가능한 원인 및 데이터 불일치를 해결하기 위해 취할 수 있는 제안된 작업을 확인합니다.

   >[!NOTE]
   >
   >약간의 차이가 예상되며 Customer Journey Analytics으로의 업그레이드에 문제가 있음을 나타내지는 않습니다.

   일반적인 문제는 다음과 같습니다.

   * Adobe Analytics은 장치 기반 방문자를 계산하지만 Customer Journey Analytics은 장치 간 ID 결합을 사용하여 사람을 계산합니다.
   * Adobe Analytics은 수집 시간에 데이터를 처리하는 반면, Customer Journey Analytics은 보고서 시간에 데이터를 처리합니다.
   * 세션 정의는 다릅니다. Adobe Analytics 방문에서는 고정된 시간 제한을 사용하는 반면 Customer Journey Analytics 세션은 구성할 수 있습니다.
   * Adobe Analytics은 기본적으로 보트를 필터링하지만 Customer Journey Analytics 보트 필터링은 옵트인입니다.
   * Adobe Analytics은 누락된 값을 &quot;지정되지 않음&quot; 또는 &quot;없음&quot;으로 보고하고 Customer Journey Analytics은 &quot;값 없음&quot;으로 보고합니다.
   * 마케팅 채널 차이는 소급하여 적용된 Adobe Analytics 파생 필드와 비교되는 Customer Journey Analytics 처리 규칙으로 인해 발생할 수 있습니다.
   * Customer Journey Analytics 값이 모든 지표에서 일관되게 Adobe Analytics 값의 약 두 배인 경우, 이는 일반적으로 ID 결합 효과가 아니라 데이터 보기에 중복 데이터를 나타냅니다.

1. 제안된 작업이 유효한지 확인한 다음 Adobe Experience Platform 또는 Adobe Analytics에서 해결하십시오.

1. (선택 사항) [확인할 데이터 선택](#choose-the-data-to-validate)에 설명된 대로 다른 지표를 분석하거나 다른 차원을 분석하거나 최대 40개의 지표와 20개의 차원으로 구성된 다른 보고서를 실행하여 분석을 계속합니다. 회사, 보고서 세트 및 데이터 보기 선택 사항이 대화 전체에서 수행되도록 설정 프로세스를 반복할 필요는 없습니다.

1. Customer Journey Analytics 업그레이드 가이드의 [권장 업그레이드 단계](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/cja-upgrade-recommendations#recommended-upgrade-steps-for-most-organizations) 또는 동적으로 생성된 업그레이드 단계를 계속 수행합니다. Customer Journey Analytics에서 가이드에 액세스하려면 **[!UICONTROL Workspace]** 탭을 선택한 다음 왼쪽 패널에서 **[!UICONTROL Customer Journey Analytics으로 업그레이드]**&#x200B;를 선택합니다. 화면에 표시되는 안내를 따릅니다.

