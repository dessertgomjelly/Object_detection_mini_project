# 🏀 객체 검출 프로젝트: 농구 경기 분석
- Object detection의 핵심 원리를 이해한 후, 이를 기반으로한 개인 프로젝트를 수행하였습니다.

<Br>


## [배경]
- 농구 경기 객체 검출을 통해 스포츠 분석과 경기 영상 처리에 활용 가능성을 탐구
- 딥 러닝 기술을 실제 응용 분야에 적용하는 방법을 연구하고자 진행

<br>


## [주요 기능]
- 농구 경기 동영상 내의 [Ball , Hoop, Ref, player, team point] 검출 성공
<img width="300" alt="testVideo2 " src="https://github.com/dessertgomjelly/Object_detection_mini_project/assets/127851446/cb857bb9-a21f-4fe0-b328-140a3febd97b">


<img width="400" alt="testVideo2" src="https://github.com/dessertgomjelly/Object_detection_mini_project/assets/127851446/31e98fc5-3670-42bb-8aaa-754ca567e6d2">
<br>
<br>
<br>
<br>


<img width="500" alt="객체인식test2" src="https://github.com/dessertgomjelly/Object_detection_mini_project/assets/127851446/40353988-756b-4d70-b345-b7ecf5ec92ef">

<img width="500" alt="객체인식tes3" src="https://github.com/dessertgomjelly/Object_detection_mini_project/assets/127851446/828b3bd8-66c8-4350-9547-b5d76a8078a6">


<br>

## [데이터 수집]
- [Roboflow](https://roboflow.com/) 사이트 내의 basketball data image 118장 사용
  - 학습 데이터 세트 : 78 Images
  - 검증 데이터 세트 : 22 Images
  - 테스트 데이터 세트 : 18 Images
 
    
- YOLO v5 PytTorch format으로 api_key를 이용하여 내보내기


<pre>
#파일구조
/농구-12
  /test
    /images
    /labels
  /train
    /images
    /labels
  /valid
    /images
    /labels
  /data.yaml
</pre>

<br>


## [모델 선정]
- [소스코드](https://colab.research.google.com/github/dessertgomjelly/Object_detection_mini_project/blob/main/%08%EB%86%8D%EA%B5%AC_%EA%B0%9D%EC%B2%B4_%EC%9D%B8%EC%8B%9D.ipynb)
- colab의 하드웨어 가속기 T4 GPU를 사용
- YOLO v5 PyTorch model

<pre>
!git clone https://github.com/ultralytics/yolov5
%cd /content/yolov5/
!pip install -r requirements.txt
</pre>

- 하이퍼파라미터 조정
  - img size : 416
  - batch size : 16
  - epochs : 100

- YOLOv5s summary
  - 157 layers
  - 7037095 parameters

<br>


## [한계점]
- 모든 클래스 감지 어려움
  - 설정한 클래스 10개 중 최종적으로 5개의 객체만 검출 할 수 있었음.

<pre>
#data.yaml
names: [Ball, Hoop, Period, Player, Ref, Shot Clock, Team Name, Team Points, Time Remaining, player
nc: 10
roboflow:
  license: CC BY 4.0
  project: -suoek
  url: https://universe.roboflow.com/project/-suoek/dataset/12
  version: 12
  workspace: project
test: /content/농구-12/test/images
train: /content/농구-12/train/images
val: /content/농구-12/valid/images
</pre>

<br>

- 정확도를 중시하면 객체 검출이 어려워지고, 감지율을 높이려면 정확한 검출이 어려워지는 딜레마
  - 해당 클래스에 대한 데이터를 더 수집하거나, 모델의 하이퍼파라미터를 조절하여 클래스에 더 집중하도록 노력 할 예정

  
