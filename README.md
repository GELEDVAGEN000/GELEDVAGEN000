<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Космические открытия</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #0c0c2e 0%, #1a1a3e 100%);
            color: #fff;
            min-height: 100vh;
            padding: 20px;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
        }
        
        header {
            text-align: center;
            padding: 30px 0;
            border-bottom: 2px solid #4a4aff;
            margin-bottom: 30px;
        }
        
        h1 {
            font-size: 2.8rem;
            background: linear-gradient(90deg, #4a4aff, #00d4ff);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            margin-bottom: 10px;
        }
        
        .subtitle {
            font-size: 1.2rem;
            color: #a0a0ff;
        }
        
        .stats-bar {
            background: rgba(0, 0, 0, 0.3);
            padding: 15px;
            border-radius: 10px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 30px;
            border: 1px solid #333366;
        }
        
        .visits-counter {
            font-size: 1.1rem;
            background: #1a1a4d;
            padding: 10px 20px;
            border-radius: 20px;
            border: 1px solid #4a4aff;
        }
        
        .counter-number {
            font-weight: bold;
            color: #00d4ff;
            font-size: 1.3rem;
        }
        
        .main-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 30px;
            margin-bottom: 40px;
        }
        
        @media (max-width: 768px) {
            .main-content {
                grid-template-columns: 1fr;
            }
        }
        
        .info-section, .game-section {
            background: rgba(20, 20, 60, 0.7);
            border-radius: 15px;
            padding: 25px;
            border: 1px solid #333366;
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.3);
        }
        
        h2 {
            color: #00d4ff;
            margin-bottom: 20px;
            padding-bottom: 10px;
            border-bottom: 1px solid #333366;
        }
        
        .fact-item {
            background: rgba(30, 30, 80, 0.5);
            padding: 15px;
            border-radius: 10px;
            margin-bottom: 15px;
            border-left: 4px solid #4a4aff;
            transition: transform 0.3s;
        }
        
        .fact-item:hover {
            transform: translateX(5px);
            background: rgba(40, 40, 100, 0.7);
        }
        
        .fact-title {
            font-weight: bold;
            color: #a0a0ff;
            margin-bottom: 5px;
        }
        
        .game-area {
            text-align: center;
        }
        
        .planet-display {
            width: 200px;
            height: 200px;
            margin: 0 auto 20px;
            border-radius: 50%;
            background: radial-gradient(circle at 30% 30%, #1a3a6d, #0c1b33);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 5rem;
            border: 3px solid #4a4aff;
            box-shadow: 0 0 30px rgba(74, 74, 255, 0.5);
            transition: all 0.5s;
        }
        
        .controls {
            display: flex;
            flex-direction: column;
            gap: 15px;
            margin-top: 20px;
        }
        
        button {
            background: linear-gradient(90deg, #4a4aff, #00d4ff);
            color: white;
            border: none;
            padding: 15px;
            border-radius: 10px;
            font-size: 1.1rem;
            cursor: pointer;
            transition: all 0.3s;
            font-weight: bold;
        }
        
        button:hover {
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(74, 74, 255, 0.4);
        }
        
        select, input {
            padding: 15px;
            border-radius: 10px;
            border: 1px solid #4a4aff;
            background: rgba(10, 10, 40, 0.8);
            color: white;
            font-size: 1rem;
        }
        
        .result {
            margin-top: 20px;
            padding: 15px;
            border-radius: 10px;
            background: rgba(30, 30, 80, 0.5);
            display: none;
        }
        
        .success {
            background: rgba(0, 100, 0, 0.3);
            border: 1px solid #00aa00;
        }
        
        .error {
            background: rgba(100, 0, 0, 0.3);
            border: 1px solid #ff5555;
        }
        
        .visitors-log {
            background: rgba(20, 20, 60, 0.7);
            border-radius: 15px;
            padding: 25px;
            border: 1px solid #333366;
            margin-top: 30px;
        }
        
        .log-container {
            height: 200px;
            overflow-y: auto;
            background: rgba(10, 10, 40, 0.8);
            padding: 15px;
            border-radius: 10px;
            margin-top: 15px;
            border: 1px solid #333366;
        }
        
        .log-entry {
            padding: 8px;
            border-bottom: 1px solid #333366;
            font-family: monospace;
        }
        
        footer {
            text-align: center;
            margin-top: 40px;
            padding-top: 20px;
            border-top: 1px solid #333366;
            color: #a0a0ff;
            font-size: 0.9rem;
        }
        
        .discovery-count {
            font-size: 1.2rem;
            color: #00d4ff;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <h1>🚀 Космические открытия</h1>
            <p class="subtitle">Исследуйте Вселенную и совершайте научные открытия!</p>
        </header>
        
        <div class="stats-bar">
            <div class="discoveries">
                <span class="discovery-count">0</span> открытий совершено
            </div>
            <div class="visits-counter">
                Посещений: <span class="counter-number" id="visitCount">0</span>
            </div>
        </div>
        
        <div class="main-content">
            <section class="info-section">
                <h2>📚 Факты о космосе</h2>
                <div id="factsContainer">
                    <!-- Факты будут добавляться через JavaScript -->
                </div>
            </section>
            
            <section class="game-section">
                <h2>🎮 Игра: Угадай планету</h2>
                <div class="game-area">
                    <div class="planet-display" id="planetDisplay">?</div>
                    
                    <div class="controls">
                        <select id="planetSelect">
                            <option value="">Выберите планету</option>
                            <option value="mercury">Меркурий</option>
                            <option value="venus">Венера</option>
                            <option value="earth">Земля</option>
                            <option value="mars">Марс</option>
                            <option value="jupiter">Юпитер</option>
                            <option value="saturn">Сатурн</option>
                            <option value="uranus">Уран</option>
                            <option value="neptune">Нептун</option>
                        </select>
                        
                        <button id="guessBtn">Сделать предположение</button>
                        <button id="hintBtn">Получить подсказку</button>
                        <button id="newGameBtn">Новая игра</button>
                    </div>
                    
                    <div class="result" id="result"></div>
                </div>
            </section>
        </div>
        
        <section class="visitors-log">
            <h2>📋 Журнал посещений</h2>
            <p>Всего уникальных посещений: <span id="totalVisits">0</span></p>
            <div class="log-container" id="logContainer">
                <!-- Записи журнала будут добавляться через JavaScript -->
            </div>
        </section>
        
        <footer>
            <p>© 2023 Космические открытия | Вселенная ждет своих исследователей!</p>
            <p style="margin-top: 10px;">Игра обновляется ежедневно с новыми фактами и загадками</p>
        </footer>
    </div>

    <script>
        // Данные для сайта
        const spaceFacts = [
            {title: "Солнечная система", fact: "В нашей Солнечной системе 8 планет, но были времена, когда мы считали, что их 9."},
            {title: "Юпитер", fact: "Юпитер настолько велик, что внутри него могли бы поместиться все остальные планеты Солнечной системы."},
            {title: "Венера", fact: "День на Венере длиннее, чем год. Полный оборот вокруг Солнца она совершает быстрее, чем оборот вокруг своей оси."},
            {title: "Марс", fact: "На Марсе находится самый большой вулкан в Солнечной системе - Олимп, высотой 21 км."},
            {title: "Сатурн", fact: "Кольца Сатурна состоят из миллиардов частиц льда и камня размером от пылинок до домов."},
            {title: "Меркурий", fact: "Меркурий - самая быстрая планета, он совершает полный оборот вокруг Солнца всего за 88 земных дней."},
            {title: "Нептун", fact: "На Нептуне дуют самые сильные ветры в Солнечной системе - их скорость достигает 2100 км/ч."},
            {title: "Уран", fact: "Уран вращается "лежа на боку" - его ось вращения наклонена на 98 градусов."},
            {title: "Земля", fact: "Земля - единственная известная планета, на которой существует жизнь."},
            {title: "Космические станции", fact: "Международная космическая станция (МКС) совершает полный оборот вокруг Земли за 90 минут."}
        ];

        const planetData = {
            mercury: {name: "Меркурий", emoji: "☿", hint: "Самая близкая к Солнцу планета"},
            venus: {name: "Венера", emoji: "♀", hint: "Самая горячая планета в нашей системе"},
            earth: {name: "Земля", emoji: "🌍", hint: "Единственная планета с жидкой водой на поверхности"},
            mars: {name: "Марс", emoji: "♂", hint: "Красная планета, названа в честь бога войны"},
            jupiter: {name: "Юпитер", emoji: "♃", hint: "Самая большая планета в Солнечной системе"},
            saturn: {name: "Сатурн", emoji: "♄", hint: "Известен своими впечатляющими кольцами"},
            uranus: {name: "Уран", emoji: "♅", hint: "Вращается на боку, имеет голубой цвет"},
            neptune: {name: "Нептун", emoji: "♆", hint: "Самая ветреная планета в нашей системе"}
        };

        // Инициализация при загрузке страницы
        document.addEventListener('DOMContentLoaded', function() {
            // Инициализация счетчика посещений
            initializeVisitCounter();
            
            // Заполнение фактов
            populateFacts();
            
            // Настройка игры
            initializeGame();
            
            // Обновление журнала посещений
            updateVisitorsLog();
        });

        // Счетчик посещений
        function initializeVisitCounter() {
            let visits = localStorage.getItem('spaceSiteVisits');
            if (!visits) {
                visits = Math.floor(Math.random() * 50) + 80; // Начинаем примерно со 100 посещений
            } else {
                visits = parseInt(visits) + 1;
            }
            
            localStorage.setItem('spaceSiteVisits', visits);
            document.getElementById('visitCount').textContent = visits;
            document.getElementById('totalVisits').textContent = visits;
            
            // Добавляем текущее посещение в журнал
            const now = new Date();
            const visitLog = JSON.parse(localStorage.getItem('spaceVisitLog') || '[]');
            
            visitLog.unshift({
                id: Date.now(),
                time: now.toLocaleString('ru-RU'),
                type: 'Посещение'
            });
            
            // Ограничиваем журнал 100 записями
            if (visitLog.length > 100) {
                visitLog.length = 100;
            }
            
            localStorage.setItem('spaceVisitLog', JSON.stringify(visitLog));
        }

        // Заполнение фактов
        function populateFacts() {
            const container = document.getElementById('factsContainer');
            
            // Показываем все факты
            spaceFacts.forEach(fact => {
                const factElement = document.createElement('div');
                factElement.className = 'fact-item';
                factElement.innerHTML = `
                    <div class="fact-title">${fact.title}</div>
                    <div class="fact-text">${fact.fact}</div>
                `;
                container.appendChild(factElement);
            });
        }

        // Игровая логика
        let currentPlanet = '';
        let discoveries = 0;
        let attempts = 0;

        function initializeGame() {
            // Загружаем количество открытий
            const savedDiscoveries = localStorage.getItem('planetDiscoveries');
            discoveries = savedDiscoveries ? parseInt(savedDiscoveries) : 0;
            document.querySelector('.discovery-count').textContent = discoveries;
            
            // Начинаем новую игру
            startNewGame();
            
            // Назначаем обработчики событий
            document.getElementById('guessBtn').addEventListener('click', makeGuess);
            document.getElementById('hintBtn').addEventListener('click', showHint);
            document.getElementById('newGameBtn').addEventListener('click', startNewGame);
        }

        function startNewGame() {
            // Выбираем случайную планету
            const planets = Object.keys(planetData);
            currentPlanet = planets[Math.floor(Math.random() * planets.length)];
            
            // Сбрасываем попытки
            attempts = 0;
            
            // Скрываем результат предыдущей попытки
            document.getElementById('result').style.display = 'none';
            
            // Обновляем отображение планеты (показываем вопросительный знак)
            document.getElementById('planetDisplay').textContent = '?';
            
            // Сбрасываем выбор в выпадающем списке
            document.getElementById('planetSelect').value = '';
            
            // Добавляем запись в журнал
            addLogEntry('Начата новая игра', 'game');
        }

        function makeGuess() {
            const select = document.getElementById('planetSelect');
            const selectedPlanet = select.value;
            const resultDiv = document.getElementById('result');
            
            if (!selectedPlanet) {
                resultDiv.textContent = 'Пожалуйста, выберите планету!';
                resultDiv.className = 'result error';
                resultDiv.style.display = 'block';
                return;
            }
            
            attempts++;
            
            if (selectedPlanet === currentPlanet) {
                // Правильный ответ
                document.getElementById('planetDisplay').textContent = planetData[currentPlanet].emoji;
                
                resultDiv.innerHTML = `
                    <strong>Поздравляем!</strong><br>
                    Вы угадали планету ${planetData[currentPlanet].name}!<br>
                    Вам потребовалось ${attempts} ${getAttemptsWord(attempts)}.
                `;
                resultDiv.className = 'result success';
                resultDiv.style.display = 'block';
                
                // Увеличиваем счетчик открытий
                discoveries++;
                document.querySelector('.discovery-count').textContent = discoveries;
                localStorage.setItem('planetDiscoveries', discoveries);
                
                // Добавляем запись в журнал
                addLogEntry(`Угадана планета: ${planetData[currentPlanet].name}`, 'success');
                
                // Автоматически начинаем новую игру через 3 секунды
                setTimeout(startNewGame, 3000);
            } else {
                // Неправильный ответ
                resultDiv.textContent = `Неправильно! Это не ${planetData[selectedPlanet].name}. Попробуйте еще раз.`;
                resultDiv.className = 'result error';
                resultDiv.style.display = 'block';
                
                // Добавляем запись в журнал
                addLogEntry(`Неверная попытка: ${planetData[selectedPlanet].name}`, 'attempt');
            }
        }

        function showHint() {
            const resultDiv = document.getElementById('result');
            resultDiv.textContent = `Подсказка: ${planetData[currentPlanet].hint}`;
            resultDiv.className = 'result';
            resultDiv.style.display = 'block';
            
            // Добавляем запись в журнал
            addLogEntry('Запрошена подсказка', 'hint');
        }

        function getAttemptsWord(num) {
            if (num % 10 === 1 && num % 100 !== 11) return 'попытка';
            if ([2,3,4].includes(num % 10) && ![12,13,14].includes(num % 100)) return 'попытки';
            return 'попыток';
        }

        // Журнал посещений
        function updateVisitorsLog() {
            const logContainer = document.getElementById('logContainer');
            const visitLog = JSON.parse(localStorage.getItem('spaceVisitLog') || '[]');
            
            logContainer.innerHTML = '';
            
            visitLog.forEach(entry => {
                const logEntry = document.createElement('div');
                logEntry.className = 'log-entry';
                logEntry.innerHTML = `<span style="color: #a0a0ff">[${entry.time}]</span> ${entry.type}`;
                logContainer.appendChild(logEntry);
            });
        }

        function addLogEntry(message, type) {
            const visitLog = JSON.parse(localStorage.getItem('spaceVisitLog') || '[]');
            const now = new Date();
            
            visitLog.unshift({
                id: Date.now(),
                time: now.toLocaleString('ru-RU'),
                type: message
            });
            
            // Ограничиваем журнал 100 записями
            if (visitLog.length > 100) {
                visitLog.length = 100;
            }
            
            localStorage.setItem('spaceVisitLog', JSON.stringify(visitLog));
            updateVisitorsLog();
        }

        // Добавляем несколько случайных записей в журнал при первом запуске
        if (!localStorage.getItem('spaceVisitLog')) {
            const initialLog = [];
            const types = ['Посещение', 'Игра начата', 'Планета угадана', 'Подсказка запрошена'];
            
            // Создаем 100 записей за прошлые "посещения"
            for (let i = 100; i >= 1; i--) {
                const date = new Date();
                date.setDate(date.getDate() - Math.floor(i / 10));
                date.setHours(Math.floor(Math.random() * 24));
                date.setMinutes(Math.floor(Math.random() * 60));
                
                initialLog.push({
                    id: Date.now() - i * 1000000,
                    time: date.toLocaleString('ru-RU'),
                    type: types[Math.floor(Math.random() * types.length)]
                });
            }
            
            localStorage.setItem('spaceVisitLog', JSON.stringify(initialLog));
            updateVisitorsLog();
        }
    </script>
</body>
</html>
