https://www.youtube.com/watch?v=GBpnsFfLt2Q



### 컴퓨터비전 문제

-------------

object detection & recognition

Scene understanding

3D reconstruction

tracking

image/video restoration

segmentation



## 딥러닝과 컴퓨터비전

AlexNet - 획기적인 결과를 보여줌



## Openpose

최초의 딥러닝기반 2D 멀티 휴먼 포즈추정 기법

Bottom-up 방식: 입력영상내의 모든 2D joint들을 추정한 후, joint들간의 관계성 (part affinity field)정보를 이용하여 개별 사람의 포즈 검출





### Refinement 기법 - PoseFix

-------------------------------------------------------------

PoseFix: 기존 시스템의 에러를 줄이는 후처리 시스템

대부분의 휴먼포즈 추정시스템은 공통적인 에러특성을 가지고 있음

실제 에러특성 확률 모델을 이용 가상의 에러 데이터를 합성, refine network 학습



### 3D Human Pose

------------------------------------

V2V PoseNet: 입력과 출력을 모두 Voxel로 표현함으로써 성능향상



RGB기반 2D포즈로부터 3D 포즈 추정 기법

최초의 single 휴먼 3D 포즈추정기법

3D 포즈 추정문제를 '2D 포즈 추정' + 'Lifting' 문제로 분리 해결



### 3D Shape and Pose

-------------------------

단일 RGB영상으로부터 인체의 3D shape과 포즈 정보를 동시에 추정하는 최초의 기법

Parametric human 모델(SMPL) 사용





### 결론 및 전망

휴먼포즈 인식 추정 기술은 최근 5-6년간 딥러닝 기술에 힘입어 획기적인 발전을 이룸

기술의 성숙도에 따라 다양한 응용분야에서의 새로운 비즈니스가 창출될 것으로 예상

특히 AR/VR, 로봇, 의료분야에서의 폭발적 성장이 예상됨



향후과제

- 행동인식 및 예측문제에 적용
- 원거리, 극한 상황에서의 휴먼 포즈 인식 문제해결
- 3D 포즈 생성 및 전이 문제
- 실시간 엣지 컴퓨팅 기술 확보
- 응용분야별 대용량 실제 데이터셋 확보 필요
- 다양한 사회문제 대응, 새로운 비즈니스 창출







