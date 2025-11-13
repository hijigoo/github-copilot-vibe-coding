# Sessions 데이터 파일 가이드

이 폴더에는 각 세션에서 사용할 실습용 샘플 데이터 파일들이 포함되어 있습니다.

## 📁 파일 목록 및 용도

### Session 1: 회의록 자동 정리
- **`sample_meeting_notes.txt`**
  - 실제 회의록 형식의 샘플 텍스트
  - Action Item 추출 실습에 사용

### Session 3: UX 리서치 분석
- **`user_feedback_data.txt`**
  - 15명의 사용자 인터뷰 결과
  - 피드백 자동 분류 및 인사이트 도출 실습에 사용

### Session 4: CSV to HTML Report
- **`customer_satisfaction_survey.csv`**
  - 고객 만족도 설문조사 데이터 (50건)
  - 컬럼: 응답ID, 연령대, 직업, 각종 만족도 지표, 불만사항
  - 데이터 시각화 및 HTML 리포트 생성 실습

### Session 5: 업무 자동화
- **`customer_list_full.csv`**
  - 고객 정보 및 예약 상태 데이터 (20건)
  - 컬럼: 고객ID, 이름, 이메일, 전화번호, 상태, 등록일, 금액, 지역
  - Excel 필터링 자동화 실습
  
- **`email_extraction_sample.txt`**
  - 이메일 주소가 포함된 텍스트 파일
  - 정규표현식을 이용한 이메일 자동 추출 실습

## 🚀 사용 방법

### 파일 경로 지정
실습 시 다음 경로를 사용하세요:

```python
# 상대 경로 (sessions 폴더 기준)
df = pd.read_csv('data/customer_satisfaction_survey.csv')

# 절대 경로 (프로젝트 루트 기준)
df = pd.read_csv('sessions/data/customer_satisfaction_survey.csv')
```

### 파일 복사
참가자들에게 이 폴더 전체를 공유하거나, 개별 파일을 다운로드할 수 있도록 안내하세요.

## 📊 데이터 특징

### 현실적인 데이터
## 주요 특징

- 숙박/예약 도메인에 맞는 실습 데이터
- 실제 업무에서 마주칠 수 있는 형식과 구조
- 다양한 응답 패턴 포함 (긍정/부정/중립)

### 적절한 데이터 크기
- 너무 작지 않아 의미 있는 분석 가능
- 너무 크지 않아 실습 시간 내 처리 가능
- 확장 가능한 구조

## 💡 활용 팁

### 데이터 확장
필요시 Copilot에게 더 많은 데이터 생성 요청:

```
위와 같은 형식의 CSV 데이터를 100개 더 생성해줘.
```

### 커스터마이징
실제 프로젝트에 맞게 데이터 수정:

```
이 CSV 파일의 컬럼을 다음과 같이 변경해줘:
- "상태" 컬럼에 "환불 요청" 추가
- "지역" 컬럼에 "해외" 옵션 추가
```

### 에러 처리
파일을 찾을 수 없을 때:
1. 현재 작업 디렉토리 확인: `pwd` (Mac/Linux) 또는 `cd` (Windows)
2. 절대 경로로 파일 지정
3. 파일이 올바른 위치에 있는지 확인

## 🔍 데이터 검증

각 파일을 열어서 다음을 확인하세요:

### CSV 파일
- UTF-8 인코딩 (한글 깨짐 방지)
- 헤더 행 포함
- 쉼표로 구분된 값

### TXT 파일
- 읽기 쉬운 형식
- 실제 업무 문서와 유사한 구조

## 📞 문제 해결

### Q: 파일이 열리지 않아요
**A**: 
```python
# 인코딩 지정
df = pd.read_csv('data/file.csv', encoding='utf-8-sig')
```

### Q: 한글이 깨져요
**A**: 
```python
# macOS/Linux
df = pd.read_csv('data/file.csv', encoding='utf-8')

# Windows
df = pd.read_csv('data/file.csv', encoding='cp949')
```

### Q: 경로를 찾을 수 없어요
**A**: 
```python
import os
print(os.getcwd())  # 현재 디렉토리 확인
```

## 🎓 학습 목표

이 샘플 데이터들을 통해:
- ✅ 실제 업무 데이터 처리 경험
- ✅ 다양한 파일 형식 다루기 (CSV, TXT)
- ✅ Copilot을 활용한 데이터 분석 자동화
- ✅ 에러 처리 및 문제 해결 능력

---

**Happy Learning!** 🚀
