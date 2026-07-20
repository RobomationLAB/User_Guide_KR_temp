# 리스트

리스트는 "할 일 목록"이나 "쇼핑 목록"처럼 **항목들이 순서대로 나열된 집합**입니다.  
리스트의 항목들은 어떤 타입이라도 될 수 있으며, 동일한 값이 리스트에 여러 번 나타날 수 있습니다.

<br>

# 블록 <-> 파이썬 변환 규칙

## 리스트 만들기

**리스트 만들기** 블록을 사용하면 새로운 리스트에 초기값을 지정할 수 있습니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/lists/1.png" alt="Image">

<!-- 
## Javascript
```javascript
[item0, item1, item2]
```
-->

## Python
```python
[item0, item1, item2]
```

## 항목으로 리스트 설정

**항목으로 리스트 설정** 블록을 사용하면 지정된 항목을 반복하여 원하는 개수만큼 리스트를 만들 수 있습니다.
예를 들어, 아래의 블록은 변수 **words**를 ["very", "very", "very"]로 설정합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/lists/2.png" alt="Image">

<!-- 
## Javascript
```javascript
new Array(times).fill(item)
```
-->

## Python
```python
[item] * times
```

## 길이

**길이** 블록의 값은 리스트의 항목 수입니다.
예를 들어, 아래 블록에서 **color**는 3개의 항목을 가졌기 때문에 3을 반환합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/lists/3.png" alt="Image">

<!-- 
## Javascript
```javascript
list.length
```
-->

## Python
```python
len(list)
```

## 리스트 나타난 위치

이 블록들은 리스트에서 항목의 위치를 찾습니다.
리스트에 항목이 없는 경우, 결과는 0입니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/lists/4.png" alt="Image">

<!-- 
## Javascript
```javascript
list.indexOf(VALUE) + 1    // FIRST
list.lastIndexOf(VALUE) + 1  // LAST
```
-->

## Python
```python
list.index(VALUE) + 1
```

## 리스트에서 항목 가져오기

**color** 리스트에서 특정 위치의 항목을 가져올 수 있습니다.  
첫 번째, 마지막, 임의 항목, N번째 등 다양한 옵션이 있습니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/lists/5.png" alt="Image">

<!-- 
## Javascript
```javascript
list[0]              // first
list[list.length - 1]  // last
list[Math.floor(Math.random() * list.length)]  // random
list[N - 1]          // #N (1-based)
list[list.length - N]  // last_#N
```
-->

## Python
```python
list[0]
list[-1]
list[int(random.random() * len(list))]
list[N - 1]
list[-N]
```

## 빈 리스트 생성

가장 간단한 리스트는 빈 리스트로, **빈 리스트 생성** 블록을 사용하여 생성합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/lists/6.png" alt="Image">

<!-- 
## Javascript
```javascript
[]
```
-->

## Python
```python
[]
```

## 비어 있습니다

**비어 있습니다** 블록의 값은 입력이 빈 리스트일 경우 **참**, 그 외에는 **거짓**입니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/lists/7.png" alt="Image">

<!-- 
## Javascript
```javascript
!list.length
```
-->

## Python
```python
not len(list)
```

## 리스트에서 항목 가져오기 및 제거

**리스트에서 ... 가져오기 및 제거** 블록은 항목을 가져오는 것뿐만 아니라 원본 리스트에서 해당 항목을 제거합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/lists/8.png" alt="Image">

<!-- 
## Javascript
```javascript
list.splice(0, 1)[0]                   // first
list.pop()                             // last
// random
function listsGetRandomItem(list, remove) {
    var x = Math.floor(Math.random() * list.length);
    if (remove) { return list.splice(x, 1)[0]; }
    else { return list[x]; }
}
listsGetRandomItem(list, true)
list.splice(N - 1, 1)[0]               // #N (1-based)
list.splice(list.length - N, 1)[0]     // last_#N
```
-->

## Python
```python
list.pop(0)                            # first
list.pop()                             # last
# random
def lists_remove_random_item(myList):
    x = int(random.random() * len(myList))
    return myList.pop(x)
lists_remove_random_item(list)
list.pop(N - 1)                        # #N (1-based)
list.pop(-N)                           # last_#N
```

## 리스트에서 항목 제거

드롭다운에서 "삭제"를 선택하면 블록의 왼쪽 플러그가 사라지고, 지정한 위치의 항목이 리스트에서 제거되기만 합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/lists/9.png" alt="Image">

<!-- 
## Javascript
```javascript
list.splice(0, 1)                       // first
list.pop()                              // last
list.splice(Math.floor(Math.random() * list.length), 1)  // random
list.splice(N - 1, 1)                   // #N (1-based)
list.splice(list.length - N, 1)         // last_#N
```
-->

## Python
```python
list.pop(0)                             # first
list.pop()                              # last
list.pop(int(random.random() * len(list)))  # random
list.pop(N - 1)                         # #N (1-based)
list.pop(-N)                            # last_#N
```

## 리스트에서 항목 설정

**리스트에서 ... 설정** 블록은 지정된 위치의 항목을 다른 항목으로 교체합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/lists/10.png" alt="Image">

<!-- 
## Javascript
```javascript
list[0] = value                                          // first
list[list.length - 1] = value                            // last
list[N - 1] = value                                      // #N (1-based)
list[list.length - N] = value                            // last_#N
var tmpX = Math.floor(Math.random() * list.length);
list[tmpX] = value                                       // random
```
-->

## Python
```python
list[0] = value                                          # first
list[-1] = value                                         # last
list[N - 1] = value                                      # #N (1-based)
list[-N] = value                                         # last_#N
tmp_x = int(random.random() * len(list))
list[tmp_x] = value                                      # random
```

## 리스트에서 원하는 위치에 삽입

**리스트에서 ... 원하는 위치에 삽입** 블록은 새 항목을 지정한 위치에 삽입합니다.  
기존 항목은 유지되며 길이가 1 증가합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/lists/11.png" alt="Image">

<!-- 
## Javascript
```javascript
list.unshift(value)                              // first
list.push(value)                                 // last
list.splice(N - 1, 0, value)                     // #N (1-based)
list.splice(list.length - N, 0, value)           // last_#N
var tmpX = Math.floor(Math.random() * list.length);
list.splice(tmpX, 0, value)                      // random
```
-->

## Python
```python
list.insert(0, value)                            # first
list.append(value)                               # last
list.insert(N - 1, value)                        # #N (1-based)
list.insert(-N, value)                           # last_#N
tmp_x = int(random.random() * len(list))
list.insert(tmp_x, value)                        # random
```

## 서브리스트 추출

**리스트에서 ... 서브리스트 추출** 블록은 시작과 끝 위치를 지정하여 서브리스트를 추출합니다.  
원본 리스트는 변경되지 않습니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/lists/12.png" alt="Image">

<!-- 
## Javascript
```javascript
// 시작이 첫 번째 위치(#1)
list.slice(0, END)                     // #N → 끝 위치 N (1-based)
list.slice(0, list.length - N)         // last_#N
list.slice(0)                          // last (끝까지)

// 시작이 last_#N
list.slice(list.length - N, END)
list.slice(list.length - N, list.length - M)
list.slice(list.length - N)            // 끝까지

// 시작이 first
list.slice(0, END)
list.slice(0, list.length - N)
list.slice(0)
```
-->

## Python
```python
# 시작이 첫 번째 위치(#1)
list[ : N]                             # #N (1-based)
list[ : -N]                            # last_#N
list[ : ]                              # last

# 시작이 last_#N
list[-N : M]
list[-N : -M]
list[-N : ]

# 시작이 first
list[ : N]
list[ : -N]
list[ : ]
```

## 리스트 ... 항목을 ... (으)로 바꾼 리스트 추출

**리스트 ... 항목을 ... (으)로 바꾼 리스트 추출** 블록은 지정된 위치에 있는 항목을 다른 항목으로 치환한 뒤, 전체 리스트를 반환합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/lists/13.png" alt="Image">

<!-- 
## Javascript
```javascript
// unit = "#" (1-based index)
list.map((data, idx) => (idx === (N - 1) ? value : data))

// unit = "last_#"
list.map((data, idx) => (idx === (list.length - N) ? value : data))

// unit = "first"
list.map((data, idx) => (idx === 0 ? value : data))

// unit = "last"
list.map((data, idx) => (idx === (list.length - 1) ? value : data))
```
-->

## Python
```python
# unit = "#"
[value if i == (N - 1) else data for i, data in enumerate(list)]

# unit = "last_#"
[value if i == (len(list) - N) else data for i, data in enumerate(list)]

# unit = "first"
[value if i == 0 else data for i, data in enumerate(list)]

# unit = "last"
[value if i == (len(list) - 1) else data for i, data in enumerate(list)]
```

## 텍스트에서 목록 만들기

**텍스트에서 목록 만들기** 블록은 주어진 텍스트를 구분자를 기준으로 나누어 리스트로 반환합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/lists/14.png" alt="Image">

<!-- 
## Javascript
```javascript
text.split(delimiter)
```
-->

## Python
```python
text.split(delimiter)
```

## 목록에서 텍스트 만들기

**목록에서 텍스트 만들기** 블록은 구분자를 사용하여 리스트의 항목들을 하나의 텍스트로 결합합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/lists/15.png" alt="Image">

<!-- 
## Javascript
```javascript
list.join(delimiter)
```
-->

## Python
```python
delimiter.join(list)
```

## 정렬

리스트를 원하는 기준에 따라 **정렬하는 블록**입니다.
숫자 또는 알파벳을 기준으로 정렬할 수 있으며, 오름차순과 내림차순을 선택할 수 있습니다.
또한, 알파벳 정렬 시 대소문자를 무시하고 정렬할 수도 있습니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/lists/16.png" alt="Image">

<!-- 
## Javascript
```javascript
function listsGetSortCompare(type, direction) {
    var compareFuncs = {
        'NUMERIC':     function(a, b) { return Number(a) - Number(b); },
        'TEXT':        function(a, b) { return String(a) > String(b) ? 1 : -1; },
        'IGNORE_CASE': function(a, b) { return String(a).toLowerCase() > String(b).toLowerCase() ? 1 : -1; },
    };
    var compare = compareFuncs[type];
    return function(a, b) { return compare(a, b) * direction; };
}

list.slice().sort(listsGetSortCompare("NUMERIC", 1))      // 숫자, 오름차순
list.slice().sort(listsGetSortCompare("NUMERIC", -1))     // 숫자, 내림차순
list.slice().sort(listsGetSortCompare("TEXT", 1))         // 문자, 오름차순
list.slice().sort(listsGetSortCompare("TEXT", -1))        // 문자, 내림차순
list.slice().sort(listsGetSortCompare("IGNORE_CASE", 1))  // 대소문자 구분 X, 오름차순
list.slice().sort(listsGetSortCompare("IGNORE_CASE", -1)) // 대소문자 구분 X, 내림차순
```
-->

## Python
```python
def lists_sort(my_list, type, reverse):
    def try_float(s):
        try: return float(s)
        except: return 0
    key_funcs = {
        "NUMERIC": try_float,
        "TEXT": str,
        "IGNORE_CASE": lambda s: str(s).lower()
    }
    key_func = key_funcs[type]
    list_cpy = list(my_list)
    return sorted(list_cpy, key=key_func, reverse=reverse)

lists_sort(my_list, "NUMERIC", False)      # 숫자, 오름차순
lists_sort(my_list, "NUMERIC", True)       # 숫자, 내림차순
lists_sort(my_list, "TEXT", False)         # 문자, 오름차순
lists_sort(my_list, "TEXT", True)          # 문자, 내림차순
lists_sort(my_list, "IGNORE_CASE", False)  # 대소문자 구분 X, 오름차순
lists_sort(my_list, "IGNORE_CASE", True)   # 대소문자 구분 X, 내림차순
```

## 뒤집기

리스트의 요소 순서를 **역순으로 변경**하는 블록입니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/common/lists/17.png" alt="Image">

<!-- 
## Javascript
```javascript
list.slice().reverse()
```
-->

## Python
```python
list(reversed(my_list))
```
