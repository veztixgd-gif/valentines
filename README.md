<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cute Valentine's Day</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background: radial-gradient(circle at 20% 50%, #ffcccc 0%, #ffb3ba 25%, #ff69b4 50%, #ff1493 75%, #dc143c 100%);
            color: #d63384;
            text-align: center;
            margin: 0;
            padding: 0;
            overflow-x: hidden;
            position: relative;
        }

        /* Static heart decorations around the edges */
        body::before {
            content: "💖 💕 💓 💖 💕 💓";
            position: absolute;
            top: 10px;
            left: 10px;
            font-size: 1.5em;
            opacity: 0.5;
            pointer-events: none;
        }

        body::after {
            content: "💓 💖 💕 💓 💖 💕";
            position: absolute;
            bottom: 10px;
            right: 10px;
            font-size: 1.5em;
            opacity: 0.5;
            pointer-events: none;
        }

        header {
            background: #ff69b4;
            padding: 20px;
            border-radius: 0 0 50% 50%;
            position: relative;
            z-index: 1;
        }

        h1 {
            margin: 0;
            font-size: 2.5em;
        }

        main {
            padding: 20px;
            max-width: 600px;
            margin: 0 auto;
            position: relative;
            z-index: 1;
        }

        .heart-container {
            margin: 20px 0;
        }

        .heart {
            font-size: 5em;
            cursor: pointer;
            transition: transform 0.3s;
        }

        .heart:hover {
            transform: scale(1.2);
        }

        button {
            background: #ff1493;
            color: white;
            border: none;
            padding: 10px 20px;
            font-size: 1.2em;
            border-radius: 25px;
            cursor: pointer;
            margin: 10px;
            position: relative; /* For movement */
            transition: all 0.5s ease; /* Smooth movement */
        }

        button:hover {
            background: #dc143c;
        }

        #love-message {
            margin-top: 20px;
            font-size: 1.5em;
            font-style: italic;
            background: rgba(255, 255, 255, 0.8);
            padding: 15px;
            border-radius: 15px;
            box-shadow: 0 0 10px rgba(255, 105, 180, 0.5);
        }

        .floating-hearts {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            overflow: hidden;
            z-index: 0;
        }

        .heart-particle, .chocolate-particle, .tulip-particle {
            position: absolute;
            font-size: 2em;
            animation: float 5s linear infinite;
            opacity: 0.8;
        }

        .heart-particle {
            color: #ff69b4;
        }

        .chocolate-particle {
            color: #8B4513; /* Brown for chocolate */
        }

        .tulip-particle {
            color: #ff69b4; /* Pink for tulips */
        }

        .heart-particle:nth-child(odd) {
            font-size: 1.5em;
            animation-duration: 6s;
        }

        .heart-particle:nth-child(even) {
            font-size: 2.5em;
            animation-duration: 4s;
        }

        .tulip-particle:nth-child(odd) {
            font-size: 1.8em;
            animation-duration: 7s;
        }

        @keyframes float {
            0% { transform: translateY(100vh) rotate(0deg); opacity: 1; }
            100% { transform: translateY(-100px) rotate(360deg); opacity: 0; }
        }

        @keyframes beat {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.3); }
        }

        footer {
            background: #ffb3ba;
            padding: 10px;
            position: fixed;
            bottom: 0;
            width: 100%;
            z-index: 1;
        }
    </style>
</head>
<body>
    <header>
        <h1>Happy Valentines Day Elay! 💖</h1>
    </header>
    <main>
        <div class="heart-container">
            <div class="heart" id="clickable-heart">🐱</div>
            <p id="message">Click the heart for a surprise!</p>
        </div>
        <button id="generate-message">click mo to elay dali!! 🌷💖</button>
        <div id="love-message"></div>
        <div class="floating-hearts"></div>
    </main>
    <footer>
        <p>lapit na din birthday mo march 14</p>
    </footer>
    <script>
        // Array of cute love messages (now with your custom message)
        const messages = [
            "Happy Valentine’s Day! I know this is kind of random, but I tried making a website and a message to put in some effort since I had nothing else to do. Even though we don’t really talk or interact much anymore, I still wish for your happiness and wellbeing. If I had one more chance to prove my love again, I would—if you’d allow me. But it’s okay if not, because I can accept that. I still like you, Elay, but since I made mistakes with you, I accept those wrongs and I want to show that I won’t be like that again. Still, it’s up to you. I just want you to know how I feel about you. I want to get to know you more, and I’m always interested in you. I sometimes wonder how you’re doing, because I don’t want anyone else unless it’s you. You still deserve to be loved and to receive flowers or messages like this, maybe not from me but from other people you want in your life. Anyway, good luck on your upcoming exams and with more challenges in life. Happy Valentine’s Day again 🥰🥰"
        ];

        // Playful button sequence with movement
        let clickCount = 0;
        const button = document.getElementById('generate-message');
        button.addEventListener('click', () => {
            clickCount++;
            if (clickCount === 1) {
                // First click: Move more to upper right, change text to "click mo ulet"
                button.textContent = 'click mo ulet';
                button.style.position = 'absolute';
                button.style.top = '10%'; // More upper
                button.style.right = '5%'; // More right
                button.style.left = 'auto';
            } else if (clickCount === 2) {
                // Second click: Move to middle, change text to "click mo din yung pusa na emoji pala"
                button.textContent = 'click mo din yung pusa na emoji pala';
                button.style.top = '50%';
                button.style.left = '50%';
                button.style.transform = 'translate(-50%, -50%)';
            } else if (clickCount === 3) {
                // Third click: Move to lower left side, change text to "basahin mo lahat ha"
                button.textContent = 'basahin mo lahat ha';
                button.style.top = '70%';
                button.style.left = '10%';
                button.style.transform = 'none';
            } else if (clickCount === 4) {
                // Fourth click: Move back to center, reset text, show message, and hide the button
                button.textContent = 'click mo to elay dali!! 🌷💖';
                button.style.position = 'relative';
                button.style.top = 'auto';
                button.style.left = 'auto';
                button.style.right = 'auto';
                button.style.transform = 'none';
                document.getElementById('love-message').textContent = messages[0];
                // Hide the button so it can't be clicked again
                button.style.display = 'none';
                clickCount = 0; // Reset counter for replay (though button is hidden)
            }
        });

        // Heart click interaction - now shows cute cat gif AND the text
        document.getElementById('clickable-heart').addEventListener('click', () => {
            const heart = document.getElementById('clickable-heart');
            heart.style.animation = 'beat 0.5s';
            setTimeout(() => heart.style.animation = '', 500);
            document.getElementById('message').innerHTML = '<img src="https://media.giphy.com/media/vFKqnCdLPNOKc/giphy.gif" alt="Cute Cat" style="width: 200px; height: auto; border-radius: 10px; display: block; margin: 0 auto;"><br><span style="font-size: 1.2em; color: #d63384;">syempre eto parin si makulit na jazzie HAHAHAHAHA</span>';
        });

        // Floating hearts, chocolates, and tulips animation with variety
        const heartEmojis = ['💖', '💕', '💓', '❤️'];
        function createHeart() {
            const heart = document.createElement('div');
            heart.className = 'heart-particle';
            heart.textContent = heartEmojis[Math.floor(Math.random() * heartEmojis.length)];
            heart.style.left = Math.random() * 100 + 'vw';
            heart.style.animationDelay = Math.random() * 5 + 's';
            document.querySelector('.floating-hearts').appendChild(heart);
            setTimeout(() => heart.remove(), 5000);
        }

        function createChocolate() {
            const chocolate = document.createElement('div');
            chocolate.className = 'chocolate-particle';
            chocolate.textContent = '🍫';
            chocolate.style.left = Math.random() * 100 + 'vw';
            chocolate.style.animationDelay = Math.random() * 5 + 's';
            document.querySelector('.floating-hearts').appendChild(chocolate);
            setTimeout(() => chocolate.remove(), 5000);
        }

        function createTulip() {
            const tulip = document.createElement('div');
            tulip.className = 'tulip-particle';
            tulip.textContent = '🌷';
            tulip.style.left = Math.random() * 100 + 'vw';
            tulip.style.animationDelay = Math.random() * 5 + 's';
            document.querySelector('.floating-hearts').appendChild(tulip);
            setTimeout(() => tulip.remove(), 5000);
        }

        // Create hearts, chocolates, and tulips periodically
        setInterval(createHeart, 600);
        setInterval(createChocolate, 1000);
        setInterval(createTulip, 800); // Tulips at a medium frequency for balance
    </script>
</body>
</html>
