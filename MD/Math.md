# 연산

이 문서는 다양한 연산 블록의 기능과 사용법을 설명합니다.  
숫자 연산, 리스트 처리, 확률 및 각도 연산 등 다양한 수학적 연산을 수행하는 블록을 소개합니다.

<br>

# 블록 <-> 파이썬 변환 규칙

## 배열 생성 및 연산

**배열**을 생성하는 블록입니다.
`[]` 안에 입력한 값들을 요소로 가지는 배열을 반환합니다.
`[]` 안에 원하는 값을 입력하여 리스트를 만들 수 있으며, 문자열은 " "로 감싸야 합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/math/1.png" alt="Image">

<!-- 
## Javascript
```javascript
[1, 2, 3]
```
-->

## Python
```python
[1, 2, 3]
```

## 숫자 값

입력된 **숫자 값**을 그대로 반환하는 블록입니다.  
이 블록을 사용하면 특정 숫자를 변수에 저장하거나 다른 연산에 활용할 수 있습니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/math/2.png" alt="Image">

## Python
```
50
```

## 기본 산술 연산

두 개의 숫자 값을 사용하여 **산술 연산**(덧셈, 뺄셈, 곱셈, 나눗셈, 거듭제곱)을 수행하는 블록입니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/math/3.png" alt="Image">

<!-- 
## Javascript
```javascript
A + B
A - B
A * B
A / B
Math.pow(A, B)
```
-->

## Python
```python
A + B
A - B
A * B
A / B
A ** B
```

## 나머지

두 숫자의 나눗셈에서 **나머지**를 구하는 블록입니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/math/4.png" alt="Image">

<!-- 
## Javascript
```javascript
A % B
```
-->

## Python
```python
A % B
```

## 고급 연산 (단항 수학 함수)

제곱근, 절댓값, 부호 반전, 지수, 로그 함수 등 **단항 연산**를 수행하는 블록입니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/math/5.png" alt="Image">

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/math/6.png" alt="Image">

<!-- 
## Javascript
```javascript
Math.sqrt(NUM)
Math.abs(NUM)
-NUM
Math.log(NUM)
Math.log(NUM) / Math.log(10)
Math.exp(NUM)
Math.pow(10, NUM)
```
-->

## Python
```python
math.sqrt(NUM)
math.fabs(NUM)
-NUM
math.log(NUM)
math.log10(NUM)
math.exp(NUM)
10 ** NUM
```

## 삼각 함수

사인, 코사인, 탄젠트 등 **삼각 함수** 값을 계산하는 블록입니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/math/7.png" alt="Image">

<!-- 
## Javascript
```javascript
Math.sin(NUM / 180 * Math.PI)
Math.cos(NUM / 180 * Math.PI)
Math.tan(NUM / 180 * Math.PI)
Math.asin(NUM) / Math.PI * 180
Math.acos(NUM) / Math.PI * 180
Math.atan(NUM) / Math.PI * 180
```
-->

## Python
```python
math.sin(NUM / 180.0 * math.pi)
math.cos(NUM / 180.0 * math.pi)
math.tan(NUM / 180.0 * math.pi)
math.asin(NUM) / math.pi * 180
math.acos(NUM) / math.pi * 180
math.atan(NUM) / math.pi * 180
```

## 올림, 버림, 반올림

입력된 숫자를 **반올림(ROUND), 올림(ROUNDUP), 버림(ROUNDDOWN)** 처리하여 값을 반환합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/math/8.png" alt="Image">

<!-- 
## Javascript
```javascript
Math.round(NUM)   // ROUND
Math.ceil(NUM)    // ROUNDUP
Math.floor(NUM)   // ROUNDDOWN
```
-->

## Python
```python
round(NUM)        # ROUND
math.ceil(NUM)    # ROUNDUP
math.floor(NUM)   # ROUNDDOWN
```

## 특수 숫자 값

연산에 필요한 **수학 상수**(π, e, 황금비, √2, √(1/2), 무한대)를 반환합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/math/9.png" alt="Image">

<!-- 
## Javascript
```javascript
Math.PI                      // π
Math.E                       // e
(1 + Math.sqrt(5)) / 2       // 황금비
Math.SQRT2                   // √2
Math.SQRT1_2                 // √(1/2)
Infinity                     // 무한대
```
-->

## Python
```python
math.pi                      # π
math.e                       # e
(1 + math.sqrt(5)) / 2       # 황금비
math.sqrt(2)                 # √2
math.sqrt(1.0 / 2)           # √(1/2)
float('inf')                 # 무한대
```

## 숫자 조건

입력된 숫자가 짝수, 홀수, 소수, 정수, 양수, 음수, 또는 특정 수의 배수인지를 판별하여 **참/거짓**을 반환합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/math/10.png" alt="Image">

<!-- 
## Javascript
```javascript
function mathIsPrime(n) {
    if (n == 2 || n == 3) { return true; }
    if (isNaN(n) || n <= 1 || n % 1 !== 0 || n % 2 === 0 || n % 3 === 0) { return false; }
    for (var x = 6; x <= Math.sqrt(n) + 1; x += 6) {
        if (n % (x - 1) === 0 || n % (x + 1) === 0) { return false; }
    }
    return true;
}

NUM % 2 === 0          // EVEN (짝수)
NUM % 2 === 1          // ODD (홀수)
mathIsPrime(NUM)       // PRIME (소수)
NUM % 1 === 0          // WHOLE (정수)
NUM > 0                // POSITIVE (양수)
NUM < 0                // NEGATIVE (음수)
NUM % DIVISOR === 0    // DIVISIBLE_BY (배수)
```
-->

## Python
```python
def math_isPrime(n):
    if not isinstance(n, Number):
        try: n = float(n)
        except: return False
    if n == 2 or n == 3: return True
    if n <= 1 or n % 1 != 0 or n % 2 == 0 or n % 3 == 0: return False
    for x in range(6, int(math.sqrt(n)) + 2, 6):
        if n % (x - 1) == 0 or n % (x + 1) == 0: return False
    return True

NUM % 2 == 0           # EVEN (짝수)
NUM % 2 == 1           # ODD (홀수)
math_isPrime(NUM)      # PRIME (소수)
NUM % 1 == 0           # WHOLE (정수)
NUM > 0                # POSITIVE (양수)
NUM < 0                # NEGATIVE (음수)
NUM % DIVISOR == 0     # DIVISIBLE_BY (배수)
```

## 리스트 연산

리스트를 대상으로 합계, 최솟값, 최댓값, 평균값, 중간값, 최빈값, 표준 편차, 임의 항목 추출 연산을 수행합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/math/11.png" alt="Image">

<!-- 
## Javascript
```javascript
function mathMean(myList) {
    return myList.reduce(function(x, y) { return x + y; }, 0) / myList.length;
}

function mathMedian(myList) {
    var localList = myList.filter(function (x) { return typeof x === 'number'; });
    if (!localList.length) return null;
    localList.sort(function(a, b) { return b - a; });
    if (localList.length % 2 === 0) {
        return (localList[localList.length / 2 - 1] + localList[localList.length / 2]) / 2;
    } else {
        return localList[(localList.length - 1) / 2];
    }
}

function mathModes(values) {
    var modes = [];
    var counts = [];
    var maxCount = 0;
    for (var i = 0; i < values.length; i++) {
        var value = values[i];
        var found = false;
        var thisCount;
        for (var j = 0; j < counts.length; j++) {
            if (counts[j][0] === value) {
                thisCount = ++counts[j][1];
                found = true;
                break;
            }
        }
        if (!found) {
            counts.push([value, 1]);
            thisCount = 1;
        }
        maxCount = Math.max(thisCount, maxCount);
    }
    for (var j = 0; j < counts.length; j++) {
        if (counts[j][1] === maxCount) { modes.push(counts[j][0]); }
    }
    return modes;
}

function mathStandardDeviation(numbers) {
    var n = numbers.length;
    if (!n) return null;
    var mean = numbers.reduce(function(x, y) { return x + y; }) / n;
    var variance = 0;
    for (var j = 0; j < n; j++) { variance += Math.pow(numbers[j] - mean, 2); }
    variance /= n;
    return Math.sqrt(variance);
}

function mathRandomList(list) {
    var x = Math.floor(Math.random() * list.length);
    return list[x];
}

list.reduce(function(x, y) { return x + y; }, 0)  // SUM
Math.min.apply(null, list)                        // MIN
Math.max.apply(null, list)                        // MAX
mathMean(list)                                    // AVERAGE
mathMedian(list)                                  // MEDIAN
mathModes(list)                                   // MODE
mathStandardDeviation(list)                       // STD_DEV
mathRandomList(list)                              // RANDOM
```
-->

## Python
```python
def math_mean(myList):
    localList = [e for e in myList if isinstance(e, Number)]
    if not localList: return
    return float(sum(localList)) / len(localList)

def math_median(myList):
    localList = sorted([e for e in myList if isinstance(e, Number)])
    if not localList: return
    if len(localList) % 2 == 0:
        return (localList[len(localList) // 2 - 1] + localList[len(localList) // 2]) / 2.0
    else:
        return localList[(len(localList) - 1) // 2]

def math_modes(some_list):
    modes = []
    counts = []
    maxCount = 1
    for item in some_list:
        found = False
        for count in counts:
            if count[0] == item:
                count[1] += 1
                maxCount = max(maxCount, count[1])
                found = True
        if not found:
            counts.append([item, 1])
    for counted_item, item_count in counts:
        if item_count == maxCount:
            modes.append(counted_item)
    return modes

def math_standard_deviation(numbers):
    n = len(numbers)
    if n == 0: return
    mean = float(sum(numbers)) / n
    variance = sum((x - mean) ** 2 for x in numbers) / n
    return math.sqrt(variance)

sum(list)                          # SUM
min(list)                          # MIN
max(list)                          # MAX
math_mean(list)                    # AVERAGE
math_median(list)                  # MEDIAN
math_modes(list)                   # MODE
math_standard_deviation(list)      # STD_DEV
random.choice(list)                # RANDOM
```

## 값의 범위 설정

입력된 값이 지정한 **최솟값/최댓값** 범위를 벗어나지 않도록 제한합니다.
범위 밖의 값은 가까운 경계값으로 조정됩니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/math/12.png" alt="Image">

<!-- 
## Javascript
```javascript
Math.min(Math.max(VALUE, LOW), HIGH)
```
-->

## Python
```python
min(max(VALUE, LOW), HIGH)
```

## 랜덤 정수

지정한 범위 내에서 **랜덤한 정수**를 생성하는 블록입니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/math/13.png" alt="Image">

<!-- 
## Javascript
```javascript
Math.floor(Math.random() * (TO - FROM + 1) + FROM)
```
-->

## Python
```python
random.randint(FROM, TO)
```

## 임의 분수

0과 1 사이에서 **무작위의 분수 값**을 생성합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/math/14.png" alt="Image">

<!-- 
## Javascript
```javascript
Math.random()
```
-->

## Python
```python
random.random()
```

## 각도

주어진 (x, y) 좌표가 원점 (0,0)과 이루는 각도를 계산하는 블록입니다.  
좌표 위치를 기반으로 방향을 판별하는 데 사용할 수 있습니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/math/15.png" alt="Image">

<!-- 
## Javascript
```javascript
Math.atan2(Y, X) / Math.PI * 180
```
-->

## Python
```python
math.atan2(Y, X) / math.pi * 180
```
