# Session 0: 환경 세팅 & Hello Copilot
## ⏰ 소요 시간: 25분 (0:00 – 0:25)

---

## 🎯 학습 목표

이 세션을 마치면 다음을 할 수 있습니다:
- ✅ GitHub Copilot이 활성화된 VS Code 환경 구축
- ✅ Copilot Chat과 Inline Suggestions의 차이 이해
- ✅ 첫 프롬프트를 작성하여 간단한 문서 생성

---

## 📋 사전 체크리스트

시작하기 전에 다음 항목을 확인하세요:

- [ ] 노트북 (macOS 또는 Windows)
- [ ] GitHub 계정 (없다면 [github.com](https://github.com)에서 생성)
- [ ] 인터넷 연결
- [ ] VS Code 설치 (없다면 아래 설치 가이드 참조)

---

## 🔧 Step 1: VS Code 설치하기 (5분)

### macOS 사용자

1. [Visual Studio Code 다운로드](https://code.visualstudio.com/Download)
2. 다운로드한 `.zip` 파일 압축 해제
3. `Visual Studio Code.app`을 `Applications` 폴더로 이동
4. Spotlight 검색 (⌘ + Space)에서 "Visual Studio Code" 입력하여 실행

### Windows 사용자

1. [Visual Studio Code 다운로드](https://code.visualstudio.com/Download)
2. 다운로드한 `.exe` 파일 실행
3. 설치 마법사 따라 진행 (기본 설정 권장)
4. 설치 완료 후 VS Code 실행

---

## 🚀 Step 2: GitHub Copilot 확장 설치하기 (5분)

1. **VS Code 열기**
2. **확장(Extensions) 패널 열기**
   - 단축키: `⌘ + Shift + X` (macOS) / `Ctrl + Shift + X` (Windows)
   - 또는 왼쪽 사이드바에서 블록 아이콘 클릭

3. **GitHub Copilot 검색 및 설치**
   ```
   검색창에 "GitHub Copilot" 입력
   → "GitHub Copilot" (by GitHub) 찾기
   → "Install" 버튼 클릭
   ```

4. **GitHub Copilot Chat 설치**
   ```
   검색창에 "GitHub Copilot Chat" 입력
   → "GitHub Copilot Chat" (by GitHub) 찾기
   → "Install" 버튼 클릭
   ```

5. **로그인 요청 확인**
   - 설치 후 "Sign in to use GitHub Copilot" 알림 표시
   - "Sign In to GitHub" 버튼 클릭
   - 브라우저에서 GitHub 계정 로그인
   - 권한 승인 (Authorize)

---

## ✅ Step 3: Copilot 활성화 확인하기 (2분)

### 상태 바 확인
- VS Code 오른쪽 하단에 **Copilot 아이콘** 표시 확인
- 아이콘 색상:
  - 🟢 **초록색**: 정상 활성화
  - 🔴 **빨간색**: 비활성화 또는 오류

### Copilot Chat 패널 열기
1. 단축키: `⌘ + Shift + I` (macOS) / `Ctrl + Shift + I` (Windows)
2. 또는 왼쪽 사이드바에서 **Chat 아이콘** 클릭
3. Chat 창이 열리면 "Hello, Copilot!" 입력하여 응답 확인

---

## 🎓 Step 4: Copilot Chat vs Inline Suggestions 이해하기 (5분)

### 1. Copilot Chat (대화형 도우미)
**특징**:
- 자연어로 질문하고 대화
- 긴 설명이나 코드 생성
- 파일 전체를 분석하고 제안

**사용 시나리오**:
- "이 회의록을 요약해줘"
- "PRD 문서 템플릿 만들어줘"
- "이 데이터를 분석하고 인사이트 도출해줘"

**실습**: Chat 패널에서 다음 입력해보기
```
"안녕하세요! GitHub Copilot이 뭐예요?"
```

---

### 2. Inline Suggestions (코드 작성 중 자동완성)
**특징**:
- 타이핑하면 자동으로 제안 표시
- Tab 키로 수락
- 짧은 코드나 텍스트 완성

**사용 시나리오**:
- 주석 작성 후 코드 자동 완성
- 반복적인 패턴 빠르게 작성

**실습**: 
1. 새 파일 만들기 (`⌘ + N` / `Ctrl + N`)
2. 파일 형식을 Markdown으로 설정 (`⌘ + K, M` → "markdown" 입력)
3. 다음 텍스트 입력 후 Enter:
   ```
   # 오늘의 회의 주제:
   ```
4. Copilot이 자동으로 제안하는 내용 확인
5. `Tab` 키로 수락 또는 `Esc`로 무시

---

## 💪 Step 5: 첫 프롬프트 실습하기 (8분)

### 미션: 회의 메모를 Markdown 문서로 요약하기

#### 시나리오
여러분은 방금 팀 회의를 마쳤습니다. 메모한 내용을 정리하여 팀원들과 공유해야 합니다.

#### 샘플 회의 메모 (복사해서 사용)
```
2024년 11월 13일 신규 숙박 검색 기능 개선 회의

참석자: 김민수(PO), 이지혜(UX), 박준형(개발), 최수진(마케터)

논의 내용:
- 사용자들이 지역 검색할 때 자동완성이 너무 느림
- 모바일에서 필터 버튼 위치가 불편하다는 피드백 다수
- 경쟁사 대비 검색 속도 3초 더 걸림
- 다음 스프린트에 검색 성능 개선 우선 반영
- UX팀에서 필터 UI 재설계안 다음주 금요일까지 제출
- 마케팅팀은 개선 후 프로모션 계획 수립

다음 회의: 11월 20일 오전 10시
```

---

### 실습 단계

#### 1단계: 새 파일 만들기
```
⌘ + N (macOS) / Ctrl + N (Windows)
```

#### 2단계: Copilot Chat 열기
```
⌘ + Shift + I (macOS) / Ctrl + Shift + I (Windows)
```

#### 3단계: Chat에 프롬프트 입력
```
위의 회의 메모를 아래 형식으로 정리해줘:

1. 회의 정보 (날짜, 참석자)
2. 주요 논의 사항 (bullet points)
3. 결정 사항
4. 액션 아이템 (담당자, 마감일)

Markdown 형식으로 작성해줘.
```

#### 4단계: 결과를 파일에 복사
- Copilot이 생성한 내용을 복사 (Copy 버튼 클릭)
- 새 파일에 붙여넣기

#### 5단계: 파일 저장
```
⌘ + S (macOS) / Ctrl + S (Windows)
파일명: hello_copilot.md
```

---

## 🎯 예상 결과물 예시

```markdown
# 신규 숙박 검색 기능 개선 회의

## 📅 회의 정보
- **날짜**: 2024년 11월 13일
- **참석자**: 김민수(PO), 이지혜(UX), 박준형(개발), 최수진(마케터)

## 💬 주요 논의 사항
- 지역 검색 시 자동완성 속도 저하 문제
- 모바일 필터 버튼 위치 사용성 이슈
- 경쟁사 대비 검색 속도 3초 지연
- 사용자 피드백 기반 우선순위 조정 필요

## ✅ 결정 사항
- 다음 스프린트에 검색 성능 개선 최우선 반영
- 필터 UI 재설계 진행

## 📋 액션 아이템
| 담당자 | 작업 내용 | 마감일 |
|--------|-----------|--------|
| 박준형 | 검색 성능 개선 개발 | 다음 스프린트 종료 |
| 이지혜 | 필터 UI 재설계안 제출 | 11월 20일 (금) |
| 최수진 | 개선 후 프로모션 계획 수립 | TBD |

## 🔄 다음 회의
- **일정**: 11월 20일 (수) 오전 10시
```

---

## 🎉 축하합니다!

첫 번째 세션을 완료했습니다! 이제 여러분은:
- ✅ GitHub Copilot을 실무에 사용할 준비가 되었습니다
- ✅ Chat과 Inline의 차이를 이해했습니다
- ✅ 첫 문서를 Copilot으로 생성했습니다

---

## 🔍 자주 묻는 질문 (FAQ)

### Q1: Copilot이 응답하지 않아요
**A**: 다음을 확인하세요:
- 인터넷 연결 상태
- GitHub 로그인 상태 (오른쪽 하단 아이콘)
- Copilot 라이선스 활성화 여부

### Q2: Inline Suggestions가 보이지 않아요
**A**: 설정 확인:
1. `⌘ + ,` (설정 열기)
2. "copilot" 검색
3. "Editor: Inline Suggest" → "Enabled" 체크

### Q3: 한글로 프롬프트를 써도 되나요?
**A**: 네! Copilot은 한글을 완벽하게 이해합니다. 편한 언어로 작성하세요.

---

## 📚 다음 세션 미리보기

**Session 1: 회의록 자동 정리**에서는:
- 실제 회의록에서 Action Item 자동 추출
- 담당자별 작업 테이블 생성
- 회의록 템플릿 만들기

준비물: 없음 (바로 시작 가능)

---

## 💡 팁: 처음 사용자를 위한 프롬프트 작성 가이드

**좋은 프롬프트**:
- ✅ "이 회의록을 Markdown 표로 정리해줘"
- ✅ "주요 결정 사항 3가지만 뽑아줘"
- ✅ "공식 문서 톤으로 다시 작성해줘"

**개선이 필요한 프롬프트**:
- ❌ "정리해줘" (무엇을 정리할지 불명확)
- ❌ "좀 바꿔줘" (어떻게 바꿀지 구체적이지 않음)

**핵심**: 구체적이고 명확하게!

---

**다음**: [Session 1: 회의록 자동 정리 →](session1_meeting_notes.md)
