<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Trevor Coburn | Unleash the Vibe</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --neon-blue: #00ddeb;
            --neon-red: #ff0066;
            --neon-green: #39ff14;
            --dark-bg: #0d0d1a;
            --light-text: #e0e0e0;
            --shadow: 0 0 15px rgba(0, 221, 235, 0.5);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Orbitron', sans-serif;
        }

        body {
            background: var(--dark-bg);
            color: var(--light-text);
            line-height: 1.6;
            overflow-x: hidden;
            background-image: linear-gradient(45deg, rgba(0, 221, 235, 0.1), rgba(255, 0, 102, 0.1));
        }

        /* Floating Particles */
        .particle {
            position: fixed;
            z-index: -1;
            width: 10px;
            height: 10px;
            background: var(--neon-blue);
            border-radius: 50%;
            animation: drift 20s infinite linear;
            opacity: 0.5;
        }

        @keyframes drift {
            0% { transform: translate(0, 0); }
            50% { transform: translate(50vw, 50vh); opacity: 0.8; }
            100% { transform: translate(100vw, 100vh); opacity: 0; }
        }

        header {
            background: linear-gradient(135deg, var(--neon-blue), var(--neon-red));
            text-align: center;
            padding: 4rem 1rem;
            position: relative;
            box-shadow: var(--shadow);
        }

        .glitch-text {
            font-size: 4rem;
            font-weight: 900;
            text-transform: uppercase;
            color: var(--light-text);
            text-shadow: 0 0 10px var(--neon-blue), 0 0 20px var(--neon-red);
            animation: glitch 2s infinite;
        }

        @keyframes glitch {
            0%, 100% { transform: translate(0); }
            20% { transform: translate(-5px, 5px) skew(10deg); }
            40% { transform: translate(5px, -5px) skew(-10deg); }
        }

        .tagline {
            font-size: 1.5rem;
            color: var(--neon-green);
            animation: pulse 1.5s infinite;
        }

        @keyframes pulse {
            0%, 100% { opacity: 1; }
            50% { opacity: 0.7; }
        }

        nav {
            background: rgba(13, 13, 26, 0.9);
            position: sticky;
            top: 0;
            z-index: 1000;
            backdrop-filter: blur(10px);
        }

        nav ul {
            display: flex;
            justify-content: center;
            padding: 1rem;
        }

        nav li {
            margin: 0 1rem;
        }

        nav a {
            color: var(--neon-blue);
            text-decoration: none;
            font-size: 1.2rem;
            padding: 0.5rem 1rem;
            transition: all 0.3s;
            position: relative;
        }

        nav a:hover {
            color: var(--neon-red);
            text-shadow: var(--shadow);
            transform: translateY(-3px);
        }

        nav a::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--neon-green);
            transition: width 0.3s;
        }

        nav a:hover::after {
            width: 100%;
        }

        .section {
            padding: 4rem 2rem;
            max-width: 1200px;
            margin: 0 auto;
            text-align: center;
        }

        h2 {
            font-size: 2.5rem;
            color: var(--neon-blue);
            text-shadow: var(--shadow);
            margin-bottom: 2rem;
            animation: fadeIn 1s ease-in;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(-20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .music-links {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 1.5rem;
        }

        .music-btn {
            background: linear-gradient(45deg, var(--neon-blue), var(--neon-red));
            padding: 1.5rem;
            border-radius: 10px;
            color: var(--light-text);
            text-decoration: none;
            font-size: 1.2rem;
            font-weight: bold;
            box-shadow: var(--shadow);
            transition: all 0.4s;
            position: relative;
            overflow: hidden;
        }

        .music-btn:hover {
            transform: scale(1.05) rotate(2deg);
            box-shadow: 0 0 25px var(--neon-green);
            background: linear-gradient(45deg, var(--neon-red), var(--neon-green));
        }

        .music-btn::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: rgba(255, 255, 255, 0.2);
            transform: rotate(30deg);
            transition: all 0.5s;
        }

        .music-btn:hover::before {
            transform: rotate(30deg) translate(50%, 50%);
        }

        #upcoming {
            background: linear-gradient(90deg, var(--neon-blue), var(--neon-red), var(--neon-green));
            padding: 2rem;
            border-radius: 15px;
            margin: 2rem auto;
            max-width: 700px;
            box-shadow: var(--shadow);
            animation: glow 2s infinite alternate;
        }

        @keyframes glow {
            0% { box-shadow: 0 0 10px var(--neon-blue); }
            100% { box-shadow: 0 0 30px var(--neon-red); }
        }

        .email-btn {
            display: inline-block;
            margin: 2rem 0;
            background: var(--neon-green);
            color: var(--dark-bg);
            padding: 1.5rem 3rem;
            border-radius: 50px;
            text-decoration: none;
            font-size: 1.3rem;
            font-weight: bold;
            box-shadow: var(--shadow);
            transition: all 0.3s;
        }

        .email-btn:hover {
            background: var(--neon-red);
            color: var(--light-text);
            transform: scale(1.1);
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 2rem;
            margin-top: 2rem;
        }

        .social-btn {
            width: 60px;
            height: 60px;
            background: var(--neon-blue);
            color: var(--dark-bg);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            transition: all 0.3s;
            box-shadow: var(--shadow);
        }

        .social-btn:hover {
            background: var(--neon-green);
            transform: rotate(360deg);
        }

        footer {
            background: rgba(13, 13, 26, 0.9);
            padding: 2rem;
            text-align: center;
            color: var(--neon-blue);
            font-size: 0.9rem;
        }

        .marquee {
            background: var(--neon-red);
            color: var(--dark-bg);
            padding: 0.5rem 0;
            overflow: hidden;
            white-space: nowrap;
        }

        .marquee-content {
            display: inline-block;
            animation: marquee 15s linear infinite;
        }

        @keyframes marquee {
            0% { transform: translateX(100%); }
            100% { transform: translateX(-100%); }
        }

        @media (max-width: 768px) {
            .glitch-text { font-size: 2.5rem; }
            nav ul { flex-direction: column; }
            nav li { margin: 0.5rem 0; }
            .music-links { grid-template-columns: 1fr; }
        }
    </style>
    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700;900&display=swap" rel="stylesheet">
</head>
<body>
    <!-- Particles -->
    <div class="particle" style="top: 10%; left: 20%;"></div>
    <div class="particle" style="top: 30%; left: 70%;"></div>
    <div class="particle" style="top: 60%; left: 40%;"></div>
    <div class="particle" style="top: 80%; left: 90%;"></div>

    <header>
        <h1 class="glitch-text">TREVOR COBURN</h1>
        <p class="tagline">Drop Beats, Not Bombs</p>
    </header>

    <div class="marquee">
        <div class="marquee-content">
            🔥 NEW SINGLE "LINK IN BIO" DROPS MARCH 2025! • STREAM NOW ON SPOTIFY • VIBE WITH TREVOR 🔥
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
        <p>March 2025 – Prepare for the Hype!</p>
    </div>

    <section id="about" class="section">
        <h2>Who’s Trevor?</h2>
        <p>Bristol’s sonic rebel. Husband. Dream-weaver. His beats? A portal to another dimension.</p>
    </section>

    <section id="music" class="section">
        <h2>The Soundwave</h2>
        <p>Plug in and blast off:</p>
        <div class="music-links">
            <a href="https://open.spotify.com/artist/63gY4LCMTTRiKwPbzPqJwE" class="music-btn" target="_blank">Spotify Artist</a>
            <a href="https://open.spotify.com/album/18oP3HVNXvO8aHh26ttPnh?si=OjkV_XJ7QTS-BUDIbXFOCw" class="music-btn" target="_blank">"Live More" Spotify</a>
            <a href="https://music.amazon.com/albums/B0DT4VH4KN" class="music-btn" target="_blank">Amazon Music</a>
            <a href="https://youtu.be/kMeiOctw5Q8?si=u9O5DcTmTbi8J4sf" class="music-btn" target="_blank">"I Ain’t Sorry" YouTube</a>
            <a href="https://youtu.be/IuC3oQwssic?si=IqHvIbNzsIL-_pDe" class="music-btn" target="_blank">"Summertime" YouTube</a>
            <a href="https://youtu.be/ZWM0e7dLQq0?si=DoSN0BAIHA05jweI" class="music-btn" target="_blank">"See The Fame" YouTube</a>
        </div>
    </section>

    <section id="contact" class="section">
        <h2>Connect</h2>
        <a href="mailto:trevor.coburn@yahoo.com" class="email-btn">Hit Trevor Up ➤</a>
        <div class="social-links">
            <a href="https://www.instagram.com/trevorcoburn/?igsh=aGYydWxieWtteGJ5" class="social-btn" target="_blank"><i class="fab fa-instagram"></i></a>
        </div>
    </section>

    <footer>
        <p>© 2025 Trevor Coburn | Powered by the Beat</p>
    </footer>

    <script>
        // Smooth Scroll
        document.querySelectorAll('nav a').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                document.querySelector(this.getAttribute('href')).scrollIntoView({ behavior: 'smooth' });
            });
        });

        // Interactive Particles
        document.addEventListener('mousemove', (e) => {
            const particle = document.createElement('div');
            particle.className = 'particle';
            particle.style.left = `${e.pageX}px`;
            particle.style.top = `${e.pageY}px`;
            document.body.appendChild(particle);
            setTimeout(() => particle.remove(), 2000);
        });
    </script>
</body>
</html>
