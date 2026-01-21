---
layout: default
title: TryHackMe
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

@keyframes pulse {
  0% { transform: scale(1); }
  50% { transform: scale(1.05); }
  100% { transform: scale(1); }
}

@keyframes blink {
  0%, 100% { opacity: 1; }
  50% { opacity: 0; }
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
  background: #0a0e1a;
  color: #e2e8f0;
  line-height: 1.6;
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
  color: rgba(220, 38, 38, 0.15);
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
  padding: 40px 20px;
  background: rgba(0, 20, 40, 0.6);
  border-radius: 30px;
  border: 3px solid #7a1f1f;
  box-shadow: 0 0 40px rgba(220, 38, 38, 0.5), inset 0 0 30px rgba(220, 38, 38, 0.2);
}

.platform-badge {
  display: inline-block;
  padding: 10px 25px;
  background: rgba(220, 38, 38, 0.2);
  color: #ef4444;
  font-size: 1em;
  font-weight: 700;
  border-radius: 20px;
  margin-bottom: 20px;
  border: 1px solid rgba(220, 38, 38, 0.3);
  letter-spacing: 2px;
}

.page-title {
  font-size: 4em;
  color: #dc2626;
  text-shadow: 
    0 0 10px #dc2626,
    0 0 20px #dc2626,
    0 0 30px #dc2626,
    0 0 40px #991b1b;
  margin: 0 0 20px 0;
  font-weight: 900;
  letter-spacing: 8px;
  text-transform: uppercase;
  font-style: italic;
  -webkit-text-stroke: 2px #991b1b;
}

.page-subtitle {
  font-size: 1.5em;
  color: #ef4444;
  margin: 10px 0 0 0;
  text-shadow: 0 0 10px #ef4444, 0 0 20px #dc2626;
  letter-spacing: 3px;
  font-style: italic;
}

.page-subtitle::after {
  content: '_';
  animation: blink 1s infinite;
  color: #ef4444;
}

.profile-section {
  text-align: center;
  margin: 40px 0;
  padding: 30px;
  background: rgba(15, 23, 42, 0.85);
  border: 1px solid rgba(220, 38, 38, 0.3);
  border-radius: 15px;
}

.profile-section iframe {
  border: none;
  max-width: 100%;
}

.terminal {
  background: rgba(15, 23, 42, 0.85);
  border: 1px solid rgba(220, 38, 38, 0.3);
  border-radius: 12px;
  padding: 25px;
  margin: 40px 0;
  font-family: 'Courier New', monospace;
}

.terminal-header {
  display: flex;
  gap: 8px;
  margin-bottom: 15px;
}

.terminal-dot {
  width: 10px;
  height: 10px;
  border-radius: 50%;
}

.terminal-dot.red { background: #ff5f56; }
.terminal-dot.yellow { background: #ffbd2e; }
.terminal-dot.green { background: #27c93f; }

.terminal-text {
  color: #ef4444;
  line-height: 1.8;
  font-size: 0.95em;
}

.prompt {
  color: #dc2626;
  font-weight: bold;
}

.section-title {
  font-size: 2.5em;
  color: transparent;
  background: linear-gradient(90deg, #dc2626, #ef4444, #991b1b);
  background-size: 200% auto;
  -webkit-background-clip: text;
  background-clip: text;
  animation: gradientBG 3s ease infinite;
  margin: 60px 0 30px 0;
  font-weight: 900;
  text-align: center;
}

.rooms-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
  gap: 25px;
  margin: 40px 0;
}

.room-card {
  background: rgba(15, 23, 42, 0.85);
  border: 1px solid rgba(220, 38, 38, 0.3);
  border-radius: 15px;
  padding: 30px;
  transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
  position: relative;
  overflow: hidden;
  text-decoration: none;
  color: inherit;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}

.room-card:before {
  content: '';
  position: absolute;
  top: -2px;
  left: -2px;
  right: -2px;
  bottom: -2px;
  background: linear-gradient(45deg, #dc2626, #ef4444, transparent);
  z-index: -1;
  opacity: 0;
  transition: opacity 0.4s;
}

.room-card:hover:before {
  opacity: 0.5;
}

.room-card:hover {
  transform: translateY(-10px) scale(1.02);
  border-color: #ef4444;
  box-shadow: 0 15px 35px rgba(220, 38, 38, 0.3);
}

.room-image {
  width: 110px; 
  height: 70px;
  object-fit: contain;
  border-radius: 8px;
  margin-bottom: 18px;
}

.room-card h3 {
  color: #fff;
  font-size: 1.5em;
  margin: 0 0 12px 0;
  font-weight: 700;
  text-align: left;
}

.room-description {
  color: #cbd5e1;
  font-size: 0.95em;
  line-height: 1.6;
  margin-bottom: 20px;
  text-align: left;
}

.status-badge {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  background: rgba(220, 38, 38, 0.15);
  padding: 8px 16px;
  border-radius: 20px;
  font-size: 0.9em;
  color: #ef4444;
  border: 1px solid rgba(220, 38, 38, 0.3);
  margin-top: auto;
}

.status-badge.done {
  background: rgba(16, 185, 129, 0.15);
  border-color: rgba(16, 185, 129, 0.3);
  color: #10b981;
}

.status-dot {
  width: 8px;
  height: 8px;
  background: #dc2626;
  border-radius: 50%;
  animation: pulse 2s infinite;
}

.status-dot.done {
  background: #10b981;
  animation: none;
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
  background: rgba(220, 38, 38, 0.2);
  border: 1px solid #dc2626;
  border-radius: 10px;
  color: #ef4444;
  text-decoration: none;
  font-weight: 600;
  transition: all 0.3s;
}

.nav-button:hover {
  background: #dc2626;
  color: white;
  transform: translateY(-3px);
  box-shadow: 0 10px 20px rgba(220, 38, 38, 0.4);
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
  
  .rooms-grid {
    grid-template-columns: 1fr;
  }
}
</style>

<div class="binary-background"></div>

<div class="container">
  <div class="page-header">
    <div class="platform-badge">TRYHACKME</div>
    <h1 class="page-title">CYBERSECURITY</h1>
    <p class="page-subtitle">Learning Journey & Room Notes</p>
  </div>

  <div class="profile-section">
    <iframe src="https://tryhackme.com/api/v2/badges/public-profile?userPublicId=3165378"></iframe>
  </div>

  <div class="terminal">
    <div class="terminal-header">
      <div class="terminal-dot red"></div>
      <div class="terminal-dot yellow"></div>
      <div class="terminal-dot green"></div>
    </div>
    <div class="terminal-text">
      <span class="prompt">haname@tryhackme:~$</span> cat journey_info.txt<br>
      → Approche: Random Rooms & Challenges<br>
      → Focus: Practical Skills & Real-World Scenarios<br>
      → Documentation: Write-ups & Notes pour chaque room<br>
      → Status: Active learning...
    </div>
  </div>

  <h2 class="section-title">Rooms & Write-ups</h2>
  
  <div class="rooms-grid">
    <a href="https://www.canva.com/design/DAG-szd4Ha4/FUYHK4XgKzJ9cewGWGoNaw/edit?utm_content=DAG-szd4Ha4&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton" class="room-card">
      <img src="{{ site.baseurl }}/assets/images/honey.png" alt="Honeypots" class="room-image">
      <h3>Introduction To Honeypots</h3>
      <p class="room-description">Learn about honeypots and how they can be used to detect and analyze malicious activity in a network environment.</p>
      <div class="status-badge done">
        <span class="status-dot done"></span>
        Done
      </div>
    </a>

   <a href="https://www.canva.com/design/DAG-rGFAO3Q/3FW6lGUjPm0yXQBBDkcSKQ/edit?utm_content=DAG-rGFAO3Q&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton" target="_blank" class="room-card">
      <img src="{{ site.baseurl }}/assets/images/dock.png" alt="Docker" class="room-image">
      <h3>Introduction to Docker</h3>
      <p class="room-description">Learn the basics of Docker containerization, understand core concepts, and get hands-on experience with containers.</p>
      <div class="status-badge done">
        <span class="status-dot done"></span>
        Done
      </div>
    </a>

   <a href="https://www.canva.com/design/DAG-yGatPVg/TdUJPJGrO0DccBwOh2OtTw/edit?utm_content=DAG-yGatPVg&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton" class="room-card">
      <img src="{{ site.baseurl }}/assets/images/iot.png" alt="IoT Pentesting" class="room-image">
      <h3>Intro to IoT Pentesting</h3>
      <p class="room-description">Discover the fundamentals of IoT security and learn penetration testing techniques for Internet of Things devices.</p>
      <div class="status-badge done">
        <span class="status-dot done"></span>
        Done
      </div>
    </a>

   <a href="https://www.canva.com/design/DAG-y0eYKzw/5WrIOY1MGnqsIvEns_DpWg/edit?utm_content=DAG-y0eYKzw&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton" class="room-card">
      <img src="{{ site.baseurl }}/assets/images/crypto1.png" alt="Cryptography Basics" class="room-image">
      <h3>Cryptography Basics</h3>
      <p class="room-description">Learn the basics of cryptography and symmetric encryption.</p>
      <div class="status-badge done">
        <span class="status-dot done"></span>
        Done
      </div>
    </a>

   <a href="#" class="room-card">
      <img src="{{ site.baseurl }}/assets/images/crypto1.png" alt="Public Key Cryptography" class="room-image">
      <h3>Public Key Cryptography Basics</h3>
      <p class="room-description">Discover how public key ciphers such as RSA work and explore their role in applications such as SSH.</p>
      <div class="status-badge done">
        <span class="status-dot done"></span>
        Done
      </div>
    </a>

   <a href="#" class="room-card">
      <img src="{{ site.baseurl }}/assets/images/crypto2.png" alt="Hashing Basics" class="room-image">
      <h3>Hashing Basics</h3>
      <p class="room-description">Learn about hashing functions and their uses in password verification and file integrity checking.</p>
      <div class="status-badge done">
        <span class="status-dot done"></span>
        Done
      </div>
    </a>

   <a href="#" class="room-card">
      <img src="{{ site.baseurl }}/assets/images/jhon.png" alt="John the Ripper" class="room-image">
      <h3>John the Ripper: The Basics</h3>
      <p class="room-description">Learn how to use John the Ripper, a powerful and adaptable hash-cracking tool.</p>
      <div class="status-badge done">
        <span class="status-dot done"></span>
        Done
      </div>
    </a>

   <a href="https://www.canva.com/design/DAG-9aWxX_E/OMOr6swEWBCkKz3fMkJ6cw/edit?utm_content=DAG-9aWxX_E&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton" class="room-card">
      <img src="{{ site.baseurl }}/assets/images/Gouv.png" alt="Governance & Regulation" class="room-image">
      <h3>Governance & Regulation</h3>
      <p class="room-description">Explore policies and frameworks vital for regulating cyber security in an organisation.</p>
      <div class="status-badge done">
        <span class="status-dot done"></span>
        Done
      </div>
    </a>

   <a href="https://www.canva.com/design/DAG--b-keWE/XOwv2THcEwci6br-HkwYzQ/edit?utm_content=DAG--b-keWE&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton" class="room-card">
      <img src="{{ site.baseurl }}/assets/images/anal.png" class="room-image">
      <h3>Junior Security Analyst Intro</h3>
      <p class="room-description">Play through a day in the life of a Security Analyst and experience their everyday duties.</p>
      <div class="status-badge done">
        <span class="status-dot done"></span>
        Done
      </div>
    </a>

   <a href="https://www.canva.com/design/DAG--sYoFjY/MhZHZBlMEOq3M1yUNYSR3Q/edit?utm_content=DAG--sYoFjY&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton" class="room-card">
      <img src="{{ site.baseurl }}/assets/images/soc.png" class="room-image">
      <h3>SOC Role in Blue Team</h3>
      <p class="room-description">Discover security roles and learn how to advance your SOC career, starting from the L1 analyst.</p>
      <div class="status-badge done">
        <span class="status-dot done"></span>
        Done
      </div>
    </a>

   <a href="https://www.canva.com/design/DAG--7v-mEA/3uK8rfMVrBx5uzCo0pEYsw/edit?utm_content=DAG--7v-mEA&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton" class="room-card">
      <img src="{{ site.baseurl }}/assets/images/hu.png" class="room-image">
      <h3>Humans as Attack Vectors</h3>
      <p class="room-description">Learn how attackers exploit vulnerable and misconfigured systems, and how you can protect them.</p>
      <div class="status-badge done">
        <span class="status-dot done"></span>
        Done
      </div>
    </a>
     <a href="https://www.canva.com/design/DAG-_zfcGMY/qSU10HYB2cA10WGS2jMgpA/edit?utm_content=DAG-_zfcGMY&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton" class="room-card">
      <img src="{{ site.baseurl }}/assets/images/hu.png" class="room-image">
      <h3>Systems as Attack Vectors</h3>
      <p class="room-description">Understand why and how people are targeted in cyber attacks and how the SOC helps defend them.</p>
      <div class="status-badge done">
        <span class="status-dot done"></span>
        Done
      </div>
    </a>
   <a href="https://www.canva.com/design/DAG_AT1jkTw/FahY6GCaBBjkyqhOBKaWkQ/edit?utm_content=DAG_AT1jkTw&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton" class="room-card">
      <img src="{{ site.baseurl }}/assets/images/l1.png" class="room-image">
      <h3>SOC L1 Alert Triage</h3>
      <p class="room-description">Learn more about SOC alerts and build a systematic approach to efficiently triaging them.</p>
      <div class="status-badge done">
        <span class="status-dot done"></span>
        Done
      </div>
    </a> 
  </div>

  <div class="footer-nav">
    <a href="{{ site.baseurl }}/my-lab" class="nav-button">← Back to Lab</a>
    <a href="https://tryhackme.com" target="_blank" class="nav-button">TryHackMe</a>
  </div>
</div>

<script>
document.addEventListener('DOMContentLoaded', function() {
  const binaryContainer = document.querySelector('.binary-background');
  
  for (let i = 0; i < 100; i++) {
    const digit = document.createElement('div');
    digit.className = 'binary-digit';
    digit.textContent = Math.random() > 0.5 ? '1' : '0';
    digit.style.left = Math.random() * 100 + 'vw';
    digit.style.fontSize = (Math.random() * 18 + 12) + 'px';
    digit.style.animationDuration = (Math.random() * 10 + 5) + 's';
    digit.style.animationDelay = Math.random() * 5 + 's';
    digit.style.opacity = Math.random() * 0.2 + 0.05;
    const colors = ['rgba(220, 38, 38, 0.15)', 'rgba(239, 68, 68, 0.15)', 'rgba(153, 27, 27, 0.15)'];
    digit.style.color = colors[Math.floor(Math.random() * colors.length)];
    binaryContainer.appendChild(digit);
  }
  
  for (let i = 0; i < 30; i++) {
    const floatDigit = document.createElement('div');
    floatDigit.className = 'binary-digit float';
    floatDigit.textContent = Math.random() > 0.5 ? '1' : '0';
    floatDigit.style.left = Math.random() * 100 + 'vw';
    floatDigit.style.top = Math.random() * 100 + 'vh';
    floatDigit.style.fontSize = (Math.random() * 22 + 14) + 'px';
    floatDigit.style.animationDelay = Math.random() * 2 + 's';
    floatDigit.style.opacity = Math.random() * 0.3 + 0.1;
    const floatColors = ['rgba(220, 38, 38, 0.25)', 'rgba(239, 68, 68, 0.25)'];
    floatDigit.style.color = floatColors[Math.floor(Math.random() * floatColors.length)];
    binaryContainer.appendChild(floatDigit);
  }
});
</script>
