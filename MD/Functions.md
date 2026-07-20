# 함수

**함수(Function)** 는 특정 작업을 수행하는 **블록(명령어)들의 모음**입니다.  
반복적으로 사용되는 동작을 하나의 함수로 정의하면, 코드를 **간결하고 효율적**으로 관리할 수 있습니다.

함수는 다음과 같은 특징을 가집니다.  
- **재사용 가능**: 한 번 정의하면 여러 번 호출하여 사용할 수 있습니다.  
- **입력과 출력**: 매개변수(입력 값)를 받아 처리한 후 결과(출력 값)를 반환할 수 있습니다.  
- **코드의 가독성 향상**: 프로그램의 흐름을 논리적으로 구성할 수 있습니다.

<br>

# 블록 <-> 파이썬 변환 규칙

## setup

프로그램 시작 시 한 번 실행되는 setup 함수의 컨테이너 블록입니다.  
초기화 코드를 작성합니다.

<!-- 
## Javascript
```javascript
// put setup code here, to run once:
async function setup() {
  // ...body...
}
```
-->

## Python
```python
# put setup code here, to run once:
async def setup():
    # ...body...
    return
```

## loop

프로그램이 실행되는 동안 반복 호출되는 loop 함수의 컨테이너 블록입니다.  
반복 실행할 코드를 작성합니다.

<!-- 
## Javascript
```javascript
// put control code here, to run repeatedly:
async function loop() {
  // ...body...
}
```
-->

## Python
```python
# put control code here, to run repeatedly:
async def loop():
    # ...body...
    return
```

## 함수 정의 (반환값 없음)

함수를 정의하는 블록을 사용하면 **새로운 함수**를 만들 수 있습니다.
반환값이 없는 함수는 특정 동작을 수행하지만 **값을 반환하지 않는 함수**입니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/functions/1.png" alt="Image">

<!-- 
## Javascript
```javascript
function myFunction(arg1, arg2) {
  // ...body...
}
```
-->

## Python
```python
def myFunction(arg1, arg2):
    # ...body...
```

## 함수 정의 (반환값 있음)

반환값이 있는 함수는 특정 작업을 수행한 후, 결과 **값을 반환**하여 다른 블록에서 활용할 수 있습니다.
아래 함수는 두 숫자의 합을 반환하는 함수입니다.  
**매개변수 x, y를 입력받아 x + y의 결과를 반환**합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/functions/2.png" alt="Image">

<!-- 
## Javascript
```javascript
function myFunction(arg1) {
  // ...body...
  return returnValue;
}
```
-->

## Python
```python
def myFunction(arg1):
    # ...body...
    return returnValue
```

## 함수 호출

함수를 정의하면, **사용자 정의 함수 블록**이 자동으로 생성됩니다.
이를 통해 **미리 정의한 함수**를 호출하여 실행할 수 있습니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/functions/3.png" alt="Image">

<!-- 
## Javascript
```javascript
myFunction(arg1, arg2);   // callnoreturn
myFunction(arg1, arg2)    // callreturn (value)
```
-->

## Python
```python
myFunction(arg1, arg2)
```

## 만약 다음을 돌려줌

함수 내에서 **특정 조건을 만족하면 즉시 값을 반환**하고 함수를 종료하는 기능을 수행하는 블록입니다.
이 블록은 **함수 내부에서만 사용**할 수 있으며, 다른 곳에서는 비활성화됩니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/functions/4.png" alt="Image">

<!-- 
## Javascript
```javascript
if (condition) { return value; }
```
-->

## Python
```python
if condition:
    return value
```
