# 색깔 찾기

## 인스턴스 선언

색깔 찾기(ColorDetection) 블록을 작업 영역에 추가하면, Python 코드에는 다음과 같은 인스턴스 선언이 자동으로 삽입됩니다:

```python
color_detection = ColorDetection(0)
# 여러 인스턴스가 있는 경우
color_detection_1 = ColorDetection(1)
```

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| index | 드롭다운 옵션 | 인스턴스 번호 (0부터 시작) | 0 이상 정수 | 0 |


<br>

# 블록 <-> 파이썬 변환 규칙

## 카메라 장치 선택하기

색깔 찾기를 위한 카메라를 설정합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/ColorDetection/1.png" alt="카메라 장치 선택하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 카메라 장치 이름 | 시스템 카메라 라벨 | - |

<!-- 
### JavaScript
```javascript
$('ColorDetection*0:camera.device_id').d = __cameraId('FaceTime HD Camera');
```
-->

### Python
```python
color_detection = ColorDetection(0)

color_detection.device('')
```

---

## 색 등록하기

색깔 찾기를 통해 인식할 색깔을 추가합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/ColorDetection/2.png" alt="색 등록하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| color | 드롭다운 옵션 | 색깔 이름 | 검정(black), 빨강(red), 노랑(yellow), 초록(green), 청록(cyan), 파랑(blue), 자홍(magenta), 흰색(white) | - |
| wait | 체크박스 | 완료 대기 여부 | TRUE / FALSE | TRUE |

<!-- 
### JavaScript
```javascript
$('ColorDetection*0:color.register').d = 1;   // red
await $('ColorDetection*0:color.!register').w();
```
-->

### Python
```python
color_detection = ColorDetection(0)

color_detection.register_color('red', wait=True)
```

---

## 색 삭제하기

색깔 찾기를 통해 인식할 색깔에서 해당 색깔을 삭제합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/ColorDetection/3.png" alt="색 삭제하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| color | 드롭다운 옵션 | 색깔 이름 | 검정(black), 빨강(red), 노랑(yellow), 초록(green), 청록(cyan), 파랑(blue), 자홍(magenta), 흰색(white) | - |
| wait | 체크박스 | 완료 대기 여부 | TRUE / FALSE | TRUE |

<!-- 
### JavaScript
```javascript
$('ColorDetection*0:color.delete').d = 5;   // blue
await $('ColorDetection*0:color.!delete').w();
```
-->

### Python
```python
color_detection = ColorDetection(0)

color_detection.delete_color('blue', wait=True)
```

---

## 면적 조건 설정하기

인식할 색깔 영역 넓이의 최소 크기를 정합니다. 영역의 넓이가 이 이상인 경우에만 화면에 표시됩니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/ColorDetection/4.png" alt="면적 조건 설정하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| data | 입력값 (블록) | 면적 조건값 | 0 이상 실수 | - |

<!-- 
### JavaScript
```javascript
$('ColorDetection*0:color.area_condition').d = 50;
```
-->

### Python
```python
color_detection = ColorDetection(0)

color_detection.area_condition(50)
```

---

## 한 번 인식하기

인식 가능한 색깔 중, 현재 화면에 있는 색깔들을 찾아 딱 한번 영역을 표시합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/ColorDetection/5.png" alt="한 번 인식하기">

### 매개변수

(없음)

<!-- 
### JavaScript
```javascript
$('ColorDetection*0:detect.once').d = 1;
```
-->

### Python
```python
color_detection = ColorDetection(0)

color_detection.detect_once()
```

---

## 연속 인식 시작 / 중지

인식 가능한 색깔 중, 현재 화면에 있는 색깔들을 계속해서 따라가며 화면 상에 영역을 표시합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/ColorDetection/6.png" alt="연속 인식 시작 / 중지">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 동작 | 시작(start), 중지(stop) | - |

<!-- 
### JavaScript
```javascript
$('ColorDetection*0:detect.continuous').d = 1;
```
-->

### Python
```python
color_detection = ColorDetection(0)

# unit = "start"
color_detection.detect_continuous()
# unit = "stop"
color_detection.stop()
```

---

## 인식 화면 표시하기

카메라 화면에 색깔 찾기 결과를 표시할지 말지를 결정합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/ColorDetection/7.png" alt="인식 화면 표시하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| on | 드롭다운 옵션 | 표시 ON / OFF | 표시(on=True), 숨기기(off=False) | TRUE |

<!-- 
### JavaScript
```javascript
$('ColorDetection*0:display').d = 1;
```
-->

### Python
```python
color_detection = ColorDetection(0)

color_detection.display(True)
color_detection.display(False)
```

---

## 색 정보

지정한 색의 위치/크기 값을 반환합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/ColorDetection/8.png" alt="색 정보">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| color | 드롭다운 옵션 | 색깔 이름 | 검정(black), 빨강(red), 노랑(yellow), 초록(green), 청록(cyan), 파랑(blue), 자홍(magenta), 흰색(white) | - |
| pos | 드롭다운 옵션 | 좌표/크기 종류 | x, y, min_x, max_x, min_y, max_y, width, height, area | - |

<!-- 
### JavaScript
```javascript
$('ColorDetection*0:color.x').d[1]     // red
$('ColorDetection*0:color.area').d[5]  // blue
```
-->

### Python
```python
color_detection = ColorDetection(0)

color_detection.color('red', 'x')
color_detection.color('green', 'y')
color_detection.color('blue', 'area')
```

---

## 특정 색 감지 여부

선택한 색깔을 찾았는지 여부

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/ColorDetection/9.png" alt="특정 색 감지 여부">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| color | 드롭다운 옵션 | 색깔 이름 | 검정(black), 빨강(red), 노랑(yellow), 초록(green), 청록(cyan), 파랑(blue), 자홍(magenta), 흰색(white) | - |

<!-- 
### JavaScript
```javascript
$('ColorDetection*0:color.area').d[1] >= $('ColorDetection*0:color.area_condition').d
```
-->

### Python
```python
color_detection = ColorDetection(0)

color_detection.color_detected('red')
```
