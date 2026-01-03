---
layout: default
title: TryHackMe
nav: tryhackme
---

<style>
:root {
  --main-bg: #0a0a0a;
  --card-bg: #121212;
  --accent-red: #ff2e2e;
  --accent-blue: #2e8bff;
  --accent-purple: #8a2be2;
  --text-primary: #ffffff;
  --text-secondary: #b0b0b0;
}

body {
  background: 
    radial-gradient(circle at 20% 30%, rgba(255, 46, 46, 0.1) 0%, transparent 50%),
    radial-gradient(circle at 80% 70%, rgba(46, 139, 255, 0.1) 0%, transparent 50%),
    radial-gradient(circle at 40% 90%, rgba(138, 43, 226, 0.1) 0%, transparent 50%),
    var(--main-bg);
  font-family: 'Courier New', monospace;
}

.thm-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 2rem;
  position: relative;
  overflow: hidden;
}

/* Glitch effect */
@keyframes glitch {
  0% { transform: translate(0); }
  20% { transform: translate(-2px, 2px); }
  40% { transform: translate(-2px, -2px); }
  60% { transform: translate(2px, 2px); }
  80% { transform: translate(2px, -2px); }
  100% { transform: translate(0); }
}

@keyframes scanline {
  0% { transform: translateY(-100%); }
  100% { transform: translateY(100vh); }
}

@keyframes pulse {
  0%, 100% { opacity: 1; }
  50% { opacity: 0.7; }
}

.header {
  text-align: center;
  margin-bottom: 3rem;
  position: relative;
  padding: 2rem;
  border: 3px solid var(--accent-red);
  background: rgba(18, 18, 18, 0.9);
  box-shadow: 
    0 0 30px rgba(255, 46, 46, 0.3),
    inset 0 0 30px rgba(255, 46, 46, 0.1);
}

.header::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 3px;
  background: linear-gradient(90deg, 
    var(--accent-red), 
    var(--accent-blue), 
    var(--accent-purple),
    var(--accent-red));
  animation: pulse 2s infinite;
}

.header h1 {
  font-size: 3.5rem;
  color: var(--text-primary);
  text-transform: uppercase;
  letter-spacing: 4px;
  margin: 0;
  text-shadow: 
    0 0 10px var(--accent-red),
    0 0 20px rgba(255, 46, 46, 0.5);
  animation: glitch 3s infinite;
}

.header p {
  color: var(--text-secondary);
  font-size: 1.2rem;
  margin-top: 1rem;
  font-style: italic;
}

/* Grid System */
.paths-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
  gap: 2rem;
  margin: 3rem 0;
}

.path-card {
  background: var(--card-bg);
  border: 2px solid var(--accent-red);
  padding: 2rem;
  position: relative;
  transition: all 0.3s ease;
  overflow: hidden;
}

.path-card:hover {
  transform: translateY(-5px);
  box-shadow: 
    0 10px 30px rgba(255, 46, 46, 0.3),
    0 0 50px rgba(46, 139, 255, 0.2);
  border-color: var(--accent-blue);
}

.path-card::before {
  content: '>>';
  position: absolute;
  top: 1rem;
  left: 1rem;
  color: var(--accent-red);
  font-weight: bold;
}

.path-title {
  color: var(--accent-blue);
  font-size: 1.8rem;
  margin: 0 0 1.5rem 2rem;
  text-transform: uppercase;
  letter-spacing: 2px;
}

/* Room List */
.room-list {
  list-style: none;
  padding: 0;
  margin: 0;
}

.room-item {
  color: var(--text-primary);
  padding: 0.8rem 1rem 0.8rem 2.5rem;
  margin: 0.5rem 0;
  background: rgba(255, 255, 255, 0.05);
  border-left: 3px solid var(--accent-purple);
  position: relative;
  transition: all 0.3s ease;
  font-size: 0.95rem;
}

.room-item:hover {
  background: rgba(46, 139, 255, 0.1);
  border-left-color: var(--accent-blue);
  padding-left: 3rem;
}

.room-item::before {
  content: '•';
  position: absolute;
  left: 1rem;
  color: var(--accent-red);
  font-size: 1.5rem;
}

.room-item.completed {
  color: var(--text-secondary);
  text-decoration: line-through;
  opacity: 0.7;
}

.room-item.completed::before {
  content: '✓';
  color: #00ff00;
}

/* Terminal Effect */
.terminal {
  background: rgba(0, 0, 0, 0.9);
  border: 2px solid var(--accent-red);
  padding: 2rem;
  margin: 2rem 0;
  font-family: 'Courier New', monospace;
  color: #00ff00;
  position: relative;
  overflow: hidden;
}

.terminal::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 2px;
  background: linear-gradient(90deg, 
    transparent, 
    var(--accent-red), 
    transparent);
  animation: pulse 1.5s infinite;
}

.terminal-line {
  margin: 0.5rem 0;
  line-height: 1.6;
}

.terminal-line::before {
  content: '$ ';
  color: var(--accent-blue);
  font-weight: bold;
}

/* Stats Panel */
.stats-panel {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 1.5rem;
  margin: 3rem 0;
}

.stat-box {
  background: linear-gradient(135deg, 
    rgba(255, 46, 46, 0.1), 
    rgba(46, 139, 255, 0.1));
  border: 1px solid rgba(255, 46, 46, 0.3);
  padding: 1.5rem;
  text-align: center;
  position: relative;
  overflow: hidden;
}

.stat-box::before {
  content: '';
  position: absolute;
  top: -50%;
  left: -50%;
  width: 200%;
  height: 200%;
  background: linear-gradient(45deg, 
    transparent, 
    rgba(255, 255, 255, 0.1), 
    transparent);
  transform: rotate(45deg);
  animation: shimmer 3s infinite;
}

@keyframes shimmer {
  0% { transform: translateX(-100%) rotate(45deg); }
  100% { transform: translateX(100%) rotate(45deg); }
}

.stat-number {
  font-size: 2.5rem;
  color: var(--accent-red);
  font-weight: bold;
  margin-bottom: 0.5rem;
  text-shadow: 0 0 10px currentColor;
}

.stat-label {
  color: var(--text-secondary);
  font-size: 0.9rem;
  text-transform: uppercase;
  letter-spacing: 1px;
}

/* Scanline overlay */
.scanline {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  pointer-events: none;
  z-index: 9999;
  opacity: 0.03;
}

.scanline::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 4px;
  background: linear-gradient(
    to bottom,
    transparent,
    rgba(0, 255, 0, 0.5),
    transparent
  );
  animation: scanline 10s linear infinite;
}

/* Responsive */
@media (max-width: 768px) {
  .header h1 {
    font-size: 2.5rem;
  }
  
  .paths-grid {
    grid-template-columns: 1fr;
  }
  
  .thm-container {
    padding: 1rem;
  }
}
</style>

<div class="scanline"></div>

<div class="thm-container">

  <div class="header">
    <h1>TRYHACKME PROGRESS</h1>
    <p>CYBERSECURITY LEARNING PATH</p>
  </div>

  <div class="stats-panel">
    <div class="stat-box">
      <div class="stat-number">12+</div>
      <div class="stat-label">Rooms Completed</div>
    </div>
    <div class="stat-box">
      <div class="stat-number">5</div>
      <div class="stat-label">Badges Earned</div>
    </div>
    <div class="stat-box">
      <div class="stat-number">3165378</div>
      <div class="stat-label">User ID</div>
    </div>
    <div class="stat-box">
      <div class="stat-number">24/7</div>
      <div class="stat-label">Active Learning</div>
    </div>
  </div>

  <div class="paths-grid">

  <div class="path-card">
      <h2 class="path-title">Introduction to Cyber Security</h2>
      <ul class="room-list">
        <li class="room-item completed">What is Cyber Security?</li>
        <li class="room-item completed">Offensive vs Defensive</li>
        <li class="room-item completed">Careers in Cyber</li>
      </ul>
    </div>

  <div class="path-card">
      <h2 class="path-title">Introduction to Pentesting</h2>
      <ul class="room-list">
        <li class="room-item completed">Pentesting Fundamentals</li>
        <li class="room-item">Principles of Security</li>
        <li class="room-item">Methodologies</li>
      </ul>
    </div>

   <div class="path-card">
      <h2 class="path-title">Introduction to Web Hacking</h2>
      <ul class="room-list">
        <li class="room-item">Burp Suite</li>
        <li class="room-item">OWASP Top 10</li>
        <li class="room-item">SQL Injection</li>
        <li class="room-item">XSS Attacks</li>
      </ul>
    </div>

  <div class="path-card">
      <h2 class="path-title">Network Security</h2>
      <ul class="room-list">
        <li class="room-item">Nmap Basics</li>
        <li class="room-item">Passive Recon</li>
        <li class="room-item">Active Recon</li>
        <li class="room-item">Protocol Analysis</li>
      </ul>
    </div>

   <div class="path-card">
      <h2 class="path-title">Advanced Topics</h2>
      <ul class="room-list">
        <li class="room-item">Vulnerability Research</li>
        <li class="room-item">Metasploit Framework</li>
        <li class="room-item">Privilege Escalation</li>
        <li class="room-item">Post-Exploitation</li>
      </ul>
    </div>

  <div class="path-card">
      <h2 class="path-title">Certification Path</h2>
      <ul class="room-list">
        <li class="room-item">Jr. Penetration Tester (PT1)</li>
        <li class="room-item">Practical Challenges</li>
        <li class="room-item">Exam Preparation</li>
      </ul>
    </div>

  </div>

  <div class="terminal">
    <div class="terminal-line">[root@tryhackme]$ ./status_check.sh</div>
    <div class="terminal-line">>> Loading user profile: 3165378</div>
    <div class="terminal-line">>> Current path: Beginner → Intermediate</div>
    <div class="terminal-line">>> Active learning: TRUE</div>
    <div class="terminal-line">>> Next target: Complete Web Hacking module</div>
    <div class="terminal-line">>> Estimated completion: 2-3 weeks</div>
    <div class="terminal-line">>> [SYSTEM] Keep hacking!</div>
  </div>

</div>
