# Project
**군집분석을 활용한 고객 분류 및 맞춤형 상품 추천**

<br/>

## 1. 배경 & 목적
 
- 고객의 구매 데이터를 활용하여 고객을 여러 그룹으로 구분
- 각 그룹에 따라 적절한 마케팅 기법을 제안하고자 함
- 이를 통한 매출 극대화가 목표

<br/>

## 2. 프로젝트 기간

- 2020.04 ~ 2020.06

<br/>

## 3. 고객 세분화

데이터 전처리를 통해 생성된 변수들을 통해 KMeans 기법을 수행 
총 33개의 변수 중 상관관계가 높은 변수 및 범주형 데이터를 제거, 총 20개의 변수를 이용하여 군집분석 실시  

![image](https://github.com/KiSeoupShin/Project/assets/108209592/7bd0a29c-4af1-4d9c-a613-57a83619a4e0)

<br/>

#### 고객 세분화 결과
![image](https://github.com/KiSeoupShin/Project/assets/108209592/c04b4fe8-bfb1-430d-934f-94ab2e0e93a9)

총 5개의 그룹으로 구분되었으며, 각각 그룹에 대한 특징들은 다음과 같다
1. Main Group
2. Potential Main Group
3. Fashion & Cosmetics Group
4. Useful Group
5. Cheap & Many Group

<br/>

#### 그룹 별 추천 상품 목록
![image](https://github.com/KiSeoupShin/Project/assets/108209592/7ce88b3f-e162-4692-be62-344b6d9778b3)

<br/>

## 4. 그룹 별 마케팅 방안
#### 1. Main Group
![image](https://github.com/KiSeoupShin/Project/assets/108209592/4595d697-3acc-479d-a11c-4d46759c6b01)

특징
- 구매액 표준편차가 매우 큼
- 구매 건수가 전체 그룹 중 2위이고, 최대 구매액은 1위를 차지

제안 방안
- 구매액 표준편차가 크다는 것은 가격대를 크게 고려하지 않는다는 것이기 때문에 많은 방문을 유도하는 것이 중요
- 해당 그룹은 오프라인 방문비율이 약 61%로 매우 높기 때문에 매장에 특별한 공간을 마련해 혜택을 제공

<br/>

#### 2. Potential Main Group
![image](https://github.com/KiSeoupShin/Project/assets/108209592/bd64cb34-3e8a-42b8-bf3d-38c218849d9a)


특징
- 평균 구매액은 적지만 방문 횟수가 높아 총 구매액이 높은 편
- Main Group과 유사한 형태를 보이지만 고가 상품을 구매하지 않음

제안 방안
- 해당 그룹에 속한 고객들은 main group으로 이동할 확률이 가장 높기 때문에 고가 상품 구매 유도를 위해 고가 상품 전용 할인 쿠폰 증정
- 더 많은 방문을 유도하기 위해 몇 회 이상 방문 시 사은품을 증정하는 이벤트 개최

<br/>

#### 3. Fashion & Cosmetics Group
![image](https://github.com/KiSeoupShin/Project/assets/108209592/bd64cb34-3e8a-42b8-bf3d-38c218849d9a)


특징
- 평균 구매액은 적지만 방문 횟수가 높아 총 구매액이 높은 편
- Main Group과 유사한 형태를 보이지만 고가 상품을 구매하지 않음

제안 방안
- 해당 그룹에 속한 고객들은 main group으로 이동할 확률이 가장 높기 때문에 고가 상품 구매 유도를 위해 고가 상품 전용 할인 쿠폰 증정
- 더 많은 방문을 유도하기 위해 몇 회 이상 방문 시 사은품을 증정하는 이벤트 개최

<br/>

