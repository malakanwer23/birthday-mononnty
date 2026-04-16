
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="A cute birthday greeting page for Mononnty">
    <title>Happy Birthday Mononnty! 🎉</title>
    <style>
        /* Import Google Fonts for a modern, cute typography */
        @import url('https://fonts.googleapis.com/css2?family=Fredoka:wght@400;600&family=Poppins:wght@400;500;600&display=swap');

        /* CSS Variables for color palette */
        :root {
            --primary-pink: #ff9a9e;
            --secondary-pink: #fecfef;
            --text-dark: #5a3e4b;
            --text-highlight: #d15c7a;
            --btn-gradient-start: #ff758c;
            --btn-gradient-end: #ff7eb3;
        }

        /* Base Reset & Styling */
        body, html {
            margin: 0;
            padding: 0;
            width: 100%;
            min-height: 100vh;
            font-family: 'Poppins', sans-serif;
            background: linear-gradient(135deg, var(--primary-pink) 0%, var(--secondary-pink) 100%);
            overflow-x: hidden; /* Prevent horizontal scroll */
            display: flex;
            justify-content: center;
            align-items: center;
            color: var(--text-dark);
            position: relative;
        }

        /* Float Hearts Background Container */
        .hearts-container {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            overflow: hidden;
            pointer-events: none; /* Let clicks pass through */
            z-index: 1;
        }

        /* Glassmorphism Main Content Container */
        .container {
            background: rgba(255, 255, 255, 0.45);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px); /* Safari support */
            border-radius: 30px;
            padding: 40px 30px;
            width: 90%;
            max-width: 450px;
            text-align: center;
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.08);
            border: 1px solid rgba(255, 255, 255, 0.6);
            position: relative;
            z-index: 10;
            
            /* Initial animation */
            transform: translateY(30px);
            opacity: 0;
            animation: slideUpFade 1.2s ease forwards;
        }

        @keyframes slideUpFade {
            to {
                transform: translateY(0);
                opacity: 1;
            }
        }

        /* Circular Placeholder Image */
        .profile-img {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            object-fit: cover;
            border: 5px solid white;
            box-shadow: 0 10px 25px rgba(255, 154, 158, 0.4);
            margin: 0 auto 20px;
            display: block;
            background: #ffe5ec;
            transition: transform 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        }

        .profile-img:hover {
            transform: scale(1.08) rotate(3deg);
        }

        /* Animated Title */
        h1 {
            font-family: 'Fredoka', sans-serif;
            font-size: 2.2rem;
            margin: 0 0 10px 0;
            color: var(--text-highlight);
            
            /* Entry Animation */
            opacity: 0;
            transform: scale(0.8);
            animation: bounceIn 1s cubic-bezier(0.175, 0.885, 0.32, 1.275) forwards;
            animation-delay: 0.5s;
        }

        @keyframes bounceIn {
            to {
                opacity: 1;
                transform: scale(1);
            }
        }

        /* Message Text */
        p.message {
            font-size: 1.05rem;
            line-height: 1.6;
            margin-bottom: 25px;
            color: var(--text-dark);
            font-weight: 500;
        }

        /* Styled Button */
        button {
            background: linear-gradient(45deg, var(--btn-gradient-start) 0%, var(--btn-gradient-end) 100%);
            border: none;
            padding: 14px 28px;
            border-radius: 30px;
            color: white;
            font-family: 'Poppins', sans-serif;
            font-size: 1.05rem;
            font-weight: 600;
            cursor: pointer;
            box-shadow: 0 8px 15px rgba(255, 117, 140, 0.3);
            transition: all 0.3s ease;
            outline: none;
            position: relative;
            overflow: hidden;
        }

        button:hover {
            transform: translateY(-3px);
            box-shadow: 0 12px 20px rgba(255, 117, 140, 0.45);
        }

        button:active {
            transform: translateY(1px);
        }

        /* Hidden Surprise Message */
        .surprise-text {
            margin-top: 20px;
            background: rgba(255, 255, 255, 0.7);
            border-radius: 15px;
            font-size: 1.05rem;
            font-weight: 600;
            color: var(--text-highlight);
            border: 2px dashed var(--primary-pink);
            
            /* Setup for fade/slide animation */
            opacity: 0;
            max-height: 0;
            padding: 0 20px; /* Horizontal padding only initially */
            overflow: hidden;
            transform: translateY(-10px);
            transition: all 0.6s cubic-bezier(0.4, 0, 0.2, 1);
        }

        /* Revealed State */
        .surprise-text.show {
            opacity: 1;
            max-height: 300px;
            padding: 20px;
            transform: translateY(0);
        }

        /* Individual Floating Elements (Hearts/Confetti) */
        .heart-icon {
            position: absolute;
            bottom: -50px; /* Start below the screen */
            width: 30px;
            height: 30px;
            background-color: transparent;
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 24px;
            animation: floatUp linear infinite;
        }

        /* Keyframes for endless floating upwards */
        @keyframes floatUp {
            0% {
                transform: translateY(0) scale(0.5) rotate(0deg);
                opacity: 0;
            }
            15% {
                opacity: 0.9;
            }
            85% {
                opacity: 0.9;
            }
            100% {
                /* Float above viewing area */
                transform: translateY(-110vh) scale(1.5) rotate(360deg);
                opacity: 0;
            }
        }

        /* Responsive Adjustments */
        @media (max-width: 480px) {
            .container {
                padding: 30px 20px;
                border-radius: 20px;
            }
            h1 { font-size: 1.8rem; }
            .profile-img { width: 120px; height: 120px; border-width: 4px; }
            p.message { font-size: 0.95rem; }
            button { font-size: 0.95rem; padding: 12px 24px;}
            .surprise-text { font-size: 0.95rem; }
        }
    </style>
</head>
<body>

    <!-- Container for dynamic background items -->
    <div class="hearts-container" id="heartsContainer"></div>

    <!-- Main Card -->
    <div class="container">
        <!-- Profile Image Placeholder (Using high quality aesthetic placeholder) -->
        <img src="images/manona.jpeg" class="profile-img">
        
        <!-- Big Animated Title -->
        <h1>Happy Birthday Mononnty! 🎉</h1>
        
        <!-- Heartfelt Message -->
        <p class="message">
            Wishing you a day painted in pastel colors, filled with pure joy, and wrapped in endless happiness. You deserve the absolute brightest smile on your special day! 💖
        </p>
        
        <!-- Interactive Button -->
        <button id="surpriseBtn" onclick="revealSurprise()">Click for a Surprise 🎁</button>

        <!-- Hidden Sweet Message to be revealed -->
        <div id="surpriseMessage" class="surprise-text">
            ✨ Yay! ✨<br>
            You are incredibly wonderful and bring so much light everywhere you go. Keep shining, stay sweet, and have the most beautiful birthday ever! 🍰🌸🎈
        </div>
    </div>

    <!-- Interaction & Animation Logic -->
    <script>
        // Reveal surprise message when button is clicked
        function revealSurprise() {
            const msg = document.getElementById("surpriseMessage");
            const btn = document.getElementById("surpriseBtn");
            
            // Trigger CSS transition
            msg.classList.add("show");
            
            // Alter the button state
            btn.innerText = "Enjoy your day! 💕";
            btn.style.pointerEvents = "none";
            btn.style.opacity = "0.7";

            // Add an extra burst of hearts/emojis!
            createFloatingItems(15, true);
        }

        // Generate floating animations dynamically
        function createFloatingItems(amount, isBurst = false) {
            const container = document.getElementById("heartsContainer");
            // Array of cute emojis to float around
            const floatingEmojis = ['💖', '💕', '🌸', '✨', '🎈', '🎉'];
            
            for (let i = 0; i < amount; i++) {
                const item = document.createElement("div");
                item.classList.add("heart-icon");
                
                // Pick a random emoji from the list
                item.innerText = floatingEmojis[Math.floor(Math.random() * floatingEmojis.length)];
                
                // Random horizontal positioning (0 to 100 viewport width)
                item.style.left = Math.random() * 100 + "vw";
                
                // Random duration for how fast it floats
                const duration = Math.random() * 7 + 4; // between 4s and 11s
                item.style.animationDuration = duration + "s";
                
                // Random start delay
                const delay = isBurst ? (Math.random() * 0.5) : (Math.random() * 5);
                item.style.animationDelay = delay + "s";

                // Faster animation if it's a burst
                if (isBurst) {
                    item.style.animationDuration = (duration * 0.4) + "s";
                    // Remove burst elements after they finish one cycle
                    setTimeout(() => {
                        item.remove();
                    }, duration * 0.4 * 1000);
                }

                container.appendChild(item);
            }
        }

        // On page load, initialize the continuous background floaters
        window.onload = () => {
            createFloatingItems(25);
        };
    </script>
</body>
</html>
