# 소리 센서

## 인스턴스 선언

소리 센서(CSD07) 블록을 작업 영역에 추가하면, Python 코드에는 다음과 같은 인스턴스 선언이 자동으로 삽입됩니다:

```python
cheesestick = CheeseStick(0)
csd07 = cheesestick.CSD07()
```

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| index | 드롭다운 옵션 | 인스턴스 번호 (0부터 시작) | 0 이상 정수 | 0 |


<br>

# 블록 <-> 파이썬 변환 규칙

## 입력 포트 설정하기

CSD07 (소리 센서) 가 연결된 포트를 설정합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/cheesestick_ext/CSD07/1.png" alt="입력 포트 설정하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 연결할 포트 | Sa, Sb, Sc | - |

<!-- 
### JavaScript
```javascript
$('CheeseStick*0:S_port.Sa.mode').d = $('CheeseStick*0:S_port.Sa.mode^analog_input');
```
-->

### Python
```python
cheesestick = CheeseStick(0)
csd07 = cheesestick.CSD07()

csd07.set_port('Sa')
```

---

## 소리 센서 값

선택한 포트의 소리 센서 값

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/cheesestick_ext/CSD07/2.png" alt="소리 센서 값">

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
csd07 = cheesestick.CSD07()

csd07.get_input('Sa')
```
