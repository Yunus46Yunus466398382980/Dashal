<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Поздравление с 8 марта!</title>
    <script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.5.1/dist/confetti.browser.min.js"></script>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <div class="container">
        <h1>С 8 Марта!</h1>
        <div class="flower">🌸</div>
        <p class="message">Дорогая Даша, с праздником весны и красоты! 💐</p>
        <div class="heart">
        <button onclick="fireworks()" class="serdse">

            
            ❤️
        </button>    
        
        
        </div>
        
        <!-- Падающие цветы -->
        <div class="falling-flower" style="left: 20%; animation-delay: 0s;">🌼</div>
        <div class="falling-flower" style="left: 40%; animation-delay: 1s;">🌷</div>
        <div class="falling-flower" style="left: 60%; animation-delay: 2s;">💐</div>
        <div class="falling-flower" style="left: 80%; animation-delay: 3s;">🌸</div>
    </div>




    <script>
        function fireworks() {
            const duration = 3 * 1000; // Длительность 3 секунды
            const end = Date.now() + duration;

            (function frame() {
                confetti({
                    particleCount: 5,
                    angle: Math.random() * 360,
                    spread: 60,
                    origin: { x: Math.random(), y: Math.random() * 0.6 }
                });

                if (Date.now() < end) {
                    requestAnimationFrame(frame);
                }
            })();
        }
    </script>

</body>
</html>

body {
    text-align: center;
    padding-top: 100px;
}
button {
    font-size: 20px;
    padding: 10px 20px;
    cursor: pointer;
}
body {
    margin: 0;
    padding: 0;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    background-color: #f5f5f5;
    font-family: 'Arial', sans-serif;
    overflow: hidden;
}

.container {
    text-align: center;
    position: relative;
}

h1 {
    font-size: 3rem;
    color: #e91e63;
    margin: 0;
    animation: titleAnimation 2s ease-in-out;
}

@keyframes titleAnimation {
    0% {
        transform: scale(0);
        opacity: 0;
    }
    50% {
        transform: scale(1.2);
        opacity: 1;
    }
    100% {
        transform: scale(1);
    }
}

.flower {
    font-size: 3rem;
    animation: flowerAnimation 2s ease-in-out infinite alternate;
}

@keyframes flowerAnimation {
    0% {
        transform: rotate(0deg);
    }
    50% {
        transform: rotate(20deg);
    }
    100% {
        transform: rotate(0deg);
    }
}

.message {
    font-size: 2rem;
    color: #ff4081;
    animation: fadeIn 3s ease-in-out;
    margin-top: 20px;
}

@keyframes fadeIn {
    0% {
        opacity: 0;
        transform: translateY(-50px);
    }
    100% {
        opacity: 1;
        transform: translateY(0);
    }
}

.heart {
    color: red;
    font-size: 3rem;
    animation: pulseHeart 1.5s ease-in-out infinite;
}

@keyframes pulseHeart {
    0% {
        transform: scale(1);
    }
    50% {
        transform: scale(1.2);
    }
    100% {
        transform: scale(1);
    }
}

/* Анимация для падающих цветков */
.falling-flower {
    position: absolute;
    animation: fall 5s linear infinite;
}

@keyframes fall {
    0% {
        top: -50px;
        left: 50%;
        transform: translateX(-50%) rotate(0deg);
    }
    100% {
        top: 100vh;
        transform: translateX(-50%) rotate(360deg);
    }
}

.serdse{
border: none;
background-color: transparent;
font-size: 50px;
}
