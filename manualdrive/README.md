# manual drive

➨ jetson 장치의 카메라로 촬영한 영상을 실시간으로 전송하고 로컬에 저장하며, Dynamixel 모터를 원격으로 제어하는 것.

# Makefile

➨ https://github.com/smHan22/smart-vision/blob/main/manualdrive/makefile

• Makefile은 프로젝트의 빌드 과정을 자동화하는 파일로, 여러 파일이 포함된 프로젝트를 쉽게 컴파일하고 관리할 수 있도록 함.

    • TARGET = manualdrive는 생성할 최종 실행 파일 이름을 manualdrive로 설정.

    • $(TARGET) : $(OBJS)는 main.o와 dxl.o가 준비되면 실행 파일 manualdrive를 생성. $(CX) -o $(TARGET) $(OBJS) $(LDFLAGS): 지정된 컴파일러와 링크 플래그로 오프젝트 파일들을 링크하여 실행 파일을 생성.

    • main.o : main.cpp은 main.cpp를 컴파일하여 main.o를 생성. $(CX) $(CXFLAGS) -c main.cpp는 컴파일러와 컴파일 플래그를 사용하여 main.cpp를 오브젝트 파일로 만듬.

    • dxl.o : dxl.hpp dxl.cpp은 dxl.cpp와 헤더 파일 dxl.hpp를 컴파일하여 dxl.o를 생성.

    • $(CX) $(CXFLAGS) -c dxl.cpp는 지정된 컴팡일러와 컴파일 플래그를 사용하여 dxl.cpp를 오프젝트 파일로 만듬.

# main.cpp 

 ➨ 


# 실행결과 
