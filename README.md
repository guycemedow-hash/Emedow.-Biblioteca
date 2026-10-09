<head>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <meta charset="UTF-8">
    <title>Цифровой Исторический Архив и Библиотека</title>
    <style>
        body {
            background-color: #120e0a;
            color: #ebdcb9;
            font-family: 'Times New Roman', serif;
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        header {
            background: linear-gradient(rgba(0,0,0,0.85), rgba(0,0,0,0.85)), url('https://unsplash.com');
            background-size: cover;
            background-position: center;
            text-align: center;
            padding: 35px 15px;
            border-bottom: 2px solid #c5a059;
        }
        header h1 {
            color: #c5a059;
            margin: 0;
            font-size: 22px;
            letter-spacing: 1px;
            text-shadow: 2px 2px 4px #000;
        }
        header p {
            font-style: italic;
            font-size: 13px;
            color: #bfae90;
            margin-top: 8px;
        }
        .container {
            padding: 15px;
            max-width: 480px;
            margin: 0 auto;
        }
        .section-title {
            color: #c5a059;
            font-size: 18px;
            border-left: 3px solid #c5a059;
            padding-left: 10px;
            margin-top: 20px;
            margin-bottom: 15px;
        }
        .doc-card {
            background: #1c1610;
            border: 1px solid #362b20;
            border-radius: 6px;
            padding: 12px;
            margin-bottom: 15px;
        }
        .doc-card h3 {
            color: #ebdcb9;
            margin-top: 0;
            font-size: 16px;
            margin-bottom: 5px;
        }
        .doc-card p {
            font-size: 13px;
            line-height: 1.5;
            margin: 5px 0;
            color: #c4b595;
        }
        .tag {
            background-color: #362b20;
            color: #c5a059;
            font-size: 11px;
            padding: 2px 6px;
            border-radius: 3px;
            display: inline-block;
            margin-top: 5px;
        }
        /* Интерактивный блок: Хронология истории */
        .timeline-section {
            background: #18120c;
            border: 1px solid #c5a059;
            border-radius: 6px;
            padding: 15px;
            text-align: center;
            margin-top: 25px;
        }
        .timeline-section h3 {
            color: #c5a059;
            margin-top: 0;
            font-size: 16px;
        }
        .year-input {
            width: 75%;
            padding: 10px;
            border: 1px solid #362b20;
            background: #0f0b07;
            color: #ebdcb9;
            border-radius: 4px;
            font-size: 14px;
            margin-bottom: 10px;
            text-align: center;
        }
        .search-btn {
            background: #c5a059;
            color: #120e0a;
            border: none;
            padding: 10px 15px;
            font-weight: bold;
            border-radius: 4px;
            cursor: pointer;
            width: 80%;
            font-size: 14px;
        }
        .search-btn:active { background: #ab8743; }
        #history-result {
            margin-top: 15px;
            font-size: 13px;
            line-height: 1.5;
            color: #5af78e;
            min-height: 30px;
            text-align: justify;
        }
        footer {
            text-align: center;
            padding: 15px;
            font-size: 11px;
            color: #6e5d47;
            background: #0b0805;
            margin-top: 30px;
        }
    </style>
</head>
<body>

    <header>
        <h1>ЦИФРОВОЙ ИСТОРИЧЕСКИЙ АРХИВ</h1>
        <p>Электронная библиотека первоисточников и исторических документов</p>
    </header>

    <div class="container">
        
        <div class="section-title">📜 Ценные исторические фонды</div>

        <!-- Исторический документ 1 -->
        <div class="doc-card">
            <h3>Анналы и Хроники Древнего Мира</h3>
            <p>Оригинальные летописи, описывающие военные походы, падение старых династий и создание первых государств. Главный источник для изучения политической истории науки.</p>
            <span class="tag">Раздел: Античность</span>
        </div>

        <!-- Исторический документ 2 -->
        <div class="doc-card">
            <h3>Древние Картографические Свитки</h3>
            <p>Собрание уникальных географических карт, по которым историки изучают, как менялись границы великих государств, древние торговые пути и названия городов на протяжении веков.</p>
            <span class="tag">Раздел: Историческая география</span>
        </div>

        <!-- Исторический документ 3 -->
        <div class="doc-card">
            <h3>Дипломатическая переписка монархов</h3>
            <p>Архивные секретные письма, мирные договоры и тайные указы императоров Европы и Азии, которые раскрывают истинные и скрытые причины великих войн прошлого.</p>
            <span class="tag">Раздел: Средневековье</span>
        </div>

        <!-- ИНТЕРАКТИВНЫЙ БЛОК: ПОИСК СОБЫТИЙ -->
        <div class="timeline-section">
            <h3>🔍 Интерактивная Хронология Истории</h3>
            <p style="font-size: 12px; color: #bfae90; margin-bottom: 12px;">Введите важный год мировой истории (Пример: 476, 1492, 1945)</p>
            <input type="number" id="year-input" class="year-input" placeholder="Введите год...">
            <button class="search-btn" onclick="checkHistory()">Узнать событие из архива</button>
            <div id="history-result"></div>
        </div>

    </div>

    <footer>
        <p>Научно-исследовательский проект по дисциплине «История». Разработано на смартфоне Honor.</p>
    </footer>

    <!-- Логика интерактивного поиска событий на русском языке -->
    <script>
        function checkHistory() {
            const year = document.getElementById('year-input').value.trim();
            const result = document.getElementById('history-result');
            
            if (year === "") {
                result.style.color = "#ff6b6b";
                result.innerHTML = "Пожалуйста, введите год!";
                return;
            }
            
            result.style.color = "#ebdcb9";
            
            // База исторических дат
            if (year == "476") {
                result.innerHTML = "🏛️ <b>476 год:</b> Падение Западной Римской империи. В исторической науке этот момент считается официальным завершением эпохи Древнего мира и началом Средних веков.";
            } else if (year == "1492") {
                result.innerHTML = "⛵ <b>1492 год:</b> Экспедиция Христофора Колумба достигла берегов Нового Света (Америки). Начало эпохи Великих географических открытий.";
            } else if (year == "1945") {
                result.innerHTML = "🎖️ <b>1945 год:</b> Окончание Второй мировой войны — самого масштабного и разрушительного конфликта в истории человечества. Создание Организации Объединенных Наций (ООН).";
            } else {
                result.style.color = "#c5a059";
                result.innerHTML = "📜 Запись об этом годе сейчас находится в процессе оцифровки историками нашего архива. Попробуйте ввести ключевые вехи истории: 476, 1492 или 1945.";
            }
        }
    </script>
</body>
</html>
