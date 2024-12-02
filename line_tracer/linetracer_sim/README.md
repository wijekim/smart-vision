# 라인트레이서_모션제어

➨ 지난 시간 라인 검출에 이어서 검출한 라인과 위치오차를 이용하여 속도명령을 설계하는 것을 설명하겠습니다.

https://github.com/smHan22/smart-vision/blob/f10042d2c82ec4e662953af3035686868e0f5b8c/line_tracer/linetracer_sim/main.cpp#L135

```ruby
centerOfImage.x는 화면의 중심 x좌표

closestCenter.x는 현재 라인의 중심점 x좌표

error는 화면 중심과 라인의 중심 간의 x축 거리 차이를 나타냅니다.

값이 양수이면 라인이 화면 중앙보다 왼쪽에 위치, 값이 음수이면 라인이 화면 중앙보다 오른쪽에 위치, 값이 0이면 라인이 화면 중앙에 정확히 위치
```
