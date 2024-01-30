## Project
**LSTM을 활용한 유튜브 댓글 분석**

<br/>

## 1. 분석 배경 및 목적
- 핸드폰 혹은 전자기기를 구매할 때 가장 큰 고민은 갤럭시 vs 애플이다
- 이런 고민을 해결하기 위해 주로 Youtube 리뷰 영상을 참고하게 되는데, 이때 각 회사 별로 리뷰에 대한 댓글 반응이 어떤지를 알아보고자 한다
- keyword는 '갤럭시 리뷰', '애플 리뷰'

<br/>

## 2. 데이터 수집
- Selenium과 BeautifulSoup을 통해 유튜브 댓글을 수집하였음

#### 수집 과정
1. 앞서 지정한 keyword를 유튜브 검색 창에 입력
2. 그 후, 스크롤을 내려가며 약 50여개의 유튜브 영상 링크를 추출(이때 shorts 영상은 제외)
3. 추출한 영상에 하나씩 접속하여 유튜브 '더보기' 클릭
4. 영상의 채널명, 구독자수, 조회수, 댓글수, 댓글을 dataframe에 저장

<br/>

## 3. 데이터 전처리
<img src="https://github.com/KiSeoupShin/Project/assets/108209592/60a70e61-cfe1-494c-8e59-0ffbe841e327" width="1000" height="450"/>

<br/>

<img src="https://github.com/KiSeoupShin/Project/assets/108209592/c3b390f4-0edd-4b2e-a107-4a347a0c2aa0" width="1000" height="500"/>

<br/>

<img src="https://github.com/KiSeoupShin/Project/assets/108209592/2a84a415-1f99-4cc3-b895-60693f4b2d6b" width="1000" height="350"/>

<br/>

<img src="https://github.com/KiSeoupShin/Project/assets/108209592/c43bdc44-a3dc-4ce7-bbd9-a97ded6c14af" width="1000" height="500"/>

<br/>

<img src="https://github.com/KiSeoupShin/Project/assets/108209592/ede3b3ed-55f5-4cfe-bd1c-6f29c1c716c2" width="1000" height="500"/>

<br/>

<img src="https://github.com/KiSeoupShin/Project/assets/108209592/1170d698-48ed-462e-b501-0efd7ba78ef7" width="1000" height="450"/>

<br/>

<img src="https://github.com/KiSeoupShin/Project/assets/108209592/e75f3ba1-7a4a-4c55-87c6-8f0578cd2a8b" width="1000" height="450"/>

<br/>

## 4. 워드클라우드 생성
1. stopwords를 재정의하여 댓글에 자주 등장하지만 의미없는 단어들을 삭제 처리
2. 또한, 워드클라우드에서는 접속사와 같은 품사는 의미가 없기 때문에 필요한 품사만을 사용

### 갤럭시
![image](https://github.com/KiSeoupShin/Project/assets/108209592/8dff27e6-99ae-4582-a988-efa3c31a403a)

<br/>

### 애플
![image](https://github.com/KiSeoupShin/Project/assets/108209592/ea563c7d-9583-4839-b34b-98feaa81d3c2)

<br/>

## 5. Text Classification
- LSTM을 활용하여 특정 댓글이 들어왔을 때 해당 댓글은 애플의 리뷰인지 혹은 갤럭시의 리뷰인지를 분류하는 모델 생성

### 최종 loss & 정확도
![image](https://github.com/KiSeoupShin/Project/assets/108209592/8f5b58ae-a771-4dc5-9445-be2119f6389c)

![image](https://github.com/KiSeoupShin/Project/assets/108209592/fefbc561-fa3d-466d-8df2-16860043e0e2)

<br/>

## 6. 결론 및 발전 방향성
### 결론
- 데이터의 구성이 갤럭시 2, 애플 1로 구성되어 있어 대부분 갤럭시로 분류되었다
- 또한, 대부분의 댓글이 특정 회사의 제품만을 이야기하는 것이 아닌 두 회사를 비교하는 댓글이 많아 분류에는 어려움이 있었다
- 두 클래스를 가장 잘 구분하는 단어로는 '워치', 'S23'과 같은 단어였다

### 발전 방향성  
- 유튜브 댓글은 데이터 생성 속도가 매우 빠르기 때문에 다량의 데이터를 수집하는 데에는 큰 문제가 없을 것 같아 꾸준히 프로젝트를 진행하면 더욱 높은 정확도를 얻을 수 있을 것이다
- 또한, LSTM 모델이 아닌 Transformer 기반 모델을 활용한다면 더 높은 정확도가 나올 것으로 기대
