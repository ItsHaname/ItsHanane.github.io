---
layout: default
title: Accueil
nav: home
---

<style>
@import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700;900&family=Share+Tech+Mono&family=Oxanium:wght@300;400;600&display=swap');

:root {
  --neon-pink: #ff00ff;
  --neon-blue: #00ffff;
  --neon-purple: #9d00ff;
  --cyber-green: #00ff9d;
  --matrix-green: #0f0;
  --dark-bg: #0a0a0f;
  --terminal-bg: #000011;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  background: var(--dark-bg);
  font-family: 'Oxanium', monospace;
  overflow-x: hidden;
  color: #fff;
}

@keyframes matrixRain {
  0% { background-position: 0% 0%; }
  100% { background-position: 0% 100%; }
}

@keyframes float {
  0%, 100% { transform: translateY(0) rotate(0deg); }
  50% { transform: translateY(-20px) rotate(5deg); }
}

@keyframes glitch {
  0% { transform: translate(0); }
  20% { transform: translate(-2px, 2px); }
  40% { transform: translate(-2px, -2px); }
  60% { transform: translate(2px, 2px); }
  80% { transform: translate(2px, -2px); }
  100% { transform: translate(0); }
}

@keyframes pulseNeon {
  0%, 100% { 
    text-shadow: 0 0 10px var(--neon-pink),
                 0 0 20px var(--neon-pink),
                 0 0 30px var(--neon-pink);
  }
  50% { 
    text-shadow: 0 0 20px var(--neon-pink),
                 0 0 40px var(--neon-pink),
                 0 0 60px var(--neon-pink),
                 0 0 80px var(--neon-purple);
  }
}

@keyframes scanline {
  0% { transform: translateY(-100%); }
  100% { transform: translateY(100vh); }
}

@keyframes typewriter {
  from { width: 0; }
  to { width: 100%; }
}

@keyframes blink {
  50% { border-color: transparent; }
}

@keyframes hologram {
  0% { 
    box-shadow: 0 0 20px var(--neon-blue),
                inset 0 0 20px rgba(0, 255, 255, 0.1);
  }
  100% { 
    box-shadow: 0 0 40px var(--neon-purple),
                inset 0 0 40px rgba(157, 0, 255, 0.2);
  }
}

.matrix-bg {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: 
    linear-gradient(rgba(10, 10, 15, 0.95), rgba(10, 10, 15, 0.98)),
    repeating-linear-gradient(0deg, 
      transparent, 
      transparent 2px, 
      rgba(0, 255, 0, 0.03) 2px, 
      rgba(0, 255, 0, 0.03) 4px);
  animation: matrixRain 20s linear infinite;
  z-index: -2;
}

.container {
  max-width: 1400px;
  margin: 0 auto;
  padding: 20px;
  position: relative;
  z-index: 1;
}

.neon-border {
  border: 2px solid var(--neon-pink);
  box-shadow: 
    0 0 15px var(--neon-pink),
    inset 0 0 15px var(--neon-pink);
  animation: pulseNeon 2s infinite;
}

/* Holographic Header */
.holographic-header {
  text-align: center;
  margin: 60px 0;
  position: relative;
}

.hologram-title {
  font-family: 'Orbitron', sans-serif;
  font-size: 5rem;
  font-weight: 900;
  text-transform: uppercase;
  letter-spacing: 0.3em;
  color: transparent;
  background: linear-gradient(
    45deg,
    var(--neon-pink),
    var(--neon-blue),
    var(--neon-purple),
    var(--cyber-green)
  );
  background-size: 400% 400%;
  -webkit-background-clip: text;
  background-clip: text;
  animation: gradientShift 3s ease infinite;
  position: relative;
  display: inline-block;
}

@keyframes gradientShift {
  0%, 100% { background-position: 0% 50%; }
  50% { background-position: 100% 50%; }
}

.hologram-title::before {
  content: attr(data-text);
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: linear-gradient(
    45deg,
    var(--neon-pink),
    var(--neon-blue),
    var(--neon-purple),
    var(--cyber-green)
  );
  background-size: 400% 400%;
  -webkit-background-clip: text;
  background-clip: text;
  filter: blur(20px);
  opacity: 0.7;
  animation: gradientShift 3s ease infinite reverse;
  z-index: -1;
}

/* Cyber Terminal */
.cyber-terminal {
  background: rgba(0, 0, 0, 0.9);
  border: 3px solid var(--matrix-green);
  border-radius: 15px;
  padding: 40px;
  margin: 50px auto;
  width: 90%;
  max-width: 1000px;
  position: relative;
  overflow: hidden;
  font-family: 'Share Tech Mono', monospace;
}

.terminal-header {
  display: flex;
  align-items: center;
  gap: 15px;
  margin-bottom: 30px;
  padding-bottom: 15px;
  border-bottom: 2px solid var(--matrix-green);
}

.terminal-dots {
  display: flex;
  gap: 10px;
}

.terminal-dot {
  width: 18px;
  height: 18px;
  border-radius: 50%;
}

.dot-red { background: #ff5c5c; box-shadow: 0 0 10px #ff5c5c; }
.dot-yellow { background: #ffdd5c; box-shadow: 0 0 10px #ffdd5c; }
.dot-green { background: #5cff8c; box-shadow: 0 0 10px #5cff8c; }

.terminal-title {
  color: var(--matrix-green);
  font-size: 1.5rem;
  letter-spacing: 0.2em;
  flex-grow: 1;
}

.scanline {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 4px;
  background: linear-gradient(
    to right,
    transparent,
    rgba(0, 255, 0, 0.8),
    transparent
  );
  animation: scanline 3s linear infinite;
  z-index: 2;
}

.typewriter-container {
  margin: 30px 0;
}

.typewriter-text {
  font-size: 1.8rem;
  color: var(--matrix-green);
  white-space: nowrap;
  overflow: hidden;
  border-right: 3px solid var(--matrix-green);
  animation: 
    typewriter 4s steps(40) 1s 1 normal both,
    blink 0.75s step-end infinite;
  width: 0;
}

/* Holographic Navigation Grid */
.hologrid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 30px;
  margin: 60px 0;
  perspective: 1000px;
}

.hologram-card {
  background: rgba(0, 0, 0, 0.7);
  border: 1px solid rgba(0, 255, 255, 0.3);
  border-radius: 15px;
  padding: 40px 30px;
  text-align: center;
  position: relative;
  overflow: hidden;
  transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
  transform-style: preserve-3d;
}

.hologram-card::before {
  content: '';
  position: absolute;
  top: -2px;
  left: -2px;
  right: -2px;
  bottom: -2px;
  background: linear-gradient(
    45deg,
    var(--neon-pink),
    var(--neon-blue),
    var(--neon-purple)
  );
  z-index: -1;
  filter: blur(20px);
  opacity: 0;
  transition: opacity 0.4s;
}

.hologram-card:hover::before {
  opacity: 0.7;
}

.hologram-card:hover {
  transform: translateY(-15px) rotateX(5deg);
  border-color: var(--neon-blue);
  animation: hologram 1.5s infinite alternate;
}

.hologram-icon {
  font-size: 3rem;
  margin-bottom: 20px;
  color: var(--neon-blue);
  text-shadow: 0 0 20px currentColor;
}

.hologram-card h3 {
  font-family: 'Orbitron', sans-serif;
  font-size: 1.8rem;
  color: var(--neon-pink);
  margin-bottom: 15px;
  text-transform: uppercase;
  letter-spacing: 0.2em;
}

.hologram-card p {
  color: rgba(255, 255, 255, 0.8);
  font-size: 1.1rem;
  line-height: 1.6;
}

/* Floating Elements */
.floating-elements {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  pointer-events: none;
  z-index: -1;
}

.floating-element {
  position: absolute;
  font-family: 'Share Tech Mono', monospace;
  color: rgba(0, 255, 0, 0.3);
  font-size: 1.5rem;
  animation: float 10s infinite ease-in-out;
}

/* Badge Matrix */
.badge-matrix {
  display: flex;
  justify-content: center;
  gap: 25px;
  margin: 50px 0;
  flex-wrap: wrap;
}

.cyber-badge {
  padding: 15px 35px;
  background: rgba(0, 0, 0, 0.8);
  border: 2px solid var(--neon-purple);
  border-radius: 50px;
  color: white;
  font-family: 'Orbitron', sans-serif;
  font-size: 1.2rem;
  text-transform: uppercase;
  letter-spacing: 0.1em;
  cursor: pointer;
  position: relative;
  overflow: hidden;
  transition: all 0.3s;
}

.cyber-badge::before {
  content: '';
  position: absolute;
  top: 0;
  left: -100%;
  width: 100%;
  height: 100%;
  background: linear-gradient(
    90deg,
    transparent,
    rgba(157, 0, 255, 0.4),
    transparent
  );
  transition: left 0.5s;
}

.cyber-badge:hover::before {
  left: 100%;
}

.cyber-badge:hover {
  transform: translateY(-5px);
  box-shadow: 
    0 0 30px var(--neon-purple),
    inset 0 0 20px rgba(157, 0, 255, 0.3);
}

/* Binary Rain */
.binary-rain {
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
  color: rgba(0, 255, 0, 0.1);
  font-family: 'Share Tech Mono', monospace;
  font-size: 24px;
  animation: fall linear infinite;
  text-shadow: 0 0 10px rgba(0, 255, 0, 0.5);
}

@keyframes fall {
  to { transform: translateY(100vh); }
}

/* Responsive */
@media (max-width: 768px) {
  .hologram-title {
    font-size: 3rem;
    letter-spacing: 0.2em;
  }
  
  .cyber-terminal {
    padding: 20px;
    width: 95%;
  }
  
  .hologrid {
    grid-template-columns: 1fr;
  }
  
  .typewriter-text {
    font-size: 1.4rem;
  }
}
</style>

<script>
// Create floating elements
document.addEventListener('DOMContentLoaded', function() {
  const floatingContainer = document.createElement('div');
  floatingContainer.className = 'floating-elements';
  document.body.appendChild(floatingContainer);

  const symbols = ['</>', '{ }', ';', '0x0F', '0x1A', '404', '200', '500', 'root#', 'admin@', 'sudo', 'ssh', 'ftp', 'http', 'https'];
  
  for (let i = 0; i < 20; i++) {
    const element = document.createElement('div');
    element.className = 'floating-element';
    element.textContent = symbols[Math.floor(Math.random() * symbols.length)];
    element.style.left = Math.random() * 100 + 'vw';
    element.style.top = Math.random() * 100 + 'vh';
    element.style.animationDelay = Math.random() * 10 + 's';
    element.style.animationDuration = (Math.random() * 10 + 15) + 's';
    floatingContainer.appendChild(element);
  }

  // Create binary rain
  const binaryRain = document.createElement('div');
  binaryRain.className = 'binary-rain';
  document.body.appendChild(binaryRain);

  for (let i = 0; i < 100; i++) {
    const digit = document.createElement('div');
    digit.className = 'binary-digit';
    digit.textContent = Math.random() > 0.5 ? '1' : '0';
    digit.style.left = Math.random() * 100 + 'vw';
    digit.style.animationDuration = (Math.random() * 3 + 2) + 's';
    digit.style.animationDelay = Math.random() * 5 + 's';
    digit.style.fontSize = (Math.random() * 20 + 12) + 'px';
    digit.style.opacity = Math.random() * 0.3 + 0.1;
    binaryRain.appendChild(digit);
  }

  // Terminal text animation
  const terminalText = document.querySelector('.typewriter-text');
  const phrases = [
    "Initializing security protocols...",
    "Loading cyber defense systems...",
    "Establishing secure connection...",
    "Welcome to the cyber frontier...",
    "Access granted. User: HANAME..."
  ];
  
  let phraseIndex = 0;
  
  function cyclePhrases() {
    terminalText.style.animation = 'none';
    setTimeout(() => {
      terminalText.textContent = phrases[phraseIndex];
      terminalText.style.width = '0';
      setTimeout(() => {
        terminalText.style.animation = 'typewriter 3s steps(40) 1 normal both, blink 0.75s step-end infinite';
      }, 50);
    }, 1000);
    
    phraseIndex = (phraseIndex + 1) % phrases.length;
    setTimeout(cyclePhrases, 4000);
  }
  
  setTimeout(cyclePhrases, 4000);
});

// Add cursor trail effect
document.addEventListener('mousemove', function(e) {
  const trail = document.createElement('div');
  trail.className = 'cursor-trail';
  trail.style.position = 'fixed';
  trail.style.left = e.clientX + 'px';
  trail.style.top = e.clientY + 'px';
  trail.style.width = '5px';
  trail.style.height = '5px';
  trail.style.background = 'radial-gradient(circle, var(--neon-blue), transparent)';
  trail.style.borderRadius = '50%';
  trail.style.pointerEvents = 'none';
  trail.style.zIndex = '9999';
  
  document.body.appendChild(trail);
  
  setTimeout(() => {
    trail.style.opacity = '0';
    trail.style.transform = 'scale(2)';
    setTimeout(() => trail.remove(), 300);
  }, 50);
});
</script>

<!-- Matrix Background -->
<div class="matrix-bg"></div>

<!-- Main Container -->
<div class="container">

  <!-- Holographic Header -->
  <div class="holographic-header">
    <div class="hologram-title" data-text="HANAME">HANAME</div>
    <div style="
      font-family: 'Orbitron', sans-serif;
      color: var(--cyber-green);
      font-size: 1.5rem;
      letter-spacing: 0.5em;
      margin-top: 20px;
      text-transform: uppercase;
      animation: glitch 3s infinite;
    ">
      CYBERSECURITY_SPECIALIST
    </div>
  </div>

  <!-- Cyber Terminal -->
  <div class="cyber-terminal">
    <div class="scanline"></div>
    <div class="terminal-header">
      <div class="terminal-dots">
        <div class="terminal-dot dot-red"></div>
        <div class="terminal-dot dot-yellow"></div>
        <div class="terminal-dot dot-green"></div>
      </div>
      <div class="terminal-title">TERMINAL v3.14</div>
    </div>
    
    <div class="typewriter-container">
      <div class="typewriter-text">Initializing security protocols...</div>
    </div>
    
    <div style="
      color: var(--matrix-green);
      font-size: 1.2rem;
      line-height: 1.8;
      margin-top: 30px;
      padding: 20px;
      border: 1px solid rgba(0, 255, 0, 0.2);
      border-radius: 10px;
      background: rgba(0, 0, 0, 0.5);
    ">
      <span style="color: var(--neon-blue);">$</span> whoami<br>
      > HANAME - CYBERSECURITY STUDENT @ FSSM<br><br>
      
      <span style="color: var(--neon-blue);">$</span> status<br>
      > ACTIVE | LEARNING | EXPLORING<br><br>
      
      <span style="color: var(--neon-blue);">$</span> mission<br>
      > SHARE KNOWLEDGE | BUILD LABS | SOLVE CHALLENGES<br>
    </div>
  </div>

  <!-- Holographic Navigation Grid -->
  <div class="hologrid">
    <div class="hologram-card" onclick="window.location='{{ site.baseurl }}/about'">
      <div class="hologram-icon">⟢</div>
      <h3>IDENTITY PROFILE</h3>
      <p>Access complete bio, skills matrix, and mission statement. Unlock the story behind the code.</p>
    </div>
    
    <div class="hologram-card" onclick="window.location='{{ site.baseurl }}/fssm'">
      <div class="hologram-icon">⎈</div>
      <h3>ACADEMIC CORE</h3>
      <p>FSSM curriculum decrypted. Modules, projects, and cryptographic achievements detailed.</p>
    </div>
    
    <div class="hologram-card" onclick="window.location='{{ site.baseurl }}/tryhackme'">
      <div class="hologram-icon">⚔</div>
      <h3>CTF ARENA</h3>
      <p>TryHackMe battle logs. Rooms conquered, badges earned, and challenge write-ups archived.</p>
    </div>
    
    <div class="hologram-card" onclick="window.location='{{ site.baseurl }}/my-lab'">
      <div class="hologram-icon">⎔</div>
      <h3>SANDBOX NETWORK</h3>
      <p>Virtualized testing environment. Machines, topologies, and exploitation playgrounds.</p>
    </div>
  </div>

  <!-- Welcome Message -->
  <div style="
    text-align: center;
    margin: 80px auto;
    padding: 40px;
    max-width: 800px;
    background: rgba(0, 0, 0, 0.7);
    border: 1px solid rgba(255, 0, 255, 0.3);
    border-radius: 20px;
    position: relative;
    overflow: hidden;
  ">
    <div style="
      position: absolute;
      top: 0;
      left: 0;
      right: 0;
      height: 2px;
      background: linear-gradient(90deg, 
        transparent,
        var(--neon-pink),
        var(--neon-blue),
        var(--neon-purple),
        transparent
      );
    "></div>
    
    <p style="
      font-size: 1.5rem;
      line-height: 1.8;
      color: rgba(255, 255, 255, 0.9);
      margin-bottom: 20px;
    ">
      <span style="color: var(--neon-pink); font-weight: bold;">[SYSTEM MESSAGE]</span><br>
      Greetings. I am <span style="color: var(--cyber-green); text-shadow: 0 0 10px currentColor;">HANAME</span>, 
      cybersecurity operative specializing in network defense, ethical hacking, and digital forensics.<br><br>
      
      This terminal serves as my digital nexus - hosting academic records, capture-the-flag exploits, 
      and experimental sandbox environments.<br><br>
      
      <span style="color: var(--neon-blue);">Access level: UNCLASSIFIED</span><br>
      <span style="color: var(--matrix-green);">Status: ACTIVE AND LEARNING</span>
    </p>
  </div>

  <!-- Cyber Badges -->
  <div class="badge-matrix">
    <div class="cyber-badge" onclick="window.open('https://tryhackme.com')">TRYHACKME</div>
    <div class="cyber-badge" onclick="window.open('https://github.com/ItsHaname')">GITHUB</div>
    <div class="cyber-badge">TWITTER/X</div>
    <div class="cyber-badge">LINKEDIN</div>
    <div class="cyber-badge" onclick="window.open('mailto:contact@haname.cyber')">CONTACT</div>
  </div>

  <!-- Footer -->
  <footer style="
    text-align: center;
    margin-top: 100px;
    padding: 30px;
    color: rgba(255, 255, 255, 0.5);
    font-family: 'Share Tech Mono', monospace;
    letter-spacing: 0.2em;
    border-top: 1px solid rgba(0, 255, 255, 0.1);
  ">
    <div style="margin-bottom: 15px;">
      <span style="color: var(--neon-pink);">[</span>
      <span style="color: var(--neon-blue);">SYSTEM ACTIVE</span>
      <span style="color: var(--neon-pink);">]</span>
    </div>
    © 2025 HANAME CYBERSECURITY OPERATIONS<br>
    FSSM ACADEMIC AFFILIATION | SECURITY CLEARANCE: LEVEL 7<br>
    <span style="color: var(--matrix-green); font-size: 0.9rem;">
      LAST UPDATED: <span id="current-date"></span>
    </span>
  </footer>

</div>

<script>
// Set current date
document.getElementById('current-date').textContent = 
  new Date().toLocaleDateString('en-GB', {
    day: '2-digit',
    month: 'short',
    year: 'numeric',
    hour: '2-digit',
    minute: '2-digit'
  }).toUpperCase();

// Add sound effects on hover
document.querySelectorAll('.hologram-card, .cyber-badge').forEach(el => {
  el.addEventListener('mouseenter', () => {
    const context = new (window.AudioContext || window.webkitAudioContext)();
    const oscillator = context.createOscillator();
    const gainNode = context.createGain();
    
    oscillator.connect(gainNode);
    gainNode.connect(context.destination);
    
    oscillator.type = 'sine';
    oscillator.frequency.value = 800 + Math.random() * 400;
    gainNode.gain.value = 0.1;
    gainNode.gain.exponentialRampToValueAtTime(0.001, context.currentTime + 0.2);
    
    oscillator.start();
    oscillator.stop(context.currentTime + 0.2);
  });
});

// Matrix code effect in background
function createMatrixCode() {
  const chars = "01ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz";
  const codeLength = Math.floor(Math.random() * 50) + 20;
  let code = "";
  
  for (let i = 0; i < codeLength; i++) {
    code += chars[Math.floor(Math.random() * chars.length)];
  }
  
  return code;
}

setInterval(() => {
  const matrixText = document.createElement('div');
  matrixText.className = 'matrix-text';
  matrixText.textContent = createMatrixCode();
  matrixText.style.position = 'fixed';
  matrixText.style.right = Math.random() * 100 + 'vw';
  matrixText.style.top = '-50px';
  matrixText.style.color = 'rgba(0, 255, 0, 0.1)';
  matrixText.style.fontFamily = 'Share Tech Mono, monospace';
  matrixText.style.fontSize = (Math.random() * 10 + 8) + 'px';
  matrixText.style.whiteSpace = 'nowrap';
  matrixText.style.pointerEvents = 'none';
  matrixText.style.zIndex = '-1';
  matrixText.style.animation = `fall ${Math.random() * 5 + 3}s linear forwards`;
  
  document.body.appendChild(matrixText);
  
  setTimeout(() => matrixText.remove(), 5000);
}, 100);
</script>
