# Session 6: 간단한 웹 애플리케이션 만들기
## ⏰ 소요 시간: 30분 (2:50 – 3:20)

## 🎯 학습 목표
- Flask로 간단한 웹 서버 만들기
- HTML 페이지 생성
- 실시간으로 작동하는 웹 애플리케이션 경험
- **성취감**: "내가 웹 개발자가 될 수 있구나!" 💪

---

## 📚 시나리오

여러분은 팀의 **일일 할 일 관리 웹 페이지**를 만들고 싶습니다.
- 할 일을 추가/삭제할 수 있는 간단한 페이지
- 팀원들이 브라우저에서 바로 사용
- 예쁜 디자인으로 사용하기 편하게!

**Copilot과 함께라면 30분 만에 가능합니다!** 🚀

---

## Step 1: 프로젝트 폴더 생성 (2분)

### 폴더 구조 만들기
```bash
# 가상환경이 활성화되어 있는지 확인
# 터미널에 (.venv)가 보여야 합니다

# 프로젝트 폴더 생성
mkdir todo-app
cd todo-app

# 필요한 폴더 생성
mkdir templates
mkdir static
```

**폴더 구조**:
```
todo-app/
├── app.py           # Flask 서버 (곧 만들 예정)
├── templates/       # HTML 파일
│   └── index.html   # 메인 페이지
└── static/          # CSS, 이미지 등
    └── style.css    # 스타일 파일
```

---

## Step 2: Flask 앱 만들기 (10분)

### VS Code에서 새 파일 생성

1. `todo-app/app.py` 파일 생성
2. Copilot Chat 열기 (`⌘+I` 또는 `Ctrl+I`)

### 프롬프트 1: 기본 Flask 앱 생성

```
Flask로 간단한 할 일 관리 웹 앱을 만들어줘:
- 할 일을 추가할 수 있어야 함
- 할 일을 삭제할 수 있어야 함
- 할 일 목록을 보여줘야 함
- 데이터는 메모리에 저장 (간단하게)
- 포트 5000에서 실행
```

### 예상 결과:

<details>
<summary>app.py (클릭하여 펼치기)</summary>

```python
from flask import Flask, render_template, request, redirect, url_for

app = Flask(__name__)

# 할 일 목록 (메모리에 저장)
todos = []

@app.route('/')
def index():
    return render_template('index.html', todos=todos)

@app.route('/add', methods=['POST'])
def add_todo():
    todo = request.form.get('todo')
    if todo:
        todos.append(todo)
    return redirect(url_for('index'))

@app.route('/delete/<int:index>')
def delete_todo(index):
    if 0 <= index < len(todos):
        todos.pop(index)
    return redirect(url_for('index'))

if __name__ == '__main__':
    app.run(debug=True, port=5000)
```

</details>

### ✅ 체크포인트
- `app.py` 파일에 코드가 생성되었나요?
- 에러 표시가 없나요?

---

## Step 3: HTML 페이지 만들기 (10분)

### 1. templates/index.html 파일 생성

### 프롬프트 2: 예쁜 HTML 페이지 만들기

```
할 일 관리 웹 페이지를 만들어줘:
- 깔끔하고 모던한 디자인
- 할 일 입력 폼
- 할 일 목록 표시
- 각 항목에 삭제 버튼
- 반응형 디자인 (모바일에서도 예쁘게)
- 색상은 파란색 계열로
- 완료된 항목은 체크할 수 있게
```

### 예상 결과:

<details>
<summary>templates/index.html (클릭하여 펼치기)</summary>

```html
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>할 일 관리</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 20px;
        }
        
        .container {
            background: white;
            padding: 40px;
            border-radius: 20px;
            box-shadow: 0 20px 60px rgba(0,0,0,0.3);
            max-width: 500px;
            width: 100%;
        }
        
        h1 {
            color: #667eea;
            margin-bottom: 30px;
            text-align: center;
            font-size: 32px;
        }
        
        .add-form {
            display: flex;
            gap: 10px;
            margin-bottom: 30px;
        }
        
        input[type="text"] {
            flex: 1;
            padding: 15px;
            border: 2px solid #e0e0e0;
            border-radius: 10px;
            font-size: 16px;
            transition: border 0.3s;
        }
        
        input[type="text"]:focus {
            outline: none;
            border-color: #667eea;
        }
        
        button {
            padding: 15px 30px;
            background: #667eea;
            color: white;
            border: none;
            border-radius: 10px;
            font-size: 16px;
            font-weight: bold;
            cursor: pointer;
            transition: background 0.3s;
        }
        
        button:hover {
            background: #5568d3;
        }
        
        .todo-list {
            list-style: none;
        }
        
        .todo-item {
            background: #f8f9fa;
            padding: 15px;
            margin-bottom: 10px;
            border-radius: 10px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            animation: slideIn 0.3s ease;
        }
        
        @keyframes slideIn {
            from {
                opacity: 0;
                transform: translateY(-10px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        .todo-text {
            flex: 1;
            font-size: 16px;
            color: #333;
        }
        
        .delete-btn {
            background: #ff6b6b;
            padding: 8px 15px;
            font-size: 14px;
        }
        
        .delete-btn:hover {
            background: #ee5a52;
        }
        
        .empty-state {
            text-align: center;
            color: #999;
            padding: 40px;
            font-size: 18px;
        }
        
        .count {
            text-align: center;
            color: #666;
            margin-top: 20px;
            font-size: 14px;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>✨ 오늘의 할 일</h1>
        
        <form class="add-form" action="/add" method="POST">
            <input type="text" name="todo" placeholder="할 일을 입력하세요..." required>
            <button type="submit">추가</button>
        </form>
        
        {% if todos %}
            <ul class="todo-list">
                {% for todo in todos %}
                    <li class="todo-item">
                        <span class="todo-text">{{ todo }}</span>
                        <a href="/delete/{{ loop.index0 }}">
                            <button type="button" class="delete-btn">삭제</button>
                        </a>
                    </li>
                {% endfor %}
            </ul>
            <div class="count">총 {{ todos|length }}개의 할 일</div>
        {% else %}
            <div class="empty-state">
                할 일을 추가해보세요! 🎯
            </div>
        {% endif %}
    </div>
</body>
</html>
```

</details>

---

## Step 4: 웹 앱 실행하기! (3분)

### 터미널에서 실행

```bash
# 가상환경이 활성화되어 있는지 확인
# (.venv)가 보여야 합니다

# Flask 앱 실행
python app.py
```

### 예상 출력:
```
 * Serving Flask app 'app'
 * Debug mode: on
 * Running on http://127.0.0.1:5000
```

### 브라우저에서 열기

1. 웹 브라우저 실행
2. 주소창에 입력: `http://localhost:5000`
3. 🎉 **여러분의 첫 웹 애플리케이션!**

---

## Step 5: 기능 테스트 (5분)

### 테스트 시나리오

1. **할 일 추가하기**
   - 입력창에 "Copilot 실습 완료하기" 입력
   - "추가" 버튼 클릭
   - ✅ 목록에 추가되었나요?

2. **여러 개 추가하기**
   - "점심 먹기" 추가
   - "회의 참석하기" 추가
   - "보고서 작성하기" 추가
   - ✅ 모두 목록에 보이나요?

3. **삭제하기**
   - 아무 항목의 "삭제" 버튼 클릭
   - ✅ 사라졌나요?

4. **개수 확인**
   - 하단에 "총 X개의 할 일" 표시
   - ✅ 개수가 정확한가요?

---

## 🎨 도전 과제 (추가 시간이 있다면)

### 도전 1: 완료 기능 추가

**프롬프트**:
```
할 일 완료 기능을 추가해줘:
- 각 항목에 체크박스 추가
- 체크하면 취소선 표시
- 완료된 항목은 회색으로 표시
```

### 도전 2: 우선순위 기능

**프롬프트**:
```
할 일에 우선순위를 추가해줘:
- 높음, 중간, 낮음 선택 가능
- 우선순위에 따라 색상 다르게 표시
- 우선순위 순으로 정렬
```

### 도전 3: 저장 기능

**프롬프트**:
```
할 일을 파일에 저장하는 기능을 추가해줘:
- JSON 파일로 저장
- 앱을 다시 시작해도 데이터 유지
- 자동 저장 기능
```

---

## 💡 프롬프트 작성 팁

### 좋은 프롬프트
✅ "할 일 추가 버튼을 더 크고 눈에 띄게 만들어줘"
✅ "완료된 항목은 연한 회색으로 표시하고 취소선을 그어줘"
✅ "모바일에서도 잘 보이게 반응형으로 만들어줘"

### 피해야 할 프롬프트
❌ "예쁘게 해줘" (너무 모호함)
❌ "더 좋게 만들어줘" (구체적이지 않음)
❌ "UI 개선" (무엇을 어떻게?)

---

## 🔧 트러블슈팅

### 문제 1: Flask를 찾을 수 없다는 에러
```
ModuleNotFoundError: No module named 'flask'
```

**해결방법**:
```bash
# 가상환경 활성화 확인
source .venv/bin/activate  # macOS/Linux
.venv\Scripts\activate     # Windows

# Flask 설치
pip install flask
```

### 문제 2: 포트가 이미 사용 중
```
Address already in use
```

**해결방법**:
```python
# app.py의 마지막 줄을 다음으로 변경
if __name__ == '__main__':
    app.run(debug=True, port=5001)  # 다른 포트 사용
```

### 문제 3: 템플릿을 찾을 수 없음
```
TemplateNotFound: index.html
```

**해결방법**:
- `templates` 폴더가 `app.py`와 같은 위치에 있는지 확인
- `index.html` 파일이 `templates` 폴더 안에 있는지 확인

---

## 📸 스크린샷 예시

### 초기 화면
```
┌─────────────────────────┐
│   ✨ 오늘의 할 일       │
│                          │
│  [_____________] [추가]  │
│                          │
│  할 일을 추가해보세요! 🎯 │
└─────────────────────────┘
```

### 할 일 추가 후
```
┌─────────────────────────┐
│   ✨ 오늘의 할 일       │
│                          │
│  [_____________] [추가]  │
│                          │
│  □ Copilot 실습 완료    │
│  □ 점심 먹기            │
│  □ 회의 참석하기        │
│                          │
│  총 3개의 할 일          │
└─────────────────────────┘
```

---

## 🎓 배운 내용 정리

### 기술적 개념
- ✅ **Flask**: Python 웹 프레임워크
- ✅ **라우팅**: URL과 함수 연결
- ✅ **템플릿**: HTML에 데이터 삽입
- ✅ **HTTP 메서드**: GET, POST
- ✅ **웹 서버**: 로컬 개발 서버

### 실무 활용
- 팀 내부 도구 만들기
- 간단한 대시보드 제작
- 데이터 입력 폼 생성
- 프로토타입 빠르게 만들기

---

## 🚀 다음 단계

### 더 배우고 싶다면
1. **Flask 공식 문서**: https://flask.palletsprojects.com/
2. **Flask Mega Tutorial**: 단계별 학습
3. **Bootstrap**: 더 예쁜 디자인
4. **데이터베이스**: SQLite, PostgreSQL 연동

### 실전 프로젝트 아이디어
- 📊 팀 설문조사 시스템
- 📝 간단한 블로그
- 🗓️ 일정 관리 시스템
- 📈 데이터 시각화 대시보드

---

## 🎉 축하합니다!

**여러분은 방금 웹 개발자가 되었습니다!** 🎊

30분 전만 해도 상상도 못했던 일이죠?
- ✨ 자신만의 웹 애플리케이션
- 🎨 예쁜 디자인
- ⚙️ 실제로 작동하는 기능
- 🌐 브라우저에서 실행

**이것이 바로 Copilot의 힘입니다!**

---

## 📝 자주 묻는 질문

### Q: 이 앱을 다른 사람도 사용할 수 있나요?
**A**: 현재는 로컬에서만 실행됩니다. 배포하려면:
- Heroku, Vercel 등 클라우드 플랫폼 사용
- 또는 회사 서버에 배포

### Q: 데이터를 영구 저장하려면?
**A**: 파일이나 데이터베이스를 사용해야 합니다:
- 간단한 방법: JSON 파일
- 전문적인 방법: SQLite, PostgreSQL

### Q: 더 복잡한 기능을 추가할 수 있나요?
**A**: 물론입니다! Copilot에게 물어보세요:
- 사용자 인증
- 파일 업로드
- 이메일 알림
- API 연동

### Q: 모바일 앱으로 만들 수 있나요?
**A**: 반응형 웹으로 모바일에서도 사용 가능합니다.
진짜 네이티브 앱은 React Native, Flutter 학습이 필요합니다.

---

**다음 세션**: Session 6 - 반복 작업 자동화 →

지금까지 배운 기술로 실제 업무를 자동화해봅시다!
