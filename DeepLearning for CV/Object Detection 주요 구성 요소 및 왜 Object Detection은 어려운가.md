# Object Detection 주요 구성 요소 및 왜 Object Detection은 어려운가?



#### 주요 Backend CNN Classification

- 범용 - Resnet
- Tensorflow Object API - Inception, Mobilenet





#### Object Detection의 난제

- Classification + Regression을 동시에 - 이미지에서 여러 개의 물체를 classification함과 동시에 위치를 찾아야함.

- 다양한 크기와 유형의 오브젝트가 섞여 있음 - 크기가 서로 다르고, 생김새가 다양한 오브젝트가 섞여있는 이미지에서 이들을 Detect해야 함.

- 중요한 Detect 시간 - Detect시간이 중요한 실시간 영상 기반에서 Detect해야하는 요구사항 증대

- 명확하지 않은 이미지 - 오브젝트 이미지가 명확하지 않은 경우가 많음. 또한 전체 이미지에서 detect할 오브젝트가 차지하는 비중이 높지 않음.(배경이 대부분을 차지하는 경우가 많음)

- 데이터세트의 부족 - 훈련 가능한 데이터 세트가 부족하며 annotation을 만들어야 하므로 훈련 데이터 세트를 생성하기가 상대적으로 어려움

  

