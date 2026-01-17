---
layout: default
title: About
nav: about
---
<link rel="icon" href="https://raw.githubusercontent.com/ItsHaname/ItsHaname.github.io/main/logo" type="image/png">
<style>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
    background: #0a0e1a;
    color: #e2e8f0;
    line-height: 1.7; /* Légèrement augmenté pour plus de confort */
    font-size: 1.1em;   /* Texte de base un peu plus grand */
}

.container {
    max-width: 1300px; /* Élargi à 1300px pour occuper plus d'espace */
    width: 92%;
    margin: 0 auto;
    padding: 80px 0;   /* Plus d'espace en haut et en bas */
}

/* Hero Section */
.hero {
    text-align: center;
    margin-bottom: 70px;
    padding-bottom: 50px;
    border-bottom: 2px solid rgba(59, 130, 246, 0.2);
}

.hero-image-container {
    position: relative;
    width: 320px;      /* Photo légèrement plus grande */
    height: 320px;
    margin: 0 auto 35px;
    border-radius: 50%;
    overflow: hidden;
    border: 6px solid #00d4ff;
    box-shadow: 
        0 0 40px rgba(0, 212, 255, 0.4),
        0 15px 50px rgba(59, 130, 246, 0.3);
    background: #0a0e1a;
}

.hero img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    object-position: center 30%;
    display: block;
    transform: scale(1.15);
}

.hero h1 {
    font-size: 3.2em;   /* Titre principal plus grand */
    color: #fff;
    margin-bottom: 15px;
    letter-spacing: 1px;
}

.hero .role {
    font-size: 1.5em;   /* Rôle plus visible */
    color: #60a5fa;
    margin-bottom: 25px;
}

.hero .bio {
    font-size: 1.2em;
    color: #cbd5e1;
    max-width: 900px;  /* Bio plus large pour s'aligner sur le nouveau style */
    margin: 0 auto 40px;
}

.stats {
    display: flex;
    justify-content: center;
    gap: 80px;         /* Plus d'espace entre les stats */
    margin-top: 40px;
}

.stat-value {
    font-size: 2.2em;   /* Chiffres des stats plus grands */
    color: #60a5fa;
    font-weight: 700;
    display: block;
}

/* Section */
section {
    margin-bottom: 70px;
}

section h2 {
    color: #60a5fa;
    font-size: 2.4em;   /* Titres de sections plus grands */
    margin-bottom: 30px;
    padding-bottom: 12px;
    border-bottom: 2px solid rgba(59, 130, 246, 0.3);
}

/* Cards Grid */
.cards {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(350px, 1fr)); /* Cartes plus larges */
    gap: 30px;
    margin-top: 30px;
}

.card {
    background: rgba(15, 23, 42, 0.6);
    border: 1px solid rgba(59, 130, 246, 0.3);
    border-radius: 15px;
    padding: 35px;      /* Plus de padding interne */
}

.card h3 {
    font-size: 1.5em;
}

/* Responsive */
@media (max-width: 1024px) {
    .container {
        max-width: 900px;
    }
}

@media (max-width: 768px) {
    .container {
        padding: 40px 20px;
        width: 100%;
    }
    .hero h1 { font-size: 2.2em; }
    .hero-image-container { width: 220px; height: 220px; }
    .stats { flex-direction: column; gap: 30px; }
}
</style>

<div class="container">
    <div class="hero">
        <div class="hero-image-container">
            <img src="/assets/images/me.png" alt="Hanane AIT BAH">
        </div>
        <h1>HANANE AIT BAH</h1>
        <p class="role">Network Security Student | Cybersecurity Enthusiast</p>
        <p class="bio">
            Passionate about <span class="highlight">offensive security</span>, <span class="highlight">vulnerability analysis</span>, and <span class="highlight">reverse engineering</span>. Currently pursuing a Bachelor's in Networking and Cybersecurity at FSSM, Cadi Ayyad University.
        </p>
        
  <div class="stats">
            <div class="stat">
                <span class="stat-value">2026</span>
                <span class="stat-label">Blog Launch</span>
            </div>
            <div class="stat">
                <span class="stat-value">NSC</span>
                <span class="stat-label">Program</span>
            </div>
            <div class="stat">
                <span class="stat-value">FSSM</span>
                <span class="stat-label">University</span>
            </div>
        </div>
    </div>

 <section>
        <h2>Focus Areas</h2>
        <div class="skills">
            <div class="skill-tag">Penetration Testing</div>
            <div class="skill-tag">Network Defense</div>
            <div class="skill-tag">Vulnerability Analysis</div>
            <div class="skill-tag">CTF Challenges</div>
            <div class="skill-tag">Linux Systems</div>
            <div class="skill-tag">Virtual Labs</div>
            <div class="skill-tag">TryHackMe</div>
            <div class="skill-tag">Security Research</div>
        </div>
    </section>

  <section>
        <h2>Education</h2>
        <div class="timeline-item">
            <h3>Bachelor's in Networking & Cybersecurity</h3>
            <p class="period">FSSM, Cadi Ayyad University | 2025-2026 - Present</p>
            <p>Specialized program focusing on network defense, penetration testing, and security protocols. Building strong foundations in system administration and threat analysis.</p>
        </div>
        <div class="timeline-item">
            <h3>Computer Science Foundations</h3>
            <p class="period">FSSM | 2023 - 2025</p>
            <p>Core studies in programming, algorithms, databases, and computer architecture. and technical fundamentals.</p>
        </div>
    </section>

  <section>
        <h2>What You'll Find Here</h2>
        <div class="cards">
            <div class="card">
                <h3>Academic Notes</h3>
                <p class="meta">NSC Program @ FSSM</p>
                <ul>
                    <li>Network security fundamentals</li>
                    <li>Course materials and study guides</li>
                    <li>University projects and labs</li>
                </ul>
            </div>
            <div class="card">
                <h3>TryHackMe Journey</h3>
                <p class="meta">Practical Cybersecurity Training</p>
                <ul>
                    <li>Completed challenges and rooms</li>
                    <li>Detailed write-ups and walkthroughs</li>
                    <li>Skills development tracking</li>
                </ul>
            </div>
            <div class="card">
                <h3>Personal Lab</h3>
                <p class="meta">Hands-On Learning Environment</p>
                <ul>
                    <li>Virtual machine configurations</li>
                    <li>Network topologies and setups</li>
                    <li>Security experiments and tests</li>
                </ul>
            </div>
            <div class="card">
                <h3>Learning Resources</h3>
                <p class="meta">Community & Knowledge Sharing</p>
                <ul>
                    <li>Curated study materials</li>
                    <li>Tools and software reviews</li>
                    <li>Security best practices</li>
                </ul>
            </div>
        </div>
    </section>

 <section>
        <h2>About This Blog</h2>
        <p>On January 1st, 2026, I launched <span class="highlight">Cyberia</span> to document my journey through the world of cybersecurity. This blog serves as both a personal learning journal and a resource for others interested in the field.</p>
        <p>The content here reflects my academic path at FSSM, hands-on practice through platforms like TryHackMe, and my experiments in building a home lab for security testing. This is a living record of what I learn, the challenges I face, and the progress I make.</p>
        <p>Whether you're a fellow student, a cybersecurity enthusiast, or just curious about the field, I hope you find something useful here. Welcome to Cyberia.</p>
    </section>
</div>
