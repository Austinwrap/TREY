<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>TREY</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@700&family=Poppins:wght@300;500;700&display=swap" rel="stylesheet">
    <script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r134/three.min.js"></script>
    <style>
        :root {
            --primary-blue: #00d4ff;
            --accent-red: #ff2e63;
            --dark-bg: #0a0f1c;
            --light-text: #f0f0f0;
            --neon-glow: 0 0 15px rgba(0, 212, 255, 0.9), 0 0 30px rgba(255, 46, 99, 0.7), 0 0 60px rgba(0, 212, 255, 0.5);
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

        #scene {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -2;
        }

        /* Cosmic Overlay */
        body::before {
            content: '';
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle, rgba(0, 212, 255, 0.15), rgba(255, 46, 99, 0.15), transparent);
            animation: cosmicShift 15s infinite alternate;
            z-index: -1;
            pointer-events: none;
        }

        @keyframes cosmicShift {
            0% { transform: rotate(0deg) scale(1); opacity: 0.4; }
            100% { transform: rotate(360deg) scale(1.1); opacity: 0.7; }
        }

        header {
            position: relative;
            text-align: center;
            padding: 6rem 1rem;
            background: linear-gradient(135deg, rgba(0, 212, 255, 0.4), rgba(255, 46, 99, 0.4));
            animation: headerPulse 2s infinite alternate;
            z-index: 10;
        }

        @keyframes headerPulse {
            0% { transform: scale(1); box-shadow: inset 0 0 30px rgba(0, 212, 255, 0.6); }
            100% { transform: scale(1.02); box-shadow: inset 0 0 60px rgba(255, 46, 99, 0.6); }
        }

        .logo-text {
            font-family: 'Orbitron', sans-serif;
            font-size: 7rem;
            font-weight: 700;
            letter-spacing: 6px;
            color: var(--light-text);
            text-transform: uppercase;
            text-shadow: var(--neon-glow);
            animation: glitch 2s infinite;
            position: relative;
        }

        @keyframes glitch {
            0%, 100% { transform: translate(0); }
            20% { transform: translate(-5px, 5px); }
            40% { transform: translate(5px, -5px); }
            60% { transform: translate(-5px, 0); }
            80% { transform: translate(5px, 0); }
        }

        .tagline {
            font-size: 2rem;
            font-weight: 300;
            color: var(--primary-blue);
            margin-top: 1rem;
            text-shadow: var(--neon-glow);
            animation: fadeInUp 1.5s ease forwards;
        }

        @keyframes fadeInUp {
            from { opacity: 0; transform: translateY(30px); }
            to { opacity: 1; transform: translateY(0); }
        }

        nav {
            background: rgba(10, 15, 28, 0.98);
            position: sticky;
            top: 0;
            z-index: 1000;
            backdrop-filter: blur(15px);
            padding: 2rem 0;
            box-shadow: var(--neon-glow);
        }

        nav ul {
            display: flex;
            justify-content: center;
            gap: 4rem;
        }

        nav a {
            color: var(--light-text);
            text-decoration: none;
            font-size: 1.5rem;
            font-weight: 700;
            text-transform: uppercase;
            position: relative;
            transition: var(--transition);
        }

        nav a::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 0;
            width: 0;
            height: 4px;
            background: linear-gradient(90deg, var(--primary-blue), var(--accent-red));
            transition: width 0.4s ease;
        }

        nav a:hover::after {
            width: 100%;
        }

        nav a:hover {
            color: var(--accent-red);
            text-shadow: var(--neon-glow);
            transform: scale(1.1);
        }

        .section {
            padding: 8rem 2rem;
            max-width: 1600px;
            margin: 0 auto;
            text-align: center;
            position: relative;
            z-index: 10;
        }

        h2 {
            font-family: 'Orbitron', sans-serif;
            font-size: 4rem;
            font-weight: 700;
            color: var(--primary-blue);
            margin-bottom: 4rem;
            text-transform: uppercase;
            text-shadow: var(--neon-glow);
            animation: glowPulse 2s infinite alternate;
        }

        @keyframes glowPulse {
            0% { text-shadow: var(--neon-glow); }
            100% { text-shadow: 0 0 20px rgba(255, 46, 99, 0.9), 0 0 40px rgba(0, 212, 255, 0.7); }
        }

        .music-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 3rem;
        }

        .music-link {
            background: rgba(255, 255, 255, 0.05);
            padding: 2.5rem;
            border-radius: 15px;
            color: var(--light-text);
            text-decoration: none;
            font-weight: 700;
            font-size: 1.5rem;
            transition: var(--transition);
            position: relative;
            overflow: hidden;
            border: 2px solid var(--primary-blue);
            box-shadow: var(--neon-glow);
        }

        .music-link::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255, 46, 99, 0.3), transparent);
            opacity: 0;
            transition: opacity 0.4s ease;
        }

        .music-link:hover::before {
            opacity: 1;
        }

        .music-link:hover {
            background: var(--primary-blue);
            transform: translateY(-15px) scale(1.1) rotate(2deg);
            box-shadow: 0 0 80px rgba(0, 212, 255, 0.9);
            color: var(--dark-bg);
        }

        #upcoming {
            background: linear-gradient(45deg, var(--primary-blue), var(--accent-red));
            padding: 4rem;
            border-radius: 20px;
            max-width: 1000px;
            margin: 4rem auto;
            box-shadow: var(--neon-glow);
            animation: supernova 2s infinite alternate;
            position: relative;
            overflow: hidden;
            z-index: 10;
        }

        #upcoming::after {
            content: '🌌';
            position: absolute;
            top: 20px;
            right: 20px;
            font-size: 3rem;
            animation: orbit 3s infinite linear;
        }

        @keyframes orbit {
            100% { transform: rotate(360deg); }
        }

        @keyframes supernova {
            0% { box-shadow: 0 0 20px var(--primary-blue); transform: scale(1); }
            100% { box-shadow: 0 0 100px var(--accent-red); transform: scale(1.05); }
        }

        #upcoming h3 {
            font-family: 'Orbitron', sans-serif;
            font-size: 2.5rem;
            font-weight: 700;
            color: var(--light-text);
            text-shadow: var(--neon-glow);
        }

        #upcoming p {
            font-size: 1.5rem;
            font-weight: 300;
            color: var(--dark-bg);
        }

        .connect-btn {
            display: inline-block;
            margin: 3rem 0;
            background: linear-gradient(90deg, var(--primary-blue), var(--accent-red));
            color: var(--light-text);
            padding: 2rem 4rem;
            border-radius: 60px;
            text-decoration: none;
            font-weight: 700;
            font-size: 2rem;
            transition: var(--transition);
            box-shadow: var(--neon-glow);
            position: relative;
            overflow: hidden;
        }

        .connect-btn::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255, 255, 255, 0.3), transparent);
            opacity: 0;
            transition: opacity 0.4s ease;
        }

        .connect-btn:hover::before {
            opacity: 1;
        }

        .connect-btn:hover {
            transform: scale(1.15) rotate(5deg);
            box-shadow: 0 0 100px rgba(255, 46, 99, 0.9);
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 3rem;
            margin-top: 3rem;
        }

        .social-btn {
            width: 100px;
            height: 100px;
            background: rgba(255, 255, 255, 0.1);
            color: var(--light-text);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 3rem;
            transition: var(--transition);
            border: 3px solid var(--accent-red);
            position: relative;
        }

        .social-btn:hover {
            background: var(--primary-blue);
            transform: scale(1.3) rotate(720deg);
            box-shadow: var(--neon-glow);
            border-color: var(--light-text);
        }

        footer {
            background: rgba(10, 15, 28, 0.98);
            padding: 3rem;
            text-align: center;
            font-size: 1.2rem;
            color: var(--primary-blue);
            box-shadow: var(--neon-glow);
            z-index: 10;
            position: relative;
        }

        /* Audio Visualizer */
        #visualizer {
            position: fixed;
            bottom: 0;
            left: 0;
            width: 100%;
            height: 100px;
            z-index: -1;
            opacity: 0.5;
        }

        @media (max-width: 768px) {
            .logo-text { font-size: 4rem; }
            nav ul { flex-direction: column; gap: 2rem; }
            .music-grid { grid-template-columns: 1fr; }
            h2 { font-size: 2.5rem; }
            .social-btn { width: 70px; height: 70px; font-size: 2rem; }
        }
    </style>
</head>
<body>
    <div id="scene"></div>
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
        <p></p>
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
        <p>© 2025 TREY | Trevor Coburn - Conqueror of the Cosmos</p>
    </footer>

    <script>
        // 3D Background with Three.js
        const scene = new THREE.Scene();
        const camera = new THREE.PerspectiveCamera(75, window.innerWidth / window.innerHeight, 0.1, 1000);
        const renderer = new THREE.WebGLRenderer({ alpha: true });
        renderer.setSize(window.innerWidth, window.innerHeight);
        document.getElementById('scene').appendChild(renderer.domElement);

        const geometry = new THREE.TorusKnotGeometry(10, 3, 100, 16);
        const material = new THREE.MeshPhongMaterial({ color: 0x00d4ff, emissive: 0xff2e63, shininess: 100 });
        const torusKnot = new THREE.Mesh(geometry, material);
        scene.add(torusKnot);

        const light = new THREE.PointLight(0xffffff, 1, 100);
        light.position.set(10, 10, 10);
        scene.add(light);

        camera.position.z = 30;

        function animate3D() {
            requestAnimationFrame(animate3D);
            torusKnot.rotation.x += 0.01;
            torusKnot.rotation.y += 0.01;
            renderer.render(scene, camera);
        }
        animate3D();

        window.addEventListener('resize', () => {
            renderer.setSize(window.innerWidth, window.innerHeight);
            camera.aspect = window.innerWidth / window.innerHeight;
            camera.updateProjectionMatrix();
        });

        // Smooth Scroll
        document.querySelectorAll('nav a').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                document.querySelector(this.getAttribute('href')).scrollIntoView({ behavior: 'smooth' });
            });
        });

        // Audio Visualizer
        const audio = new Audio('https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3'); // Replace with Trey's track if available
        audio.loop = true;
        audio.volume = 0.3;
        audio.play();

        const visualizerCanvas = document.getElementById('visualizer');
        const vCtx = visualizerCanvas.getContext('2d');
        visualizerCanvas.width = window.innerWidth;
        visualizerCanvas.height = 100;

        const audioCtx = new (window.AudioContext || window.webkitAudioContext)();
        const analyser = audioCtx.createAnalyser();
        const source = audioCtx.createMediaElementSource(audio);
        source.connect(analyser);
        analyser.connect(audioCtx.destination);
        analyser.fftSize = 256;

        const bufferLength = analyser.frequencyBinCount;
        const dataArray = new Uint8Array(bufferLength);

        function drawVisualizer() {
            requestAnimationFrame(drawVisualizer);
            analyser.getByteFrequencyData(dataArray);
            vCtx.clearRect(0, 0, visualizerCanvas.width, visualizerCanvas.height);

            const barWidth = (visualizerCanvas.width / bufferLength) * 2.5;
            let x = 0;

            for (let i = 0; i < bufferLength; i++) {
                const barHeight = dataArray[i];
                vCtx.fillStyle = `hsl(${i * 2}, 100%, 50%)`;
                vCtx.fillRect(x, visualizerCanvas.height - barHeight / 2, barWidth, barHeight / 2);
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
