<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Электронный методический кейс воспитателя ДОУ</title>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #4f46e5;
            --primary-soft: #eef2ff;
            --accent: #06b6d4;
            --bg: #f8fafc;
            --surface: #ffffff;
            --text-main: #0f172a;
            --text-muted: #64748b;
            --border: #e2e8f0;
            --shadow-sm: 0 2px 8px rgba(0,0,0,0.04);
            --shadow-md: 0 10px 25px -5px rgba(0,0,0,0.08);
            --radius: 16px;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Inter', sans-serif;
            -webkit-tap-highlight-color: transparent;
        }

        body {
            background-color: var(--bg);
            color: var(--text-main);
            padding-bottom: 60px;
            line-height: 1.5;
        }

        .container {
            max-width: 960px;
            margin: 0 auto;
            padding: 0 16px;
        }

        /* HEADER / HERO SECTION */
        header {
            background: linear-gradient(135deg, #4f46e5 0%, #3b82f6 100%);
            color: white;
            padding: 40px 24px 32px;
            border-radius: 0 0 28px 28px;
            margin-bottom: 24px;
            box-shadow: 0 12px 30px -10px rgba(79, 70, 229, 0.4);
        }

        .profile-badge {
            display: inline-flex;
            align-items: center;
            gap: 6px;
            background: rgba(255, 255, 255, 0.18);
            backdrop-filter: blur(8px);
            padding: 6px 14px;
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 0.5px;
            margin-bottom: 16px;
        }

        .profile-card {
            display: flex;
            align-items: center;
            gap: 20px;
            margin-bottom: 20px;
        }

        .avatar {
            width: 72px;
            height: 72px;
            border-radius: 50%;
            background: #ffffff;
            color: var(--primary);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2rem;
            font-weight: 700;
            box-shadow: 0 4px 12px rgba(0,0,0,0.15);
            flex-shrink: 0;
        }

        .profile-info h1 {
            font-size: 1.5rem;
            font-weight: 700;
            line-height: 1.2;
            margin-bottom: 4px;
        }

        .profile-info p {
            font-size: 0.95rem;
            opacity: 0.9;
        }

        .credo {
            background: rgba(255, 255, 255, 0.12);
            padding: 12px 16px;
            border-radius: 12px;
            font-style: italic;
            font-size: 0.88rem;
            border-left: 3px solid #60a5fa;
        }

        /* STATS COUNTER */
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 12px;
            margin-bottom: 24px;
        }

        .stat-card {
            background: var(--surface);
            padding: 14px;
            border-radius: var(--radius);
            border: 1px solid var(--border);
            text-align: center;
            box-shadow: var(--shadow-sm);
        }

        .stat-number {
            font-size: 1.3rem;
            font-weight: 700;
            color: var(--primary);
        }

        .stat-label {
            font-size: 0.75rem;
            color: var(--text-muted);
            font-weight: 500;
        }

        /* SEARCH & TABS */
        .controls {
            position: sticky;
            top: 12px;
            z-index: 100;
            background: rgba(248, 250, 252, 0.9);
            backdrop-filter: blur(10px);
            padding: 8px 0;
            margin-bottom: 20px;
        }

        .search-box {
            position: relative;
            margin-bottom: 12px;
        }

        .search-box input {
            width: 100%;
            padding: 12px 16px 12px 42px;
            border-radius: 12px;
            border: 1px solid var(--border);
            font-size: 0.95rem;
            outline: none;
            background: var(--surface);
            box-shadow: var(--shadow-sm);
            transition: all 0.2s;
        }

        .search-box input:focus {
            border-color: var(--primary);
            box-shadow: 0 0 0 3px rgba(79, 70, 229, 0.12);
        }

        .search-icon {
            position: absolute;
            left: 14px;
            top: 50%;
            transform: translateY(-50%);
            color: var(--text-muted);
        }

        .tabs {
            display: flex;
            gap: 8px;
            overflow-x: auto;
            padding-bottom: 4px;
            scrollbar-width: none;
        }

        .tabs::-webkit-scrollbar { display: none; }

        .tab-btn {
            padding: 8px 16px;
            border-radius: 20px;
            border: 1px solid var(--border);
            background: var(--surface);
            color: var(--text-muted);
            font-size: 0.85rem;
            font-weight: 500;
            cursor: pointer;
            white-space: nowrap;
            transition: all 0.2s;
        }

        .tab-btn.active {
            background: var(--primary);
            color: white;
            border-color: var(--primary);
            box-shadow: 0 4px 12px rgba(79, 70, 229, 0.25);
        }

        /* CARDS GRID */
        .section-header {
            font-size: 1.15rem;
            font-weight: 700;
            margin: 24px 0 14px;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .cards-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 16px;
        }

        .doc-card {
            background: var(--surface);
            border: 1px solid var(--border);
            border-radius: var(--radius);
            padding: 18px;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            transition: all 0.25s ease;
            box-shadow: var(--shadow-sm);
        }

        .doc-card:hover {
            transform: translateY(-3px);
            box-shadow: var(--shadow-md);
            border-color: #cbd5e1;
        }

        .doc-top {
            display: flex;
            gap: 14px;
            margin-bottom: 14px;
        }

        .doc-icon {
            width: 44px;
            height: 44px;
            border-radius: 12px;
            background: var(--primary-soft);
            color: var(--primary);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.3rem;
            flex-shrink: 0;
        }

        .doc-title {
            font-weight: 600;
            font-size: 0.98rem;
            margin-bottom: 4px;
            color: var(--text-main);
        }

        .doc-desc {
            font-size: 0.83rem;
            color: var(--text-muted);
            line-height: 1.4;
        }

        .doc-btn {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: 6px;
            width: 100%;
            padding: 10px;
            background: #f1f5f9;
            color: var(--primary);
            font-weight: 600;
            font-size: 0.85rem;
            text-decoration: none;
            border-radius: 10px;
            transition: all 0.2s;
            margin-top: 10px;
        }

        .doc-card:hover .doc-btn {
            background: var(--primary);
            color: white;
        }

        footer {
            text-align: center;
            margin-top: 48px;
            padding-top: 24px;
            border-top: 1px solid var(--border);
            color: var(--text-muted);
            font-size: 0.82rem;
        }

        @media (max-width: 600px) {
            .profile-card { flex-direction: column; text-align: center; }
            .credo { text-align: center; }
        }
    </style>
</head>
<body>

    <!-- HERO HEADER -->
    <header>
        <div class="container">
            <div class="profile-badge">📱 QR-Кейс Документации</div>
            <div class="profile-card">
                <div class="avatar">👩‍🏫</div>
                <div class="profile-info">
                    <h1>Электронный кейс воспитателя ДОУ</h1>
                    <p>Методический портфель & Нормативная база</p>
                </div>
            </div>
            <div class="credo">
                «Воспитание — это умение открыть ребенку дверь в мир знаний и доброты».
            </div>
        </div>
    </header>

    <div class="container">
        
        <!-- СТАТИСТИКА -->
        <div class="stats-grid">
            <div class="stat-card">
                <div class="stat-number">15+</div>
                <div class="stat-label">Разделов документов</div>
            </div>
            <div class="stat-card">
                <div class="stat-number">100%</div>
                <div class="stat-label">Соответствие ФГОС</div>
            </div>
            <div class="stat-card">
                <div class="stat-number">24/7</div>
                <div class="stat-label">Доступ по QR</div>
            </div>
        </div>

        <!-- ПОИСК И НАВИГАЦИЯ -->
        <div class="controls">
            <div class="search-box">
                <span class="search-icon">🔍</span>
                <input type="text" id="searchInput" placeholder="Поиск документа, проекта, картотеки..." onkeyup="filterDocs()">
            </div>
            <div class="tabs">
                <button class="tab-btn active" onclick="filterCategory('all', this)">Все материалы</button>
                <button class="tab-btn" onclick="filterCategory('norm', this)">⚖️ Нормативка</button>
                <button class="tab-btn" onclick="filterCategory('plan', this)">📅 Планирование</button>
                <button class="tab-btn" onclick="filterCategory('metod', this)">📁 Копилка</button>
                <button class="tab-btn" onclick="filterCategory('parents', this)">👨‍👩‍👧 Родителям</button>
            </div>
        </div>

        <!-- СПИСОК КАРТОЧЕК -->
        <div id="docsGrid" class="cards-grid">
            
            <!-- 1. НОРМАТИВКА -->
            <div class="doc-card" data-cat="norm">
                <div class="doc-top">
                    <div class="doc-icon">📘</div>
                    <div>
                        <div class="doc-title">ФГОС ДО и ФОП ДО</div>
                        <div class="doc-desc">Федеральный госстандарт и программа дошкольного образования.</div>
                    </div>
                </div>
                <a href="https://drive.google.com" target="_blank" class="doc-btn">Открыть файлы ↗</a>
            </div>

            <div class="doc-card" data-cat="norm">
                <div class="doc-top">
                    <div class="doc-icon">📜</div>
                    <div>
                        <div class="doc-title">Локальные акты ДОУ</div>
                        <div class="doc-desc">Устав, правила распорядка, должностные инструкции воспитателя.</div>
                    </div>
                </div>
                <a href="#" target="_blank" class="doc-btn">Открыть файлы ↗</a>
            </div>

            <div class="doc-card" data-cat="norm">
                <div class="doc-top">
                    <div class="doc-icon">🛡️</div>
                    <div>
                        <div class="doc-title">Охрана труда и ТБ</div>
                        <div class="doc-desc">Инструкции по жизни и здоровью воспитанников, противопожарная ТБ.</div>
                    </div>
                </div>
                <a href="#" target="_blank" class="doc-btn">Открыть файлы ↗</a>
            </div>

            <!-- 2. ПЛАНИРОВАНИЕ -->
            <div class="doc-card" data-cat="plan">
                <div class="doc-top">
                    <div class="doc-icon">📆</div>
                    <div>
                        <div class="doc-title">Календарное планирование</div>
                        <div class="doc-desc">Планы воспитательно-образовательной работы по неделям и темам.</div>
                    </div>
                </div>
                <a href="#" target="_blank" class="doc-btn">Смотреть планы ↗</a>
            </div>

            <div class="doc-card" data-cat="plan">
                <div class="doc-top">
                    <div class="doc-icon">⏰</div>
                    <div>
                        <div class="doc-title">Режим дня и сетка занятий</div>
                        <div class="doc-desc">Расписание организованной деятельности и циклограмма воспитателя.</div>
                    </div>
                </div>
                <a href="#" target="_blank" class="doc-btn">Смотреть сетку ↗</a>
            </div>

            <div class="doc-card" data-cat="plan">
                <div class="doc-top">
                    <div class="doc-icon">📈</div>
                    <div>
                        <div class="doc-title">Педагогический мониторинг</div>
                        <div class="doc-desc">Карты развития детей, сводные таблицы и динамика освоения ФОП.</div>
                    </div>
                </div>
                <a href="#" target="_blank" class="doc-btn">Открыть карты ↗</a>
            </div>

            <!-- 3. МЕТОДИЧЕСКАЯ КОПИЛКА -->
            <div class="doc-card" data-cat="metod">
                <div class="doc-top">
                    <div class="doc-icon">💡</div>
                    <div>
                        <div class="doc-title">Конспекты занятий</div>
                        <div class="doc-desc">Картотека открытых и календарных занятий по всем пяти областям.</div>
                    </div>
                </div>
                <a href="#" target="_blank" class="doc-btn">Открыть картотеку ↗</a>
            </div>

            <div class="doc-card" data-cat="metod">
                <div class="doc-top">
                    <div class="doc-icon">🎮</div>
                    <div>
                        <div class="doc-title">Картотеки игр</div>
                        <div class="doc-desc">Подвижные, сюжетно-ролевые, дидактические и пальчиковые игры.</div>
                    </div>
                </div>
                <a href="#" target="_blank" class="doc-btn">Скачать игры ↗</a>
            </div>

            <div class="doc-card" data-cat="metod">
                <div class="doc-top">
                    <div class="doc-icon">🚀</div>
                    <div>
                        <div class="doc-title">Проекты и инклюзия</div>
                        <div class="doc-desc">Паспорта проектов и индивидуальные маршруты (ОВЗ/адаптация).</div>
                    </div>
                </div>
                <a href="#" target="_blank" class="doc-btn">Смотреть проекты ↗</a>
            </div>

            <!-- 4. РАБОТА С РОДИТЕЛЯМИ -->
            <div class="doc-card" data-cat="parents">
                <div class="doc-top">
                    <div class="doc-icon">📝</div>
                    <div>
                        <div class="doc-title">Протоколы собраний</div>
                        <div class="doc-desc">Протоколы родительских собраний, явочные листы, решения.</div>
                    </div>
                </div>
                <a href="#" target="_blank" class="doc-btn">Открыть архив ↗</a>
            </div>

            <div class="doc-card" data-cat="parents">
                <div class="doc-top">
                    <div class="doc-icon">📌</div>
                    <div>
                        <div class="doc-title">Наглядные консультации</div>
                        <div class="doc-desc">Папки-передвижки, памятки, буклеты для родительского уголка.</div>
                    </div>
                </div>
                <a href="#" target="_blank" class="doc-btn">Перейти к папкам ↗</a>
            </div>

        </div>

        <footer>
            <p>© Электронный методический кейс воспитателя ДОУ | Оптимизировано под QR-код</p>
        </footer>

    </div>

    <script>
        let currentCat = 'all';

        function filterDocs() {
            const query = document.getElementById('searchInput').value.toLowerCase();
            const cards = document.querySelectorAll('.doc-card');

            cards.forEach(card => {
                const title = card.querySelector('.doc-title').innerText.toLowerCase();
                const desc = card.querySelector('.doc-desc').innerText.toLowerCase();
                const cat = card.getAttribute('data-cat');

                const matchesSearch = title.includes(query) || desc.includes(query);
                const matchesCat = (currentCat === 'all' || cat === currentCat);

                if (matchesSearch && matchesCat) {
                    card.style.display = 'flex';
                } else {
                    card.style.display = 'none';
                }
            });
        }

        function filterCategory(cat, btn) {
            currentCat = cat;
            document.querySelectorAll('.tab-btn').forEach(b => b.classList.remove('active'));
            btn.classList.add('active');
            filterDocs();
        }
    </script>
</body>
</html>
