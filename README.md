<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy Birthday Tilak!</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #ff9a9e 0%, #fad0c4 100%);
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            padding: 20px;
            overflow-x: hidden;
        }
        
        .container {
            max-width: 800px;
            width: 100%;
            background-color: rgba(255, 255, 255, 0.9);
            border-radius: 20px;
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.2);
            padding: 40px;
            text-align: center;
            position: relative;
            overflow: hidden;
        }
        
        h1 {
            color: #ff6b6b;
            font-size: 3rem;
            margin-bottom: 20px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.1);
        }
        
        p {
            color: #555;
            font-size: 1.2rem;
            line-height: 1.6;
            margin-bottom: 25px;
        }
        
        .birthday-link {
            display: inline-block;
            background: linear-gradient(to right, #ff6b6b, #ff8e8e);
            color: white;
            padding: 15px 35px;
            border-radius: 50px;
            text-decoration: none;
            font-weight: bold;
            font-size: 1.3rem;
            margin: 25px 0;
            box-shadow: 0 5px 15px rgba(255, 107, 107, 0.4);
            transition: all 0.3s ease;
            cursor: pointer;
        }
        
        .birthday-link:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 20px rgba(255, 107, 107, 0.6);
        }
        
        .birthday-link:active {
            transform: translateY(0);
        }
        
        .message {
            display: none;
            background: linear-gradient(135deg, #a1c4fd 0%, #c2e9fb 100%);
            padding: 30px;
            border-radius: 15px;
            margin-top: 30px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            animation: fadeIn 1s ease;
        }
        
        .message h2 {
            color: #4a69bd;
            font-size: 2.2rem;
            margin-bottom: 15px;
        }
        
        .message p {
            color: #333;
            font-size: 1.2rem;
        }
        
        .confetti {
            position: absolute;
            width: 10px;
            height: 10px;
            background-color: #ff6b6b;
            opacity: 0.8;
            animation: fall linear forwards;
        }
        
        @keyframes fall {
            to {
                transform: translateY(100vh);
                opacity: 0;
            }
        }
        
        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        .cake {
            font-size: 4rem;
            margin: 20px 0;
            animation: bounce 2s infinite;
        }
        
        @keyframes bounce {
            0%, 100% {
                transform: translateY(0);
            }
            50% {
                transform: translateY(-20px);
            }
        }
        
        .footer {
            margin-top: 30px;
            color: #777;
            font-size: 0.9rem;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Happy Birthday Tilak</h1>
        <div class="cake">🎂</div>
        <p>Click the link below to reveal a special birthday message!</p>
        
        <a class="birthday-link" onclick="revealMessage()">Click for your birthday surprise!</a>
        
        <div id="birthdayMessage" class="message">
            <h2>Happy Birthday, Tilak! 🎉</h2>
            <p>Wishing you a day filled with joy, laughter, and all the things that make you smile! May this year bring you success, happiness, and wonderful new opportunities. You deserve the very best!</p>
            <p>Enjoy your special day to the fullest! 🎂🎈🎁</p>
        </div>
        
        <p class="footer">Made with ❤️ for Tilak's special day</p>
    </div>

    <script>
        function revealMessage() {
            const message = document.getElementById('birthdayMessage');
            message.style.display = 'block';
            
            createConfetti();
            
            const link = document.querySelector('.birthday-link');
            link.style.display = 'none';
        }
        
        function createConfetti() {
            const container = document.querySelector('.container');
            const colors = ['#ff6b6b', '#4a69bd', '#ff9a9e', '#a1c4fd', '#fad0c4'];
            
            for (let i = 0; i < 100; i++) {
                const confetti = document.createElement('div');
                confetti.className = 'confetti';
                confetti.style.left = Math.random() * 100 + '%';
                confetti.style.animationDuration = Math.random() * 3 + 2 + 's';
                confetti.style.backgroundColor = colors[Math.floor(Math.random() * colors.length)];
                confetti.style.width = Math.random() * 10 + 5 + 'px';
                confetti.style.height = Math.random() * 10 + 5 + 'px';
                container.appendChild(confetti);
                
                setTimeout(() => {
                    confetti.remove();
                }, 5000);
            }
        }
    </script>
</body>
</html>
