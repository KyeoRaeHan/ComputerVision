## Human Pose Estimation 기술의 발전과 미래

https://www.youtube.com/watch?v=GBpnsFfLt2Q



### 컴퓨터비전 문제

-------------

시각정보(vision)은 인간지능을 구성하는 가장 중요한 요소



##### 컴퓨터비전이란 무엇인가?

----------

- 컴퓨터로 하여금 인간과 같이 보고, 물체 및 환경 등을 인식, 이해하게 하는 AI기술
- 컴퓨터로 하여금 영상으로부터 의미를 찾게하는 기술



##### 컴퓨터비전이 다루는 문제

-----------------------

1. **Object detection & recognition**

2. **Scene understanding**

3. **3D reconstruction**

4. **Tracking**

5. **Image/video restoration**

6. **Segmentation**

   

#### 딥러닝과 컴퓨터비전

---------------------------

![image-20200611224734939](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20200611224734939.png)

딥러닝의 혁명은 컴퓨터비전으로부터 시작, 서로 긴밀히 영향을 주고 받으며 발전

CV는 현재 전 공학분야에서 가장 영향력 있는 분야



### 휴먼포즈추정 문제란?

-----

- RGB영상 또는 거리(depth)영상으로부터 주요 신체 분위(joint)의 위치를 찾는 문제

- 정의된 신체모델 사용


![image-20200611225452647](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20200611225452647.png)



### 응용분야

------------------------------------

- HCI(Human Computer Interface), AR/VR 핵심기술

- 자율자동차, 로봇, 게임, 의료, 스포츠, 감시 장치




### 왜 어려운가?

----

![image-20200611230006609](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20200611230006609.png)

- self and External occulsion: 물체 혹은 타인에 의해 가려짐

- arms and legs foreshortenig: 카메라 효과

- varying illumination: 조명

- clothing variation: 옷 속의 관절 찾기 어려움

- motion blur: blur로 인해 정확한 관절찾기가 어려움

  

### Marker vs. Markerless 시스템

------

- Marker 기반 motion capture system: 특수 마커(marker) 부착 및 센싱 기반의 신체 joint 위치 추정기술

- 스튜디오환경에서 영화, 게임, AR/VR 등 특수효과에 주로 사용




##### marker의 단점

- high cost - 최소 $10000
- 특수 장비, 복장 및 환경의 제약성



##### Markerless 시스템: 현재 Markerless 시스템을 개발하기 위한 연구들이 많이 진행되고 있다.

- Markerless 포즈추정 시스템: RGB 카메라 또는 depth 카메라를 이용하여 마커 없이 신체 joint 위치 추정

- Low cost, 일반환경에서 다양한 응용에 사용가능

![image-20200612002558518](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20200612002558518.png)

![image-20200612002617553](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20200612002617553.png)



### Makerless 휴먼포즈 추정 문제의 종류

--------------------------

![image-20200604111938149](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20200604111938149.png)



2D pose는 연구가 많이 진행되었지만, 3D pose는 아직 미미한 상태



### 딥러닝 이전의 휴먼포즈 추정기법

-------------

#### 초창기 접근 방법 - Pictorial Structure Model

- Pictorial Structure
- 사람의 신체를 신체부위 (part)와 관계(spring)으로 모델링
- 영상에서 해당 부위를 매칭함으로써 포즈 추정
- 최초의 휴먼포즈 추정 기법



- Mixture of parts
- 더 작은 단위의 신체파트와 이들의 결합으로 표현
- 유연성과 정확도 향상



### 거리정보(Depth) 기반 포즈 추정 기법

--------------------

Microsoft Kinect Xbox - 착용장비없이 게임을 플레이할 수 있다. 



##### 사업적 성공실패

- 프라이버시 문제
- 기술을 이용할만한 다양한 소프트웨어 부재





### 딥러닝 기반 휴먼포즈 추정 기법

----------------------------------------

DeepPose: 최초의 딥러닝 기반 2D 휴먼포즈 추정

입력 RGB 영상에 대해 CNN-regressor를 이용하여 점진적으로 신체 joint의 2D 좌표를 추정



### Heatmap 이용

----------------

##### Heatmap을 사용한 휴먼 포즈 추정 기법

좌표 대신 joint가 나타날 확률(heatmap)을 추정함으로써 정확도 향상

그래프 모델과 CNN을 결합함으로써 joint들간의 위치관계 사용

여전히 신체구조적 정보 부족



Context, receptive field, local & global feature

------------------

##### 컨텍스트(Context)와 신체 구조 정보의 활용

CPM: Body joint들의 공간적 관계 정보 학습을 위하여 큰 receptive field을 이용

순차적으로 receptive field를 키우고 contex정보를 이용하여 joint추정의 정확도를 높임

![image-20200611233838768](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20200611233838768.png)



### 전역과 지역 특징정보의 활용

----------------

- 풀링과 업스케일링으로 이루어진 Hourglass(모래시계) 네티워크를 연속 사용
- 다중 스케일에서의 전역과 지역적 특징을 모두 활용
- Residual module + intermediate supervision

![image-20200611234046120](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20200611234046120.png)



### 딥러닝 기반 2D 멀티 휴먼 포즈 추정 기법

-------------------------------

- OpenPose: 최초의 딥러닝기반 2D 멀티 휴먼 포즈추정 기법

- Bottom-up 방식: 입력영상내의 '모든' 2D joint들을 추정한 후, joint들간의 관계성 (part affinity field)정보를 이용하여 개별 사람의 포즈 검출




##### 현재 SOTA 2D 다중 휴먼 포즈 추정 기법

- RSN(Res-Steps-Net): Winner of COCO keypoint Chanllenge 2019
- 다중 스케일 정보 활용, refine stage를 이용하여 순차적 정확도 향상



##### Refinement 기법 - PoseFix

PoseFix: 기존 시스템의 에러를 줄이는 후처리 시스템

대부분의 휴먼포즈 추정시스템은 공통적인 에러특성을 가지고 있음

실제 에러특성 확률 모델을 이용 가상의 에러 데이터를 합성, refine network 학습



### 3D Human Pose

------------------------------------

거리(Depth) 정보기반 3D 포즈 추정 기법

V2V PoseNet: 입력과 출력을 모두 Voxel로 표현함으로써 성능향상



##### RGB기반 2D포즈로부터 3D 포즈 추정 기법

----------

최초의 single 휴먼 3D 포즈추정기법

3D 포즈 추정문제를 **2D 포즈 추정' + 'Lifting**문제로 분리 해결



![image-20200612000421397](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20200612000421397.png)

​                                                         <lifting network>

영상에서 2D 포즈를 추정한 후, network를 통해서 3차원으로 변경시켜줌.



### RGB기반 3D 다중 휴먼 포즈 추정기법

-----------------

- 최초의 end-to-end 다중 휴먼 3D pose estimation 기법

- 카메리 기반 실제 거리 정보 추정 


![image-20200612001329188](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20200612001329188.png)

- 단일영상에서의 대상 사람의 실제 거리 측정의 모호성 존재
- 학습을 통하여 대상의 나이, 자세 등을 파악 영상내 크기와 실제 거리와의 모호성을 해결




### 3D Shape and Pose

---------------

##### Model 기반 3D 형상 및 포즈 추정 기법

- 단일 RGB영상으로부터 인체의 3D shape과 포즈 정보를 동시에 추정하는 최초의 기법

- Parametric human 모델(SMPL) 사용

  

##### Model-free 3D 형상 및 포즈 추정 기법

- End-to-end model free, 직접 3D 메쉬모델 포즈 추정

- SOTA 성능


![image-20200612002225046](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20200612002225046.png)



### 결론 및 전망

--------------------------------

- 휴먼포즈 인식 추정 기술은 최근 5-6년간 딥러닝 기술에 힘입어 획기적인 발전을 이룸

- 기술의 성숙도에 따라 다양한 응용분야에서의 새로운 비즈니스가 창출될 것으로 예상

- 특히 AR/VR, 로봇, 의료분야에서의 폭발적 성장이 예상됨




##### 향후과제

- 행동인식 및 예측문제에 적용
- 원거리, 극한 상황에서의 휴먼 포즈 인식 문제해결
- 3D 포즈 생성 및 전이 문제
- 실시간 엣지 컴퓨팅 기술 확보
- 응용분야별 대용량 실제 데이터셋 확보 필요
- 다양한 사회문제 대응, 새로운 비즈니스 창출







