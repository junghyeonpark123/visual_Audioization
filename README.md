# OSSP 최종 보고서



### 주제

- 시각의 청각화 (visual audioization)

      명화를 음악으로

### 필요성 및 기대효과

시각 장애인들이 그림을 보는 대신 들을 수 있도록 함.

일반 사용자들은 원하는 이미지를 입력함으로써 연상 되는 멜로디의 음악을 출력 할 수 있음.

### 사용 라이센스

Opencv 라이브러리 - apache 2.0

Magenta 라이브러리 - apache 2.0



### 참고 오픈소스

**Magenta tutorial**

[https://colab.research.google.com/notebooks/magenta/hello_magenta/hello_magenta.ipynb](https://colab.research.google.com/notebooks/magenta/hello_magenta/hello_magenta.ipynb)

### 참고 지식

🔸**Hue, Saturation, Value**

H ➡️ 색상 ➡️ 0~360 ➡️ opencv에서는 1/2값인 0~180만 사용 ➡️ 0에 가까울 수록 장파장

S ➡️ 채도 ➡️ 색의 진하기  ➡️ opencv기준 0~255 ➡️ 값이 클 수록 고채도

V ➡️ 명도 ➡️ 색의 밝기 ➡️ opencv 기준 0~255 ➡️ 값이 클 수록 고명도

🔸**색상과 감정의 상관관계**

장파장(난색), 고채도, 고명도일 수록 빠른 시간감과 비례한다.

장파장(난색), 고채도, 고명도일 수록 흥분감을 불러일으킨다.

🔸ptich? Midi에서 음의 높낮이를 나타낸다.

🔸velocity? 볼륨 크기

### 코드 작성 및 변경 부분

<opencv를 이용한 H,S,V 분리, 이미지 Resizing>


<색상은 장파,중파,단파 3가지 영역으로, 채도와 명도는 각각 2가지 영역으로 나누어
색상,채도,명도 순으로 우선시하여 12개의 영역에 0.2초부터 1.3까지 0.1초 간격으로
 매칭한 코드>

<채도와 명도 모두 255부터 28씩 줄어가도록하여 9개의 범주 생성하고
	다시 고채도, 고명도 순으로 연결하여 총 81개의 범주를 
	높은 음의 pitch부터 연결시켰다.>


### 출처에 대한 참고 문헌 목록

**note-sequence에 관한 변수 설명 github**

[https://github.com/magenta/note-seq/blob/main/note_seq/protobuf/music.proto#L27](https://github.com/magenta/note-seq/blob/main/note_seq/protobuf/music.proto#L27)

**hsv 색상표 분석 관련 문헌**

[https://subscription.packtpub.com/book/data/9781789537147/1/ch01lvl1sec09/object-detection-using-color-in-hsv](https://subscription.packtpub.com/book/data/9781789537147/1/ch01lvl1sec09/object-detection-using-color-in-hsv)
