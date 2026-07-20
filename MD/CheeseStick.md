# 치즈스틱

## 인스턴스 선언

치즈스틱(CheeseStick) 블록을 작업 영역에 추가하면, Python 코드에는 다음과 같은 인스턴스 선언이 자동으로 삽입됩니다:

```python
cheesestick = CheeseStick(0)
# 여러 인스턴스가 있는 경우
cheesestick_1 = CheeseStick(1)
```

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| index | 드롭다운 옵션 | 인스턴스 번호 (0부터 시작) | 0 이상 정수 | 0 |


<br>

# 블록 <-> 파이썬 변환 규칙

## 입력 모드 설정하기

선택한 포트의 입력 모드를 설정합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/CheeseStick/1.png" alt="입력 모드 설정하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 입력 포트 | Sa, Sb, Sc, La, Lb, Lc | - |
| option | 드롭다운 옵션 | 입력 모드 | 메이키 입력(makey), 버튼 입력(button), 디지털 풀업(digital_pullup), 디지털 풀다운(digital_pulldown), 아날로그(analog), 아날로그 전압(analog_voltage) | - |

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

cheesestick.set_input_mode('Sa', 'button')
```

---

## 입력 범위 설정하기

선택한 포트의 입력값을 지정한 최소~최대 범위로 변환합니다.  
입력값의 범위는 0 ~ 255 입니다.  
변환할 수 있는 값의 범위는 -100 ~ 100 입니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/CheeseStick/2.png" alt="입력 범위 설정하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 입력 포트 | Sa, Sb, Sc, La, Lb, Lc | - |
| src_min | 입력값 (필드) | 원본 최소값 | 0 ~ 255 정수 | - |
| src_max | 입력값 (필드) | 원본 최대값 | 0 ~ 255 정수 | - |
| dst_min | 입력값 (필드) | 변환 후 최소값 | -100 ~ 100 정수 | - |
| dst_max | 입력값 (필드) | 변환 후 최대값 | -100 ~ 100 정수 | - |

<!-- 
### JavaScript
```javascript
__setIORange('CheeseStick*0', 'Sa', 0, 1023, 0, 100);
```
-->

### Python
```python
cheesestick = CheeseStick(0)

cheesestick.set_input_range('Sa', 0, 255, 0, 100)
```

---

## 중간값으로 입력 범위 설정하기

선택한 포트의 입력값을 지정한 최소~중간~최대 범위로 변환합니다.  
입력값의 범위는 0 ~ 255 입니다.  
변환할 수 있는 값의 범위는 -100 ~ 100 입니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/CheeseStick/3.png" alt="중간값으로 입력 범위 설정하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 입력 포트 | Sa, Sb, Sc, La, Lb, Lc | - |
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

cheesestick.set_input_range_median('Sa', 0, 128, 255, -100, 0, 100)
```

---

## 입력 값

선택한 포트의 입력 값

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/CheeseStick/4.png" alt="입력 값">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 입력 포트 | Sa, Sb, Sc, La, Lb, Lc | - |

<!-- 
### JavaScript
```javascript
$('CheeseStick*0:input.Sa').d
```
-->

### Python
```python
cheesestick = CheeseStick(0)

cheesestick.get_input('Sa')
```

---

<!--
## 버튼 입력

치즈스틱 포트에 연결된 버튼이 눌렸는지 여부를 **참(True) / 거짓(False)** 으로 반환합니다.

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 입력 포트 | Sa, Sb, Sc, La, Lb, Lc | - |

<!-- 
### JavaScript
```javascript
$('CheeseStick*0:input.Sa').d === 0
```

### Python
```python
cheesestick = CheeseStick(0)

cheesestick.get_input('Sa') == 0
```

---
-->

## 펄스 입력 모드 설정하기

선택한 포트의 펄스 입력 모드를 설정합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/CheeseStick/5.png" alt="펄스 입력 모드 설정하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 펄스 입력 포트 | Sc, Lc | - |
| option | 드롭다운 옵션 | 풀 모드 | 기본(default), 풀업(pull-up), 풀다운(pull-down) | - |

<!-- 
### JavaScript
```javascript
$('CheeseStick*0:S_port.pulse_detect').d = 1;
$('CheeseStick*0:S_port.Sa.mode').d = $('CheeseStick*0:S_port.Sa.mode^digital_input');
$('CheeseStick*0:S_port.Sa.pull').d = $('CheeseStick*0:S_port.Sa.pull^pull-up');
```
-->

### Python
```python
cheesestick = CheeseStick(0)

cheesestick.set_pulse_input_mode('Sc', 'pull-up')
```

---

## 펄스 입력 값

선택한 포트에 펄스 입력이 감지되었는지 여부

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/CheeseStick/6.png" alt="펄스 입력 값">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 펄스 입력 포트 | Sc, Lc | - |

<!-- 
### JavaScript
```javascript
$('CheeseStick*0:input.Sa_pulse.detect').e
```
-->

### Python
```python
cheesestick = CheeseStick(0)

cheesestick.get_pulse_input('Sc')
```

---

## 디지털 출력 설정하기

지정한 포트의 디지털 출력 값을 설정합니다.  
선택할 수 있는 값은 0 또는 1입니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/CheeseStick/7.png" alt="디지털 출력 설정하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 디지털 출력 포트 | Sa, Sb, Sc, La, Lb, Lc, Mab, Mcd | - |
| value | 드롭다운 옵션 | 출력값 | 0 또는 1 | - |

<!-- 
### JavaScript
```javascript
$('CheeseStick*0:S_port.Sa.mode').d = $('CheeseStick*0:S_port.Sa.mode^digital_output');
$('CheeseStick*0:output.digital.Sa').d = 1;
```
-->

### Python
```python
cheesestick = CheeseStick(0)

cheesestick.set_digital_output('Sa', 1)
```

---

## PWM 출력 설정하기

지정한 포트의 PWM 출력 값을 설정합니다.  
선택할 수 있는 값의 범위는 0 ~ 100 입니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/CheeseStick/8.png" alt="PWM 출력 설정하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | PWM 출력 포트 | Sa, Sb, Sc, La, Lb, Lc | - |
| value | 입력값 (필드) | PWM 값 | 0 ~ 100 정수 | - |

<!-- 
### JavaScript
```javascript
$('CheeseStick*0:S_port.Sa.mode').d = $('CheeseStick*0:S_port.Sa.mode^pwm_output');
$('CheeseStick*0:output.pwm.Sa').d = 50;
```
-->

### Python
```python
cheesestick = CheeseStick(0)

cheesestick.set_pwm_output('Sa', 50)
```

---

## PWM 출력 변경하기

지정한 포트의 PWM 출력 값을 변경합니다.  
선택할 수 있는 값의 범위는 -100 ~ 100 입니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/CheeseStick/9.png" alt="PWM 출력 변경하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | PWM 출력 포트 | Sa, Sb, Sc, La, Lb, Lc | - |
| value | 입력값 (필드) | 변경할 PWM 차 | -100 ~ 100 정수 | - |

<!-- 
### JavaScript
```javascript
$('CheeseStick*0:S_port.Sa.mode').d = $('CheeseStick*0:S_port.Sa.mode^pwm_output');
$('CheeseStick*0:output.pwm.Sa').d = $('CheeseStick*0:output.pwm.Sa').d + 10;
```
-->

### Python
```python
cheesestick = CheeseStick(0)

cheesestick.change_pwm_output('Sa', 10)
```

---

## 버저음 설정하기

치즈스틱의 버저음을 설정합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/CheeseStick/10.png" alt="버저음 설정하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| hz | 입력값 (블록) | 주파수 (Hz) | 0 ~ 6553.5 실수 | - |

<!-- 
### JavaScript
```javascript
$('CheeseStick*0:sound.buzz').d = 440;
```
-->

### Python
```python
cheesestick = CheeseStick(0)

cheesestick.sound_buzz(440)
```

---

## 음계 연주하기

치즈스틱이 지정된 음계를 재생합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/CheeseStick/11.png" alt="음계 연주하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| note | 드롭다운 옵션 | 음계 | 도(C), 도#(C#), 레(D), 레#(D#), 미(E), 파(F), 파#(F#), 솔(G), 솔#(G#), 라(A), 라#(A#), 시(B) | - |
| octave | 드롭다운 옵션 | 옥타브 | 1, 2, 3, 4, 5, 6, 7 | 4 |

<!-- 
### JavaScript
```javascript
$('CheeseStick*0:sound.note').d = 49;
```
-->

### Python
```python
cheesestick = CheeseStick(0)

cheesestick.sound_note('D', 5)
```

---

## 소리 재생하기

치즈스틱이 특정 사운드 클립을 재생합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/CheeseStick/12.png" alt="소리 재생하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| clip | 드롭다운 옵션 | 사운드 클립 이름 | `'mute'`, `'beep'`, `'siren'`, `'engine'`, `'robot'`, `'happy'`, `'angry'`, `'sad'` 등 | - |
| wait | 체크박스 | 완료 대기 여부 | TRUE / FALSE | TRUE |

<!-- 
### JavaScript
```javascript
$('CheeseStick*0:sound.clip').d = $('CheeseStick*0:sound.clip^siren');
await $('CheeseStick*0:sound.!clip').w();  // wait = TRUE
```
-->

### Python
```python
cheesestick = CheeseStick(0)

cheesestick.sound_clip('siren', wait=True)
```

---

## 소리 끄기

치즈스틱의 소리를 끕니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/CheeseStick/13.png" alt="소리 끄기">

### 매개변수

(없음)

<!-- 
### JavaScript
```javascript
__stopSound('CheeseStick*0');
```
-->

### Python
```python
cheesestick = CheeseStick(0)

cheesestick.sound_off()
```

---

## 가속도 값

특정 축의 중력 가속도 값

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/CheeseStick/14.png" alt="가속도 값">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 측정 축 | x, y, z | - |

<!-- 
### JavaScript
```javascript
$('CheeseStick*0:acceleration.x').d
```
-->

### Python
```python
cheesestick = CheeseStick(0)

cheesestick.acceleration('x')
```

---

## 온도 센서 값

온도 센서 값

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/CheeseStick/15.png" alt="온도 센서 값">

### 매개변수

(없음)

<!-- 
### JavaScript
```javascript
$('CheeseStick*0:temperature').d
```
-->

### Python
```python
cheesestick = CheeseStick(0)

cheesestick.temperature()
```

---

## 신호 세기 값

신호 세기

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/CheeseStick/16.png" alt="신호 세기 값">

### 매개변수

(없음)

<!-- 
### JavaScript
```javascript
$('CheeseStick*0:signal_strength').d
```
-->

### Python
```python
cheesestick = CheeseStick(0)

cheesestick.signal_strength()
```

---

## 배터리 전압

배터리 전압

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/CheeseStick/17.png" alt="배터리 전압">

### 매개변수

(없음)

<!-- 
### JavaScript
```javascript
$('CheeseStick*0:battery.level').d
```
-->

### Python
```python
cheesestick = CheeseStick(0)

cheesestick.battery()
```

---

## 상태 변경 여부

로봇의 상태가 변했는지 여부

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/CheeseStick/18.png" alt="상태 변경 여부">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 상태 종류 | 0 ~ 7 (아래 표 참조) | - |

| unit | 조건 |
|------|------|
| 0 | `acceleration('x') > 960` |
| 1 | `acceleration('x') < -960` |
| 2 | `acceleration('y') > 960` |
| 3 | `acceleration('y') < -960` |
| 4 | `acceleration('z') > 960` |
| 5 | `acceleration('z') < -960` |
| 6 | `tap()` (탭 이벤트) |
| 7 | `fall()` (낙하 이벤트) |

<!-- 
### JavaScript
```javascript
$('CheeseStick*0:acceleration.x').d > 960
$('CheeseStick*0:acceleration.tap').e   // case 6
$('CheeseStick*0:acceleration.fall').e  // case 7
```
-->

### Python
```python
cheesestick = CheeseStick(0)

cheesestick.acceleration('x') > 960
cheesestick.tap()    # case 6
cheesestick.fall()   # case 7
```
