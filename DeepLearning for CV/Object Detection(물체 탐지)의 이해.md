### Object Detection(물체 탐지)의 이해

---------



###  Localization과 Detection

--------------

Object(s)의 위치를 찾아내는 것



##### 이미지에 Object가 1개인 경우

##### Classification

이것은 A이다.

##### Localization

A의 이미지 안 위치(특정 좌표)를 찾아주는 것 

단 하나의 Object 위치를 Bounding box로 지정하여 찾음



##### 이미지가 Object에 여러 개인 경우

##### Detection

여러 개의 Object들에 대한 위치를 Bounding box로 지정하여 찾음

##### Segmentation

Detection보다 더 발전된 형태로 **pixel 레벨**의 detection 수행



- Localization/Detection은 해당 Object의 위치 Bounding box로 찾고, Bounding Box내의 오브젝트를 판별합니다.

  

- Localization/Detection은 Bounding box regression(box의 좌표값을 예측)과 Classification 두 개의 문제가 합쳐져 있습니다.

  

- Localiztion에 비해 Detection은 두 개 이상의 Object를 이미지의 임의 위치에서 찾아야 하므로 상대적으로 Localization보다 **여러가지 어려운 문제**에 봉착하게 됩니다.











