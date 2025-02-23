# my-zen-website
eat snake
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>觉悟之光</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        .sutra {
            color: #ff4500;
            font-weight: bold;
        }
        
        .lotus {
            background-image: url('data:image/svg+xml,%3Csvg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100" width="100" height="100"%3E%3Cstyle%3E.path { fill: %23fff; } %3C/style%3E%3Cpath d="M67.5 60c-4.5 0-9 .9-9 3v4.5h21v-4.5c0-2.1-.9-3-3-3zm-3-7.5h-4.8l-.9-3H45c-3.3 0-6.1.9-8.9 3.2C34.7 45.9 32 49.6 32 52.7V83h10v-4.5c0-3.3-.9-5.7-5.7-5.7H29.2c1.8 0 3.5.7 4.9 1.1L56 52h10l4.8 7.5z"/%3E%3C/svg%3E");
        }
    </style>
</head>
<body class="bg-amber-50 min-h-screen">
    <div class="container mx-auto px-4 py-8">
        <!-- 导航 -->
        <nav class="mb-12">
            <ul class="flex justify-center space-x-6 text-lg">
                <li><a href="#" class="text-gray-700 hover:text-orange-500">经典经文</a></li>
                <li><a href="#" class="text-gray-700 hover:text-orange-500">禅宗故事</a></li>
                <li><a href="#" class="text-gray-700 hover:text-orange-500">菩萨道</a></li>
                <li><a href="#" class="text-gray-700 hover:text-orange-500">冥想空间</a></li>
            </ul>
        </nav>

        <!-- 主内容 -->
        <div class="max-w-2xl mx-auto">
            <div class="lotus bg-cover rounded-lg p-8 mb-8 shadow-lg transition duration-500 hover:shadow-xl">
                <p class="text-center text-3xl font-bold mb-6">放下执念</p>
                <article class="prose max-w-none">
                    <p>人生如梦幻泡影，一切唯心造。</p>
                    <p>当我们放下对外物的执着，心灵自然获得解脱。</p>
                    <p>禅修不仅仅是打坐，更是时时刻刻觉察当下。</p>
                </article>
            </div>

            <!-- 图片 -->
            <div class="bg-fixed opacity-20" style="background-image: url('https://images.unsplash.com/photo-1584622659714-9567b68c5eah?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80')">
                <div class="relative z-index-10 text-center py-16">
                    <h2 class="text-4xl font-bold mb-4">觉悟之光</h2>
                    <p class="text-xl text-gray-700 mb-8">愿您在佛法的指引下找到内心的平静与光明。</p>
                </div>
            </div>

            <!-- 脚注 -->
            <footer class="mt-16 py-8 border-t">
                <p class="text-center text-gray-600">
                    众生平等，蜎飞蠕动，皆具如来智慧德相。
                    <br>
                    愿众生平安喜乐。
                </p>
            </footer>
        </div>

    </div>

    <script>
        // 简单的交互效果
        window.addEventListener('scroll', function() {
            const nav = document.querySelector('nav');
            if (window.scrollY > 100) {
                nav.style.top = '0';
                nav.style.backgroundColor = 'rgba(255, 245, 239, 0.9)';
            } else {
                nav.style.top = '-100px';
                nav.style.backgroundColor = 'transparent';
            }
        });

        // 禅意钟声
        const zenHourglass = setInterval(function() {
            const currentTime = new Date();
            if (currentTime.getHours() % 4 === 0) {
                playZenSound();
            }
        }, 1000);

        function playZenSound() {
            new Audio('https://assets.mixkit.co/active_storage/sfx/2693/2693-preview.mp3').play().catch(() => {});
        }

        // 偶尔出现随机经文
        setInterval(function() {
            const randomQuotes = [
                "一切众生皆具如来智慧德相，只因妄想执着而不能证得。",
                "放下屠刀，立地成佛。",
                "菩提本无树，明镜亦非台。本来无一物，何处惹尘埃？"
            ];
            
            const randomQuote = randomQuotes[Math.floor(Math.random() * randomQuotes.length)];
            document.querySelector('.sutra').textContent = randomQuote;
        }, 60000);
    </script>
</body>
</html>
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>贪吃蛇游戏</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background-color: #f0f0f0;
            font-family: Arial, sans-serif;
        }

        .game-container {
            text-align: center;
            display: flex;
            align-items: center;
            justify-content: space-between;
            max-width: 100%;
            flex-wrap: wrap;
        }

        #gameCanvas {
            border: 2px solid #333;
            border-radius: 5px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            margin: 0 auto;
        }

        #gameControls {
            text-align: center;
            margin: 0 auto;
            padding: 0 8px;
        }

        #gameScore {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
        }

        #score {
            font-size: 24px;
            margin: 10px 0;
        }

        #startBtn {
            font-size: 18px;
            padding: 12px 24px;
            background: linear-gradient(145deg, #f0f0f0, #cacaca);
            color: #333;
            border: none;
            border-radius: 10px;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 5px 5px 10px #bebebe,
                -5px -5px 10px #ffffff;
            position: relative;
            overflow: hidden;
            font-weight: bold;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        #startBtn::before {
            content: '';
            position: absolute;
            top: 2px;
            left: 2px;
            right: 2px;
            bottom: 50%;
            background: linear-gradient(180deg, rgba(255, 255, 255, 0.3), transparent);
            border-radius: 8px 8px 0 0;
            pointer-events: none;
        }

        #startBtn:hover {
            transform: translateY(-2px);
            box-shadow: 6px 6px 12px #bebebe,
                -6px -6px 12px #ffffff;
            background: linear-gradient(145deg, #f5f5f5, #d0d0d0);
        }

        #startBtn:active {
            transform: translateY(1px);
            box-shadow: inset 4px 4px 8px #bebebe,
                inset -4px -4px 8px #ffffff;
            background: linear-gradient(145deg, #e6e6e6, #c0c0c0);
        }

        .controls {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 10px;
            width: 180px;
            margin: 20px auto;
        }

        .control-btn {
            width: 60px;
            height: 60px;
            font-size: 24px;
            background: linear-gradient(145deg, #f0f0f0, #cacaca);
            color: #333;
            border: none;
            border-radius: 50%;
            cursor: pointer;
            transition: all 0.3s ease;
            display: flex;
            justify-content: center;
            align-items: center;
            box-shadow: 5px 5px 10px #bebebe,
                -5px -5px 10px #ffffff;
            position: relative;
            overflow: hidden;
        }

        .control-btn::before {
            content: '';
            position: absolute;
            top: 5%;
            left: 5%;
            right: 5%;
            bottom: 5%;
            border-radius: 50%;
            z-index: -1;
        }

        .control-btn:hover {
            transform: translateY(-2px);
            box-shadow: 6px 6px 12px #bebebe,
                -6px -6px 12px #ffffff;
        }

        .control-btn:active {
            transform: translateY(1px);
            box-shadow: inset 4px 4px 8px #bebebe,
                inset -4px -4px 8px #ffffff;
        }

        #up {
            grid-column: 2;
        }

        #left {
            grid-column: 1;
            grid-row: 2;
        }

        #right {
            grid-column: 3;
            grid-row: 2;
        }

        #down {
            grid-column: 2;
            grid-row: 3;
        }
    </style>
</head>

<body>
    <div class="game-container">
        <canvas id="gameCanvas" width="300" height="300"></canvas>
        <div id="gameControls">
            <div id="gameScore">
                <div id="score">得分: 0</div>
                <button id="startBtn">开始游戏</button>
            </div>
            <div class="controls">
                <button id="up" class="control-btn" onclick="changeDirectionByButton('up')">↑</button>
                <button id="left" class="control-btn" onclick="changeDirectionByButton('left')">←</button>
                <button id="right" class="control-btn" onclick="changeDirectionByButton('right')">→</button>
                <button id="down" class="control-btn" onclick="changeDirectionByButton('down')">↓</button>
            </div>
        </div>
    </div>
    <script>
        const canvas = document.getElementById('gameCanvas');
        const ctx = canvas.getContext('2d');
        const scoreElement = document.getElementById('score');
        const startBtn = document.getElementById('startBtn');

        const gridSize = 15;
        const tileCount = canvas.width / gridSize;

        let snake = [{ x: 10, y: 10 }];
        let food = { x: 15, y: 15 };
        let dx = 0;
        let dy = 0;
        let score = 0;
        let gameRunning = false;

        function drawGame() {
            if (!gameRunning) return;

            clearCanvas();
            moveSnake();
            drawSnake();
            drawFood();
            checkCollision();
            updateScore();
            setTimeout(drawGame, 200);
        }

        function clearCanvas() {
            ctx.fillStyle = '#f0f0f0';
            ctx.fillRect(0, 0, canvas.width, canvas.height);
        }

        function moveSnake() {
            const head = { x: snake[0].x + dx, y: snake[0].y + dy };
            snake.unshift(head);

            if (head.x === food.x && head.y === food.y) {
                generateFood();
                score += 10;
            } else {
                snake.pop();
            }
        }

        function drawSnake() {
            snake.forEach((segment, index) => {
                const gradient = ctx.createLinearGradient(
                    segment.x * gridSize,
                    segment.y * gridSize,
                    (segment.x + 1) * gridSize,
                    (segment.y + 1) * gridSize
                );
                gradient.addColorStop(0, '#4CAF50');
                gradient.addColorStop(1, '#45a049');
                ctx.fillStyle = gradient;
                ctx.fillRect(segment.x * gridSize, segment.y * gridSize, gridSize - 2, gridSize - 2);

                if (index === 0) {
                    // Draw eyes
                    ctx.fillStyle = 'white';
                    ctx.beginPath();
                    ctx.arc(segment.x * gridSize + 5, segment.y * gridSize + 5, 2, 0, 2 * Math.PI);
                    ctx.arc(segment.x * gridSize + 10, segment.y * gridSize + 5, 2, 0, 2 * Math.PI);
                    ctx.fill();
                }
            });
        }

        function drawFood() {
            const gradient = ctx.createRadialGradient(
                food.x * gridSize + gridSize / 2,
                food.y * gridSize + gridSize / 2,
                2,
                food.x * gridSize + gridSize / 2,
                food.y * gridSize + gridSize / 2,
                gridSize / 2
            );
            gradient.addColorStop(0, '#ff6b6b');
            gradient.addColorStop(1, '#ee5253');
            ctx.fillStyle = gradient;
            ctx.beginPath();
            ctx.arc(food.x * gridSize + gridSize / 2, food.y * gridSize + gridSize / 2, gridSize / 2 - 1, 0, 2 * Math.PI);
            ctx.fill();
        }

        function generateFood() {
            food.x = Math.floor(Math.random() * tileCount);
            food.y = Math.floor(Math.random() * tileCount);
        }

        function checkCollision() {
            const head = snake[0];

            if (head.x < 0 || head.x >= tileCount || head.y < 0 || head.y >= tileCount) {
                gameOver();
            }

            for (let i = 1; i < snake.length; i++) {
                if (head.x === snake[i].x && head.y === snake[i].y) {
                    gameOver();
                }
            }
        }

        function gameOver() {
            gameRunning = false;
            startBtn.textContent = '重新开始';
            startBtn.style.display = 'inline-block';
            alert(`游戏结束！你的得分是: ${score}`);
        }

        function updateScore() {
            scoreElement.textContent = `得分: ${score}`;
        }

        function resetGame() {
            snake = [{ x: 10, y: 10 }];
            food = { x: 15, y: 15 };
            dx = 0;
            dy = 0;
            score = 0;
            updateScore();
        }

        document.addEventListener('keydown', changeDirection);

        function changeDirection(event) {
            const LEFT_KEY = 37;
            const RIGHT_KEY = 39;
            const UP_KEY = 38;
            const DOWN_KEY = 40;

            const keyPressed = event.keyCode;

            const goingUp = dy === -1;
            const goingDown = dy === 1;
            const goingRight = dx === 1;
            const goingLeft = dx === -1;

            if (keyPressed === LEFT_KEY && !goingRight) {
                dx = -1;
                dy = 0;
            }

            if (keyPressed === UP_KEY && !goingDown) {
                dx = 0;
                dy = -1;
            }

            if (keyPressed === RIGHT_KEY && !goingLeft) {
                dx = 1;
                dy = 0;
            }

            if (keyPressed === DOWN_KEY && !goingUp) {
                dx = 0;
                dy = 1;
            }
        }

        function changeDirectionByButton(direction) {
            if (direction === 'left' && dx !== 1) {
                dx = -1;
                dy = 0;
            } else if (direction === 'up' && dy !== 1) {
                dx = 0;
                dy = -1;
            } else if (direction === 'down' && dy !== -1) {
                dx = 0;
                dy = 1;
            } else if (direction === 'right' && dx !== -1) {
                dx = 1;
                dy = 0;
            }
        }

        startBtn.addEventListener('click', () => {
            resetGame();
            gameRunning = true;
            startBtn.style.display = 'none';
            drawGame();
        });

        clearCanvas();
    </script>
</body>

</html>



