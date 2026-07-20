# 색상

색상은 다양한 그래픽 프로그램에서 사용됩니다. 

<br>

# 블록 <-> 파이썬 변환 규칙

## 팔레트에서 색상 선택

가장 간단한 색상을 얻는 방법은 **색상 선택기**를 사용하는 것입니다.  
이 블록은 흰색의 둥근 사각형으로 표시됩니다.  
클릭하면 색상 팔레트가 나타나며, 원하는 색상을 선택할 수 있습니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/color/1.png" alt="Image">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| color | 색상 | 색상 프리셋 | 검정색(black), 빨간색(red), 노란색(yellow), 초록색(green), 청록색(cyan), 파란색(blue), 자홍색(magenta), 흰색(white) | - |

<!-- 
### JavaScript
```javascript
// 예: 주황색 선택 시
[255, 128, 0]
```
-->

### Python
```python
# 예: 빨간색 프리셋 선택 시
Utils.color('red')
```

---

## 슬라이더를 사용한 색상 생성

**슬라이더**를 이용해 색상을 직접 조합할 수 있습니다.  
원형 슬라이더는 빨강(R), 초록(G), 파랑(B) 값 조정을 담당하며, 막대 슬라이더로 **명도**(밝기)를 조절할 수 있습니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/color/2.png" alt="Image">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| color | 색상 | 색상 휠 + 명도 슬라이더 | r: 0~255, g: 0~255, b: 0~255 | - |

<!-- 
### JavaScript
```javascript
// 컬러 휠에서 선택한 색상 → [R, G, B]
[255, 128, 0]
```
-->

### Python
```python
# 컬러 휠에서 선택한 색상 → [R, G, B]
Utils.color_slider(255, 128, 0)
```

---

## RGB 값으로 색상 만들기

**색상 설정** 블록은 빨강, 초록, 파랑 값을 각각 지정하여 RGB 배열을 만듭니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/color/3.png" alt="Image">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| r | 입력값 (블록) | 빨강 값 | 0 ~ 255 정수 | - |
| g | 입력값 (블록) | 초록 값 | 0 ~ 255 정수 | - |
| b | 입력값 (블록) | 파랑 값 | 0 ~ 255 정수 | - |

<!-- 
### JavaScript
```javascript
[red, green, blue]
```
-->

### Python
```python
Utils.color_rgb(red, green, blue)
```

---

## 랜덤 색상 생성

호출될 때마다 무작위 RGB 색상을 생성합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/color/4.png" alt="Image">

### 매개변수

(없음)

<!-- 
### JavaScript
```javascript
__randomColor()
```
-->

### Python
```python
Utils.random_color()
```
