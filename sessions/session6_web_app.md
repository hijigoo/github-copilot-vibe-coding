# Session 6: 인터랙티브 웹 페이지 만들기
## ⏰ 소요 시간: 30분 (2:50 – 3:20)

---

## 🎯 학습 목표

이 세션을 마치면:
- HTML 파일 하나로 작동하는 웹 페이지 만들기
- 할 일 추가/삭제 기능 체험
- 성취감: "내가 웹 페이지를 만들었어!"

---

## 📖 HTML이란?

**쉽게 말하면**: 웹 페이지를 만드는 언어입니다.
- 모든 웹사이트는 HTML로 만들어집니다
- 파일 하나만 있으면 브라우저에서 바로 실행
- 서버 없이도 작동합니다

**왜 배우나요?**
- 간단한 웹 페이지를 직접 만들 수 있습니다
- 팀 내부 도구를 빠르게 만들 수 있습니다
- 브라우저만 있으면 어디서든 사용 가능

---

## 📚 시나리오

팀의 **일일 할 일 관리 웹 페이지**를 만들어봅니다.
- 할 일 추가/삭제 기능
- HTML 파일 하나로 완성
- 브라우저에서 더블클릭만 하면 실행

---

## 💪 Step 1: 새 파일 만들기 (2분)

### VS Code에서 새 파일 생성

1. VS Code에서 `File` → `New File` 클릭
2. 파일 이름: `todo.html`
3. 저장 위치: 바탕화면 또는 편한 곳

**그게 끝입니다!** 이제 이 파일에 코드를 넣으면 됩니다.

---

## 💬 Step 2: Copilot에게 웹 페이지 만들어달라고 요청하기 (10분)

**Copilot Chat 열기**: `Cmd+I` (Mac) / `Ctrl+I` (Windows)

**Copilot에게 이렇게 요청하세요**:
```
할 일 관리 웹 페이지를 HTML 파일 하나로 만들어줘:

기능:
- 할 일 입력창과 추가 버튼
- 할 일 목록 표시
- 각 할 일마다 삭제 버튼
- 체크박스로 완료 표시 가능

디자인:
- 모던하고 깔끔한 디자인
- 파란색 계열 그라데이션 배경
- 카드 스타일 레이아웃
- 모바일에서도 예쁘게 보이도록

기술:
- HTML + CSS + JavaScript를 모두 하나의 파일에
- 브라우저에서 바로 실행 가능하도록
- 데이터는 브라우저 로컬 저장소에 저장

파일 이름: todo.html
```

Copilot Agent가 자동으로 HTML 코드를 생성하고 파일에 저장합니다.

---

## ✅ Step 3: 웹 페이지 실행하기 (3분)

**실행은 매우 간단합니다!**

1. `todo.html` 파일을 찾습니다
2. 파일을 **더블클릭**합니다
3. 브라우저가 열리면서 웹 페이지가 나타납니다!

**또는**:
- 파일 우클릭 → "연결 프로그램" → Chrome 선택
- Chrome을 먼저 열고 파일을 드래그앤드롭

**중요**: 서버 설치나 실행 필요 없습니다!

---

## 🎨 Step 4: 기능 테스트 (5분)

**테스트 시나리오**:

1. **할 일 추가하기**
   - 입력창에 "Copilot 실습 완료하기" 입력
   - "추가" 버튼 클릭
   - 목록에 추가되는지 확인

2. **여러 개 추가하기**
   - "점심 먹기", "회의 참석하기", "보고서 작성하기" 추가
   - 모두 목록에 보이는지 확인

3. **체크박스로 완료 표시**
   - 체크박스 클릭
   - 취소선이 그어지는지 확인

4. **삭제하기**
   - "삭제" 버튼 클릭
   - 항목이 사라지는지 확인

5. **새로고침 테스트**
   - 브라우저 새로고침 (F5 또는 Cmd+R)
   - 할 일이 그대로 남아있는지 확인

**브라우저 로컬 저장소에 저장되어 새로고침해도 유지됩니다!**

---

## 🎨 도전 과제 (선택사항)

시간이 남으면 다음 기능을 추가해보세요:

**도전 1: 색상 테마 변경**
```
todo.html의 색상 테마를 초록색 계열로 변경해줘
```

**도전 2: 우선순위 추가**
```
할 일에 우선순위를 추가해줘 (높음/중간/낮음)
우선순위에 따라 색상 다르게 표시
```

**도전 3: 마감일 추가**
```
각 할 일에 마감일을 추가해줘
마감일이 지나면 빨간색으로 표시
```

---

## 💡 HTML 웹 페이지의 장점

**장점**:
- 파일 하나만 있으면 실행 가능
- 서버 필요 없음
- 설치 필요 없음
- 친구에게 파일 보내면 바로 사용 가능
- 이메일 첨부 가능

**제한사항**:
- 혼자만 사용 가능 (파일 전송 필요)
- 데이터가 브라우저에만 저장됨
- 컴퓨터를 바꾸면 데이터 사라짐
- 여러 사람이 동시에 사용 불가

**실무 활용**:
- 개인 도구: 할 일 관리, 메모장, 계산기
- 프로토타입 제작: 아이디어 빠르게 시연
- 팀 내부 도구: 파일 공유해서 사용

---

## 🔧 문제 해결

**문제 1: 파일이 브라우저에서 열리지 않아요**
- 파일 이름이 `todo.html`로 끝나는지 확인
- 우클릭 → "연결 프로그램" → Chrome 선택

**문제 2: 새로고침하면 데이터가 사라져요**
- 정상입니다! 코드에 로컬 저장소 기능이 있으면 유지됩니다
- Copilot에게 "로컬 저장소에 데이터 저장하는 기능 추가해줘" 요청

**문제 3: 한글이 깨져 보여요**
- 파일 저장 시 UTF-8 인코딩으로 저장
- VS Code 하단에 "UTF-8" 표시 확인

---

## 🎓 배운 내용 정리

**기술적 개념**:
- **HTML**: 웹 페이지의 구조
- **CSS**: 웹 페이지 디자인
- **JavaScript**: 웹 페이지 동작
- **로컬 저장소**: 브라우저에 데이터 저장

**실무 활용**:
- 간단한 웹 도구 만들기
- 프로토타입 빠르게 제작
- 팀 내부 유틸리티

---

## 🚀 다음 단계

**더 배우고 싶다면**:
- HTML/CSS 기초: w3schools.com
- JavaScript 기초
- Bootstrap 프레임워크

**실전 프로젝트 아이디어**:
- 간단한 메모장
- 설문조사 폼
- 색상 팔레트 도구
- 미니 달력

---

## 🎉 축하합니다!

**여러분은 방금 웹 페이지를 만들었습니다!**

30분 전만 해도 상상도 못했던 일이죠?
- HTML 파일 하나로 작동하는 웹 페이지
- 예쁜 디자인
- 실제로 작동하는 기능 (추가, 삭제, 완료 체크)
- 데이터 저장 기능

**이것이 바로 Copilot의 힘입니다!**

---

## ❓ 자주 묻는 질문

**Q: 이 파일을 다른 사람에게 보낼 수 있나요?**
A: 네! 파일을 보내면 그 사람도 브라우저에서 바로 사용할 수 있습니다.

**Q: 데이터는 어디에 저장되나요?**
A: 브라우저의 로컬 저장소에 저장됩니다. 새로고침해도 유지되지만 다른 컴퓨터에서는 안 보입니다.

**Q: 더 복잡한 기능을 추가할 수 있나요?**
A: 물론입니다! Copilot에게 요청하세요 (검색, 필터링, 카테고리, 마감일 등).

**Q: 스마트폰에서도 사용할 수 있나요?**
A: 네! 파일을 스마트폰으로 보내서 브라우저로 열면 됩니다.

---

**다음**: [Session 7: 업무 자동화 →](session7_automation.md)

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
            font-family: 'Segoe UI', 'Malgun Gothic', sans-serif;
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
            align-items: center;
            gap: 10px;
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
        
        .todo-item.completed .todo-text {
            text-decoration: line-through;
            color: #999;
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

        input[type="checkbox"] {
            width: 20px;
            height: 20px;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>✨ 오늘의 할 일</h1>
        
        <div class="add-form">
            <input type="text" id="todoInput" placeholder="할 일을 입력하세요..." />
            <button onclick="addTodo()">추가</button>
        </div>
        
        <ul class="todo-list" id="todoList"></ul>
        
        <div class="count" id="count"></div>
    </div>

    <script>
        // 브라우저 로컬 저장소에서 할 일 불러오기
        function loadTodos() {
            const todos = JSON.parse(localStorage.getItem('todos') || '[]');
            renderTodos(todos);
        }

        // 할 일 목록 화면에 표시
        function renderTodos(todos) {
            const todoList = document.getElementById('todoList');
            const count = document.getElementById('count');
            
            if (todos.length === 0) {
                todoList.innerHTML = '<div class="empty-state">할 일을 추가해보세요! 🎯</div>';
                count.textContent = '';
                return;
            }
            
            todoList.innerHTML = todos.map((todo, index) => `
                <li class="todo-item ${todo.completed ? 'completed' : ''}">
                    <input type="checkbox" 
                           ${todo.completed ? 'checked' : ''} 
                           onchange="toggleTodo(${index})" />
                    <span class="todo-text">${todo.text}</span>
                    <button class="delete-btn" onclick="deleteTodo(${index})">삭제</button>
                </li>
            `).join('');
            
            count.textContent = `총 ${todos.length}개의 할 일`;
        }

        // 할 일 추가
        function addTodo() {
            const input = document.getElementById('todoInput');
            const text = input.value.trim();
            
            if (!text) {
                alert('할 일을 입력해주세요!');
                return;
            }
            
            const todos = JSON.parse(localStorage.getItem('todos') || '[]');
            todos.push({ text: text, completed: false });
            localStorage.setItem('todos', JSON.stringify(todos));
            
            input.value = '';
            renderTodos(todos);
        }

        // 할 일 완료/미완료 토글
        function toggleTodo(index) {
            const todos = JSON.parse(localStorage.getItem('todos') || '[]');
            todos[index].completed = !todos[index].completed;
            localStorage.setItem('todos', JSON.stringify(todos));
            renderTodos(todos);
        }

        // 할 일 삭제
        function deleteTodo(index) {
            const todos = JSON.parse(localStorage.getItem('todos') || '[]');
            todos.splice(index, 1);
            localStorage.setItem('todos', JSON.stringify(todos));
            renderTodos(todos);
        }

        // Enter 키로 추가
        document.getElementById('todoInput').addEventListener('keypress', function(e) {
            if (e.key === 'Enter') {
                addTodo();
            }
        });

        // 페이지 로드 시 할 일 불러오기
        loadTodos();
    </script>
</body>
</html>
```

</details>

**💡 이 코드의 특징**:
- HTML, CSS, JavaScript가 모두 하나의 파일에
- 브라우저 로컬 저장소에 데이터 저장 (새로고침해도 유지됨)
- 체크박스로 완료 표시 가능
- 모바일에서도 예쁘게 보임

---

## Step 3: 웹 페이지 실행하기! (3분)

### 실행 방법

**매우 간단합니다!**

1. `todo.html` 파일을 찾습니다
2. 파일을 **더블클릭**합니다
3. 🎉 **브라우저가 열리면서 여러분의 웹 페이지가 나타납니다!**

또는:

1. `todo.html` 파일을 우클릭
2. "연결 프로그램" → "Chrome" (또는 Safari, Edge 등) 선택
3. 🎉 **완료!**

**💡 Tip**: 
- 서버가 필요 없습니다!
- 파일만 있으면 언제든지 실행 가능
- 친구에게 파일을 보내면 친구도 사용 가능
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

### 강사가 실행 방법을 보여드립니다

**걱정하지 마세요!** 
- 강사가 화면을 공유하며 보여드립니다
- 명령어 하나만 입력하면 됩니다
- 에러가 나면 강사가 즉시 해결해드립니다

### 예상 결과

화면에 다음과 같은 메시지가 나오면 **성공**입니다:
```
 * Running on http://127.0.0.1:5000
```

### 브라우저에서 확인하기

**강사가 안내하는 순서**:
1. 크롬이나 사파리를 엽니다
2. 주소창에 `localhost:5000` 입력
3. 🎉 **여러분이 만든 웹 페이지가 나타납니다!**

**💡 Tip**: `localhost:5000`은 "내 컴퓨터의 5000번 주소"라는 뜻입니다

---

## Step 4: 기능 테스트 (5분)

### 테스트 시나리오

**강사와 함께 하나씩 테스트해봅니다**:

1. **할 일 추가하기**
   - 입력창에 "Copilot 실습 완료하기" 입력
   - "추가" 버튼 클릭
   - ✅ 목록에 추가되었나요?

2. **여러 개 추가하기**
   - "점심 먹기" 추가
   - "회의 참석하기" 추가
   - "보고서 작성하기" 추가
   - ✅ 모두 목록에 보이나요?

3. **체크박스로 완료 표시**
   - 체크박스를 클릭
   - ✅ 취소선이 그어지나요?

4. **삭제하기**
   - 아무 항목의 "삭제" 버튼 클릭
   - ✅ 사라졌나요?

5. **새로고침 테스트**
   - 브라우저 새로고침 (F5 또는 Cmd+R)
   - ✅ 할 일이 그대로 남아있나요?

**💡 Tip**: 브라우저 로컬 저장소에 저장되어 새로고침해도 유지됩니다!

---

## 🎨 도전 과제 (추가 시간이 있다면)

### 도전 1: 색상 테마 변경

**프롬프트**:
```
todo.html의 색상 테마를 초록색 계열로 변경해줘:
- 배경 그라데이션을 초록색으로
- 버튼 색상도 초록색으로
- 전체적으로 통일감 있게
```

### 도전 2: 할 일 우선순위 추가

**프롬프트**:
```
할 일에 우선순위를 추가해줘:
- 추가할 때 높음/중간/낮음 선택 가능
- 우선순위에 따라 색상 다르게 표시 (빨강/노랑/파랑)
- 우선순위 높은 것부터 위에 표시
```

### 도전 3: 마감일 추가

**프롬프트**:
```
각 할 일에 마감일을 추가해줘:
- 날짜 선택 가능
- 마감일이 지나면 빨간색으로 표시
- 마감일 순으로 정렬 옵션
```

---

## 💡 HTML 웹 페이지의 장점

### ✅ 이런 점이 좋아요
- 파일 하나만 있으면 실행 가능
- 서버 필요 없음
- 설치 필요 없음
- 친구에게 파일 보내면 바로 사용 가능
- 이메일 첨부 가능

### ⚠️ 제한사항
- 혼자만 사용 가능 (공유하려면 파일 전송 필요)
- 데이터가 브라우저에만 저장됨
- 컴퓨터를 바꾸면 데이터 사라짐
- 여러 사람이 동시에 사용 불가

### 💡 실무 활용 팁
- 개인 도구로 사용: 할 일 관리, 메모장, 계산기
- 프로토타입 제작: 아이디어 빠르게 시연
- 팀 내부 도구: 파일 공유해서 사용

---

## 🔧 문제 해결

### 문제 1: 파일이 브라우저에서 열리지 않아요
**해결방법**:
- 파일 이름이 `todo.html`로 끝나는지 확인
- 우클릭 → "연결 프로그램" → Chrome 선택
- 또는 Chrome을 먼저 열고 파일을 드래그앤드롭

### 문제 2: 새로고침하면 데이터가 사라져요
**해결방법**:
- 정상입니다! 코드에 로컬 저장소 기능이 포함되어 있으면 유지됩니다
- 코드를 다시 확인하고 `localStorage` 부분이 있는지 확인
- 없으면 Copilot에게 "로컬 저장소에 데이터 저장하는 기능 추가해줘" 요청

### 문제 3: 한글이 깨져 보여요
**해결방법**:
- 파일 저장 시 UTF-8 인코딩으로 저장
- VS Code 하단에 "UTF-8" 표시 확인
- 없으면 "UTF-8"을 클릭해서 인코딩 변경

---

## 🎓 배운 내용 정리

### 기술적 개념
- ✅ **HTML**: 웹 페이지의 구조를 만드는 언어
- ✅ **CSS**: 웹 페이지를 예쁘게 꾸미는 언어
- ✅ **JavaScript**: 웹 페이지에 동작을 추가하는 언어
- ✅ **로컬 저장소**: 브라우저에 데이터를 저장하는 기능

### 실무 활용
- 간단한 웹 도구 만들기
- 프로토타입 빠르게 제작
- 팀 내부 유틸리티
- 아이디어 시연

---

## 🚀 다음 단계

### 더 배우고 싶다면
1. **HTML/CSS 기초**: w3schools.com에서 무료 학습
2. **JavaScript 기초**: 인터랙티브한 기능 더 추가하기
3. **Bootstrap**: 더 예쁜 디자인 프레임워크
4. **웹 서버**: 다른 사람과 공유하고 싶다면 배포 학습

### 실전 프로젝트 아이디어
- � 간단한 메모장
- � 설문조사 폼
- 🎨 색상 팔레트 도구
- � 미니 달력

---

## 🎉 축하합니다!

**여러분은 방금 인터랙티브 웹 페이지를 만들었습니다!** 🎊

30분 전만 해도 상상도 못했던 일이죠?
- ✨ HTML 파일 하나로 작동하는 웹 페이지
- 🎨 예쁜 디자인
- ⚙️ 실제로 작동하는 기능 (추가, 삭제, 완료 체크)
- 💾 데이터 저장 기능

**이것이 바로 Copilot의 힘입니다!**

---

## 📝 자주 묻는 질문

### Q: 이 파일을 다른 사람에게 보낼 수 있나요?
**A**: 네! 파일을 보내면 그 사람도 브라우저에서 바로 사용할 수 있습니다.
- 이메일 첨부
- 카카오톡/슬랙으로 전송
- USB에 담아서 전달

### Q: 데이터는 어디에 저장되나요?
**A**: 브라우저의 로컬 저장소에 저장됩니다.
- 새로고침해도 유지됩니다
- 하지만 다른 컴퓨터에서는 안 보입니다
- 브라우저 데이터를 지우면 사라집니다

### Q: 더 복잡한 기능을 추가할 수 있나요?
**A**: 물론입니다! Copilot에게 물어보세요:
- 검색 기능
- 필터링 (완료된 것만 보기)
- 카테고리 분류
- 마감일 알림

### Q: 스마트폰에서도 사용할 수 있나요?
**A**: 네! 파일을 스마트폰으로 보내서 브라우저로 열면 됩니다.
반응형 디자인이라 모바일에서도 예쁘게 보입니다.

---

**다음 세션**: [Session 7: 업무 자동화](session7_automation.md) →

지금까지 배운 기술로 실제 업무를 자동화해봅시다!
