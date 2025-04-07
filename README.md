# CV
## 250407 Double Click to Draw Circles
거시적인 구조
```C++
Mat g_imgColor;                    // 전역 이미지
RNG g_rng(getTickCount());         // 랜덤 생성기
Scalar randomColor(RNG &g_rng);    // 무작위 색 생성 함수
void mouse_callback(...);          // 마우스 이벤트 콜백
int main() { ... }                 // 메인 루프
```
### Mat
- OpenCV의 이미지(Matrix)를 담는 클래스
- 픽셀들의 2차원 배열로 구성
- ``` C++
  Mat :: zeros()  //  모든 픽셀이 0으로 채워진 검은 이미지 생성
  ```

### Scalar
- 색상 표현
- 4채널 이하에서 영상의 픽셀 값 표시
- OpenCV는 색 순서가 BGR임에 주의
- ```
  C++
  Scalar(255, 0, 0) // 파란색
  Scalar(0, 255, 0) // 초록색
  Scalar(0, 0, 255) // 빨간색
  ```

  ### Point
  - (x,y) 좌표를 표현
  - 이미지 상 픽셀 위치 지정 시 사용
  - ex) 마우스로 클릭한 지점에 원을 그릴 경우, 해당 좌표가 ``` Point(x,y) ```
