---
layout: default
title: ItsHanane - Cybersecurity Student
---

<style>
  @import url('https://fonts.googleapis.com/css2?family=Fira+Code:wght@400;700&display=swap');
  
  :root {
    --neon-green: #00ff88;
    --neon-blue: #00d4ff;
    --neon-pink: #ff00ff;
    --dark-bg: #0a0e27;
    --card-bg: #1a1f3a;
  }
  
  body {
    background: linear-gradient(135deg, #0a0e27 0%, #1a1f3a 50%, #0a0e27 100%);
    color: #fff;
    font-family: 'Segoe UI', system-ui, sans-serif;
    line-height: 1.6;
  }
  
  .hero-banner {
    text-align: center;
    padding: 4rem 2rem;
    background: linear-gradient(135deg, rgba(0,255,136,0.1), rgba(0,212,255,0.1));
    border-radius: 20px;
    margin: 2rem 0;
    border: 2px solid var(--neon-green);
    box-shadow: 0 0 40px rgba(0,255,136,0.3);
    animation: glow 3s ease-in-out infinite alternate;
  }
  
  @keyframes glow {
    from { box-shadow: 0 0 20px rgba(0,255,136,0.3); }
    to { box-shadow: 0 0 60px rgba(0,212,255,0.5); }
  }
  
  .hero-title {
    font-size: 3.5rem;
    font-weight: bold;
    background: linear-gradient(135deg, var(--neon-green), var(--neon-blue), var(--neon-pink));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    margin-bottom: 1rem;
    text-shadow: 0 0 30px rgba(0,255,136,0.5);
  }
  
  .hero-subtitle {
    font-size: 1.5rem;
    color: var(--neon-green);
    margin-bottom: 1.5rem;
    font-family: 'Fira Code', monospace;
  }
  
  .terminal-line {
    font-family: 'Fira Code', monospace;
    color: var(--neon-green);
    font-size: 1.2rem;
    border-left: 3px solid var(--neon-green);
    padding-left: 1rem;
    margin: 1rem 0;
  }
  
  .category-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 2rem;
    margin: 3rem 0;
  }
  
  .category-card {
    background: rgba(26, 31, 58, 0.8);
    border: 2px solid var(--neon-green);
    border-radius: 15px;
    padding: 2rem;
    transition: all 0.3s ease;
    position: relative;
    overflow: hidden;
  }
  
  .category-card::before {
    content: '';
    position: absolute;
    top: -50%;
    left: -50%;
    width: 200%;
    height: 200%;
    background: linear-gradient(45deg, transparent, rgba(0,255,136,0.1), transparent);
    transform: rotate(45deg);
    transition: all 0.5s;
  }
  
  .category-card:hover {
    transform: translateY(-10px) scale(1.02);
    box-shadow: 0 15px 50px rgba(0,255,136,0.4);
    border-color: var(--neon-blue);
  }
  
  .category-card:hover::before {
    top: -100%;
    left: -100%;
  }
  
  .category-icon {
    font-size: 3rem;
    margin-bottom: 1rem;
    display: block;
  }
  
  .category-title {
    color: var(--neon-green);
    font-size: 1.8rem;
    margin-bottom: 1rem;
    font-weight: bold;
  }
  
  .category-desc {
    color: #bbb;
    margin-bottom: 1rem;
    line-height: 1.8;
  }
  
  .category-link {
    color: var(--neon-blue);
    text-decoration: none;
    font-weight: bold;
    display: inline-flex;
    align-items: center;
    transition: all 0.3s;
  }
  
  .category-link:hover {
    color: var(--neon-pink);
    gap: 10px;
  }
  
  .stats-container {
    display: flex;
    justify-content: space-around;
    flex-wrap: wrap;
    margin: 3rem 0;
    gap: 2rem;
  }
  
  .stat-box {
    background: rgba(26, 31, 58, 0.8);
    border: 2px solid var(--neon-blue);
    border-radius: 15px;
    padding: 2rem;
    text-align: center;
    min-width: 200px;
    transition: all 0.3s;
  }
  
  .stat-box:hover {
    transform: scale(1.1);
    box-shadow: 0 10px 40px rgba(0,212,255,0.4);
  }
  
  .stat-number {
    font-size: 3rem;
    color: var(--neon-green);
    font-weight: bold;
    font-family: 'Fira Code', monospace;
  }
  
  .stat-label {
    color: #bbb;
    font-size: 1.1rem;
    margin-top: 0.5rem;
  }
  
  .project-item {
    background: rgba(26, 31, 58, 0.8);
    border-left: 4px solid var(--neon-green);
    padding: 1.5rem;
    margin: 1.5rem 0;
    border-radius: 10px;
    transition: all 0.3s;
  }
  
  .project-item:hover {
    transform: translateX(10px);
    box-shadow: -10px 0 40px rgba(0,255,136,0.3);
  }
  
  .project-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 1rem;
    flex-wrap: wrap;
  }
  
  .project-title {
    color: var(--neon-blue);
    font-size: 1.5rem;
    font-weight: bold;
  }
  
  .project-lang {
    background: rgba(0,255,136,0.2);
    color: var(--neon-green);
    padding: 0.3rem 1rem;
    border-radius: 20px;
    font-size: 0.9rem;
    border: 1px solid var(--neon-green);
  }
  
  .tags {
    display: flex;
    gap: 0.5rem;
    flex-wrap: wrap;
    margin-top: 1rem;
  }
  
  .tag {
    background: rgba(0,212,255,0.2);
    color: var(--neon-blue);
    padding: 0.3rem 0.8rem;
    border-radius: 15px;
    font-size: 0.85rem;
    border: 1px solid var(--neon-blue);
  }
  
  .skill-bar-container {
    margin: 1.5rem 0;
  }
  
  .skill-name {
    display: flex;
    justify-content: space-between;
    color: var(--neon-green);
    margin-bottom: 0.5rem;
    font-weight: bold;
  }
  
  .skill-bar {
    height: 10px;
    background: rgba(255,255,255,0.1);
    border-radius: 10px;
    overflow: hidden;
    border: 1px solid rgba(0,255,136,0.3);
  }
  
  .skill-progress {
    height: 100%;
    background: linear-gradient(90deg, var(--neon-green), var(--neon-blue));
    border-radius: 10px;
    transition: width 2s ease;
  }
  
  .social-links {
    display: flex;
    justify-content: center;
    gap: 2rem;
    margin: 3rem 0;
    flex-wrap: wrap;
  }
  
  .social-btn {
    display: inline-flex;
    align-items: center;
    gap: 0.5rem;
    padding: 1rem 2rem;
    background: transparent;
    border: 2px solid var(--neon-green);
    color: var(--neon-green);
    text-decoration: none;
    border-radius: 10px;
    font-weight: bold;
    transition: all 0.3s;
  }
  
  .social-btn:hover {
    background: var(--neon-green);
    color: var(--dark-bg);
    transform: scale(1.1);
    box-shadow: 0 0 30px var(--neon-green);
  }
  
  .section-title {
    font-size: 2.5rem;
    text-align: center;
    margin: 3rem 0 2rem 0;
    background: linear-gradient(135deg, var(--neon-green), var(--neon-blue));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    font-weight: bold;
  }
  
  blockquote {
    border-left: 4px solid var(--neon-pink);
    padding-left: 1.5rem;
    margin: 2rem 0;
    font-style: italic;
    color: #bbb;
    background: rgba(255,0,255,0.1);
    padding: 1rem 1rem 1rem 1.5rem;
    border-radius: 5px;
  }
  
  @media (max-width: 768px) {
    .hero-title { font-size: 2rem; }
    .hero-subtitle { font-size: 1.2rem; }
    .category-grid { grid-template-columns: 1fr; }
    .project-header { flex-direction: column; align-items: flex-start; gap: 0.5rem; }
  }
</style>

<div class="hero-banner">
  <h1 class="hero-title">⚡ CYBERSECURITY STUDENT</h1>
  <p class="hero-subtitle">Passionnée par la sécurité offensive & défensive</p>
  <div class="terminal-line">
    root@hanane:~$ whoami<br>
    → Étudiante en Cybersécurité | Ethical Hacker | CTF Player
  </div>
</div>

---

## 🎯 Catégories

<div class="category-grid">
  <div class="category-card">
    <span class="category-icon">🔓</span>
    <h3 class="category-title">Pentesting</h3>
    <p class="category-desc">Tests d'intrusion, méthodologies, outils et writeups TryHackMe, HackTheBox, Root-Me.</p>
    <a href="#pentesting" class="category-link">Explorer Pentesting →</a>
  </div>

  <div class="category-card">
    <span class="category-icon">🌐</span>
    <h3 class="category-title">Réseau</h3>
    <p class="category-desc">Protocoles, sécurité réseau, concepts fondamentaux, TCP/IP, firewalls, IDS/IPS.</p>
    <a href="#reseau" class="category-link">Explorer Réseau →</a>
  </div>

  <div class="category-card">
    <span class="category-icon">🕸️</span>
    <h3 class="category-title">Web Security</h3>
    <p class="category-desc">OWASP Top 10, vulnérabilités web, sécurisation d'applications, XSS, SQLi, CSRF.</p>
    <a href="#websec" class="category-link">Explorer Web Security →</a>
  </div>

  <div class="category-card">
    <span class="category-icon">🔐</span>
    <h3 class="category-title">Cryptographie</h3>
    <p class="category-desc">Chiffrement, hachage, signatures numériques, PKI, SSL/TLS, algorithmes modernes.</p>
    <a href="#crypto" class="category-link">Explorer Cryptographie →</a>
  </div>

  <div class="category-card">
    <span class="category-icon">🦠</span>
    <h3 class="category-title">Malware Analysis</h3>
    <p class="category-desc">Analyse de malwares, reverse engineering, détection de menaces, forensics.</p>
    <a href="#malware" class="category-link">Explorer Malware →</a>
  </div>

  <div class="category-card">
    <span class="category-icon">🚩</span>
    <h3 class="category-title">CTF Writeups</h3>
    <p class="category-desc">Solutions détaillées de challenges CTF, techniques d'exploitation, méthodologies.</p>
    <a href="#ctf" class="category-link">Explorer CTF →</a>
  </div>
</div>

---

<h2 class="section-title">📊 Statistiques</h2>

<div class="stats-container">
  <div class="stat-box">
    <div class="stat-number">50+</div>
    <div class="stat-label">CTF Résolus</div>
  </div>
  <div class="stat-box">
    <div class="stat-number">20+</div>
    <div class="stat-label">Articles Publiés</div>
  </div>
  <div class="stat-box">
    <div class="stat-number">15+</div>
    <div class="stat-label">Projets GitHub</div>
  </div>
  <div class="stat-box">
    <div class="stat-number">5+</div>
    <div class="stat-label">Certifications</div>
  </div>
</div>

---

<h2 class="section-title">💻 Compétences Techniques</h2>

<div class="skill-bar-container">
  <div class="skill-name">
    <span>🐍 Python</span>
    <span>90%</span>
  </div>
  <div class="skill-bar">
    <div class="skill-progress" style="width: 90%"></div>
  </div>
</div>

<div class="skill-bar-container">
  <div class="skill-name">
    <span>🐧 Linux / Kali</span>
    <span>85%</span>
  </div>
  <div class="skill-bar">
    <div class="skill-progress" style="width: 85%"></div>
  </div>
</div>

<div class="skill-bar-container">
  <div class="skill-name">
    <span>🌐 Network Security</span>
    <span>80%</span>
  </div>
  <div class="skill-bar">
    <div class="skill-progress" style="width: 80%"></div>
  </div>
</div>

<div class="skill-bar-container">
  <div class="skill-name">
    <span>🕸️ Web Security (OWASP)</span>
    <span>75%</span>
  </div>
  <div class="skill-bar">
    <div class="skill-progress" style="width: 75%"></div>
  </div>
</div>

<div class="skill-bar-container">
  <div class="skill-name">
    <span>🔐 Cryptographie</span>
    <span>70%</span>
  </div>
  <div class="skill-bar">
    <div class="skill-progress" style="width: 70%"></div>
  </div>
</div>

<div class="skill-bar-container">
  <div class="skill-name">
    <span>🔍 Reverse Engineering</span>
    <span>65%</span>
  </div>
  <div class="skill-bar">
    <div class="skill-progress" style="width: 65%"></div>
  </div>
</div>

---

<h2 class="section-title">🚀 Projets Récents</h2>

<div class="project-item">
  <div class="project-header">
    <h3 class="project-title">🔐 Password Manager CLI</h3>
    <span class="project-lang">Python</span>
  </div>
  <p>Gestionnaire de mots de passe sécurisé en ligne de commande avec chiffrement AES-256-GCM, génération de mots de passe forts et authentification maître.</p>
  <div class="tags">
    <span class="tag">Python</span>
    <span class="tag">Cryptography</span>
    <span class="tag">CLI</span>
    <span class="tag">AES-256</span>
  </div>
</div>

<div class="project-item">
  <div class="project-header">
    <h3 class="project-title">🕷️ Web Vulnerability Scanner</h3>
    <span class="project-lang">Python</span>
  </div>
  <p>Scanner automatisé pour détecter les vulnérabilités web courantes : SQL Injection, XSS, CSRF, headers de sécurité manquants.</p>
  <div class="tags">
    <span class="tag">Python</span>
    <span class="tag">Web Security</span>
    <span class="tag">OWASP</span>
    <span class="tag">Automation</span>
  </div>
</div>

<div class="project-item">
  <div class="project-header">
    <h3 class="project-title">🔍 Network Traffic Analyzer</h3>
    <span class="project-lang">Python / Scapy</span>
  </div>
  <p>Analyseur de trafic réseau pour capturer et analyser les paquets en temps réel, détecter les anomalies et visualiser les données.</p>
  <div class="tags">
    <span class="tag">Scapy</span>
    <span class="tag">Network</span>
    <span class="tag">Packet Analysis</span>
    <span class="tag">IDS</span>
  </div>
</div>

<div class="project-item">
  <div class="project-header">
    <h3 class="project-title">🎯 CTF Solutions Repository</h3>
    <span class="project-lang">Multi-language</span>
  </div>
  <p>Collection complète de mes solutions de CTF avec writeups détaillés : HackTheBox, TryHackMe, Root-Me, PicoCTF.</p>
  <div class="tags">
    <span class="tag">CTF</span>
    <span class="tag">Writeups</span>
    <span class="tag">Pentesting</span>
    <span class="tag">Learning</span>
  </div>
</div>

---

<h2 class="section-title">📚 Derniers Articles</h2>

### 🔥 Introduction à la Cryptographie Moderne
**📅 15 Décembre 2024** | ⏱️ 8 min de lecture

Découvrez les fondamentaux de la cryptographie : chiffrement symétrique vs asymétrique, fonctions de hachage, et applications pratiques.

**Tags:** `Cryptographie` `Sécurité` `AES` `RSA`

[Lire l'article →](#)

---

### 🌐 Analyse OWASP Top 10 - 2024
**📅 10 Décembre 2024** | ⏱️ 12 min de lecture

Guide complet des 10 vulnérabilités web les plus critiques avec exemples pratiques et techniques de mitigation.

**Tags:** `Web Security` `OWASP` `Vulnerabilities` `Best Practices`

[Lire l'article →](#)

---

### 🚩 CTF Write-up : HackTheBox - Pentester Academy
**📅 5 Décembre 2024** | ⏱️ 15 min de lecture

Résolution détaillée d'un challenge HTB niveau intermédiaire : reconnaissance, exploitation, élévation de privilèges.

**Tags:** `CTF` `HackTheBox` `PenTesting` `Linux`

[Lire l'article →](#)

---

<h2 class="section-title">🎓 Certifications & Formations</h2>

- ✅ **eJPT** - eLearnSecurity Junior Penetration Tester
- 📖 **CEH** - Certified Ethical Hacker *(en cours)*
- ✅ **OWASP Top 10** - Formation complète
- ✅ **TryHackMe** - Learning Paths completed
- 📖 **OSCP** - Offensive Security *(préparation)*

---

<h2 class="section-title">📧 Contact & Réseaux</h2>

<div class="social-links">
  <a href="https://github.com/ItsHanane" class="social-btn">
    ⚡ GitHub
  </a>
  <a href="https://linkedin.com/in/yourprofile" class="social-btn">
    💼 LinkedIn
  </a>
  <a href="mailto:your.email@example.com" class="social-btn">
    📧 Email
  </a>
  <a href="https://twitter.com/yourhandle" class="social-btn">
    🐦 Twitter
  </a>
</div>

---

> *"La sécurité n'est pas un produit, mais un processus."* - Bruce Schneier

---

<div style="text-align: center; margin-top: 4rem; padding: 2rem; border-top: 2px solid var(--neon-green);">
  <p style="color: var(--neon-green); font-family: 'Fira Code', monospace;">
    © 2024 ItsHanane | Fait avec 💚 et ☕ | Powered by GitHub Pages
  </p>
  <p style="color: #666; font-size: 0.9rem; margin-top: 1rem;">
    "The only truly secure system is one that is powered off" - Gene Spafford
  </p>
</div>

