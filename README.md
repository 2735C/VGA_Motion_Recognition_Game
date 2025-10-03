# AI 반도체 설계 2기 Final Project

## 팀원 


|Team Leader|Team Member1|Team Member2| 
--|--|--|
| [<img src="/History/img/another/profile_1.png" width=150 > </br> @문우진](https://github.com/) |  [<img src="/History/img/another/profile_2.png" width=150 > </br> @김병현](https://github.com/)|  [<img src="/History/img/another/profile_3.png" width=150 > </br> @김을중](https://github.com/)| 

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

(1) 

(2) Sobel 

> ### :two: Parttern Algorithm

> ### :three: Uart

## 시연 영상


## 🚀Trouble Shooting 
[⚒️[Trouble_Shooting1]](/History/trouble_shooting/Trouble_Shooting1.md)   <br>
[⚒️[Trouble_Shooting2]](/History/trouble_shooting/Trouble_Shooting2.md)  <br>
[⚒️[Trouble_Shooting3]](/History/trouble_shooting/Trouble_Shooting3.md) <br>


