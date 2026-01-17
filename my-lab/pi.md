---
layout: default
title: Raspberry Pi Lab
---
<link rel="icon" href="https://raw.githubusercontent.com/ItsHaname/ItsHaname.github.io/main/logo" type="image/png">
<style>
@keyframes matrixRain {
  0% { transform: translateY(-100vh); }
  100% { transform: translateY(100vh); }
}

@keyframes floatUpDown {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(-20px); }
}

@keyframes gradientBG {
  0% { background-position: 0% 50%; }
  50% { background-position: 100% 50%; }
  100% { background-position: 0% 50%; }
}

@keyframes slideIn {
  from { opacity: 0; transform: translateY(-20px); }
  to { opacity: 1; transform: translateY(0); }
}

@keyframes pulse {
  0% { transform: scale(1); }
  50% { transform: scale(1.05); }
  100% { transform: scale(1); }
}

@keyframes blink {
  0%, 100% { opacity: 1; }
  50% { opacity: 0; }
}

@keyframes rotate {
  0% { transform: rotate(0deg); }
  100% { transform: rotate(360deg); }
}

body {
  background: #0a0e1a;
  min-height: 100vh;
  margin: 0;
  position: relative;
  overflow-x: hidden;
}

.binary-background {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  pointer-events: none;
  z-index: -1;
}

.binary-digit {
  position: absolute;
  font-family: 'Courier New', monospace;
  font-size: 16px;
  color: rgba(59, 130, 246, 0.15);
  opacity: 0;
  animation: matrixRain linear infinite;
}

.binary-digit.float {
  animation: floatUpDown 3s ease-in-out infinite;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 40px 20px;
  position: relative;
  z-index: 1;
}

.page-header {
  text-align: center;
  margin-bottom: 60px;
  padding: 50px 20px;
  background: rgba(0, 20, 40, 0.6);
  border-radius: 30px;
  border: 3px solid #1e4d7b;
  box-shadow: 0 0 40px rgba(30, 77, 123, 0.5), inset 0 0 30px rgba(30, 77, 123, 0.2);
  position: relative;
  overflow: hidden;
}

.raspberry-logo {
  width: 200px;
  height: 200px;
  margin: 0 auto 30px;
  animation: floatUpDown 4s ease-in-out infinite;
  filter: drop-shadow(0 0 25px rgba(194, 51, 82, 0.6));
}

.raspberry-logo img {
  width: 100%;
  height: 100%;
  object-fit: contain;
}

.page-title {
  font-size: 4em;
  color: #ff6b4a;
  text-shadow: 
    0 0 10px #ff6b4a,
    0 0 20px #ff6b4a,
    0 0 30px #ff6b4a,
    0 0 40px #ff3300;
  margin: 0 0 20px 0;
  font-weight: 900;
  letter-spacing: 8px;
  text-transform: uppercase;
  font-style: italic;
  -webkit-text-stroke: 2px #ff3300;
}

.page-subtitle {
  font-size: 1.5em;
  color: #60a5fa;
  margin: 10px 0 0 0;
  text-shadow: 0 0 10px #60a5fa, 0 0 20px #3b82f6;
  letter-spacing: 3px;
  font-style: italic;
}

.page-subtitle::after {
  content: '_';
  animation: blink 1s infinite;
  color: #60a5fa;
}

.hero-section {
  background: linear-gradient(135deg, rgba(15, 23, 42, 0.9), rgba(0, 20, 40, 0.8));
  border: 2px solid rgba(59, 130, 246, 0.3);
  border-radius: 20px;
  padding: 40px;
  margin-bottom: 50px;
  text-align: center;
}

.hero-section h2 {
  color: transparent;
  background: linear-gradient(90deg, #3b82f6, #60a5fa, #2563eb);
  background-size: 200% auto;
  -webkit-background-clip: text;
  background-clip: text;
  animation: gradientBG 3s ease infinite;
  font-size: 2.5em;
  margin: 0 0 20px 0;
  font-weight: 900;
}

.hero-section p {
  color: #cbd5e1;
  font-size: 1.2em;
  line-height: 1.8;
  margin: 0;
}

.hero-section strong {
  color: #60a5fa;
}

.specs-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 20px;
  margin: 50px 0;
}

.spec-card {
  background: rgba(15, 23, 42, 0.85);
  border: 1px solid rgba(59, 130, 246, 0.3);
  border-radius: 15px;
  padding: 25px;
  text-align: center;
  transition: all 0.3s;
}

.spec-card:hover {
  transform: translateY(-5px);
  border-color: #60a5fa;
  box-shadow: 0 10px 25px rgba(59, 130, 246, 0.3);
}

.spec-icon {
  font-size: 3em;
  margin-bottom: 15px;
  color: #ff6b4a;
  font-weight: 900;
}

.spec-card h3 {
  color: #3b82f6;
  font-size: 1.3em;
  margin: 0 0 10px 0;
  font-weight: 600;
}

.spec-card p {
  color: #cbd5e1;
  margin: 0;
  line-height: 1.6;
}

.section-title {
  font-size: 2.5em;
  color: transparent;
  background: linear-gradient(90deg, #3b82f6, #60a5fa, #2563eb);
  background-size: 200% auto;
  -webkit-background-clip: text;
  background-clip: text;
  animation: gradientBG 3s ease infinite;
  margin: 60px 0 30px 0;
  font-weight: 900;
  text-align: center;
}

.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
  gap: 25px;
  margin: 40px 0;
}

.project-card {
  background: rgba(15, 23, 42, 0.85);
  border: 1px solid rgba(59, 130, 246, 0.3);
  border-radius: 15px;
  padding: 30px;
  transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
  position: relative;
  overflow: hidden;
  text-decoration: none;
  color: inherit;
  display: block;
}

.project-card:before {
  content: '';
  position: absolute;
  top: -2px;
  left: -2px;
  right: -2px;
  bottom: -2px;
  background: linear-gradient(45deg, #3b82f6, #60a5fa, transparent);
  z-index: -1;
  opacity: 0;
  transition: opacity 0.4s;
}

.project-card:hover:before {
  opacity: 0.5;
}

.project-card:hover {
  transform: translateY(-10px) scale(1.02);
  border-color: #60a5fa;
  box-shadow: 0 15px 35px rgba(59, 130, 246, 0.3);
}

.project-number {
  display: inline-block;
  width: 50px;
  height: 50px;
  background: linear-gradient(135deg, #c23352, #a02b43);
  color: white;
  font-size: 1.5em;
  font-weight: 900;
  border-radius: 50%;
  text-align: center;
  line-height: 50px;
  margin-bottom: 20px;
  box-shadow: 0 5px 15px rgba(194, 51, 82, 0.4);
}

.project-card h3 {
  color: #3b82f6;
  font-size: 1.6em;
  margin: 0 0 15px 0;
  font-weight: 600;
}

.project-card p {
  color: #cbd5e1;
  line-height: 1.6;
  margin: 0 0 15px 0;
}

.status-badge {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  background: rgba(59, 130, 246, 0.15);
  padding: 8px 16px;
  border-radius: 20px;
  font-size: 0.9em;
  color: #60a5fa;
  border: 1px solid rgba(59, 130, 246, 0.3);
  margin-top: 15px;
}

.status-dot {
  width: 8px;
  height: 8px;
  background: #3b82f6;
  border-radius: 50%;
  animation: pulse 2s infinite;
}

.info-box {
  background: rgba(194, 51, 82, 0.1);
  border: 2px solid rgba(194, 51, 82, 0.3);
  border-radius: 15px;
  padding: 30px;
  margin: 40px 0;
}

.info-box h3 {
  color: #ff6b4a;
  font-size: 1.8em;
  margin: 0 0 20px 0;
}

.info-box ul {
  list-style: none;
  margin: 0;
  padding: 0;
}

.info-box li {
  color: #cbd5e1;
  padding: 10px 0 10px 30px;
  position: relative;
  line-height: 1.6;
}

.info-box li:before {
  content: "▸";
  position: absolute;
  left: 0;
  color: #ff6b4a;
  font-size: 1.2em;
  font-weight: 900;
}

.footer-nav {
  display: flex;
  justify-content: center;
  gap: 20px;
  margin-top: 60px;
  flex-wrap: wrap;
}

.nav-button {
  display: inline-block;
  padding: 15px 30px;
  background: rgba(59, 130, 246, 0.2);
  border: 1px solid #3b82f6;
  border-radius: 10px;
  color: #60a5fa;
  text-decoration: none;
  font-weight: 600;
  transition: all 0.3s;
}

.nav-button:hover {
  background: #3b82f6;
  color: white;
  transform: translateY(-3px);
  box-shadow: 0 10px 20px rgba(59, 130, 246, 0.4);
}

@media (max-width: 768px) {
  .page-title {
    font-size: 2.5em;
    letter-spacing: 4px;
  }
  
  .page-subtitle {
    font-size: 1.2em;
    letter-spacing: 2px;
  }
  
  .raspberry-logo {
    width: 140px;
    height: 140px;
  }
  
  .projects-grid {
    grid-template-columns: 1fr;
  }
  
  .specs-grid {
    grid-template-columns: 1fr;
  }
}
</style>

<div class="binary-background"></div>

<div class="container">
  <div class="page-header">
    <div class="raspberry-logo">
      <img src="/assets/images/pi.png" alt="Raspberry Pi Logo">
    </div>
    <h1 class="page-title">RASPBERRY PI</h1>
    <p class="page-subtitle">Professional Cybersecurity Lab</p>
  </div>

  <div class="hero-section">
    <h2>What is Raspberry Pi?</h2>
    <p>
      The <strong>Raspberry Pi</strong> is a small, affordable single-board computer that's perfect for learning, 
      experimenting, and building cybersecurity projects. It's my go-to device for <strong>penetration testing</strong>, 
      <strong>network monitoring</strong>, and running various <strong>security tools</strong> in a portable format.
    </p>
  </div>

  <div class="specs-grid">
    <div class="spec-card">
      <div class="spec-icon">CPU</div>
      <h3>Processor</h3>
      <p>ARM Cortex CPU<br>Quad-core performance</p>
    </div>
    
  <div class="spec-card">
      <div class="spec-icon">RAM</div>
      <h3>Memory</h3>
      <p>Up to 8GB RAM<br>Perfect for multi-tasking</p>
    </div>
    
  <div class="spec-card">
      <div class="spec-icon">NET</div>
      <h3>Connectivity</h3>
      <p>WiFi, Bluetooth, Ethernet<br>Network security ready</p>
    </div>
    
  <div class="spec-card">
      <div class="spec-icon">PWR</div>
      <h3>Portable</h3>
      <p>Low power consumption<br>Take it anywhere</p>
    </div>
  </div>

  <h2 class="section-title">My Raspberry Pi Projects</h2>

  <div class="projects-grid">
    <a href="#" class="project-card">
      <div class="project-number">1</div>
      <h3>Network Scanner</h3>
      <p>Building a network discovery and scanning tool using Nmap and custom Python scripts for vulnerability assessment.</p>
      <div class="status-badge">
        <span class="status-dot"></span>
        In Progress
      </div>
    </a>

  <a href="#" class="project-card">
      <div class="project-number">2</div>
      <h3>Portable Pentesting Station</h3>
      <p>Setting up Kali Linux with essential pentesting tools for on-the-go security testing and assessments.</p>
      <div class="status-badge">
        <span class="status-dot"></span>
        In Progress
      </div>
    </a>

   <a href="#" class="project-card">
      <div class="project-number">3</div>
      <h3>Pi-hole DNS Blocker</h3>
      <p>Network-wide ad blocking and DNS filtering to protect against malicious domains and improve privacy.</p>
      <div class="status-badge">
        <span class="status-dot"></span>
        Planning
      </div>
    </a>

   <a href="#" class="project-card">
      <div class="project-number">4</div>
      <h3>Honeypot System</h3>
      <p>Creating a honeypot to attract and analyze malicious attacks, learning about attack patterns and techniques.</p>
      <div class="status-badge">
        <span class="status-dot"></span>
        Planning
      </div>
    </a>

   <a href="#" class="project-card">
      <div class="project-number">5</div>
      <h3>WiFi Auditing Platform</h3>
      <p>Building a wireless auditing platform for testing WiFi security and performing authorized security assessments.</p>
      <div class="status-badge">
        <span class="status-dot"></span>
        Coming Soon
      </div>
    </a>

  <a href="#" class="project-card">
      <div class="project-number">6</div>
      <h3>Security Monitoring Dashboard</h3>
      <p>Real-time network monitoring with Grafana and Prometheus to visualize security metrics and alerts.</p>
      <div class="status-badge">
        <span class="status-dot"></span>
        Coming Soon
      </div>
    </a>
  </div>

  <div class="info-box">
    <h3>Why Use Raspberry Pi for Cybersecurity?</h3>
    <ul>
      <li><strong>Affordable</strong> - Low-cost platform for learning and experimenting</li>
      <li><strong>Portable</strong> - Easy to carry and deploy anywhere</li>
      <li><strong>Versatile</strong> - Can run multiple Linux distributions and security tools</li>
      <li><strong>Low Power</strong> - Perfect for 24/7 monitoring and long-term projects</li>
      <li><strong>Community</strong> - Huge support community and tons of tutorials</li>
      <li><strong>Learning</strong> - Hands-on experience with Linux, networking, and security</li>
    </ul>
  </div>

  <div class="footer-nav">
    <a href="/my-lab" class="nav-button">← Back to Lab</a>
    <a href="https://www.raspberrypi.org/" target="_blank" class="nav-button">Official Raspberry Pi Website</a>
  </div>
</div>

<script>
document.addEventListener('DOMContentLoaded', function() {
  const binaryContainer = document.querySelector('.binary-background');
  
  // Falling binary digits
  for (let i = 0; i < 100; i++) {
    const digit = document.createElement('div');
    digit.className = 'binary-digit';
    digit.textContent = Math.random() > 0.5 ? '1' : '0';
    digit.style.left = Math.random() * 100 + 'vw';
    digit.style.fontSize = (Math.random() * 18 + 12) + 'px';
    digit.style.animationDuration = (Math.random() * 10 + 5) + 's';
    digit.style.animationDelay = Math.random() * 5 + 's';
    digit.style.opacity = Math.random() * 0.2 + 0.05;
    const colors = ['rgba(59, 130, 246, 0.15)', 'rgba(96, 165, 250, 0.15)', 'rgba(37, 99, 235, 0.15)'];
    digit.style.color = colors[Math.floor(Math.random() * colors.length)];
    binaryContainer.appendChild(digit);
  }
  
  // Floating binary digits
  for (let i = 0; i < 30; i++) {
    const floatDigit = document.createElement('div');
    floatDigit.className = 'binary-digit float';
    floatDigit.textContent = Math.random() > 0.5 ? '1' : '0';
    floatDigit.style.left = Math.random() * 100 + 'vw';
    floatDigit.style.top = Math.random() * 100 + 'vh';
    floatDigit.style.fontSize = (Math.random() * 22 + 14) + 'px';
    floatDigit.style.animationDelay = Math.random() * 2 + 's';
    floatDigit.style.opacity = Math.random() * 0.3 + 0.1;
    const floatColors = ['rgba(59, 130, 246, 0.25)', 'rgba(96, 165, 250, 0.25)'];
    floatDigit.style.color = floatColors[Math.floor(Math.random() * floatColors.length)];
    binaryContainer.appendChild(floatDigit);
  }
});
</script>
