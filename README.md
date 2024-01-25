# 🫥 객체 검출 미니 프로젝트 : 농구 게임 분석
<br>

## [주요 기능]
- 농구 게임 동영상 내의 [Ball , Hoop, Ref, player, team point] 검출 성공
<img width="300" alt="testVideo2 " src="https://github.com/dessertgomjelly/Object_detection_mini_project/assets/127851446/cb857bb9-a21f-4fe0-b328-140a3febd97b">


<img width="600" alt="testVideo2" src="https://github.com/dessertgomjelly/Object_detection_mini_project/assets/127851446/31e98fc5-3670-42bb-8aaa-754ca567e6d2">

<br>
<br>

## [데이터 수집]
- [Roboflow](https://roboflow.com/) 사이트 내의 basketball data image 118장 사용
- YOLO v5 PytTorch format으로 api_key를 이용하여 export


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
<br>

## [모델 선정]
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
