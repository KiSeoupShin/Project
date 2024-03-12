## Project
**실시간 객체 탐지를 활용한 해양침적폐기물 수거 모델 개발**

<br/>

## Project 기간
2023.04 ~ 2023.06

<br/>

## 1. 분석 배경 및 목적
- 현재 해양쓰레기는 꾸준히 증가하고 있지만, 해양쓰레기 중 침적폐기물은 수거 비율이 약 13%에 불과
- 이는 수거 인력 예산안이 큰 문제
- 따라서 이를 해결하기 위해 침적폐기물을 실시간으로 탐지하는 모델을 개발하여 수중 드론에 탑재하여 수거 효율을 증대하고자 하는 것이 목표

<br/>

## 2. 데이터셋
#### AIHub 해양침적쓰레기 이미지 데이터 고도화
- 해양침적쓰레기 9종에 대한 총 111,890장의 이미지 데이터
- 수중 촬영 영상 중 일부 프레임 이미지화
![image](https://github.com/KiSeoupShin/Project/assets/108209592/51fead99-1cb5-4472-9779-87b19ac9b2b6)

<br/>

## 3. 제안 방법론
#### 문제 정의
- 데이터 구성을 보면 플라스틱이나 금속과 같이 보기 쉬운 객체들은 Bounding Box 형태로, 로프나 어망과 같은 알아보기 어려운 객체는 polygon 형태로 존재
- 따라서, 이를 동시에 탐지할 수 있는 모델 필요성 존재
- 최종 목표는 카메라 1대를 통해 detection과 segmentation을 동시에 수행하는 모델 개발
- 더 나아가, 드론이 실시간으로 탐지가 가능해야 하기 때문에 Real-Time을 목표로 개발

<br/>

#### Model Pipeline
![image](https://github.com/KiSeoupShin/Project/assets/108209592/b9a62a07-0b39-4e17-a004-1acac6c5edcb)

1. 입력이 들어오면 U-Net을 통해 Denoising을 진행
   - 수중 영상이라는 특이점으로 인해 부유물이 많아 noise를 제거하는 과정이 필요
2. DCE-Net을 활용해 Low-Light Image Enhancement 진행
   - 이 역시 수중이기에 아무리 전등을 사용한다 하더라도 밝기가 낮기 때문에 밝기 조절이 필요
3. RTMDet + CondInst를 활용해 Detection과 Segmentation을 동시에 진행

<br/>

#### 모델 세부 내용
![image](https://github.com/KiSeoupShin/Project/assets/108209592/be79bada-d86e-405f-ac55-757453c6485f)

<br/>
<br/>

![image](https://github.com/KiSeoupShin/Project/assets/108209592/c356c81b-93eb-41e4-a393-a87c6350ce94)

<br/>
<br/>

![image](https://github.com/KiSeoupShin/Project/assets/108209592/fbba7021-efc1-4422-8728-26b0f9417314)

<br/>
<br/>

![image](https://github.com/KiSeoupShin/Project/assets/108209592/a34789e2-f604-4601-9ff3-933f072aaa13)

<br/>
<br/>

![image](https://github.com/KiSeoupShin/Project/assets/108209592/f4425bd1-84a2-47cc-9dd9-354c1b08778d)

<br/>
<br/>

## 4. 결론 및 한계
#### 결론
1. 데이터에 특화된 전처리를 진행하면서 데이터의 품질 향상
2. 기존 연구 대비 성능 향상 기대
3. 수중 로봇에 실제로 탑재하면 저렴한 비용을 쓰레기 수거가 가능할 것으로 기대

<br/>

#### 한계
1. 수중 영상이기 때문에 이미지 왜곡 존재 가능
2. 모델 pipeline에 있어서 투입되는 모델이 너무 많아 실제 inference 속도가 어떻게 될지 장담 불가

<br/>

#### 코드는 추후 개발 예정
