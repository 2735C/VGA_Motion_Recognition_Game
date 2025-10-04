## [CDC(Clock Domain Crossing) Issue ]

### 🔥 문제: 화면 밀림 이슈

> 세부 사항:
 - GUI 화면 전환에 **빨간색 객체 탐지**가 사용되는데, **CDC 문제**로 인하여 **화면이 밀려** 4, 5, 6번의 우측 가장자리에 빨간색을 가져다 대면 1, 2, 3 번 화면 좌측 가장자리에서 빨간색이 검출된 것으로 인식되는 문제 발생
 - 즉, **설계자가 정한 구역이 아니더라도 빨간색이 검출되면 GUI 화면이 넘어감**

 > 화면 예시 

 <img src="/History/img/hw/img_14.png" width=500 >|<img src="/History/img/hw/img_15.png" width=500 >|
 --|--


### ⏳🔧 임시방편

- 빨간색 감지에 사용되는 영역에 마진을 주어 문제 방지


문제 상황| 해결 방법
--|--
 <img src="/History/img/hw/img_16.png" width=500 >| <img src="/History/img/hw/img_17.png" width=500 >|
 <img src="/History/img/hw/img_11.png" width=500 >| <img src="/History/img/hw/img_10.png" width=500 >|


### 🤩 최종 해결 방법

#### 🤔 원인: 

CLK Type: 1. system clk 100MHz 2. pclk(OV7670 → FPGA) 25MHz

:arrow_right: 비디오/패턴 경로 레이턴시 불일치


:arrow_right:  3FF Synchronizer를 사용하여 Display 모듈에 연결되는 타이밍을 맞춰준 결과 화면이 더 이상 밀리지 않고 정상적으로 출력되었다. 

🔙 수정 전|🔜 해결 후
--|--
 <img src="/History/img/hw/img_12.png" width=500 >| <img src="/History/img/hw/img_13.png" width=500 >|


 ✅ 3FF Synchronizer를 사용 → 타이밍 mismatch 해결
 ☑️ 화면이 더 이상 밀리지 않고 정상적으로 출력됨