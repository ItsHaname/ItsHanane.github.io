---
layout: default
title: TryHackMe
nav: tryhackme
---

<style>
:root {
  --cyber-teal: #00ffff;
  --cyber-purple: #9d00ff;
  --cyber-pink: #ff00ff;
  --dark-bg: #0a0a0a;
  --darker-bg: #050505;
  --text-glow: #ffffff;
}

body {
  background-color: var(--dark-bg);
  color: var(--text-glow);
  font-family: 'Courier New', monospace;
  margin: 0;
  padding: 0;
  overflow-x: hidden;
}

/* Matrix rain effect */
.matrix-bg {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: -1;
  opacity: 0.1;
  pointer-events: none;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 2rem;
  position: relative;
}

/* Header */
.header {
  text-align: center;
  padding: 3rem 0;
  border-bottom: 2px solid var(--cyber-teal);
  margin-bottom: 3rem;
  position: relative;
}

.header::before {
  content: '';
  position: absolute;
  bottom: -2px;
  left: 25%;
  width: 50%;
  height: 4px;
  background: linear-gradient(90deg, 
    transparent, 
    var(--cyber-purple), 
    var(--cyber-pink), 
    var(--cyber-purple), 
    transparent);
  filter: blur(2px);
}

.title {
  font-size: 4rem;
  margin: 0;
  color: var(--cyber-teal);
  text-shadow: 
    0 0 10px var(--cyber-teal),
    0 0 20px var(--cyber-teal);
  letter-spacing: 4px;
  text-transform: uppercase;
}

.subtitle {
  color: var(--cyber-pink);
  font-size: 1.2rem;
  margin-top: 1rem;
  letter-spacing: 2px;
}

/* Terminal style intro */
.terminal {
  background: var(--darker-bg);
  border: 1px solid var(--cyber-teal);
  padding: 2rem;
  margin: 2rem 0;
  box-shadow: 
    0 0 20px rgba(0, 255, 255, 0.2),
    inset 0 0 20px rgba(0, 255, 255, 0.1);
  position: relative;
}

.terminal::before {
  content: 'user@tryhackme:~$';
  position: absolute;
  top: -12px;
  left: 20px;
  background: var(--darker-bg);
  padding: 0 10px;
  color: var(--cyber-pink);
  font-weight: bold;
}

.terminal p {
  margin: 0.5rem 0;
  color: #00ff00;
}

.terminal p::before {
  content: '> ';
  color: var(--cyber-teal);
}

/* Modules grid */
.modules-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
  margin: 3rem 0;
}

.module-card {
  background: linear-gradient(
    145deg,
    rgba(0, 255, 255, 0.05),
    rgba(157, 0, 255, 0.05)
  );
  border: 1px solid rgba(0, 255, 255, 0.3);
  padding: 2rem;
  transition: all 0.3s ease;
  position: relative;
  overflow: hidden;
}

.module-card:hover {
  transform: translateY(-5px);
  border-color: var(--cyber-pink);
  box-shadow: 
    0 10px 30px rgba(255, 0, 255, 0.3),
    0 0 50px rgba(157, 0, 255, 0.2);
}

.module-card::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 3px;
  background: linear-gradient(90deg, 
    var(--cyber-teal), 
    var(--cyber-purple), 
    var(--cyber-pink));
}

.module-title {
  color: var(--cyber-teal);
  font-size: 1.5rem;
  margin-top: 0;
  margin-bottom: 1rem;
  text-transform: uppercase;
  letter-spacing: 1px;
}

/* Room list */
.room-list {
  list-style: none;
  padding: 0;
  margin: 0;
}

.room-item {
  padding: 0.8rem 1rem;
  margin: 0.5rem 0;
  background: rgba(255, 255, 255, 0.03);
  border-left: 3px solid var(--cyber-purple);
  transition: all 0.3s ease;
  font-size: 0.95rem;
}

.room-item:hover {
  background: rgba(0, 255, 255, 0.1);
  border-left-color: var(--cyber-pink);
  padding-left: 1.5rem;
}

/* Status indicators */
.status {
  display: inline-block;
  width: 10px;
  height: 10px;
  border-radius: 50%;
  margin-right: 10px;
}

.status-completed {
  background: #00ff00;
  box-shadow: 0 0 10px #00ff00;
}

.status-inprogress {
  background: var(--cyber-teal);
  box-shadow: 0 0 10px var(--cyber-teal);
  animation: pulse 2s infinite;
}

.status-pending {
  background: var(--cyber-pink);
  box-shadow: 0 0 10px var(--cyber-pink);
  opacity: 0.5;
}

@keyframes pulse {
  0%, 100% { opacity: 1; }
  50% { opacity: 0.5; }
}

/* Profile section */
.profile-section {
  text-align: center;
  padding: 3rem;
  margin: 3rem 0;
  background: linear-gradient(
    135deg,
    rgba(0, 255, 255, 0.05),
    rgba(157, 0, 255, 0.05)
  );
  border: 1px solid rgba(255, 0, 255, 0.3);
}

.profile-link {
  color: var(--cyber-teal);
  text-decoration: none;
  font-size: 1.2rem;
  border: 1px solid var(--cyber-teal);
  padding: 0.8rem 2rem;
  display: inline-block;
  margin-top: 1rem;
  transition: all 0.3s ease;
}

.profile-link:hover {
  background: var(--cyber-teal);
  color: var(--dark-bg);
  box-shadow: 0 0 20px var(--cyber-teal);
}

/* Footer */
.footer {
  text-align: center;
  padding: 2rem;
  margin-top: 3rem;
  border-top: 1px solid rgba(0, 255, 255, 0.3);
  color: rgba(255, 255, 255, 0.5);
  font-size: 0.9rem;
}

/* Responsive */
@media (max-width: 768px) {
  .title {
    font-size: 2.5rem;
  }
  
  .container {
    padding: 1rem;
  }
  
  .modules-grid {
    grid-template-columns: 1fr;
  }
}
</style>

<div class="matrix-bg" id="matrixCanvas"></div>

<div class="container">

  <div class="header">
    <h1 class="title">TRYHACKME</h1>
    <div class="subtitle">CYBERSECURITY LEARNING JOURNEY</div>
  </div>

  <div class="terminal">
    <p>User: 3165378</p>
    <p>Status: Active Learner</p>
    <p>Path: Beginner → Pentester</p>
    <p>Current Focus: Web Application Security</p>
    <p>Motto: "Learn. Hack. Document."</p>
  </div>

  <div class="modules-grid">
    
    <div class="module-card">
      <h3 class="module-title">Cyber Security Basics</h3>
      <ul class="room-list">
        <li class="room-item">
          <span class="status status-completed"></span>
          Introduction to Cyber Security
        </li>
        <li class="room-item">
          <span class="status status-completed"></span>
          What is Offensive Security
        </li>
        <li class="room-item">
          <span class="status status-inprogress"></span>
          Defensive Security Principles
        </li>
      </ul>
    </div>

    <div class="module-card">
      <h3 class="module-title">Penetration Testing</h3>
      <ul class="room-list">
        <li class="room-item">
          <span class="status status-completed"></span>
          Pentesting Fundamentals
        </li>
        <li class="room-item">
          <span class="status status-inprogress"></span>
          Testing Methodologies
        </li>
        <li class="room-item">
          <span class="status status-pending"></span>
          Ethics & Legal Aspects
        </li>
      </ul>
    </div>

    <div class="module-card">
      <h3 class="module-title">Web Hacking</h3>
      <ul class="room-list">
        <li class="room-item">
          <span class="status status-inprogress"></span>
          Introduction to Web Hacking
        </li>
        <li class="room-item">
          <span class="status status-pending"></span>
          Burp Suite Mastery
        </li>
        <li class="room-item">
          <span class="status status-pending"></span>
          OWASP Top 10
        </li>
      </ul>
    </div>

    <div class="module-card">
      <h3 class="module-title">Network Security</h3>
      <ul class="room-list">
        <li class="room-item">
          <span class="status status-pending"></span>
          Network Reconnaissance
        </li>
        <li class="room-item">
          <span class="status status-pending"></span>
          Nmap & Network Scanning
        </li>
        <li class="room-item">
          <span class="status status-pending"></span>
          Protocol Analysis
        </li>
      </ul>
    </div>

    <div class="module-card">
      <h3 class="module-title">Advanced Tools</h3>
      <ul class="room-list">
        <li class="room-item">
          <span class="status status-pending"></span>
          Metasploit Framework
        </li>
        <li class="room-item">
          <span class="status status-pending"></span>
          Vulnerability Research
        </li>
        <li class="room-item">
          <span class="status status-pending"></span>
          Privilege Escalation
        </li>
      </ul>
    </div>

    <div class="module-card">
      <h3 class="module-title">Certification Path</h3>
      <ul class="room-list">
        <li class="room-item">
          <span class="status status-pending"></span>
          Jr. Penetration Tester (PT1)
        </li>
        <li class="room-item">
          <span class="status status-pending"></span>
          Practical Challenges
        </li>
        <li class="room-item">
          <span class="status status-pending"></span>
          Real-world Scenarios
        </li>
      </ul>
    </div>

  </div>

  <div class="profile-section">
    <h3 style="color: var(--cyber-pink); margin-bottom: 1rem;">
      MY TRYHACKME PROFILE
    </h3>
    <p>ID: 3165378</p>
    <a href="https://tryhackme.com/p/3165378" target="_blank" class="profile-link">
      VISIT PROFILE →
    </a>
  </div>

  <div class="footer">
    <p>© CYBERIA | Cybersecurity Knowledge Base</p>
    <p>Last Updated: Today | Always Learning</p>
  </div>

</div>

<script>
// Simple Matrix effect
const canvas = document.createElement('canvas');
const ctx = canvas.getContext('2d');
const matrixBg = document.getElementById('matrixCanvas');

matrixBg.appendChild(canvas);

canvas.width = matrixBg.clientWidth;
canvas.height = matrixBg.clientHeight;

const matrix = "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ123456789@#$%^&*()*&^%+-/~{[|`]}";
const matrixArray = matrix.split("");

const font_size = 12;
const columns = canvas.width / font_size;
const drops = [];

for(let x = 0; x < columns; x++)
    drops[x] = 1; 

function draw() {
    ctx.fillStyle = "rgba(0, 0, 0, 0.04)";
    ctx.fillRect(0, 0, canvas.width, canvas.height);
    
    ctx.fillStyle = "#0F0";
    ctx.font = font_size + "px monospace";
    
    for(let i = 0; i < drops.length; i++) {
        const text = matrixArray[Math.floor(Math.random() * matrixArray.length)];
        ctx.fillText(text, i * font_size, drops[i] * font_size);
        
        if(drops[i] * font_size > canvas.height && Math.random() > 0.975)
            drops[i] = 0;
        
        drops[i]++;
    }
}

setInterval(draw, 35);

// Resize canvas on window resize
window.addEventListener('resize', function() {
    canvas.width = matrixBg.clientWidth;
    canvas.height = matrixBg.clientHeight;
});
</script>
