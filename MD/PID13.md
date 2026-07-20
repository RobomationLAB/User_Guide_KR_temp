# PID-13 조이스틱과 버튼

## 인스턴스 선언

PID-13 조이스틱과 버튼(PID13) 블록을 작업 영역에 추가하면, Python 코드에는 다음과 같은 인스턴스 선언이 자동으로 삽입됩니다:

```python
cheesestick = CheeseStick(0)
pid13 = cheesestick.PID13()
```

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| index | 드롭다운 옵션 | 인스턴스 번호 (0부터 시작) | 0 이상 정수 | 0 |


<br>

# 블록 <-> 파이썬 변환 규칙

## 조이스틱 시작하기

조이스틱과 버튼을 사용합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/cheesestick_ext/PID13/1.png" alt="조이스틱 시작하기">

### 매개변수

(없음)

<!-- 
### JavaScript
```javascript
$('CheeseStick*0:PID>').d = $('CheeseStick*0:PID>PID13+').mid;  // 13
```
-->

### Python
```python
cheesestick = CheeseStick(0)
pid13 = cheesestick.PID13()

pid13.start()
```

---

## 조이스틱 값

조이스틱의 x / y 값.  
각 값의 범위는 -128 ~ 127입니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/cheesestick_ext/PID13/2.png" alt="조이스틱 값">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 측정 축 | x, y | - |

<!-- 
### JavaScript
```javascript
$('CheeseStick*0:PID>PID13+x').d
```
-->

### Python
```python
cheesestick = CheeseStick(0)
pid13 = cheesestick.PID13()

pid13.joystick('x')
```

---

## 버튼 입력 값

선택한 버튼의 입력 상태  
버튼이 눌려있으면 1, 버튼이 눌려있지 않으면 0을 출력합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/cheesestick_ext/PID13/3.png" alt="버튼 입력 값">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 버튼 이름 | A 버튼(a), B 버튼(b) | - |

<!-- 
### JavaScript
```javascript
$('CheeseStick*0:PID>PID13+button.a').d
```
-->

### Python
```python
cheesestick = CheeseStick(0)
pid13 = cheesestick.PID13()

pid13.button_input('a')
```

---

## 버튼을 클릭했는가?

선택한 버튼의 클릭 여부  
이 블록은 선택한 버튼이 클릭되는 순간에만 참을 반환하고, 이외에는 거짓을 반환합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/cheesestick_ext/PID13/4.png" alt="버튼을 클릭했는가?">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 버튼 이름 | A 버튼(a), B 버튼(b) | - |

<!-- 
### JavaScript
```javascript
$('CheeseStick*0:PID>PID13+button.a').e
```
-->

### Python
```python
cheesestick = CheeseStick(0)
pid13 = cheesestick.PID13()

pid13.button_click('a')
```
