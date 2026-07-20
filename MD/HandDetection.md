# 손 찾기

## 인스턴스 선언

손 찾기(HandDetection) 블록을 작업 영역에 추가하면, Python 코드에는 다음과 같은 인스턴스 선언이 자동으로 삽입됩니다:

```python
hand_detection = HandDetection(0)
# 여러 인스턴스가 있는 경우
hand_detection_1 = HandDetection(1)
```

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| index | 드롭다운 옵션 | 인스턴스 번호 (0부터 시작) | 0 이상 정수 | 0 |


<br>

# 블록 <-> 파이썬 변환 규칙

## 카메라 장치 선택하기

손 찾기를 위한 카메라를 설정합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/HandDetection/1.png" alt="카메라 장치 선택하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 카메라 장치 이름 | 시스템 카메라 라벨 | - |

<!-- 
### JavaScript
```javascript
$('HandDetection*0:camera.device_id').d = __cameraId('FaceTime HD Camera');
```
-->

### Python
```python
hand_detection = HandDetection(0)

hand_detection.device('')
```

---

## 모델 로드하기

학습된 손 모델을 불러옵니다. '손 찾기' 모듈의 기능들을 사용하기 위해서는 이 작업이 반드시 필요합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/HandDetection/2.png" alt="모델 로드하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| wait | 체크박스 | 로드 완료 대기 여부 | TRUE / FALSE | TRUE |

<!-- 
### JavaScript
```javascript
$('HandDetection*0:load_model').d = 1;
await $('HandDetection*0:!load_model').w();   // wait = TRUE
```
-->

### Python
```python
hand_detection = HandDetection(0)

hand_detection.load_model(wait=True)
```

---

## 최대 손 수 설정하기

손을 찾을 때, 한 손을 기준으로 찾을지, 양손을 기준으로 찾을지 결정합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/HandDetection/3.png" alt="최대 손 수 설정하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 손 개수 | 한 손(one), 두 손(both) | - |

<!-- 
### JavaScript
```javascript
$('HandDetection*0:max_count').d = 1;   // one
$('HandDetection*0:max_count').d = 2;   // both
```
-->

### Python
```python
hand_detection = HandDetection(0)

hand_detection.max_hands('one')
hand_detection.max_hands('both')
```

---

## 한 번 인식하기

현재 화면에 있는 손을 찾아 딱 한번 표시합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/HandDetection/4.png" alt="한 번 인식하기">

### 매개변수

(없음)

<!-- 
### JavaScript
```javascript
$('HandDetection*0:detect.once').d = 1;
```
-->

### Python
```python
hand_detection = HandDetection(0)

hand_detection.detect_once()
```

---

## 연속 인식 시작 / 중지

현재 화면에 있는 손을 계속해서 따라가며 화면 상에 표시합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/HandDetection/5.png" alt="연속 인식 시작 / 중지">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 동작 | 시작(start), 중지(stop) | - |

<!-- 
### JavaScript
```javascript
$('HandDetection*0:detect.continuous').d = 1;
```
-->

### Python
```python
hand_detection = HandDetection(0)

# unit = "start"
hand_detection.detect_continuous()
# unit = "stop"
hand_detection.stop()
```

---

## 인식 화면 표시하기

카메라 화면에 손 찾기 결과를 표시할지 말지를 결정합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/HandDetection/6.png" alt="인식 화면 표시하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| on | 드롭다운 옵션 | 표시 ON / OFF | 표시(on=True), 숨기기(off=False) | TRUE |

<!-- 
### JavaScript
```javascript
$('HandDetection*0:display').d = 1;
```
-->

### Python
```python
hand_detection = HandDetection(0)

hand_detection.display(True)
hand_detection.display(False)
```

---

## 손 부위 좌표

지정한 손의 손바닥/손목 위치 정보를 반환합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/HandDetection/7.png" alt="손 부위 좌표">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| side | 드롭다운 옵션 | 손 방향 | 왼손(left), 오른손(right) | - |
| unit | 드롭다운 옵션 | 손 부위 | 손바닥(palm), 손목(wrist) | - |
| pos | 드롭다운 옵션 | 좌표/크기 종류 | x, y | - |

<!-- 
### JavaScript
```javascript
$('HandDetection*0:left.palm.x').d
$('HandDetection*0:right.wrist.y').d
$('HandDetection*0:left.hand.min_x').d
```
-->

### Python
```python
hand_detection = HandDetection(0)

hand_detection.hand('left', 'palm', 'x')
hand_detection.hand('right', 'wrist', 'y')
hand_detection.hand('left', 'hand', 'min_x')
hand_detection.hand('right', 'palm', 'width')
```

---

## 손가락 관절 좌표

지정한 손가락의 관절 좌표를 반환합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/HandDetection/8.png" alt="손가락 관절 좌표">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| side | 드롭다운 옵션 | 손 방향 | 왼손(left), 오른손(right) | - |
| unit | 드롭다운 옵션 | 손가락 | 엄지(thumb), 검지(index), 중지(middle), 약지(ring), 새끼(pinky) | - |
| joint | 드롭다운 옵션 | 관절 위치 | 첫째 마디(first), 둘째 마디(second), 셋째 마디(third), 끝(last) | - |
| pos | 드롭다운 옵션 | 좌표 | x, y | - |

<!-- 
### JavaScript
```javascript
$('HandDetection*0:left.index.first.x').d
```
-->

### Python
```python
hand_detection = HandDetection(0)

hand_detection.finger('left', 'index', 'first', 'x')
hand_detection.finger('right', 'thumb', 'last', 'y')
```

---

## 손 사각형 정보

지정한 손 영역 사각형의 위치/크기 값을 반환합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/HandDetection/9.png" alt="손 사각형 정보">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| side | 드롭다운 옵션 | 손 방향 | 왼손(left), 오른손(right) | - |
| unit | 드롭다운 옵션 | 손 부위 | 손(hand), 손바닥(palm) | - |
| pos | 드롭다운 옵션 | | 사각형 정보 | 최소 x(min_x), 최대 x(max_x), 최소 y(min_y), 최대 y(max_y), 폭(width), 높이(height), 넓이(area) | - |

<!-- 
### JavaScript
```javascript
$('HandDetection*0:left.palm.x').d
$('HandDetection*0:right.wrist.y').d
$('HandDetection*0:left.hand.min_x').d
```
-->

### Python
```python
hand_detection = HandDetection(0)

hand_detection.hand('left', 'hand', 'min_x')
hand_detection.hand('right', 'palm', 'width')
```

---

## 손과 손 사이 거리

두 손 부위 사이의 거리를 반환합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/HandDetection/10.png" alt="손과 손 사이 거리">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit1 | 입력값 (문자열) | 첫 번째 손 부위 | 손: `'side_unit'` (예: `'left_palm'`). side=left/right, unit=palm/wrist/hand  | - |
| unit2 | 입력값 (문자열) | 두 번째 손 부위 | 손: `'side_unit'` (예: `'right_palm'`). side=left/right, unit=palm/wrist/hand, | - |
| type | 드롭다운 옵션 | 거리 종류 | 거리(생략 또는 None), 가로 거리(horizontal), 세로 거리(vertical) | None |

<!-- 
### JavaScript
```javascript
// hand_to_hand
Math.sqrt( Math.pow(($('HandDetection*0:right.palm.x').d - $('HandDetection*0:left.palm.x').d), 2) + Math.pow(($('HandDetection*0:right.palm.y').d - $('HandDetection*0:left.palm.y').d), 2) )
```
-->

### Python
```python
hand_detection = HandDetection(0)

# 손 ↔ 손 / 거리
hand_detection.get_distance('left_palm', 'right_palm')  
```

---

## 손과 손가락 사이 거리

손 부위와 손가락 관절 사이의 거리를 반환합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/HandDetection/11.png" alt="손과 손가락 사이 거리">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit1 | 입력값 (문자열) | 첫 번째 부위 | 손: `'side_unit'` (예: `'left_palm'`).side=left/right, unit=palm/wrist/hand | - |
| unit2 | 입력값 (문자열) | 두 번째 부위 | 손가락: `'side_unit_joint'` (예: `'right_index_first'`). unit=thumb/index/middle/ring/pinky, joint=first/second/third/last | - |
| type | 드롭다운 옵션 | 거리 종류 | 거리(생략 또는 None), 가로 거리(horizontal), 세로 거리(vertical) | None |

<!-- 
### JavaScript
```javascript
// hand_to_joint
Math.sqrt( Math.pow(($('HandDetection*0:right.index.first.x').d - $('HandDetection*0:left.palm.x').d), 2) + Math.pow(($('HandDetection*0:right.index.first.y').d - $('HandDetection*0:left.palm.y').d), 2) )
```
-->

### Python
```python
hand_detection = HandDetection(0)

# 손 ↔ 손가락 관절 / 가로 거리
hand_detection.get_distance('left_palm', 'right_index_first')
```

---

## 손가락과 손가락 사이 거리

두 손가락 관절 사이의 거리를 반환합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/HandDetection/12.png" alt="손가락과 손가락 사이 거리">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit1 | 입력값 (문자열) | 첫 번째 부위 | 손가락: `'side_unit_joint'` (예: `'left_thumb_last'`). unit=thumb/index/middle/ring/pinky, joint=first/second/third/last | - |
| unit2 | 입력값 (문자열) | 두 번째 부위 | 손가락: `'side_unit_joint'` (예: `'right_index_first'`). unit=thumb/index/middle/ring/pinky, joint=first/second/third/last | - |
| type | 드롭다운 옵션 | 거리 종류 | 거리(생략 또는 None), 가로 거리(horizontal), 세로 거리(vertical) | None |

<!-- 
### JavaScript
```javascript
// joint_to_joint
Math.sqrt( Math.pow(($('HandDetection*0:right.index.last.x').d - $('HandDetection*0:left.thumb.last.x').d), 2) + Math.pow(($('HandDetection*0:right.index.last.y').d - $('HandDetection*0:left.thumb.last.y').d), 2) )
```
-->

### Python
```python
hand_detection = HandDetection(0)

# 손가락 관절 ↔ 손가락 관절 / 세로 거리
hand_detection.get_distance('left_thumb_last', 'right_index_first', 'vertical')
```

---

## 모델 상태

손 모델 로딩 상태를 반환합니다.  
아직 불러오지 않았으면 0, 불러오는 중이면 1, 불러오기를 완료했으면 2를 반환합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/HandDetection/13.png" alt="모델 상태">

### 매개변수

(없음)

<!-- 
### JavaScript
```javascript
$('HandDetection*0:model_state').d
```
-->

### Python
```python
hand_detection = HandDetection(0)

hand_detection.model_state()
```

---

## 손 감지 여부

손을 찾았는지 여부

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/HandDetection/14.png" alt="손 감지 여부">

### 매개변수

(없음)

<!-- 
### JavaScript
```javascript
$('HandDetection*0:detected').d
```
-->

### Python
```python
hand_detection = HandDetection(0)

hand_detection.detected()
```
