<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>TREY | Trevor Coburn</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;500;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary-blue: #00c4ff;
            --accent-red: #ff1e56;
            --dark-bg: #0a0f1c;
            --light-text: #f0f0f0;
            --shadow-glow: 0 0 20px rgba(0, 196, 255, 0.4);
            --transition: all 0.3s ease;
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

        /* Subtle Background Gradient */
        body::before {
            content: '';
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, rgba(0, 196, 255, 0.05), rgba(255, 30, 86, 0.05));
            z-index: -1;
        }

        header {
            position: relative;
            text-align: center;
            padding: 3rem 1rem;
            background: linear-gradient(135deg, rgba(0, 196, 255, 0.2), rgba(255, 30, 86, 0.2));
        }

        .logo-text {
            font-size: 3.5rem;
            font-weight: 700;
            letter-spacing: 2px;
            color: var(--light-text);
            text-transform: uppercase;
            text-shadow: var(--shadow-glow);
            transition: var(--transition);
        }

        .logo-text:hover {
            color: var(--primary-blue);
        }

        .tagline {
            font-size: 1.2rem;
            font-weight: 300;
            color: var(--primary-blue);
            margin-top: 0.5rem;
        }

        nav {
            background: rgba(10, 15, 28, 0.9);
            position: sticky;
            top: 0;
            z-index: 1000;
            backdrop-filter: blur(8px);
            padding: 1rem 0;
        }

        nav ul {
            display: flex;
            justify-content: center;
            gap: 2rem;
        }

        nav a {
            color: var(--light-text);
            text-decoration: none;
            font-size: 1.1rem;
            font-weight: 500;
            text-transform: uppercase;
            position: relative;
            transition: var(--transition);
        }

        nav a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--primary-blue);
            transition: width 0.3s ease;
        }

        nav a:hover::after {
            width: 100%;
        }

        nav a:hover {
            color: var(--primary-blue);
        }

        .section {
            padding: 4rem 2rem;
            max-width: 1200px;
            margin: 0 auto;
            text-align: center;
        }

        h2 {
            font-size: 2.2rem;
            font-weight: 700;
            color: var(--primary-blue);
            margin-bottom: 2rem;
            text-transform: uppercase;
        }

        .music-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 1.5rem;
        }

        .music-link {
            background: rgba(255, 255, 255, 0.05);
            padding: 1.5rem;
            border-radius: 8px;
            color: var(--light-text);
            text-decoration: none;
            font-weight: 500;
            font-size: 1.1rem;
            transition: var(--transition);
            position: relative;
            overflow: hidden;
        }

        .music-link:hover {
            background: var(--primary-blue);
            transform: translateY(-5px);
            box-shadow: var(--shadow-glow);
        }

        #upcoming {
            background: linear-gradient(90deg, var(--primary-blue), var(--accent-red));
            padding: 2rem;
            border-radius: 10px;
            max-width: 600px;
            margin: 2rem auto;
            box-shadow: var(--shadow-glow);
            animation: pulseGlow 2s infinite alternate;
        }

        @keyframes pulseGlow {
            0% { box-shadow: 0 0 10px var(--primary-blue); }
            100% { box-shadow: 0 0 25px var(--accent-red); }
        }

        #upcoming h3 {
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--light-text);
        }

        #upcoming p {
            font-size: 1.1rem;
            font-weight: 300;
        }

        .connect-btn {
            display: inline-block;
            margin: 2rem 0;
            background: var(--primary-blue);
            color: var(--dark-bg);
            padding: 1rem 2.5rem;
            border-radius: 30px;
            text-decoration: none;
            font-weight: 500;
            font-size: 1.2rem;
            transition: var(--transition);
        }

        .connect-btn:hover {
            background: var(--accent-red);
            color: var(--light-text);
            transform: scale(1.05);
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 1.5rem;
            margin-top: 1.5rem;
        }

        .social-btn {
            width: 50px;
            height: 50px;
            background: rgba(255, 255, 255, 0.1);
            color: var(--light-text);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.3rem;
            transition: var(--transition);
        }

        .social-btn:hover {
            background: var(--primary-blue);
            transform: scale(1.1);
        }

        footer {
            background: rgba(10, 15, 28, 0.9);
            padding: 1.5rem;
            text-align: center;
            font-size: 0.9rem;
            color: var(--primary-blue);
        }

        @media (max-width: 768px) {
            .logo-text { font-size: 2.5rem; }
            nav ul { flex-direction: column; gap: 1rem; }
            .music-grid { grid-template-columns: 1fr; }
        }
    </style>
</head>
<body>
    <header>
        <h1 class="logo-text">TREY</h1>
        <p class="tagline">Trevor Coburn • Sound of the Future</p>
    </header>

    <nav>
        <ul>
            <li><a href="#music">Music</a></li>
            <li><a href="#contact">Connect</a></li>
        </ul>
    </nav>

    <div id="upcoming">
        <h3>NEW SINGLE "LINK IN BIO"</h3>
        <p>March 2025 – Get Ready to Vibe</p>
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
    </script>
</body>
</html>
