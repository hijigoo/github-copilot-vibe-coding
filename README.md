# GitHub Copilot 워크숍

> 🚀 **처음 오셨나요?** [`START_HERE.md`](START_HERE.md) 파일부터 읽어보세요!

---

## 📚 프로젝트 개요

비개발자(PO/UX/마케터 등)를 위한 GitHub Copilot 실전 활용 교육 자료입니다.

**대상**: 코딩 경험이 없는 비개발자  
**목표**: AI로 업무 자동화 및 생산성 향상  
**특징**: 100% 실습 중심, 즉시 활용 가능한 실전 예제

---

## 📁 프로젝트 구조

```
yeogi-hackathon/
├── README.md                   # 이 파일 (시작 가이드)
│
├── sessions/                   # 📚 세션별 실습 가이드
│   ├── session0_setup.md              # 환경 세팅 & Hello Copilot (25분)
│   ├── session1_meeting_notes.md      # 회의록 자동 정리 (30분)
│   ├── session2_document_automation.md # 문서 자동 작성 (30분)
│   ├── session3_ux_research.md        # UX 리서치 분석 (25분)
│   ├── session4_csv_report.md         # CSV 데이터 분석 (25분)
│   ├── session5_automation.md         # 반복 작업 자동화 (20분)
│   ├── session6_workflow.md           # 실전 워크플로우 통합 (20분)
│   └── data/                          # 실습용 샘플 데이터
│       ├── sample_meeting_notes.txt
│       ├── user_feedback_data.txt
│       ├── customer_satisfaction_survey.csv
│       ├── customer_list_full.csv
│       ├── email_extraction_sample.txt
│       └── README.md
│
└── samples/                    # 📂 추가 샘플 파일
    ├── customer_satisfaction.csv
    ├── customer_list.csv
    ├── meeting_notes.txt
    └── README.md
```

---

## 🎯 학습 목표

이 워크샵을 통해 다음을 배웁니다:

### 핵심 역량
1. **AI 프롬프트 작성** - Copilot과 효과적으로 대화하는 방법
2. **문서 자동화** - 회의록, PRD, 보고서를 5분 만에 작성
3. **데이터 분석** - Python으로 데이터 분석 및 시각화
4. **웹 개발 기초** - 간단한 웹 애플리케이션 만들기
5. **업무 자동화** - 반복 작업을 스크립트로 자동화
6. **워크플로우 설계** - 여러 기술을 통합한 자동화 시스템

### 기대 효과
- ⏱️ **시간 절약**: 주당 17시간 이상 절약
- 📈 **생산성 향상**: 반복 작업 자동화
- 💡 **새로운 가능성**: 코딩으로 문제 해결
- 🎨 **창의적 업무**: 단순 작업에서 벗어나 전략적 업무에 집중

---

## 📘 세션 구성

### 전체 실습 환경
모든 세션은 **Python 가상환경 (.venv)**에서 진행됩니다.
- 독립적인 실습 환경
- 시스템 Python과 분리
- 패키지 충돌 방지

### 세션 목록

| # | 세션 | 주요 내용 | 결과물 | 시간 |
|---|------|-----------|--------|------|
| 0 | **환경 세팅** | VS Code, Copilot, 가상환경 설정 | `.venv/` 생성 | 25분 |
| 1 | **회의록 자동 정리** | Action Item 추출, 구조화 | `meeting_action_items.md` | 30분 |
| 2 | **문서 자동 작성** | PRD 5분 만에 완성 | `feature_prd.md` | 30분 |
| - | ☕ **Break** | 휴식 | - | 15분 |
| 3 | **UX 리서치 분석** | 사용자 피드백 자동 분석 | `ux_insights.md` | 25분 |
| 4 | **데이터 분석 & 시각화** | CSV → 차트 자동 생성 | `report.png` | 25분 |
| 5 | **웹 애플리케이션** | 간단한 웹페이지 만들기 | `app.py`, `index.html` | 30분 |
| 6 | **반복 작업 자동화** | 이메일 추출, 파일 정리 | `automation.py` | 20분 |
| 7 | **실전 워크플로우** | 모든 기술 통합 | `workflow.py` | 20분 |

**총 소요 시간**: 약 3시간 40분 (휴식 포함)

---

## 🚀 빠른 시작

### 📺 교육 당일 순서
1. **강사 안내에 따라** `sessions/session0_setup.md` 파일을 엽니다
2. **Step-by-Step**으로 따라하면서 실습합니다
3. **각 세션 종료 후** 결과물을 저장합니다
4. **질문이 있으면** 언제든 강사에게 물어보세요!

### 📋 사전 준비물

1. **노트북** (macOS 또는 Windows)
2. **GitHub 계정** - [가입하기](https://github.com/signup)
3. **GitHub Copilot 라이선스** (회사 제공)
4. **VS Code** - [다운로드](https://code.visualstudio.com/)

### 설치 가이드

#### 1. VS Code 설치
```bash
# macOS (Homebrew 사용 시)
brew install --cask visual-studio-code

# 또는 공식 웹사이트에서 다운로드
# https://code.visualstudio.com/Download
```

#### 2. GitHub Copilot 확장 설치
- VS Code 실행
- Extensions (`⌘+Shift+X` 또는 `Ctrl+Shift+X`) 열기
- "GitHub Copilot" 검색 및 설치
- "GitHub Copilot Chat" 검색 및 설치
- GitHub 계정으로 로그인

#### 3. Python 설치
```bash
# macOS
brew install python

# Windows
# https://www.python.org/downloads/ 에서 다운로드
# "Add Python to PATH" 옵션 체크!

# 설치 확인
python --version  # 또는 python3 --version
```

#### 4. 가상환경 설정 (중요!)
```bash
# 프로젝트 폴더로 이동
cd yeogi-hackathon

# 가상환경 생성
python -m venv .venv

# 가상환경 활성화
# macOS/Linux:
source .venv/bin/activate

# Windows (PowerShell):
.venv\Scripts\Activate.ps1

# Windows (CMD):
.venv\Scripts\activate.bat

# 가상환경이 활성화되면 (.venv)가 터미널 앞에 표시됩니다
```

#### 5. 필요한 패키지 설치
```bash
# 가상환경 활성화 후 실행
pip install pandas matplotlib flask
```

---

## 📖 실습 방법

### 1단계: 세션 문서 열기
- VS Code에서 `sessions/session0_setup.md` 파일을 엽니다
- Markdown Preview (`⌘+Shift+V` 또는 `Ctrl+Shift+V`)를 사용하면 더 보기 좋습니다

### 2단계: 단계별로 따라하기
- 문서의 각 단계를 순서대로 진행합니다
- 프롬프트를 복사하여 Copilot Chat에 입력합니다
- 생성된 결과물을 확인하고 저장합니다

### 3단계: 다음 세션으로
- 한 세션이 끝나면 다음 세션으로 넘어갑니다
- Session 0 → 1 → 2 → (휴식) → 3 → 4 → 5 → 6 → 7

### 💡 도움이 필요하면?
- 각 세션 문서의 "자주 묻는 질문" 섹션을 확인하세요
- 언제든 강사에게 질문하세요!

---

## 💡 주요 학습 포인트

### 1. 프롬프트 작성 기술
- ✅ 구체적이고 명확하게
- ✅ 원하는 형식 지정 (표, 리스트 등)
- ✅ 단계별로 요청
- ✅ 예시 제공

### 2. Copilot 활용 시나리오
- 📝 문서 작성 및 정리
- 📊 데이터 분석 및 시각화
- 🤖 반복 업무 자동화
- 🔄 업무 프로세스 개선

### 3. 실무 적용 팁
- 템플릿화하여 재사용
- 팀과 프롬프트 공유
- 시간 절약 효과 측정
- 지속적인 개선

---

## 📊 기대 효과

### 시간 절약
- 회의록 정리: 30분 → 5분 (**83% 단축**)
- PRD 작성: 2시간 → 5분 (**96% 단축**)
- UX 데이터 분석: 5.5시간 → 18분 (**95% 단축**)
- CSV 데이터 분석: 5시간 → 20분 (**93% 단축**)
- 웹 페이지 제작: 2일 → 30분 (**99% 단축**)
- 이메일 추출: 65분 → 3초 (**99.9% 단축**)
- **주당 평균 17시간 이상 절약 가능**

### 품질 향상
- 일관된 문서 형식
- 실수 감소
- 더 많은 분석 시도
- 창의적 업무에 집중



---

## 🎓 추가 학습 자료

### 공식 문서
- [GitHub Copilot Documentation](https://docs.github.com/en/copilot)
- [Copilot Best Practices](https://github.blog/developer-skills/github/how-to-write-better-prompts-for-github-copilot/)

### 커뮤니티
- [GitHub Copilot Community](https://github.com/community)
- [Stack Overflow](https://stackoverflow.com/questions/tagged/github-copilot)

### 비디오 튜토리얼
- [GitHub YouTube Channel](https://www.youtube.com/@GitHub)
- Copilot 활용 사례 영상

---

## 🤝 기여 및 피드백

### 피드백 제공
- 교육 후 설문조사 참여
- 개선 아이디어 제안
- 성공 사례 공유

### 문서 개선
- 오타나 오류 발견 시 제보
- 추가 예제 제안
- 번역 개선

---

##  라이선스

이 교육 자료는 GitHub Copilot 학습용으로 자유롭게 사용하실 수 있습니다.

---

## 🎊 감사의 말

이 워크숍을 통해 여러분이:
- ⏱️ 시간을 절약하고
- 📈 생산성을 높이고
- ✨ 더 창의적인 업무에 집중할 수 있기를

바랍니다!

**GitHub Copilot과 함께 더 효율적으로 일하세요!** 🚀

---

## 📂 주요 문서

- [`sessions/`](sessions/) - 세션별 실습 가이드 (Session 0-7) ⭐
- [`sessions/data/`](sessions/data/) - 실습용 샘플 데이터
- [`samples/`](samples/) - 추가 샘플 파일

---

**버전**: v3.0  
**최종 업데이트**: 2024년 11월  
**작성**: GitHub Copilot Workshop Team
