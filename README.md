<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Trevor Coburn | Official Fan Page</title>
    <style>
        :root {
            --primary: #3498db;
            --secondary: #e74c3c;
            --accent1: #f1c40f;
            --accent2: #2ecc71;
            --dark: #2c3e50;
            --light: #ecf0f1;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: var(--light);
            color: var(--dark);
            line-height: 1.6;
            overflow-x: hidden;
            background-image: 
                radial-gradient(circle at 10% 20%, rgba(52, 152, 219, 0.1) 0%, transparent 20%),
                radial-gradient(circle at 90% 30%, rgba(231, 76, 60, 0.1) 0%, transparent 20%),
                radial-gradient(circle at 30% 70%, rgba(241, 196, 15, 0.1) 0%, transparent 20%),
                radial-gradient(circle at 70% 90%, rgba(46, 204, 113, 0.1) 0%, transparent 20%);
        }
        
        .floating {
            position: fixed;
            z-index: -1;
            opacity: 0.7;
            animation: float 15s infinite ease-in-out;
        }
        
        .note1 {
            top: 20%;
            left: 10%;
            font-size: 2rem;
            color: var(--accent1);
            animation-delay: 0s;
            transform: rotate(-15deg);
        }
        
        .note2 {
            top: 60%;
            right: 15%;
            font-size: 2.5rem;
            color: var(--accent2);
            animation-delay: 3s;
            transform: rotate(20deg);
        }
        
        .note3 {
            bottom: 30%;
            left: 20%;
            font-size: 2rem;
            color: var(--primary);
            animation-delay: 6s;
            transform: rotate(5deg);
        }
        
        .note4 {
            top: 40%;
            right: 25%;
            font-size: 1.8rem;
            color: var(--secondary);
            animation-delay: 9s;
            transform: rotate(-10deg);
        }
        
        @keyframes float {
            0% { transform: translate(0, 0) rotate(0deg); }
            25% { transform: translate(-15px, 15px) rotate(5deg); }
            50% { transform: translate(15px, -15px) rotate(-5deg); }
            75% { transform: translate(-15px, -15px) rotate(3deg); }
            100% { transform: translate(0, 0) rotate(0deg); }
        }
        
        header {
            background: linear-gradient(135deg, var(--primary), var(--secondary), var(--accent1));
            color: white;
            text-align: center;
            padding: 2rem 1rem;
            position: relative;
            overflow: hidden;
        }
        
        .glitch-text {
            font-size: 2.8rem;
            margin-bottom: 0.5rem;
            text-shadow: 3px 3px 0px rgba(0,0,0,0.3);
            position: relative;
            animation: glitch 5s infinite;
        }
        
        @keyframes glitch {
            0% { transform: skew(0deg); }
            20% { transform: skew(0deg); }
            21% { transform: skew(-15deg); text-shadow: -3px 0 var(--accent1), 3px 0 var(--accent2); }
            23% { transform: skew(0deg); text-shadow: none; }
            55% { transform: skew(0deg); }
            56% { transform: skew(10deg); text-shadow: 3px 0 var(--accent2), -3px 0 var(--accent1); }
            58% { transform: skew(0deg); text-shadow: none; }
            100% { transform: skew(0deg); }
        }
        
        .tagline {
            font-style: italic;
            animation: color-cycle 8s infinite;
        }
        
        @keyframes color-cycle {
            0% { color: white; }
            25% { color: var(--accent1); }
            50% { color: var(--accent2); }
            75% { color: var(--primary); }
            100% { color: white; }
        }
        
        nav {
            background-color: var(--dark);
            position: sticky;
            top: 0;
            z-index: 100;
        }
        
        nav ul {
            display: flex;
            list-style: none;
            justify-content: center;
            padding: 0.5rem;
        }
        
        nav li {
            margin: 0 0.5rem;
        }
        
        nav a {
            color: white;
            text-decoration: none;
            padding: 0.5rem 1rem;
            display: block;
            border-radius: 4px;
            transition: all 0.3s;
            position: relative;
            overflow: hidden;
        }
        
        nav a:hover {
            background-color: rgba(255,255,255,0.2);
            transform: scale(1.1);
        }
        
        nav a::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.2), transparent);
            transition: 0.5s;
        }
        
        nav a:hover::before {
            left: 100%;
        }
        
        .section {
            padding: 2rem 1rem;
            max-width: 800px;
            margin: 0 auto;
            position: relative;
        }
        
        h2 {
            color: var(--primary);
            margin-bottom: 1rem;
            text-align: center;
            position: relative;
            animation: shimmer 3s infinite;
        }
        
        @keyframes shimmer {
            0% { color: var(--primary); }
            50% { color: var(--secondary); }
            100% { color: var(--primary); }
        }
        
        h2::after {
            content: '';
            display: block;
            width: 50px;
            height: 3px;
            background-color: var(--secondary);
            margin: 0.5rem auto;
            animation: line-grow 3s infinite alternate;
        }
        
        @keyframes line-grow {
            from { width: 0; }
            to { width: 100px; }
        }
        
        p {
            margin-bottom: 1rem;
        }
        
        .music-links {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 1rem;
            margin-top: 1.5rem;
            position: relative;
        }
        
        .music-btn {
            display: block;
            background: linear-gradient(45deg, var(--primary), var(--secondary));
            color: white;
            text-decoration: none;
            padding: 1rem;
            border-radius: 8px;
            text-align: center;
            font-weight: bold;
            box-shadow: 0 4px 8px rgba(0,0,0,0.1);
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
            transform-origin: center;
            animation: 3s infinite alternate;
        }
        
        .music-btn:nth-child(1) { animation-name: pulse-1; animation-delay: 0s; }
        .music-btn:nth-child(2) { animation-name: pulse-2; animation-delay: 0.5s; }
        .music-btn:nth-child(3) { animation-name: pulse-3; animation-delay: 1s; }
        .music-btn:nth-child(4) { animation-name: pulse-4; animation-delay: 1.5s; }
        .music-btn:nth-child(5) { animation-name: pulse-5; animation-delay: 2s; }
        .music-btn:nth-child(6) { animation-name: pulse-6; animation-delay: 2.5s; }
        
        @keyframes pulse-1 {
            0% { transform: scale(1) rotate(0deg); }
            100% { transform: scale(1.05) rotate(1deg); }
        }
        @keyframes pulse-2 {
            0% { transform: scale(1) rotate(0deg); }
            100% { transform: scale(1.05) rotate(-1deg); }
        }
        @keyframes pulse-3 {
            0% { transform: scale(1) rotate(0deg); }
            100% { transform: scale(1.05) rotate(1deg); }
        }
        @keyframes pulse-4 {
            0% { transform: scale(1) rotate(0deg); }
            100% { transform: scale(1.05) rotate(-1deg); }
        }
        @keyframes pulse-5 {
            0% { transform: scale(1) rotate(0deg); }
            100% { transform: scale(1.05) rotate(1deg); }
        }
        @keyframes pulse-6 {
            0% { transform: scale(1) rotate(0deg); }
            100% { transform: scale(1.05) rotate(-1deg); }
        }
        
        .music-btn:hover {
            transform: translateY(-5px) scale(1.1);
            box-shadow: 0 12px 20px rgba(0,0,0,0.2);
            animation-play-state: paused;
            background: linear-gradient(45deg, var(--accent1), var(--accent2));
        }
        
        .music-btn::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: rgba(255,255,255,0.1);
            transform: rotate(45deg);
            transition: transform 0.6s;
            z-index: 1;
        }
        
        .music-btn:hover::before {
            transform: rotate(45deg) translate(50%, 50%);
        }
        
        .music-btn span {
            position: relative;
            z-index: 2;
        }
        
        .email-btn {
            display: block;
            margin: 2rem auto;
            background: linear-gradient(45deg, var(--primary), var(--accent2), var(--secondary));
            background-size: 300% 300%;
            animation: gradient-shift 5s ease infinite;
            color: white;
            text-decoration: none;
            padding: 1.2rem 2rem;
            border-radius: 50px;
            text-align: center;
            font-weight: bold;
            font-size: 1.2rem;
            box-shadow: 0 8px 16px rgba(0,0,0,0.2);
            transition: all 0.3s ease;
            max-width: 400px;
        }
        
        @keyframes gradient-shift {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }
        
        .email-btn:hover {
            transform: translateY(-8px);
            box-shadow: 0 16px 25px rgba(0,0,0,0.3);
            letter-spacing: 1px;
        }
        
        .social-links {
            display: flex;
            justify-content: center;
            margin-top: 1.5rem;
            gap: 1rem;
        }
        
        .social-btn {
            background: var(--primary);
            color: white;
            width: 60px;
            height: 60px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            text-decoration: none;
            font-size: 1.2rem;
            transition: all 0.3s;
            box-shadow: 0 4px 8px rgba(0,0,0,0.2);
            animation: float-social 4s infinite alternate;
        }
        
        @keyframes float-social {
            0% { transform: translateY(0) rotate(0deg); }
            100% { transform: translateY(-10px) rotate(10deg); }
        }
        
        .social-btn:hover {
            transform: scale(1.2) rotate(10deg);
            background: var(--secondary);
            box-shadow: 0 8px 16px rgba(0,0,0,0.3);
        }
        
        footer {
            text-align: center;
            padding: 2rem 1rem;
            background-color: var(--dark);
            color: white;
            margin-top: 2rem;
            position: relative;
            overflow: hidden;
        }
        
        footer::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 300%;
            height: 2px;
            background: linear-gradient(90deg, var(--primary), var(--secondary), var(--accent1), var(--accent2));
            animation: slide 8s linear infinite;
        }
        
        @keyframes slide {
            to { transform: translateX(50%); }
        }
        
        #upcoming {
            background: linear-gradient(-45deg, var(--secondary), var(--accent1), var(--primary), var(--accent2));
            background-size: 400% 400%;
            color: white;
            padding: 1.5rem;
            border-radius: 8px;
            text-align: center;
            margin: 2rem auto;
            max-width: 600px;
            animation: gradient 15s ease infinite, bounce 2s infinite alternate;
            box-shadow: 0 8px 16px rgba(0,0,0,0.2);
        }
        
        @keyframes gradient {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }
        
        @keyframes bounce {
            from { transform: translateY(0); }
            to { transform: translateY(-10px); }
        }
        
        #upcoming h3 {
            font-size: 1.8rem;
            margin-bottom: 0.5rem;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
        }
        
        .marquee {
            width: 100%;
            overflow: hidden;
            position: relative;
            height: 30px;
            background-color: var(--dark);
            color: white;
        }
        
        .marquee-content {
            display: block;
            width: 200%;
            position: absolute;
            overflow: hidden;
            animation: marquee 20s linear infinite;
            white-space: nowrap;
            padding: 5px 0;
        }
        
        @keyframes marquee {
            0% { left: 0; }
            100% { left: -100%; }
        }
        
        @media (max-width: 600px) {
            nav ul {
                flex-direction: column;
                align-items: center;
            }
            
            nav li {
                margin: 0.25rem 0;
                width: 100%;
                text-align: center;
            }
            
            .glitch-text {
                font-size: 2rem;
            }
            
            .floating {
                display: none;
            }
        }
    </style>
</head>
<body>
    <div class="floating note1">♪</div>
    <div class="floating note2">♫</div>
    <div class="floating note3">♬</div>
    <div class="floating note4">♩</div>
    
    <header>
        <h1 class="glitch-text">TREVOR COBURN</h1>
        <p class="tagline">Music that moves you...</p>
    </header>
    
    <div class="marquee">
        <div class="marquee-content">
            NEW SINGLE "LINK IN BIO" DROPPING THIS MARCH! • LISTEN NOW ON SPOTIFY & AMAZON MUSIC • FOLLOW TREVOR FOR THE LATEST UPDATES • NEW SINGLE "LINK IN BIO" DROPPING THIS MARCH!
        </div>
    </div>
    
    <nav>
        <ul>
            <li><a href="#about">About</a></li>
            <li><a href="#music">Music</a></li>
            <li><a href="#contact">Contact</a></li>
        </ul>
    </nav>
    
    <div id="upcoming">
        <h3>NEW SINGLE "LINK IN BIO"</h3>
        <p>Coming this March! Get ready for the drop!</p>
    </div>
    
    <section id="about" class="section">
        <h2>Who is Trevor?</h2>
        <p>Bristol's enigmatic musical force. Husband. Creator. Visionary. The rest? You'll have to discover through his music...</p>
    </section>
    
    <section id="music" class="section">
        <h2>The Sounds</h2>
        <p>Dive into Trevor's musical universe:</p>
        
        <div class="music-links">
            <a href="https://open.spotify.com/artist/63gY4LCMTTRiKwPbzPqJwE" class="music-btn" target="_blank">
                <span>Spotify Artist Page</span>
            </a>
            
            <a href="https://open.spotify.com/album/18oP3HVNXvO8aHh26ttPnh?si=OjkV_XJ7QTS-BUDIbXFOCw" class="music-btn" target="_blank">
                <span>"Live More" on Spotify</span>
            </a>
            
            <a href="https://music.amazon.com/albums/B0DT4VH4KN" class="music-btn" target="_blank">
                <span>Amazon Music</span>
            </a>
            
            <a href="https://youtu.be/kMeiOctw5Q8?si=u9O5DcTmTbi8J4sf" class="music-btn" target="_blank">
                <span>"I Ain't Sorry" on YouTube</span>
            </a>
            
            <a href="https://youtu.be/IuC3oQwssic?si=IqHvIbNzsIL-_pDe" class="music-btn" target="_blank">
                <span>"Summertime" on YouTube</span>
            </a>
            
            <a href="https://youtu.be/ZWM0e7dLQq0?si=DoSN0BAIHA05jweI" class="music-btn" target="_blank">
                <span>"See The Fame" on YouTube</span>
            </a>
        </div>
    </section>
    
    <section id="contact" class="section">
        <h2>Reach Out</h2>
        
        <a href="mailto:trevor.coburn@yahoo.com" class="email-btn">
            DROP TREVOR A MESSAGE ➤
        </a>
        
        <div class="social-links">
            <a href="https://www.instagram.com/trevorcoburn/?igsh=aGYydWxieWtteGJ5#" class="social-btn" target="_blank">IG</a>
        </div>
    </section>
    
    <footer>
        <p>&copy; 2025 Trevor Coburn Fan Page. All rights reserved.</p>
    </footer>

    <script>
        // Smooth scrolling for navigation links
        document.querySelectorAll('nav a').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                const targetId = this.getAttribute('href');
                const targetElement = document.querySelector(targetId);
                
                window.scrollTo({
                    top: targetElement.offsetTop - 60,
                    behavior: 'smooth'
                });
            });
        });
        
        // Random movement for music buttons when mouse moves
        document.addEventListener('mousemove', function(e) {
            const buttons = document.querySelectorAll('.music-btn');
            buttons.forEach((btn, index) => {
                const moveX = (e.clientX / window.innerWidth - 0.5) * 5;
                const moveY = (e.clientY / window.innerHeight - 0.5) * 5;
                const delay = index * 0.05;
                
                btn.style.transition = 'transform 0.3s ease';
                btn.style.transform = `perspective(500px) rotateY(${moveX}deg) rotateX(${-moveY}deg)`;
            });
        });
        
        // Reset button transform when mouse leaves
        document.addEventListener('mouseleave', function() {
            const buttons = document.querySelectorAll('.music-btn');
            buttons.forEach(btn => {
                btn.style.transform = 'perspective(500px) rotateY(0) rotateX(0)';
            });
        });
    </script>
</body>
</html>
