# 동작 영상

➩ 유튜브 링크
https://youtu.be/2eD7gTxhmKs

# 코드 설명

```ruby
https://github.com/smHan22/smart-vision/blob/8cb6b47f67f977d489f124b9ced5eef658c4f531/line_tracer/main.cpp#L11C5-L20C37
string videoPath = "/home/hsmin22/workspace/line_tracer/simulation/7_lt_ccw_100rpm_in.mp4";

VideoCapture cap(videoPath);
if (!cap.isOpened()) {
    cerr << "Error: Unable to open video file!" << endl;
    return -1;
}

double fps = cap.get(CAP_PROP_FPS);
int delay = cvRound(1000 / fps);
```
