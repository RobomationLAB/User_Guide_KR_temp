# 제어

블록 코딩에서 **제어 블록**은 프로그램의 흐름을 조작하는 역할을 합니다.  
일정 시간 대기하거나, 키보드 입력 감지, 로그 출력 등의 기능을 수행할 수 있습니다.

<br>

# 블록 <-> 파이썬 변환 규칙

## 1 프레임 기다리기

프로그램의 실행을 한 프레임(약 0.001초) 동안 멈춥니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/control/1.png" alt="Image">

### 매개변수

(없음 — 0.001 초 고정)

<!-- 
### JavaScript
```javascript
await __wait(1);
```
-->

### Python
```python
Utils.wait(0.001)
```

---

## 무한 기다리기

프로그램의 실행을 멈추고 무한히 대기합니다.

### 매개변수

(없음)

<!-- 
### JavaScript
```javascript
await __wait_forever();
```
-->

### Python
```python
Utils.wait_forever()
```

---

## 기다리기

지정한 시간(초) 동안 대기한 후 다음 명령을 실행합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/control/2.png" alt="Image">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| sec | 입력값 (필드) | 대기 시간 — **리터럴 숫자** (예: `Utils.wait(0.5)`) | 0 이상 실수 | - |
| sec | 입력값 (블록) | 대기 시간 — **변수/식** (예: `Utils.wait(time)`) | 0 이상 실수 | - |

<!-- 
### JavaScript
```javascript
// field sec = 2 → sec * 1000 = 2000
await __wait(2000);
// sec = myVar (variable) → "myVar * 1000"
await __wait(myVar * 1000);
```
-->

### Python
```python
# field sec = 2 → 그대로 (초 단위)
Utils.wait(2)

# 변수 입력
Utils.wait(myVar)
```

---

## 키 다운 / 키 업

특정 키를 눌렀을 때 또는 키에서 손을 뗄 때 동작을 수행합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/control/3.png" alt="Image">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| updown | 드롭다운 옵션 | 이벤트 종류 | 누름(keydown), 뗌(keyup) | - |
| key | 드롭다운 옵션 | 키 코드 | 정수 (예: 32=space, 65=a) | - |

<!-- 
### JavaScript
```javascript
// updown=keydown, key=32 (space)
keydown(32)
// updown=keyup, key=65 (a)
keyup(65)
```
-->

### Python
```python
# updown=keydown, key=32 (space)
keydown(32)
# updown=keyup, key=65 (a)
keyup(65)
```

---

## 키 입력

특정 키가 눌려 있는지 여부를 **참(True) / 거짓(False)** 으로 반환합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/control/4.png" alt="Image">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| key | 입력값 | 키 이름 | 문자열: space, up, left, right, down, a~z, 0~9, shift, ctrl, alt, enter, tab, esc, backspace | - |

<!-- 
### JavaScript
```javascript
__keypressed(32)
```
-->

### Python
```python
Utils.keypressed('space')
```

---

## 로그 출력하기

특정 변수나 속성 값을 실시간으로 **콘솔** 창에 출력합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/control/5.png" alt="Image">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| data | 입력값 | 출력할 값 | 임의 값 | - |
| tag | 입력값 | 로그 태그 | 문자열 | None |
| unit | 입력값 | 단위 표시 | 문자열 | None |

<!-- 
### JavaScript
```javascript
__log(data, 'speed', 'cm/s');
```
-->

### Python
```python
Utils.log(data, 'speed', 'cm/s')
```

---

## 스코프 출력하기

특정 값의 변화를 실시간 그래프 형태로 **스코프** 창에 표시합니다.  
그래프의 색상, 최소/최대 값, 범위를 설정할 수 있습니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/control/6.png" alt="Image">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| signal | 입력값 (블록) | 그래프 신호 값 | 실수 | - |
| name | 입력값 | 그래프 이름 | 문자열 | - |
| min_val | 입력값 (필드) | 그래프 최소값 | 실수 | - |
| max_val | 입력값 (필드) | 그래프 최대값 | 실수 | - |
| color | 색상 | 그래프 색상 (hex) | hex 문자열 | - |

<!-- 
### JavaScript
```javascript
__scope(signal, 'channel1', -100, 100, '#f00');
```
-->

### Python
```python
Utils.scope(signal, 'channel1', -100, 100, '#ff0000')
```
