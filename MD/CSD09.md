# 모터

## 인스턴스 선언

모터(CSD09) 블록을 작업 영역에 추가하면, Python 코드에는 다음과 같은 인스턴스 선언이 자동으로 삽입됩니다:

```python
cheesestick = CheeseStick(0)
csd09 = cheesestick.CSD09()
```

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| index | 드롭다운 옵션 | 인스턴스 번호 (0부터 시작) | 0 이상 정수 | 0 |


<br>

# 블록 <-> 파이썬 변환 규칙

## 서보 모터 시작하기

서보 모터를 사용할 포트를 지정합니다.  
포트를 지정하지 않으면, 모터가 정상적으로 동작하지 않습니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/cheesestick_ext/CSD09/1.png" alt="서보 모터 시작하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 서보 모터 포트 | Sa, Sb, Sc | - |

<!-- 
### JavaScript
```javascript
$('CheeseStick*0:S_port.Sa.mode').d = $('CheeseStick*0:S_port.Sa.mode^analog_servo_output');
```
-->

### Python
```python
cheesestick = CheeseStick(0)
csd09 = cheesestick.CSD09()

csd09.start_servo_motor('Sa')
```

---

## 서보 모터 각도 설정하기

지정한 포트의 서보 모터 각도를 설정합니다.  
선택할 수 있는 값의 범위는 0 ~ 180 입니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/cheesestick_ext/CSD09/2.png" alt="서보 모터 각도 설정하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 서보 모터 포트 | Sa, Sb, Sc | 마지막 `start_servo_motor` 의 포트 |
| value | 입력값 (필드) | 회전 각도 (도) | 0 ~ 180 정수 | - |

<!-- 
### JavaScript
```javascript
$('CheeseStick*0:output.analog_servo.Sa').d = 90;
```
-->

### Python
```python
cheesestick = CheeseStick(0)
csd09 = cheesestick.CSD09()

csd09.set_servo_motor('Sa', 90)
```

---

## 서보 모터 각도 변경하기

지정한 포트의 서보 모터 각도를 변경합니다.  
선택할 수 있는 값의 범위는 -180 ~ 180 입니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/cheesestick_ext/CSD09/3.png" alt="서보 모터 각도 변경하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 서보 모터 포트 | Sa, Sb, Sc | 마지막 `start_servo_motor` 의 포트 |
| value | 입력값 (필드) | 변경할 각도 차 | 정수 | - |

<!-- 
### JavaScript
```javascript
$('CheeseStick*0:output.analog_servo.Sa').d = $('CheeseStick*0:output.analog_servo.Sa').d + 10;
```
-->

### Python
```python
cheesestick = CheeseStick(0)
csd09 = cheesestick.CSD09()

csd09.change_servo_motor('Sa', 10)
```

---

## 서보 모터 정지하기

지정한 포트의 서보 모터의 전원을 끕니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/cheesestick_ext/CSD09/4.png" alt="서보 모터 정지하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 서보 모터 포트 | Sa, Sb, Sc | 마지막 `start_servo_motor` 의 포트 |

<!-- 
### JavaScript
```javascript
$('CheeseStick*0:S_port.Sa.mode').d = 0;
```
-->

### Python
```python
cheesestick = CheeseStick(0)
csd09 = cheesestick.CSD09()

csd09.stop_servo_motor('Sa')
```

---

## DC 모터 시작하기

지정한 포트를 사용하여 DC 모터를 제어할 수 있도록 합니다.
DC 모터 관련 다른 블록을 사용하기 전에 한 번 호출해야 합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/cheesestick_ext/CSD09/5.png" alt="DC 모터 시작하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | DC 모터 포트 | Mab, Mcd | - |

<!-- 
### JavaScript
```javascript
$('CheeseStick*0:M_port.Ma.mode').d = $('CheeseStick*0:M_port.Ma.mode^pwm_output');
```
-->

### Python
```python
cheesestick = CheeseStick(0)
csd09 = cheesestick.CSD09()

csd09.start_dc_motor('Mab')
```

---

## DC 모터 속도 설정하기

DC 모터의 PWM 출력값을 설정합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/cheesestick_ext/CSD09/6.png" alt="DC 모터 속도 설정하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | DC 모터 포트 | Mab, Mcd | 마지막 `start_dc_motor` 의 포트 |
| value | 입력값 (필드) | PWM 출력값 | 0 ~ 100 정수 | - |

<!-- 
### JavaScript
```javascript
$('CheeseStick*0:output.pwm.Mab').d = 50;
```
-->

### Python
```python
cheesestick = CheeseStick(0)
csd09 = cheesestick.CSD09()

csd09.set_dc_motor('Mab', 50)
```

---

## DC 모터 속도 변경하기

현재 DC 모터의 PWM 출력값에 입력한 변화량을 더해 새로운 값을 설정합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/cheesestick_ext/CSD09/7.png" alt="DC 모터 속도 변경하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | DC 모터 포트 | Mab, Mcd | 마지막 `start_dc_motor` 의 포트 |
| value | 입력값 (필드) | 변경할 PWM 차 | 정수 | - |

<!-- 
### JavaScript
```javascript
$('CheeseStick*0:output.pwm.Mab').d = $('CheeseStick*0:output.pwm.Mab').d + 10;
```
-->

### Python
```python
cheesestick = CheeseStick(0)
csd09 = cheesestick.CSD09()

csd09.change_dc_motor('Mab', 10)
```

---

## DC 모터 정지하기

DC 모터의 출력을 정지합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/cheesestick_ext/CSD09/8.png" alt="DC 모터 정지하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | DC 모터 포트 | Mab, Mcd | 마지막 `start_dc_motor` 의 포트 |

<!-- 
### JavaScript
```javascript
$('CheeseStick*0:output.pwm.Mab').d = 0;
```
-->

### Python
```python
cheesestick = CheeseStick(0)
csd09 = cheesestick.CSD09()

csd09.stop_dc_motor('Mab')
```

---

## 스텝 모터 시작하기

스텝 모터를 사용합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/cheesestick_ext/CSD09/9.png" alt="스텝 모터 시작하기">

### 매개변수

(없음)

<!-- 
### JavaScript
```javascript
$('CheeseStick*0:M_port.mode').d = $('CheeseStick*0:M_port.mode^step_motor');
$('CheeseStick*0:M_port.driver').d = $('CheeseStick*0:M_port.driver^full_step');
```
-->

### Python
```python
cheesestick = CheeseStick(0)
csd09 = cheesestick.CSD09()

csd09.start_step_motor()
```

---

## 스텝 모터 모드 설정하기

스텝 모터를 제어할 모드를 설정합니다.  
별도로 모드를 설정하지 않으면, 기본으로 '파워' 모드로 설정됩니다.  
주의! 스텝 모터가 회전하는 도중에 모드를 바꿔서는 안됩니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/cheesestick_ext/CSD09/10.png" alt="스텝 모터 모드 설정하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 구동 모드 | off(끄기), 기본(wave_step), 파워(full_step) | - |

<!-- 
### JavaScript
```javascript
$('CheeseStick*0:M_port.driver').d = $('CheeseStick*0:M_port.driver^full_step');
```
-->

### Python
```python
cheesestick = CheeseStick(0)
csd09 = cheesestick.CSD09()

csd09.set_step_motor_mode('full_step')
```

---

## 스텝 모터 속도 설정하기

스텝 모터의 속도를 설정합니다.  
선택할 수 있는 값의 범위는 -1000 ~ 1000 입니다.  
값이 음수인 경우, 반대 방향으로 회전합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/cheesestick_ext/CSD09/11.png" alt="스텝 모터 속도 설정하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| value | 입력값 (필드) | 회전 속도 (PPS) | 0 이상 정수 | - |

<!-- 
### JavaScript
```javascript
$('CheeseStick*0:M_port.step.pps').d = 100;
```
-->

### Python
```python
cheesestick = CheeseStick(0)
csd09 = cheesestick.CSD09()

csd09.set_step_motor_speed(100)
```

---

## 스텝 모터 회전하기

스텝 모터를 회전할 펄스 수를 설정합니다.  
선택할 수 있는 값의 범위는 0 ~ 65535 입니다.  
스탭 모터의 속도를 선택하지 않은 경우, 회전하지 않습니다.  
기다리기를 체크하면, 회전이 완료될 때까지 기다립니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/cheesestick_ext/CSD09/12.png" alt="스텝 모터 회전하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| value | 입력값 (필드) | 회전할 스텝 수 | 정수 | - |
| wait | 체크박스 | 완료 대기 여부 | TRUE / FALSE | TRUE |

<!-- 
### JavaScript
```javascript
// wait = TRUE
$('CheeseStick*0:M_port.step.move').d = 360;
await $('CheeseStick*0:M_port.step.!move').w();

// wait = FALSE
$('CheeseStick*0:M_port.step.move').d = 360;
```
-->

### Python
```python
cheesestick = CheeseStick(0)
csd09 = cheesestick.CSD09()

# wait = TRUE
csd09.rotate_step_motor(360, wait=True)

# wait = FALSE
csd09.rotate_step_motor(360, wait=False)
```

---

## 스텝 모터 속도 변경하기

스텝 모터의 속도를 변경합니다.  
선택할 수 있는 값의 범위는 -2000 ~ 2000 입니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/cheesestick_ext/CSD09/13.png" alt="스텝 모터 속도 변경하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| value | 입력값 (필드) | 변경할 PPS 차 | 정수 | - |

<!-- 
### JavaScript
```javascript
$('CheeseStick*0:M_port.step.pps').d = $('CheeseStick*0:M_port.step.pps').d + 10;
```
-->

### Python
```python
cheesestick = CheeseStick(0)
csd09 = cheesestick.CSD09()

csd09.change_step_motor_speed(10)
```

---

## 스텝 모터 정지하기

스텝 모터를 정지하거나 전원을 끕니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/cheesestick_ext/CSD09/14.png" alt="스텝 모터 정지하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 정지 방식 | 정지(stop), 전원 끄기(power) | - |

<!-- 
### JavaScript
```javascript
// unit = "stop"
$('CheeseStick*0:M_port.step.pps').d = 0;
$('CheeseStick*0:M_port.step.move').d = 0;

// unit = "power"
$('CheeseStick*0:M_port.driver').d = $('CheeseStick*0:M_port.driver^off');
$('CheeseStick*0:M_port.step.pps').d = 0;
$('CheeseStick*0:M_port.step.move').d = 0;
```
-->

### Python
```python
cheesestick = CheeseStick(0)
csd09 = cheesestick.CSD09()

# unit = "stop"
csd09.stop_step_motor()

# unit = "power"
csd09.turn_off_step_motor()
```

---

## 누적 스텝 수

스텝 모터가 지금까지 회전한 누적 스텝 수를 반환합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/cheesestick_ext/CSD09/15.png" alt="누적 스텝 수">

### 매개변수

(없음)

<!-- 
### JavaScript
```javascript
$('CheeseStick*0:M_port.step.~move').d
```
-->

### Python
```python
cheesestick = CheeseStick(0)
csd09 = cheesestick.CSD09()

csd09.get_steps()
```
