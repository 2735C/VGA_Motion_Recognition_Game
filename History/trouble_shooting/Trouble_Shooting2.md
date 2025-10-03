## [GAME STATE 전환 X]

### 1️⃣ 문제점 1 

| <img src="https://raw.githubusercontent.com/2735C/VGA_Motion_Recognition_Game/main/History/img/another/uart_troubleshooting.gif" width="380"> | <img src="https://raw.githubusercontent.com/2735C/VGA_Motion_Recognition_Game/main/History/img/hw/img_66.png" width="500"> |
|:--:|:--:|

### 2️⃣ 예상 원인
- UART RX_DATA 수신 Error ➡️ UART Simulation 결과 정상 

<img src="https://raw.githubusercontent.com/2735C/VGA_Motion_Recognition_Game/main/History/img/hw/img_67.png" width="500">

- FSM 이동 조건 타이밍 Miss ➡️ FSM 구조 집중 수정