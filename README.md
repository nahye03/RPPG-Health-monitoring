# remote-Health-monitoring
> Remote PPG를 활용한 Health Monitoring SW

## Table of Contents
1. 주요기술
2. UI
3. Demo
4. Code
5. 성과

## 1. 주요기술
### remote PPG 신호 측정
- 단일 RGB 카메라를 통해 비접촉식으로 PPG를 측정할 수 있는 기술
- 얼굴 피부색 변화를 통해 PPG 신호 추출

### restored rPPG 신호 추출
- remote PPG 신호를 contact PPG 신호 수준으로 복원하는 기술
- SVR + Deep learning 모델을 활용하여 신호 복원
- 논문 : [Restoration of Remote PPG Signal through Correspondence with Contact Sensor Signal](https://www.mdpi.com/1424-8220/21/17/5910)

### 산소포화도 신호 추출
- remote PPG 신호에서 헤모글로빈의 영향을 받는 신호를 활용하여 산소포화도 신호를 추출하는 기술
- RGB color space를 YCgCr color space로 변환한 후 계산을 통해 산소포화도 추출
- 논문 : [Non-Contact Oxygen Saturation Measurement Using YCgCr Color Space with an RGB Camera](https://www.mdpi.com/1424-8220/21/18/6120)

### HRV 추출
- remote PPG 신호에서 자율신경계의 변화로 인해 발생하는 심장 박동을 변화인 HRV 추출
- time domain과 frequency domain에서의 HRV 지표 추출
- 논문 : [Pulse Rate Variability Analysis Using Remote Photoplethysmography Signals](https://www.mdpi.com/1424-8220/21/18/6241)

## UI
<p><img src="https://user-images.githubusercontent.com/54797864/212313030-f9f00083-448e-4752-b8e5-d87af4776bc6.png"  width="60%"></p>

## Demo
[![Video Label](http://img.youtube.com/vi/CxKecaLFaLk/0.jpg)](https://youtu.be/CxKecaLFaLk)

## Code
- [model](https://github.com/nahye03/remote-Health-monitoring/tree/main/model) : face detect model
- [model_rppg](https://github.com/nahye03/remote-Health-monitoring/tree/main/model_rppg) : restored PPG 추출에 필요한 model
- [uti](https://github.com/nahye03/remote-Health-monitoring/tree/main/uti) : face tracking, skin ROI model
- [UI_9.py](https://github.com/nahye03/remote-Health-monitoring/blob/main/UI_9.py) : main file
- [analysis_functions](https://github.com/nahye03/remote-Health-monitoring/blob/main/analysis_functions.py) : mean_pulserate, spo2, hrv, restored ppg 신호 추출 함수
- [functions](https://github.com/nahye03/remote-Health-monitoring/blob/main/functions.py) : analysis_functions에 필요한 함수들
- [get_rgb_funcionts](https://github.com/nahye03/remote-Health-monitoring/blob/main/get_rgb_function.py) : 얼굴 영역에서 R, G, B 성분 추출
- [monitoring_5.ui](https://github.com/nahye03/remote-Health-monitoring/blob/main/monitoring_5.ui) : 전체 UI
- [result_dialog.py](https://github.com/nahye03/remote-Health-monitoring/blob/main/result_dialog.py) : 분석 결과창 UI

## 성과
"Non-contact Bio-marker Monitoring Using Remote Photoplethysmography," 제40회 한국법과학회 추계학술대회, 2021.11.23 ~ 2021.11.30, 온라인.
