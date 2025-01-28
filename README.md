# sexura
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Countdown to November 10, 2025</title>
    <style>
        body {
            margin: 0;
            font-family: Arial, sans-serif;
            color: white;
            text-align: center;
            overflow: hidden;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background: linear-gradient(to bottom, red, pink);
            background-size: 200% 200%;
            animation: gradientMove 8s linear infinite;
        }

        @keyframes gradientMove {
            0% {
                background-position: 0% 50%;
            }
            50% {
                background-position: 100% 50%;
            }
            100% {
                background-position: 0% 50%;
            }
        }

        /* Falling images */
        .falling-image {
            position: absolute;
            width: 30px;
            height: 30px;
            background-image: url('https://cdn.shopify.com/s/files/1/0692/4058/6418/files/2025-01-28_210336.png?v=1738080236');
            background-size: contain;
            background-repeat: no-repeat;
            animation: fall 10s linear infinite;
            z-index: -1;
        }

        @keyframes fall {
            0% {
                transform: translateY(-100vh) scale(0.5);
                opacity: 1;
            }
            100% {
                transform: translateY(100vh) scale(0.8);
                opacity: 0;
            }
        }

        /* Timer and text styles */
        h1 {
            font-size: 2rem;
            margin: 20px 0;
        }

        h2 {
            font-size: 1.5rem;
            margin-bottom: 30px;
        }

        .timer {
            font-size: 3rem;
            margin-bottom: 30px;
            color: #fff;
        }

        /* Button styles */
        .buttons {
            margin-top: 20px;
        }

        .buttons a {
            display: inline-block;
            margin: 10px;
            padding: 15px 20px;
            background: white;
            color: black;
            text-transform: uppercase;
            font-weight: bold;
            border-radius: 5px;
            text-decoration: none;
            transition: 0.3s;
        }

        .buttons a:hover {
            opacity: 0.5;
        }

        /* Mobile optimization for iPhone 13 and 15 */
        @media (max-width: 430px) {
            h1 {
                font-size: 1.5rem;
            }

            h2 {
                font-size: 1.2rem;
            }

            .timer {
                font-size: 2rem;
            }

            .buttons a {
                padding: 10px 15px;
            }
        }
    </style>
</head>
<body>
    <h1>До встречи Егора и Алисы</h1>
    <div class="timer" id="countdown">00d 00h 00m 00s</div>
    <h2>С любовью, до 10 ноября 2025 года</h2>

    <div class="buttons">
        <a href="https://t.me/onmyswitch" target="_blank">Для Егора</a>
        <a href="https://t.me/Doctornefarioo" target="_blank">Для Алисы</a>
    </div>

    <!-- JavaScript for countdown timer and falling images -->
    <script>
        // Countdown timer logic
        const countdownElement = document.getElementById('countdown');
        const targetDate = new Date('2025-11-10T00:00:00+05:00'); // Yekaterinburg time

        function updateCountdown() {
            const now = new Date();
            const diff = targetDate - now;

            if (diff <= 0) {
                countdownElement.textContent = 'The day has arrived!';
                return;
            }

            const days = Math.floor(diff / (1000 * 60 * 60 * 24));
            const hours = Math.floor((diff % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            const minutes = Math.floor((diff % (1000 * 60 * 60)) / (1000 * 60));
            const seconds = Math.floor((diff % (1000 * 60)) / 1000);

            countdownElement.textContent = `${days}d ${hours}h ${minutes}m ${seconds}s`;
        }

        setInterval(updateCountdown, 1000);

        // Falling images animation
        const body = document.body;
        const createFallingImage = () => {
            const img = document.createElement('div');
            img.classList.add('falling-image');
            img.style.left = Math.random() * 100 + 'vw';
            img.style.animationDuration = Math.random() * 3 + 7 + 's';
            body.appendChild(img);

            setTimeout(() => {
                img.remove();
            }, 10000);
        };

        setInterval(createFallingImage, 300);
    </script>
</body>
</html>
