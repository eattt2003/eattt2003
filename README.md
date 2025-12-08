<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Lina's Cute Homepage ✨</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Comic Sans MS', 'Arial Rounded MT Bold', cursive;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            overflow-x: hidden;
            position: relative;
        }

        /* 漂浮的云朵背景 */
        .cloud {
            position: absolute;
            background: rgba(255, 255, 255, 0.3);
            border-radius: 100px;
            animation: float 20s infinite ease-in-out;
        }

        .cloud1 { width: 100px; height: 40px; top: 10%; left: -100px; animation-delay: 0s; }
        .cloud2 { width: 140px; height: 50px; top: 30%; left: -140px; animation-delay: 5s; }
        .cloud3 { width: 80px; height: 35px; top: 60%; left: -80px; animation-delay: 10s; }

        @keyframes float {
            0%, 100% { transform: translateX(0); }
            50% { transform: translateX(calc(100vw + 200px)); }
        }

        /* 主容器 */
        .container {
            max-width: 900px;
            margin: 50px auto;
            padding: 20px;
            position: relative;
            z-index: 10;
        }

        /* 头部卡片 */
        .header-card {
            background: white;
            border-radius: 30px;
            padding: 40px;
            text-align: center;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
            margin-bottom: 30px;
            position: relative;
            overflow: hidden;
            animation: slideDown 0.8s ease-out;
        }

        @keyframes slideDown {
            from { opacity: 0; transform: translateY(-50px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .avatar-container {
            position: relative;
            display: inline-block;
            margin-bottom: 20px;
        }

        .avatar {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            border: 5px solid #ff6b9d;
            animation: bounce 2s infinite;
            cursor: pointer;
            transition: transform 0.3s;
        }

        .avatar:hover {
            transform: scale(1.1) rotate(5deg);
        }

        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }

        .sparkle {
            position: absolute;
            width: 20px;
            height: 20px;
            background: #ffd700;
            clip-path: polygon(50% 0%, 61% 35%, 98% 35%, 68% 57%, 79% 91%, 50% 70%, 21% 91%, 32% 57%, 2% 35%, 39% 35%);
            animation: sparkle 1.5s infinite;
        }

        .sparkle1 { top: 10px; left: 10px; animation-delay: 0s; }
        .sparkle2 { top: 10px; right: 10px; animation-delay: 0.5s; }
        .sparkle3 { bottom: 10px; left: 10px; animation-delay: 1s; }

        @keyframes sparkle {
            0%, 100% { opacity: 0; transform: scale(0) rotate(0deg); }
            50% { opacity: 1; transform: scale(1) rotate(180deg); }
        }

        h1 {
            color: #ff6b9d;
            font-size: 2.5em;
            margin: 10px 0;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.1);
        }

        .subtitle {
            color: #666;
            font-size: 1.2em;
            margin: 10px 0;
        }

        /* 食物区域 */
        .food-section {
            background: white;
            border-radius: 30px;
            padding: 40px;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
            margin-bottom: 30px;
            animation: slideUp 0.8s ease-out 0.2s both;
        }

        @keyframes slideUp {
            from { opacity: 0; transform: translateY(50px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .section-title {
            color: #667eea;
            font-size: 2em;
            text-align: center;
            margin-bottom: 30px;
            position: relative;
        }

        .section-title::after {
            content: '✨';
            margin-left: 10px;
            animation: rotate 2s linear infinite;
        }

        @keyframes rotate {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }

        .food-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin-top: 20px;
        }

        .food-item {
            background: linear-gradient(135deg, #ffecd2 0%, #fcb69f 100%);
            border-radius: 20px;
            padding: 20px;
            text-align: center;
            cursor: pointer;
            transition: all 0.3s;
            position: relative;
            overflow: hidden;
        }

        .food-item:hover {
            transform: translateY(-10px) scale(1.05);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
        }

        .food-item::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255, 255, 255, 0.3) 0%, transparent 70%);
            transform: scale(0);
            transition: transform 0.5s;
        }

        .food-item:hover::before {
            transform: scale(1);
        }

        .food-emoji {
            font-size: 4em;
            display: block;
            margin-bottom: 10px;
            animation: wiggle 1s ease-in-out infinite;
        }

        @keyframes wiggle {
            0%, 100% { transform: rotate(0deg); }
            25% { transform: rotate(-5deg); }
            75% { transform: rotate(5deg); }
        }

        .food-item:hover .food-emoji {
            animation: jump 0.5s;
        }

        @keyframes jump {
            0%, 100% { transform: translateY(0) scale(1); }
            50% { transform: translateY(-20px) scale(1.2); }
        }

        .food-name {
            font-size: 1.3em;
            color: #333;
            font-weight: bold;
            margin-bottom: 5px;
        }

        .food-desc {
            color: #666;
            font-size: 1em;
        }

        /* 空调区域 */
        .ac-section {
            background: linear-gradient(135deg, #a8edea 0%, #fed6e3 100%);
            border-radius: 30px;
            padding: 40px;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
            margin-bottom: 30px;
            text-align: center;
            animation: slideUp 0.8s ease-out 0.4s both;
            position: relative;
        }

        .ac-button {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            border: none;
            padding: 15px 40px;
            font-size: 1.2em;
            border-radius: 50px;
            cursor: pointer;
            transition: all 0.3s;
            font-family: inherit;
            margin-top: 20px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }

        .ac-button:hover {
            transform: scale(1.1);
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.3);
        }

        .ac-button:active {
            transform: scale(0.95);
        }

        .cold-effect {
            position: absolute;
            font-size: 2em;
            animation: fall 3s linear infinite;
            opacity: 0;
        }

        @keyframes fall {
            0% { top: -50px; opacity: 1; }
            100% { top: 100%; opacity: 0; }
        }

        /* 联系方式 */
        .contact-section {
            background: white;
            border-radius: 30px;
            padding: 40px;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
            text-align: center;
            animation: slideUp 0.8s ease-out 0.6s both;
        }

        .contact-buttons {
            display: flex;
            justify-content: center;
            gap: 20px;
            flex-wrap: wrap;
            margin-top: 20px;
        }

        .contact-btn {
            display: inline-flex;
            align-items: center;
            gap: 10px;
            padding: 15px 30px;
            background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
            color: white;
            text-decoration: none;
            border-radius: 50px;
            font-size: 1.1em;
            transition: all 0.3s;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }

        .contact-btn:hover {
            transform: translateY(-5px) scale(1.05);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
        }

        .contact-btn.linkedin {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
        }

        /* 响应式设计 */
        @media (max-width: 768px) {
            .container {
                padding: 10px;
            }

            h1 {
                font-size: 2em;
            }

            .food-grid {
                grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            }

            .contact-buttons {
                flex-direction: column;
            }
        }

        /* 鼠标跟随效果 */
        .cursor-follow {
            position: fixed;
            width: 20px;
            height: 20px;
            background: rgba(255, 107, 157, 0.6);
            border-radius: 50%;
            pointer-events: none;
            z-index: 9999;
            transition: transform 0.1s;
        }
    </style>
</head>
<body>
    <!-- 云朵背景 -->
    <div class="cloud cloud1"></div>
    <div class="cloud cloud2"></div>
    <div class="cloud cloud3"></div>

    <!-- 鼠标跟随 -->
    <div class="cursor-follow" id="cursorFollow"></div>

    <div class="container">
        <!-- 头部卡片 -->
        <div class="header-card">
            <div class="avatar-container">
                <div class="sparkle sparkle1"></div>
                <div class="sparkle sparkle2"></div>
                <div class="sparkle sparkle3"></div>
                <img src="https://media.giphy.com/media/WOwiryOPA0G6jhKqB0/giphy.gif" alt="Lina" class="avatar" id="avatar">
            </div>
            <h1>Hi! I'm Lina! 👋</h1>
            <p class="subtitle">🌸 Welcome to my cute homepage! 🌸</p>
            <p class="subtitle">✨ AI Researcher | Food Lover | Life Enjoyer ✨</p>
        </div>

        <!-- 食物区域 -->
        <div class="food-section">
            <h2 class="section-title">🍽️ My Favorite Foods</h2>
            <p style="text-align: center; color: #666; margin-bottom: 20px;">Click on the food to see magic! ✨</p>
            <div class="food-grid">
                <div class="food-item" onclick="eatFood(this, '🍕')">
                    <span class="food-emoji">🍕</span>
                    <div class="food-name">Pizza</div>
                    <div class="food-desc">Great!</div>
                </div>
                <div class="food-item" onclick="eatFood(this, '🍣')">
                    <span class="food-emoji">🍣</span>
                    <div class="food-name">Sushi</div>
                    <div class="food-desc">Wonderful!</div>
                </div>
                <div class="food-item" onclick="eatFood(this, '🍦')">
                    <span class="food-emoji">🍦</span>
                    <div class="food-name">Ice Cream</div>
                    <div class="food-desc">Perfect!</div>
                </div>
                <div class="food-item" onclick="eatFood(this, '🍜')">
                    <span class="food-emoji">🍜</span>
                    <div class="food-name">Ramen</div>
                    <div class="food-desc">Woww!</div>
                </div>
            </div>
        </div>

        <!-- 空调区域 -->
        <div class="ac-section" id="acSection">
            <h2 class="section-title">❄️ Cool Air Station</h2>
            <img src="https://media.giphy.com/media/l41YoV54ZT606BGO4/giphy.gif" width="150" alt="Air Conditioner" style="margin: 20px 0;">
            <p style="font-size: 1.3em; color: #333; margin: 20px 0;">
                <strong>🌞 Summer is here! 🌞</strong>
            </p>
            <p style="font-size: 1.1em; color: #666;">
                Click the button to feel the cool breeze!
            </p>
            <button class="ac-button" onclick="turnOnAC()">
                Turn On AC ❄️
            </button>
        </div>

        <!-- 联系方式 -->
        <div class="contact-section">
            <h2 class="section-title">💌 Connect With Me</h2>
            <p style="color: #666; margin: 20px 0;">Let's be friends! 🎉</p>
            <div class="contact-buttons">
                <a href="mailto:JUNWEN003@e.ntu.edu.sg" class="contact-btn">
                    📧 Email Me
                </a>
                <a href="https://www.linkedin.com/in/junwen-zheng-0444a7347/" class="contact-btn linkedin" target="_blank">
                    💼 LinkedIn
                </a>
            </div>
        </div>
    </div>

    <script>
        // 鼠标跟随效果
        const cursorFollow = document.getElementById('cursorFollow');
        document.addEventListener('mousemove', (e) => {
            cursorFollow.style.left = e.clientX - 10 + 'px';
            cursorFollow.style.top = e.clientY - 10 + 'px';
        });

        // 头像点击效果
        document.getElementById('avatar').addEventListener('click', function() {
            this.style.animation = 'none';
            setTimeout(() => {
                this.style.animation = 'bounce 2s infinite';
            }, 10);
            
            // 创建心形特效
            for (let i = 0; i < 10; i++) {
                setTimeout(() => {
                    createHeart(this);
                }, i * 100);
            }
        });

        function createHeart(element) {
            const heart = document.createElement('div');
            heart.innerHTML = '💖';
            heart.style.position = 'fixed';
            heart.style.fontSize = '2em';
            heart.style.zIndex = '9999';
            heart.style.pointerEvents = 'none';
            
            const rect = element.getBoundingClientRect();
            heart.style.left = rect.left + rect.width / 2 + 'px';
            heart.style.top = rect.top + rect.height / 2 + 'px';
            
            document.body.appendChild(heart);
            
            const angle = Math.random() * Math.PI * 2;
            const distance = 100 + Math.random() * 100;
            const endX = Math.cos(angle) * distance;
            const endY = Math.sin(angle) * distance;
            
            heart.animate([
                { transform: 'translate(0, 0) scale(1)', opacity: 1 },
                { transform: `translate(${endX}px, ${endY}px) scale(0)`, opacity: 0 }
            ], {
                duration: 1000,
                easing: 'ease-out'
            }).onfinish = () => heart.remove();
        }

        // 食物点击效果
        function eatFood(element, emoji) {
            // 创建飘落的食物
            for (let i = 0; i < 8; i++) {
                setTimeout(() => {
                    createFallingEmoji(emoji, element);
                }, i * 50);
            }
            
            // 振动效果
            element.style.animation = 'none';
            setTimeout(() => {
                element.style.animation = '';
            }, 10);
        }

        function createFallingEmoji(emoji, element) {
            const fall = document.createElement('div');
            fall.innerHTML = emoji;
            fall.style.position = 'fixed';
            fall.style.fontSize = '2em';
            fall.style.zIndex = '9999';
            fall.style.pointerEvents = 'none';
            
            const rect = element.getBoundingClientRect();
            fall.style.left = rect.left + Math.random() * rect.width + 'px';
            fall.style.top = rect.top + 'px';
            
            document.body.appendChild(fall);
            
            fall.animate([
                { transform: 'translateY(0) rotate(0deg)', opacity: 1 },
                { transform: `translateY(${window.innerHeight}px) rotate(${360 + Math.random() * 360}deg)`, opacity: 0 }
            ], {
                duration: 2000 + Math.random() * 1000,
                easing: 'ease-in'
            }).onfinish = () => fall.remove();
        }

        // 空调效果
        function turnOnAC() {
            const acSection = document.getElementById('acSection');
            const button = event.target;
            
            button.innerHTML = 'AC is ON! ❄️❄️❄️';
            button.style.background = 'linear-gradient(135deg, #a8edea 0%, #fed6e3 100%)';
            
            // 创建冷气效果
            for (let i = 0; i < 30; i++) {
                setTimeout(() => {
                    createColdEffect();
                }, i * 100);
            }
            
            setTimeout(() => {
                button.innerHTML = 'Turn On AC ❄️';
                button.style.background = 'linear-gradient(135deg, #667eea 0%, #764ba2 100%)';
            }, 3000);
        }

        function createColdEffect() {
            const cold = document.createElement('div');
            const effects = ['❄️', '💨', '🧊', '💙'];
            cold.innerHTML = effects[Math.floor(Math.random() * effects.length)];
            cold.className = 'cold-effect';
            cold.style.left = Math.random() * 100 + '%';
            cold.style.animationDuration = (2 + Math.random() * 2) + 's';
            
            document.getElementById('acSection').appendChild(cold);
            
            setTimeout(() => cold.remove(), 3000);
        }

        // 页面加载动画
        window.addEventListener('load', () => {
            document.body.style.opacity = '0';
            setTimeout(() => {
                document.body.style.transition = 'opacity 1s';
                document.body.style.opacity = '1';
            }, 100);
        });
    </script>
</body>
</html>
