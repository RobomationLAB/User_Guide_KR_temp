# 상세하게 얼굴 찾기

## 인스턴스 선언

상세하게 얼굴 찾기(DetailedFaceDetection) 블록을 작업 영역에 추가하면, Python 코드에는 다음과 같은 인스턴스 선언이 자동으로 삽입됩니다:

```python
detailed_face_detection = DetailedFaceDetection(0)
# 여러 인스턴스가 있는 경우
detailed_face_detection_1 = DetailedFaceDetection(1)
```

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| index | 드롭다운 옵션 | 인스턴스 번호 (0부터 시작) | 0 이상 정수 | 0 |


<br>

# 블록 <-> 파이썬 변환 규칙

## 카메라 장치 선택하기

상세하게 얼굴 찾기를 위한 카메라를 설정합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/DetailedFaceDetection/1.png" alt="카메라 장치 선택하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 카메라 장치 이름 | 시스템 카메라 라벨 | - |

<!-- 
### JavaScript
```javascript
$('DetailedFaceDetection*0:camera.device_id').d = __cameraId('FaceTime HD Camera');
```
-->

### Python
```python
detailed_face_detection = DetailedFaceDetection(0)

detailed_face_detection.device('')
```

---

## 모델 로드하기

학습된 얼굴 모델을 불러옵니다. '상세하게 얼굴 찾기' 모듈의 기능들을 사용하기 위해서는 이 작업이 반드시 필요합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/DetailedFaceDetection/2.png" alt="모델 로드하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| wait | 체크박스 | 로드 완료 대기 여부 | TRUE / FALSE | TRUE |

<!-- 
### JavaScript
```javascript
$('DetailedFaceDetection*0:load_model').d = 1;
await $('DetailedFaceDetection*0:!load_model').w();   // wait = TRUE
```
-->

### Python
```python
detailed_face_detection = DetailedFaceDetection(0)

detailed_face_detection.load_model(wait=True)
```

---

## 한 번 인식하기

현재 화면에 있는 얼굴을 찾아 딱 한번 표시합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/DetailedFaceDetection/3.png" alt="한 번 인식하기">

### 매개변수

(없음)

<!-- 
### JavaScript
```javascript
$('DetailedFaceDetection*0:detect.once').d = 1;
```
-->

### Python
```python
detailed_face_detection = DetailedFaceDetection(0)

detailed_face_detection.detect_once()
```

---

## 연속 인식 시작 / 중지

현재 화면에 있는 얼굴을 계속해서 따라가며 화면 상에 표시합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/DetailedFaceDetection/4.png" alt="연속 인식 시작 / 중지">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 동작 | 시작(start), 중지(stop) | - |

<!-- 
### JavaScript
```javascript
$('DetailedFaceDetection*0:detect.continuous').d = 1;
```
-->

### Python
```python
detailed_face_detection = DetailedFaceDetection(0)

# unit = "start"
detailed_face_detection.detect_continuous()
# unit = "stop"
detailed_face_detection.stop()
```

---

## 인식 화면 표시하기

카메라 화면에 얼굴 찾기 결과를 표시할지 말지를 결정합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/DetailedFaceDetection/5.png" alt="인식 화면 표시하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| on | 드롭다운 옵션 | 표시 ON / OFF | 표시(on=True), 숨기기(off=False) | TRUE |

<!-- 
### JavaScript
```javascript
$('DetailedFaceDetection*0:display').d = 1;
```
-->

### Python
```python
detailed_face_detection = DetailedFaceDetection(0)

detailed_face_detection.display(True)
detailed_face_detection.display(False)
```

---

## 얼굴 부위 좌표

얼굴 부위별 좌표를 반환합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/DetailedFaceDetection/6.png" alt="얼굴 부위 좌표">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 얼굴 부위 | 얼굴(face), 왼쪽 눈(left eye), 오른쪽 눈(right eye), 입(mouth), 코(nose), 윗입술(upper lip), 아랫입술(lower lip), 왼쪽 입꼬리(left lip), 오른쪽 입꼬리(right lip), 왼쪽 눈동자(left pupil), 오른쪽 눈동자(right pupil) | - |
| pos | 드롭다운 옵션 | 좌표 | x, y | - |

<!-- 
### JavaScript
```javascript
$('DetailedFaceDetection*0:face.x').d
$('DetailedFaceDetection*0:eye.left.y').d
$('DetailedFaceDetection*0:lip.up.x').d
```
-->

### Python
```python
detailed_face_detection = DetailedFaceDetection(0)

detailed_face_detection.face('x')
detailed_face_detection.left_eye('y')
detailed_face_detection.upper_lip('x')
detailed_face_detection.right_pupil('y')
```

---

## 얼굴 부위 사각형 정보

얼굴 부위별 영역 사각형의 위치/크기 값을 반환합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/DetailedFaceDetection/7.png" alt="얼굴 부위 사각형 정보">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 얼굴 부위 | 얼굴(face), 왼쪽 눈(left eye), 오른쪽 눈(right eye), 입(mouth) | - |
| pos | 드롭다운 옵션 | 사각형 정보 | 최소 x(min_x), 최대 x(max_x), 최소 y(min_y), 최대 y(max_y), 폭(width), 높이(height), 넓이(area) | - |

<!-- 
### JavaScript
```javascript
$('DetailedFaceDetection*0:face.x').d
$('DetailedFaceDetection*0:eye.left.y').d
$('DetailedFaceDetection*0:lip.up.x').d
```
-->

### Python
```python
detailed_face_detection = DetailedFaceDetection(0)

detailed_face_detection.face('min_x')
detailed_face_detection.left_eye('area')
```

---

## 두 부위 사이 거리

얼굴 부위 두 곳 사이의 거리를 반환합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/DetailedFaceDetection/8.png" alt="두 부위 사이 거리">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit1 | 드롭다운 옵션 | 첫 번째 부위 | 얼굴 부위 이름 | - |
| unit2 | 드롭다운 옵션 | 두 번째 부위 | 얼굴 부위 이름 | - |
| type | 드롭다운 옵션 | 거리 종류 | 거리(생략 또는 None), 가로 거리(horizontal), 세로 거리(vertical) | None |

<!-- 
### JavaScript
```javascript
// distance
Math.sqrt( Math.pow(($('DetailedFaceDetection*0:eye.right.x').d - $('DetailedFaceDetection*0:eye.left.x').d), 2) + Math.pow(($('DetailedFaceDetection*0:eye.right.y').d - $('DetailedFaceDetection*0:eye.left.y').d), 2) )
```
-->

### Python
```python
detailed_face_detection = DetailedFaceDetection(0)

detailed_face_detection.get_distance('left_eye', 'right_eye')  # 거리
detailed_face_detection.get_distance('left_pupil', 'right_pupil', 'horizontal')  # 가로 거리
detailed_face_detection.get_distance('upper_lip', 'lower_lip', 'vertical')  # 세로 거리
```

---

## 모델 상태

얼굴 모델 로딩 상태를 반환합니다.  
아직 불러오지 않았으면 0, 불러오는 중이면 1, 불러오기를 완료했으면 2를 반환합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/DetailedFaceDetection/9.png" alt="모델 상태">

### 매개변수

(없음)

<!-- 
### JavaScript
```javascript
$('DetailedFaceDetection*0:model_state').d
```
-->

### Python
```python
detailed_face_detection = DetailedFaceDetection(0)

detailed_face_detection.model_state()
```

---

## 얼굴 감지 여부

얼굴을 찾았는지 여부

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/DetailedFaceDetection/10.png" alt="얼굴 감지 여부">

### 매개변수

(없음)

<!-- 
### JavaScript
```javascript
$('DetailedFaceDetection*0:detected').d
```
-->

### Python
```python
detailed_face_detection = DetailedFaceDetection(0)

detailed_face_detection.detected()
```
