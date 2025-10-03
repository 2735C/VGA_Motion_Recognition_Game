## [GAME STATE 전환 X]

### 1️⃣ 문제점

| <img src="https://raw.githubusercontent.com/2735C/VGA_Motion_Recognition_Game/main/History/img/another/uart_troubleshooting.gif" width="380"> | <img src="https://raw.githubusercontent.com/2735C/VGA_Motion_Recognition_Game/main/History/img/hw/img_66.png" width="500"> |
|:--:|:--:|

### 2️⃣ 예상 원인
- UART RX_DATA 수신 Error 예상 ➡️ UART Simulation 결과 정상 

<img src="https://raw.githubusercontent.com/2735C/VGA_Motion_Recognition_Game/main/History/img/hw/img_67.png" width="800"> |
--|

- FSM 이동 조건 타이밍 Miss로 예상 ➡️ FSM 구조 집중 수정 (해결 x)

### 3️⃣ 실제 원인
**RX_FIFO POP 신호 미연결** ➡️ 처음 RX_Data 수신 후 Update 불가

<img src="https://raw.githubusercontent.com/2735C/VGA_Motion_Recognition_Game/main/History/img/hw/img_68.png" width="700"> |
--|

### 4️⃣ 해결 방법

Rx_Data 수신이 완료될 때 마다 Pop 신호 출력

<img src="https://raw.githubusercontent.com/2735C/VGA_Motion_Recognition_Game/main/History/img/hw/img_69.png" width="700"> |
--|