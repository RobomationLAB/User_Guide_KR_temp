# 변수

우리는 변수라는 용어를 수학이나 다른 프로그래밍 언어에서 사용되는 것과 동일한 의미로 사용합니다.  
즉, **값을 저장하며 변경할 수 있는 이름을 가진 요소**를 의미합니다.  
  
  변수는 여러 가지 방법으로 생성할 수 있습니다.  

- [으로 계산](loops#으로-계산) 및 [각 항목에 대해](loops#각-항목에-대해)와 같은 일부 블록은 변수를 사용하며, 해당 변수의 값을 정의합니다.  
이러한 변수는 전통적인 컴퓨터 과학 용어로 **반복 변수(loop variables)** 라고 합니다.  
- **사용자 정의 함수** 는 입력값을 정의할 수 있으며, 이는 함수 내에서만 사용할 수 있는 변수(매개변수 또는 인자)를 생성합니다.  
- 사용자는 **설정** 블록을 통해 언제든지 변수를 생성할 수 있습니다. 이는 전통적으로 "**전역 변수(global variables)**" 라고 불립니다.  
- 블록 컴포저는 **지역 변수(local variables)** 를 지원하지 않습니다.  

변수 블록의 드롭다운을 클릭하면 다음과 같은 옵션이 나타납니다.  

- 프로그램에서 정의된 모든 기존 변수 이름이 표시됩니다.  
- **"변수 이름 바꾸기"**: 프로그램 전체에서 해당 변수의 이름을 변경합니다. 이 옵션을 선택하면 새 이름을 입력할 수 있는 창이 나타납니다.  
- **"변수 삭제"**: 프로그램에서 이 변수를 참조하는 모든 블록을 삭제합니다. 

<br>

# 블록 <-> 파이썬 변환 규칙

## 값 가져오기

아래 블록은 변수에 저장된 값을 제공하지만, 해당 값을 변경하지는 않습니다.  
설정 블록 없이 블록을 사용하는 것도 가능하지만, 이는 올바른 프로그래밍 방식이 아닙니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/variables/1.png" alt="Image">

## Python
```python
age
```

## 설정

**설정** 블록은 변수에 값을 할당합니다.  
코드 상에 해당 변수가 선언되어 있지 않은 경우, 새 변수를 선언한 뒤 값을 할당합니다.  
예를 들어, 아래 블록은 `age` 라는 변수를 만들고 값 `12`를 할당합니다.  

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/variables/2.png" alt="Image">

<!-- 
## Javascript
```javascript
myVar = value;
```
-->

## Python
```python
age = 12
```

## 바꾸기

**바꾸기** 블록은 변수의 값에 숫자를 더하는 역할을 합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/variables/3.png" alt="Image">

<!-- 
## Javascript
```javascript
myVar = (typeof myVar == 'number' ? myVar : 0) + delta;
```
-->

## Python
```python
age = age + 1
```
