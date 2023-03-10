---
layout: post
title: "[비전 시스템을 위한 딥러닝] chapter1 정리"
description: >
  책 [비전 시스템을 위한 딥러닝]을 읽고 정리한 내용입니다. 
sitemap: false
hide_last_modified: true

data: 2023-01-09
last_modefied_at: 2023-01-18
---

```개인공부용```

![](https://velog.velcdn.com/images/yuhyeon0809/post/691b1d04-d262-4104-9a24-6a749aa77010/image.png)



책 '비전 시스템을 위한 딥러닝'을 읽고 정리한 내용입니다. 

## Part1 딥러닝 기초

## Chapter1 컴퓨터 비전 입문

### 1.1 컴퓨터 비전
#### 컴퓨터 비전이란?
모든 인공지능 시스템을 관통하는 핵심 개념은 기계가 자신이 처한 환경을 스스로 **인식**하고, 그에 맞게 조치를 취할 수 있다는 것이다. 그렇다면 인공지능은 무엇을 **인식**할까? 텍스트가 될 수도 있고, 이미지나 영상이 될 수도 있다. 물론 소리, 즉 오디오도 그 대상이 될 수 있다.  **컴퓨터 비전(Computer Vision)**은 그중에서도 **시각적 인지**를 다루는 인공지능 분야이다. 
 <!--
#### 시각적 인지(Visual Perception)
- 시야나 시각적 입력으로 패턴을 관찰하는 행위
- 패턴을 관찰한다는 것은, 예를 들어 자율주행차의 경우 보행자 또는 차량이 주행 중인 차선, 신호등의 상태와 신호의 의미 등 주변에 위치한 사물과 그 상태를 이해하는 것
- 시각적 인지를 갖추기 위해서는 주변 환경을 단순히 '스캔'하는 것에서 나아가 주변을 실질적으로 인식해야 한다. 

#### 비전 시스템
- 전통적 이미지 처리를 넘어 이미지를 이해하고 이미지에 담긴 내용을 해석해야 함
- 사람의 시각 시스템 
  - 시각 센서: 눈, 해석 시스템: 뇌
  - 우리는 오랫동안 훈련된 시각 시스템을 가지고 일상 생활을 하며 들어온 시각 정보를 해석하고 처리할 수 있다. 
  - 그러나 컴퓨터는 하나의 사물을 구별하기 위해 적어도 수천장에서 많게는 수백만 장의 사진을 학습해야 한다. 
- 인공지능의 비전 시스템
  - 인간의 시각 시스템에서 착안
  - 시각 센서 : 감지 장치, 해석 및 분류 : 알고리즘
  
#### 감지 장치
- 시스템이 처한 주변 환경을 가장 잘 파악할 수 있는 감지 장치 선택이 중요
- 자율주행차의 경우 감지 장치로 라이다, 카메라, 레이다가 있고, 
- 의학 진단 영역에는 x-ray 또는 CT 촬영 기기가 있다. 
- 알맞은 감지 장치를 선택하기 위해 해당 시각 시스템의 목적 파악이 우선

#### 해석 장치
- 감지 장치에서 출력한 이미지를 입력 받아 특징과 패턴을 학습할 수 있는 '뇌' 역할 장치가 필요하며, 그 역할을 보통 컴퓨터 비전 알고리즘이 담당한다. 
- 이에 사람의 뇌로부터 영감을 받아 만들어진 것이 인공신경망(artificial neural network)
- 인공신경망은 실제 생물학적 뉴런과 비슷하게 기능한다. 뉴런을 주 처리 단위로 삼아 입력을 받고 출력을 내보낸다. 
- 하지만 뉴런 하나로는 '뇌' 역할을 하기에 역부족
- 결과적으로 수백만 개의 뉴런을 모아 여러층을 가진 네트워크를 만드는 기법이 사용되고 있고, 이것이 딥러닝이다. 
-->
---


### 1.2 컴퓨터 비전 응용 분야
#### 이미지 분류
**이미지 분류(image classification)**란 **미리 정의된 유한한 수의 레이블(label)**을 이미지에 부여하는 task를 말한다. 널리 쓰이고 있어 한 번쯤 들어봤을 **CNN(Convolutional Neural Network)**이라고 하는 합성곱 신경망이 이미지 처리 및 분류에 많이 사용된다.  

> **이미지 분류 예시 - 폐암 진단**  
구글 AI가 환자의 CT 이미지를 분석해 폐결절의 악성 여부를 분석할 수 있는 기술을 개발했다고 한다. 기존의 폐암 진단은 CT 이미지를 의사가 육안으로 관찰해 작은 병변을 찾아내는 식으로 이루어졌는데, 여기에 딥러닝 기술을 도입해 훨씬 더 정교한 분석을 할 수 있게 된 것이다.
![](https://velog.velcdn.com/images/yuhyeon0809/post/33cf3a91-12b0-4881-9356-6e18760fdfeb/image.png)  
자료 출처: https://www.joongang.co.kr/article/23473802#home  


#### 사물 탐지와 위치 인식
- 이미지 분류는 **사물 1개**가 찍힌 이미지를 분류하는 task이다. 
- 그러나 사람과 비슷한 수준의 능력을 갖추려면 한 이미지 안에서 여러 개의 사물을 인식하고, 그 위치도 파악할 수 있어야 한다. 
- 사물 인식이 가능한 모델로 ```YOLO, SSD, Faster R-CNN``` 등이 있다. 
- 이러한 사물 인식 시스템은 입력 받은 이미지를 여러 조각으로 나눈 뒤, 각 조각에서 인식된 사물에 대한 레이블을 부여하는 방식으로 **사물 인식**과 **위치 파악**을 동시에 수행한다. 

#### 화풍 모방하기
- **neural style transfer** (신경망을 이용한 화풍 모방)
- 입력 받은 이미지에 특정 화풍을 적용해 새로운 이미지를 만들어낸다. 
> ![](https://velog.velcdn.com/images/yuhyeon0809/post/9a09be95-0565-47ad-96f4-8cc840151c65/image.png)
```출처 : https://godatadriven.com/blog/how-to-style-transfer-your-own-images/```

#### 새로운 이미지 창조하기
- 머신러닝 연구원 이안 굿펠로가 2014년에 발표한 **_생성적 적대 신경망 Generative Adverserial Network_**으로부터 고안된 딥러닝 모델 **GAN**
- GAN은 CNN을 발전시킨 모델로 딥러닝의 주요한 성취 중 하나이다. 
> GAN의 핵심은 충분히 **있을 법한**, 그러나 실제로 존재하지는 않는 이미지를 생성하는 것이다. 

![](https://velog.velcdn.com/images/yuhyeon0809/post/22559705-a941-493a-b451-22876dd2b3f8/image.png)

- ```vanilla GAN```에서부터 시작해 ```DCGAN, styleGAN``` 등 **variation**이 매우 많다. 
- 오래되지 않은 연구임에도 압도적으로 큰 성과를 거두고 있어 머신러닝 학계에서 최근 가장 주목받고 있는 연구 중 하나라고 한다. 
- GAN을 응용한 결과물은 아직까지 이미지로 한정되어 있지만, 머지 않아 다른 형태의 데이터를 생성해낼 수도 있을 것이다. 
- 따라서 곧 ai가 만들어낸 책, 음악 등을 즐길 수 있을지도...
- 텍스트 설명만으로 예술 작품이 뚝딱 만들어질 수 있다는 점이 흥미롭다. 
> 2018년 10월에 인공지능 화가 모비어스가 그린 _에드몽드 드 벨라미 Edmond de Belamy_ 가 뉴욕 크리스티 경매소에서 43만 2,500 달러(한화 5억원)에 낙찰되었다. 이 그림은 25세 프랑스 학생 세 명이 GAN을 이용해 생성한 이미지로, 에드몽드 드 벨라미라는 가상의 인물을 그린 초상화이다. 14세기부터 20세기 사이에 그려진 15,000장의 초상화를 수집한 데이터셋을 신경망에 학습시켰다고 한다. 
![](https://velog.velcdn.com/images/yuhyeon0809/post/7b593922-7ff4-46e7-9c3a-0951a1447497/image.png)
> ```출처: https://news.mt.co.kr/mtview.php?no=2018102616445477785```

#### 안면 인식
- 안면 인식 _Face Recognition_ 이란 사람의 이미지를 식별하거나 테그를 지정하는 기술이다. 
- 친구 또는 가족과 함께 찍은 사진에 자동 태깅이 되는 것도 안면 인식을 활용한 기술이다. 
- 아주 많은 레이블이 정의된 이미지 분류라고 할 수 있다. 

안면 인식 분야에서 유명한 책인 _Handbook of Face Recognition, 2nd ed_ 에 따르면, 안면 인식은 크게 두 부류로 나눌 수 있다. 

- **안면 식별 face identification** : 일대다 매칭 과정이다. 입력 받은 안면 이미지를 데이터베이스에 저장된 이미지들과 비교해 일치하는 후보를 식별한다. 
- **안면 대조 face verification** : 일대일 매칭 과정이다. 입력 받은 안면 이미지와 하나의 후보를 비교해 신원 일치 여부를 판단한다. 
> ![](https://velog.velcdn.com/images/yuhyeon0809/post/ac682cdf-8b4c-4cdf-a544-89ab776a0e5f/image.png)  



#### 이미지 추천 시스템
- 이미지 추천 시스템은 질의로 들어온 이미지와 **유사한** 이미지를 제공하는 시스템이다. 
- 쉽게 말해 **사용자 맞춤 광고**의 기반이 되는 시스템이라고 할 수 있는데, 
- 인터넷 쇼핑몰을 예로 들면, 클라이언트가 이전에 봤거나 구매했던 상품과 (이미지가) 유사한 상품을 추천하는 시스템이다.  
  
---

### 1.3 컴퓨터 비전 파이프라인 전체 처리 과정  

#### 컴퓨터 비전 파이프라인이란?  
비전 시스템이 이미지를 인식하고 분석하는 과정에도 **대략적인 흐름**이 존재한다. 데이터를 획득하고, 처리한 다음 분석 및 인식 과정을 통해 특정한 task를 수행하는 이 일련의 단계를 _**컴퓨터 비전 파이프라인 Computer Vision Pipeline**_ 이라고 한다.  
  
![](https://velog.velcdn.com/images/yuhyeon0809/post/5286cac4-9f65-4a0b-aaa3-025b559c0b4a/image.png)  



모터사이클이 찍힌 사진을 입력으로 받아 이 사진에 담긴 사물이 모터사이클, 자동차, 개 중 어느 것에 해당하는지 확률을 예측하는 분류기를 만든다고 가정하자.  

![](https://velog.velcdn.com/images/yuhyeon0809/post/73fa14eb-20cf-458b-8164-a447c546f521/image.png)

```출처 : https://freecontent.manning.com/computer-vision-pipeline-part-1-the-big-picture/```  


이 이미지는 분류 파이프라인을 통과하며 다음과 같은 과정을 거칠 것이다:
> 1. 컴퓨터가 카메라와 같은 감지 장치를 통해 이미지를 입력받는다.  
> 2. 이미지가 **전처리 과정**을 거친다. 전처리 과정에는 ```크기 조정, 흐릿하게 하기, 회전, 모양 변경, 색상 조정``` 등이 있다. 
> 3. 이미지로부터 **특징** _feature_ 을 추출한다. 특징은 사물을 식별할 수 있는 정보로, 모터사이클을 구분할 수 있게 해주는 특징은 ```바퀴, 헤드라이트, 흙받기``` 정도가 있다. **특징 벡터** _feature vector_ 가 이 단계의 출력이 된다. 
> 4. 추출된 특징을 **분류 모델** _classification model_ 에 입력한다. 여기서 입력된 특징 벡터를 보고 이미지가 속한 클래스를 예측한다. 

위 과정을 거치면 결과적으로 Classifier를 통해 이미지 속 대상이 미리 정의해 둔 각 class에 속할 확률이 출력된다. 


