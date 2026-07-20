# 몸 찾기

## 인스턴스 선언

몸 찾기(BodyDetection) 블록을 작업 영역에 추가하면, Python 코드에는 다음과 같은 인스턴스 선언이 자동으로 삽입됩니다:

```python
body_detection = BodyDetection(0)
# 여러 인스턴스가 있는 경우
body_detection_1 = BodyDetection(1)
```

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| index | 드롭다운 옵션 | 인스턴스 번호 (0부터 시작) | 0 이상 정수 | 0 |


<br>

# 블록 <-> 파이썬 변환 규칙

## 카메라 장치 선택하기

몸 찾기를 위한 카메라를 설정합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/BodyDetection/1.png" alt="카메라 장치 선택하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 카메라 장치 이름 | 시스템 카메라 라벨 | - |

<!-- 
### JavaScript
```javascript
$('BodyDetection*0:camera.device_id').d = __cameraId('FaceTime HD Camera');
```
-->

### Python
```python
body_detection = BodyDetection(0)

body_detection.device('')
```

---

## 모델 로드하기

학습된 몸 모델을 불러옵니다. '몸 찾기' 모듈의 기능들을 사용하기 위해서는 이 작업이 반드시 필요합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/BodyDetection/2.png" alt="모델 로드하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| wait | 체크박스 | 로드 완료 대기 여부 | TRUE / FALSE | TRUE |

<!-- 
### JavaScript
```javascript
$('BodyDetection*0:load_model').d = 1;
await $('BodyDetection*0:!load_model').w();   // wait = TRUE
```
-->

### Python
```python
body_detection = BodyDetection(0)

body_detection.load_model(wait=True)
```

---

## 한 번 인식하기

현재 화면에 있는 몸을 찾아 딱 한번 표시합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/BodyDetection/3.png" alt="한 번 인식하기">

### 매개변수

(없음)

<!-- 
### JavaScript
```javascript
$('BodyDetection*0:detect.once').d = 1;
```
-->

### Python
```python
body_detection = BodyDetection(0)

body_detection.detect_once()
```

---

## 연속 인식 시작 / 중지

현재 화면에 있는 몸을 계속해서 따라가며 화면 상에 표시합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/BodyDetection/4.png" alt="연속 인식 시작 / 중지">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 동작 | 시작(start), 중지(stop) | - |

<!-- 
### JavaScript
```javascript
$('BodyDetection*0:detect.continuous').d = 1;
```
-->

### Python
```python
body_detection = BodyDetection(0)

# unit = "start"
body_detection.detect_continuous()
# unit = "stop"
body_detection.stop()
```

---

## 인식 화면 표시하기

카메라 화면에 몸 찾기 결과를 표시할지 말지를 결정합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/BodyDetection/5.png" alt="인식 화면 표시하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| on | 드롭다운 옵션 | 표시 ON / OFF | 표시(on=True), 숨기기(off=False) | TRUE |

<!-- 
### JavaScript
```javascript
$('BodyDetection*0:display').d = 1;
```
-->

### Python
```python
body_detection = BodyDetection(0)

body_detection.display(True)
body_detection.display(False)
```

---

## 신체 부위 좌표

신체 부위별 좌표를 반환합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/BodyDetection/6.png" alt="신체 부위 좌표">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 신체 부위 | 코(nose), 입(mouth), 왼눈(left eye), 오른눈(right eye), 왼귀(left ear), 오른귀(right ear), 왼쪽 어깨(left shoulder), 오른쪽 어깨(right shoulder), 왼쪽 팔꿈치(left elbow), 오른쪽 팔꿈치(right elbow), 왼쪽 손목(left wrist), 오른쪽 손목(right wrist), 왼손(left hand), 오른손(right hand), 왼쪽 엉덩이(left hip), 오른쪽 엉덩이(right hip), 왼쪽 무릎(left knee), 오른쪽 무릎(right knee), 왼쪽 발목(left ankle), 오른쪽 발목(right ankle), 왼발(left foot), 오른발(right foot) | - |
| pos | 드롭다운 옵션 | 좌표 | x, y | - |

<!-- 
### JavaScript
```javascript
$('BodyDetection*0:nose.x').d
$('BodyDetection*0:shoulder.left.y').d
```
-->

### Python
```python
body_detection = BodyDetection(0)

body_detection.nose('x')
body_detection.mouth('y')
body_detection.left_eye('x')
body_detection.right_shoulder('y')
body_detection.left_hand('x')
```

---

## 두 부위 사이 거리

신체 부위 두 곳 사이의 거리를 반환합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/BodyDetection/7.png" alt="두 부위 사이 거리">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit1 | 드롭다운 옵션 | 첫 번째 신체 부위 | (위 신체 부위 표 참조) | - |
| unit2 | 드롭다운 옵션 | 두 번째 신체 부위 | (위 신체 부위 표 참조) | - |
| type | 드롭다운 옵션 | 거리 종류 | 거리(생략 또는 None), 가로 거리(horizontal), 세로 거리(vertical) | None |

<!-- 
### JavaScript
```javascript
// distance
Math.sqrt( Math.pow(($('BodyDetection*0:shoulder.right.x').d - $('BodyDetection*0:shoulder.left.x').d), 2) + Math.pow(($('BodyDetection*0:shoulder.right.y').d - $('BodyDetection*0:shoulder.left.y').d), 2) )
```
-->

### Python
```python
body_detection = BodyDetection(0)

body_detection.get_distance('left_shoulder', 'right_shoulder')  # 거리
body_detection.get_distance('left_wrist', 'right_wrist', 'horizontal')  # 가로 거리
body_detection.get_distance('left_hip', 'left_knee', 'vertical')  # 세로 거리
```

---

## 모델 상태

몸 모델 로딩 상태를 반환합니다.  
아직 불러오지 않았으면 0, 불러오는 중이면 1, 불러오기를 완료했으면 2를 반환합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/BodyDetection/8.png" alt="모델 상태">

### 매개변수

(없음)

<!-- 
### JavaScript
```javascript
$('BodyDetection*0:model_state').d
```
-->

### Python
```python
body_detection = BodyDetection(0)

body_detection.model_state()
```

---

## 신체 감지 여부

몸을 찾았는지 여부

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/BodyDetection/9.png" alt="신체 감지 여부">

### 매개변수

(없음)

<!-- 
### JavaScript
```javascript
$('BodyDetection*0:detected').d
```
-->

### Python
```python
body_detection = BodyDetection(0)

body_detection.detected()
```
