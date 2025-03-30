<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>TREY | Trevor Coburn</title>
    <link rel="icon" href="data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'><text y='.9em' font-size='90'>⚡️</text></svg>">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;500;700&family=Orbitron:wght@700&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary-blue: #00d4ff;
            --accent-red: #ff2e63;
            --dark-bg: #0a0f1c;
            --light-text: #ffffff;
            --subtle-gray: #1e2a44;
            --transition: all 0.3s ease;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Inter', sans-serif;
            -webkit-tap-highlight-color: transparent; /* Removes tap highlight on iPhone */
        }

        body {
            background: linear-gradient(135deg, var(--dark-bg) 0%, var(--subtle-gray) 100%);
            color: var(--light-text);
            line-height: 1.5;
            overflow-x: hidden;
            -webkit-font-smoothing: antialiased; /* Crisp text on iOS */
        }

        body::before {
            content: '';
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" width="50" height="50" fill="none"><path stroke="rgba(0,212,255,0.1)" d="M0 0h50v50H0zM25 0v50M0 25h50"/></svg>') repeat;
            opacity: 0.15;
            z-index: -1;
        }

        header {
            text-align: center;
            padding: 3rem 1rem;
        }

        .logo-text {
            font-family: 'Orbitron', sans-serif;
            font-size: 3.5rem;
            font-weight: 700;
            letter-spacing: 2px;
            color: var(--light-text);
            text-transform: uppercase;
        }

        .tagline {
            font-size: 1rem;
            font-weight: 300;
            color: var(--primary-blue);
            margin-top: 0.5rem;
        }

        nav {
            background: rgba(10, 15, 28, 0.95);
            position: sticky;
            top: 0;
            z-index: 100;
            padding: 0.75rem;
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.2);
        }

        nav ul {
            display: flex;
            justify-content: center;
            gap: 1.5rem;
        }

        nav a {
            color: var(--light-text);
            text-decoration: none;
            font-size: 1rem;
            font-weight: 500;
            text-transform: uppercase;
            padding: 0.5rem;
            transition: var(--transition);
        }

        nav a:hover,
        nav a:active {
            color: var(--primary-blue);
        }

        .section {
            padding: 2rem 1rem;
            max-width: 100%;
            margin: 0 auto;
            text-align: center;
        }

        h2 {
            font-family: 'Orbitron', sans-serif;
            font-size: 1.75rem;
            font-weight: 700;
            color: var(--primary-blue);
            margin-bottom: 1.5rem;
            text-transform: uppercase;
        }

        .music-grid {
            display: grid;
            grid-template-columns: 1fr;
            gap: 1rem;
            padding: 0 1rem;
        }

        .music-link {
            background: rgba(255, 255, 255, 0.05);
            padding: 1rem;
            border-radius: 6px;
            color: var(--light-text);
            text-decoration: none;
            font-weight: 500;
            font-size: 1rem;
            transition: var(--transition);
            border: 1px solid var(--primary-blue);
            display: block;
        }

        .music-link:hover,
        .music-link:active {
            background: var(--primary-blue);
            color: var(--dark-bg);
            transform: translateY(-2px);
        }

        #upcoming {
            background: linear-gradient(135deg, var(--primary-blue), var(--accent-red));
            padding: 1.5rem;
            border-radius: 10px;
            margin: 1.5rem 1rem;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
        }

        #upcoming h3 {
            font-family: 'Orbitron', sans-serif;
            font-size: 1.25rem;
            font-weight: 700;
            color: var(--light-text);
        }

        #upcoming p {
            font-size: 0.9rem;
            font-weight: 300;
            color: var(--dark-bg);
        }

        .connect-btn {
            display: inline-block;
            margin: 1rem 0;
            background: var(--primary-blue);
            color: var(--light-text);
            padding: 0.75rem 1.5rem;
            border-radius: 20px;
            text-decoration: none;
            font-weight: 500;
            font-size: 1rem;
            transition: var(--transition);
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.2);
        }

        .connect-btn:hover,
        .connect-btn:active {
            background: var(--accent-red);
            transform: translateY(-2px);
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 1rem;
            margin-top: 1rem;
        }

        .social-btn {
            width: 40px;
            height: 40px;
            background: rgba(255, 255, 255, 0.1);
            color: var(--light-text);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.25rem;
            transition: var(--transition);
            border: 1px solid var(--primary-blue);
        }

        .social-btn:hover,
        .social-btn:active {
            background: var(--accent-red);
            transform: scale(1.05);
        }

        footer {
            background: rgba(10, 15, 28, 0.95);
            padding: 1rem;
            text-align: center;
            font-size: 0.85rem;
            color: var(--primary-blue);
            box-shadow: 0 -2px 8px rgba(0, 0, 0, 0.2);
        }

        #visualizer {
            position: fixed;
            bottom: 0;
            left: 0;
            width: 100%;
            height: 60px;
            z-index: -1;
            opacity: 0.4;
        }

        /* iPhone Optimization */
        @media (min-width: 768px) {
            header { padding: 4rem 1rem; }
            .logo-text { font-size: 4rem; }
            .tagline { font-size: 1.25rem; }
            nav { padding: 1rem; }
            nav ul { gap: 2rem; }
            nav a { font-size: 1.1rem; }
            .section { padding: 3rem 1rem; }
            h2 { font-size: 2rem; }
            .music-grid { grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); padding: 0; }
            .music-link { font-size: 1.1rem; }
            #upcoming { padding: 2rem; margin: 2rem auto; max-width: 600px; }
            #upcoming h3 { font-size: 1.5rem; }
            #upcoming p { font-size: 1rem; }
            .connect-btn { font-size: 1.1rem; padding: 0.9rem 2rem; }
            .social-btn { width: 50px; height: 50px; font-size: 1.5rem; }
            footer { font-size: 1rem; }
        }
    </style>
</head>
<body>
    <canvas id="visualizer"></canvas>
    <header>
        <h1 class="logo-text">TREY</h1>
        <p class="tagline"></p>
    </header>

    <nav>
        <ul>
            <li><a href="#music">Music</a></li>
            <li><a href="#contact">Connect</a></li>
        </ul>
    </nav>

    <div id="upcoming">
        <h3>NEW SINGLE "LINK IN BIO"</h3>
        <p>March 2025</p>
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
            <a href="https://youtu.be/kMeiOctw5Q8?si=u9O5DcTmTbi8J4sf" class="social-btn" target="_blank"><i class="fab fa-youtube"></i></a>
        </div>
    </section>

    <footer>
        <p>© 2025 TREY | Trevor Coburn</p>
    </footer>

    <script>
        // Smooth Scroll
        document.querySelectorAll('nav a').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                document.querySelector(this.getAttribute('href')).scrollIntoView({ behavior: 'smooth' });
            });
        });

        // Audio Visualizer
        const audio = new Audio('https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3');
        audio.loop = true;
        audio.volume = 0.3;
        audio.play();

        const visualizerCanvas = document.getElementById('visualizer');
        const vCtx = visualizerCanvas.getContext('2d');
        visualizerCanvas.width = window.innerWidth;
        visualizerCanvas.height = 60;

        const audioCtx = new (window.AudioContext || window.webkitAudioContext)();
        const analyser = audioCtx.createAnalyser();
        const source = audioCtx.createMediaElementSource(audio);
        source.connect(analyser);
        analyser.connect(audioCtx.destination);
        analyser.fftSize = 128; // Reduced for better iPhone performance

        const bufferLength = analyser.frequencyBinCount;
        const dataArray = new Uint8Array(bufferLength);

        function drawVisualizer() {
            requestAnimationFrame(drawVisualizer);
            analyser.getByteFrequencyData(dataArray);
            vCtx.clearRect(0, 0, visualizerCanvas.width, visualizerCanvas.height);

            const barWidth = (visualizerCanvas.width / bufferLength) * 2;
            let x = 0;

            for (let i = 0; i < bufferLength; i++) {
                const barHeight = dataArray[i] * 0.8; // Scaled down for mobile
                vCtx.fillStyle = `hsl(${(i / bufferLength) * 360}, 80%, 50%)`;
                vCtx.fillRect(x, visualizerCanvas.height - barHeight, barWidth, barHeight);
                x += barWidth + 1;
            }
        }
        drawVisualizer();

        window.addEventListener('resize', () => {
            visualizerCanvas.width = window.innerWidth;
        });
    </script>
</body>
</html>
