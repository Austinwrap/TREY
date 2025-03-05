<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>TREY | Trevor Coburn</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@700&family=Poppins:wght@300;500;700&display=swap" rel="stylesheet">
    <script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r134/three.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/dat-gui/0.7.9/dat.gui.min.js"></script>
    <style>
        :root {
            --primary-blue: #00d4ff;
            --accent-red: #ff2e63;
            --dark-bg: #0a0f1c;
            --light-text: #f0f0f0;
            --neon-glow: 0 0 20px rgba(0, 212, 255, 1), 0 0 40px rgba(255, 46, 99, 0.9), 0 0 80px rgba(0, 212, 255, 0.7);
            --transition: all 0.5s cubic-bezier(0.23, 1, 0.32, 1);
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
            overflow-x: hidden; /* Changed from overflow: hidden to allow vertical scrolling */
            position: relative;
            perspective: 1000px;
        }

        #scene {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -2;
        }

        /* Holographic Overlay */
        body::before {
            content: '';
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(45deg, rgba(0, 212, 255, 0.2), rgba(255, 46, 99, 0.2), transparent);
            animation: holoShift 10s infinite alternate;
            z-index: -1;
            pointer-events: none;
        }

        @keyframes holoShift {
            0% { transform: translateZ(-100px) rotate(0deg); opacity: 0.5; }
            100% { transform: translateZ(100px) rotate(360deg); opacity: 0.8; }
        }

        header {
            position: relative;
            text-align: center;
            padding: 8rem 1rem;
            background: none;
            animation: holoPulse 3s infinite alternate;
            z-index: 10;
            transform-style: preserve-3d;
        }

        @keyframes holoPulse {
            0% { transform: translateZ(0) scale(1); }
            100% { transform: translateZ(50px) scale(1.05); }
        }

        .logo-text {
            font-family: 'Orbitron', sans-serif;
            font-size: 10rem;
            font-weight: 700;
            letter-spacing: 8px;
            color: var(--light-text);
            text-transform: uppercase;
            text-shadow: var(--neon-glow);
            animation: cyberGlitch 1.5s infinite;
            position: relative;
            transform-style: preserve-3d;
        }

        @keyframes cyberGlitch {
            0%, 100% { transform: translateZ(0); clip-path: polygon(0 0, 100% 0, 100% 100%, 0 100%); }
            20% { transform: translateZ(20px) translateX(-10px); clip-path: polygon(0 20%, 100% 0, 100% 80%, 0 100%); }
            40% { transform: translateZ(-20px) translateY(10px); clip-path: polygon(0 0, 100% 20%, 100% 100%, 0 80%); }
            60% { transform: translateZ(10px) translateX(10px); clip-path: polygon(20% 0, 100% 0, 80% 100%, 0 100%); }
        }

        .tagline {
            font-size: 2.5rem;
            font-weight: 300;
            color: var(--accent-red);
            margin-top: 1.5rem;
            text-shadow: var(--neon-glow);
            animation: fadeInUp 2s ease forwards;
            transform: translateZ(20px);
        }

        nav {
            background: rgba(10, 15, 28, 0.95);
            position: sticky;
            top: 0;
            z-index: 1000;
            backdrop-filter: blur(20px);
            padding: 2.5rem 0;
            box-shadow: var(--neon-glow);
            transform: translateZ(30px);
        }

        nav ul {
            display: flex;
            justify-content: center;
            gap: 5rem;
        }

        nav a {
            color: var(--light-text);
            text-decoration: none;
            font-size: 2rem;
            font-weight: 700;
            text-transform: uppercase;
            position: relative;
            transition: var(--transition);
            transform-style: preserve-3d;
            z-index: 1001; /* Ensure nav links are clickable */
        }

        nav a::after {
            content: '';
            position: absolute;
            bottom: -12px;
            left: 0;
            width: 0;
            height: 5px;
            background: linear-gradient(90deg, var(--primary-blue), var(--accent-red));
            transition: width 0.5s ease;
        }

        nav a:hover::after {
            width: 100%;
        }

        nav a:hover {
            color: var(--primary-blue);
            text-shadow: var(--neon-glow);
            transform: translateZ(20px) scale(1.2);
        }

        .section {
            padding: 10rem 2rem;
            max-width: 1800px;
            margin: 0 auto;
            text-align: center;
            position: relative;
            z-index: 10;
            transform-style: preserve-3d;
        }

        h2 {
            font-family: 'Orbitron', sans-serif;
            font-size: 5rem;
            font-weight: 700;
            color: var(--primary-blue);
            margin-bottom: 5rem;
            text-transform: uppercase;
            text-shadow: var(--neon-glow);
            animation: holoText 2s infinite alternate;
            transform: translateZ(40px);
        }

        @keyframes holoText {
            0% { transform: translateZ(40px) rotateX(0deg); }
            100% { transform: translateZ(60px) rotateX(10deg); }
        }

        .music-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
            gap: 4rem;
            transform: translateZ(20px);
        }

        .music-link {
            background: rgba(255, 255, 255, 0.05);
            padding: 3rem;
            border-radius: 20px;
            color: var(--light-text);
            text-decoration: none;
            font-weight: 700;
            font-size: 1.8rem;
            transition: var(--transition);
            position: relative;
            overflow: hidden;
            border: 3px solid var(--accent-red);
            box-shadow: var(--neon-glow);
            transform-style: preserve-3d;
            z-index: 10; /* Ensure links are clickable */
        }

        .music-link::before {
            content: '';
            position: absolute;
            top: -100%;
            left: -100%;
            width: 300%;
            height: 300%;
            background: radial-gradient(circle, rgba(0, 212, 255, 0.4), transparent);
            opacity: 0;
            transition: opacity 0.5s ease;
        }

        .music-link:hover::before {
            opacity: 1;
        }

        .music-link:hover {
            background: var(--accent-red);
            transform: translateZ(50px) scale(1.15) rotateY(15deg);
            box-shadow: 0 0 120px rgba(255, 46, 99, 1);
            color: var(--dark-bg);
        }

        #upcoming {
            background: linear-gradient(135deg, var(--primary-blue), var(--accent-red));
            padding: 5rem;
            border-radius: 25px;
            max-width: 1200px;
            margin: 5rem auto;
            box-shadow: var(--neon-glow);
            animation: blackHole 3s infinite alternate;
            position: relative;
            overflow: hidden;
            z-index: 10;
            transform: translateZ(30px);
        }

        #upcoming::after {
            content: '⚡️';
            position: absolute;
            top: 30px;
            right: 30px;
            font-size: 4rem;
            animation: zap 1s infinite alternate;
        }

        @keyframes zap {
            0% { transform: translateZ(0) scale(1); opacity: 1; }
            100% { transform: translateZ(20px) scale(1.2); opacity: 0.7; }
        }

        @keyframes blackHole {
            0% { box-shadow: 0 0 30px var(--primary-blue); transform: translateZ(30px) scale(1); }
            100% { box-shadow: 0 0 150px var(--accent-red); transform: translateZ(50px) scale(1.1); }
        }

        #upcoming h3 {
            font-family: 'Orbitron', sans-serif;
            font-size: 3rem;
            font-weight: 700;
            color: var(--light-text);
            text-shadow: var(--neon-glow);
            transform: translateZ(20px);
        }

        #upcoming p {
            font-size: 2rem;
            font-weight: 300;
            color: var(--dark-bg);
            transform: translateZ(10px);
        }

        .connect-btn {
            display: inline-block;
            margin: 4rem 0;
            background: linear-gradient(90deg, var(--primary-blue), var(--accent-red));
            color: var(--light-text);
            padding: 2.5rem 5rem;
            border-radius: 80px;
            text-decoration: none;
            font-weight: 700;
            font-size: 2.5rem;
            transition: var(--transition);
            box-shadow: var(--neon-glow);
            position: relative;
            overflow: hidden;
            transform: translateZ(30px);
            z-index: 10; /* Ensure button is clickable */
        }

        .connect-btn::before {
            content: '';
            position: absolute;
            top: -100%;
            left: -100%;
            width: 300%;
            height: 300%;
            background: radial-gradient(circle, rgba(255, 255, 255, 0.5), transparent);
            opacity: 0;
            transition: opacity 0.5s ease;
        }

        .connect-btn:hover::before {
            opacity: 1;
        }

        .connect-btn:hover {
            transform: translateZ(50px) scale(1.2) rotateX(10deg);
            box-shadow: 0 0 150px rgba(0, 212, 255, 1);
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 4rem;
            margin-top: 4rem;
            transform: translateZ(20px);
        }

        .social-btn {
            width: 120px;
            height: 120px;
            background: rgba(255, 255, 255, 0.1);
            color: var(--light-text);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 4rem;
            transition: var(--transition);
            border: 4px solid var(--primary-blue);
            position: relative;
            transform-style: preserve-3d;
            z-index: 10; /* Ensure social buttons are clickable */
        }

        .social-btn:hover {
            background: var(--accent-red);
            transform: translateZ(40px) scale(1.4) rotateY(360deg);
            box-shadow: var(--neon-glow);
            border-color: var(--light-text);
        }

        footer {
            background: rgba(10, 15, 28, 0.98);
            padding: 4rem;
            text-align: center;
            font-size: 1.5rem;
            color: var(--primary-blue);
            box-shadow: var(--neon-glow);
            z-index: 10;
            position: relative;
            transform: translateZ(20px);
        }

        /* Audio Visualizer */
        #visualizer {
            position: fixed;
            bottom: 0;
            left: 0;
            width: 100%;
            height: 150px;
            z-index: -1;
            opacity: 0.7;
            transform: translateZ(-50px);
        }

        @media (max-width: 768px) {
            .logo-text { font-size: 6rem; }
            nav ul { flex-direction: column; gap: 2.5rem; }
            .music-grid { grid-template-columns: 1fr; }
            h2 { font-size: 3rem; }
            .social-btn { width: 80px; height: 80px; font-size: 2.5rem; }
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
        <p>March 2025 – Detonate the Multiverse</p>
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
        <p>© 2025 TREY | Trevor Coburn - Master of Infinite Realms</p>
    </footer>

    <script>
        // 3D Holographic Background with Three.js
        const scene = new THREE.Scene();
        const camera = new THREE.PerspectiveCamera(75, window.innerWidth / window.innerHeight, 0.1, 1000);
        const renderer = new THREE.WebGLRenderer({ alpha: true });
        renderer.setSize(window.innerWidth, window.innerHeight);
        document.getElementById('scene').appendChild(renderer.domElement);

        const geometry = new THREE.IcosahedronGeometry(15, 1);
        const material = new THREE.ShaderMaterial({
            uniforms: {
                time: { value: 0 },
                color1: { value: new THREE.Color(0x00d4ff) },
                color2: { value: new THREE.Color(0xff2e63) }
            },
            vertexShader: `
                varying vec3 vNormal;
                void main() {
                    vNormal = normal;
                    gl_Position = projectionMatrix * modelViewMatrix * vec4(position, 1.0);
                }
            `,
            fragmentShader: `
                uniform float time;
                uniform vec3 color1;
                uniform vec3 color2;
                varying vec3 vNormal;
                void main() {
                    float t = sin(time) * 0.5 + 0.5;
                    vec3 color = mix(color1, color2, t * abs(vNormal.y));
                    gl_FragColor = vec4(color, 0.8);
                }
            `,
            wireframe: true
        });
        const icosahedron = new THREE.Mesh(geometry, material);
        scene.add(icosahedron);

        const light = new THREE.PointLight(0xffffff, 1.5, 100);
        light.position.set(20, 20, 20);
        scene.add(light);

        camera.position.z = 40;

        const gui = new dat.GUI();
        gui.add({ rotateSpeed: 0.01 }, 'rotateSpeed', 0, 0.1).onChange(val => rotateSpeed = val);
        gui.hide(); // Uncomment to show controls

        let rotateSpeed = 0.01;
        let time = 0;

        function animate3D() {
            requestAnimationFrame(animate3D);
            time += 0.05;
            material.uniforms.time.value = time;
            icosahedron.rotation.x += rotateSpeed;
            icosahedron.rotation.y += rotateSpeed;
            renderer.render(scene, camera);
        }
        animate3D();

        window.addEventListener('resize', () => {
            renderer.setSize(window.innerWidth, window.innerHeight);
            camera.aspect = window.innerWidth / window.innerHeight;
            camera.updateProjectionMatrix();
            visualizerCanvas.width = window.innerWidth;
        });

        // Smooth Scroll with PreventDefault Fix
        document.querySelectorAll('nav a').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({ behavior: 'smooth' });
                }
            });
        });

        // Audio Visualizer with Generative Effects
        const audio = new Audio('https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3'); // Replace with Trey's track
        audio.loop = true;
        audio.volume = 0.4;
        audio.play();

        const visualizerCanvas = document.getElementById('visualizer');
        const vCtx = visualizerCanvas.getContext('2d');
        visualizerCanvas.width = window.innerWidth;
        visualizerCanvas.height = 150;

        const audioCtx = new (window.AudioContext || window.webkitAudioContext)();
        const analyser = audioCtx.createAnalyser();
        const source = audioCtx.createMediaElementSource(audio);
        source.connect(analyser);
        analyser.connect(audioCtx.destination);
        analyser.fftSize = 512;

        const bufferLength = analyser.frequencyBinCount;
        const dataArray = new Uint8Array(bufferLength);

        function drawVisualizer() {
            requestAnimationFrame(drawVisualizer);
            analyser.getByteFrequencyData(dataArray);
            vCtx.clearRect(0, 0, visualizerCanvas.width, visualizerCanvas.height);

            const barWidth = (visualizerCanvas.width / bufferLength) * 2;
            let x = 0;

            for (let i = 0; i < bufferLength; i++) {
                const barHeight = dataArray[i] * 1.5;
                const hue = (i / bufferLength) * 360;
                vCtx.fillStyle = `hsl(${hue}, 100%, 50%)`;
                vCtx.fillRect(x, visualizerCanvas.height - barHeight, barWidth, barHeight);
                vCtx.fillStyle = `hsla(${hue}, 100%, 50%, 0.3)`;
                vCtx.fillRect(x, 0, barWidth, barHeight / 2);
                x += barWidth + 2;
            }
        }
        drawVisualizer();

        // Mouse Interaction
        document.addEventListener('mousemove', (e) => {
            const mouseX = (e.clientX / window.innerWidth - 0.5) * 2;
            const mouseY = (e.clientY / window.innerHeight - 0.5) * 2;
            icosahedron.rotation.x = mouseY * 0.5;
            icosahedron.rotation.y = mouseX * 0.5;
        });
    </script>
</body>
</html>
