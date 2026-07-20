# 나이, 성별, 표정

## 인스턴스 선언

나이, 성별, 표정(FaceExpression) 블록을 작업 영역에 추가하면, Python 코드에는 다음과 같은 인스턴스 선언이 자동으로 삽입됩니다:

```python
face_expression = FaceExpression(0)
# 여러 인스턴스가 있는 경우
face_expression_1 = FaceExpression(1)
```

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| index | 드롭다운 옵션 | 인스턴스 번호 (0부터 시작) | 0 이상 정수 | 0 |


<br>

# 블록 <-> 파이썬 변환 규칙

## 카메라 장치 선택하기

나이, 성별, 표정 인식을 위한 카메라를 설정합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/FaceExpression/1.png" alt="카메라 장치 선택하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 카메라 장치 이름 | 시스템 카메라 라벨 | - |

<!-- 
### JavaScript
```javascript
$('FaceExpression*0:camera.device_id').d = __cameraId('FaceTime HD Camera');
```
-->

### Python
```python
face_expression = FaceExpression(0)

face_expression.device('')
```

---

## 모델 로드하기

학습된 나이, 성별, 표정 모델을 불러옵니다. '나이, 성별, 표정' 모듈의 기능들을 사용하기 위해서는 이 작업이 반드시 필요합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/FaceExpression/2.png" alt="모델 로드하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| wait | 체크박스 | 로드 완료 대기 여부 | TRUE / FALSE | TRUE |

<!-- 
### JavaScript
```javascript
$('FaceExpression*0:load_model').d = 1;
await $('FaceExpression*0:!load_model').w();   // wait = TRUE
```
-->

### Python
```python
face_expression = FaceExpression(0)

face_expression.load_model(wait=True)
```

---

## 한 번 인식하기

현재 화면에 있는 얼굴을 분석하여 예측한 나이, 성별, 표정을 딱 한번 표시합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/FaceExpression/3.png" alt="한 번 인식하기">

### 매개변수

(없음)

<!-- 
### JavaScript
```javascript
$('FaceExpression*0:detect.once').d = 1;
```
-->

### Python
```python
face_expression = FaceExpression(0)

face_expression.detect_once()
```

---

## 연속 인식 시작 / 중지

현재 화면에 있는 얼굴을 계속해서 분석하여 예측한 나이, 성별, 표정을 화면 상에 표시합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/FaceExpression/4.png" alt="연속 인식 시작 / 중지">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 동작 | 시작(start), 중지(stop) | - |

<!-- 
### JavaScript
```javascript
$('FaceExpression*0:detect.continuous').d = 1;
```
-->

### Python
```python
face_expression = FaceExpression(0)

# unit = "start"
face_expression.detect_continuous()
# unit = "stop"
face_expression.stop()
```

---

## 인식 화면 표시하기

카메라 화면에 나이, 성별, 표정 인식 결과를 표시할지 말지를 결정합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/FaceExpression/5.png" alt="인식 화면 표시하기">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| on | 드롭다운 옵션 | 표시 ON / OFF | 표시(on=True), 숨기기(off=False) | TRUE |

<!-- 
### JavaScript
```javascript
$('FaceExpression*0:display').d = 1;
```
-->

### Python
```python
face_expression = FaceExpression(0)

face_expression.display(True)
face_expression.display(False)
```

---

## 나이

나이

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/FaceExpression/6.png" alt="나이">

### 매개변수

(없음)

<!-- 
### JavaScript
```javascript
$('FaceExpression*0:age').d
```
-->

### Python
```python
face_expression = FaceExpression(0)

face_expression.age()
```

---

## 성별

성별

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/FaceExpression/7.png" alt="성별">

### 매개변수

(없음)

<!-- 
### JavaScript
```javascript
$('FaceExpression*0:gender.class').d
```
-->

### Python
```python
face_expression = FaceExpression(0)

face_expression.gender()
```

---

## 표정

표정

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/FaceExpression/8.png" alt="표정">

### 매개변수

(없음)

<!-- 
### JavaScript
```javascript
$('FaceExpression*0:expression.class').d
```
-->

### Python
```python
face_expression = FaceExpression(0)

face_expression.expression()
```

---

## 성별 감지 여부

성별 인식 여부

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/FaceExpression/9.png" alt="성별 감지 여부">

### 매개변수

(없음)

<!-- 
### JavaScript
```javascript
$('FaceExpression*0:gender.detected').d
```
-->

### Python
```python
face_expression = FaceExpression(0)

face_expression.gender_detected()
```

---

## 특정 성별인가?

인식된 성별이 지정한 값과 일치하는지 여부를 **참(True) / 거짓(False)** 으로 반환합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/FaceExpression/10.png" alt="특정 성별인가?">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 성별 | 남성(male), 여성(female) | - |

<!-- 
### JavaScript
```javascript
$('FaceExpression*0:gender.class').d === 'male'
```
-->

### Python
```python
face_expression = FaceExpression(0)

face_expression.is_gender('male')
face_expression.is_gender('female')
```

---

## 성별 신뢰도

선택한 성별일 확률(신뢰도)

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/FaceExpression/11.png" alt="성별 신뢰도">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 성별 | 남성(male), 여성(female) | - |

<!-- 
### JavaScript
```javascript
$('FaceExpression*0:gender.confidence').d[$('FaceExpression*0:gender.labels.^male')]
```
-->

### Python
```python
face_expression = FaceExpression(0)

face_expression.gender_confidence('male')
face_expression.gender_confidence('female')
```

---

## 표정 감지 여부

표정 인식 여부

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/FaceExpression/12.png" alt="표정 감지 여부">

### 매개변수

(없음)

<!-- 
### JavaScript
```javascript
$('FaceExpression*0:expression.detected').d
```
-->

### Python
```python
face_expression = FaceExpression(0)

face_expression.expression_detected()
```

---

## 특정 표정인가?

인식된 표정이 지정한 값과 일치하는지 여부를 **참(True) / 거짓(False)** 으로 반환합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/FaceExpression/13.png" alt="특정 표정인가?">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 표정 | 화남(angry), 역겨움(disgusted), 두려움(fearful), 행복(happy), 무표정(neutral), 슬픔(sad), 놀람(surprised) | - |

<!-- 
### JavaScript
```javascript
$('FaceExpression*0:expression.class').d === 'happy'
```
-->

### Python
```python
face_expression = FaceExpression(0)

face_expression.is_expression('happy')
face_expression.is_expression('sad')
```

---

## 표정 신뢰도

선택한 표정일 확률(신뢰도)

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/FaceExpression/14.png" alt="표정 신뢰도">

### 매개변수

| 이름 | 구분 | 설명 | 범위 / 종류 | 기본값 |
| --- | --- | --- | --- | --- |
| unit | 드롭다운 옵션 | 표정 | angry, disgusted, fearful, happy, neutral, sad, surprised | - |

<!-- 
### JavaScript
```javascript
$('FaceExpression*0:expression.confidence').d[$('FaceExpression*0:expression.labels.^happy')]
```
-->

### Python
```python
face_expression = FaceExpression(0)

face_expression.expression_confidence('happy')
face_expression.expression_confidence('angry')
```

---

## 모델 상태

나이, 성별, 표정 모델 로딩 상태를 반환합니다.  
아직 불러오지 않았으면 0, 불러오는 중이면 1, 불러오기를 완료했으면 2를 반환합니다.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_KR/main/assets/ai/FaceExpression/15.png" alt="모델 상태">

### 매개변수

(없음)

<!-- 
### JavaScript
```javascript
$('FaceExpression*0:model_state').d
```
-->

### Python
```python
face_expression = FaceExpression(0)

face_expression.model_state()
```
