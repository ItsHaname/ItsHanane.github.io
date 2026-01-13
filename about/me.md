---
layout: default
title: About
nav: about
---

<style>
/* --- ANIMATIONS --- */
@keyframes matrixRain {
    0% { transform: translateY(-100vh); }
    100% { transform: translateY(100vh); }
}

@keyframes float {
    0%, 100% { transform: translateY(0px); }
    50% { transform: translateY(-20px); }
}

@keyframes gradientShift {
    0% { background-position: 0% 50%; }
    50% { background-position: 100% 50%; }
    100% { background-position: 0% 50%; }
}

@keyframes blink {
    0%, 100% { opacity: 1; }
    50% { opacity: 0; }
}

/* --- BASE STYLES --- */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    background: #050810;
    min-height: 100vh;
    font-family: 'Segoe UI', Roboto, sans-serif;
    color: #e2e8f0;
    overflow-x: hidden;
}

body::before {
    content: '';
    position: fixed;
    top: 0; left: 0; width: 100%; height: 100%;
    background: 
        radial-gradient(circle at 10% 20%, rgba(59, 130, 246, 0.1) 0%, transparent 40%),
        radial-gradient(circle at 90% 80%, rgba(37, 99, 235, 0.05) 0%, transparent 40%);
    z-index: 0;
}

.binary-background {
    position: fixed;
    top: 0; left: 0; width: 100%; height: 100%;
    pointer-events: none;
    z-index: 1;
}

.binary-digit {
    position: absolute;
    font-family: 'Courier New', monospace;
    color: rgba(59, 130, 246, 0.15);
    animation: matrixRain linear infinite;
}

/* --- LAYOUT FULL WIDTH (L'ÉLARGISSEMENT) --- */
.about-container {
    width: 100%;             /* Prend 100% de la largeur */
    max-width: 100vw;        /* Aucune limite de pixels */
    margin: 0;
    padding: 60px 40px;      /* Espacement léger sur les bords écran */
    position: relative;
    z-index: 2;
}

.main-layout {
    display: grid;
    grid-template-columns: 450px 1fr; /* Sidebar fixe, le reste s'étire à l'infini */
    gap: 40px;
    align-items: start;
}

/* --- SIDEBAR --- */
.profile-sidebar {
    position: sticky;
    top: 40px;
}

.profile-card {
    background: rgba(15, 23, 42, 0.7);
    backdrop-filter: blur(15px);
    border: 1px solid rgba(59, 130, 246, 0.3);
    border-radius: 40px;
    padding: 60px 40px;
    text-align: center;
}

.profile-image-wrapper {
    width: 280px;
    height: 280px;
    margin: 0 auto 30px;
}

.profile-image {
    width: 100%;
    height: 100%;
    border-radius: 50%;
    border: 4px solid #3b82f6;
    overflow: hidden;
    animation: float 6s ease-in-out infinite;
}

.profile-image img {
    width: 100%;
    height: 100%;
    object-fit: cover;
}

.profile-name {
    font-size: 3.5em;
    font-weight: 800;
    background: linear-gradient(135deg, #fff 0%, #3b82f6 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
}

.profile-info {
    margin-top: 40px;
    text-align: left;
    background: rgba(30, 41, 59, 0.5);
    padding: 30px;
    border-radius: 20px;
}

/* --- CONTENT AREA (EXTRA LARGE) --- */
.content-area {
    display: flex;
    flex-direction: column;
    gap: 30px;
    width: 100%; /* S'assure de prendre tout le reste de l'écran */
}

.content-header h1 {
    font-size: 8vw; /* Taille dynamique : énorme sur grand écran */
    font-weight: 900;
    line-height: 0.9;
    letter-spacing: -5px;
    background: linear-gradient(to right, #ffffff, #3b82f6, #2563eb);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    animation: gradientShift 5s linear infinite;
}

/* Les carrés deviennent des bannières larges */
.content-section {
    width: 100%; 
    background: rgba(15, 23, 42, 0.5);
    backdrop-filter: blur(10px);
    border: 1px solid rgba(255, 255, 255, 0.1);
    border-left: 8px solid #3b82f6;
    border-radius: 30px;
    padding: 80px; /* Espace interne immense pour le look premium */
    transition: background 0.3s ease;
}

.content-section h2 {
    font-size: 3.5em;
    color: #60a5fa;
    margin-bottom: 30px;
}

.content-section p {
    font-size: 1.5em; /* Texte plus grand pour remplir l'espace */
    line-height: 1.6;
    color: #cbd5e1;
    max-width: 90%; /* Évite que les lignes soient trop longues à lire */
}

/* Grille de Focus qui s'étale sur 3 ou 4 colonnes selon l'écran */
.focus-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(400px, 1fr)); 
    gap: 30px;
    margin-top: 40px;
    width: 100%;
}

.focus-item {
    background: rgba(30, 41, 59, 0.4);
    border: 1px solid rgba(59, 130, 246, 0.2);
    border-radius: 25px;
    padding: 50px;
    transition: all 0.3s ease;
}

.focus-item:hover {
    background: rgba(59, 130, 246, 0.15);
    transform: translateY(-10px);
}

.focus-item h3 {
    font-size: 2em;
    color: #fff;
    margin-bottom: 20px;
}

.highlight {
    color: #60a5fa;
    font-weight: 700;
}

/* RESPONSIVE */
@media (max-width: 1300px) {
    .main-layout { grid-template-columns: 1fr; }
    .profile-sidebar { position: relative; }
    .content-header h1 { font-size: 12vw; }
}
</style>

<div class="binary-background" id="binaryBg"></div>

<div class="about-container">
    <div class="main-layout">
        <aside class="profile-sidebar">
            <div class="profile-card">
                <div class="profile-image-wrapper">
                    <div class="profile-image">
                        <img src="https://github.com/user-attachments/assets/6c553521-15b0-4d1a-aa6f-798d79f1c896" alt="Hanane">
                    </div>
                </div>
                <h2 class="profile-name">HANANE</h2>
                <p style="color: #94a3b8; font-size: 1.3em;">Network Security Student</p>
                
 <div class="profile-info">
                    <p style="margin-bottom:10px;"><strong>Location:</strong> Marrakech, MA</p>
                    <p style="margin-bottom:10px;"><strong>University:</strong> FSSM</p>
                    <p><strong>Status:</strong> Active Learner</p>
                </div>
            </div>
        </aside>

 <main class="content-area">
            <div class="content-header">
                <h1>WELCOME TO<br>CYBERIA.</h1>
                <p style="font-size: 2.5em; color: #94a3b8; letter-spacing: 2px;">// SCANNING FOR VULNERABILITIES</p>
            </div>

   <section class="content-section">
                <h2>01. Background</h2>
                <p>
                    I am <span class="highlight">Hanane</span>, specializing in <span class="highlight">vulnerability analysis</span> and <span class="highlight">offensive tactics</span>. 
                    This blog is designed as an ultra-wide digital terminal to document my research at FSSM and beyond.
                </p>
            </section>

 <section class="content-section">
                <h2>02. Learning Path</h2>
                <div class="focus-grid">
                    <div class="focus-item">
                        <h3>Academic</h3>
                        <p>Core networking and cybersecurity modules from the NSC program.</p>
                    </div>
                    <div class="focus-item">
                        <h3>Pentesting</h3>
                        <p>Real-world labs and TryHackMe challenge walkthroughs.</p>
                    </div>
                    <div class="focus-item">
                        <h3>Home Lab</h3>
                        <p>High-scale virtual environments for testing security protocols.</p>
                    </div>
                    <div class="focus-item">
                        <h3>Research</h3>
                        <p>Deep dives into binary exploitation and reverse engineering.</p>
                    </div>
                </div>
            </section>
        </main>
    </div>
</div>

<script>
function createBinaryBackground() {
    const container = document.getElementById('binaryBg');
    for (let i = 0; i < 100; i++) {
        const digit = document.createElement('div');
        digit.className = 'binary-digit';
        digit.textContent = Math.random() > 0.5 ? '0' : '1';
        digit.style.left = Math.random() * 100 + '%';
        digit.style.fontSize = (Math.random() * 10 + 15) + 'px';
        digit.style.animationDuration = (Math.random() * 10 + 5) + 's';
        digit.style.opacity = Math.random() * 0.2;
        container.appendChild(digit);
    }
}
createBinaryBackground();
</script>
