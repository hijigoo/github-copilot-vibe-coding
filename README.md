# GitHub Copilot 워크숍 - 여기어때컴퍼니

> 🚀 **처음 오셨나요?** [`START_HERE.md`](START_HERE.md) 파일부터 읽어보세요!

---

## 📚 프로젝트 개요

여기어때컴퍼니 비개발자(PO/UX/마케팅) 대상 GitHub Copilot 실전 활용 교육 자료입니다.

**교육 일정**: 2024년 11월 말 ~ 12월 초 (12/11 해커톤 사전 교육)  
**교육 시간**: 3시간 15분 (휴식 포함)  
**참가 인원**: 45명 (PO 16명 + UX 16명 + 마케터 1명 + 개발자 28명)

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

## 🎯 교육 목표

비개발자가 GitHub Copilot을 활용하여:
1. **문서 작업 자동화** - 회의록, PRD, 보고서를 5분 만에 작성
2. **데이터 분석 간소화** - UX 리서치, 설문 데이터 자동 분석
3. **반복 업무 자동화** - Excel 처리, 파일 정리 등 스크립트 생성
4. **개인별 워크플로 설계** - 일일/주간 업무 루틴에 Copilot 통합

---

## 📘 세션 구성

| 시간 | 세션 | 주요 내용 | 결과물 |
|------|------|-----------|--------|
| 0:00-0:25 | **Session 0** | 환경 세팅 & 첫 프롬프트 | `hello_copilot.md` |
| 0:25-0:55 | **Session 1** | 회의록 자동 정리 | `meeting_action_items.md` |
| 0:55-1:27 | **Session 2** | PRD 5분 만에 작성 | `feature_prd.md` |
| 1:27-1:42 | ☕ **Break** | 휴식 | - |
| 1:42-2:10 | **Session 3** | UX 피드백 자동 분석 | `ux_insights.md`, `ux_analysis.py` |
| 2:10-2:37 | **Session 4** | CSV 데이터 분석 & 시각화 | `satisfaction_report.png` |
| 2:37-2:57 | **Session 5** | 반복 작업 자동화 | `email_extraction.py` |
| 2:57-3:15 | **Session 6** | 실전 워크플로우 통합 | `workflow_automation.py` |

**총 소요 시간**: 3시간 13분 (여유 시간 2분 포함) ✅

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

1. **VS Code 설치**
   ```bash
   # macOS (Homebrew 사용 시)
   brew install --cask visual-studio-code
   
   # 또는 공식 웹사이트에서 다운로드
   # https://code.visualstudio.com/Download
   ```

2. **GitHub Copilot 확장 설치**
   - VS Code 실행
   - Extensions (`⌘+Shift+X`) 열기
   - "GitHub Copilot" 검색 및 설치
   - "GitHub Copilot Chat" 검색 및 설치
   - GitHub 계정으로 로그인

3. **Python 설치** (Session 4, 5 필요)
   ```bash
   # macOS
   brew install python
   
   # Windows
   # https://www.python.org/downloads/
   ```

4. **필요한 Python 패키지**
   ```bash
   pip install pandas matplotlib
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
- Session 0 → 1 → 2 → (휴식) → 3 → 4 → 5 → 6

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

## 📊 실제 검증된 효과

### 시간 절약 (Dry-Run 검증 완료)
- 회의록 정리: 30분 → 5분 (**83% 단축**) ✅
- PRD 작성: 2시간 → 5분 (**96% 단축**) ✅
- UX 데이터 분석: 5.5시간 → 18분 (**95% 단축**) ✅
- CSV 데이터 분석: 5시간 → 20분 (**93% 단축**) ✅
- 이메일 추출: 65분 → 3초 (**99.9% 단축**) ✅
- 통합 워크플로우: 4.5시간 → 1초 (**99.99% 단축**) ✅
- **주당 평균 17시간 이상 절약** (평균 94.5% 절약률)

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

## 📞 문의

**교육 담당**: 여기어때컴퍼니 기술기획팀 크림슨  
**교육 일정**: 2024년 11월 말 ~ 12월 초  
**교육 장소**: 오프라인 (여기어때 사옥 또는 별도 장소)  
**해커톤 일정**: 2024년 12월 11일 (목)

---

## 📝 라이선스

이 교육 자료는 여기어때컴퍼니의 내부 교육용으로 제작되었습니다.

---

## 🎊 감사의 말

이 워크숍을 통해 여러분이:
- ⏱️ 시간을 절약하고
- 📈 생산성을 높이고
- ✨ 더 창의적인 업무에 집중할 수 있기를

바랍니다!

**해커톤에서의 성공을 응원합니다!** 🚀

---

## 📂 주요 문서

- [`sessions/`](sessions/) - 세션별 실습 가이드 (Session 0-6) ⭐
- [`sessions/data/`](sessions/data/) - 실습용 샘플 데이터
- [`samples/`](samples/) - 추가 샘플 파일

---

**버전**: v2.1  
**최종 업데이트**: 2024년 11월 13일  
**작성**: GitHub Copilot Workshop Team
