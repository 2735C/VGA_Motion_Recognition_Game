## [점수 계산 Error]

### 🔥 문제: 평가 기준 Perfect/Good/Bad 중 Bad만 출력되는 현상 


<img src="https://github.com/2735C/VGA_Motion_Recognition_Game/blob/main/History/img/another/game_2.gif?raw=true" width="380">|
--|

> #### 세부 문제

1. **로직에 문제**가 존재
2. 하지만, 로직을 수정하기에는 이미 **LUT가 99%**


### 🤩 문제 해결 1: LUT 축소 (4% 🔽)

> ### 기존 Logic: Register를 사용하여 결과 저장

```systemverilog
assign score = ((temp_grn_cnt_reg * 10) / (temp_grn_cnt_reg + temp_red_cnt_reg));

assign perfect = (score >= 8) ? 1'b1 : 1'b0;
assign good    = ((score >= 5) && (score < 8)) ? 1'b1 : 1'b0;
assign bad     = (score < 5) ? 1'b1 : 1'b0;

assign result = {perfect, good, bad}; 
// 3'b100 : perfect, 3'b010 : good, 3'b001 : bad
```

> ### 수정 Logic: 삼항 연산자를 사용해 결과를 저장 ✖️, 비교 ⭕

```systemverilog
logic [22:0] sum = temp_grn_cnt_reg + temp_red_cnt_reg;

// result = {perfect, good, bad}
assign result =  (temp_grn_cnt_reg * 5 >= (sum << 2)) ? 3'b100 : ((temp_grn_cnt_reg << 1) < sum) ? 3'b001 : 3'b010; 
```

### 🤩 문제 해결 2:  Porch 영역 Count 배제

> ### 기존 Logic 

:arrow_right: flag on 되는 순간에 (0,0)부터 flag off 되는 (639, 479)까지 점수로 판별하고자 하는 부분을 Count

<img src="/History/img/hw/img_114.png" width=300> | (Pattern 내부) & (Chroma 영역 X) : Green Count ++ <br> (Pattern 외부) & (Chroma 영역 X) : Red Count ++ <br> <img src="/History/img/hw/img_8.png" width=300> |
--|--


(Pattern 내부) & (Chroma 영역 X) : Green Count ++|
--|
(Pattern 외부) & (Chroma 영역 X) : Red Count ++ |

$$
\text{Score} = \frac{\textcolor{green}{\text{Green cnt}}}{\textcolor{green}{\text{Green cnt}} + \textcolor{red}{\text{Red cnt}}} \times 100
$$

### ❗원인
<img src="/History/img/hw/img_115.png" width=300> |
--|

* Porch 영역까지 Count 되어서 생각했던 것보다 더 많은 Red가 Count됨.

     *  Porch 영역 : Display 영역 출력 전/후 Sync를 맞추기 위한 Margin영역
역

### 🤩 해결 방법 

:arrow_right: VGA Decoder의 DE 신호를 받아서 처리 -> 유효한 픽셀의 수만 Count(640x480)
