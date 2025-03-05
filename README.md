<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>TREY</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;500;700&family=Orbitron:wght@700&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary-blue: #00d4ff;
            --accent-red: #ff2e63;
            --dark-bg: #0a0f1c;
            --light-text: #f0f0f0;
            --neon-glow: 0 0 15px rgba(0, 212, 255, 0.8), 0 0 30px rgba(255, 46, 99, 0.6);
            --transition: all 0.4s ease;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', sans-serif;
        }

        body {
            background: var(--dark-bg);
            color: var(--light-text);
            line-height: 1.6;
            overflow-x: hidden;
            position: relative;
        }

        /* Cosmic Background */
        body::before {
            content: '';
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle, rgba(0, 212, 255, 0.1), rgba(255, 46, 99, 0.1), transparent);
            animation: cosmicPulse 10s infinite alternate;
            z-index: -1;
        }

        @keyframes cosmicPulse {
            0% { opacity: 0.3; transform: scale(1); }
            100% { opacity: 0.6; transform: scale(1.05); }
        }

        header {
            position: relative;
            text-align: center;
            padding: 5rem 1rem;
            background: linear-gradient(135deg, rgba(0, 212, 255, 0.3), rgba(255, 46, 99, 0.3));
            animation: headerGlow 3s infinite alternate;
        }

        @keyframes headerGlow {
            0% { box-shadow: inset 0 0 20px rgba(0, 212, 255, 0.5); }
            100% { box-shadow: inset 0 0 40px rgba(255, 46, 99, 0.5); }
        }

        .logo-text {
            font-family: 'Orbitron', sans-serif;
            font-size: 5rem;
            font-weight: 700;
            letter-spacing: 4px;
            color: var(--light-text);
            text-transform: uppercase;
            text-shadow: var(--neon-glow);
            transition: var(--transition);
        }

        .logo-text:hover {
            color: var(--primary-blue);
            transform: scale(1.05);
        }

        .tagline {
            font-size: 1.5rem;
            font-weight: 300;
            color: var(--accent-red);
            margin-top: 1rem;
            animation: fadeInUp 1s ease forwards;
        }

        @keyframes fadeInUp {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        nav {
            background: rgba(10, 15, 28, 0.95);
            position: sticky;
            top: 0;
            z-index: 1000;
            backdrop-filter: blur(12px);
            padding: 1.5rem 0;
            box-shadow: var(--neon-glow);
        }

        nav ul {
            display: flex;
            justify-content: center;
            gap: 3rem;
        }

        nav a {
            color: var(--light-text);
            text-decoration: none;
            font-size: 1.3rem;
            font-weight: 700;
            text-transform: uppercase;
            position: relative;
            transition: var(--transition);
        }

        nav a::after {
            content: '';
            position: absolute;
            bottom: -8px;
            left: 0;
            width: 0;
            height: 3px;
            background: linear-gradient(90deg, var(--primary-blue), var(--accent-red));
            transition: width 0.4s ease;
        }

        nav a:hover::after {
            width: 100%;
        }

        nav a:hover {
            color: var(--primary-blue);
            text-shadow: var(--neon-glow);
        }

        .section {
            padding: 6rem 2rem;
            max-width: 1400px;
            margin: 0 auto;
            text-align: center;
            position: relative;
        }

        h2 {
            font-family: 'Orbitron', sans-serif;
            font-size: 3rem;
            font-weight: 700;
            color: var(--primary-blue);
            margin-bottom: 3rem;
            text-transform: uppercase;
            text-shadow: var(--neon-glow);
        }

        .music-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .music-link {
            background: rgba(255, 255, 255, 0.05);
            padding: 2rem;
            border-radius: 12px;
            color: var(--light-text);
            text-decoration: none;
            font-weight: 500;
            font-size: 1.3rem;
            transition: var(--transition);
            position: relative;
            overflow: hidden;
            border: 1px solid rgba(0, 212, 255, 0.3);
        }

        .music-link::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(0, 212, 255, 0.2), transparent);
            opacity: 0;
            transition: opacity 0.4s ease;
        }

        .music-link:hover::before {
            opacity: 1;
        }

        .music-link:hover {
            background: var(--accent-red);
            transform: translateY(-10px) scale(1.05);
            box-shadow: var(--neon-glow);
            color: var(--dark-bg);
        }

        #upcoming {
            background: linear-gradient(45deg, var(--primary-blue), var(--accent-red));
            padding: 3rem;
            border-radius: 15px;
            max-width: 800px;
            margin: 3rem auto;
            box-shadow: var(--neon-glow);
            animation: pulseNeon 1.5s infinite alternate;
            position: relative;
            overflow: hidden;
        }

        #upcoming::after {
            content: '🔥';
            position: absolute;
            top: 10px;
            right: 10px;
            font-size: 2rem;
            animation: spin 2s infinite linear;
        }

        @keyframes spin {
            100% { transform: rotate(360deg); }
        }

        @keyframes pulseNeon {
            0% { box-shadow: 0 0 15px var(--primary-blue); }
            100% { box-shadow: 0 0 40px var(--accent-red); }
        }

        #upcoming h3 {
            font-family: 'Orbitron', sans-serif;
            font-size: 2rem;
            font-weight: 700;
            color: var(--light-text);
            text-shadow: var(--neon-glow);
        }

        #upcoming p {
            font-size: 1.3rem;
            font-weight: 300;
            color: var(--dark-bg);
        }

        .connect-btn {
            display: inline-block;
            margin: 2rem 0;
            background: linear-gradient(90deg, var(--primary-blue), var(--accent-red));
            color: var(--light-text);
            padding: 1.5rem 3rem;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 700;
            font-size: 1.5rem;
            transition: var(--transition);
            box-shadow: var(--neon-glow);
        }

        .connect-btn:hover {
            transform: scale(1.1) rotate(2deg);
            box-shadow: 0 0 50px rgba(255, 46, 99, 0.8);
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 2rem;
            margin-top: 2rem;
        }

        .social-btn {
            width: 70px;
            height: 70px;
            background: rgba(255, 255, 255, 0.1);
            color: var(--light-text);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2rem;
            transition: var(--transition);
            border: 2px solid var(--primary-blue);
        }

        .social-btn:hover {
            background: var(--primary-blue);
            transform: scale(1.2) rotate(360deg);
            box-shadow: var(--neon-glow);
        }

        footer {
            background: rgba(10, 15, 28, 0.95);
            padding: 2rem;
            text-align: center;
            font-size: 1rem;
            color: var(--primary-blue);
            box-shadow: var(--neon-glow);
        }

        /* Particle Effect */
        #particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: -1;
        }

        @media (max-width: 768px) {
            .logo-text { font-size: 3.5rem; }
            nav ul { flex-direction: column; gap: 1.5rem; }
            .music-grid { grid-template-columns: 1fr; }
            h2 { font-size: 2rem; }
        }
    </style>
</head>
<body>
    <canvas id="particles"></canvas>
    <header>
        <h1 class="logo-text">TREY</h1>
        <p class="tagline">TREY</p>
    </header>

    <nav>
        <ul>
            <li><a href="#music">Music</a></li>
            <li><a href="#contact">Connect</a></li>
        </ul>
    </nav>

    <div id="upcoming">
        <h3>NEW SINGLE "LINK IN BIO"</h3>
        <p>March 2025 – Ignite the Universe</p>
    </div>

    <section id="music" class="section">
        <h2>Music</h2>
        <div class="music-grid">
            <a href="https://open.spotify.com/artist/63gY4LCMTTRiKwPbzPqJwE" class="music-link" target="_blank">Spotify Artist</a>
            <a href="https://open.spotify.com/album/18oP3HVNXvO8aHh26ttPnh?si=OjkV_XJ7QTS-BUDIbXFOCw" class="music-link" target="_blank">"Live More" Spotify</a>
            <a href="https://music.amazon.com/albums/B0DT4VH4KN" class="music-link" target="_blank">Amazon Music</a>
            <a href="https://youtu.be/kMeiOctw5Q8?si=u9O5DcTmTbi8J4sf" class="music-link" target="_blank">"I Ain’t Sorry" YouTube</a>
            <a href="https://youtu.be/IuC3oQwssic?si=IqHvIbNzsIL-_pDe" class="music-link" target="_blank">"Summertime" YouTube</a>
            <a href="https://youtu.be/ZWM0e7dLQq0?si=DoSN0BAIHA05jweI" class="music-link" target="_blank">"See The Fame" YouTube</a>
        </div>
    </section>

    <section id="contact" class="section">
        <h2>Connect</h2>
        <a href="mailto:trevor.coburn@yahoo.com" class="connect-btn">Drop a Line</a>
        <div class="social-links">
            <a href="https://www.instagram.com/trevorcoburn/?igsh=aGYydWxieWtteGJ5" class="social-btn" target="_blank"><i class="fab fa-instagram"></i></a>
            <a href="https://open.spotify.com/artist/63gY4LCMTTRiKwPbzPqJwE" class="social-btn" target="_blank"><i class="fab fa-spotify"></i></a>
            <a href="https://www.youtube.com/@trevorcoburn" class="social-btn" target="_blank"><i class="fab fa-youtube"></i></a>
        </div>
    </section>

    <footer>
        <p>© 2025 TREY | Trevor Coburn - Powered by the Cosmos</p>
    </footer>

    <script>
        // Smooth Scroll
        document.querySelectorAll('nav a').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                document.querySelector(this.getAttribute('href')).scrollIntoView({ behavior: 'smooth' });
            });
        });

        // Particle Effect
        const canvas = document.getElementById('particles');
        const ctx = canvas.getContext('2d');
        canvas.width = window.innerWidth;
        canvas.height = window.innerHeight;

        const particlesArray = [];
        const numberOfParticles = 100;

        class Particle {
            constructor() {
                this.x = Math.random() * canvas.width;
                this.y = Math.random() * canvas.height;
                this.size = Math.random() * 5 + 1;
                this.speedX = Math.random() * 1 - 0.5;
                this.speedY = Math.random() * 1 - 0.5;
                this.color = `hsl(${Math.random() * 360}, 100%, 50%)`;
            }
            update() {
                this.x += this.speedX;
                this.y += this.speedY;
                if (this.size > 0.2) this.size -= 0.01;
            }
            draw() {
                ctx.fillStyle = this.color;
                ctx.beginPath();
                ctx.arc(this.x, this.y, this.size, 0, Math.PI * 2);
                ctx.fill();
            }
        }

        function init() {
            for (let i = 0; i < numberOfParticles; i++) {
                particlesArray.push(new Particle());
            }
        }

        function animate() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            for (let i = 0; i < particlesArray.length; i++) {
                particlesArray[i].update();
                particlesArray[i].draw();
                if (particlesArray[i].size <= 0.2) {
                    particlesArray.splice(i, 1);
                    i--;
                    particlesArray.push(new Particle());
                }
            }
            requestAnimationFrame(animate);
        }

        init();
        animate();

        window.addEventListener('resize', () => {
            canvas.width = window.innerWidth;
            canvas.height = window.innerHeight;
        });
    </script>
</body>
</html>
