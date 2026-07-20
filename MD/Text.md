# 문자열

문자열의 예시는 다음과 같습니다:
- "thing #1"
- "March 12, 2010"
- "" (빈 문자열)

문자열에는 대문자 또는 소문자로 된 문자, 숫자, 구두점, 기타 기호 및 단어 사이의 공백이 포함될 수 있습니다.  

<br>

# 블록 <-> 파이썬 변환 규칙

## 문자열 만들기

문자열은 대문자 또는 소문자로 된 문자, 숫자, 구두점, 기타 기호 및 단어 사이의 공백이 포함될 수 있습니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/text/1.png" alt="Image">

<!-- 
## Javascript / Python
```
'hello'
```
-->

## 문자열 연결

**문자열 만들기** 블록은 여러 문자열의 값을 결합(연결)하여 새로운 문자열을 생성합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/text/2.png" alt="Image">

<!-- 
## Javascript
```javascript
'' + A + B + C
```
-->

## Python
```python
'' + str(A) + str(B) + str(C)
```

## 문자열 수정 (...내용 덧붙이기)

**...내용 덧붙이기** 블록은 지정된 변수에 주어진 문자열를 추가합니다.
아래 `greeting` 변수의 값이 "`hello`"에서 "`hello, there!`"로 변경됩니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/text/3.png" alt="Image">

<!-- 
## Javascript
```javascript
VAR = String(VAR) + TEXT;
```
-->

## Python
```python
VAR = str(VAR) + TEXT
```

## 문자열 길이

**길이** 블록은 각 문자열에서 문자, 숫자 등을 세어 총 길이를 반환합니다.
아래 "`We're #1!`"의 길이는 9이며, 빈 문자열의 길이는 0입니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/text/4.png" alt="Image">

<!-- 
## Javascript
```javascript
String(VALUE).length
```
-->

## Python
```python
len(VALUE)
```

## 빈 문자열 확인

**비어 있습니다** 블록은 주어진 문자열가 비었는지(길이가 0인지) 확인합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/text/5.png" alt="Image">

<!-- 
## Javascript
```javascript
String(VALUE).length === 0
```
-->

## Python
```python
len(VALUE) == 0
```

## 문자열 찾기

이 블록들은 특정 문자열이 다른 문자열 안에 있는지 확인하고, 존재하는 경우 위치를 반환합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/text/6.png" alt="Image">

<!-- 
## Javascript
```javascript
VALUE.indexOf(FIND) + 1    // FIRST
VALUE.lastIndexOf(FIND) + 1  // LAST
```
-->

## Python
```python
(VALUE.find(FIND) + 1)
(VALUE.rfind(FIND) + 1)
```

## 단일 문자 추출

문자열에서 특정 위치의 한 문자를 가져옵니다.  
첫 번째, 마지막, 임의 위치, N번째 등 다양한 옵션이 있습니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/text/7.png" alt="Image">

<!-- 
## Javascript
```javascript
TEXT[N - 1]              // #N
TEXT[TEXT.length - N]    // last_#N
TEXT[0]                  // first
TEXT[TEXT.length - 1]    // last
TEXT[Math.floor(Math.random() * TEXT.length)]  // random
```
-->

## Python
```python
TEXT[N - 1]
TEXT[len(TEXT) - N]
TEXT[0]
TEXT[-1]
TEXT[int(random.random() * len(TEXT))]
```

## 문자열 일부 추출

**문자열에서...부분 문자열 가져오기** 블록을 사용하면 특정 범위의 문자열를 추출할 수 있습니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/text/8.png" alt="Image">

<!-- 
## Javascript
```javascript
TEXT.slice(at1, at2 + 1)
```
-->

## Python
```python
TEXT[at1:at2]
```

## 문자열 대소문자 변경

이 블록은 입력 문자열를 다음 형식 중 하나로 변환합니다:

- **대문자** (모든 문자 대문자로 변환)
- **소문자**
- **첫 글자만 대문자** (각 단어의 첫 글자만 대문자로 변환)

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/text/9.png" alt="Image">

<!-- 
## Javascript
```javascript
TEXT.toUpperCase()   // UPPERCASE
TEXT.toLowerCase()   // LOWERCASE
TEXT[0].toUpperCase() + TEXT.slice(1).toLowerCase()  // TITLECASE
```
-->

## Python
```python
TEXT.upper()
TEXT.lower()
TEXT.title()
```

## 공백 제거

다음 블록은 문자열에서 다음 위치의 공백을 제거합니다:
- 문자열의 앞쪽
- 문자열의 끝쪽
- 양쪽 모두

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/text/10.png" alt="Image">

<!-- 
## Javascript
```javascript
TEXT.trim()       // BOTH
TEXT.trimLeft()   // LEFT
TEXT.trimRight()  // RIGHT
```
-->

## Python
```python
TEXT.strip()
TEXT.lstrip()
TEXT.rstrip()
```

## 문자열에서 특정 문자열 숫자 세기

주어진 문자열에서 특정한 단어(부분 문자열)가 등장하는 횟수를 세어 반환합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/text/11.png" alt="Image">

<!-- 
## Javascript
```javascript
function textCount(haystack, needle) {
    if (needle.length === 0) {
        return haystack.length + 1;
    } else {
        return haystack.split(needle).length - 1;
    }
}

textCount(HAYSTACK, NEEDLE)
```
-->

## Python
```python
HAYSTACK.count(NEEDLE)
```

## 문자열에서 특정 문자 변경

문자열 내에서 특정 문자(부분 문자열)를 다른 문자로 일괄 변경합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/text/12.png" alt="Image">

<!-- 
## Javascript
```javascript
function textReplace(haystack, needle, replacement) {
    needle = needle.replace(/([-()\[\]{}+?*.$\^|,:#<!\\])/g, '\\$1').replace(/\x08/g, '\\x08');
    return haystack.replace(new RegExp(needle, 'g'), replacement);
}

textReplace(HAYSTACK, NEEDLE, REPLACEMENT)
```
-->

## Python
```python
HAYSTACK.replace(NEEDLE, REPLACEMENT)
```

## 문자열 뒤집기

문자열의 순서를 거꾸로 바꾼 새로운 문자열을 반환합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/text/13.png" alt="Image">

<!-- 
## Javascript
```javascript
TEXT.split('').reverse().join('')
```
-->

## Python
```python
TEXT[::-1]
```

## 문자열 출력

**출력** 블록은 입력 값을 팝업 창에 표시합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/text/14.png" alt="Image">

<!-- 
## Javascript
```javascript
window.alert(TEXT);
```
-->

## Python
```python
print(TEXT)
```

## 사용자 입력 받기

다음 블록은 사용자에게 입력을 요청하는 팝업 창을 생성하며, 입력된 값은 변수에 저장됩니다.  
텍스트 또는 숫자를 입력받을 수 있습니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/text/15.png" alt="Image">

<!-- 
## Javascript
```javascript
window.prompt(TEXT)     // TEXT type
parseFloat(window.prompt(TEXT))  // NUMBER type
```
-->

## Python
```python
input(TEXT)
float(input(TEXT))
```
