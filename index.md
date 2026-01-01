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

@keyframes blink {
  0%, 100% { opacity: 1; }
  50% { opacity: 0; }
}

@keyframes glitch-1 {
  0% { clip-path: inset(40% 0 61% 0); }
  100% { clip-path: inset(92% 0 1% 0); }
}

@keyframes glitch-2 {
  0% { clip-path: inset(25% 0 58% 0); }
  100% { clip-path: inset(75% 0 1% 0); }
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

/* CYBERIA Header - Style néon avec couleurs bleues marines */
.cyberia-header {
  text-align: center;
  margin-bottom: 60px;
  padding: 40px 20px;
  position: relative;
  background: rgba(0, 20, 40, 0.6);
  border-radius: 30px;
  border: 3px solid #1e4d7b;
  box-shadow: 0 0 40px rgba(30, 77, 123, 0.5), inset 0 0 30px rgba(30, 77, 123, 0.2);
}

.cyberia-title {
  font-size: 5em;
  color: #ff6b4a;
  text-shadow: 
    0 0 10px #ff6b4a,
    0 0 20px #ff6b4a,
    0 0 30px #ff6b4a,
    0 0 40px #ff3300;
  margin: 0;
  font-weight: 900;
  letter-spacing: 10px;
  text-transform: uppercase;
  position: relative;
  font-style: italic;
  -webkit-text-stroke: 2px #ff3300;
  paint-order: stroke fill;
}

/* Ligne horizontale */
.cyberia-line {
  width: 100%;
  height: 3px;
  background: linear-gradient(90deg, 
    transparent, 
    #1e4d7b, 
    #3b82f6, 
    #1e4d7b, 
    transparent);
  margin: 20px auto;
  max-width: 500px;
  box-shadow: 0 0 15px #3b82f6;
}

.cyberia-subtitle {
  font-size: 1.8em;
  color: #60a5fa;
  margin: 10px 0 0 0;
  text-shadow: 
    0 0 10px #60a5fa,
    0 0 20px #3b82f6,
    0 0 30px #2563eb;
  letter-spacing: 4px;
  font-weight: 300;
  font-style: italic;
}

.cyberia-subtitle::after {
  content: '_';
  animation: blink 1s infinite;
  color: #60a5fa;
}

/* Rest of the page - theme bleu marine */
.cyber-header {
  text-align: center;
  margin-bottom: 60px;
}

.neon-title {
  font-size: 3em;
  text-align: center;
  color: transparent;
  background: linear-gradient(90deg, #3b82f6, #60a5fa, #2563eb);
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
  color: #94a3b8;
  text-align: center;
  margin-bottom: 40px;
  font-style: italic;
}

.glitch-text {
  font-size: 1.8em;
  font-weight: bold;
  color: #e2e8f0;
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
  text-shadow: -1px 0 #3b82f6;
  animation: glitch-1 2s infinite linear alternate-reverse;
}

.glitch-text:after {
  left: -2px;
  text-shadow: -1px 0 #60a5fa;
  animation: glitch-2 3s infinite linear alternate-reverse;
}

.hologram-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 20px;
  margin: 60px 0;
}

.holo-card {
  background: rgba(15, 23, 42, 0.85);
  border: 1px solid rgba(59, 130, 246, 0.3);
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
  background: linear-gradient(45deg, #3b82f6, #60a5fa, transparent);
  z-index: -1;
  opacity: 0;
  transition: opacity 0.4s;
}

.holo-card:hover:before {
  opacity: 0.5;
}

.holo-card:hover {
  transform: translateY(-10px) scale(1.02);
  border-color: #60a5fa;
  box-shadow: 0 15px 35px rgba(59, 130, 246, 0.3);
}

.holo-card h3 {
  color: #3b82f6;
  margin: 0 0 15px 0;
  font-size: 1.5em;
  font-weight: 600;
}

.holo-card p {
  color: #cbd5e1;
  margin: 0;
  line-height: 1.6;
}

.welcome-text {
  text-align: center;
  font-size: 1.2em;
  color: #94a3b8;
  margin: 50px 0;
  padding: 30px;
  background: rgba(15, 23, 42, 0.7);
  border-radius: 15px;
  border-left: 4px solid #3b82f6;
  animation: slideIn 1s ease-out;
}

.mission-statement {
  text-align: center;
  font-size: 1.1em;
  color: #60a5fa;
  margin: 40px 0;
  padding: 20px;
  background: rgba(15, 23, 42, 0.5);
  border-radius: 10px;
  border: 1px solid rgba(59, 130, 246, 0.2);
}

.mission-statement strong {
  color: #3b82f6;
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
  background: rgba(15, 23, 42, 0.8);
  border: 1px solid #1e40af;
  border-radius: 25px;
  color: #60a5fa;
  text-decoration: none;
  font-weight: 500;
  transition: all 0.3s;
  animation: pulse 2s infinite;
}

.floating-badge:hover {
  background: #3b82f6;
  color: white;
  transform: translateY(-3px);
  box-shadow: 0 10px 20px rgba(59, 130, 246, 0.4);
  animation: none;
}

.cyber-footer {
  text-align: center;
  margin-top: 80px;
  padding-top: 30px;
  border-top: 1px solid rgba(59, 130, 246, 0.3);
  color: #64748b;
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
  
  .cyberia-line {
    max-width: 300px;
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
    
    // Blue marine colors
    const colors = [
      'rgba(59, 130, 246, 0.15)',
      'rgba(96, 165, 250, 0.15)',
      'rgba(37, 99, 235, 0.15)',
      'rgba(30, 64, 175, 0.15)'
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
    
    // Blue marine colors - brighter for floating ones
    const floatColors = [
      'rgba(59, 130, 246, 0.25)',
      'rgba(96, 165, 250, 0.25)',
      'rgba(37, 99, 235, 0.25)'
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
});
</script>

<div class="container">

  <!-- CYBERIA Header avec ligne horizontale -->
  <div class="cyberia-header">
    <div class="cyberia-title">CYBERIA</div>
    <div class="cyberia-line"></div>
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
    <p>Salut — je suis <strong style="color: #3b82f6;">Haname</strong>, étudiante en cybersécurité à la FSSM.<br>
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
