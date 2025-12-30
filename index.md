---
layout: default
title: Accueil
nav: home
---

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

@keyframes cyberiaGlitch {
  0% { text-shadow: 2px 2px 0px #ff00ff, -2px -2px 0px #00ffff; }
  25% { text-shadow: -2px 2px 0px #ff00ff, 2px -2px 0px #00ffff; }
  50% { text-shadow: 2px -2px 0px #00ffff, -2px 2px 0px #ff00ff; }
  75% { text-shadow: -2px -2px 0px #00ffff, 2px 2px 0px #ff00ff; }
  100% { text-shadow: 2px 2px 0px #ff00ff, -2px -2px 0px #00ffff; }
}

@keyframes blink {
  0%, 100% { opacity: 1; }
  50% { opacity: 0; }
}

@keyframes cloudFloat {
  0%, 100% { 
    transform: translateX(0) translateY(0);
    filter: blur(0px);
  }
  25% { 
    transform: translateX(-10px) translateY(-5px);
    filter: blur(1px);
  }
  50% { 
    transform: translateX(10px) translateY(5px);
    filter: blur(0.5px);
  }
  75% { 
    transform: translateX(-5px) translateY(3px);
    filter: blur(0.8px);
  }
}

body {
  background: #0a0a0f;
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
  color: rgba(0, 170, 255, 0.15);
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

/* CYBERIA Header avec nuage */
.cyberia-header {
  text-align: center;
  margin-bottom: 60px;
  padding: 40px 20px;
  position: relative;
}

.cyberia-title {
  font-size: 5em;
  color: #ff00ff;
  text-shadow: 0 0 20px #ff00ff;
  margin: 0;
  font-weight: 900;
  letter-spacing: 10px;
  text-transform: uppercase;
  animation: cyberiaGlitch 0.8s infinite;
  position: relative;
}

.cyberia-subtitle {
  font-size: 1.8em;
  color: #00ffff;
  margin: 10px 0 0 0;
  text-shadow: 0 0 10px #00ffff;
  letter-spacing: 4px;
  font-weight: 300;
}

.cyberia-subtitle::after {
  content: '_';
  animation: blink 1s infinite;
  color: #ff00ff;
}

/* Nuage autour de CYBERIA */
.cloud-container {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  pointer-events: none;
  z-index: -1;
}

.cloud {
  position: absolute;
  background: rgba(255, 255, 255, 0.05);
  border-radius: 50%;
  filter: blur(20px);
  animation: cloudFloat 20s ease-in-out infinite;
}

.cloud-1 {
  width: 300px;
  height: 100px;
  top: -30px;
  left: 10%;
  animation-delay: 0s;
}

.cloud-2 {
  width: 250px;
  height: 80px;
  top: 30px;
  right: 15%;
  animation-delay: 5s;
}

.cloud-3 {
  width: 200px;
  height: 60px;
  bottom: 40px;
  left: 20%;
  animation-delay: 10s;
}

.cloud-4 {
  width: 180px;
  height: 50px;
  bottom: 20px;
  right: 25%;
  animation-delay: 15s;
}

/* Rest of the page - keeping original style */
.cyber-header {
  text-align: center;
  margin-bottom: 60px;
}

.neon-title {
  font-size: 3em;
  text-align: center;
  color: transparent;
  background: linear-gradient(90deg, #ff00ff, #00ffff, #ff6b9d);
  background-size: 200% auto;
  -webkit-background-clip: text;
  background-clip: text;
  animation: gradientBG 3s ease infinite;
  margin: 40px 0 10px 0;
  font-weight: 900;
  letter-spacing: 2px;
}

.subtitle {
  font-size: 1.5em;
  color: #8b949e;
  text-align: center;
  margin-bottom: 40px;
  font-style: italic;
}

.glitch-text {
  font-size: 1.8em;
  font-weight: bold;
  color: #fff;
  position: relative;
  display: inline-block;
  margin: 10px 0 40px 0;
}

.glitch-text:before,
.glitch-text:after {
  content: attr(data-text);
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}

.glitch-text:before {
  left: 2px;
  text-shadow: -1px 0 #ff00ff;
  animation: glitch-1 2s infinite linear alternate-reverse;
}

.glitch-text:after {
  left: -2px;
  text-shadow: -1px 0 #00ffff;
  animation: glitch-2 3s infinite linear alternate-reverse;
}

@keyframes glitch-1 {
  0% { clip-path: inset(40% 0 61% 0); }
  100% { clip-path: inset(92% 0 1% 0); }
}

@keyframes glitch-2 {
  0% { clip-path: inset(25% 0 58% 0); }
  100% { clip-path: inset(75% 0 1% 0); }
}

.hologram-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 20px;
  margin: 60px 0;
}

.holo-card {
  background: rgba(13, 17, 23, 0.85);
  border: 1px solid rgba(138, 141, 255, 0.3);
  border-radius: 15px;
  padding: 30px;
  text-align: center;
  transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
  position: relative;
  overflow: hidden;
  text-decoration: none;
  color: inherit;
  display: block;
}

.holo-card:before {
  content: '';
  position: absolute;
  top: -2px;
  left: -2px;
  right: -2px;
  bottom: -2px;
  background: linear-gradient(45deg, #ff00ff, #00ffff, transparent);
  z-index: -1;
  opacity: 0;
  transition: opacity 0.4s;
}

.holo-card:hover:before {
  opacity: 0.5;
}

.holo-card:hover {
  transform: translateY(-10px) scale(1.02);
  border-color: #00ffff;
  box-shadow: 0 15px 35px rgba(0, 255, 255, 0.2);
}

.holo-card h3 {
  color: #ff00ff;
  margin: 0 0 15px 0;
  font-size: 1.5em;
  font-weight: 600;
}

.holo-card p {
  color: #c9d1d9;
  margin: 0;
  line-height: 1.6;
}

.welcome-text {
  text-align: center;
  font-size: 1.2em;
  color: #8b949e;
  margin: 50px 0;
  padding: 30px;
  background: rgba(13, 17, 23, 0.7);
  border-radius: 15px;
  border-left: 4px solid #ff00ff;
  animation: slideIn 1s ease-out;
}

.mission-statement {
  text-align: center;
  font-size: 1.1em;
  color: #00ffff;
  margin: 40px 0;
  padding: 20px;
  background: rgba(13, 17, 23, 0.5);
  border-radius: 10px;
  border: 1px solid rgba(0, 255, 255, 0.2);
}

.mission-statement strong {
  color: #ff00ff;
}

.badge-container {
  display: flex;
  gap: 20px;
  justify-content: center;
  margin: 40px 0;
  flex-wrap: wrap;
}

.floating-badge {
  display: inline-block;
  padding: 12px 25px;
  background: rgba(22, 27, 34, 0.8);
  border: 1px solid #30363d;
  border-radius: 25px;
  color: #00ffff;
  text-decoration: none;
  font-weight: 500;
  transition: all 0.3s;
  animation: pulse 2s infinite;
}

.floating-badge:hover {
  background: #ff00ff;
  color: white;
  transform: translateY(-3px);
  box-shadow: 0 10px 20px rgba(255, 0, 255, 0.3);
  animation: none;
}

.cyber-footer {
  text-align: center;
  margin-top: 80px;
  padding-top: 30px;
  border-top: 1px solid rgba(255, 0, 255, 0.3);
  color: #586069;
  font-size: 0.9em;
}

@media (max-width: 1024px) {
  .hologram-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (max-width: 768px) {
  .cyberia-title {
    font-size: 3em;
    letter-spacing: 5px;
  }
  
  .cyberia-subtitle {
    font-size: 1.2em;
    letter-spacing: 2px;
  }
  
  .cloud-1, .cloud-2, .cloud-3, .cloud-4 {
    transform: scale(0.7);
  }
  
  .neon-title {
    font-size: 2em;
  }
  
  .subtitle {
    font-size: 1.2em;
  }
  
  .glitch-text {
    font-size: 1.4em;
  }
  
  .hologram-grid {
    grid-template-columns: 1fr;
    gap: 20px;
  }
  
  .badge-container {
    gap: 10px;
  }
  
  .floating-badge {
    padding: 10px 20px;
    font-size: 0.9em;
  }
}
</style>

<script>
// Create binary rain background with moving 0 and 1
document.addEventListener('DOMContentLoaded', function() {
  const binaryContainer = document.createElement('div');
  binaryContainer.className = 'binary-background';
  document.body.appendChild(binaryContainer);
  
  // Create falling binary digits (matrix rain style)
  for (let i = 0; i < 100; i++) {
    const digit = document.createElement('div');
    digit.className = 'binary-digit';
    digit.textContent = Math.random() > 0.5 ? '1' : '0';
    
    // Random position
    digit.style.left = Math.random() * 100 + 'vw';
    
    // Random size
    const size = Math.random() * 18 + 12;
    digit.style.fontSize = size + 'px';
    
    // Random animation speed
    const duration = Math.random() * 10 + 5;
    const delay = Math.random() * 5;
    digit.style.animationDuration = duration + 's';
    digit.style.animationDelay = delay + 's';
    
    // Random opacity
    digit.style.opacity = Math.random() * 0.2 + 0.05;
    
    // Cyberia colors
    const colors = [
      'rgba(255, 0, 255, 0.15)',
      'rgba(0, 255, 255, 0.15)',
      'rgba(255, 107, 157, 0.15)',
      'rgba(88, 166, 255, 0.15)'
    ];
    digit.style.color = colors[Math.floor(Math.random() * colors.length)];
    
    binaryContainer.appendChild(digit);
  }
  
  // Create floating binary digits (up and down movement)
  for (let i = 0; i < 30; i++) {
    const floatDigit = document.createElement('div');
    floatDigit.className = 'binary-digit float';
    floatDigit.textContent = Math.random() > 0.5 ? '1' : '0';
    
    // Random position
    floatDigit.style.left = Math.random() * 100 + 'vw';
    floatDigit.style.top = Math.random() * 100 + 'vh';
    
    // Random size
    const floatSize = Math.random() * 22 + 14;
    floatDigit.style.fontSize = floatSize + 'px';
    
    // Random animation delay
    floatDigit.style.animationDelay = Math.random() * 2 + 's';
    
    // Random opacity
    floatDigit.style.opacity = Math.random() * 0.3 + 0.1;
    
    // Cyberia colors - brighter for floating ones
    const floatColors = [
      'rgba(255, 0, 255, 0.25)',
      'rgba(0, 255, 255, 0.25)',
      'rgba(255, 107, 157, 0.25)'
    ];
    floatDigit.style.color = floatColors[Math.floor(Math.random() * floatColors.length)];
    
    binaryContainer.appendChild(floatDigit);
  }
  
  // Add subtle floating animation to cards
  const cards = document.querySelectorAll('.holo-card');
  cards.forEach((card, index) => {
    card.style.animationDelay = (index * 0.1) + 's';
    card.style.animation = 'slideIn 0.8s ease-out forwards';
    card.style.opacity = '0';
  });
  
  // Create cloud container
  const cloudContainer = document.createElement('div');
  cloudContainer.className = 'cloud-container';
  document.querySelector('.cyberia-header').appendChild(cloudContainer);
});
</script>

<div class="container">

  <!-- CYBERIA Header avec nuage -->
  <div class="cyberia-header">
    <div class="cloud-container">
      <div class="cloud cloud-1"></div>
      <div class="cloud cloud-2"></div>
      <div class="cloud cloud-3"></div>
      <div class="cloud cloud-4"></div>
    </div>
    
    <div class="cyberia-title">CYBERIA</div>
    <div class="cyberia-subtitle">Cafe & Club</div>
  </div>

  <div class="cyber-header">
    <div class="neon-title">WELCOME TO MY CYBERSPACE</div>
    <div class="subtitle">A digital notebook for everything I learn</div>
    <div class="glitch-text" data-text="CYBERSECURITY KNOWLEDGE BASE">CYBERSECURITY KNOWLEDGE BASE</div>
  </div>

  <div class="mission-statement">
    <p>In this website, I document <strong>every concept I learn</strong>, <strong>every challenge I solve</strong>, and <strong>every skill I develop</strong> in cybersecurity.<br>
    From academic notes to hands-on labs, this is my personal knowledge repository.</p>
  </div>

  <div class="hologram-grid">
    <a href="{{ site.baseurl }}/about" class="holo-card">
      <h3>À PROPOS</h3>
      <p>Mon parcours, passions et motivation dans la cybersécurité</p>
    </a>
    
    <a href="{{ site.baseurl }}/fssm" class="holo-card">
      <h3>FSSM</h3>
      <p>Formation académique, projets et compétences acquises</p>
    </a>
    
    <a href="{{ site.baseurl }}/tryhackme" class="holo-card">
      <h3>TRYHACKME</h3>
      <p>Paths complétés, badges et write-ups de challenges</p>
    </a>
    
    <a href="{{ site.baseurl }}/my-lab" class="holo-card">
      <h3>MON LAB</h3>
      <p>Environnement de test, machines virtuelles et expériences</p>
    </a>
  </div>

  <div class="welcome-text">
    <p>Salut — je suis <strong style="color: #ff00ff;">Haname</strong>, étudiante en cybersécurité à la FSSM.<br>
    Bienvenue sur mon site où je partage mon parcours, mes parcours (paths) TryHackMe, la formation FSSM, et mes laboratoires personnels.</p>
  </div>

  <div class="badge-container">
    <a href="{{ site.baseurl }}/tryhackme" class="floating-badge">TRYHACKME</a>
    <a href="https://github.com/ItsHaname" class="floating-badge" target="_blank">GITHUB</a>
    <a href="#" class="floating-badge">TWITTER</a>
    <a href="#" class="floating-badge">LINKEDIN</a>
  </div>

  <div class="cyber-footer">
    © 2025 CYBERIA — HANAME — FSSM — Personal Knowledge Repository
  </div>

</div>
