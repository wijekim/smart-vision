# manual drive

➨ jetson 장치의 카메라로 촬영한 영상을 실시간으로 전송하고 로컬에 저장하며, Dynamixel 모터를 원격으로 제어하는 것.

# Makefile

• Makefile은 프로젝트의 빌드 과정을 자동화하는 파일로, 여러 파일이 포함된 프로젝트를 쉽게 컴파일하고 관리할 수 있도록 함.

https://github.com/smHan22/smart-vision/blob/5b19626f19f421ec92a4cf5716a24f2f6214c217/manualdrive/makefile#L1-L15
```
• TARGET = manualdrive는 생성할 최종 실행 파일 이름을 manualdrive로 설정.

• $(TARGET) : $(OBJS)는 main.o와 dxl.o가 준비되면 실행 파일 manualdrive를 생성. $(CX) -o $(TARGET) $(OBJS) $(LDFLAGS): 지정된 컴파일러와 링크 플래그로 오프젝트 파일들을 링크하여 실행 파일을 생성.

• main.o : main.cpp은 main.cpp를 컴파일하여 main.o를 생성. $(CX) $(CXFLAGS) -c main.cpp는 컴파일러와 컴파일 플래그를 사용하여 main.cpp를 오브젝트 파일로 만듬.

• dxl.o : dxl.hpp dxl.cpp은 dxl.cpp와 헤더 파일 dxl.hpp를 컴파일하여 dxl.o를 생성.

• $(CX) $(CXFLAGS) -c dxl.cpp는 지정된 컴팡일러와 컴파일 플래그를 사용하여 dxl.cpp를 오프젝트 파일로 만듬.
```
# main.cpp 

 ➨ https://github.com/smHan22/smart-vision/blob/main/manualdrive/main.cpp

 • jetson 카메라로 실시간 영상을 촬영하고, 촬영된 영상을 로컬 파일과 스트림으로 전송하면서 다이나믹셀 모터를 제어하는 것.

     • VideoCapture source(src, CAP_GSTREAMER);는 src 파이프라인을 사용해 카메라 입력을 설정.

     • dst1은 GStreamer를 사용하여 영상 데이터를 UEP로 전송하는 파이프라인 스트링.

     • local_file은 촬영한 영상을 로컬에 저장할 파일 이름. 

     • goal1과 goal2에 설정된 목표 속도에 따라 vel1과 vel2의 점진적으로 증가 또는 감소시키며, 갑작스러운 속도 변화를 줄임. mx.setVelocity(vel1, vel2);를 통해 모터의 속도를 설정.

     • ctrl_c_pressed가 true일 때 루프를 탈출하여 프로그램을 종료함.


# 실행결과 

https://youtu.be/RJZUxHrEgbM

