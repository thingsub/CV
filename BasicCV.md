# CV
## 기본 클래스 정리
### Mat
- OpenCV의 이미지(Matrix)를 담는 클래스
- 픽셀들의 2차원 배열로 구성
- ``` C++
  Mat :: zeros()  //  모든 픽셀이 0으로 채워진 검은 이미지 생성
  ```
| 타입 | 정의 | 용도 |
|------|---|-------|
|CV_8UC1|	8-bit unsigned, 1채널|흑백(Grayscale) 이미지|
|CV_8UC3|	8-bit unsigned, 3채널|BGR|
|CV_8UC4|	8-bit unsigned, 4채널|BGR + Alpha|

### Scalar
- 색상 표현
- 4채널 이하에서 영상의 픽셀 값 표시
- OpenCV는 색 순서가 BGR임에 주의
``` C++
  Scalar(255, 0, 0) // 파란색
  Scalar(0, 255, 0) // 초록색
  Scalar(0, 0, 255) // 빨간색
  ```
✅ 이미지 크기 = 전체 픽셀 수 (위치 정보)<br>
✅ 각 픽셀 = 3개의 채널 값 (색 정보)<br>
✅ 각 채널 값 = 0~255 (명도)<br>
✅ 세 채널의 값이 합쳐져서 픽셀의 실제 색을 만들어낸다<br>
✅ "픽셀 당 가지는 값의 개수 = 채널 수"<br>
✅ "보여지는 화면 = 채널 값들이 합쳐져 만든 색상"<br>

``` "픽셀 당 가지는 값의 개수는 채널 수와 같고, 실제 보여지는 화면은 이 채널들의 값이 합쳐져서 구현된다" ```

### Point
- (x,y) 좌표를 표현
- 이미지 상 픽셀 위치 지정 시 사용
- ex) 마우스로 클릭한 지점에 원을 그릴 경우, 해당 좌표가 ``` Point(x,y) ```

### RNG
- Random Number Generator
- ``` C++
  // 예시
  g_rng.uniform(10, 50) // 10부터 50 사이의 랜덤 정수를 반환
  randomColor(g_rng) // 무작위 색을 만들어주는 함수 (RGB 각각 랜덤으로)
  ```

🔍 namedWindow()
- OpenCV에서 GUI 윈도우(실행창) 를 생성해주는 함수
- 이름 부여 시 나중에 그 이름으로 이미지를 출력하거나, 이벤트를 연결 가능
``` cpp
namedWindow("My Window"); // "My Window"라는 이름을 가진 빈 실행창(윈도우) 하나가 생성됨.
```
<pr>
Q. 이미지를 윈도우에 표시하려면?<br>
=> imshow() 함수에서 윈도우 이름을 동일하게 표시하도록

``` cpp
imshow("My Window", myImage); // "My Window"라는 창에 myImage가 표시됨.
```
'두 함수는 짝꿍이다.
namedWindow()로 창을 만들고, imshow()로 그 창에 이미지를 띄워주는 거지.'

