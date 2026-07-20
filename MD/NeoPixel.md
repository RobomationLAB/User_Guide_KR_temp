# 네오픽셀

## 인스턴스 선언

네오픽셀(NeoPixel) 블록을 작업 영역에 추가하면, Python 코드에는 다음과 같은 인스턴스 선언이 자동으로 삽입됩니다:

```python
cheesestick = CheeseStick(0)
neopixel = cheesestick.NeoPixel()
```

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| index | 드롭다운 옵션 | 인스턴스 번호 (0부터 시작) | 0 이상 정수 | 0 |


<br>

# 블록 <-> 파이썬 변환 규칙

## 시작하기

네오픽셀을 사용합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/cheesestick_ext/NeoPixel/1.png" alt="시작하기">

### 매개변수

(없음)

<!-- 
### JavaScript
```javascript
$('CheeseStick*0:NeoPixel+S_port.neo_led').d = 1;
$('CheeseStick*0:NeoPixel+S_port.Sa.mode').d = $('CheeseStick*0:NeoPixel+S_port.Sa.mode^analog_servo_output');
```
-->

### Python
```python
cheesestick = CheeseStick(0)
neopixel = cheesestick.NeoPixel()

neopixel.start()
```

---

## 색 모드 설정하기

네오픽셀의 LED 모드를 설정합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/cheesestick_ext/NeoPixel/2.png" alt="색 모드 설정하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 색 채널 모드 | GRBW, GRB | GRBW |

<!-- 
### JavaScript
```javascript
$('CheeseStick*0:NeoPixel+mode').d = $('CheeseStick*0:NeoPixel+mode^GRBW');
```
-->

### Python
```python
cheesestick = CheeseStick(0)
neopixel = cheesestick.NeoPixel()

neopixel.mode('GRBW')
```

---

## 한 픽셀 색 설정하기

지정한 번호의 픽셀 한 개에 색을 설정합니다.  
색상 팔레트에서 색을 선택하면 **색 이름**(영문 문자열)으로 변환되어 호출됩니다. (R, G, B 숫자 값이 아니라 색 이름으로 코드가 생성됩니다.)

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/cheesestick_ext/NeoPixel/3.png" alt="한 픽셀 색 설정하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| idx | 입력값 (필드) | 픽셀 번호 (1부터 시작) | 1 이상 정수 | - |
| color | 색상 | 색상 팔레트 선택 → 색 이름(영문)으로 변환 | 색 이름: `'black'`, `'red'`, `'yellow'`, `'green'`, `'cyan'`, `'blue'`, `'magenta'`, `'white'` | - |

<!-- 
### JavaScript
```javascript
// idx=1, color=#ff0000
$('CheeseStick*0:NeoPixel+command').d = $('CheeseStick*0:NeoPixel+command^fill');
$('CheeseStick*0:NeoPixel+from').d = 1;
$('CheeseStick*0:NeoPixel+to').d = 1;
$('CheeseStick*0:NeoPixel+red.value').d = 255;
$('CheeseStick*0:NeoPixel+green.value').d = 0;
$('CheeseStick*0:NeoPixel+blue.value').d = 0;
```
-->

### Python
```python
cheesestick = CheeseStick(0)
neopixel = cheesestick.NeoPixel()

neopixel.set_one_color(1, 'red')
```

---

## 색상 카테고리 블록으로 한 픽셀 색 설정하기

색상 카테고리 블록을 입력으로 받아 한 픽셀 색을 설정합니다.  
색상 블록의 출력(`Utils.color()` / `Utils.color_rgb()` / `Utils.color_slider()`, 모두 `[R, G, B]` 반환)을 `*`(별표)로 언팩하여 `set_one_color` 의 r, g, b 인자로 전달합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/cheesestick_ext/NeoPixel/4.png" alt="색상 카테고리 블록으로 한 픽셀 색 설정하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| idx | 입력값 (필드) | 픽셀 번호 (1부터 시작) | 1 이상 정수 | - |
| data | 입력값 (색상) | 색상 카테고리 블록 또는 `[R, G, B]` 배열 | [0~255, 0~255, 0~255] | - |

<!-- 
### JavaScript
```javascript
// 입력 [255, 0, 0], idx=1
$('CheeseStick*0:NeoPixel+command').d = $('CheeseStick*0:NeoPixel+command^fill');
$('CheeseStick*0:NeoPixel+from').d = 1;
$('CheeseStick*0:NeoPixel+to').d = 1;
$('CheeseStick*0:NeoPixel+red.value').d = 255;
$('CheeseStick*0:NeoPixel+green.value').d = 0;
$('CheeseStick*0:NeoPixel+blue.value').d = 0;
```
-->

### Python
```python
cheesestick = CheeseStick(0)
neopixel = cheesestick.NeoPixel()

neopixel.set_one_color(1, *Utils.color('red'))
```

---

## 한 픽셀 RGB 만큼 색 변경하기

지정한 한 픽셀의 현재 RGB 값에 변화량을 더해 새로운 색을 설정합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/cheesestick_ext/NeoPixel/5.png" alt="한 픽셀 RGB 만큼 색 변경하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| idx | 입력값 (필드) | 픽셀 번호 (1부터 시작) | 1 이상 정수 | - |
| r | 입력값 (필드) | 빨강 변화량 | -255 ~ 255 정수 | 0 |
| g | 입력값 (필드) | 초록 변화량 | -255 ~ 255 정수 | 0 |
| b | 입력값 (필드) | 파랑 변화량 | -255 ~ 255 정수 | 0 |

<!-- 
### JavaScript
```javascript
$('CheeseStick*0:NeoPixel+command').d = $('CheeseStick*0:NeoPixel+command^fill');
$('CheeseStick*0:NeoPixel+from').d = 1;
$('CheeseStick*0:NeoPixel+to').d = 1;
$('CheeseStick*0:NeoPixel+red.value').d = $('CheeseStick*0:NeoPixel+red.value').d + 10;
$('CheeseStick*0:NeoPixel+green.value').d = $('CheeseStick*0:NeoPixel+green.value').d + 0;
$('CheeseStick*0:NeoPixel+blue.value').d = $('CheeseStick*0:NeoPixel+blue.value').d + 0;
```
-->

### Python
```python
cheesestick = CheeseStick(0)
neopixel = cheesestick.NeoPixel()

neopixel.change_one_color(1, 10, 0, 0)
```

---

## 한 픽셀 끄기

n번째 LED 색을 없앱니다.  
LED 번호의 범위는 1 ~ 144입니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/cheesestick_ext/NeoPixel/6.png" alt="한 픽셀 끄기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| idx | 입력값 (필드) | 픽셀 번호 (1부터 시작) | 1 이상 정수 | - |

<!-- 
### JavaScript
```javascript
$('CheeseStick*0:NeoPixel+command').d = $('CheeseStick*0:NeoPixel+command^fill');
$('CheeseStick*0:NeoPixel+from').d = 1;
$('CheeseStick*0:NeoPixel+to').d = 1;
$('CheeseStick*0:NeoPixel+white.value').d = 0;
$('CheeseStick*0:NeoPixel+red.value').d = 0;
$('CheeseStick*0:NeoPixel+green.value').d = 0;
$('CheeseStick*0:NeoPixel+blue.value').d = 0;
```
-->

### Python
```python
cheesestick = CheeseStick(0)
neopixel = cheesestick.NeoPixel()

neopixel.turn_off_one(1)
```

---

## 범위 패턴 설정하기

지정한 범위에 해당하는 모든 LED의 색 패턴을 설정합니다.  
LED 번호의 범위는 1 ~ 144입니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/cheesestick_ext/NeoPixel/7.png" alt="범위 패턴 설정하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| from_idx | 입력값 (필드) | 시작 픽셀 번호 (1부터 시작) | 1 이상 정수 | - |
| to_idx | 입력값 (필드) | 끝 픽셀 번호 (1부터 시작) | 1 이상 정수 | - |
| pattern | 드롭다운 옵션 | 색 패턴 이름 | `3_colors`, `6_colors`, `12_colors`, `red_green`, `red_blue`, `red_white`, `green_red`, `green_blue`, `green_white`, `blue_red`, `blue_green`, `blue_white`, `white_red`, `white_green`, `white_blue`, `black_red`, `black_green`, `black_blue`, `black_white`, `red_black`, `green_black`, `blue_black`, `white_black` | - |

<!-- 
### JavaScript
```javascript
// from=1, to=10, pattern='3_colors'
$('CheeseStick*0:NeoPixel+command').d = $('CheeseStick*0:NeoPixel+command^pattern');
$('CheeseStick*0:NeoPixel+from').d = 1;          
$('CheeseStick*0:NeoPixel+to').d = 10;            
$('CheeseStick*0:NeoPixel+pattern.mode').d = $('CheeseStick*0:NeoPixel+pattern.mode^3_colors');
$('CheeseStick*0:NeoPixel+pattern.block').d = 10;  // to - from + 1
```
-->

### Python
```python
cheesestick = CheeseStick(0)
neopixel = cheesestick.NeoPixel()

neopixel.set_range_pattern(1, 10, '3_colors')
```

---

## 범위 색 설정하기

지정한 픽셀 범위 전체에 동일한 색을 설정합니다.  
색상 팔레트에서 색을 선택하면 **색 이름**(영문 문자열)으로 변환되어 호출됩니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/cheesestick_ext/NeoPixel/8.png" alt="범위 색 설정하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| from_idx | 입력값 (필드) | 시작 픽셀 번호 (1부터 시작) | 1 이상 정수 | - |
| to_idx | 입력값 (필드) | 끝 픽셀 번호 (1부터 시작) | 1 이상 정수 | - |
| color | 색상 | 색상 팔레트 선택 → 색 이름(영문)으로 변환 | 색 이름: `'black'`, `'red'`, `'yellow'`, `'green'`, `'cyan'`, `'blue'`, `'magenta'`, `'white'` | - |

<!-- 
### JavaScript
```javascript
$('CheeseStick*0:NeoPixel+command').d = $('CheeseStick*0:NeoPixel+command^fill');
$('CheeseStick*0:NeoPixel+from').d = 1;
$('CheeseStick*0:NeoPixel+to').d = 10;
$('CheeseStick*0:NeoPixel+red.value').d = 255;
$('CheeseStick*0:NeoPixel+green.value').d = 0;
$('CheeseStick*0:NeoPixel+blue.value').d = 0;
```
-->

### Python
```python
cheesestick = CheeseStick(0)
neopixel = cheesestick.NeoPixel()

neopixel.set_range_color(1, 10, 'red')
```

---

## 색상 카테고리 블록으로 범위 색 설정하기

색상 카테고리 블록을 입력으로 받아 픽셀 범위 색을 설정합니다.  
색상 블록의 출력(`Utils.color()` / `Utils.color_rgb()` / `Utils.color_slider()`)을 `*`(별표)로 언팩하여 `set_range_color` 의 r, g, b 인자로 전달합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/cheesestick_ext/NeoPixel/9.png" alt="색상 카테고리 블록으로 범위 색 설정하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| from_idx | 입력값 (필드) | 시작 픽셀 번호 (1부터 시작) | 1 이상 정수 | - |
| to_idx | 입력값 (필드) | 끝 픽셀 번호 (1부터 시작) | 1 이상 정수 | - |
| data | 입력값 (색상) | 색상 카테고리 블록 또는 `[R, G, B]` 배열 | `[0~255, 0~255, 0~255]` | - |

### Python
```python
cheesestick = CheeseStick(0)
neopixel = cheesestick.NeoPixel()

neopixel.set_range_color(1, 10, *Utils.color('red'))
```

---

## 범위 RGB 만큼 색 변경하기

지정한 픽셀 범위의 현재 색에 RGB 변화량을 더해 새로운 색을 설정합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/cheesestick_ext/NeoPixel/10.png" alt="범위 RGB 만큼 색 변경하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| from_idx | 입력값 (필드) | 시작 픽셀 번호 (1부터 시작) | 1 이상 정수 | - |
| to_idx | 입력값 (필드) | 끝 픽셀 번호 (1부터 시작) | 1 이상 정수 | - |
| r | 입력값 (필드) | 빨강 변화량 | -255 ~ 255 정수 | 0 |
| g | 입력값 (필드) | 초록 변화량 | -255 ~ 255 정수 | 0 |
| b | 입력값 (필드) | 파랑 변화량 | -255 ~ 255 정수 | 0 |

### Python
```python
cheesestick = CheeseStick(0)
neopixel = cheesestick.NeoPixel()

neopixel.change_range_color(1, 10, 10, 0, 0)
```

---

## 범위 색 끄기

지정한 범위에 해당하는 모든 LED의 색을 없앱니다.  
LED 번호의 범위는 1 ~ 144입니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/cheesestick_ext/NeoPixel/11.png" alt="범위 색 끄기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| from_idx | 입력값 (필드) | 시작 픽셀 번호 (1부터 시작) | 1 이상 정수 | - |
| to_idx | 입력값 (필드) | 끝 픽셀 번호 (1부터 시작) | 1 이상 정수 | - |

### Python
```python
cheesestick = CheeseStick(0)
neopixel = cheesestick.NeoPixel()

neopixel.turn_off_range(1, 10)
```

---

## n 칸마다 범위 색 설정하기

지정한 픽셀 범위 안에서 `increment` 칸마다 색을 설정합니다.  
색상 팔레트에서 색을 선택하면 **색 이름**(영문 문자열)으로 변환되어 호출됩니다.  
(예: 1, 3, 5, ... 칸만 켜기)

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/cheesestick_ext/NeoPixel/12.png" alt="n 칸마다 범위 색 설정하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| from_idx | 입력값 (필드) | 시작 픽셀 번호 (1부터 시작) | 1 이상 정수 | - |
| to_idx | 입력값 (필드) | 끝 픽셀 번호 (1부터 시작) | 1 이상 정수 | - |
| increment | 입력값 (필드) | 간격 (칸 수) | 1 이상 정수 | - |
| color | 색상 | 색상 팔레트 선택 → 색 이름(영문)으로 변환 | 색 이름: `'black'`, `'red'`, `'yellow'`, `'green'`, `'cyan'`, `'blue'`, `'magenta'`, `'white'` | - |

<!-- 
### JavaScript
```javascript
$('CheeseStick*0:NeoPixel+command').d = $('CheeseStick*0:NeoPixel+command^fill');
$('CheeseStick*0:NeoPixel+from').d = 0;
$('CheeseStick*0:NeoPixel+to').d = 9;
$('CheeseStick*0:NeoPixel+increment').d = 2;
$('CheeseStick*0:NeoPixel+red.value').d = 255;
$('CheeseStick*0:NeoPixel+green.value').d = 0;
$('CheeseStick*0:NeoPixel+blue.value').d = 0;
```
-->

### Python
```python
cheesestick = CheeseStick(0)
neopixel = cheesestick.NeoPixel()

neopixel.set_range_increment_color(1, 10, 2, 'red')
```

---

## 색상 카테고리 블록으로 n 칸마다 범위 색 설정하기

색상 카테고리 블록을 입력으로 받아 지정한 픽셀 범위 안에서 n 칸마다 색을 설정합니다.  
색상 블록의 출력(`Utils.color()` / `Utils.color_rgb()` / `Utils.color_slider()`)을 `*`(별표)로 언팩하여 `set_range_increment_color` 의 r, g, b 인자로 전달합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/cheesestick_ext/NeoPixel/13.png" alt="색상 카테고리 블록으로 n 칸마다 범위 색 설정하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| from_idx | 입력값 (필드) | 시작 픽셀 번호 (1부터 시작) | 1 이상 정수 | - |
| to_idx | 입력값 (필드) | 끝 픽셀 번호 (1부터 시작) | 1 이상 정수 | - |
| increment | 입력값 (필드) | 간격 (칸 수) | 1 이상 정수 | - |
| data | 입력값 (색상) | 색상 카테고리 블록 또는 `[R, G, B]` 배열 | `[0~255, 0~255, 0~255]` | - |

### Python
```python
cheesestick = CheeseStick(0)
neopixel = cheesestick.NeoPixel()

neopixel.set_range_increment_color(1, 10, 2, *Utils.color('red'))
```

---

## n 칸마다 범위 RGB 만큼 변경하기

n 칸마다 픽셀들의 현재 색에 RGB 변화량을 더해 새로운 색을 설정합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/cheesestick_ext/NeoPixel/14.png" alt="n 칸마다 범위 RGB 만큼 변경하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| from_idx | 입력값 (필드) | 시작 픽셀 번호 (1부터 시작) | 1 이상 정수 | - |
| to_idx | 입력값 (필드) | 끝 픽셀 번호 (1부터 시작) | 1 이상 정수 | - |
| increment | 입력값 (필드) | 증분 간격 (칸 수) | 1 이상 정수 | - |
| r | 입력값 (필드) | 빨강 변화량 | -255 ~ 255 정수 | 0 |
| g | 입력값 (필드) | 초록 변화량 | -255 ~ 255 정수 | 0 |
| b | 입력값 (필드) | 파랑 변화량 | -255 ~ 255 정수 | 0 |

### Python
```python
cheesestick = CheeseStick(0)
neopixel = cheesestick.NeoPixel()

neopixel.change_range_increment_color(1, 10, 2, 10, 0, 0)
```

---

## n 칸마다 범위 색 끄기

지정한 범위와 간격에 해당하는 모든 LED 색을 없앱니다.  
LED 번호의 범위는 1 ~ 144입니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/cheesestick_ext/NeoPixel/15.png" alt="n 칸마다 범위 색 끄기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| from_idx | 입력값 (필드) | 시작 픽셀 번호 (1부터 시작) | 1 이상 정수 | - |
| to_idx | 입력값 (필드) | 끝 픽셀 번호 (1부터 시작) | 1 이상 정수 | - |
| increment | 입력값 (필드) | 증분 간격 (칸 수) | 1 이상 정수 | - |

### Python
```python
cheesestick = CheeseStick(0)
neopixel = cheesestick.NeoPixel()

neopixel.turn_off_range_increment(1, 10, 2)
```

---

## 이동 / 회전

지정한 방향과 칸 만큼 LED를 이동하거나 회전합니다.  
선택할 수 있는 값의 범위는 1 ~ 143 입니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/cheesestick_ext/NeoPixel/16.png" alt="이동 / 회전">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 동작 종류 | 시프트(shift), 회전(rotate) | - |
| direction | 드롭다운 옵션 | 방향 | 왼쪽(left), 오른쪽(right) | - |
| pixel | 입력값 (필드) | 이동할 픽셀 수 | 1 이상 정수 | - |

<!-- 
### JavaScript
```javascript
// unit='shift', direction='left', pixel=1
$('CheeseStick*0:NeoPixel+command').d = $('CheeseStick*0:NeoPixel+command^shift');
$('CheeseStick*0:NeoPixel+shift.mode').d = $('CheeseStick*0:NeoPixel+shift.mode^shift');
$('CheeseStick*0:NeoPixel+shift.direction').d = $('CheeseStick*0:NeoPixel+shift.direction^left');
$('CheeseStick*0:NeoPixel+shift.pixel').d = 1;
```
-->

### Python
```python
cheesestick = CheeseStick(0)
neopixel = cheesestick.NeoPixel()

# unit = 'shift'
neopixel.shift('left', 1)

# unit = 'rotate'
neopixel.rotate('left', 1)
```

---

## 밝기 설정하기

네오픽셀의 밝기를 설정합니다.  
선택할 수 있는 값의 범위는 0 ~ 100 입니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/cheesestick_ext/NeoPixel/17.png" alt="밝기 설정하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| value | 입력값 (필드) | 밝기 | 0 ~ 100 정수 | - |

<!-- 
### JavaScript
```javascript
$('CheeseStick*0:NeoPixel+brightness').d = 50;
```
-->

### Python
```python
cheesestick = CheeseStick(0)
neopixel = cheesestick.NeoPixel()

neopixel.set_brightness(50)
```

---

## 밝기 변경하기

네오픽셀의 밝기를 변경합니다.  
선택할 수 있는 값의 범위는 -100 ~ 100 입니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/cheesestick_ext/NeoPixel/18.png" alt="밝기 변경하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| value | 입력값 (필드) | 밝기 변화량 | -100 ~ 100 정수 | - |

<!-- 
### JavaScript
```javascript
$('CheeseStick*0:NeoPixel+brightness').d = $('CheeseStick*0:NeoPixel+brightness').d + 10;
```
-->

### Python
```python
cheesestick = CheeseStick(0)
neopixel = cheesestick.NeoPixel()

neopixel.change_brightness(10)
```
