# 스위치

## 인스턴스 선언

스위치(CSD01) 블록을 작업 영역에 추가하면, Python 코드에는 다음과 같은 인스턴스 선언이 자동으로 삽입됩니다:

```python
cheesestick = CheeseStick(0)
csd01 = cheesestick.CSD01()
```

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| index | 드롭다운 옵션 | 인스턴스 번호 (0부터 시작) | 0 이상 정수 | 0 |


<br>

# 블록 <-> 파이썬 변환 규칙

## 입력 포트 설정하기

CSD01 (Tact Switch) 가 연결된 포트를 설정합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/cheesestick_ext/CSD01/1.png" alt="입력 포트 설정하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 연결할 포트 | Sa, Sb, Sc | - |

<!-- 
### JavaScript
```javascript
$('CheeseStick*0:S_port.Sa.mode').d = $('CheeseStick*0:S_port.Sa.mode^button_input');
$('CheeseStick*0:S_port.Sa.pull').d = $('CheeseStick*0:S_port.Sa.pull^pull-up');
```
-->

### Python
```python
cheesestick = CheeseStick(0)
csd01 = cheesestick.CSD01()

csd01.set_port('Sa')
```

---

## 버튼 입력 값

선택한 포트의 버튼 입력 값  
버튼이 눌려있으면 0, 그렇지 않으면 1을 반환합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/cheesestick_ext/CSD01/2.png" alt="버튼 입력 값">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 읽어올 포트 | Sa, Sb, Sc | 마지막 `set_port` 의 포트 |

<!-- 
### JavaScript
```javascript
$('CheeseStick*0:input.Sa').d
```
-->

### Python
```python
cheesestick = CheeseStick(0)
csd01 = cheesestick.CSD01()

csd01.button_input('Sa')
```

---

## 버튼이 눌렸는가?

선택한 포트에 연결된 스위치 버튼이 눌려있는지 여부

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/cheesestick_ext/CSD01/3.png" alt="버튼이 눌렸는가?">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 읽어올 포트 | Sa, Sb, Sc | 마지막 `set_port` 의 포트 |

<!-- 
### JavaScript
```javascript
$('CheeseStick*0:input.Sa').d === 0
```
-->

### Python
```python
cheesestick = CheeseStick(0)
csd01 = cheesestick.CSD01()

csd01.button_pressed('Sa')
```
