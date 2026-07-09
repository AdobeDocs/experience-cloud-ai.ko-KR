---
title: Adobe Analytics에서 Customer Journey Analytics으로 업그레이드할 때 Coworker를 사용하여 데이터 유효성 검사
description: Analytics 관리자가 CX Enterprise Coworker 데이터 유효성 검사 기술을 사용하여 마이그레이션 도중 Adobe Analytics 및 Customer Journey Analytics 데이터를 비교하는 방법에 대해 알아봅니다.
hold: true
source-git-commit: 850bfef76e3c3e081f9860b9757e5e5128383f76
workflow-type: tm+mt
source-wordcount: '710'
ht-degree: 0%

---

# Adobe Analytics에서 Customer Journey Analytics으로 업그레이드할 때 Coworker를 사용하여 데이터 유효성 검사

CX Enterprise Coworker에는 Adobe Analytics에서 Customer Journey Analytics으로 업그레이드할 때 데이터의 유효성을 검사할 수 있는 유효성 검사 기술이 포함되어 있습니다. 데이터 유효성 검사는 단일 대화 내에서 완료됩니다.

이 스킬은 다음을 자동으로 비교합니다.

* 각 차원, 지표 및 트렌드는 구현 간에 개별적으로 표시됩니다.

* 모든 Adobe Analytics 데이터 보기에 대한 모든 Customer Journey Analytics 보고서 세트입니다.

이러한 비교를 수행한 후 이 기술은 Customer Journey Analytics으로 쉽게 업그레이드할 수 있도록 구현할 수 있는 AI 기반 인사이트와 권장 사항을 생성합니다.

## 시작하기에 앞서

업그레이드의 일부로 데이터의 유효성을 검사하려면 다음을 수행해야 합니다.

* 유효성을 검사할 Adobe Analytics 보고서 세트입니다.

* 동일한 데이터가 포함된 Customer Journey Analytics 데이터 보기.

구현을 미리 설계할 필요가 없습니다. 이 기술은 데이터가 Analytics 소스 커넥터를 통해 매핑되는지 또는 두 개의 병렬 구현을 통해 매핑되는지를 자동으로 감지하므로 해당 컨텍스트를 직접 제공할 필요가 없습니다.

## 유효성 검사 세션 시작

1. CX Enterprise Coworker에 로그인합니다.

1. [!UICONTROL **새 채팅**]&#x200B;을 선택하세요.

1. 텍스트 필드에서 에이전트에게 Adobe Analytics에서 Customer Journey Analytics으로 마이그레이션의 유효성을 검사하라는 메시지를 표시합니다.

   **프롬프트**

   > 회사의 Adobe Analytics에서 Customer Journey Analytics으로의 업그레이드를 확인하는 데 도움이 됩니다.

   요청이 데이터 유효성 검사 기술로 라우팅되어 대화형 설정 프로세스가 시작됩니다.

1. 설정 프로세스에는 아래 표의 질문이 포함되어 있습니다. 각 질문에 대한 답변을 선택한 다음 [!UICONTROL **제출**]&#x200B;을 선택합니다.

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
   | [!UICONTROL **전체 보고서 세트 및 데이터 보기 감사**] | 한 번의 실행으로 최대 20개의 지표와 차원을 비교할 수 있습니다. 마이그레이션의 전체 상태를 종합적으로 보려는 경우 사용합니다. |

1. 다음 섹션을 계속합니다. [분석을 검토합니다](#review-the-analysis).

## 분석 검토

1. 분석을 검토하려면 다음 탭을 각각 선택하십시오.

   | 분석 검토 탭 | 설명 |
   |---------|----------|
   | [!UICONTROL **전체 일치율**] | Adobe Analytics 보고서 세트의 데이터가 Customer Journey Analytics 데이터 보기의 데이터와 일치하는 정도를 나타내는 백분율입니다. |
   | [!UICONTROL **주요 인사이트**] | 분석 중에 발견된 주요 인사이트. |
   | [!UICONTROL **요약**] | Adobe Analytics 합계, Customer Journey Analytics 합계, 총 차이, 합격 일수 및 중요 일수. <!--what are these?--> |
   | [!UICONTROL **일별 트렌드**] | Adobe Analytics 데이터와 Customer Journey Analytics 데이터의 병렬 비교를 보여 주는 그래프입니다. |
   | [!UICONTROL **일별 세부 정보**] | <!--what goes here?--> |

1. 분석 중에 발견된 추가 패턴, 해당 패턴의 가능한 원인 및 데이터 불일치를 해결하기 위해 취할 수 있는 제안된 작업을 보려면 분석에서 아래로 스크롤하십시오.

1. 제안된 작업이 유효한지 확인한 다음 Adobe Experience Platform 또는 Adobe Analytics에서 해결하십시오.

1. (선택 사항) [확인할 데이터 선택](#choose-the-data-to-validate)에 설명된 대로 다른 지표를 분석하거나 다른 차원을 분석하거나 최대 20개의 지표 및 차원으로 구성된 다른 보고서를 실행하여 분석을 계속합니다.

