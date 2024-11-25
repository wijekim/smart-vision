# 동작 영상

➩ 유튜브 링크
https://youtu.be/2eD7gTxhmKs

# 코드 설명

https://github.com/smHan22/smart-vision/blob/f372cbe151428829943ed32c1621077622cab18c/line_tracer/main.cpp#L11-L20

  ```ruby
● 비디오 파일을 열고, 프레임 속도를 설정하는 부분입니다.

● VideoCaputre를 사용하여 비디오 파일을 열고, cap.get(CAP_PROP_FPS)로 비디오의 FPS(초당 프레임 수)를 가져옵니다.

● FPS를 이용하여 delay를 계산하고 각 프레임을 처리하는 시간 간격을 설정합니다.
```

https://github.com/smHan22/smart-vision/blob/43959dff97d8274cf134eedba4f08d541011f169/line_tracer/main.cpp#L22-L28

```ruby
● 영상 처리와 관련된 변수들을 초기화합니다.

● previousCenter는 이전 프레임에서 라인의 중심점을 저장하는 변수이며, firstFrame은 첫 번째 프레임을 처리하는지 확인하는 변수입니다.

● MAX_DISTANCE는 라인의 중심점 간의 최대 허용 거리로 설정되며, start와 edn1은 측정을 위한 변수입니다.

● error는 중앙점과 라인의 중심점 간의 오차를 계산하는 변수입니다.
```

https://github.com/smHan22/smart-vision/blob/f6c86c6a355d03f59dcd9ec9131eb645077c8f81/line_tracer/main.cpp#L29-L45

```ruby
● 비디오에서 한 프레임을 읽고, 그레이스케일로 변환합니다.

● cap >> frame는 비디오에서 한 프레임을 읽어옵니다. 비디오가 끝나면 frame.empty()가 true가 되어 루프를 종료합니다.

● cvtColor(frame, gray, COLOR_BGR2GRAY)는 컬러 영상을 그레이스케일로 변환합니다.

● mean(gray)를 통해 그레이스케일 영상의 평균 밝기를 계산합니다. 이 평균 밝기를 바탕으로 밝기를 조정하여 gray의 밝기를 100에 맞춥니다.

● threshold() 함수는 그레이스케일 영상을 이진화하여 binary로 만듭니다. 밝은 영역은 255(흰색)으로, 어두운 영역은 0(검은색)으로 변환됩니다.

● Rect roi는 (0, 270)dptj (640, 90) 크기로 자릅니다.

● ResizedBinary = binary(roe)로 이진화된 영상에서 정의된 영역을 잘라냅니다.
```

https://github.com/smHan22/smart-vision/blob/83a1647082c41f5e2203509030ede28a1e905121/line_tracer/main.cpp#L47-L67

```ruby
● connectedComponentsWithStats() 함수는 이진화된 영상에서 연결된 객체들을 찾아 라벨을 지정하고, 각 객체의 바운딩 박스와 중심점을 계산합니다.

● labelImage는 각 픽셀의 라벨을 저장하는 영상, stats는 바운딩 박스 정보, centroids는 각 객체의 중심점 정보를 저장합니다.

● 각 라인의 중심점을 계산하고 바운딩 박스를 그립니다.

● 각 라벨에 대해 stats에서 바운딩 박스의 위치와 크기를 가져오고, centroids에서 중심점을 계산합니다.

● lineCenters 백터에 각 라인의 중심점을 추가하고, rectangle()과 circle() 함수로 바운딩 박스와 중심점을 그립니다.

```
