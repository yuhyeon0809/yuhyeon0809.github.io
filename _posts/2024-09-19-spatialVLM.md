---
title: "SpatialVLM: Endowing Vision-Language Models with Spatial Reasoning Capabilities 리뷰"
excerpt: "공간을 이해하는 VLM, 구글의 SpatialVLM을 리뷰합니다."

categories: 
  - paper-review
# tags: 
#   - [tag1, tag2]

permalink: /paper-review/spatialvlm/ 

toc: true
toc_sticky: true
---

[https://arxiv.org/abs/2401.12168](https://arxiv.org/abs/2401.12168){:target="_blank"}

<img width="655" alt="spatialvlm_main" src="https://github.com/user-attachments/assets/d50aa137-99b0-44a9-bf81-6cddbe103315">

## Intro
<!-- 간략한 소개 -->
```
- 최신 VLM들의 general task 성능 좋다.
- 이를 real-world에 적용하면? 잘 못 하는 예시
- 왜 그럴까? spatial reasoning 능력 부족하기 때문이다.
```
하루가 다르게 발전하고 있는 멀티모달 모델, 그 근간에 VLM이 있습니다. GPT-4o, Gemini-1.5 Pro, Claude 3.5 sonnet 등 최신 VLM 모델을 써 보았다면 알겠지만, Image Captioning이나 VQA 같은 전통적인 VLM 태스크에서는 아주 좋은 성능을 보입니다. 시각적 요소를 잘 잡아내어, 자연스러운 문맥을 생성해내죠. 

그런데, 이들에게 실제 세계에서의 작업을 시키면 어떻게 될까요? 예를 들어, '사진 속 공간에서 소파와 테이블 사이를 1m 너비의 로봇 청소기가 지나갈 수 있을까?'라는 요청을 받으면, GPT-4V는 이렇게 대답한다고 합니다.   

```
🤖 저는 AI이기 때문에 물리적으로 환경과 상호작용할 수는 없지만, 제공된 이미지를 바탕으로 몇 가지 통찰을 제공할 수 있습니다. 이미지에서 시각적인 추정을 할 수 있는데, 소파와 테이블이 매우 가까이 있어 보이며, 1미터 너비의 로봇이 들어갈 만한 충분한 공간이 없을 수도 있을 것 같습니다. 
```  
이렇게 애매한 답변을 내뱉는 VLM으로 과연 실제 로봇을 제어할 수 있을까요? 물체의 크기와 거리를 계산하지 못하고 이리저리 부딪힐 게 뻔합니다. 비싼 로봇이 금방 망가지겠죠. 

사실 GPT-4V가 위와 같은 질문에 애매한 답변을 내놓는 데에는 이유가 있습니다. 바로 **Spatial Reasoning(공간적 추론) 능력**이 부족하기 때문인데요. 2024년 1월, Google Deepmind의 연구진이 이 문제를 해결하고자 수행한 연구인 SpatialVLM을 소개합니다. Spatial Reasoning이 무엇이고, 이를 어떻게 VLM에 탑재할 수 있었을까요? 

## Spatial Reasoning이란?

```
- spatial reasoning이란 이런 능력을 말한다.
- 로보틱스, AR/VR 태스크에 있어 중요하다. (물리 세계의 물체들 간 거리, 크기 등을 추정할 수 있게 해주므로)
- 그렇다면 기존 VLM의 spatial reasoning 능력이 떨어졌던 원인은?
- 훈련 데이터에 Spatial knowledge가 포함되어 있지 않았기 때문이다.
- 이러한 맥락에서, SpatialVLM을 제안한다. 즉, spatial reasoning을 위한 데이터로 학습되어 general+spatial task를 모두 수행할 수 있는 VLM
```

## Data Generation Pipeline for Spatial Reasoning

```
- 좋은 공간 추론 능력을 얻기 위해서는 우선 양질의 데이터셋이 필요하다.
```


  
  

## Outro


