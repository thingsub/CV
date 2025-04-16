## 🔵 5. User Interface (UI 인터랙션)

| 폴더 | 제목                           | 주요 함수                                           | 시험 포인트                                         |
|------|--------------------------------|----------------------------------------------------|----------------------------------------------------|
| 5.1  | Keyboard Inputs                | `waitKey()`, `flip()`                              | 키 입력 감지 후 이미지 반전 (x, y, ESC)            |
| 5.2  | Mouse Double Click - Circle    | `setMouseCallback()`, `circle()`, `EVENT_LBUTTONDBLCLK` | 마우스 더블 클릭 시 원 그리기 (좌표, 랜덤 색상)    |
| 5.3  | Mouse Drag - Rectangle         | `setMouseCallback()`, `rectangle()`, `EVENT_LBUTTONDOWN/UP` | 마우스 드래그로 사각형 생성                 |
| 5.4  | Trackbar Color Palette         | `createTrackbar()`, `getTrackbarPos()`             | RGB값 조정 트랙바로 이미지 색상 변경, 스위치 포함 |

## 🔵 6. Histogram (히스토그램 시각화)

| 폴더 | 제목                      | 주요 함수                              | 시험 포인트                                       |
|------|---------------------------|----------------------------------------|--------------------------------------------------|
| 6.1  | Histogram Grayscale       | `calcHist()`, `normalize()`, `line()`  | 그레이스케일 이미지 히스토그램 그리기            |
| 6.2  | Histogram Color           | `split()`, `minMaxLoc()`, `calcHist()` | RGB 채널별 히스토그램 시각화, 최대 bin 정규화    |
| 6.3  | Histogram Equalization    | `equalizeHist()`, `sum()`, `hconcat()` | 평활화 전후 비교, 누적 히스토그램 그리기         |

## 🔵 7. Thresholding (이진화)

| 폴더 | 제목                        | 주요 함수                                                  | 시험 포인트                                             |
|------|-----------------------------|-------------------------------------------------------------|----------------------------------------------------------|
| 7.1  | Thresholding Types          | `threshold()`                                               | 5종류 이진화 모드 (`BINARY`, `INV`, `TRUNC`, `TOZERO`, `TOZERO_INV`) 비교 |
| 7.2  | Otsu Binarization           | `threshold() + THRESH_OTSU`, `GaussianBlur()`              | Otsu 전/후 비교, 자동 임계값 추정                        |
| 7.3  | Adaptive Thresholding 01    | `adaptiveThreshold()`                                      | 블러 후 `MEAN_C`, `GAUSSIAN_C` 방식 비교                 |
| 7.4  | Adaptive Thresholding 02    | `adaptiveThreshold()`                                      | 블러 없이 방식 비교, block size & C 값 영향 분석         |

## 🔵 8. Image Blending & Bitwise Operations

| 폴더 | 제목              | 주요 함수                                                    | 시험 포인트                                      |
|------|-------------------|---------------------------------------------------------------|--------------------------------------------------|
| 8.1  | Image Blending    | `addWeighted()`                                              | 두 이미지 간 선형 혼합 (w값 변화 시 애니메이션 구현) |
| 8.2  | Bitwise Operation | `cvtColor()`, `threshold()`, `bitwise_and()`, `bitwise_not()`, `add()` | 이미지 마스킹, ROI 위치에 로고 합성            |

## 🔵 9. Filtering (노이즈 제거 필터)

| 폴더 | 제목             | 주요 함수              | 시험 포인트                                       |
|------|------------------|------------------------|--------------------------------------------------|
| 9.1  | Mean Filter      | `blur()`               | 기본 평균 필터 적용 (커널 사이즈 변화 영향)       |
| 9.2  | Box Filter       | `boxFilter()`          | `normalize` 여부에 따른 차이                     |
| 9.3  | Gaussian Filter  | `GaussianBlur()`       | 가우시안 필터 - σ값 및 커널 크기 영향            |
| 9.4  | Median Filter    | `medianBlur()`         | 소금-후추 잡음 제거에 강력                        |
| 9.5  | Bilateral Filter | `bilateralFilter()`    | 엣지 보존 필터, 가장 느리지만 가장 성능 좋음     |

## 🔵 10. Edge Detection (엣지 검출)

| 폴더 | 제목           | 주요 함수                                 | 시험 포인트                                    |
|------|----------------|--------------------------------------------|------------------------------------------------|
| 10.1 | Sobel Edge     | `Sobel()`, `convertScaleAbs()`, `addWeighted()` | x, y 방향 미분 후 절댓값 합산               |
| 10.2 | Laplacian Edge | `Laplacian()`                              | 2차 미분 이용, 부드러운 이미지에 적합          |
| 10.3 | Canny Edge     | `Canny()`                                  | 가장 정확한 엣지 검출, threshold 조정 중요     |

## ✅ 🧠 종합 체크리스트 요약

| 항목           | 핵심 함수                                                            | 기억해야 할 포인트                                 |
|----------------|----------------------------------------------------------------------|----------------------------------------------------|
| UI             | `waitKey()`, `setMouseCallback()`, `createTrackbar()`                | 사용자 입력으로 이미지 조작 구현                    |
| Histogram      | `calcHist()`, `normalize()`, `equalizeHist()`                        | 정규화 및 누적 히스토그램 시각화                    |
| Threshold      | `threshold()`, `adaptiveThreshold()`, `THRESH_OTSU`                  | 이진화 종류 구분, block size & C 영향 분석          |
| Bitwise        | `bitwise_and()`, `bitwise_not()`                                     | ROI 영역 마스킹 및 로고 삽입                       |
| Blending       | `addWeighted()`                                                      | w값으로 두 이미지 부드럽게 혼합                     |
| Filtering      | `blur()`, `boxFilter()`, `GaussianBlur()`, `medianBlur()`, `bilateralFilter()` | 필터별 특성 (노이즈 제거 vs 엣지 보존) 비교 |
| Edge Detection | `Sobel()`, `Laplacian()`, `Canny()`                                  | 엣지 검출 방법 비교 및 임계값 이해                   |




<br>
<br>




## 🔵 6. Histogram (히스토그램 시각화)

| **함수**           | **목적**                                                                                                  | **형태**                                        | **주요 파라미터**                                                       | **예시 코드**                                                                 |
|-------------------|--------------------------------------------------------------------------------------------------------|------------------------------------------------|---------------------------------------------------------------------|----------------------------------------------------------------------------|
| `calcHist()`       | 히스토그램 계산. 이미지의 색상 분포를 나타내는 히스토그램을 계산. 그레이스케일 또는 컬러 채널에 대해 사용. | `cv2.calcHist(images, channels, mask, histSize, ranges)` | `images`: 이미지 리스트, `channels`: 채널 (예: [0] 그레이스케일), `mask`: 마스크 이미지, `histSize`: 히스토그램의 bin 수, `ranges`: 픽셀 값 범위 | `hist = cv2.calcHist([gray], [0], None, [256], [0, 256])`               |
| `normalize()`      | 히스토그램 정규화. 계산된 히스토그램의 값을 지정된 범위로 정규화.                                          | `cv2.normalize(src, dst, alpha, beta, norm_type)`  | `src`: 입력 이미지, `dst`: 출력 이미지, `alpha`: 최소값, `beta`: 최대값, `norm_type`: 정규화 방법 (예: `cv2.NORM_MINMAX`) | `cv2.normalize(hist, hist, 0, 255, cv2.NORM_MINMAX)`                     |
| `equalizeHist()`   | 히스토그램 평활화. 이미지 대비를 개선하기 위해 히스토그램을 평활화하여 전체 밝기 수준을 조정.                | `cv2.equalizeHist(src)`                        | `src`: 입력 이미지                                          | `equalized = cv2.equalizeHist(gray)`                                      |

## 🔵 7. Thresholding (이진화)

| **함수**           | **목적**                                                                                                  | **형태**                                        | **주요 파라미터**                                                       | **예시 코드**                                                                 |
|-------------------|--------------------------------------------------------------------------------------------------------|------------------------------------------------|---------------------------------------------------------------------|----------------------------------------------------------------------------|
| `threshold()`      | 이미지 이진화. 특정 임계값을 기준으로 이미지를 두 값으로 나누어 이진화 처리.                           | `cv2.threshold(src, thresh, maxval, type)`     | `src`: 입력 이미지, `thresh`: 임계값, `maxval`: 최대값, `type`: 이진화 종류 | `ret, th = cv2.threshold(gray, 127, 255, cv2.THRESH_BINARY)`             |
| `adaptiveThreshold()` | 지역적 이진화. 이미지의 각 부분에 대해 다른 임계값을 설정하여 이진화 처리.                             | `cv2.adaptiveThreshold(src, maxValue, adaptiveMethod, thresholdType, blockSize, C)` | `src`: 입력 이미지, `maxValue`: 최대값, `adaptiveMethod`: 적응 방식 (예: `cv2.ADAPTIVE_THRESH_MEAN_C`), `thresholdType`: 이진화 방식 (예: `cv2.THRESH_BINARY`), `blockSize`: 블록 크기, `C`: 조정 값 | `th = cv2.adaptiveThreshold(gray, 255, cv2.ADAPTIVE_THRESH_MEAN_C, cv2.THRESH_BINARY, 11, 2)` |
| `threshold() + THRESH_OTSU` | Otsu의 이진화. 이미지 히스토그램을 기반으로 자동으로 최적의 임계값을 추정하여 이진화.               | `cv2.threshold(src, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)` | `src`: 입력 이미지                                            | `ret, th = cv2.threshold(gray, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)` |

## 🔵 8. Bitwise & Blending

| **함수**           | **목적**                                                                                                  | **형태**                                        | **주요 파라미터**                                                       | **예시 코드**                                                                 |
|-------------------|--------------------------------------------------------------------------------------------------------|------------------------------------------------|---------------------------------------------------------------------|----------------------------------------------------------------------------|
| `addWeighted()`    | 이미지 혼합. 두 이미지를 비율에 맞게 혼합하여 하나의 이미지로 만듬.<br>이미지 합성 시 많이 사용됨.        | `cv2.addWeighted(src1, alpha, src2, beta, gamma)` | `src1`: 첫 번째 이미지, `alpha`: 첫 번째 이미지의 가중치, `src2`: 두 번째 이미지, `beta`: 두 번째 이미지의 가중치, `gamma`: 추가 값 | `dst = cv2.addWeighted(img1, 0.6, img2, 0.4, 0)`                          |
| `bitwise_and()`    | 비트 AND 연산. 두 이미지의 픽셀 비트별 AND 연산을 수행하여 공통된 부분을 추출.                         | `cv2.bitwise_and(src1, src2)`                   | `src1`, `src2`: 두 입력 이미지                                    | `result = cv2.bitwise_and(img1, img2)`                                    |
| `bitwise_not()`    | 비트 NOT 연산. 이미지를 반전시켜 픽셀 값을 반전시킴.                                                      | `cv2.bitwise_not(src)`                          | `src`: 입력 이미지                                              | `result = cv2.bitwise_not(img)`                                           |
| `add()`            | 두 이미지 더하기. 두 이미지를 픽셀 단위로 더하여 이미지를 합성.                                         | `cv2.add(src1, src2)`                           | `src1`, `src2`: 두 입력 이미지                                    | `result = cv2.add(img1, img2)`                                            |

## 🔵 9. Filtering (노이즈 제거 필터)

| **함수**           | **목적**                                                                                                  | **형태**                                        | **주요 파라미터**                                                       | **예시 코드**                                                                 |
|-------------------|--------------------------------------------------------------------------------------------------------|------------------------------------------------|---------------------------------------------------------------------|----------------------------------------------------------------------------|
| `blur()`           | 평균 필터 적용. 주변 픽셀들과 평균을 계산하여 이미지 블러링.                                           | `cv2.blur(src, ksize)`                          | `src`: 입력 이미지, `ksize`: 커널 크기 (가로, 세로 크기 튜플)        | `result = cv2.blur(img, (5, 5))`                                           |
| `boxFilter()`      | 박스 필터 적용. 일정 영역 내의 평균 값을 계산하여 블러링 처리.                                          | `cv2.boxFilter(src, ddepth, ksize, anchor, normalize)` | `src`: 입력 이미지, `ddepth`: 출력 이미지의 데이터 타입, `ksize`: 커널 크기, `normalize`: 정규화 여부 | `result = cv2.boxFilter(img, -1, (5, 5), normalize=False)`                |
| `GaussianBlur()`   | 가우시안 필터 적용. 가우시안 분포를 이용해 필터링하여 이미지 블러링.                                    | `cv2.GaussianBlur(src, ksize, sigmaX)`          | `src`: 입력 이미지, `ksize`: 커널 크기, `sigmaX`: X 방향 시그마 값  | `result = cv2.GaussianBlur(img, (5, 5), 1.5)`                             |
| `medianBlur()`     | 중앙값 필터 적용. 이미지를 중간값으로 필터링하여 노이즈 제거.                                           | `cv2.medianBlur(src, ksize)`                    | `src`: 입력 이미지, `ksize`: 커널 크기 (홀수여야 함)                 | `result = cv2.medianBlur(img, 5)`                                          |
| `bilateralFilter()` | 양방향 필터 적용. 엣지를 보존하면서 노이즈를 제거하는 필터.                                             | `cv2.bilateralFilter(src, d, sigmaColor, sigmaSpace)` | `src`: 입력 이미지, `d`: 필터 크기, `sigmaColor`: 색상 공간의 표준 편차, `sigmaSpace`: 좌표 공간의 표준 편차 | `result = cv2.bilateralFilter(img, 9, 75, 75)`                            |
