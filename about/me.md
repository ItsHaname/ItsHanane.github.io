---
layout: default
title: About
nav: about
---

<style>
@keyframes matrixRain {
    0% { transform: translateY(-100vh); }
    100% { transform: translateY(100vh); }
}

@keyframes float {
    0%, 100% { transform: translateY(0px); }
    50% { transform: translateY(-15px); }
}

@keyframes gradientShift {
    0% { background-position: 0% 50%; }
    50% { background-position: 100% 50%; }
    100% { background-position: 0% 50%; }
}

@keyframes fadeIn {
    from { opacity: 0; transform: translateY(30px); }
    to { opacity: 1; transform: translateY(0); }
}

@keyframes slideInLeft {
    from { opacity: 0; transform: translateX(-40px); }
    to { opacity: 1; transform: translateX(0); }
}

@keyframes slideInRight {
    from { opacity: 0; transform: translateX(40px); }
    to { opacity: 1; transform: translateX(0); }
}

@keyframes pulse {
    0%, 100% { box-shadow: 0 0 20px rgba(59, 130, 246, 0.3); }
    50% { box-shadow: 0 0 40px rgba(59, 130, 246, 0.6); }
}

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    background: #0a0e1a;
    min-height: 100vh;
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
    color: #e2e8f0;
    overflow-x: hidden;
}

body::before {
    content: '';
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: radial-gradient(ellipse at top, rgba(59, 130, 246, 0.15) 0%, transparent 60%);
    pointer-events: none;
    z-index: 0;
}

.binary-background {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    pointer-events: none;
    z-index: 0;
    overflow: hidden;
}

.binary-digit {
    position: absolute;
    font-family: 'Courier New', monospace;
    font-size: 16px;
    color: rgba(59, 130, 246, 0.1);
    opacity: 0;
    animation: matrixRain linear infinite;
}

.cv-container {
    max-width: 1600px;
    margin: 0 auto;
    padding: 80px 50px;
    position: relative;
    z-index: 1;
}

/* Hero Banner - Full Width */
.hero-banner {
    background: linear-gradient(135deg, rgba(15, 23, 42, 0.95), rgba(30, 41, 59, 0.9));
    backdrop-filter: blur(20px);
    border: 1px solid rgba(59, 130, 246, 0.3);
    border-radius: 30px;
    padding: 80px;
    margin-bottom: 60px;
    position: relative;
    overflow: hidden;
    animation: fadeIn 1s ease-out;
}

.hero-banner::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    height: 4px;
    background: linear-gradient(90deg, #3b82f6, #60a5fa, #3b82f6);
    background-size: 200% auto;
    animation: gradientShift 3s linear infinite;
}

.hero-content {
    display: grid;
    grid-template-columns: 320px 1fr;
    gap: 60px;
    align-items: center;
}

.hero-photo {
    width: 320px;
    height: 320px;
    border-radius: 50%;
    overflow: hidden;
    border: 5px solid #3b82f6;
    animation: float 6s ease-in-out infinite, pulse 3s ease-in-out infinite;
    box-shadow: 0 20px 60px rgba(59, 130, 246, 0.5);
}

.hero-photo img {
    width: 100%;
    height: 100%;
    object-fit: cover;
}

.hero-text h1 {
    font-size: 4.5em;
    font-weight: 900;
    background: linear-gradient(135deg, #ffffff, #60a5fa);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    margin-bottom: 20px;
    letter-spacing: 1px;
}

.hero-text .role {
    font-size: 2em;
    color: #60a5fa;
    margin-bottom: 25px;
    font-weight: 600;
}

.hero-text .bio {
    font-size: 1.3em;
    color: #cbd5e1;
    line-height: 1.8;
    margin-bottom: 30px;
}

.hero-stats {
    display: flex;
    gap: 40px;
    margin-top: 30px;
}

.stat-item {
    text-align: center;
}

.stat-value {
    font-size: 2em;
    color: #60a5fa;
    font-weight: 700;
    display: block;
}

.stat-label {
    font-size: 1em;
    color: #94a3b8;
    margin-top: 5px;
}

.highlight {
    color: #60a5fa;
    font-weight: 700;
}

/* Main Layout - Sidebar + Content */
.main-content {
    display: grid;
    grid-template-columns: 400px 1fr;
    gap: 50px;
}

/* Left Sidebar */
.sidebar {
    animation: slideInLeft 1s ease-out;
}

.sidebar-section {
    background: rgba(15, 23, 42, 0.8);
    backdrop-filter: blur(10px);
    border: 1px solid rgba(59, 130, 246, 0.3);
    border-radius: 25px;
    padding: 40px;
    margin-bottom: 30px;
    transition: all 0.3s ease;
}

.sidebar-section:hover {
    border-color: #3b82f6;
    box-shadow: 0 10px 30px rgba(59, 130, 246, 0.3);
}

.sidebar-section h3 {
    font-size: 1.8em;
    color: #60a5fa;
    margin-bottom: 25px;
    font-weight: 700;
    display: flex;
    align-items: center;
    gap: 12px;
}

.sidebar-section h3::before {
    content: '';
    width: 4px;
    height: 30px;
    background: linear-gradient(180deg, #3b82f6, #60a5fa);
    border-radius: 2px;
}

.info-item {
    display: flex;
    justify-content: space-between;
    padding: 15px 0;
    border-bottom: 1px solid rgba(59, 130, 246, 0.2);
}

.info-item:last-child {
    border-bottom: none;
}

.info-label {
    color: #94a3b8;
    font-size: 1.05em;
}

.info-value {
    color: #60a5fa;
    font-weight: 600;
    font-size: 1.05em;
}

.skill-tag {
    display: inline-block;
    background: rgba(59, 130, 246, 0.15);
    color: #60a5fa;
    padding: 10px 18px;
    border-radius: 10px;
    margin: 6px 6px 6px 0;
    font-size: 0.95em;
    border: 1px solid rgba(59, 130, 246, 0.3);
    transition: all 0.3s ease;
}

.skill-tag:hover {
    background: rgba(59, 130, 246, 0.3);
    transform: translateY(-2px);
}

/* Right Content Area */
.content-area {
    animation: slideInRight 1s ease-out;
}

.content-section {
    background: rgba(15, 23, 42, 0.8);
    backdrop-filter: blur(10px);
    border: 1px solid rgba(59, 130, 246, 0.3);
    border-radius: 25px;
    padding: 50px;
    margin-bottom: 40px;
    transition: all 0.3s ease;
}

.content-section:hover {
    border-color: #3b82f6;
    box-shadow: 0 10px 30px rgba(59, 130, 246, 0.3);
}

.content-section h2 {
    font-size: 2.5em;
    color: #60a5fa;
    margin-bottom: 35px;
    font-weight: 700;
    display: flex;
    align-items: center;
    gap: 15px;
}

.content-section h2::before {
    content: '';
    width: 6px;
    height: 40px;
    background: linear-gradient(180deg, #3b82f6, #60a5fa);
    border-radius: 3px;
}

.content-section p {
    color: #cbd5e1;
    line-height: 1.9;
    font-size: 1.15em;
    margin-bottom: 20px;
}

/* Cards Grid */
.cards-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 25px;
    margin-top: 30px;
}

.content-card {
    background: rgba(30, 41, 59, 0.6);
    border: 1px solid rgba(59, 130, 246, 0.25);
    border-radius: 18px;
    padding: 30px;
    transition: all 0.3s ease;
}

.content-card:hover {
    background: rgba(30, 41, 59, 0.8);
    border-color: #3b82f6;
    transform: translateY(-5px);
    box-shadow: 0 8px 25px rgba(59, 130, 246, 0.3);
}

.content-card h3 {
    font-size: 1.5em;
    color: #fff;
    margin-bottom: 12px;
    font-weight: 600;
}

.content-card .meta {
    color: #60a5fa;
    font-size: 1em;
    margin-bottom: 15px;
    font-weight: 500;
}

.content-card ul {
    list-style: none;
    padding: 0;
}

.content-card li {
    color: #cbd5e1;
    padding-left: 20px;
    position: relative;
    margin-bottom: 8px;
    line-height: 1.6;
}

.content-card li::before {
    content: '▹';
    position: absolute;
    left: 0;
    color: #3b82f6;
    font-size: 1.2em;
}

/* Timeline Style for Education */
.timeline-item {
    position: relative;
    padding-left: 40px;
    margin-bottom: 30px;
}

.timeline-item::before {
    content: '';
    position: absolute;
    left: 0;
    top: 8px;
    width: 12px;
    height: 12px;
    background: #3b82f6;
    border-radius: 50%;
    box-shadow: 0 0 0 4px rgba(59, 130, 246, 0.2);
}

.timeline-item::after {
    content: '';
    position: absolute;
    left: 5px;
    top: 20px;
    width: 2px;
    height: calc(100% + 10px);
    background: rgba(59, 130, 246, 0.3);
}

.timeline-item:last-child::after {
    display: none;
}

.timeline-item h3 {
    font-size: 1.5em;
    color: #fff;
    margin-bottom: 8px;
}

.timeline-item .period {
    color: #60a5fa;
    font-size: 1.05em;
    margin-bottom: 12px;
    font-weight: 500;
}

.timeline-item p {
    color: #cbd5e1;
    line-height: 1.7;
}

/* Responsive */
@media (max-width: 1400px) {
    .main-content {
        grid-template-columns: 380px 1fr;
    }
}

@media (max-width: 1200px) {
    .main-content {
        grid-template-columns: 1fr;
    }
    
    .hero-content {
        grid-template-columns: 1fr;
        text-align: center;
    }
    
    .hero-photo {
        margin: 0 auto;
    }
    
    .hero-stats {
        justify-content: center;
    }
}

@media (max-width: 768px) {
    .cv-container {
        padding: 40px 25px;
    }
    
    .hero-banner {
        padding: 50px 35px;
    }
    
    .hero-text h1 {
        font-size: 3em;
    }
    
    .hero-photo {
        width: 250px;
        height: 250px;
    }
    
    .cards-grid {
        grid-template-columns: 1fr;
    }
    
    .hero-stats {
        flex-direction: column;
        gap: 20px;
    }
}
</style>

<div class="binary-background" id="binaryBg"></div>

<div class="cv-container">
    <!-- Hero Banner -->
    <section class="hero-banner">
        <div class="hero-content">
            <div class="hero-photo">
                <img src="https://github.com/user-attachments/assets/6c553521-15b0-4d1a-aa6f-798d79f1c896" alt="Hanane AIT BAH">
            </div>
            
   <div class="hero-text">
                <h1>HANANE AIT BAH</h1>
                <p class="role">Network Security Student | Cybersecurity Enthusiast</p>
                <p class="bio">
                    Passionate about <span class="highlight">offensive security</span>, <span class="highlight">vulnerability analysis</span>, and <span class="highlight">reverse engineering</span>. Currently pursuing a Bachelor's in Networking and Cybersecurity at FSSM, Cadi Ayyad University.
                </p>
                
  <div class="hero-stats">
                    <div class="stat-item">
                        <span class="stat-value">2026</span>
                        <span class="stat-label">Blog Launch</span>
                    </div>
                    <div class="stat-item">
                        <span class="stat-value">NSC</span>
                        <span class="stat-label">Program</span>
                    </div>
                    <div class="stat-item">
                        <span class="stat-value">FSSM</span>
                        <span class="stat-label">University</span>
        </div>
   </div>
            </div>
        </div>
    </section>

    <!-- Main Layout -->
<div class="main-content">
        <!-- Left Sidebar -->
        <aside class="sidebar">
            <!-- Contact Info -->
            <div class="sidebar-section">
                <h3>Contact Info</h3>
                <div class="info-item">
                    <span class="info-label">Location</span>
                    <span class="info-value">Marrakech, MA</span>
                </div>
                <div class="info-item">
                    <span class="info-label">University</span>
                    <span class="info-value">FSSM</span>
                </div>
                <div class="info-item">
                    <span class="info-label">Program</span>
                    <span class="info-value">NSC</span>
                </div>
            </div>

            <!-- Skills -->
<div class="sidebar-section">
                <h3>Focus Areas</h3>
                <div>
                    <div class="skill-tag">Penetration Testing</div>
                    <div class="skill-tag">Network Defense</div>
                    <div class="skill-tag">Vulnerability Analysis</div>
                    <div class="skill-tag">CTF Challenges</div>
                    <div class="skill-tag">Linux Systems</div>
                    <div class="skill-tag">Virtual Labs</div>
                    <div class="skill-tag">TryHackMe</div>
                    <div class="skill-tag">Security Research</div>
                </div>
            </div>
        </aside>

        <!-- Right Content -->
  <main class="content-area">
            <!-- Education -->
            <section class="content-section">
                <h2>Education</h2>
                <div class="timeline-item">
                    <h3>Bachelor's in Networking & Cybersecurity</h3>
                    <p class="period">FSSM, Cadi Ayyad University | 2024 - Present</p>
                    <p>Specialized program focusing on network defense, penetration testing, and security protocols. Building strong foundations in system administration and threat analysis.</p>
                </div>
                <div class="timeline-item">
                    <h3>Computer Science Foundations</h3>
                    <p class="period">FSSM | 2022 - 2024</p>
                    <p>Core studies in programming, algorithms, databases, and computer architecture. Developed strong problem-solving skills and technical fundamentals.</p>
                </div>
            </section>

            <!-- What You'll Find Here -->
 <section class="content-section">
                <h2>What You'll Find Here</h2>
                <div class="cards-grid">
                    <div class="content-card">
                        <h3>Academic Notes</h3>
                        <p class="meta">NSC Program @ FSSM</p>
                        <ul>
                            <li>Network security fundamentals</li>
                            <li>Course materials and study guides</li>
                            <li>University projects and labs</li>
                        </ul>
                    </div>
                    
  <div class="content-card">
                        <h3>TryHackMe Journey</h3>
                        <p class="meta">Practical Cybersecurity Training</p>
                        <ul>
                            <li>Completed challenges and rooms</li>
                            <li>Detailed write-ups and walkthroughs</li>
                            <li>Skills development tracking</li>
                        </ul>
                    </div>
                    
<div class="content-card">
                        <h3>Personal Lab</h3>
                        <p class="meta">Hands-On Learning Environment</p>
                        <ul>
                            <li>Virtual machine configurations</li>
                            <li>Network topologies and setups</li>
                            <li>Security experiments and tests</li>
                        </ul>
                    </div>
                    
<div class="content-card">
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

            <!-- About This Blog -->
   <section class="content-section">
       <h2>About This Blog</h2>
     <p>
                    On January 1st, 2026, I launched <span class="highlight">Cyberia</span> to document my journey through the world of cybersecurity. This blog serves as both a personal learning journal and a resource for others interested in the field.
                </p>
       <p>
                    The content here reflects my academic path at FSSM, hands-on practice through platforms like TryHackMe, and my experiments in building a home lab for security testing. This is a living record of what I learn, the challenges I face, and the progress I make.
                </p>
       <p>
                    Whether you're a fellow student, a cybersecurity enthusiast, or just curious about the field, I hope you find something useful here. Welcome to Cyberia.
                </p>
   </section>
   </main>
    </div>
</div>

<script>
function createBinaryBackground() {
    const container = document.getElementById('binaryBg');
    const binaryChars = ['0', '1'];
    const numberOfDigits = 50;

    for (let i = 0; i < numberOfDigits; i++) {
        const digit = document.createElement('div');
        digit.className = 'binary-digit';
        digit.textContent = binaryChars[Math.floor(Math.random() * 2)];
        digit.style.left = Math.random() * 100 + '%';
        digit.style.animationDuration = (Math.random() * 10 + 10) + 's';
        digit.style.animationDelay = Math.random() * 5 + 's';
        digit.style.opacity = Math.random() * 0.5 + 0.1;
        container.appendChild(digit);
    }
}

createBinaryBackground();
</script>
