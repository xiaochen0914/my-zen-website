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

