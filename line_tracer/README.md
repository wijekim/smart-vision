# 동작 영상

➩ 유튜브 링크
https://youtu.be/2eD7gTxhmKs

# 코드 설명

https://github.com/smHan22/smart-vision/blob/f372cbe151428829943ed32c1621077622cab18c/line_tracer/main.cpp#L11-L20

● 비디오 파일을 열고, 프레임 속도를 설정하는 부분입니다.

● VideoCaputre를 사용하여 비디오 파일을 열고, cap.get(CAP_PROP_FPS)로 비디오의 FPS(초당 프레임 수)를 가져옵니다.

● FPS를 이용하여 delay를 계산하고 각 프레임을 처리하는 시간 간격을 설정합니다.

https://github.com/smHan22/smart-vision/blob/43959dff97d8274cf134eedba4f08d541011f169/line_tracer/main.cpp#L22-L28

● 영상 처리와 관련된 변수들을 초기화합니다.

● previousCenter는 이전 프레임에서 라인의 중심점을 저장하는 변수이며, firstFrame은 첫 번째 프레임을 처리하는지 확인하는 변수입니다.

● MAX_DISTANCE는 라인의 중심점 간의 최대 허용 거리로 설정되며, start와 edn1은 측정을 위한 변수입니다.

● error는 중앙점과 라인의 중심점 간의 오차를 계산하는 변수입니다.
