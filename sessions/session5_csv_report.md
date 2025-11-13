# Session 5: CSV 데이터를 HTML 리포트로 변환
## ⏰ 소요 시간: 30분 (2:20 – 2:50)

---

## 🎯 학습 목표

이 세션을 마치면 다음을 할 수 있습니다:
- ✅ CSV 데이터를 자동으로 읽고 분석
- ✅ 데이터 시각화 (막대그래프, 파이차트)
- ✅ HTML 리포트 자동 생성
- ✅ 브라우저에서 결과 확인 및 공유

---

## 📖 시나리오

> **상황**: 여러분은 고객 만족도 설문조사를 진행했습니다. 100개의 응답 데이터가 CSV 파일로 수집되었습니다. 이제 이 데이터를 분석하고, 경영진에게 보고할 시각화 리포트를 만들어야 합니다.

**문제점**:
- Excel로 수작업 분석 시 시간 소요 (2~3시간)
- 차트 만들기 번거로움
- 매번 같은 형식의 리포트 작성 반복

**목표**:
- Copilot으로 10분 내에 리포트 완성
- 자동 차트 생성 및 인사이트 도출
- HTML로 내보내어 쉽게 공유

---

## 📋 실습 재료: 샘플 CSV 파일

### 방법 1: 샘플 파일 사용 (권장)
`sessions/data/customer_satisfaction_survey.csv` 파일을 사용하세요. (50건의 데이터 포함)

### 방법 2: 직접 생성

#### Step 1: 새 파일 생성
파일명: `customer_satisfaction.csv`

#### Step 2: CSV 데이터 입력

<details>
<summary>샘플 데이터 보기 (클릭하여 펼치기)</summary>

다음 데이터를 복사하여 붙여넣으세요:

```csv
응답ID,연령대,직업,서비스_만족도,가격_만족도,앱_사용성,고객센터_만족도,재이용_의향,추천_의향,주요_불만사항
1,20대,학생,4,3,4,5,4,4,가격이 비쌈
2,30대,직장인,5,4,5,5,5,5,없음
3,20대,프리랜서,3,3,3,4,3,3,검색 속도 느림
4,40대,자영업,4,4,4,4,4,4,없음
5,30대,직장인,2,2,3,3,2,2,리뷰 신뢰도 낮음
6,20대,학생,4,3,4,4,4,3,할인 부족
7,30대,공무원,5,5,5,5,5,5,없음
8,20대,대학생,3,2,3,4,3,2,UI가 구식
9,40대,회사원,4,4,4,4,4,4,없음
10,30대,프리랜서,3,3,4,3,3,3,필터 사용 불편
11,20대,직장인,4,4,5,5,4,4,없음
12,30대,회사원,2,3,3,3,2,2,검색 속도 느림
13,40대,임원,5,4,4,5,5,4,없음
14,20대,학생,3,2,3,3,3,2,가격이 비쌈
15,30대,프리랜서,4,4,4,4,4,4,없음
16,20대,직장인,5,5,5,5,5,5,매우 만족
17,30대,공무원,4,4,4,4,4,4,없음
18,40대,자영업,3,3,3,4,3,3,지도 기능 없음
19,20대,대학생,2,2,2,3,2,2,가격이 비쌈
20,30대,회사원,4,4,4,4,4,4,없음
21,30대,직장인,5,5,5,5,5,5,없음
22,20대,프리랜서,3,3,4,3,3,3,리뷰 부족
23,40대,회사원,4,4,4,5,4,4,없음
24,30대,스타트업,3,3,3,3,3,3,검색 속도 느림
25,20대,학생,4,3,4,4,4,3,할인 부족
```
</details>

---

## 💪 실습 1: Python 코드로 데이터 분석 및 HTML 생성 (15분)

### Step 1: 새 Python 파일 생성
파일명: `generate_report.py`

### Step 2: Copilot Chat에 프롬프트 입력

```
위의 customer_satisfaction.csv 파일을 읽어서
다음 작업을 수행하는 Python 코드를 작성해줘:

1. CSV 파일 읽기 (pandas 사용)
2. 기본 통계 분석:
   - 각 만족도 항목의 평균, 최소값, 최대값
   - 연령대별 평균 만족도
   - 직업별 평균 만족도
3. 데이터 시각화 (matplotlib 사용):
   - 서비스 만족도 분포 막대그래프
   - 연령대별 평균 만족도 비교 그래프
   - 재이용 의향 분포 파이차트
4. HTML 리포트 생성:
   - 리포트 제목: "고객 만족도 조사 결과"
   - 통계 요약 표
   - 그래프 3개 포함
   - CSS 스타일링 (깔끔한 디자인)
5. 브라우저에서 자동으로 열기

코드는 주석을 포함해서 작성해줘.
오류 처리도 포함해줘.
```

---

### Step 3: 파일 경로 확인

코드에서 CSV 파일 경로를 확인하세요:

```python
# 샘플 파일 사용 시
df = pd.read_csv('sessions/data/customer_satisfaction_survey.csv', encoding='utf-8')

# 또는 직접 생성한 파일 사용 시
df = pd.read_csv('customer_satisfaction.csv', encoding='utf-8')
```

### Step 4: 코드 리뷰 및 실행

Copilot이 생성한 코드를 검토하고, 필요시 다음과 같이 수정 요청:

**그래프 색상 변경**:
```
그래프 색상을 여기어때 브랜드 컬러(주황색 계열)로 변경해줘.
```

**한글 폰트 설정**:
```
matplotlib 한글 폰트 깨짐 문제를 해결하는 코드를 추가해줘.
macOS와 Windows 모두 지원되도록.
```

**추가 인사이트**:
```
주요_불만사항 항목을 분석해서,
가장 많이 언급된 불만 Top 5를 표로 추가해줘.
```

---

### Step 5: 코드 실행

터미널에서 다음 명령어 실행:

```bash
python generate_report.py
```

필요한 라이브러리가 없다면 설치:

```bash
pip install pandas matplotlib
```

**참고**: 파일 경로 오류가 발생하면 절대 경로를 사용하거나, CSV 파일과 Python 파일이 같은 폴더에 있는지 확인하세요.

---

## 🎯 예상 결과물: Python 코드 예시

```python
import pandas as pd
import matplotlib.pyplot as plt
import matplotlib.font_manager as fm
import webbrowser
import os
from collections import Counter

# 한글 폰트 설정 (macOS/Windows 호환)
try:
    # macOS
    plt.rc('font', family='AppleGothic')
except:
    try:
        # Windows
        plt.rc('font', family='Malgun Gothic')
    except:
        print("한글 폰트를 찾을 수 없습니다. 기본 폰트를 사용합니다.")

plt.rcParams['axes.unicode_minus'] = False  # 마이너스 기호 깨짐 방지

# CSV 파일 읽기
try:
    df = pd.read_csv('customer_satisfaction.csv', encoding='utf-8')
    print("✅ CSV 파일을 성공적으로 읽었습니다.")
except FileNotFoundError:
    print("❌ customer_satisfaction.csv 파일을 찾을 수 없습니다.")
    exit()

# 기본 통계 분석
satisfaction_cols = ['서비스_만족도', '가격_만족도', '앱_사용성', '고객센터_만족도']
stats = df[satisfaction_cols].describe()

# 연령대별 평균 만족도
age_avg = df.groupby('연령대')[satisfaction_cols].mean()

# 주요 불만사항 Top 5
complaints = [c for c in df['주요_불만사항'] if c != '없음']
complaint_counts = Counter(complaints)
top_complaints = complaint_counts.most_common(5)

# 시각화 1: 서비스 만족도 분포
plt.figure(figsize=(10, 6))
satisfaction_dist = df['서비스_만족도'].value_counts().sort_index()
bars = plt.bar(satisfaction_dist.index, satisfaction_dist.values, color='#FF6B35')
plt.xlabel('만족도 점수', fontsize=12)
plt.ylabel('응답 수', fontsize=12)
plt.title('서비스 만족도 분포', fontsize=14, fontweight='bold')
plt.xticks([1, 2, 3, 4, 5])
plt.grid(axis='y', alpha=0.3)
plt.tight_layout()
plt.savefig('chart1_satisfaction.png', dpi=100, bbox_inches='tight')
plt.close()

# 시각화 2: 연령대별 평균 만족도
plt.figure(figsize=(10, 6))
age_avg_overall = df.groupby('연령대')['서비스_만족도'].mean()
bars = plt.bar(age_avg_overall.index, age_avg_overall.values, color='#FF8C42')
plt.xlabel('연령대', fontsize=12)
plt.ylabel('평균 만족도', fontsize=12)
plt.title('연령대별 평균 서비스 만족도', fontsize=14, fontweight='bold')
plt.ylim(0, 5)
plt.grid(axis='y', alpha=0.3)
# 막대 위에 값 표시
for bar in bars:
    height = bar.get_height()
    plt.text(bar.get_x() + bar.get_width()/2., height,
             f'{height:.2f}',
             ha='center', va='bottom', fontsize=10)
plt.tight_layout()
plt.savefig('chart2_age_satisfaction.png', dpi=100, bbox_inches='tight')
plt.close()

# 시각화 3: 재이용 의향 분포 (파이차트)
plt.figure(figsize=(8, 8))
reuse_dist = df['재이용_의향'].value_counts().sort_index()
colors = ['#FFA07A', '#FF8C42', '#FF6B35', '#E55934', '#C44536']
plt.pie(reuse_dist.values, labels=[f'{i}점' for i in reuse_dist.index],
        autopct='%1.1f%%', startangle=90, colors=colors[:len(reuse_dist)])
plt.title('재이용 의향 분포', fontsize=14, fontweight='bold')
plt.tight_layout()
plt.savefig('chart3_reuse.png', dpi=100, bbox_inches='tight')
plt.close()

print("✅ 차트 3개를 생성했습니다.")

# HTML 리포트 생성
html_content = f"""
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>고객 만족도 조사 결과</title>
    <style>
        * {{
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }}
        body {{
            font-family: 'Segoe UI', 'Malgun Gothic', sans-serif;
            background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
            padding: 20px;
            line-height: 1.6;
        }}
        .container {{
            max-width: 1200px;
            margin: 0 auto;
            background: white;
            padding: 40px;
            border-radius: 10px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
        }}
        h1 {{
            color: #FF6B35;
            text-align: center;
            margin-bottom: 10px;
            font-size: 32px;
        }}
        .subtitle {{
            text-align: center;
            color: #666;
            margin-bottom: 40px;
            font-size: 14px;
        }}
        .summary {{
            background: #FFF5F0;
            padding: 20px;
            border-radius: 8px;
            margin-bottom: 30px;
            border-left: 4px solid #FF6B35;
        }}
        .summary h2 {{
            color: #FF6B35;
            margin-bottom: 15px;
            font-size: 20px;
        }}
        table {{
            width: 100%;
            border-collapse: collapse;
            margin: 20px 0;
        }}
        th, td {{
            padding: 12px;
            text-align: left;
            border-bottom: 1px solid #ddd;
        }}
        th {{
            background-color: #FF6B35;
            color: white;
            font-weight: bold;
        }}
        tr:hover {{
            background-color: #f5f5f5;
        }}
        .chart-section {{
            margin: 40px 0;
        }}
        .chart-section h2 {{
            color: #333;
            margin-bottom: 20px;
            font-size: 22px;
            border-bottom: 2px solid #FF6B35;
            padding-bottom: 10px;
        }}
        .chart-section img {{
            width: 100%;
            max-width: 800px;
            display: block;
            margin: 20px auto;
            border-radius: 8px;
            box-shadow: 0 4px 10px rgba(0,0,0,0.1);
        }}
        .insight {{
            background: #E8F4F8;
            padding: 20px;
            border-radius: 8px;
            margin: 20px 0;
            border-left: 4px solid #4A90E2;
        }}
        .insight h3 {{
            color: #4A90E2;
            margin-bottom: 10px;
        }}
        .footer {{
            text-align: center;
            margin-top: 40px;
            padding-top: 20px;
            border-top: 1px solid #ddd;
            color: #999;
            font-size: 12px;
        }}
    </style>
</head>
<body>
    <div class="container">
        <h1>📊 고객 만족도 조사 결과</h1>
        <p class="subtitle">여기어때 서비스 품질 개선을 위한 사용자 피드백 분석</p>
        
        <div class="summary">
            <h2>🎯 핵심 요약</h2>
            <ul>
                <li><strong>총 응답 수:</strong> {len(df)}명</li>
                <li><strong>평균 서비스 만족도:</strong> {df['서비스_만족도'].mean():.2f}/5.0</li>
                <li><strong>평균 재이용 의향:</strong> {df['재이용_의향'].mean():.2f}/5.0</li>
                <li><strong>평균 추천 의향:</strong> {df['추천_의향'].mean():.2f}/5.0</li>
                <li><strong>가장 만족도가 높은 항목:</strong> {satisfaction_cols[df[satisfaction_cols].mean().idxmax()]}</li>
                <li><strong>가장 만족도가 낮은 항목:</strong> {satisfaction_cols[df[satisfaction_cols].mean().idxmin()]}</li>
            </ul>
        </div>

        <div class="chart-section">
            <h2>📈 상세 분석 결과</h2>
            
            <h3>1. 서비스 만족도 분포</h3>
            <img src="chart1_satisfaction.png" alt="서비스 만족도 분포">
            
            <div class="insight">
                <h3>💡 인사이트</h3>
                <p>응답자의 {(df['서비스_만족도'] >= 4).sum() / len(df) * 100:.1f}%가 4점 이상의 만족도를 보여,
                전반적으로 긍정적인 평가를 받고 있습니다.</p>
            </div>

            <h3>2. 연령대별 평균 만족도</h3>
            <img src="chart2_age_satisfaction.png" alt="연령대별 만족도">
            
            <div class="insight">
                <h3>💡 인사이트</h3>
                <p>{age_avg_overall.idxmax()} 사용자의 만족도가 가장 높으며 ({age_avg_overall.max():.2f}점),
                {age_avg_overall.idxmin()} 사용자 대상 개선이 필요합니다 ({age_avg_overall.min():.2f}점).</p>
            </div>

            <h3>3. 재이용 의향 분포</h3>
            <img src="chart3_reuse.png" alt="재이용 의향">
            
            <div class="insight">
                <h3>💡 인사이트</h3>
                <p>재이용 의향 4점 이상 응답자가 {(df['재이용_의향'] >= 4).sum() / len(df) * 100:.1f}%로,
                높은 고객 충성도를 보여주고 있습니다.</p>
            </div>
        </div>

        <div class="summary">
            <h2>🔴 주요 불만사항 Top 5</h2>
            <table>
                <tr>
                    <th>순위</th>
                    <th>불만사항</th>
                    <th>언급 횟수</th>
                </tr>
                {''.join([f"<tr><td>{i+1}</td><td>{item[0]}</td><td>{item[1]}회</td></tr>" 
                         for i, item in enumerate(top_complaints)])}
            </table>
        </div>

        <div class="summary">
            <h2>📊 항목별 평균 만족도</h2>
            <table>
                <tr>
                    <th>항목</th>
                    <th>평균</th>
                    <th>최소</th>
                    <th>최대</th>
                    <th>표준편차</th>
                </tr>
                {''.join([f"""<tr>
                    <td>{col}</td>
                    <td>{stats[col]['mean']:.2f}</td>
                    <td>{stats[col]['min']:.0f}</td>
                    <td>{stats[col]['max']:.0f}</td>
                    <td>{stats[col]['std']:.2f}</td>
                </tr>""" for col in satisfaction_cols])}
            </table>
        </div>

        <div class="footer">
            <p>Generated by GitHub Copilot Workshop | 여기어때컴퍼니 | {pd.Timestamp.now().strftime('%Y년 %m월 %d일')}</p>
        </div>
    </div>
</body>
</html>
"""

# HTML 파일 저장
html_filename = 'customer_satisfaction_report.html'
with open(html_filename, 'w', encoding='utf-8') as f:
    f.write(html_content)

print(f"✅ HTML 리포트를 생성했습니다: {html_filename}")

# 브라우저에서 자동으로 열기
file_path = os.path.abspath(html_filename)
webbrowser.open('file://' + file_path)
print("🌐 브라우저에서 리포트를 열었습니다.")
```

---

## 💪 실습 2: 리포트 커스터마이징 (10분)

생성된 리포트를 개선해봅시다.

### 추가 기능 요청

**1. 인터랙티브 차트로 변경**:
```
위의 코드를 수정해서, matplotlib 대신 plotly를 사용해줘.
인터랙티브한 차트로 만들고, HTML에 임베드해줘.
```

**2. 엑셀 내보내기 기능 추가**:
```
분석 결과를 Excel 파일(.xlsx)로도 내보내는 기능을 추가해줘.
여러 시트로 구성:
- Sheet 1: 요약 통계
- Sheet 2: 연령대별 분석
- Sheet 3: 불만사항 목록
```

**3. 이메일 발송 기능**:
```
생성된 HTML 리포트를 이메일로 발송하는 함수를 추가해줘.
Gmail SMTP 사용, 첨부파일로 HTML과 이미지 포함.
```

---

## 💪 실습 3: 자동화 스크립트 만들기 (5분)

매주 반복되는 리포트 생성을 자동화해봅시다.

### 프롬프트

```
위의 코드를 개선해서, 다음 기능을 추가해줘:

1. 명령줄 인자로 CSV 파일 경로 받기
2. 리포트 출력 디렉토리 지정 가능
3. 날짜별로 리포트 자동 저장 (YYYY-MM-DD 형식)
4. 로그 파일 생성 (성공/실패 기록)
5. 에러 발생 시 상세 에러 메시지 출력

사용 예시:
python generate_report.py --input data.csv --output ./reports/

argparse 라이브러리를 사용해줘.
```

---

## 🎉 실습 완료!

축하합니다! 이제 여러분은:
- ✅ CSV 데이터를 자동으로 분석하고 시각화할 수 있습니다
- ✅ 전문가 수준의 HTML 리포트를 생성할 수 있습니다
- ✅ 코드를 커스터마이징하고 자동화할 수 있습니다
- ✅ 비개발자도 데이터 분석 작업을 수행할 수 있습니다!

---

## 💡 실무 활용 팁

### 1. 정기 리포트 자동화
```bash
# macOS/Linux: cron 작업 설정
0 9 * * 1 python /path/to/generate_report.py --input weekly_data.csv

# Windows: 작업 스케줄러 사용
```

### 2. 다양한 데이터 소스 지원
- Google Sheets API 연동
- 데이터베이스 직접 쿼리
- API에서 데이터 가져오기

### 3. 리포트 템플릿화
- 회사 CI/CD에 맞게 디자인 변경
- 로고 및 브랜드 요소 추가
- 부서별 커스텀 템플릿 생성

### 4. 대시보드로 확장
- 여러 리포트를 하나의 대시보드로 통합
- 실시간 데이터 업데이트
- 필터링 및 드릴다운 기능

---

## 🎓 추가 도전 과제

### 도전 1: 비교 리포트 생성
```
이번 달 데이터와 지난 달 데이터를 비교하는 리포트를 만들어줘.
증감률을 계산하고, 화살표(▲▼)로 표시해줘.
```

### 도전 2: 실시간 대시보드
```
Flask 웹 애플리케이션으로 실시간 대시보드를 만들어줘.
CSV 파일이 업데이트되면 자동으로 리프레시되도록.
```

### 도전 3: PDF 내보내기
```
HTML 리포트를 PDF로 변환하는 기능을 추가해줘.
pdfkit 또는 weasyprint 라이브러리 사용.
```

---

## 🔍 자주 묻는 질문

### Q1: Python을 한 번도 써본 적이 없는데 괜찮나요?
**A**: 네! Copilot이 모든 코드를 작성해줍니다. 실행만 하면 됩니다.

### Q2: CSV 파일 형식이 다르면 어떻게 하나요?
**A**: Copilot에게 실제 CSV 샘플을 보여주고 코드 수정 요청:
```
내 CSV 파일은 다음과 같은 구조야:
[샘플 데이터 붙여넣기]

이 형식에 맞게 코드를 수정해줘.
```

### Q3: 차트를 PowerPoint에 넣고 싶어요
**A**: 차트 이미지(PNG)를 PPT에 직접 삽입하거나:
```
차트를 SVG 형식으로 저장하는 옵션을 추가해줘.
고해상도로 출력되도록.
```

---

## 📚 다음 세션 미리보기

**Session 5: 업무 자동화 아이디어**에서는:
- 반복 업무를 자동화하는 코드 생성
- Excel에서 이메일 리스트 추출
- 파일 정리 자동화
- 나만의 자동화 스크립트 만들기

준비물: 없음 (바로 시작 가능)

---

**이전**: [← Session 3: UX 리서치 분석](session3_ux_research.md)  
**다음**: [Session 5: 업무 자동화 →](session5_automation.md)
