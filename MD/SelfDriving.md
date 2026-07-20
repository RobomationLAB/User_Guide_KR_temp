# 카메라 자율주행하기

## 인스턴스 선언

카메라 자율주행하기(SelfDriving) 블록을 작업 영역에 추가하면, Python 코드에는 다음과 같은 인스턴스 선언이 자동으로 삽입됩니다:

```python
self_driving = SelfDriving(0)
# 여러 인스턴스가 있는 경우
self_driving_1 = SelfDriving(1)
```

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| index | 드롭다운 옵션 | 인스턴스 번호 (0부터 시작) | 0 이상 정수 | 0 |


<br>

# 블록 <-> 파이썬 변환 규칙

## 카메라 장치 선택하기

카메라 자율주행하기를 위한 카메라를 설정합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/SelfDriving/1.png" alt="카메라 장치 선택하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 카메라 장치 이름 | 시스템 카메라 라벨 | - |

<!-- 
### JavaScript
```javascript
$('SelfDriving*0:camera.device_id').d = __cameraId('FaceTime HD Camera');
```
-->

### Python
```python
self_driving = SelfDriving(0)

self_driving.device('')
```

---

## 차선 색 설정하기

왼쪽/오른쪽 차선의 색을 설정합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/SelfDriving/2.png" alt="차선 색 설정하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| left | 드롭다운 옵션 | 왼쪽 차선 색 | 빨강(red), 초록(green), 파랑(blue) | - |
| right | 드롭다운 옵션 | 오른쪽 차선 색 | 빨강(red), 초록(green), 파랑(blue) | - |

<!-- 
### JavaScript
```javascript
$('SelfDriving*0:lane.left.color').d = 'green';
$('SelfDriving*0:lane.right.color').d = 'blue';
```
-->

### Python
```python
self_driving = SelfDriving(0)

self_driving.set_lane('green', 'blue')
```

---

## 한 번 인식하기

선택한 색깔/차선을 화면에서 찾아 딱 한번 영역을 표시합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/SelfDriving/3.png" alt="한 번 인식하기">

### 매개변수

(없음)

<!-- 
### JavaScript
```javascript
$('SelfDriving*0:detect.once').d = 1;
```
-->

### Python
```python
self_driving = SelfDriving(0)

self_driving.detect_once()
```

---

## 연속 인식 시작 / 중지

선택한 색깔/차선들에 대해 화면을 계속해서 따라가며 화면 상에 영역을 표시합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/SelfDriving/4.png" alt="연속 인식 시작 / 중지">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 동작 | 시작(start), 중지(stop) | - |

<!-- 
### JavaScript
```javascript
$('SelfDriving*0:detect.continuous').d = 1;
```
-->

### Python
```python
self_driving = SelfDriving(0)

# unit = "start"
self_driving.detect_continuous()
# unit = "stop"
self_driving.stop()
```

---

## 인식 화면 표시하기

카메라 화면에 색깔/차선 찾기 결과를 표시할지 말지를 결정합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/SelfDriving/5.png" alt="인식 화면 표시하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| on | 드롭다운 옵션 | 표시 ON / OFF | 표시(on=True), 숨기기(off=False) | TRUE |

<!-- 
### JavaScript
```javascript
$('SelfDriving*0:display').d = 1;
```
-->

### Python
```python
self_driving = SelfDriving(0)

self_driving.display(True)
self_driving.display(False)
```

---

## 차선 데이터

지정한 차선의 위치 또는 거리 값을 반환합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/SelfDriving/6.png" alt="차선 데이터">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| lane | 드롭다운 옵션 | 차선 | 왼쪽(left), 오른쪽(right) | - |
| unit | 드롭다운 옵션 | 측정 종류 | x, 거리(distance) | - |

<!-- 
### JavaScript
```javascript
$('SelfDriving*0:lane.left.x').d
$('SelfDriving*0:lane.right.y').d
```
-->

### Python
```python
self_driving = SelfDriving(0)

self_driving.lane('left', 'x')
self_driving.lane('right', 'distance')
```

---

## 색 데이터

지정한 색의 위치/크기 값을 반환합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/SelfDriving/7.png" alt="색 데이터">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| color | 드롭다운 옵션 | 색깔 이름 | 빨강(red), 초록(green), 파랑(blue) | - |
| unit | 드롭다운 옵션 | 좌표/크기 종류 | x, y, min_x, max_x, min_y, max_y, width, height, area | - |

<!-- 
### JavaScript
```javascript
$('SelfDriving*0:color.x').d[0]   // red
$('SelfDriving*0:color.area').d[2] // blue
```
-->

### Python
```python
self_driving = SelfDriving(0)

self_driving.color('red', 'x')
self_driving.color('green', 'y')
self_driving.color('blue', 'area')
```

---

## 두 색 사이 거리

두 색 사이의 거리를 반환합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/SelfDriving/8.png" alt="두 색 사이 거리">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit1 | 드롭다운 옵션 | 첫 번째 색 | 빨강(red), 초록(green), 파랑(blue) | - |
| unit2 | 드롭다운 옵션 | 두 번째 색 | 빨강(red), 초록(green), 파랑(blue) | - |
| type | 드롭다운 옵션 | 거리 종류 | 거리(생략 또는 None), 가로 거리(horizontal), 세로 거리(vertical) | None |

<!-- 
### JavaScript
```javascript
Math.sqrt(Math.pow(($('SelfDriving*0:color.x').d[0] - $('SelfDriving*0:color.x').d[2]), 2) + Math.pow(($('SelfDriving*0:color.y').d[0] - $('SelfDriving*0:color.y').d[2]), 2))
```
-->

### Python
```python
self_driving = SelfDriving(0)

self_driving.get_distance('red', 'blue')  # 거리
self_driving.get_distance('green', 'blue', 'horizontal')  # 수평 거리
```

---

## 차선 감지 여부

특정 차선을 찾았는지 여부

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/SelfDriving/9.png" alt="차선 감지 여부">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| lane | 드롭다운 옵션 | 차선 | 왼쪽(left), 오른쪽(right), 양쪽(both), 아무(any) | any |

<!-- 
### JavaScript
```javascript
// lane = "left"
$('SelfDriving*0:lane.left.detected').d
// lane = "both"
$('SelfDriving*0:lane.left.detected').d && $('SelfDriving*0:lane.right.detected').d
// lane = "any"
$('SelfDriving*0:lane.left.detected').d || $('SelfDriving*0:lane.right.detected').d
```
-->

### Python
```python
self_driving = SelfDriving(0)

self_driving.lane_detected('left')
```

---

## 색 감지 여부

특정 색깔 영역을 찾았는지 여부

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/SelfDriving/10.png" alt="색 감지 여부">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| color | 드롭다운 옵션 | 색깔 이름 | 빨간색(red), 초록색(green), 파란색(blue), 아무(any) | any |

<!-- 
### JavaScript
```javascript
$('SelfDriving*0:color.detected').d[0]   // red
$('SelfDriving*0:color.detected').d[1]   // green
$('SelfDriving*0:color.detected').d[2]   // blue
```
-->

### Python
```python
self_driving = SelfDriving(0)

self_driving.color_detected('red')
```
