# 반복

반복 제어문에는 두 가지 유형이 있습니다:  
**조건문**과 **반복문** (변수들의 값에 따라 본문을 몇 번 실행할 지 제어하는 것들)

<br>

# 블록 <-> 파이썬 변환 규칙

## 동안 반복하기 / 까지 반복하기

**동안 반복하기** 블록은 조건이 참인 동안 본문을 반복합니다.
**까지 반복하기** 블록은 조건이 거짓인 동안 본문을 반복하고, 조건이 참이 되는 순간 반복문을 탈출합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/loops/1.png" alt="Image">

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/loops/2.png" alt="Image">

<!-- 
## Javascript
```javascript
// unit = "while"
while (condition) {
  // ...
}

// unit = "until"
while (!condition) {
  // ...
}
```
-->

## Python
```python
# unit = "while"
while condition:
    # ...

# unit = "until"
while not condition:
    # ...
```

## 반복 중단 / 다음 반복

**반복 중단** 블록은 **반복문에서 일찍 빠져나올 수** 있게 해줍니다.
**다음 반복**(대부분의 프로그래밍 언어에서 **continue**)은 본문의 남은 코드를 건너뛰고 다음 반복(패스)을 시작하게 만듭니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/loops/3.png" alt="Image">

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/loops/4.png" alt="Image">

<!-- 
## Javascript
```javascript
break;
continue;
```
-->

## Python
```python
break
continue
```

## 반복

가장 간단한 **반복** 블록은 본문의 코드를 지정된 횟수만큼 실행합니다.
예를 들어, 아래의 블록은 "`Hello!`"를 열 번 출력합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/loops/5.png" alt="Image">

<!-- 
## Javascript
```javascript
for (var count = 0; count < times; count++) {
  // ...
}
```
-->

## Python
```python
for count in range(times):
    # ...
```

## 으로 계산

**으로 계산** 블록(대부분 **for loop**라고 부름)은 변수를 첫 번째 값에서 세 번째 값까지 증가량(두 번째 값)만큼 증가시키면서 본문을 각 값에 대해 한 번씩 실행합니다.
예를 들어, 아래 프로그램은 1, 3, 5를 출력합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/loops/6.png" alt="Image">

<!-- 
## Javascript
```javascript
for (var VAR = from; VAR <= to; VAR += by) {
  // ...
}
```
-->

## Python
```python
for VAR in range(from, to + 1, by):
    # ...
```

## 각 항목에 대해

**각 항목에 대해** 블록은 숫자 순서 대신 목록의 값을 차례대로 사용하는 점에서 유사합니다.
아래 프로그램은 "`첫 번째`", "`두 번째`", "`세 번째`" 목록의 각 항목을 출력합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/loops/7.png" alt="Image">

<!-- 
## Javascript
```javascript
for (var VAR in list) {
  // ...
}
```
-->

## Python
```python
for VAR in list:
    # ...
```
