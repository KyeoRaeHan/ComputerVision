# Object Detection과 Segmentation 개요



#### Object Detection 

Deep Learning 기반으로 발전



###  Localization/Detection/Segmentation

--------------

Object(s)의 위치를 찾아내는 것



- #### 이미지에 Object가 1개인 경우

##### Classification

이것은 A이다.

##### Localization

이미지 안 A의 위치(특정 좌표)를 찾아주는 것 

단 하나의 Object 위치를 Bounding box로 지정하여 찾음



- #### 이미지에 Object가 여러 개인 경우

##### Detection

여러 개의 Object들에 대한 위치를 Bounding box로 지정하여 찾음

##### Segmentation

Detection보다 더 발전된 형태로 **pixel 레벨**의 detection 수행 

- 정확도가 높으며, 넓은 방향성을 가진다.
- 활용도가 높은 application들을 만들 수 있다.



### Localization과 Detection

-----------

- Localization/Detection은 해당 Object의 위치 Bounding box로 찾고, Bounding Box내의 오브젝트를 판별합니다.

- Localization/Detection은 Bounding box regression(box의 좌표값을 예측)과 Classification 두 개의 문제가 합쳐져 있습니다.

- Localiztion에 비해 Detection은 **두 개 이상**의 Object를 이미지의 임의 위치에서 찾아야 하므로 상대적으로 Localization보다 **여러가지 어려운 문제**에 봉착하게 됩니다.



### Object Detection History

Alexnet을 기점으로 나뉜다.





