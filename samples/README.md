# GitHub Copilot 워크숍 샘플 파일

이 폴더에는 워크숍 실습에 사용할 샘플 데이터 파일들이 포함되어 있습니다.

## 📁 파일 목록

### 1. customer_satisfaction.csv
- **용도**: Session 4 (CSV 데이터 시각화) 실습
- **내용**: 고객 만족도 설문조사 응답 데이터 (25건)
- **컬럼**: 응답ID, 연령대, 직업, 서비스_만족도, 가격_만족도, 앱_사용성, 고객센터_만족도, 재이용_의향, 추천_의향, 주요_불만사항

### 2. customer_list.csv
- **용도**: Session 5 (업무 자동화) 실습
- **내용**: 고객 정보 및 결제 상태 데이터 (10건)
- **컬럼**: 고객ID, 이름, 이메일, 전화번호, 상태, 등록일, 금액

### 3. meeting_notes.txt
- **용도**: Session 5 (이메일 추출) 실습
- **내용**: 회의 참석자 정보 및 이메일 주소가 포함된 텍스트

## 🚀 사용 방법

각 세션의 실습 가이드를 따라 해당 파일을 사용하세요.

### Session 4 예시
```python
import pandas as pd
df = pd.read_csv('samples/customer_satisfaction.csv')
```

### Session 5 예시
```python
# 결제 완료 고객 필터링
df = pd.read_csv('samples/customer_list.csv')
completed = df[df['상태'] == '결제 완료']
```

## 📝 참고사항

- 모든 데이터는 실습용 샘플입니다
- 실제 개인정보가 아닌 가상의 데이터입니다
- 자유롭게 수정하여 사용할 수 있습니다

## 🎯 추가 샘플 생성

필요하다면 Copilot에게 요청하여 더 많은 샘플 데이터를 생성할 수 있습니다:

```
위와 유사한 형식의 CSV 데이터를 100개 생성해줘.
```
