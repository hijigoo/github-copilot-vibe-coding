# Session 6: 업무 자동화 아이디어
## ⏰ 소요 시간: 30분 (3:10 – 3:40)

---

## 🎯 학습 목표

이 세션을 마치면 다음을 할 수 있습니다:
- ✅ 반복되는 업무를 자동화 가능 여부 판단
- ✅ Copilot에게 업무 설명하고 자동화 아이디어 도출
- ✅ 실행 가능한 자동화 스크립트 생성
- ✅ 나만의 자동화 도구 만들기

---

## 📖 시나리오

> **상황**: 여러분은 매주 반복되는 업무에 지쳤습니다. Excel 파일 정리, 이메일 리스트 추출, 파일 이름 변경 등 단순하지만 시간이 오래 걸리는 작업들입니다. 이제 이런 업무를 자동화하여 시간을 절약하고 싶습니다.

**문제점**:
- 매주 같은 작업 반복 (시간 낭비)
- 수작업으로 인한 실수 발생
- 창의적인 업무에 집중하지 못함

**목표**:
- Copilot으로 자동화 가능한 업무 식별
- 5분 만에 자동화 스크립트 생성
- 실제 업무에 바로 적용

---

## 💪 실습 1: 나의 반복 업무 분석하기 (5분)

### Step 1: Copilot Chat에 업무 설명

```
나는 매주 다음과 같은 반복 업무를 하고 있어:

1. Excel 파일에서 특정 조건에 맞는 행만 필터링해서 새 파일로 저장
2. 여러 폴더에 흩어진 이미지 파일을 날짜별로 정리
3. 이메일 주소가 포함된 텍스트 파일에서 이메일만 추출해서 리스트 만들기
4. PDF 파일 이름을 일괄적으로 변경 (예: "보고서_날짜_버전" 형식)
5. 매주 월요일 특정 웹사이트에서 데이터 다운로드

이 중에서 Python으로 자동화할 수 있는 작업과 
각 작업의 자동화 난이도(쉬움/보통/어려움)를 알려줘.
그리고 각 작업을 자동화하면 얼마나 시간을 절약할 수 있을지 예상해줘.
```

---

## 💪 실습 2: Excel 파일 자동 정리 스크립트 (10분)

가장 많이 사용되는 자동화: Excel 파일 처리

### 시나리오 상세

매주 영업팀에서 고객 리스트 Excel 파일을 받습니다. 이 파일에서:
- "결제 완료" 상태인 고객만 필터링
- 특정 컬럼만 추출 (이름, 이메일, 전화번호)
- 새 파일로 저장

### Step 1: 샘플 Excel 파일 준비

#### 방법 1: 샘플 파일 사용 (권장)
`sessions/data/customer_list_full.csv` 파일을 사용하세요. (20건의 데이터 포함)

#### 방법 2: 직접 생성

<details>
<summary>샘플 데이터 보기 (클릭하여 펼치기)</summary>

파일명: `customer_list.csv`

```csv
고객ID,이름,이메일,전화번호,상태,등록일,금액,지역
1001,김민수,minsu.kim@email.com,010-1234-5678,결제 완료,2024-11-01,150000,서울
1002,이지은,jieun.lee@email.com,010-2345-6789,대기 중,2024-11-02,200000,부산
1003,박준형,jun.park@email.com,010-3456-7890,결제 완료,2024-11-03,180000,제주
1004,최수진,sujin.choi@email.com,010-4567-8901,결제 완료,2024-11-04,220000,서울
1005,정다혜,dahye.jung@email.com,010-5678-9012,취소,2024-11-05,100000,부산
1006,한승우,seungwoo.han@email.com,010-6789-0123,결제 완료,2024-11-06,190000,강릉
1007,강미래,mirae.kang@email.com,010-7890-1234,대기 중,2024-11-07,250000,제주
1008,윤석진,seokjin.yoon@email.com,010-8901-2345,결제 완료,2024-11-08,170000,서울
```
</details>

---

### Step 2: 자동화 스크립트 요청

파일명: `filter_customers.py`

Copilot Chat에 다음 프롬프트 입력:

```
sessions/data/customer_list_full.csv 파일을 읽어서 다음 작업을 수행하는 Python 스크립트를 작성해줘:
(또는 직접 생성한 customer_list.csv 파일 사용)

1. "상태" 컬럼이 "결제 완료"인 행만 필터링
2. 필요한 컬럼만 선택: 이름, 이메일, 전화번호, 금액
3. 새 파일로 저장: "completed_customers_YYYY-MM-DD.csv"
4. 완료 후 다음 정보 출력:
   - 전체 고객 수
   - 결제 완료 고객 수
   - 총 결제 금액

pandas 라이브러리 사용.
오류 처리 포함.
주석 상세히.
```

---

### 예상 결과 코드

```python
import pandas as pd
from datetime import datetime

# 날짜 형식 (YYYY-MM-DD)
today = datetime.now().strftime('%Y-%m-%d')

try:
    # CSV 파일 읽기
    df = pd.read_csv('customer_list.csv', encoding='utf-8')
    print(f"✅ 파일을 읽었습니다. 전체 고객 수: {len(df)}명")
    
    # "결제 완료" 상태인 고객만 필터링
    completed = df[df['상태'] == '결제 완료']
    print(f"📊 결제 완료 고객 수: {len(completed)}명")
    
    # 필요한 컬럼만 선택
    result = completed[['이름', '이메일', '전화번호', '금액']]
    
    # 총 결제 금액 계산
    total_amount = completed['금액'].sum()
    print(f"💰 총 결제 금액: {total_amount:,}원")
    
    # 새 파일로 저장
    output_filename = f'completed_customers_{today}.csv'
    result.to_csv(output_filename, index=False, encoding='utf-8-sig')
    print(f"✅ 저장 완료: {output_filename}")
    
    # 요약 정보 출력
    print("\n" + "="*50)
    print("📋 작업 요약")
    print("="*50)
    print(f"전체 고객:           {len(df)}명")
    print(f"결제 완료 고객:      {len(completed)}명 ({len(completed)/len(df)*100:.1f}%)")
    print(f"총 결제 금액:        {total_amount:,}원")
    print(f"평균 결제 금액:      {completed['금액'].mean():,.0f}원")
    print("="*50)
    
except FileNotFoundError:
    print("❌ customer_list.csv 파일을 찾을 수 없습니다.")
except Exception as e:
    print(f"❌ 오류 발생: {e}")
```

---

## 💪 실습 3: 이메일 주소 자동 추출 (8분)

텍스트 파일에서 이메일 주소를 자동으로 추출하는 스크립트를 만들어봅시다.

### Step 1: 샘플 텍스트 파일 준비

#### 방법 1: 샘플 파일 사용 (권장)
`sessions/data/email_extraction_sample.txt` 파일을 사용하세요.

#### 방법 2: 직접 생성

<details>
<summary>샘플 데이터 보기 (클릭하여 펼치기)</summary>

파일명: `meeting_notes.txt`

```text
2024년 11월 주간 회의 참석자

회의 주제: Q4 마케팅 전략 논의

참석자:
- 김민수 (minsu.kim@yeogi.com) - 마케팅 팀장
- 이지은 (jieun.lee@yeogi.com) - PO
- 박준형 (jun.park@yeogi.com) - 개발팀장
- 최수진 사외 협력사 (sujin.choi@partner.com)

추가 참조:
support@yeogi.com
info@company.co.kr

다음 회의 참석 예정:
- 정다혜 (dahye.jung@yeogi.com)
- 한승우 외부 컨설턴트 (consultant@external.com)

문의사항은 contact@yeogi.com으로 보내주세요.
```
</details>

---

### Step 2: 이메일 추출 스크립트 요청

파일명: `extract_emails.py`

```
sessions/data/email_extraction_sample.txt 파일에서 모든 이메일 주소를 추출하는 Python 스크립트를 작성해줘:
(또는 직접 생성한 meeting_notes.txt 파일 사용)

1. 정규표현식을 사용하여 이메일 패턴 찾기
2. 중복 제거
3. 알파벳 순으로 정렬
4. 다음 두 가지 형식으로 저장:
   - emails.txt (한 줄에 하나씩)
   - emails.csv (이름 있으면 함께 저장)
5. 도메인별로 그룹핑해서 출력

오류 처리 포함.
```

---

## 💪 실습 4: 파일 이름 일괄 변경 (7분)

특정 패턴으로 파일 이름을 일괄 변경하는 스크립트

### 시나리오

다운로드 폴더에 다음과 같은 파일들이 있습니다:
```
IMG_20241101_123456.jpg
IMG_20241102_234567.jpg
screenshot_2024-11-03.png
document.pdf
report_final_v2.docx
```

이 파일들을 다음 규칙으로 변경하고 싶습니다:
```
2024-11-01_photo.jpg
2024-11-02_photo.jpg
2024-11-03_screenshot.png
document.pdf (변경 없음)
2024-11-XX_report.docx
```

---

### 프롬프트

```
지정한 폴더의 모든 파일 이름을 규칙에 따라 일괄 변경하는 Python 스크립트를 작성해줘:

요구사항:
1. 명령줄 인자로 폴더 경로 받기
2. 파일 타입별로 다른 규칙 적용:
   - 이미지 파일 (.jpg, .png): "YYYY-MM-DD_photo" 형식
   - 문서 파일 (.pdf, .docx): "YYYY-MM-DD_document" 형식
3. 날짜는 파일 이름에서 추출하거나, 없으면 수정 날짜 사용
4. 변경 전 미리보기 제공 (Y/N 확인)
5. 실행 로그 저장

사용 예시:
python rename_files.py /path/to/folder

안전장치:
- 같은 이름 충돌 시 자동으로 번호 추가
- 실행 취소 옵션 (원래 이름으로 복구)
```

---

## 🎯 예상 결과 코드 (파일 이름 변경)

```python
import os
import re
import shutil
from datetime import datetime
from pathlib import Path

def extract_date_from_filename(filename):
    """파일 이름에서 날짜 추출"""
    # YYYYMMDD 패턴
    pattern1 = r'(\d{4})(\d{2})(\d{2})'
    # YYYY-MM-DD 패턴
    pattern2 = r'(\d{4})-(\d{2})-(\d{2})'
    
    match = re.search(pattern1, filename) or re.search(pattern2, filename)
    if match:
        year, month, day = match.groups()
        return f"{year}-{month}-{day}"
    return None

def get_file_category(extension):
    """파일 확장자에 따라 카테고리 반환"""
    image_exts = ['.jpg', '.jpeg', '.png', '.gif']
    doc_exts = ['.pdf', '.docx', '.doc', '.xlsx']
    
    if extension.lower() in image_exts:
        return 'photo'
    elif extension.lower() in doc_exts:
        return 'document'
    else:
        return 'file'

def generate_new_filename(file_path):
    """새로운 파일 이름 생성"""
    path = Path(file_path)
    filename = path.stem
    extension = path.suffix
    
    # 날짜 추출 시도
    date_str = extract_date_from_filename(filename)
    
    # 날짜가 없으면 파일 수정 날짜 사용
    if not date_str:
        mod_time = os.path.getmtime(file_path)
        date_str = datetime.fromtimestamp(mod_time).strftime('%Y-%m-%d')
    
    # 카테고리 결정
    category = get_file_category(extension)
    
    # 새 파일 이름 생성
    new_name = f"{date_str}_{category}{extension}"
    return new_name

def rename_files(folder_path, execute=False):
    """폴더 내 파일 이름 일괄 변경"""
    if not os.path.exists(folder_path):
        print(f"❌ 폴더를 찾을 수 없습니다: {folder_path}")
        return
    
    # 변경 계획 수립
    rename_plan = []
    for filename in os.listdir(folder_path):
        file_path = os.path.join(folder_path, filename)
        
        # 디렉토리는 제외
        if os.path.isdir(file_path):
            continue
        
        new_name = generate_new_filename(file_path)
        new_path = os.path.join(folder_path, new_name)
        
        # 이름 충돌 처리
        counter = 1
        while os.path.exists(new_path) and new_path != file_path:
            name, ext = os.path.splitext(new_name)
            new_name = f"{name}_{counter}{ext}"
            new_path = os.path.join(folder_path, new_name)
            counter += 1
        
        if file_path != new_path:
            rename_plan.append((file_path, new_path, filename, new_name))
    
    # 미리보기
    if not rename_plan:
        print("✅ 변경할 파일이 없습니다.")
        return
    
    print(f"\n📋 총 {len(rename_plan)}개 파일 이름 변경 예정:\n")
    print(f"{'이전 이름':<40} → {'새 이름':<40}")
    print("=" * 85)
    for old_path, new_path, old_name, new_name in rename_plan:
        print(f"{old_name:<40} → {new_name:<40}")
    
    # 실행 확인
    if not execute:
        response = input("\n실행하시겠습니까? (Y/N): ").strip().upper()
        if response != 'Y':
            print("❌ 취소되었습니다.")
            return
    
    # 실행
    success_count = 0
    for old_path, new_path, old_name, new_name in rename_plan:
        try:
            os.rename(old_path, new_path)
            success_count += 1
            print(f"✅ {old_name} → {new_name}")
        except Exception as e:
            print(f"❌ 실패: {old_name} - {e}")
    
    print(f"\n🎉 완료: {success_count}/{len(rename_plan)} 파일 변경됨")

# 실행 예시
if __name__ == "__main__":
    import sys
    
    if len(sys.argv) < 2:
        print("사용법: python rename_files.py <폴더경로>")
        sys.exit(1)
    
    folder = sys.argv[1]
    rename_files(folder)
```

---

## 💡 나만의 자동화 아이디어 만들기 (실습)

이제 여러분의 실제 업무를 자동화해봅시다!

### 내 업무 자동화 워크시트

Copilot Chat에 다음을 입력하세요:

```
나는 [직무: PO/UX/마케터 등]로 일하고 있어.

매주/매일 반복하는 업무:
1. [구체적인 작업 설명]
2. [구체적인 작업 설명]
3. ...

각 작업에 대해:
1. 자동화 가능 여부
2. 자동화 난이도
3. 예상 시간 절약
4. 필요한 기술/도구
5. 구체적인 자동화 방법 제안

을 알려주고, 가장 효과적인 작업 3개에 대해서는 
실행 가능한 Python 스크립트를 작성해줘.
```

---

## 🎉 실습 완료!

축하합니다! 이제 여러분은:
- ✅ 반복 업무를 자동화할 수 있습니다
- ✅ Excel, 파일, 이메일 처리를 자동화할 수 있습니다
- ✅ 실제 업무에 적용할 수 있는 스크립트를 보유했습니다
- ✅ 비개발자도 자동화 도구를 만들 수 있습니다!

---

## 💡 실무 활용 팁

### 1. 작게 시작하기
- 가장 간단한 업무부터 자동화
- 성공 경험 쌓기
- 점진적으로 확대

### 2. 자동화 체크리스트
✅ 이 작업이 반복적인가?  
✅ 규칙이 명확한가?  
✅ 수작업 시 실수가 발생하는가?  
✅ 시간이 많이 걸리는가?  
→ 모두 YES면 자동화 대상!

### 3. 팀과 공유
- 유용한 스크립트를 팀원들과 공유
- 사용 가이드 문서 작성
- 피드백 받아 개선

### 4. 정기적으로 실행
- 작업 스케줄러 활용 (cron, Task Scheduler)
- 자동 실행 환경 구축
- 로그 모니터링

---

## 🎓 추가 도전 과제

### 도전 1: 웹 스크래핑 자동화
```
특정 웹사이트에서 매일 최신 뉴스 제목을 가져와서
Excel 파일로 저장하는 스크립트를 만들어줘.
requests와 BeautifulSoup 라이브러리 사용.
```

### 도전 2: 슬랙/텔레그램 봇
```
매일 아침 9시에 오늘의 할 일을 슬랙으로 알려주는 봇을 만들어줘.
Google Calendar API와 연동.
```

### 도전 3: 이미지 일괄 처리
```
폴더 내 모든 이미지를 자동으로:
1. 리사이즈 (1920x1080)
2. 워터마크 추가
3. 포맷 변환 (PNG → JPG)
Pillow 라이브러리 사용.
```

---

## 🔍 자주 묻는 질문

### Q1: Python이 설치되어 있지 않으면?
**A**: 
- macOS/Linux: 기본 설치됨
- Windows: [python.org](https://www.python.org)에서 다운로드
- 또는 Copilot에게 "Python 설치 방법" 질문

### Q2: 스크립트가 실행되지 않아요
**A**: 다음을 확인하세요:
```bash
# Python 버전 확인
python --version

# 필요한 패키지 설치
pip install pandas

# 파일 경로 확인 (절대 경로 사용)
pwd  # 현재 디렉토리 확인
```

### Q3: 회사 보안 정책으로 스크립트 실행이 안 돼요
**A**: IT 부서에 문의하여:
- Python 실행 권한 요청
- 필요한 패키지 설치 요청
- 또는 IT 부서와 협력하여 안전한 자동화 환경 구축

---

## 📚 다음 세션 미리보기

**Session 6: 나만의 워크플로 설계**에서는:
- 지금까지 배운 내용 종합
- 나만의 Copilot 워크플로 다이어그램 작성
- 일일/주간 루틴 자동화 계획
- Q&A 및 마무리

준비물: 없음 (오늘 배운 내용 복습)

---

**이전**: [← Session 4: CSV to HTML Report](session4_csv_report.md)  
**다음**: [Session 6: 워크플로 설계 →](session6_workflow.md)
