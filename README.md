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

| 항목 | Median | Gaussian |
|---|---|---|
| 주 타겟 노이즈 | Salt & Pepper(임펄스) | 센서/가우시안 노이즈 |
| 작동 방식 | 중앙값 | 가중 평균 |
| 특징 | 에지 보존 성능 우수 | 연속적 블러, 에지 약화 |

| Median kernal | Gaussian kernal |
--|-- 
<img src="/History/img/hw/img_50.png" width=200 >|<img src="/History/img/hw/img_51.png" width=200 >|

```systemverilog
// -------------------------
//       median filter
// -------------------------
Sort #(.WIDTH(5)) U_Sort_R (  // Red
        .din (r_data),  // 5비트
        .dout(sort_r_data)
    );

Sort #(.WIDTH(6)) U_Sort_G (  // Green
    .din (g_data),  // 6비트
    .dout(sort_g_data)
);

Sort #(.WIDTH(5)) U_Sort_B (  // Blue
    .din (b_data),  // 5비트
    .dout(sort_b_data)
);

assign Median_result = {sort_r_data[4], sort_g_data[4], sort_b_data[4]};

// -------------------------
//      gaussian filter
// -------------------------
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

(1) Point In Polygon
- 어떤 점(Point)이 다각형(Polygon) 내부에 있는지 판별 <br>

|내/외부 판별 Algorithm | 핵심 기술|
--|--
|Ray Crossing | 단순 비교 나눗셈, 곱셈 연산|
|Winding Number | Vector 회전각 계산, 고정 소수점 연산|
|Triangle Fan | 삼각 분할 Data, Barycentric 좌표 연산|
|Bounding Volume | 사각 Grid, 공간 분할 연산|

> 여러 Algorithm 후보들 중에서 제한된 리소스를 가지고 구현할 수 있는 Ray Crossing 사용

- Ray Crossing <br>
<img src="/History/img/hw/img_101.png" alt="스위치 화면" width="400"> <br>
두쌍의 좌표를 입력 받아서 가상의 선분 생성 <br>
x pixel의 위치가 왼쪽이면 0, 오른쪽이면 1 출력 <br> <br>


<img src="/History/img/hw/img_102.png" width=300 >|<img src="/History/img/hw/img_103.png" width=300 >|
--|-- 


총 30개의 Module 병렬 실행 → Pattern 제작 <br>
Pattern 내부 = 1, 외부 = 0 출력


(2) 패턴 구현 자동화 스크립트 (Python)

> ### :three: Uart

## 시연 영상


## 🚀Trouble Shooting 
[⚒️[Trouble_Shooting1]](/History/trouble_shooting/Trouble_Shooting1.md)   <br>
[⚒️[Trouble_Shooting2]](/History/trouble_shooting/Trouble_Shooting2.md)  <br>
[⚒️[Trouble_Shooting3]](/History/trouble_shooting/Trouble_Shooting3.md) <br>


