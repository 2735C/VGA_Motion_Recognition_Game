# AI 반도체 설계 2기 Final Project

## 팀원 


|Team Leader|Team Member1|Team Member2| 
--|--|--|
| [<img src="/History/img/another/profile_1.png" width=150 > </br> @문우진](https://github.com/) |  [<img src="/History/img/another/profile_2.jpg" width=150 > </br> @Kim ByeonHyeon](https://bhyeon1.github.io/)|  [<img src="/History/img/another/profile_3.png" width=150 > </br> @김을중](https://github.com/)| 

|Team Member3|Team Member4|Team Member5|Team Member6| 
--|--|--|--|
| [<img src="/History/img/another/profile_4.png" width=150 > </br> @박승범](https://github.com/) |  [<img src="/History/img/another/profile_5.png" width=150 > </br> @안재용](https://github.com/)| [<img src="/History/img/another/profile_6.png" width=150 > </br> @오정일](https://github.com/) |  [<img src="/History/img/another/profile_7.jpg" width=150 > </br> @Jung EunJi](https://github.com/2735C)|



## ROLE

[SW]

|   | 김병현 | 박승범 | 김을중 | 정은지|
----|----|----|----|----
GUI 설계| UART 통신, BGM | 디자인| 시각 효과 구현| 랭킹보드 구현

[HW]

문우진

- 발표 자료 제작 및 발표
- SCCB 모듈 설계
- PIP, Ray Crossing 
- zybo board FPGA 
- zybo 기반 통합 Merge

김병현

- 전처리 필터 설계 (메디안? 가우시안?), Line Buffer 설계
- 색 검출 알고리즘 구현, 게임로직 FSM
- Basys3 기반 통합 Merge
- zybo board FPGA 
- 점수 계산 모듈 최적화 및 개선

김을중

- SCCB 모듈 설계
- 패턴 감지 모듈 설계
- zybo board FPGA 
- 점수 계산 모듈 최적화 및 개선

박승범

- 전처리 필터 설계 (메디안? 가우시안?)
- Basys3 기반 통합 Merge
- 점수 계산 모듈 최적화 및 개선

안재용

- zybo board FPGA 메인 담당
- Basys3 기반 통합 Merge
- 점수 계산 모듈 최적화 및 개선

오정일

- 전처리 필터 설계 (소벨 필터)
-  Systemverilog 기반 검증
- 패턴 감지 모듈 설계
- 패턴 제작

정은지

- 전처리 필터 설계 (소벨 필터), Systemverilog 기반 검증
- 색 검출 알고리즘 구현, 게임로직 FSM
- Basys3 기반 통합 Merge
- 점수 계산 모듈 최적화 및 개선



## 연구 배경
<img src="/History/img/hw/img_109.png" width=300 >|<img src="/History/img/hw/img_110.png" width=300 >|
--|--

현대 사회에 들어 지속적으로 우울증 환자들이 증가

→ 능동적인 활동을 통해 우울감 감소, 스트레스 해소에 도움이 되는 연구결과가 존재

<img src="/History/img/hw/img_111.png" width=300 >|<img src="/History/img/hw/img_112.png" width=300 >|
--|--

현재 K-POP은 전세게적으로 큰 인기를 끌고 있는 가운데 특히 K-POP DEMON HUNTERS라는 애니메이션은 남녀노소 어른아이 할 거 없이 좋아하며 선풍적인 인기를 얻고 있음.

<img src="/History/img/hw/img_113.png" width=300> | 
--|

K-POP DEMON HUNTERS의 춤추는 동작을 바탕으로한 모션 인식 게임을 통해 우울감, 스트레스 해소에 도움이 되고자 함.



## Game Rule

<table>
  <tr>
    <td align="center" width="400">
      <img src="https://github.com/2735C/VGA_Motion_Recognition_Game/blob/main/History/img/another/game_1.gif?raw=true" width="380" alt="게임 화면">
    </td>
    <td width="400">
      <span style="font-size:25px; font-weight:bold;">:one: 패턴을 확인한다. </span><br><br>
      <span style="font-size:25px; font-weight:bold;">:two: 패턴에 맞춰 몸을 맞춘다. </span><br><br>
      <span style="font-size:25px; font-weight:bold;">:three: 점수를 확인한다. </span><br><br>
      <span style="font-size:25px; font-weight:bold;">:four: 랭킹칸에 이름을 입력한다. </span><br><br>
    </td>
  </tr>
</table>


## 연구 일정 250911~250926

|               | 9/8~9/10| 9/11~9/13| 9/14~9/16|9/17~9/21|9/22~9/23|9/24~26|
--|--|--|--|--|--|--
|주제 선정| O|   |  |  |  |  |
|필터, SCCB 설계|  |  O |  |  |  |  | 
|GUI 설계|  |  | O |  |  |  |
|HW 설계|  |  | O | O | O |  |
|GUI 보충 및 HW 최적화|  |  |  |  |  | O |
|Zybo board|  | O | O |  | O |  |
|발표 자료 제작|  |  |  |  | O | O | 




## 프로젝트 과정

> 더 많은 내용을 확인하고 싶으면 --> [[발표 자료]](/Report/AI시스템반도체_발표용_1조_우리함께춤을.pdf)

### SW

> #### GUI

|START|SELECT|ENDING
---|--|--
|<img src="/History/img/sw/sw_1.png" alt="스위치 화면" width="400">|<img src="/History/img/sw/sw_2.png" alt="스위치 화면" width="400">|<img src="/History/img/sw/sw_6.png" alt="스위치 화면" width="400">

> #### SCORE

PERFECT|GOOD|BAD|
--|--|--
80% 이상 일치| 80%~50% 일치| 50% 미만 일치|
<img src="/History/img/sw/sw_3.png" alt="스위치 화면" width="400">|<img src="/History/img/sw/sw_4.png" alt="스위치 화면" width="400">|<img src="/History/img/sw/sw_5.png" alt="스위치 화면" width="400">|


### HW

> ### :one: Filter

#### (1) 전처리 필터 (Median / Gaussian)

소벨 필터의 노이즈 민감성을 보완하기 위해, 경계 검출 전에 스무딩(smoothing) 필터를 적용.
| 항목 | Median | Gaussian |
|---|---|---|
| 주 타겟 노이즈 | Salt & Pepper(임펄스) | 센서/가우시안 노이즈 |
| 작동 방식 | 중앙값 | 가중 평균 |
| 특징 | 에지 보존 성능 우수 | 연속적 블러, 에지 약화 |

| Median kernal (3x3) | Gaussian kernal (3x3) |
--|-- 
<img src="/History/img/hw/img_50.png" width=200 >|<img src="/History/img/hw/img_51.png" width=200 >|

#### median filter

```systemverilog
Sort #(.WIDTH(5)) U_Sort_R ( .din (r_data), .dout(sort_r_data)); // Red
Sort #(.WIDTH(6)) U_Sort_G ( .din (g_data), .dout(sort_g_data)); // Green
Sort #(.WIDTH(5)) U_Sort_B ( .din (b_data), .dout(sort_b_data));  // Blue

assign Median_result = {sort_r_data[4], sort_g_data[4], sort_b_data[4]};
```

####  gaussian filter

```systemverilog
assign red = (r_data[0] >> 4) + (r_data[1] >> 3) + (r_data[2] >> 4) + 
                 (r_data[3] >> 3) + (r_data[4] >> 1) + (r_data[5] >> 3) + 
                 (r_data[6] >> 4) + (r_data[7] >> 3) + (r_data[8] >> 4);

assign green = (g_data[0] >> 4) + (g_data[1] >> 3) + (g_data[2] >> 4) + 
                   (g_data[3] >> 3) + (g_data[4] >> 1) + (g_data[5] >> 3) + 
                   (g_data[6] >> 4) + (g_data[7] >> 3) + (g_data[8] >> 4);

assign blue = (b_data[0] >> 4) + (b_data[1] >> 3) + (b_data[2] >> 4) + 
                  (b_data[3] >> 3) + (b_data[4] >> 1) + (b_data[5] >> 3) + 
                  (b_data[6] >> 4) + (b_data[7] >> 3) + (b_data[8] >> 4);

assign Gaussian_Result = {red, green, blue};
```

#### (2) Sobel Filter

- 엣지 검출을 위한 대표적인 이미지 처리 기법 
- 이미지에서 픽셀의 밝기 값 변화를 이용해 경계선을 탐지

#### 🤔 Edge 검출 원리 

Centered Difference: $\frac{\partial I}{\partial x} = \frac{I(x+h) - I(x-h)}{2h}$

> 가운데를 기준으로 양쪽 값을 사용해 기울기 계산 → 편향 감소, 정확도 향상으로 안정적인 경계 검출 및 노이즈에 강함

 #### Edge 검출을 위한 Sobel Mask

|가로 방향 | 세로 방향|
--|--
<img src="/History/img/hw/img_1.png" width=150 >|<img src="/History/img/hw/img_2.png" width=150 >|

```systemverilog
localparam threshold = 1500;

assign xdata = data02 + (data12 << 1) + data22 - data00 - (data10 << 1) - data20;
assign ydata = data00 + (data01 << 1) + data02 - data20 - (data21 << 1) - data22;

assign absx = xdata[9] ? (~xdata + 1) : xdata;
assign absy = ydata[9] ? (~ydata + 1) : ydata;
assign sdata = (absx + absy > threshold) ? 1 : 0;
```


> ### :two: Parttern Algorithm

#### (1) Point In Polygon
- 어떤 점(Point)이 다각형(Polygon) 내부에 있는지 판별 <br>

|내/외부 판별 Algorithm | 핵심 기술|
--|--
|Ray Crossing | 단순 비교 나눗셈, 곱셈 연산|
|Winding Number | Vector 회전각 계산, 고정 소수점 연산|
|Triangle Fan | 삼각 분할 Data, Barycentric 좌표 연산|
|Bounding Volume | 사각 Grid, 공간 분할 연산|

> 여러 Algorithm 후보들 중에서 제한된 리소스를 가지고 구현할 수 있는 Ray Crossing 사용

- #### Ray Crossing

<img src="/History/img/hw/img_101.png" width=300> | <img src="/History/img/hw/img_102.png" width=300 >|<img src="/History/img/hw/img_103.png" width=300 >|
--|--|-- 

<!--
• 두쌍의 좌표를 입력 받아서 가상의 선분 생성 <br>
• x pixel의 위치가 왼쪽이면 0, 오른쪽이면 1 출력 <br>

-->

1) (x1,y1), (x2,y2) 두 점의 좌표 한 쌍으로 한 개의 선분 생성 <br>
2) 총 30개의 Module 병렬 실행 → Pattern 제작 <br>
3) x축에서 x좌표가 증가할 때마다 hit 횟수 Check (XOR 연산 : 홀수번 Hit = 1,짝수번 Hit = 0) <br>
> Pattern 내부 = 1, 외부 = 0 출력


#### (2) 패턴 구현 자동화 스크립트 (Python)

#### Issue

초기에는 수동으로 단순히 화면의 좌표를 직접 추출해 hex 코드로 변환해서 업로드

→ 측정오차, 비효율성, 비일관성

> 이러한 문제들을 해결하기 위해 파이썬을 이용해 패턴 구현 자동화 스크립트 구상

#### Process Flow
<img src="/History/img/hw/img_104.png" width=300> | 
--|
- 이미지를 불러온 후 사용하는 VGA 화면 크기로 맞춤
- 이미지 안에서 빨간색 테두리를 탐색
- 윤곽선을 꼭짓점 30개로 단순화
- 선택한 영역(x범위)에 맞추고 원하는 사이즈로 조정해서 바닥 정렬
- 꼭짓점을 연결한 선분 좌표를 추출해서 38비트로 packing → .hex 파일로 저장
- 결과를 미리보기로 확인하고, .hex 파일 다운로드

<img src="/History/img/hw/img_105.png" width=300> | 
--|


#### Result

|그림   |초기 ver | 최종 ver|
--|--|-- 
<img src="/History/img/hw/img_108.png" width=300 >|<img src="/History/img/hw/img_106.png" width=300 >|<img src="/History/img/hw/img_107.png" width=300 >|

> Auto pipeline 과정으로 정확성, 효율성, 일관성 확보





> ### :three: Color Detection Algorithm

- **색 검출 정확도를 올리기 위해서 RGB 방식 :arrow_right: HSV 방식 채택**

#### 🔙 RGB 방식

>  OpenCV 카메라로 게임에 사용할 빨간 장갑의 RGB 값 탐지

|RGB|8 bit(0~255)|4 bit(approx)(0~15)|
--|--|--
R |236| 236 * 15 / 255 ≈ 14
G |90|  90 * 15 / 255 ≈ 5
B |100| 100 * 15 / 255 ≈ 6


```systemverilog
// rgb565
assign red = (r5 >= 12) && (g6 <= 6) && (b5 <= 6); 
```

#### 🔜 HSV

레드 | RGB	| HSV
--|--|--
| # FF0000 | (255,0,0)	| (0 °, 100 %, 100 %)

#### RGB :arrow_right: HSV 변환 공식 활용

$C_{\max} = \max(R', G', B'), \quad 
C_{\min} = \min(R', G', B'), \quad 
\Delta = C_{\max} - C_{\min}$

$S = \frac{\Delta}{C_{\max}} \quad \text{if } C_{\max} \neq 0$



> 활용: 색조 및 채도 계산 방법 <br>
> 차이점: RGB666으로 최대한 원본 데이터 활용 → 데이터 손실, 오염 방지 가능

```systemverilog
// rgb666
assign max_val = (r6 > g6) ? ((r6 > b6) ? r6 : b6) : ((g6 > b6) ? g6 : b6);
assign min_val = (r6 < g6) ? ((r6 < b6) ? r6 : b6) : ((g6 < b6) ? g6 : b6);
assign delta = max_val - min_val;

assign r_is_max = (r6 > g6) && (r6 > b6) && (r6 > 32);
assign s_is_ok = (delta >= (max_val >> 2));

assign red = r_is_max && s_is_ok;
```


> ### :four: Uart
Uart Blockdiagram

<img src="/History/img/hw/img_52.png" width=600 > | <img src="/History/img/hw/img_53.png" width=600 >
--|--

Uart Sender FSM

<img src="/History/img/hw/img_54.png" width=600 >

<!--
|       구분      | 코드/비트 | 조건                | 송신 문자열 |
|:----------------:|:---------:|:--------------------:|:-----------:|
| **모드 선택**     | 0         | uart_mode_sel == 0  | 'qstick'  |
|                 | 1         | uart_mode_sel == 1  | 'golden'   |
|                 | 2         | uart_mode_sel == 2  | 'sodapop'  |
| **결과 플래그**   | 0         | result[0] == 1      | 'BAD'      |
|                 | 1         | result[1] == 1      | 'GOOD'     |
|                 | 2         | result[2] == 1      | 'PERFECT'  |

| 수신 문자열 | FSM 제어 신호 |
|:---------:|:------------:|
|'g'        | uart_sig = 1 |
|'s'        | uart_sig = 2 |
|'p'        | uart_sig = 1 |
|'f'        | uart_sig = 1 |
|'t'        | uart_sig = 1 |
-->

tx | rx
--|--
<img src="/History/img/hw/img_55.png" width=400 > | <img src="/History/img/hw/img_56.png" width=200 > 

> ### :five: Game FSM

<img src="/History/img/hw/img_57.png" width=600 >

## 시연 영상


## 🚀Trouble Shooting 
[⚒️[Trouble_Shooting1]](/History/trouble_shooting/Trouble_Shooting1.md)   <br>
[⚒️[Trouble_Shooting2]](/History/trouble_shooting/Trouble_Shooting2.md)  <br>
[⚒️[Trouble_Shooting3]](/History/trouble_shooting/Trouble_Shooting3.md) <br>


## 활용 분야
- **Home Fitness / Smart Home IoT**: 집에서 쉽게 따라하는 체조 및 동작 인식  
- **안전 모니터링**: 낙상 방지—지정 영역 이탈 감지 알람
- **K-POP 챌린지**: 점수 공유/영상 업로드로 **SNS 확산** 기대
