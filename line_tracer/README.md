# 동작 영상

➩ 유튜브 링크
https://youtu.be/2eD7gTxhmKs

# 코드 설명

https://github.com/smHan22/smart-vision/blob/f372cbe151428829943ed32c1621077622cab18c/line_tracer/main.cpp#L11-L20

● 비디오 파일을 열고, 프레임 속도를 설정하는 부분입니다.

● VideoCaputre를 사용하여 비디오 파일을 열고, cap.get(CAP_PROP_FPS)로 비디오의 FPS(초당 프레임 수)를 가져옵니다.

● FPS를 이용하여 delay를 계산하고 각 프레임을 처리하는 시간 간격을 설정합니다.
