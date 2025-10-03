[점수 게산 Error]

### 문제

<td align="center" width="400">
      <img src="https://github.com/2735C/VGA_Motion_Recognition_Game/blob/main/History/img/another/game_2.gif?raw=true" width="380">


<br>
<img src="/History/img/hw/img_114.png" width=300> | 
--|

기존 Logic 

: flag on 되는 순간에 (0,0)부터 flag off 되는 (639, 479)까지 점수로 판별하고자 하는 부분을 Count

(Pattern 내부) & (Chroma 영역 X) : Green Count ++

(Pattern 외부) & (Chroma 영역 X) : Red Count ++ 

$$
\text{Score} = \frac{\textcolor{green}{\text{Green cnt}}}{\textcolor{green}{\text{Green cnt}} + \textcolor{red}{\text{Red cnt}}} \times 100
$$

### 원인
결
### 해결

