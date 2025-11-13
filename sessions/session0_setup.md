# Session 0: 환경 세팅
## ⏰ 소요 시간: 25분

> 💡 **설치 후 바로 사용하고 싶으신가요?**  
> 이 세션이 끝나면 **[빠른 시작 가이드](session0.5_quick_start.md)**로 이동하세요!

---

## 🎯 학습 목표

이 세션을 마치면:
- ✅ VS Code 설치 완료
- ✅ GitHub Copilot 확장 설치 완료
- ✅ Python 환경 구축 완료
- ✅ 실습 준비 완료

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
1. 단축키: `⌘ + I` (macOS) / `Ctrl + I` (Windows)
2. 또는 왼쪽 사이드바에서 **Chat 아이콘** 클릭
3. Chat 창이 열리면 "Hello, Copilot!" 입력하여 응답 확인

---

## 🐍 Step 4: Python 설치하기 (5분)

### macOS 사용자
```bash
# Homebrew로 설치 (권장)
brew install python

# 설치 확인
python3 --version
# 출력 예: Python 3.11.x
```

### Windows 사용자
1. [Python 공식 사이트](https://www.python.org/downloads/) 방문
2. "Download Python" 버튼 클릭
3. 설치 프로그램 실행
4. **중요**: "Add Python to PATH" 체크박스 반드시 선택!
5. "Install Now" 클릭

### 설치 확인
터미널(또는 Command Prompt)에서:
```bash
python --version
# 또는
python3 --version
```

---

## 📦 Step 5: 가상환경 설정하기 (8분)

### 가상환경이란?
- 프로젝트마다 독립적인 Python 환경
- 패키지 충돌 방지
- 시스템 Python을 건드리지 않음

### 가상환경 생성

1. **터미널 열기**: VS Code에서 `` ⌘+` `` (macOS) 또는 ``Ctrl+` `` (Windows)

2. **프로젝트 폴더로 이동**:
```bash
# 다운로드 받은 프로젝트 폴더로 이동
cd /path/to/workshop
```

3. **가상환경 생성**:
```bash
# Python 3으로 .venv 폴더 생성
python3 -m venv .venv
```

### 가상환경 활성화

**macOS/Linux**:
```bash
source .venv/bin/activate
```

**Windows (PowerShell)**:
```powershell
.venv\Scripts\Activate.ps1
```

**Windows (CMD)**:
```cmd
.venv\Scripts\activate.bat
```

### ✅ 활성화 확인
터미널 프롬프트 앞에 `(.venv)`가 표시되면 성공!
```bash
(.venv) username@computer:~/workshop$
```

---

## 📚 Step 6: 필수 패키지 설치하기 (5분)

가상환경이 활성화된 상태에서:

```bash
# pandas: 데이터 분석
# matplotlib: 데이터 시각화
# flask: 웹 애플리케이션
pip install pandas matplotlib flask
```

### 설치 확인
```bash
pip list
```

다음 패키지들이 보이면 성공:
- pandas
- matplotlib  
- flask

---

## 🎉 축하합니다!

환경 설정을 완료했습니다! 이제 여러분은:
- ✅ VS Code 준비 완료
- ✅ GitHub Copilot 사용 가능
- ✅ Python 환경 구축 완료
- ✅ 모든 실습 준비 완료

---

## 🚀 다음 단계

### 바로 시작하고 싶으신가요?
👉 **[Session 1: 빠른 시작 가이드](session1_quick_start.md)** - 10분이면 Copilot 사용법 마스터!

### 본격적인 실습 시작
👉 **[Session 2: 회의록 자동 정리](session2_meeting_notes.md)** - 30분 작업을 5분으로!

---

## 🔍 자주 묻는 질문

### Q: Python 버전이 낮은데 괜찮나요?
**A**: Python 3.8 이상이면 모든 실습이 가능합니다.

### Q: 가상환경을 꼭 사용해야 하나요?
**A**: 네! 가상환경을 사용하면:
- 시스템 Python을 보호
- 패키지 버전 충돌 방지
- 프로젝트 독립성 유지

### Q: 가상환경 활성화를 잊어버렸어요
**A**: 터미널 앞에 `(.venv)`가 없으면 비활성화된 것입니다.  
Step 5의 활성화 명령어를 다시 실행하세요.

### Q: pip install이 실패해요
**A**: 다음을 시도해보세요:
```bash
# Python 버전 명시
python3 -m pip install pandas matplotlib flask

# 또는 업그레이드 후 재시도
pip install --upgrade pip
pip install pandas matplotlib flask
```

### Q: Windows에서 PowerShell 실행 정책 에러가 나요
**A**: PowerShell을 관리자 권한으로 열고:
```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```

---

## 💡 유용한 명령어

### 가상환경 관련
```bash
# 가상환경 비활성화
deactivate

# 가상환경 다시 활성화
source .venv/bin/activate  # macOS/Linux
.venv\Scripts\activate     # Windows

# 설치된 패키지 목록
pip list

# 특정 패키지 설치 여부 확인
pip show pandas
```

### VS Code 터미널
```bash
# 새 터미널 열기: Ctrl+Shift+`
# 터미널 전환: Ctrl+`
# 터미널 닫기: 터미널 패널에서 휴지통 아이콘
```

---

**다음**: [Session 1: 빠른 시작 가이드](session1_quick_start.md) 또는 [Session 2: 회의록 정리](session2_meeting_notes.md) →
