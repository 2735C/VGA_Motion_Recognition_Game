## [패턴 구현 자동화 스크립트 (Python)]

### 🔥 문제

초기에는 수동으로 단순히 화면의 좌표를 직접 추출해 hex 코드로 변환해서 업로드

:arrow_right: 측정오차, 비효율성, 비일관성

### 🤩 해결 방법

이러한 문제들을 해결하기 위해 파이썬을 이용해 패턴 구현 자동화 스크립트 구상

> #### Process Flow

<img src="/History/img/hw/img_104.png" width=300> | 
--|

- 이미지를 불러온 후 사용하는 VGA 화면 크기로 맞춤
- 이미지 안에서 빨간색 테두리를 탐색
- 윤곽선을 꼭짓점 30개로 단순화
- 선택한 영역(x범위)에 맞추고 원하는 사이즈로 조정해서 바닥 정렬
- 꼭짓점을 연결한 선분 좌표를 추출해서 38비트로 packing → .hex 파일로 저장
- 결과를 미리보기로 확인하고, .hex 파일 다운로드

<img src="/History/img/hw/img_105.png" width=500> | 
--|


> #### Result

|그림   |초기 ver | 최종 ver|
--|--|-- 
<img src="/History/img/hw/img_108.png" width=200 >|<img src="/History/img/hw/img_106.png" width=300 >|<img src="/History/img/hw/img_107.png" width=300 >|

:arrow_right:  Auto pipeline 과정으로 정확성, 효율성, 일관성 확보

