# 로터리 퍼텐쇼미터

## 인스턴스 선언

로터리 퍼텐쇼미터(CSD03) 블록을 작업 영역에 추가하면, Python 코드에는 다음과 같은 인스턴스 선언이 자동으로 삽입됩니다:

```python
cheesestick = CheeseStick(0)
csd03 = cheesestick.CSD03()
```

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| index | 드롭다운 옵션 | 인스턴스 번호 (0부터 시작) | 0 이상 정수 | 0 |


<br>

# 블록 <-> 파이썬 변환 규칙

## 입력 포트 설정하기

CSD03 (가변 저항) 이 연결된 포트를 설정합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/cheesestick_ext/CSD03/1.png" alt="입력 포트 설정하기">

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
csd03 = cheesestick.CSD03()

csd03.set_port('Sa')
```

---

## 입력 범위 설정하기

선택한 포트의 입력값을 지정한 최소~최대 범위로 변환합니다.  
입력값의 범위는 0 ~ 255 입니다.  
변환할 수 있는 값의 범위는 -100 ~ 100 입니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/cheesestick_ext/CSD03/2.png" alt="입력 범위 설정하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 대상 포트 | Sa, Sb, Sc | - |
| src_min | 입력값 (필드) | 원본 최소값 | 0 ~ 255 정수 | - |
| src_max | 입력값 (필드) | 원본 최대값 | 0 ~ 255 정수 | - |
| dst_min | 입력값 (필드) | 변환 후 최소값 | -100 ~ 100 정수 | - |
| dst_max | 입력값 (필드) | 변환 후 최대값 | -100 ~ 100 정수 | - |

<!-- 
### JavaScript
```javascript
__setIORange('CheeseStick*0', 'Sa', 0, 255, 0, 100);
```
-->

### Python
```python
cheesestick = CheeseStick(0)
csd03 = cheesestick.CSD03()

csd03.set_input_range('Sa', 0, 255, 0, 100)
```

---

## 중간값으로 입력 범위 설정하기

선택한 포트의 입력값을 지정한 최소~중간~최대 범위로 변환합니다.  
입력값의 범위는 0 ~ 255 입니다.  
변환할 수 있는 값의 범위는 -100 ~ 100 입니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/cheesestick_ext/CSD03/3.png" alt="중간값으로 입력 범위 설정하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 대상 포트 | Sa, Sb, Sc | - |
| src_min | 입력값 (필드) | 원본 최소값 | 0 ~ 255 정수 | - |
| src_median | 입력값 (필드) | 원본 중간값 | 0 ~ 255 정수 | - |
| src_max | 입력값 (필드) | 원본 최대값 | 0 ~ 255 정수 | - |
| dst_min | 입력값 (필드) | 변환 후 최소값 | -100 ~ 100 정수 | - |
| dst_median | 입력값 (필드) | 변환 후 중간값 | -100 ~ 100 정수 | - |
| dst_max | 입력값 (필드) | 변환 후 최대값 | -100 ~ 100 정수 | - |

<!-- 
### JavaScript
```javascript
__setIORange('CheeseStick*0', 'Sa', 0, 128, 255, -100, 0, 100);
```
-->

### Python
```python
cheesestick = CheeseStick(0)
csd03 = cheesestick.CSD03()

csd03.set_input_range_median('Sa', 0, 128, 255, -100, 0, 100)
```

---

## 입력값

선택한 포트의 로터리 퍼텐슈미터 입력 값  
입력 범위를 별도로 설정하지 않은 경우, 입력값의 범위는 0 ~ 255 입니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/cheesestick_ext/CSD03/4.png" alt="입력값">

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
csd03 = cheesestick.CSD03()

csd03.get_input('Sa')
```
