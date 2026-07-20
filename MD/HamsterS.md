# 햄스터 S

## 인스턴스 선언

햄스터 S(HamsterS) 블록을 작업 영역에 추가하면, Python 코드에는 다음과 같은 인스턴스 선언이 자동으로 삽입됩니다:

```python
hamster_s = HamsterS(0)
# 여러 인스턴스가 있는 경우
hamster_s_1 = HamsterS(1)
```

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| index | 드롭다운 옵션 | 인스턴스 번호 (0부터 시작) | 0 이상 정수 | 0 |


<br>

# 블록 <-> 파이썬 변환 규칙

## 바퀴 속도 설정하기

바퀴 속도를 결정합니다. 속도의 범위는 -100 ~ 100 입니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/HamsterS/1.png" alt="바퀴 속도 설정하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 바퀴 종류 | 왼쪽(left), 오른쪽(right), 양쪽(both) | - |
| speed | 입력값 (블록) | 바퀴 속도 | -100 ~ 100 정수, 0: 정지 | - |

<!-- 
### JavaScript
```javascript
if($('HamsterS*0:wheel.move').d != 0) {
    $('HamsterS*0:wheel.move').d = 0;
}
$('HamsterS*0:wheel.speed.left').d = __getSpeed('HamsterS*0', 50);
$('HamsterS*0:wheel.speed.right').d = __getSpeed('HamsterS*0', 50);
```
-->

### Python
```python
hamster_s = HamsterS(0)

hamster_s.set_wheel_speed('both', 50)
```

---

## 거리 이동하기

현재 바퀴 속도로 지정한 거리만큼 이동합니다.  
바퀴 속도를 설정하지 않은 경우, 기본 속도로 앞으로 이동합니다.  
거리 값이 0일 경우, 현재 바퀴 속도에 따라 계속 이동합니다.  
기다리기를 체크하면, 이동이 완료될 때까지 기다립니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/HamsterS/2.png" alt="거리 이동하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| data | 입력값 (블록) | 이동 거리 | 0 이상 실수 | - |
| unit | 드롭다운 옵션 | 거리 단위 | cm, mm, 인치(inch) | cm |
| wait | 체크박스 | 완료 대기 여부 | TRUE / FALSE | TRUE |

<!-- 
### JavaScript
```javascript
$('HamsterS*0:wheel.move').d = __getDistance('HamsterS*0', 50, 'cm');
await $('HamsterS*0:wheel.!move').w();  // wait = TRUE
```
-->

### Python
```python
hamster_s = HamsterS(0)

hamster_s.move_distance(50, 'cm', wait=True)
```

---

## 시간 이동하기

현재 바퀴 속도로 지정한 시간동안 이동합니다.  
바퀴 속도를 설정하지 않은 경우, 기본 속도로 앞으로 이동합니다.  
기다리기를 체크하면, 이동이 완료될 때까지 기다립니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/HamsterS/3.png" alt="시간 이동하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| data | 입력값 (블록) | 이동 시간 (초) | 0 이상 실수 | - |
| wait | 체크박스 | 완료 대기 여부 | TRUE / FALSE | TRUE |

<!-- 
### JavaScript
```javascript
await __stopAfterDelay('HamsterS*0', 5, true);    // wait=true
__stopAfterDelay('HamsterS*0', 5, false);          // wait=false
```
-->

### Python
```python
hamster_s = HamsterS(0)

# wait = TRUE
hamster_s.move_time(5, wait=True)
# wait = FALSE
hamster_s.move_time(5, wait=False)
```

---

## 제자리 돌기

제자리에서 회전할 방향과 각도를 설정합니다.  
기다리기를 체크하면, 회전이 완료될 때까지 기다립니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/HamsterS/4.png" alt="제자리 돌기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| direction | 드롭다운 옵션 | 회전 방향 | 왼쪽(left), 오른쪽(right) | - |
| data | 입력값 (블록) | 회전 각도 (도) | 0 이상 실수 | - |
| wait | 체크박스 | 완료 대기 여부 | TRUE / FALSE | TRUE |

<!-- 
### JavaScript
```javascript
await __turn_degree_left('HamsterS*0', 90, true);   // direction=left
await __turn_degree_right('HamsterS*0', 90, true);  // direction=right
```
-->

### Python
```python
hamster_s = HamsterS(0)

hamster_s.turn_degree('left', 90, wait=True)
```

---

## 바퀴 속도 변경하기

햄스터 S의 바퀴 속도를 변경합니다.  
현재의 바퀴 속도에 입력한 속도를 더한 값이 새로운 바퀴 속도가 됩니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/HamsterS/5.png" alt="바퀴 속도 변경하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 바퀴 종류 | 왼쪽(left), 오른쪽(right), 양쪽(both) | - |
| speed | 입력값 (블록) | 변경할 속도 차 | -200 ~ 200 정수 | - |

<!-- 
### JavaScript
```javascript
if($('HamsterS*0:wheel.move').d != 0) {
    $('HamsterS*0:wheel.move').d = 0;
}
$('HamsterS*0:wheel.speed.left').d = $('HamsterS*0:wheel.speed.left').d + __getSpeed('HamsterS*0', 10);
$('HamsterS*0:wheel.speed.right').d = $('HamsterS*0:wheel.speed.right').d + __getSpeed('HamsterS*0', 10);
```
-->

### Python
```python
hamster_s = HamsterS(0)

hamster_s.change_wheel_speed('both', 10)
```

---

## 정지하기

햄스터 S의 이동을 멈춥니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/HamsterS/6.png" alt="정지하기">

### 매개변수

(없음)

<!-- 
### JavaScript
```javascript
__stopMove('HamsterS*0');
```
-->

### Python
```python
hamster_s = HamsterS(0)

hamster_s.stop()
```

---

## 바퀴가 움직이는 중인가?

바퀴가 움직이는 중이면 true, 멈춰있으면 false를 반환합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/HamsterS/7.png" alt="바퀴가 움직이는 중인가?">

### 매개변수

(없음)

<!-- 
### JavaScript
```javascript
$('HamsterS*0:wheel.moving').d
```
-->

### Python
```python
hamster_s = HamsterS(0)

hamster_s.wheel_moving()
```

---

## 말판 앞으로 한 칸 이동하기

말판 위에서 정해진 대로 한 칸씩 움직입니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/HamsterS/8.png" alt="말판 앞으로 한 칸 이동하기">

### 매개변수

없음.

<!-- 
### JavaScript
```javascript
await __grid_move_forward('HamsterS*0', true);
```
-->

### Python
```python
hamster_s = HamsterS(0)

hamster_s.grid_move()
```

---

## 말판에서 한번 돌기

말판 위에서 정해진 방향으로 90도 회전합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/HamsterS/9.png" alt="말판에서 한번 돌기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| direction | 드롭다운 옵션 | 회전 방향 | 왼쪽(left), 오른쪽(right) | - |

<!-- 
### JavaScript
```javascript
await __grid_turn_left('HamsterS*0', true);   // unit=left
await __grid_turn_right('HamsterS*0', true);  // unit=right
```
-->

### Python
```python
hamster_s = HamsterS(0)

hamster_s.grid_turn('left')
```

---

## 펜 홀더 기준 회전하기

펜 홀더를 사용할 때, 회전할 기준과 방향, 각도를 설정합니다.  
기다리기를 체크하면, 회전이 완료될 때까지 기다립니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/HamsterS/10.png" alt="펜 홀더 기준 회전하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| base | 드롭다운 옵션 | 회전 기준 | 왼쪽 펜(left_pen), 오른쪽 펜(right_pen), 왼쪽 바퀴(left_wheel), 오른쪽 바퀴(right_wheel) | - |
| direction | 드롭다운 옵션 | 회전 방향 | 앞(forward), 뒤(backward) | - |
| degree | 입력값 (블록) | 회전 각도 (도) | 0 이상 실수 | - |
| wait | 체크박스 | 완료 대기 여부 | TRUE / FALSE | TRUE |

<!-- 
### JavaScript
```javascript
await __pivot('HamsterS*0', 'left pen', 'forward', 90, true);
```
-->

### Python
```python
hamster_s = HamsterS(0)

hamster_s.pivot('left_pen', 'forward', 90, wait=True)
```

---

## 펜 홀더 기준 원 그리며 돌기

펜 홀더를 사용해 원을 그릴 때, 회전할 기준과 방향, 반지름, 각도를 설정합니다.  
기다리기를 체크하면, 회전이 완료될 때까지 기다립니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/HamsterS/11.png" alt="펜 홀더 기준 원 그리며 돌기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| base | 드롭다운 옵션 | 회전 기준 | 왼쪽 펜(left_pen), 오른쪽 펜(right_pen) | - |
| direction | 드롭다운 옵션 | 회전 방향 | 왼쪽 앞(left_forward), 왼쪽 뒤(left_backward), 오른쪽 앞(right_forward), 오른쪽 뒤(right_backward) | - |
| degree | 입력값 (블록) | 회전 각도 (도) | 0 이상 실수 | - |
| radius | 입력값 (블록) | 회전 반지름 | 0 이상 실수 | - |
| unit | 드롭다운 옵션 | 반지름 단위 | cm, mm, 인치(inch) | cm |
| wait | 체크박스 | 완료 대기 여부 | TRUE / FALSE | TRUE |

<!-- 
### JavaScript
```javascript
await __pivot_circle('HamsterS*0', 'left pen', 'left forward', __getDistance('HamsterS*0', 1, 'cm'), 90, true);
```
-->

### Python
```python
hamster_s = HamsterS(0)

hamster_s.pivot_circle('left_pen', 'left_forward', 90, 1, 'cm', wait=True)
```

---

## 센서로 선 따라가기

햄스터 S가 바닥 센서를 이용하여 특정한 색의 선을 따라갑니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/HamsterS/12.png" alt="센서로 선 따라가기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| floor | 드롭다운 옵션 | 따라갈 바닥 센서 | 왼쪽(left), 오른쪽(right), 가운데(center) | - |
| line | 드롭다운 옵션 | 선 색 | 검정(black), 흰색(white) | black |

<!-- 
### JavaScript
```javascript
$('HamsterS*0:wheel.trace.mode').d = <const_value>;  // unit+color 조합으로 constants 조회
```
-->

### Python
```python
hamster_s = HamsterS(0)

hamster_s.trace_line('left', 'black')
```

---

## 교차로 이동 후 다음 교차로에서 멈추기

햄스터 S가 교차로에서 지정한 방향으로 이동한 뒤, 다음 교차로를 만날 때까지 이동합니다.  
기다리기를 체크하면, 이동이 완료될 때까지 기다립니다.  

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/HamsterS/13.png" alt="교차로 이동 후 다음 교차로에서 멈추기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| direction | 드롭다운 옵션 | 교차로 이동 방향 | 좌회전(left), 우회전(right), 전진(forward), 유턴(uturn) | - |
| line | 드롭다운 옵션 | 선 색 | 검정(black), 흰색(white) | black |
| wait | 체크박스 | 완료 대기 여부 | TRUE / FALSE | TRUE |

<!-- 
### JavaScript
```javascript
$('HamsterS*0:wheel.trace.mode').d = <const_value>;  // "grid_black_left" 등으로 조회
await $('HamsterS*0:wheel.trace.!mode').w();           // wait = TRUE
```
-->

### Python
```python
hamster_s = HamsterS(0)

hamster_s.trace_intersection('left', 'black', wait=True)
```

---

## 선 따라가기 속도 설정

선 따라가기 속도를 설정합니다. 속도의 범위는 1 ~ 10 입니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/HamsterS/14.png" alt="선 따라가기 속도 설정">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| data | 입력값 (블록) | 선 따라가기 속도 | 1 ~ 10 정수 | - |

<!-- 
### JavaScript
```javascript
$('HamsterS*0:wheel.trace.speed').d = 5;
```
-->

### Python
```python
hamster_s = HamsterS(0)

hamster_s.set_trace_speed(5)
```

---

## 선 따라가기 방향 변화량 설정

선 따라가기 방향 변화량을 설정합니다. 변화량의 범위는 1 ~ 10 입니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/HamsterS/15.png" alt="선 따라가기 방향 변화량 설정">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| data | 입력값 (블록) | 방향 변화량 | 1 ~ 10 정수 | - |

<!-- 
### JavaScript
```javascript
$('HamsterS*0:wheel.trace.gain').d = 5;
```
-->

### Python
```python
hamster_s = HamsterS(0)

hamster_s.set_trace_gain(5)
```

---

## 선 따라가기 멈추기

햄스터 S의 선 따라가기 기능을 종료합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/HamsterS/16.png" alt="선 따라가기 멈추기">

### 매개변수

(없음)

<!-- 
### JavaScript
```javascript
$('HamsterS*0:wheel.trace.mode').d = 0;
```
-->

### Python
```python
hamster_s = HamsterS(0)

hamster_s.stop_trace()
```

---

## LED 색 설정하기

햄스터 S의 LED 색을 설정합니다.  
색상 팔레트에서 색을 선택하면 **색 이름**(영문 문자열)으로 변환되어 호출됩니다. (R, G, B 숫자 값이 아니라 색 이름으로 코드가 생성됩니다.)

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/HamsterS/17.png" alt="LED 색 설정하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 대상 LED | 왼쪽(left), 오른쪽(right), 양쪽(both) | - |
| color | 색상 | 색상 팔레트 선택 → 색 이름(영문)으로 변환 | 색 이름: `'black'`, `'red'`, `'yellow'`, `'green'`, `'cyan'`, `'blue'`, `'magenta'`, `'white'` | - |

<!-- 
### JavaScript
```javascript
// unit=both, color=#ff0000
$('HamsterS*0:led.left').d = [255, 0, 0];
$('HamsterS*0:led.right').d = [255, 0, 0];
```
-->

### Python
```python
hamster_s = HamsterS(0)

hamster_s.set_led_color('both', 'red')
```

---

## 색상 카테고리 블록으로 LED 색 설정하기

색상 카테고리 블록 (`[R, G, B]`) 을 입력으로 받아 LED 색을 설정합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/HamsterS/18.png" alt="색상 카테고리 블록으로 LED 색 설정하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 대상 LED | 왼쪽(left), 오른쪽(right), 양쪽(both) | - |
| data | 입력값 (색상) | 색상 카테고리 블록 또는 `[R, G, B]` 배열 | `[0~255, 0~255, 0~255]` | - |

<!-- 
### JavaScript
```javascript
$('HamsterS*0:led.left').d = [255, 128, 0];
$('HamsterS*0:led.right').d = [255, 128, 0];
```
-->

### Python
```python
hamster_s = HamsterS(0)

hamster_s.set_led_color('both', *Utils.color_rgb(255, 128, 0))
```

---

## RGB 만큼 LED 색 변경하기

지정한 R, G, B 값만큼 햄스터 S의 LED 색을 변경합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/HamsterS/19.png" alt="RGB 만큼 LED 색 변경하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 대상 LED | 왼쪽(left), 오른쪽(right), 양쪽(both) | - |
| r | 입력값 (필드) | 빨강 변화량 | -255 ~ 255 정수 | 0 |
| g | 입력값 (필드) | 초록 변화량 | -255 ~ 255 정수 | 0 |
| b | 입력값 (필드) | 파랑 변화량 | -255 ~ 255 정수 | 0 |

<!-- 
### JavaScript
```javascript
// unit=both, red=10, green=0, blue=0
$('HamsterS*0:led.left').d = [$('HamsterS*0:led.left').d[0] + 10, $('HamsterS*0:led.left').d[1] + 0, $('HamsterS*0:led.left').d[2] + 0];
$('HamsterS*0:led.right').d = [$('HamsterS*0:led.right').d[0] + 10, $('HamsterS*0:led.right').d[1] + 0, $('HamsterS*0:led.right').d[2] + 0];
```
-->

### Python
```python
hamster_s = HamsterS(0)

hamster_s.change_led_color('both', 10, 0, 0)
```

---

## LED 끄기

LED 색을 없앱니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/HamsterS/20.png" alt="LED 끄기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 대상 LED | 왼쪽(left), 오른쪽(right), 양쪽(both) | both |

<!-- 
### JavaScript
```javascript
$('HamsterS*0:led.left').d = [0, 0, 0];
$('HamsterS*0:led.right').d = [0, 0, 0];
```
-->

### Python
```python
hamster_s = HamsterS(0)

hamster_s.turn_off('both')
```

---

## 버저음 설정하기

지정된 주파수로 햄스터 S의 버저음을 설정합니다.  
소리 낼 수 있는 주파수의 범위는 122.1hz ~ 4186.0hz 입니다.  
이외의 값을 입력하면 버저음이 발생하지 않습니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/HamsterS/21.png" alt="버저음 설정하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| hz | 입력값 (블록) | 주파수 (Hz) | 122.1 ~ 4186.0 실수 (그 외 0) | - |

<!-- 
### JavaScript
```javascript
$('HamsterS*0:sound.buzz').d = 440;
```
-->

### Python
```python
hamster_s = HamsterS(0)

hamster_s.sound_buzz(440)
```

---

## 음계 연주하기

햄스터 S가 지정된 음계를 재생합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/HamsterS/22.png" alt="음계 연주하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| note | 드롭다운 옵션 | 음계 | 도(C), 도#(C#), 레(D), 레#(D#), 미(E), 파(F), 파#(F#), 솔(G), 솔#(G#), 라(A), 라#(A#), 시(B) | - |
| octave | 드롭다운 옵션 | 옥타브 | 3, 4, 5, 6, 7 | 4 |

<!-- 
### JavaScript
```javascript
$('HamsterS*0:sound.note').d = 40;  // 도, 4옥타브
```
-->

### Python
```python
hamster_s = HamsterS(0)

hamster_s.sound_note('D', 5)
```

---

## 소리 재생하기

햄스터 S가 특정 사운드 클립을 재생합니다.  
기다리기를 체크하면, 재생이 완료될 때까지 기다립니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/HamsterS/23.png" alt="소리 재생하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| clip | 드롭다운 옵션 | 사운드 클립 이름 | `'mute'`, `'beep'`, `'siren'`, `'engine'`, `'robot'`, `'march'`, `'birthday'`, `'happy'`, `'angry'`, `'sad'` 등 | - |
| wait | 체크박스 | 완료 대기 여부 | TRUE / FALSE | TRUE |

<!-- 
### JavaScript
```javascript
$('HamsterS*0:sound.clip').d = 1;
await $('HamsterS*0:sound.!clip').w();  // wait = TRUE
```
-->

### Python
```python
hamster_s = HamsterS(0)

hamster_s.sound_clip('siren', wait=True)
```

---

## 소리 끄기

햄스터 S의 소리를 끕니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/HamsterS/24.png" alt="소리 끄기">

### 매개변수

(없음)

<!-- 
### JavaScript
```javascript
__stopSound('HamsterS*0');
```
-->

### Python
```python
hamster_s = HamsterS(0)

hamster_s.sound_off()
```

---

## 소리가 재생 중인가?

소리가 재생 중이면 true, 재생 중이 아니면 false를 반환합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/HamsterS/25.png" alt="소리가 재생 중인가?">

### 매개변수

(없음)

<!-- 
### JavaScript
```javascript
$('HamsterS*0:sound.playing').d
```
-->

### Python
```python
hamster_s = HamsterS(0)

hamster_s.sound_playing()
```

---

## 바퀴 속도 값

특정 바퀴의 속도

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/HamsterS/26.png" alt="바퀴 속도 값">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 대상 바퀴 | 왼쪽(left), 오른쪽(right) | - |

<!-- 
### JavaScript
```javascript
__getSpeedInput('HamsterS*0', $('HamsterS*0:wheel.speed.left').d)
```
-->

### Python
```python
hamster_s = HamsterS(0)

hamster_s.wheel_speed('left')
```

---

## 근접 센서 값

특정 근접 센서의 값

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/HamsterS/27.png" alt="근접 센서 값">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 측정 센서 위치 | 왼쪽(left), 오른쪽(right) | - |

<!-- 
### JavaScript
```javascript
$('HamsterS*0:proximity.left').d
```
-->

### Python
```python
hamster_s = HamsterS(0)

hamster_s.proximity('left')
```

---

## 바닥 센서 값

특정 바닥 센서의 값

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/HamsterS/28.png" alt="바닥 센서 값">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 측정 센서 위치 | 왼쪽(left), 오른쪽(right) | - |

<!-- 
### JavaScript
```javascript
$('HamsterS*0:floor.left').d
```
-->

### Python
```python
hamster_s = HamsterS(0)

hamster_s.floor('left')
```

---

## 중력 가속도 값

특정 축의 중력 가속도 값

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/HamsterS/29.png" alt="중력 가속도 값">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 측정 축 | x, y, z | - |

<!-- 
### JavaScript
```javascript
$('HamsterS*0:acceleration.x').d
```
-->

### Python
```python
hamster_s = HamsterS(0)

hamster_s.acceleration('x')
```

---

## 밝기 센서 값

밝기 센서 값

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/HamsterS/30.png" alt="밝기 센서 값">

### 매개변수

(없음)

<!-- 
### JavaScript
```javascript
$('HamsterS*0:light').d
```
-->

### Python
```python
hamster_s = HamsterS(0)

hamster_s.light()
```

---

## 온도 센서 값

온도 센서 값

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/HamsterS/31.png" alt="온도 센서 값">

### 매개변수

(없음)

<!-- 
### JavaScript
```javascript
$('HamsterS*0:temperature').d
```
-->

### Python
```python
hamster_s = HamsterS(0)

hamster_s.temperature()
```

---

## 신호 세기 값

신호 세기

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/HamsterS/32.png" alt="신호 세기 값">

### 매개변수

(없음)

<!-- 
### JavaScript
```javascript
$('HamsterS*0:signal_strength').d
```
-->

### Python
```python
hamster_s = HamsterS(0)

hamster_s.signal_strength()
```

---

## 배터리 전압

배터리 전압

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/HamsterS/33.png" alt="배터리 전압">

### 매개변수

(없음)

<!-- 
### JavaScript
```javascript
$('HamsterS*0:battery.level').d
```
-->

### Python
```python
hamster_s = HamsterS(0)

hamster_s.battery()
```

---

## 상태 변경 여부

로봇의 상태가 변했는지 여부

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/HamsterS/34.png" alt="상태 변경 여부">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 상태 종류 | 0 ~ 7 (아래 표 참조) | - |

| unit | 의미 | Python |
|------|------|--------|
| 0 | 앞으로 기울임 | `acceleration('x') > 5000` |
| 1 | 뒤로 기울임 | `acceleration('x') < -5000` |
| 2 | 왼쪽으로 기울임 | `acceleration('y') > 5000` |
| 3 | 오른쪽으로 기울임 | `acceleration('y') < -5000` |
| 4 | 거꾸로 뒤집힘 | `acceleration('z') > 0` |
| 5 | 뒤집어지지 않음 | `acceleration('z') < -3000` |
| 6 | 장애물/손 감지 | `proximity('left') > 50 or proximity('right') > 50` |
| 7 | 두드림 | `tap()` |

<!-- 
### JavaScript
```javascript
$('HamsterS*0:acceleration.x').d > 5000       // unit=0
$('HamsterS*0:acceleration.tap').e             // unit=7
$('HamsterS*0:proximity.left').d > 50 || $('HamsterS*0:proximity.right').d > 50  // unit=6
```
-->

### Python
```python
hamster_s = HamsterS(0)

# unit = 0
hamster_s.acceleration('x') > 5000
# unit = 6
hamster_s.proximity('left') > 50 or hamster_s.proximity('right') > 50
# unit = 7
hamster_s.tap()
```

---

## 입출력 포트 입력 모드 설정하기

IO 포트의 입력 모드를 설정합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/HamsterS/35.png" alt="입출력 포트 입력 모드 설정하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 입출력 포트 | a, b, 양쪽(both) | - |
| option | 드롭다운 옵션 | 입출력 모드 | analog_input, digital_input, digital_input_pullup, digital_input_pulldown, analog_input_voltage, servo_output, pwm_output, digital_output | - |

<!-- 
### JavaScript
```javascript
// unit=both, option=analog_input
$('HamsterS*0:io.a.mode').d = <const_value>;
$('HamsterS*0:io.b.mode').d = <const_value>;
```
-->

### Python
```python
hamster_s = HamsterS(0)

hamster_s.io_mode('both', 'analog_input')
```

---

## 입출력 포트 출력값 설정하기

지정한 IO 포트의 출력 값을 설정합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/HamsterS/36.png" alt="입출력 포트 출력값 설정하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 입출력 포트 | a, b, 양쪽(both) | - |
| data | 입력값 (블록) | 출력값 | 0 ~ 180 정수 | - |

<!-- 
### JavaScript
```javascript
$('HamsterS*0:io.a.out').d = 90;
```
-->

### Python
```python
hamster_s = HamsterS(0)

hamster_s.set_output('a', 90)
```

---

## 입출력 포트 출력값 변경하기

지정한 IO 포트의 출력 값을 변경합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/HamsterS/37.png" alt="입출력 포트 출력값 변경하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 입출력 포트 | a, b, 양쪽(both) | - |
| data | 입력값 (블록) | 변경할 출력값 차 | 정수 | - |

<!-- 
### JavaScript
```javascript
$('HamsterS*0:io.a.out').d = $('HamsterS*0:io.a.out').d + 10;
```
-->

### Python
```python
hamster_s = HamsterS(0)

hamster_s.change_output('a', 10)
```

---

## 집게 열기 / 닫기

햄스터 S의 집게를 열거나 닫습니다.  
unit 값에 따라 두 메서드 중 하나를 호출합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/HamsterS/38.png" alt="집게 열기 / 닫기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 동작 | 열기(open), 닫기(close) | - |

<!-- 
### JavaScript
```javascript
$('HamsterS*0:io.gripper').d = <const_value>;  // 'open' 또는 'close' 상수값
```
-->

### Python
```python
hamster_s = HamsterS(0)

# unit = "open"
hamster_s.open_gripper()
# unit = "close"
hamster_s.close_gripper()
```

---

## 슈터 각도 설정하기

슈터 각도를 설정하여 제어합니다. 각도의 범위는 0 ~ 180 입니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/HamsterS/39.png" alt="슈터 각도 설정하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| data | 입력값 (블록) | 슈터 각도 | 0 ~ 180 정수 | - |

<!-- 
### JavaScript
```javascript
$('HamsterS*0:io.shooter').d = 45;
```
-->

### Python
```python
hamster_s = HamsterS(0)

hamster_s.shooter(45)
```

---

## 입출력 포트 입력 값

햄스터 S의 입출력 포트 입력 값을 반환합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/roboids/HamsterS/40.png" alt="입출력 포트 입력 값">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 입출력 포트 | a, b | - |

<!-- 
### JavaScript
```javascript
$('HamsterS*0:io.a.in').d
```
-->

### Python
```python
hamster_s = HamsterS(0)

hamster_s.get_input('a')
```
