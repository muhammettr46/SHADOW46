<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Öğretmenler Günü</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background: linear-gradient(to bottom, #e5e2dd, #a38824);
            font-family: 'Arial', sans-serif;
            overflow: hidden;
        }
        h1 {
            font-size: 3em;
            color: #e0cabb;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
            margin-bottom: 20px;
            animation: fadeIn 3s ease-in-out;
        }
        img {
            width: 150px;
            height: auto;
            border-radius: 50%;
            box-shadow: 0 4px 8px rgba(208, 199, 199, 0.3);
            margin-bottom: 10px;
            animation: bounce 3s infinite;
        }
        .quote {
            font-size: 1.2em;
            color: #f5dfdf;
            text-align: center;
            margin-bottom: 40px;
            font-style: italic;
            animation: fadeIn 3s ease-in-out 2s;
        }
        .message {
            position: absolute;
            bottom: -50px;
            font-size: 1.2em;
            color: #fff4f4;
            animation: float 5s infinite ease-in-out;
        }
        .hearts {
            position: absolute;
            bottom: 20px;
            display: flex;
            gap: 10px;
            animation: fadeIn 3s ease-in-out;
        }
        .heart {
            width: 30px;
            height: 30px;
            background: rgb(227, 222, 222);
            position: relative;
            transform: rotate(-45deg);
            animation: floatHearts 5s infinite ease-in-out;
        }
        .heart::before, .heart::after {
            content: '';
            width: 30px;
            height: 30px;
            background: rgb(239, 237, 237);
            border-radius: 50%;
            position: absolute;
        }
        .heart::before {
            top: -15px;
            left: 0;
        }
        .heart::after {
            left: -15px;
            top: 0;
        }
        @keyframes float {
            0% {
                transform: translateY(100px);
                opacity: 0;
            }
            50% {
                transform: translateY(-50px);
                opacity: 1;
            }
            100% {
                transform: translateY(-200px);
                opacity: 0;
            }
        }
        @keyframes fadeIn {
            from {
                opacity: 0;
            }
            to {
                opacity: 1;
            }
        }
        @keyframes bounce {
            0%, 100% {
                transform: translateY(0);
            }
            50% {
                transform: translateY(-10px);
            }
        }
        @keyframes floatHearts {
            0% {
                transform: rotate(-45deg) translateY(0);
                opacity: 1;
            }
            100% {
                transform: rotate(-45deg) translateY(-200px);
                opacity: 0;
            }
        }
    </style>
</head>
<body>
    <h1>Öğretmenler Günü Kutlu Olsun! 🌟</h1>
    <p class="quote">"Yeni nesil, sizlerin eseri olacaktır." - Mustafa Kemal Atatürk</p>
    <div class="hearts">
        <div class="heart" style="animation-delay: 0s;"></div>
        <div class="heart" style="animation-delay: 1s;"></div>
        <div class="heart" style="animation-delay: 2s;"></div>
    </div>
    <script>
        const messages = [
            "İyi ki varsınız!",
            "Eğitim bir fidan, sizler bahçıvan!",
            "Sabır ve özveriniz için teşekkürler!",
            "Öğretmen bir mum gibi, ışık saçar!",
            "Başöğretmenimizin izindeyiz!",
            "Öğretmen diye yazılır fakat taşıdığı anlam büyüktür!"
        ];

        const createMessage = (text) => {
            const div = document.createElement("div");
            div.className = "message";
            div.textContent = text;
            div.style.left = `${Math.random() * 80 + 10}%`;
            div.style.animationDelay = `${Math.random() * 0.1}s`;
            document.body.appendChild(div);

            setTimeout(() => {
                div.remove();
            }, 5000);
        };

        setInterval(() => {
            const randomMessage = messages[Math.floor(Math.random() * messages.length)];
            createMessage(randomMessage);
        }, 2000);
    </script>
</body>
</html>
