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


| 함수 |  역할 |
|------|--------|
|namedWindow("이름")|	윈도우(실행창)를 생성|
|imshow("이름", 이미지)|	해당 이름의 윈도우에 이미지를 출력|
|setMouseCallback("이름", ...)|	해당 윈도우에 마우스 이벤트 콜백을 연결|

```
MAIN THREAD
├── Mat 초기화 (검정색 배경)
├── 윈도우 생성 (namedWindow)
├── 마우스 콜백 등록 (setMouseCallback)
└── 무한 루프
    ├── imshow(이미지 출력)
    ├── waitKey(키 입력 대기)
    └── ESC 누르면 종료

EVENT SYSTEM (OpenCV 내부)
└── 마우스 더블클릭 발생 → mouse_callback() 실행
    └── 이미지에 랜덤 원 그리기
```
### 의의

1. 비동기 : 메인 루프는 이벤트(마우스 클릭) 발생 여부와 관계없이 계속 돌고 있고, 이벤트 발생 시 콜백 함수가 끼어들어 동작하는 구조이다.
2. 초기의 검정 화면조차도 "정지된 이미지"가 아니라, OpenCV가 매 1ms마다 **프레임 단위로 계속 새로 그려주는 일종의 '동영상 프레임'**이라고 보면 된다.

``` "보여지는 화면은 정적인 것처럼 보이지만, 실제로는 1ms 주기로 계속 새로 그려지고 있다."```
```
초기 검정 화면도 매 프레임마다 OpenCV가 imshow()를 통해 다시 출력 중인 하나의 씬이야.
아무 변화가 없어 보이는 건, g_imgColor가 계속 검정색(0,0,0)으로 유지되고 있어서야.
하지만 imshow()는 GPU 버퍼에 매 프레임마다 동일한 이미지를 계속 덮어쓰기하는 중이지.
-GPT
```
