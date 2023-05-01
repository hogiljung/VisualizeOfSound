# VisualizeOfSound
 # 프로젝트 소개
   ## 1. 기획 의도
     - 주변 소리와 음성을 시각적으로 보여주어 난청인에게 도움을 주고자 함.

   ## 2. 작품 내용
    (1) 소리의 시각화
     - 스마트폰 화면을 통해 소리의 방향을 볼 수 있음.
     - 소리의 분류를 통해 어떤 소리인지 알 수 있음.
     - 분류를 통해 음성 인식 시 문자화를 통해 의미를 알 수 있음.
    (2) 위험 알림
     - 위험한 소리 인식 시 시각, 진동으로 알려줌.
     
   ## 3. 구성도
    (1) S/W 구성도
<img width="619" alt="image" src="https://user-images.githubusercontent.com/112647829/231383139-ef06fe25-2d68-400a-b0fb-1b98eec21e82.png">

     - Front-end는 Android를 사용. 
     - Back-end의 EC2에서 실행 중인 Go 언어를 이용한 서버와 Socket 통신하게 된다.
     - 데이터 요청 시 서버는 ReSpeaker와 Socket 통신을 하여 Noise 제거 소리를 얻게 된다.
     - Noise를 제거한 소리를 ODAS Library를 이용해 소리 방향벡터를 계산한다.
     - Noise를 제거한 소리를 이용해 소리 분류 학습 모델을 이용해 분류한 결과를 얻는다.
     - 음성 분류 인식 시 음성을 텍스트화해주는 API를 이용해 텍스트를 얻는다.
     - 모든 결과를 Android에 전달한다.

    (2) H/W구성도
     - 스마트폰과 ReSpeaker Core v2로 구성.
     - ReSpeaker Core V2는 스마트폰의 전력을 이용하여 구동됨.
  
# 프로젝트 수행결과
 ## 1. 주요기능
  - ReSpeaker와 서버와의 소켓통신: 소켓 통신을 이용해 서버에서 Noise제거 소리를 이용할 수 있도록 한다.
  - 소리 방향 계산: 오픈 소스를 ODAS Library를 이용해 소리의 방향에 대한 벡터 값을 구한다.
  - 서버의 음성, 비음성 분석 프로그램 입출력: 데이터를 음성, 비음성 분석 프로그램에게 전달하고 그 결과를 받는다.
  - 음성 언어 분석: 소켓을 통해 전달받은 소리 음성을 Google의 STT API를 이용해 텍스트로 변환한다.
  - 비음성 언어 분석: 소켓을 통해 Noise를 제거한 소리를 전달받아 딥러닝 기술을 적용한 학습모델을 이용해 어떤 소리인지 분류한다.
  - 안드로이드 앱과 서버와의 소켓통신: 소켓 통신을 이용해 서버의 데이터를 이용할 수 있다.
  - 안드로이드 앱에서의 데이터처리 및 UI: 소리 방향, 소리 분류, 음성언어의 소리 정보를 카메라 화면과 함께 확인할 수 있다.

 ## 2. 프로그램 작동 동영상
  - URL : https://youtu.be/n_ZrEeq-mok

 ## 3. 결과물 이미지
   <img width="634" alt="image" src="https://user-images.githubusercontent.com/112647829/231382165-b50c1118-5d53-4fe3-b32e-54aaa7044b10.png">

 ## 4. 수상
  - 2021 한이음 엑스포, 동상
