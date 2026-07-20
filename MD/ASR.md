# 음성 인식

## 인스턴스 선언

음성 인식(ASR) 블록을 작업 영역에 추가하면, Python 코드에는 다음과 같은 인스턴스 선언이 자동으로 삽입됩니다:

```python
asr = ASR(0)
# 여러 인스턴스가 있는 경우
asr_1 = ASR(1)
```

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| index | 드롭다운 옵션 | 인스턴스 번호 (0부터 시작) | 0 이상 정수 | 0 |


<br>

# 블록 <-> 파이썬 변환 규칙

## 언어 설정하기

음성 인식 언어를 설정합니다. 언어를 설정하지 않아도 자동으로 설정됩니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/ASR/1.png" alt="언어 설정하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 인식 언어 코드 | 영어(en-US), 한국어(ko-KR) | - |

<!-- 
### JavaScript
```javascript
$('ASR*0:lang').d = 'ko-KR';
```
-->

### Python
```python
asr = ASR(0)

asr.lang('ko-KR')
```

---

## 음성 인식 시작 / 중지

음성 인식을 시작하거나 중지합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/ASR/2.png" alt="음성 인식 시작 / 중지">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 동작 | 시작(start), 중지(stop) | - |

<!-- 
### JavaScript
```javascript
$('ASR*0:listen').d = 1;   // start
$('ASR*0:listen').d = 0;   // stop
```
-->

### Python
```python
asr = ASR(0)

# unit = "start"
asr.start()
# unit = "stop"
asr.stop()
```

---

## 음성 인식 결과

음성 인식 결과

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/ASR/3.png" alt="음성 인식 결과">

### 매개변수

(없음)

<!-- 
### JavaScript
```javascript
$('ASR*0:result').d
```
-->

### Python
```python
asr = ASR(0)

asr.result()
```

---

## 음성 인식 활성 상태

음성 인식이 활성 상태인지 여부를 **참(True) / 거짓(False)** 으로 반환합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/ASR/4.png" alt="음성 인식 활성 상태">

### 매개변수

(없음)

<!-- 
### JavaScript
```javascript
$('ASR*0:state').d
```
-->

### Python
```python
asr = ASR(0)

asr.is_active()
```
