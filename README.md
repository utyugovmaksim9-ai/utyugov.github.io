# utyugov.github.io
!DOCTYPE html>
<html>
<head>
    <title>My Project</title>
    <link rel="stylesheet" href="style.css">
</head>
</body>
</html>
<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>NetTalk — Платформа для общения</title>
    <!-- Подключаем шрифт -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary-color: #4f46e5;
            --bg-color: #f3f4f6;
            --text-dark: #1f2937;
            --white: #ffffff;
            --border-color: #e5e7eb;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', sans-serif;
            background-color: var(--bg-color);
            color: var(--text-dark);
            height: 100vh;
            display: flex;
            flex-direction: column;
        }

        /* --- ШАПКА (HEADER) --- */
        header {
            background-color: var(--white);
            border-bottom: 1px solid var(--border-color);
            padding: 0.75rem 1.5rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
            position: sticky;
            top: 0;
            z-index: 100;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: 600;
            color: var(--primary-color);
            text-decoration: none;
        }

        .nav-links {
            display: flex;
            gap: 20px;
        }

        .nav-links a {
            text-decoration: none;
            color: var(--text-dark);
            font-weight: 400;
            transition: color 0.3s;
        }

        .nav-links a:hover {
            color: var(--primary-color);
        }

        .user-profile {
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .avatar {
            width: 35px;
            height: 35px;
            background-color: var(--primary-color);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 0.8rem;
        }

        /* --- ОСНОВНОЙ КОНТЕНТ (GRID) --- */
        .main-container {
            display: grid;
            grid-template-columns: 300px 1fr;
            flex-grow: 1;
            overflow: hidden;
        }

        /* Боковая панель (Контакты/Комнаты) */
        .sidebar {
            background-color: var(--white);
            border-right: 1px solid var(--border-color);
            overflow-y: auto;
            padding: 1rem;
        }

        .sidebar h2 {
            font-size: 1.1rem;
            margin-bottom: 1rem;
        }

        .chat-item {
            padding: 10px;
            border-radius: 8px;
            cursor: pointer;
            transition: background 0.2s;
            margin-bottom: 5px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .chat-item:hover {
            background-color: var(--bg-color);
        }

        .chat-item.active {
            background-color: #eef2ff;
            border-left: 4px solid var(--primary-color);
        }

        /* Окно общения */
        .chat-window {
            display: flex;
            flex-direction: column;
            background-color: var(--white);
        }

        .messages-area {
            flex-grow: 1;
            padding: 2rem;
            overflow-y: auto;
            display: flex;
            flex-direction: column;
            gap: 15px;
        }

        .message {
            max-width: 70%;
            padding: 12px 16px;
            border-radius: 15px;
            font-size: 0.95rem;
            line-height: 1.4;
        }

        .msg-received {
            background-color: var(--bg-color);
            align-self: flex-start;
            border-bottom-left-radius: 2px;
        }

        .msg-sent {
            background-color: var(--primary-color);
            color: white;
            align


lf: flex-end;
            border-bottom-right-radius: 2px;
        }

        /* Поле ввода */
        .input-area {
            padding: 1.5rem;
            border-top: 1px solid var(--border-color);
            display: flex;
            gap: 10px;
        }

        input[type="text"] {
            flex-grow: 1;
            padding: 12px;
            border: 1px solid var(--border-color);
            border-radius: 8px;
            outline: none;
        }

        .send-btn {
            background-color: var(--primary-color);
            color: white;
            border: none;
            padding: 0 20px;
            border-radius: 8px;
            cursor: pointer;
            transition: opacity 0.3s;
        }

        .send-btn:hover {
            opacity: 0.9;
        }

        /* --- АДАПТИВНОСТЬ (RESPONSIVE) --- */
        max-width: 768px {
            .main-container {
                grid-template-columns: 1fr; /* Убираем сайдбар на мобильных */
            }

            .sidebar {
                display: none; /* Или можно сделать выезжающее меню */
            }

            .nav-links {
                display: none; /* Прячем ссылки, оставляем только профиль */
            }

            .message {
                max-width: 85%;
            }
        }
    </style>
</head>
<body>

    <header>
        <a href="#" class="logo">NetTalk</a>
        <nav class="nav-links">
            <a href="#">Главная</a>
            <a href="#">Группы</a>
            <a href="#">Уведомления</a>
        </nav>
        <div class="user-profile">
            <span>Алексей</span>
            <div class="avatar">АИ</div>
        </div>
    </header>

    <div class="main-container">
        <!-- Левая часть: список диалогов -->
        <aside class="sidebar">
            <h2>Чаты</h2>
            <div class="chat-item active">
                <div class="avatar" style="background: #10b981;">ВД</div>
                <div><strong>Владимир Дизайнер </strong>
<small></small></div>
            </div>
            <div class="chat-item">
                <div class="avatar" style="background: #f59e0b;">ДЗ</div>
                <div><strong>Дизайн-завод</strong>
<small>Скиньте правки...</small></div>
            </div>
            <div class="chat-item">
                <div class="avatar" style="background: #ef4444;">М</div>
                <div><strong>Маркетинг</strong>
<small>Когда созвон?</small></div>
            </div>
        </aside>

        <!-- Правая часть: само общение -->
        <main class="chat-window">
            <div class="messages-area">
                <div class="message msg-received">
                    Привет! Я слышал ты дизайнер , можешь помочь ?
                </div>
                <div class="message msg-sent">
                   Привет , да.
                </div>
                <div class="message msg-received">
                    Отлично.
                </div>
            </div>

            <div class="input-area">
                <input type="text" placeholder="Напишите сообщение...">
                <button class="send-btn">Отправить</button>
            </div>
        </main>
    </div>

</body>
</html>
<!-- Личный профиль --> 









