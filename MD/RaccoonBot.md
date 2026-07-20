# 라쿤봇

## 인스턴스 선언

라쿤봇(RaccoonBot) 블록을 작업 영역에 추가하면, Python 코드에는 다음과 같은 인스턴스 선언이 자동으로 삽입됩니다:

```python
raccoon = RaccoonBot(0)
# 여러 인스턴스가 있는 경우
raccoon_1 = RaccoonBot(1)
```

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| index | 드롭다운 옵션 | 인스턴스 번호 (0부터 시작) | 0 이상 정수 | 0 |


<br>

# 블록 <-> 파이썬 변환 규칙

<!--
## 주변 장치 설정하기

로봇과 연결해 사용할 주변 장치 (Peripheral) 을(를) 설정합니다.  
따로 설정하지 않아도, 연결된 주변 장치를 자동으로 인식하여 제어할 수 있습니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/RaccoonBot/1.png" alt="주변 장치 설정하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 주변 장치 | 없음(none), 컨베이어(conveyor), 슬라이더(slider) | - |

<!-- 
### JavaScript
```javascript
$('Raccoon4*0:peripheral>').d = 1;
```

### Python
```python
raccoon = RaccoonBot(0)

raccoon.peripheral('conveyor')
```

---
-->

## 관절 모터 제어 켜기 / 끄기

각 관절 모터에 가해져 있는 제어를 풀지 유지할지 결정합니다.  
설정하지 않을 경우, 모든 관절의 모터 제어가 켜진 상태로 시작합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/RaccoonBot/2.png" alt="관절 모터 제어 켜기 / 끄기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 관절 번호 | 모든 관절(-1), 1번(1), 2번(2), 3번(3), 4번(4) | -1 |
| on | 체크박스 | 모터 제어 ON / OFF | TRUE / FALSE | TRUE |

<!-- 
### JavaScript
```javascript
// unit = "every"
$('Raccoon4*0:motor_off.joint_1').d = 1;  // off
$('Raccoon4*0:motor_off.joint_2').d = 1;  // off
$('Raccoon4*0:motor_off.joint_3').d = 1;  // off
$('Raccoon4*0:motor_off.joint_4').d = 1;  // off
```
-->

### Python
```python
raccoon = RaccoonBot(0)

# 모든 관절, 모터 제어 끔
raccoon.motor(-1, False)

# 1번 관절, 모터 제어 켬
raccoon.motor(1, True)
```

---

## 관절 속도 설정하기

선택한 관절의 속도를 설정합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/RaccoonBot/3.png" alt="관절 속도 설정하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| joint | 드롭다운 옵션 | 관절 번호 | 모든 관절(-1), 1번(1), 2번(2), 3번(3), 4번(4) | - |
| data | 입력값 (블록) | 관절 속도 | -100 ~ 100 정수 | - |

<!-- 
### JavaScript
```javascript
$('Raccoon4*0:speed.joint_1').d = 100;
```
-->

### Python
```python
raccoon = RaccoonBot(0)

raccoon.set_speed_joint(1, 100)
```

---

## 관절 속도 변경하기

선택한 관절의 속도를 변경합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/RaccoonBot/4.png" alt="관절 속도 변경하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| joint | 드롭다운 옵션 | 관절 번호 | 모든 관절(-1), 1번(1), 2번(2), 3번(3), 4번(4) | - |
| data | 입력값 (블록) | 변경할 속도 차 | -200 ~ 200 정수 | - |

<!-- 
### JavaScript
```javascript
$('Raccoon4*0:speed.joint_1').d = $('Raccoon4*0:speed.joint_1').d + 50;
```
-->

### Python
```python
raccoon = RaccoonBot(0)

raccoon.change_speed_joint(1, 50)
```

---

## 관절 속도 한 번에 설정하기

네 관절의 속도를 한 번에 설정합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/RaccoonBot/5.png" alt="관절 속도 한 번에 설정하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| data | 입력값 (배열) | 4개 관절 속도 배열 | `[joint1, joint2, joint3, joint4]`, 각 -100~100 | - |

<!-- 
### JavaScript
```javascript
$('Raccoon4*0:speed.joint_1').d = 10;
$('Raccoon4*0:speed.joint_2').d = 20;
$('Raccoon4*0:speed.joint_3').d = 30;
$('Raccoon4*0:speed.joint_4').d = 40;
```
-->

### Python
```python
raccoon = RaccoonBot(0)

# 리터럴 배열 [10, 20, 30, 40]
raccoon.set_speed_joints(10, 20, 30, 40)

# 변수 배열
raccoon.set_speed_joints(*arr)
```

---

## 관절 각도 제어 속도 설정하기

각도 제어 모드에서 관절을 제어할 속도를 설정합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/RaccoonBot/6.png" alt="관절 각도 제어 속도 설정하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| data | 입력값 (블록) | 각도 제어 최대 속도 | 0 ~ 100 정수 | - |

<!-- 
### JavaScript
```javascript
$('Raccoon4*0:angle.max_speed').d = 100;
```
-->

### Python
```python
raccoon = RaccoonBot(0)

raccoon.angle_max_speed(100)
```

---

## 관절 각도 설정하기

선택한 관절의 각도를 설정합니다.

| joint | min | max |
|-------|-----|-----|
| 1 | -120 | 120 |
| 2 | -90 | 30 |
| 3 | -150 | 0 |
| 4 | -105 | 105 |

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/RaccoonBot/7.png" alt="관절 각도 설정하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| joint | 드롭다운 옵션 | 관절 번호 | 모든 관절(-1), 1번(1), 2번(2), 3번(3), 4번(4) | - |
| data | 입력값 (블록) | 관절 각도 (도) | 위 표 참조 (자동 clamp) | - |
| wait | 체크박스 | 완료 대기 여부 | TRUE / FALSE | TRUE |

<!-- 
### JavaScript
```javascript
$('Raccoon4*0:angle.joints').d = $('Raccoon4*0:angle.joints').d.map((data, i) => 
  (i + 1 === 1) ? 90 : Math.floor(data)
);
await $('Raccoon4*0:angle.!joints').w();  // wait = TRUE
```
-->

### Python
```python
raccoon = RaccoonBot(0)

raccoon.set_angle_joint(1, 90, wait=True)
```

---

## 관절 각도 변경하기

선택한 관절의 각도를 변경합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/RaccoonBot/8.png" alt="관절 각도 변경하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| joint | 드롭다운 옵션 | 관절 번호 | 모든 관절(-1), 1번(1), 2번(2), 3번(3), 4번(4) | - |
| data | 입력값 (블록) | 변경할 각도 차 (도) | 위 표 참조 (자동 clamp) | - |
| wait | 체크박스 | 완료 대기 여부 | TRUE / FALSE | TRUE |

<!-- 
### JavaScript
```javascript
$('Raccoon4*0:angle.joints').d = $('Raccoon4*0:angle.joints').d.map((data, i) => 
  (i + 1 === 1) ? data + 10 : data
);
await $('Raccoon4*0:angle.!joints').w();
```
-->

### Python
```python
raccoon = RaccoonBot(0)

raccoon.change_angle_joint(1, 10, wait=True)
```

---

## 관절 각도 한 번에 설정하기

네 관절의 각도를 한 번에 설정합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/RaccoonBot/9.png" alt="관절 각도 한 번에 설정하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| data | 입력값 (배열) | 4개 관절 각도 배열 또는 자세 이름 | `[j1, j2, j3, j4]` 배열 | - |
| wait | 체크박스 | 완료 대기 여부 | TRUE / FALSE | TRUE |

<!-- 
### JavaScript
```javascript
$('Raccoon4*0:angle.joints').d = [0, 0, 0, 0];
await $('Raccoon4*0:angle.!joints').w();  // wait = TRUE
```
-->

### Python
```python
raccoon = RaccoonBot(0)

# 명시적 배열
raccoon.set_angle_joints(0, 0, 0, 0, wait=True)
```

---

## 관절 상태 초기화하기

네 관절의 각도를 미리 정의된 자세 (`'zero'`, `'park'`, `'home'`) 로 설정합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/RaccoonBot/10.png" alt="관절 상태 초기화하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| data | 드롭다운 | 자세 이름 | `'zero'` / `'park'` / `'home'` | - |
| wait | 체크박스 | 완료 대기 여부 | TRUE / FALSE | TRUE |

자세 프리셋:
- `'zero'` → `[0, 0, 0, 0]`
- `'park'` → `[0, 25, -145, -60]`
- `'home'` → `[0, -10, -140, 60]`

<!-- 
### JavaScript
```javascript
$('Raccoon4*0:angle.joints').d = [0, 0, 0, 0];
await $('Raccoon4*0:angle.!joints').w();  // wait = TRUE
```
-->

### Python
```python
raccoon = RaccoonBot(0)

# 자세 프리셋
raccoon.set_angle_joints('home', wait=True)
```

---

## 관절 각도 저장하기

현재 엔코더 값을 임의의 변수에 저장합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/RaccoonBot/11.png" alt="관절 각도 저장하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| encoder | 변수 | 저장할 변수 이름 | 변수 | - |
| data | 입력값 (배열) | 저장할 초기 배열 | 4-element 배열 또는 빈 배열 | - |

<!-- 
### JavaScript
```javascript
encoder = [];
```
-->

### Python
```python
raccoon = RaccoonBot(0)
encoder = None

encoder = raccoon.save_encoder([3, -6, -73, 60])
```

---

## 특정 좌표 값 정하기

특정 좌표 값을 설정하여 로봇 팔을 이동합니다.  
각 좌표의 범위는 다음과 같습니다.  
손목 기준 => x: -20.0cm ~ 20.0cm, y: -10.0cm ~ 20.0cm, z: -2.0mm ~ 28.0cm  
그리퍼 기준 => 연결한 장치에 따라 범위가 달라질 수 있습니다.  
그리퍼의 방향은 지면과 수평 또는 수직으로 고정됩니다.  
이동할 수 없는 좌표를 입력했을 경우, 명령을 건너뜁니다.



<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/RaccoonBot/12.png" alt="특정 좌표 값 정하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| origin | 드롭다운 옵션 | 기준점 | 손목(wrist), 말단 장치(end_effector) | - |
| pos | 드롭다운 옵션 | 축 | x, y, z | - |
| data | 입력값 (블록) | 좌표값 | x: -20 ~ 20cm, y: -10 ~ 20cm, z: -2 ~ 28cm | - |
| unit | 드롭다운 옵션 | 단위 | cm, mm, 인치(inch) | cm |
| wait | 체크박스 | 완료 대기 여부 | TRUE / FALSE | TRUE |

<!-- 
### JavaScript
```javascript
$('Raccoon4*0:angle.joints').d = __xyzToAngles(
    'Raccoon4*0',
    __anglesToXyz('Raccoon4*0', [...encoders...], 'wrist')
        .map((data, i) => (i === 0) ? __getCoordinate(10, 'cm') : data),
    'wrist'
);
await $('Raccoon4*0:angle.!joints').w();
```
-->

### Python
```python
raccoon = RaccoonBot(0)

# x 좌표를 10cm 로 정하기
raccoon.set_coordinate('wrist', 'x', 10, 'cm', wait=True)

# end_effector 기준 z 좌표
raccoon.set_coordinate('end_effector', 'z', 15, 'cm', wait=True)
```

---

## 특정 좌표 값 바꾸기

현재 위치를 기준으로 특정 좌표 값을 변경하여 로봇 팔을 이동합니다.  
각 좌표의 범위는 다음과 같습니다.  
손목 기준 => x: -20.0cm ~ 20.0cm, y: -10.0cm ~ 20.0cm, z: -2.0mm ~ 28.0cm  
그리퍼 기준 => 연결한 장치에 따라 범위가 달라질 수 있습니다.  
그리퍼의 방향은 지면과 수평 또는 수직으로 고정됩니다.  
이동할 수 없는 좌표를 입력했을 경우, 명령을 건너뜁니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/RaccoonBot/13.png" alt="특정 좌표 값 바꾸기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| origin | 드롭다운 옵션 | 기준점 | 손목(wrist), 말단 장치(end_effector) | - |
| pos | 드롭다운 옵션 | 축 | x, y, z | - |
| data | 입력값 (블록) | 변경할 좌표 차 | 실수 | - |
| unit | 드롭다운 옵션 | 단위 | cm, mm, 인치(inch) | cm |
| wait | 체크박스 | 완료 대기 여부 | TRUE / FALSE | TRUE |

<!-- 
### JavaScript
```javascript
$('Raccoon4*0:angle.joints').d = __xyzToAngles(
    'Raccoon4*0',
    __anglesToXyz('Raccoon4*0', [...encoders...], 'wrist')
        .map((data, i) => (i === 1) ? data + __getCoordinate(5, 'cm') : data),
    'wrist'
);
await $('Raccoon4*0:angle.!joints').w();
```
-->

### Python
```python
raccoon = RaccoonBot(0)

raccoon.change_coordinate('wrist', 'y', 5, 'cm', wait=True)
```

---

## xyz 좌표로 이동하기

x, y, z 좌표를 각각 지정한 값으로 한 번에 설정합니다.  

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/RaccoonBot/14.png" alt="xyz 좌표로 이동하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| origin | 드롭다운 옵션 | 기준점 | 손목(wrist), 말단 장치(end_effector) | - |
| x | 입력값 (블록) | x 좌표 | 실수 | - |
| y | 입력값 (블록) | y 좌표 | 실수 | - |
| z | 입력값 (블록) | z 좌표 | 실수 | - |
| unit | 드롭다운 옵션 | 단위 | cm, mm, 인치(inch) | cm |
| wait | 체크박스 | 완료 대기 여부 | TRUE / FALSE | TRUE |

<!-- 
### JavaScript
```javascript
$('Raccoon4*0:angle.joints').d = __xyzToAngles(
    'Raccoon4*0',
    [__getCoordinate(0, 'cm'), __getCoordinate(15, 'cm'), __getCoordinate(20, 'cm')],
    'wrist'
);
await $('Raccoon4*0:angle.!joints').w();
```
-->

### Python
```python
raccoon = RaccoonBot(0)

raccoon.set_coordinates('wrist', 0, 15, 20, 'cm', wait=True)
```

---

## 말단 장치 고정 설정하기

그리퍼를 고정할 방향을 설정합니다. 옵션이 수평 또는 수직으로 설정된 이후로는, 관절 4의 속도나 각도를 제어할 수 없습니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/RaccoonBot/15.png" alt="말단 장치 고정 설정하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| mode | 드롭다운 옵션 | 고정 방향 | 고정 안 함(none), 수평(horizontal), 수직(vertical) | - |

<!-- 
### JavaScript
```javascript
$('Raccoon4*0:end_effector.lock').d = $('Raccoon4*0:end_effector.lock^horizontal');
```
-->

### Python
```python
raccoon = RaccoonBot(0)

raccoon.lock('horizontal')
```

---

## 말단 장치로 사물 집기 / 놓기

말단 장치로 사물을 잡거나 놓습니다.  
unit dropdown 값에 따라 두 메서드 중 하나를 호출합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/RaccoonBot/16.png" alt="말단 장치로 사물 집기 / 놓기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 동작 | 집기(pick), 놓기(place) | - |

<!-- 
### JavaScript
```javascript
$('Raccoon4*0:end_effector.control').d = $('Raccoon4*0:end_effector.control^pick');
```
-->

### Python
```python
raccoon = RaccoonBot(0)

# unit = "pick"
raccoon.pick()
# unit = "place"
raccoon.place()
```

---

## 말단 장치 종류

현재 연결되어 있는 그리퍼 번호  
(1, 3, 4: 집게 그리퍼, 2: 진공 그리퍼)

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/RaccoonBot/17.png" alt="말단 장치 종류">

### 매개변수

(없음)

<!-- 
### JavaScript
```javascript
$('Raccoon4*0:end_effector.device').d
```
-->

### Python
```python
raccoon = RaccoonBot(0)

raccoon.end_effector_device()
```

---

## 말단 장치 상태

그리퍼가 사물을 잡고 있는 상태  
(0: 놓은 상태, 1: 잡은 상태)

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/RaccoonBot/18.png" alt="말단 장치 상태">

### 매개변수

(없음)

<!-- 
### JavaScript
```javascript
$('Raccoon4*0:end_effector.status').d
```
-->

### Python
```python
raccoon = RaccoonBot(0)

raccoon.end_effector_status()
```

---

## 음계 연주하기

라쿤봇이 지정된 음계를 재생합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/RaccoonBot/19.png" alt="음계 연주하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| note | 드롭다운 옵션 | 음계 | 도(C), 도#(C#), 레(D), 레#(D#), 미(E), 파(F), 파#(F#), 솔(G), 솔#(G#), 라(A), 라#(A#), 시(B) | - |
| octave | 드롭다운 옵션 | 옥타브 | 1, 2, 3, 4, 5, 6, 7 | 4 |

<!-- 
### JavaScript
```javascript
$('Raccoon4*0:sound.note').d = 49;
```
-->

### Python
```python
raccoon = RaccoonBot(0)

raccoon.sound_note('D', 5)
```

---

## 소리 재생하기

라쿤봇이 특정 사운드 클립을 재생합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/RaccoonBot/20.png" alt="소리 재생하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| clip | 드롭다운 옵션 | 사운드 클립 이름 | `'mute'`, `'beep'`, `'siren'`, `'robot'`, `'connect'`, `'wake_up'`, `'start'`, `'bye'` 등 | - |
| wait | 체크박스 | 완료 대기 여부 | TRUE / FALSE | TRUE |

<!-- 
### JavaScript
```javascript
$('Raccoon4*0:sound.clip').d = $('Raccoon4*0:sound.clip^siren');
await $('Raccoon4*0:sound.!clip').w();  // wait = TRUE
```
-->

### Python
```python
raccoon = RaccoonBot(0)

raccoon.sound_clip('siren', wait=True)
```

---

## 소리 끄기

라쿤봇의 소리를 끕니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/RaccoonBot/21.png" alt="소리 끄기">

### 매개변수

(없음)

<!-- 
### JavaScript
```javascript
__stopSound('Raccoon4*0');
```
-->

### Python
```python
raccoon = RaccoonBot(0)

raccoon.sound_off()
```

---

## 엔코더 값

선택한 관절의 엔코더 값

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/RaccoonBot/22.png" alt="엔코더 값">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| joint | 드롭다운 옵션 | 관절 번호 (또는 모든 관절) | 1, 2, 3, 4, 모든 관절(-1) | -1 |

<!-- 
### JavaScript
```javascript
// unit = "joint_1"
$('Raccoon4*0:encoder.joint_1').d

// unit = "encoders"
[$('Raccoon4*0:encoder.joint_1').d, $('Raccoon4*0:encoder.joint_2').d, $('Raccoon4*0:encoder.joint_3').d, $('Raccoon4*0:encoder.joint_4').d]
```
-->

### Python
```python
raccoon = RaccoonBot(0)

# joint = 1
raccoon.encoder(1)

# 모든 관절
raccoon.encoder(-1)
```

---

## 선택한 요소의 좌표

기준점의 현재 xyz 좌표를 반환합니다.  
`pos` 를 생략하면 `[x, y, z]` 전체 배열을, 지정하면 해당 축 값만 반환합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/RaccoonBot/23.png" alt="선택한 요소의 좌표">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| origin | 드롭다운 옵션 | 기준점 | 손목(wrist), 말단 장치(end_effector) | wrist |
| pos | 드롭다운 옵션 | 축 (또는 전체) | x, y, z, 전체(생략 시 전체 배열 반환) | None (전체) |

<!-- 
### JavaScript
```javascript
// pos = "x"
__anglesToXyz('Raccoon4*0', [$('Raccoon4*0:encoder.joint_1').d, $('Raccoon4*0:encoder.joint_2').d, $('Raccoon4*0:encoder.joint_3').d, $('Raccoon4*0:encoder.joint_4').d], 'cm')[0]
```
-->

### Python
```python
raccoon = RaccoonBot(0)

# 특정 축
raccoon.get_coordinates('wrist', 'x')

# 전체 (3-element 배열)
raccoon.get_coordinates('wrist')
```

---

## 신호 세기 값

신호 세기

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/RaccoonBot/24.png" alt="신호 세기 값">

### 매개변수

(없음)

<!-- 
### JavaScript
```javascript
$('Raccoon4*0:signal_strength').d
```
-->

### Python
```python
raccoon = RaccoonBot(0)

raccoon.signal_strength()
```

---

## 배터리 전압

배터리 전압

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/RaccoonBot/25.png" alt="배터리 전압">

### 매개변수

(없음)

<!-- 
### JavaScript
```javascript
$('Raccoon4*0:battery.level').d
```
-->

### Python
```python
raccoon = RaccoonBot(0)

raccoon.battery()
```

---

## 버튼이 눌려있는가?

선택한 버튼이 눌려있는지 또는 클릭 이벤트가 발생했는지 여부

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/RaccoonBot/26.png" alt="버튼이 눌려있는가?">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 버튼 이름 | 학습(teach), 재생(play), 전원(power), 삭제(delete), 어떤 버튼이든(any) | - |
| event | 드롭다운 옵션 | 이벤트 종류 | 눌림(pressed), 클릭(click), 길게 클릭(long_click) | - |

<!-- 
### JavaScript
```javascript
$('Raccoon4*0:button.pressed.pick').d
```
-->

### Python
```python
raccoon = RaccoonBot(0)

raccoon.button('teach', 'pressed')
```

---

## 컨베이어 속도 설정하기

컨베이어 벨트의 속도를 설정합니다. 속도의 범위는 -100 ~ 100 입니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/RaccoonBot/27.png" alt="컨베이어 속도 설정하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| data | 입력값 (블록) | 컨베이어 속도 | -100 ~ 100 정수 | - |

<!-- 
### JavaScript
```javascript
$('Raccoon4*0:peripheral>conveyor+speed').d = 100;
```
-->

### Python
```python
raccoon = RaccoonBot(0)

raccoon.set_conveyor_speed(100)
```

---

## 컨베이어 이동 거리 설정하기

컨베이어로 일정 거리만큼 이동시킵니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/RaccoonBot/28.png" alt="컨베이어 이동 거리 설정하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| data | 입력값 (블록) | 이동 거리 | 0 이상 실수 | - |
| unit | 드롭다운 옵션 | 거리 단위 | cm, mm, 인치(inch) | cm |
| wait | 체크박스 | 완료 대기 여부 | TRUE / FALSE | TRUE |

<!-- 
### JavaScript
```javascript
$('Raccoon4*0:peripheral>conveyor+distance').d = __getDistance('Conveyor', 50, 'cm');
await $('Raccoon4*0:peripheral>conveyor+!distance').w();  // wait = TRUE
```
-->

### Python
```python
raccoon = RaccoonBot(0)

raccoon.conveyor_move(50, 'cm', wait=True)
```

---

## 컨베이어 속도 변경하기

컨베이어 벨트의 속도를 변경합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/RaccoonBot/29.png" alt="컨베이어 속도 변경하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| data | 입력값 (블록) | 변경할 속도 차 | -200 ~ 200 정수 | - |

<!-- 
### JavaScript
```javascript
$('Raccoon4*0:peripheral>conveyor+speed').d = $('Raccoon4*0:peripheral>conveyor+speed').d + 10;
```
-->

### Python
```python
raccoon = RaccoonBot(0)

raccoon.change_conveyor_speed(10)
```

---

## 컨베이어 정지하기

컨베이어를 정지합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/RaccoonBot/30.png" alt="컨베이어 정지하기">

### 매개변수

(없음)

<!-- 
### JavaScript
```javascript
$('Raccoon4*0:peripheral>conveyor+distance').d = 0;
$('Raccoon4*0:peripheral>conveyor+speed').d = 0;
```
-->

### Python
```python
raccoon = RaccoonBot(0)

raccoon.stop_conveyor()
```

---

## 컨베이어가 동작 중인가?

컨베이어 벨트 동작 여부

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/RaccoonBot/31.png" alt="컨베이어가 동작 중인가?">

### 매개변수

(없음)

<!-- 
### JavaScript
```javascript
$('Raccoon4*0:peripheral>conveyor+running').d
```
-->

### Python
```python
raccoon = RaccoonBot(0)

raccoon.conveyor_running()
```

---

## 컨베이어 버튼이 눌려있는가?

컨베이어의 버튼이 눌려있는지 또는 클릭 이벤트가 발생했는지 여부

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/RaccoonBot/32.png" alt="컨베이어 버튼이 눌려있는가?">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| event | 드롭다운 옵션 | 이벤트 종류 | 눌려있는가(pressed), 클릭했는가(click), 길게 클릭했는가(long_click) | - |

<!-- 
### JavaScript
```javascript
$('Raccoon4*0:peripheral>conveyor+button.pressed').d
```
-->

### Python
```python
raccoon = RaccoonBot(0)

raccoon.conveyor_button('pressed')
```
