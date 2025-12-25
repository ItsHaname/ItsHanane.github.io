<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ItsHanane - Cybersecurity Student</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: #0a0e27;
            color: #fff;
            overflow-x: hidden;
        }

        /* Animated Background */
        .bg-animation {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            background: linear-gradient(45deg, #0a0e27, #1a1f3a, #0a0e27);
            background-size: 400% 400%;
            animation: gradient 15s ease infinite;
        }

        @keyframes gradient {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        /* Matrix Effect */
        .matrix {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            opacity: 0.1;
        }

        /* Header */
        header {
            background: rgba(10, 14, 39, 0.8);
            backdrop-filter: blur(10px);
            padding: 1rem 0;
            position: sticky;
            top: 0;
            z-index: 1000;
            border-bottom: 2px solid #00ff88;
            box-shadow: 0 4px 30px rgba(0, 255, 136, 0.1);
        }

        nav {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 2rem;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: bold;
            background: linear-gradient(135deg, #00ff88, #00d4ff);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            text-shadow: 0 0 30px rgba(0, 255, 136, 0.5);
        }

        .nav-links {
            display: flex;
            gap: 2rem;
            list-style: none;
        }

        .nav-links a {
            color: #fff;
            text-decoration: none;
            font-weight: 500;
            transition: all 0.3s;
            position: relative;
        }

        .nav-links a:hover {
            color: #00ff88;
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: #00ff88;
            transition: width 0.3s;
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        /* Hero Section */
        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            padding: 2rem;
            position: relative;
        }

        .hero-content h1 {
            font-size: 4rem;
            margin-bottom: 1rem;
            background: linear-gradient(135deg, #00ff88, #00d4ff, #ff00ff);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: glow 2s ease-in-out infinite alternate;
        }

        @keyframes glow {
            from { filter: drop-shadow(0 0 20px #00ff88); }
            to { filter: drop-shadow(0 0 40px #00d4ff); }
        }

        .hero-content .subtitle {
            font-size: 1.5rem;
            color: #00ff88;
            margin-bottom: 2rem;
            font-weight: 300;
        }

        .terminal-text {
            font-family: 'Courier New', monospace;
            color: #00ff88;
            font-size: 1.2rem;
            margin-bottom: 2rem;
        }

        .cta-buttons {
            display: flex;
            gap: 1rem;
            justify-content: center;
            flex-wrap: wrap;
        }

        .btn {
            padding: 1rem 2rem;
            border: 2px solid #00ff88;
            background: transparent;
            color: #00ff88;
            cursor: pointer;
            font-size: 1rem;
            font-weight: bold;
            transition: all 0.3s;
            text-decoration: none;
            display: inline-block;
            position: relative;
            overflow: hidden;
        }

        .btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, #00ff88, transparent);
            transition: left 0.5s;
        }

        .btn:hover::before {
            left: 100%;
        }

        .btn:hover {
            background: #00ff88;
            color: #0a0e27;
            box-shadow: 0 0 30px #00ff88;
        }

        /* Categories Section */
        .categories {
            max-width: 1200px;
            margin: 4rem auto;
            padding: 2rem;
        }

        .section-title {
            font-size: 2.5rem;
            text-align: center;
            margin-bottom: 3rem;
            background: linear-gradient(135deg, #00ff88, #00d4ff);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .cards-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .card {
            background: rgba(26, 31, 58, 0.6);
            border: 1px solid #00ff88;
            border-radius: 15px;
            padding: 2rem;
            transition: all 0.3s;
            backdrop-filter: blur(10px);
            position: relative;
            overflow: hidden;
        }

        .card::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, transparent, rgba(0, 255, 136, 0.1), transparent);
            transform: rotate(45deg);
            transition: all 0.5s;
        }

        .card:hover::before {
            top: -100%;
            left: -100%;
        }

        .card:hover {
            transform: translateY(-10px);
            box-shadow: 0 10px 50px rgba(0, 255, 136, 0.3);
            border-color: #00d4ff;
        }

        .card-icon {
            font-size: 3rem;
            margin-bottom: 1rem;
        }

        .card h3 {
            color: #00ff88;
            margin-bottom: 1rem;
            font-size: 1.5rem;
        }

        .card p {
            color: #bbb;
            line-height: 1.6;
            margin-bottom: 1rem;
        }

        .card-link {
            color: #00d4ff;
            text-decoration: none;
            font-weight: bold;
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            transition: all 0.3s;
        }

        .card-link:hover {
            color: #00ff88;
            gap: 1rem;
        }

        /* Skills Section */
        .skills {
            max-width: 1200px;
            margin: 4rem auto;
            padding: 2rem;
        }

        .skills-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
        }

        .skill-item {
            background: rgba(26, 31, 58, 0.6);
            padding: 1.5rem;
            border-radius: 10px;
            border: 1px solid rgba(0, 255, 136, 0.3);
        }

        .skill-name {
            display: flex;
            justify-content: space-between;
            margin-bottom: 0.5rem;
            color: #00ff88;
        }

        .skill-bar {
            height: 8px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 10px;
            overflow: hidden;
        }

        .skill-progress {
            height: 100%;
            background: linear-gradient(90deg, #00ff88, #00d4ff);
            border-radius: 10px;
            animation: fillBar 2s ease-out;
        }

        @keyframes fillBar {
            from { width: 0; }
        }

        /* Projects Section */
        .projects {
            max-width: 1200px;
            margin: 4rem auto;
            padding: 2rem;
        }

        .project-card {
            background: rgba(26, 31, 58, 0.6);
            border: 1px solid #00ff88;
            border-radius: 15px;
            padding: 2rem;
            margin-bottom: 2rem;
            transition: all 0.3s;
        }

        .project-card:hover {
            transform: translateX(10px);
            box-shadow: -10px 0 50px rgba(0, 255, 136, 0.2);
        }

        .project-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 1rem;
        }

        .project-title {
            color: #00d4ff;
            font-size: 1.5rem;
        }

        .project-tags {
            display: flex;
            gap: 0.5rem;
            flex-wrap: wrap;
            margin-top: 1rem;
        }

        .tag {
            background: rgba(0, 255, 136, 0.2);
            color: #00ff88;
            padding: 0.3rem 0.8rem;
            border-radius: 20px;
            font-size: 0.9rem;
            border: 1px solid #00ff88;
        }

        /* Contact Section */
        .contact {
            max-width: 800px;
            margin: 4rem auto;
            padding: 2rem;
            text-align: center;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 2rem;
            margin-top: 2rem;
            flex-wrap: wrap;
        }

        .social-link {
            width: 60px;
            height: 60px;
            border: 2px solid #00ff88;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: #00ff88;
            text-decoration: none;
            font-size: 1.5rem;
            transition: all 0.3s;
        }

        .social-link:hover {
            background: #00ff88;
            color: #0a0e27;
            transform: scale(1.2) rotate(360deg);
            box-shadow: 0 0 30px #00ff88;
        }

        /* Footer */
        footer {
            background: rgba(10, 14, 39, 0.8);
            text-align: center;
            padding: 2rem;
            margin-top: 4rem;
            border-top: 2px solid #00ff88;
        }

        /* Mobile Menu */
        .mobile-menu {
            display: none;
            font-size: 1.5rem;
            cursor: pointer;
        }

        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }
            .mobile-menu {
                display: block;
            }
            .hero-content h1 {
                font-size: 2.5rem;
            }
            .hero-content .subtitle {
                font-size: 1.2rem;
            }
        }

        /* Typing Animation */
        .typing {
            overflow: hidden;
            border-right: .15em solid #00ff88;
            white-space: nowrap;
            animation: typing 3.5s steps(40, end), blink-caret .75s step-end infinite;
        }

        @keyframes typing {
            from { width: 0 }
            to { width: 100% }
        }

        @keyframes blink-caret {
            from, to { border-color: transparent }
            50% { border-color: #00ff88; }
        }
    </style>
</head>
<body>
    <div class="bg-animation"></div>
    <canvas class="matrix"></canvas>

    <header>
        <nav>
            <div class="logo">⚡ ItsHanane</div>
            <ul class="nav-links">
                <li><a href="#home">Accueil</a></li>
                <li><a href="#categories">Catégories</a></li>
                <li><a href="#skills">Compétences</a></li>
                <li><a href="#projects">Projets</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
            <div class="mobile-menu">☰</div>
        </nav>
    </header>

    <section class="hero" id="home">
        <div class="hero-content">
            <h1>CYBERSECURITY STUDENT</h1>
            <div class="subtitle">Passionnée par la sécurité offensive & défensive</div>
            <div class="terminal-text typing">root@hanane:~$ ./hack_the_planet.sh</div>
            <div class="cta-buttons">
                <a href="#projects" class="btn">Voir mes projets</a>
                <a href="#contact" class="btn">Me contacter</a>
            </div>
        </div>
    </section>

    <section class="categories" id="categories">
        <h2 class="section-title">🎯 Catégories</h2>
        <div class="cards-grid">
            <div class="card">
                <div class="card-icon">🔓</div>
                <h3>Pentesting</h3>
                <p>Tests d'intrusion, méthodologies, outils et writeups TryHackMe, HackTheBox, Root-Me.</p>
                <a href="#" class="card-link">Explorer Pentesting →</a>
            </div>

            <div class="card">
                <div class="card-icon">🌐</div>
                <h3>Réseau</h3>
                <p>Protocoles, sécurité réseau, concepts fondamentaux, TCP/IP, firewalls, IDS/IPS.</p>
                <a href="#" class="card-link">Explorer Réseau →</a>
            </div>

            <div class="card">
                <div class="card-icon">🕸️</div>
                <h3>Web Security</h3>
                <p>OWASP Top 10, vulnérabilités web, sécurisation d'applications, XSS, SQLi, CSRF.</p>
                <a href="#" class="card-link">Explorer Web Security →</a>
            </div>

            <div class="card">
                <div class="card-icon">🔐</div>
                <h3>Cryptographie</h3>
                <p>Chiffrement, hachage, signatures numériques, PKI, SSL/TLS, algorithmes modernes.</p>
                <a href="#" class="card-link">Explorer Cryptographie →</a>
            </div>

            <div class="card">
                <div class="card-icon">🦠</div>
                <h3>Malware Analysis</h3>
                <p>Analyse de malwares, reverse engineering, détection de menaces, forensics.</p>
                <a href="#" class="card-link">Explorer Malware →</a>
            </div>

            <div class="card">
                <div class="card-icon">🚩</div>
                <h3>CTF Writeups</h3>
                <p>Solutions détaillées de challenges CTF, techniques d'exploitation, méthodologies.</p>
                <a href="#" class="card-link">Explorer CTF →</a>
            </div>
        </div>
    </section>

    <section class="skills" id="skills">
        <h2 class="section-title">💻 Compétences Techniques</h2>
        <div class="skills-container">
            <div class="skill-item">
                <div class="skill-name">
                    <span>Python</span>
                    <span>90%</span>
                </div>
                <div class="skill-bar">
                    <div class="skill-progress" style="width: 90%"></div>
                </div>
            </div>

            <div class="skill-item">
                <div class="skill-name">
                    <span>Linux / Kali</span>
                    <span>85%</span>
                </div>
                <div class="skill-bar">
                    <div class="skill-progress" style="width: 85%"></div>
                </div>
            </div>

            <div class="skill-item">
                <div class="skill-name">
                    <span>Network Security</span>
                    <span>80%</span>
                </div>
                <div class="skill-bar">
                    <div class="skill-progress" style="width: 80%"></div>
                </div>
            </div>

            <div class="skill-item">
                <div class="skill-name">
                    <span>Web Security</span>
                    <span>75%</span>
                </div>
                <div class="skill-bar">
                    <div class="skill-progress" style="width: 75%"></div>
                </div>
            </div>

            <div class="skill-item">
                <div class="skill-name">
                    <span>Cryptography</span>
                    <span>70%</span>
                </div>
                <div class="skill-bar">
                    <div class="skill-progress" style="width: 70%"></div>
                </div>
            </div>

            <div class="skill-item">
                <div class="skill-name">
                    <span>Reverse Engineering</span>
                    <span>65%</span>
                </div>
                <div class="skill-bar">
                    <div class="skill-progress" style="width: 65%"></div>
                </div>
            </div>
        </div>
    </section>

    <section class="projects" id="projects">
        <h2 class="section-title">🚀 Projets Récents</h2>

        <div class="project-card">
            <div class="project-header">
                <h3 class="project-title">🔐 Password Manager CLI</h3>
                <span>Python</span>
            </div>
            <p>Gestionnaire de mots de passe sécurisé en ligne de commande avec chiffrement AES-256-GCM, génération de mots de passe forts et authentification maître.</p>
            <div class="project-tags">
                <span class="tag">Python</span>
                <span class="tag">Cryptography</span>
                <span class="tag">CLI</span>
                <span class="tag">AES-256</span>
            </div>
        </div>

        <div class="project-card">
            <div class="project-header">
                <h3 class="project-title">🕷️ Web Vulnerability Scanner</h3>
                <span>Python</span>
            </div>
            <p>Scanner automatisé pour détecter les vulnérabilités web : SQL Injection, XSS, CSRF, headers de sécurité manquants. Interface CLI intuitive.</p>
            <div class="project-tags">
                <span class="tag">Python</span>
                <span class="tag">Web Security</span>
                <span class="tag">OWASP</span>
                <span class="tag">Automation</span>
            </div>
        </div>

        <div class="project-card">
            <div class="project-header">
                <h3 class="project-title">🔍 Network Traffic Analyzer</h3>
                <span>Python / Scapy</span>
            </div>
            <p>Analyseur de trafic réseau pour capturer et analyser les paquets en temps réel, détecter les anomalies et visualiser les données.</p>
            <div class="project-tags">
                <span class="tag">Scapy</span>
                <span class="tag">Network</span>
                <span class="tag">Security</span>
                <span class="tag">Monitoring</span>
            </div>
        </div>
    </section>

    <section class="contact" id="contact">
        <h2 class="section-title">📧 Restons en Contact</h2>
        <p style="color: #bbb; margin-bottom: 2rem;">N'hésitez pas à me contacter pour collaborer sur des projets ou simplement discuter de cybersécurité !</p>
        <div class="social-links">
            <a href="https://github.com/ItsHanane" class="social-link" title="GitHub">
                <span>⚡</span>
            </a>
            <a href="https://linkedin.com/in/yourprofile" class="social-link" title="LinkedIn">
                <span>💼</span>
            </a>
            <a href="mailto:your.email@example.com" class="social-link" title="Email">
                <span>📧</span>
            </a>
            <a href="https://twitter.com/yourhandle" class="social-link" title="Twitter">
                <span>🐦</span>
            </a>
        </div>
    </section>

    <footer>
        <p>© 2024 ItsHanane | Fait avec 💚 et ☕ | Powered by GitHub Pages</p>
        <p style="margin-top: 1rem; color: #00ff88; font-family: 'Courier New', monospace;">
            "The only truly secure system is one that is powered off" - Gene Spafford
        </p>
    </footer>

    <script>
        // Matrix Rain Effect
        const canvas = document.querySelector('.matrix');
        const ctx = canvas.getContext('2d');

        canvas.width = window.innerWidth;
        canvas.height = window.innerHeight;

        const chars = '01アイウエオカキクケコサシスセソタチツテトナニヌネノハヒフヘホマミムメモヤユヨラリルレロワヲン';
        const charArray = chars.split('');
        const fontSize = 14;
        const columns = canvas.width / fontSize;
        const drops = [];

        for (let i = 0; i < columns; i++) {
            drops[i] = 1;
        }

        function drawMatrix() {
            ctx.fillStyle = 'rgba(10, 14, 39, 0.05)';
            ctx.fillRect(0, 0, canvas.width, canvas.height);

            ctx.fillStyle = '#00ff88';
            ctx.font = fontSize + 'px monospace';

            for (let i = 0; i < drops.length; i++) {
                const text = charArray[Math.floor(Math.random() * charArray.length)];
                ctx.fillText(text, i * fontSize, drops[i] * fontSize);

                if (drops[i] * fontSize > canvas.height && Math.random() > 0.975) {
                    drops[i] = 0;
                }
                drops[i]++;
            }
        }

        setInterval(drawMatrix, 35);

        window.addEventListener('resize', () => {
            canvas.width = window.innerWidth;
            canvas.height = window.innerHeight;
        });

        // Smooth Scrolling
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({ behavior: 'smooth' });
                }
            });
        });

        // Mobile Menu Toggle
        const mobileMenu = document.querySelector('.mobile-menu');
        const navLinks = document.querySelector('.nav-links');

        mobileMenu.addEventListener('click', () => {
            navLinks.style.display = navLinks.style.display === 'flex' ? 'none' : 'flex';
        });
    </script>
</body>
</html>
