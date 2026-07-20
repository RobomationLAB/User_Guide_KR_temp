# ArUco 마커 찾기

## 인스턴스 선언

ArUco 마커 찾기(ArucoMarker) 블록을 작업 영역에 추가하면, Python 코드에는 다음과 같은 인스턴스 선언이 자동으로 삽입됩니다:

```python
aruco_marker = ArucoMarker(0)
# 여러 인스턴스가 있는 경우
aruco_marker_1 = ArucoMarker(1)
```

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| index | 드롭다운 옵션 | 인스턴스 번호 (0부터 시작) | 0 이상 정수 | 0 |


<br>

# 블록 <-> 파이썬 변환 규칙

## 카메라 장치 선택하기

ArUco 마커 찾기를 위한 카메라를 설정합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/ArucoMarker/1.png" alt="카메라 장치 선택하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 카메라 장치 이름 | 시스템 카메라 라벨 | - |

<!-- 
### JavaScript
```javascript
$('ArucoMarker*0:camera.device_id').d = __cameraId('FaceTime HD Camera');
```
-->

### Python
```python
aruco_marker = ArucoMarker(0)

aruco_marker.device('')
```

---

## 최대 마커 수 설정하기

최대로 인식할 수 있는 마커의 개수를 설정합니다. 마커 개수의 범위는 0 ~ 10 입니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/ArucoMarker/2.png" alt="최대 마커 수 설정하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| data | 입력값 (블록) | 최대 마커 수 | 0 ~ 10 정수 | - |

<!-- 
### JavaScript
```javascript
$('ArucoMarker*0:max_count').d = 5;
```
-->

### Python
```python
aruco_marker = ArucoMarker(0)

aruco_marker.max_count(5)
```

---

## 한 번 인식하기

현재 화면에 있는 마커들을 찾아 딱 한번 영역을 표시합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/ArucoMarker/3.png" alt="한 번 인식하기">

### 매개변수

(없음)

<!-- 
### JavaScript
```javascript
$('ArucoMarker*0:detect.once').d = 1;
```
-->

### Python
```python
aruco_marker = ArucoMarker(0)

aruco_marker.detect_once()
```

---

## 연속 인식 시작 / 중지

현재 화면에 있는 마커들을 계속해서 따라가며 화면 상에 영역을 표시합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/ArucoMarker/4.png" alt="연속 인식 시작 / 중지">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 동작 | 시작(start), 중지(stop) | - |

<!-- 
### JavaScript
```javascript
$('ArucoMarker*0:detect.continuous').d = 1;
```
-->

### Python
```python
aruco_marker = ArucoMarker(0)

# unit = "start"
aruco_marker.detect_continuous()
# unit = "stop"
aruco_marker.stop()
```

---

## 인식 화면 표시하기

카메라 화면에 마커 찾기 결과를 표시할지 말지를 결정합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/ArucoMarker/5.png" alt="인식 화면 표시하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| on | 드롭다운 옵션 | 표시 ON / OFF | 표시(on=True), 숨기기(off=False) | TRUE |

<!-- 
### JavaScript
```javascript
$('ArucoMarker*0:display').d = 1;
```
-->

### Python
```python
aruco_marker = ArucoMarker(0)

aruco_marker.display(True)
aruco_marker.display(False)
```

---

## 마커 데이터

지정한 마커 ID 의 위치/크기 값을 반환합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/ArucoMarker/6.png" alt="마커 데이터">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| data | 입력값 (블록) | 마커 ID | 0 이상 정수 | - |
| unit | 드롭다운 옵션 | 측정 종류 | x, y, min_x, max_x, min_y, max_y, width, height, area, rotation | - |

<!-- 
### JavaScript
```javascript
$('ArucoMarker*0:marker.x').d[0]
$('ArucoMarker*0:marker.area').d[3]
```
-->

### Python
```python
aruco_marker = ArucoMarker(0)

aruco_marker.marker(0, 'x')
aruco_marker.marker(3, 'area')
```

---

## 마커 사이 거리

두 마커 사이의 거리를 반환합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/ArucoMarker/7.png" alt="마커 사이 거리">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit1 | 입력값 (블록) | 첫 번째 마커 ID | 0 이상 정수 | - |
| unit2 | 입력값 (블록) | 두 번째 마커 ID | 0 이상 정수 | - |
| type | 드롭다운 옵션 | 거리 종류 | 거리(생략 또는 None), 가로 거리(horizontal), 세로 거리(vertical) | None |

<!-- 
### JavaScript
```javascript
// distance (from=0, to=1)
Math.sqrt(Math.pow(($('ArucoMarker*0:marker.x').d[0] - $('ArucoMarker*0:marker.x').d[1]), 2) + Math.pow(($('ArucoMarker*0:marker.y').d[0] - $('ArucoMarker*0:marker.y').d[1]), 2))
```
-->

### Python
```python
aruco_marker = ArucoMarker(0)

aruco_marker.get_distance(0, 1)  # 거리
aruco_marker.get_distance(0, 2, 'horizontal')  # 가로 거리
```

---

## 마커 감지 여부

특정 id 값을 갖는 마커를 찾았는지 여부

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/ArucoMarker/8.png" alt="마커 감지 여부">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| data | 입력값 (블록) | 마커 ID | 0 이상 정수 | - |

<!-- 
### JavaScript
```javascript
$('ArucoMarker*0:marker.detected').d[0]
```
-->

### Python
```python
aruco_marker = ArucoMarker(0)

aruco_marker.marker_detected(0)
```
