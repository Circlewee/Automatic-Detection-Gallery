# ADG  <img src=https://user-images.githubusercontent.com/65718183/139021701-1237017a-2601-44ae-9c9b-8a972203e504.png width="40" height="40"/>  
#### 2021 상명대학교 캡스톤디자인 경진대회 융합공과대학 우수상 수상  
Automatic Detection Gallery  

___
## 팀원 소개
박노준 : 팀장 및 데이터셋 구성  
박건우 : 메인 앱 개발  
이현민 : 데이터셋 구성 및 학습  
정은진 : 데이터셋 구성 및 앱 개발 도움  

------------
## 프로젝트 소개
태그 기반의 검색으로 원하는 사진을 빠르게 찾을 수 있고, 사용자의 태그 **Customizing**이 가능한 갤러리 앱  
- Auto Tagging
- Fast Searching
- Tag Customizing
- Real-time Detection
------------
## 시스템 구성
![image](https://user-images.githubusercontent.com/67961082/139584477-815578a9-8384-44b7-8295-f8ac8e7e2dee.png)

------------
## Dataset
- LVIS Dataset
- Place365 Dataset
- Food Dataset  
　　&#43;
- Google image Crawling  

-> 330개 이상의 classes &#43; 100000장 이상의 train images

------------
## Model
1. Dataset 가공
    + 수집한 Dataset은 LabelImg프로그램을 이용해 Bounding Box를 지정하여 라벨링 수행
    
2. 모델링
    + Yolov4 Darknet을 이용해 모델 생성
 
3. 학습
    + 학습 진행을 위해 yolov4_train.cfg파일을 아래와 같이 설정
        + batch: 64
        + subdivisions: 32
        + width, height: 416
        + max_batches: 660000
        + steps: 528000, 594000
        + mosaic: 1
        + classes: 330
        + filters: 1005
4. tflite로 변환
    + 안드로이드 프로젝트에 모델을 탑재하기 위해 .weight 파일을 .tfilte로 변환  <img src=https://user-images.githubusercontent.com/65718183/139207444-6cb59556-e8a7-46f7-b20d-f75e08ec28f4.JPG width="900" height="180"/>
    
    
- Github의 파일 업로드 크기 제한으로 인해 앱 소스 코드에 포함되지 않았습니다. 다음 [링크](https://drive.google.com/file/d/1aibqzVww5qQXNbhwtmWB165RQ6TrCdy7/view?usp=sharing)에서 다운로드한 모델을 app/src/main/assets에 추가하면 정상 작동합니다.
