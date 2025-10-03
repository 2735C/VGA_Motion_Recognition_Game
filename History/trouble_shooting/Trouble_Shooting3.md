## [Pattern  구현 Module 리소스 ]


### 1️⃣ 모듈 구조

`ray_cross_unit` 모듈은 **화면 픽셀 좌표**(`x_pixel`, `y_pixel`)와 **라인 좌표**(`line`)를 받아서 특정 조건을 만족 시 `hit`를 1로 설정. 

* 입력 `line`은 38비트로 선분을 정의.

```systemverilog
x1: line[37:28] (10-bit)
y1: line[27:19] (9-bit)
x2: line[18:9]  (10-bit)
y2: line[8:0]   (9-bit)
``` 


### 2️⃣ 핵심 계산

#### 1. y 범위 체크:
:arrow_right: 현재 픽셀이 선분의 y 범위 안에 있는지 확인.

```systemverilog
y_in_range_s1 = (y_pixel_s0 > ymin) && (y_pixel_s0 <= ymax);
y_in_range_s2 = y_in_range_s1;
```
#### 2. x 교차점 계산:
:arrow_right: 선분과 y 위치가 일치하는 점에서의 x 좌표를 계산. 

$x =\\frac{(y_{\text{pixel}} - y_{\min})}{dy} \times dx$

#### 🔥 문제: Pattern Hit 판정 계산 시 변수간 곱셈 나눗셈으로 인해 연산량 증가

<img src="/History/img/hw/img_3.png" width=500 >|
--|


#### 🤩 해결 방법: 구간별 덧셈 연산으로 리소스 절감 

> `dy <= 4, dy <= 8, dy >8` or `dx <= 4, dx <= 8, dx >8`


| [Before] LUT 158% | [After] LUT 96% |
--|--
<img src="/History/img/hw/img_4.png" width=400 >|<img src="/History/img/hw/img_5.png" width=400 >|
<img src="/History/img/hw/img_3.png" width=400 >|<img src="/History/img/hw/img_6.png" width=400 >|

#### 3. hit 결정:
:arrow_right:  현재 픽셀이 선분 y 범위 안에 있으면서, 픽셀 x가 선분과 교차하는 x보다 오른쪽에 있는 경우 hit = 1.

```systemverilog
assign hit = y_in_range_s2 && (x_intersect_s2 < x_pixel_s2);
```
