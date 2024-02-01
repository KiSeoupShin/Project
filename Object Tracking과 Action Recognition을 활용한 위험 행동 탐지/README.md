# Project
**Object Tracking과 Action Recognition을 활용한 매장 내 위험 행동 탐지**

<br/>

## 1. 배경 & 목적
 
- 최근 무인 매장이 많이 늘어나면서 절도나 파손과 관련된 문제가 많이 발생
- 또한, 매장 내에서 폭력이나 위험 행동이 많이 일어나고 있음
- CCTV 녹화와 동시에 위험 행동을 탐지할 수 있도록 하여 피해를 최소화 하고자 한다

<br/>

## 2. 프로젝트 기간

- 2023.09 ~ 2023.12

<br/>

## 3. Model FLow

![image](https://github.com/KiSeoupShin/Project/assets/108209592/6ef550a8-abbb-415a-b6af-95aa40867157)


<br/>

전체적인 모델 구조는 다음과 같다.
1. 매장 내 CCTV가 매장 내의 영상을 실시간으로 촬영
2. OC-SORT 모델을 활용해 매장 내 존재하는 사람들의 경로 및 모습을 Tracking
3. Tracking과 동시에 5초 단위로 Action Recognition 모델인 TubeViT를 활용해 어떤 행동을 하고 있는지 탐지
4. 만약, 위험 행동으로 분류된 행동이 감지되면 알람이 울리도록 설정

<br/>

## 4. Dataset

### OC-SORT

![image](https://github.com/KiSeoupShin/Project/assets/108209592/2a3440aa-a7ed-4f37-93f2-073916df5e99)

<br/>

### TubeViT
- AIHub 실내(편의점, 매장) 사람 이상행동 데이터
- AIHub 실내(편의점, 매장) 사람 구매행동 데이터
- 위 데이터 중 이상행동 3가지(흡연, 파손, 폭행), 정상행동 2가지(매장 이동, 구매)로 총 5 class 구성

<br/>

![image](https://github.com/KiSeoupShin/Project/assets/108209592/0799d3dd-b2e1-4dfd-b740-8ef634493b90)

<br/>

## 5. 데이터 전처리

### AIHub Data
- 사람의 행동에 집중하고자 Tracking을 통해 객체를 crop하여 영상 추출
- 영상 frame 수를 32 frame으로 고정 (모델의 입력과 맞춰주기 위함)

![image](https://github.com/KiSeoupShin/Project/assets/108209592/eb33ad88-4eb2-41b6-9a5a-31d166ce4030)

<br/>

## 6. Experiment

![image](https://github.com/KiSeoupShin/Project/assets/108209592/99325e0b-585c-432f-9ccc-d8c7ce347e63)

<br/>

## 7. 한계점 및 발전방향
1. 학습에 사용한 영상 데이터 수가 적음 -> 더 많은 양의 데이터로 학습 시킨다면 성능이 올라갈 것으로 기대
2. Tracking을 통해 영상 속에서 객체만 crop한 추출한 영상에서, frame 마다 비율이 달라지는 문제
