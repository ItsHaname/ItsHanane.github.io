---
 layout: default
 title: Accueil
 nav: home
---
<link rel="icon" href="https://raw.githubusercontent.com/ItsHaname/ItsHaname.github.io/main/logo" type="image/png">
<style>
@keyframes matrixRain {
  0% { transform: translateY(-100vh); opacity: 0; }
  10% { opacity: 1; }
  90% { opacity: 1; }
  100% { transform: translateY(100vh); opacity: 0; }
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
@keyframes glow-pulse {
  0%, 100% {
    box-shadow: 
      0 0 15px rgba(59, 130, 246, 0.6),
      inset 0 0 10px rgba(59, 130, 246, 0.3);
  }
  50% {
    box-shadow: 
      0 0 30px rgba(96, 165, 250, 0.9),
      inset 0 0 20px rgba(96, 165, 250, 0.5);
  }
}
@keyframes eye-blink {
  0%, 90%, 100% { opacity: 1; }
  93%, 96% { opacity: 0.2; }
}
@keyframes scanline {
  0% { top: 0%; }
  100% { top: 100%; }
}
@keyframes lain-eyes-blink {
  0%, 92%, 100% { opacity: 1; }
  94%, 96% { opacity: 0.3; }
}
@keyframes digital-glitch {
  0%, 100% { transform: translate(0); filter: hue-rotate(0deg); }
  33% { transform: translate(-2px, 2px); filter: hue-rotate(90deg); }
  66% { transform: translate(2px, -2px); filter: hue-rotate(180deg); }
}
@keyframes neon-flicker {
  0%, 100% { opacity: 1; text-shadow: 0 0 10px #ff6b4a, 0 0 20px #ff6b4a, 0 0 30px #ff6b4a, 0 0 40px #ff3300; }
  50% { opacity: 0.8; text-shadow: 0 0 5px #ff6b4a, 0 0 10px #ff6b4a; }
}
@keyframes card-float {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(-5px); }
}
@keyframes border-glow {
  0%, 100% { border-color: #1e4d7b; box-shadow: 0 0 20px rgba(30, 77, 123, 0.3); }
  50% { border-color: #3b82f6; box-shadow: 0 0 40px rgba(59, 130, 246, 0.6); }
}
@keyframes typing {
  from { width: 0; }
  to { width: 100%; }
}

body {
  background: #0a0e1a;
  min-height: 100vh;
  margin: 0;
  position: relative;
  overflow-x: hidden;
}

/* Scanline effect overlay */
.scanline-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  pointer-events: none;
  z-index: 9999;
  background: repeating-linear-gradient(
    0deg,
    rgba(0, 0, 0, 0.1) 0px,
    transparent 1px,
    transparent 2px,
    rgba(0, 0, 0, 0.1) 3px
  );
  opacity: 0.05;
}

/* Noise/grain effect */
.noise-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  pointer-events: none;
  z-index: 9998;
  opacity: 0.03;
  background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noiseFilter'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' /%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noiseFilter)' /%3E%3C/svg%3E");
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
.cyber-header {
  text-align: center;
  margin-bottom: 60px;
}
.neon-title {
  font-size: 3em;
  text-align: center;
  color: transparent;
  background: linear-gradient(90deg, #3b82f6, #60a5fa, #2563eb, #3b82f6);
  background-size: 200% auto;
  -webkit-background-clip: text;
  background-clip: text;
  animation: gradientBG 3s ease infinite;
  margin: 40px 0 10px 0;
  font-weight: 900;
  letter-spacing: 2px;
  position: relative;
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
  text-shadow: -2px 0 #3b82f6;
  animation: glitch-1 2s infinite linear alternate-reverse;
}
.glitch-text:after {
  left: -2px;
  text-shadow: 2px 0 #60a5fa;
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
  box-shadow: 0 0 20px rgba(59, 130, 246, 0.2);
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
  box-shadow: 0 0 15px rgba(59, 130, 246, 0.15);
}
.mission-statement strong {
  color: #3b82f6;
  text-shadow: 0 0 5px rgba(59, 130, 246, 0.5);
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
  border: 2px solid #1e40af;
  border-radius: 25px;
  color: #60a5fa;
  text-decoration: none;
  font-weight: 500;
  transition: all 0.3s;
  position: relative;
  overflow: hidden;
}
.floating-badge::before {
  content: '';
  position: absolute;
  top: 50%;
  left: 50%;
  width: 0;
  height: 0;
  background: rgba(59, 130, 246, 0.3);
  border-radius: 50%;
  transform: translate(-50%, -50%);
  transition: width 0.6s, height 0.6s;
}
.floating-badge:hover::before {
  width: 200px;
  height: 200px;
}
.floating-badge:hover {
  background: #3b82f6;
  color: white;
  transform: translateY(-5px) scale(1.05);
  box-shadow: 
    0 10px 25px rgba(59, 130, 246, 0.5),
    0 0 20px rgba(59, 130, 246, 0.3);
  border-color: #60a5fa;
}
.floating-badge span {
  position: relative;
  z-index: 1;
}
.cyber-footer {
  text-align: center;
  margin-top: 80px;
  padding-top: 30px;
  border-top: 1px solid rgba(59, 130, 246, 0.3);
  color: #64748b;
  font-size: 0.9em;
}

/* === BIG SISTER COUNTER ENHANCED === */
.counter-container {
  text-align: center;
  margin: 40px 0;
  position: relative;
}

.counter-box {
  display: inline-flex;
  align-items: center;
  gap: 25px;
  background: rgba(15, 23, 42, 0.9);
  border: 2px solid #3b82f6;
  border-radius: 20px;
  padding: 25px 35px;
  box-shadow: 
    0 0 30px rgba(59, 130, 246, 0.5),
    inset 0 0 30px rgba(59, 130, 246, 0.15);
  backdrop-filter: blur(15px);
  transition: all 0.4s ease;
  position: relative;
  overflow: hidden;
}

/* Scanline effect sur le compteur */
.counter-box::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 2px;
  background: linear-gradient(90deg, transparent, #60a5fa, transparent);
  animation: scanline 4s linear infinite;
  opacity: 0.6;
}

.counter-box:hover {
  border-color: #60a5fa;
  box-shadow: 
    0 0 50px rgba(96, 165, 250, 0.8),
    inset 0 0 40px rgba(96, 165, 250, 0.2);
  transform: translateY(-5px) scale(1.02);
}

.lain-image-container {
  position: relative;
  width: 90px;
  height: 90px;
  flex-shrink: 0;
}

.lain-image {
  width: 100%;
  height: 100%;
  border-radius: 50%;
  object-fit: cover;
  border: 3px solid #3b82f6;
  box-shadow: 
    0 0 20px rgba(59, 130, 246, 0.8),
    inset 0 0 15px rgba(59, 130, 246, 0.4);
  animation: glow-pulse 3s ease-in-out infinite, lain-eyes-blink 6s infinite;
  transition: all 0.3s;
}

.lain-image:hover {
  transform: scale(1.05);
  box-shadow: 
    0 0 35px rgba(96, 165, 250, 1),
    inset 0 0 25px rgba(96, 165, 250, 0.6);
}

/* Effet de scan sur l'image */
.eye-overlay {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 100%;
  height: 100%;
  border-radius: 50%;
  background: radial-gradient(circle, transparent 40%, rgba(59, 130, 246, 0.15) 80%);
  pointer-events: none;
}

.eye-overlay::after {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 2px;
  background: linear-gradient(90deg, transparent, rgba(96, 165, 250, 0.8), transparent);
  animation: scanline 3s linear infinite;
}

.counter-content {
  display: flex;
  flex-direction: column;
  gap: 10px;
  text-align: left;
}

.counter-label {
  color: #94a3b8;
  font-size: 1.1em;
  letter-spacing: 3px;
  text-transform: uppercase;
  display: flex;
  align-items: center;
  gap: 10px;
  text-shadow: 0 0 10px rgba(148, 163, 184, 0.5);
}

.eye-icon {
  font-size: 1.5em;
  animation: eye-blink 5s infinite;
  filter: drop-shadow(0 0 8px #60a5fa);
}

.counter-number {
  color: #60a5fa;
  font-size: 3em;
  font-weight: 700;
  text-shadow: 
    0 0 15px #60a5fa,
    0 0 30px #3b82f6,
    0 0 45px #2563eb;
  font-family: 'Courier New', monospace;
  letter-spacing: 5px;
  position: relative;
}

/* Glitch effect occasionnel sur le nombre */
.counter-number.glitch {
  animation: digital-glitch 0.3s;
}

.counter-subtitle {
  color: #64748b;
  font-size: 0.9em;
  font-style: italic;
  margin-top: -5px;
  letter-spacing: 1px;
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

  .counter-box {
    flex-direction: column;
    gap: 20px;
    padding: 30px 25px;
  }

  .counter-content {
    text-align: center;
  }

  .counter-label {
    justify-content: center;
  }

  .lain-image-container {
    width: 110px;
    height: 110px;
  }

  .counter-number {
    font-size: 2.5em;
  }
}
</style>

<script>
document.addEventListener('DOMContentLoaded', function() {
  // Binary background
  const binaryContainer = document.createElement('div');
  binaryContainer.className = 'binary-background';
  document.body.appendChild(binaryContainer);
  
  // Scanline overlay
  const scanlineOverlay = document.createElement('div');
  scanlineOverlay.className = 'scanline-overlay';
  document.body.appendChild(scanlineOverlay);
  
  // Noise overlay
  const noiseOverlay = document.createElement('div');
  noiseOverlay.className = 'noise-overlay';
  document.body.appendChild(noiseOverlay);
  
  // Create falling binary digits
  for (let i = 0; i < 120; i++) {
    const digit = document.createElement('div');
    digit.className = 'binary-digit';
    digit.textContent = Math.random() > 0.5 ? '1' : '0';
    
    digit.style.left = Math.random() * 100 + 'vw';
    const size = Math.random() * 18 + 12;
    digit.style.fontSize = size + 'px';
    const duration = Math.random() * 12 + 6;
    const delay = Math.random() * 5;
    digit.style.animationDuration = duration + 's';
    digit.style.animationDelay = delay + 's';
    
    const colors = [
      'rgba(59, 130, 246, 0.2)',
      'rgba(96, 165, 250, 0.2)',
      'rgba(37, 99, 235, 0.2)',
      'rgba(30, 64, 175, 0.15)'
    ];
    digit.style.color = colors[Math.floor(Math.random() * colors.length)];
    
    binaryContainer.appendChild(digit);
  }
  
  // Create floating binary digits
  for (let i = 0; i < 40; i++) {
    const floatDigit = document.createElement('div');
    floatDigit.className = 'binary-digit float';
    floatDigit.textContent = Math.random() > 0.5 ? '1' : '0';
    
    floatDigit.style.left = Math.random() * 100 + 'vw';
    floatDigit.style.top = Math.random() * 100 + 'vh';
    const floatSize = Math.random() * 24 + 14;
    floatDigit.style.fontSize = floatSize + 'px';
    floatDigit.style.animationDelay = Math.random() * 2 + 's';
    
    const floatColors = [
      'rgba(59, 130, 246, 0.3)',
      'rgba(96, 165, 250, 0.3)',
      'rgba(37, 99, 235, 0.25)'
    ];
    floatDigit.style.color = floatColors[Math.floor(Math.random() * floatColors.length)];
    
    binaryContainer.appendChild(floatDigit);
  }
  
  // Animate cards
  const cards = document.querySelectorAll('.holo-card');
  cards.forEach((card, index) => {
    card.style.animationDelay = (index * 0.1) + 's';
    card.style.animation = 'slideIn 0.8s ease-out forwards';
    card.style.opacity = '0';
  });
  
  // Counter glitch effect
  const counterNumber = document.getElementById('visitorCount');
  setInterval(() => {
    if (Math.random() > 0.95) {
      counterNumber.classList.add('glitch');
      setTimeout(() => {
        counterNumber.classList.remove('glitch');
      }, 300);
    }
  }, 2000);
  
  // Add text wrap to badges
  const badges = document.querySelectorAll('.floating-badge');
  badges.forEach(badge => {
    const text = badge.textContent;
    badge.innerHTML = `<span>${text}</span>`;
  });
});
</script>

<div class="container">
  <!-- CYBERIA Header -->
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
    <a href="/about/me" class="holo-card">
      <h3>À PROPOS</h3>
      <p>Mon parcours, passions et motivation dans la cybersécurité</p>
    </a>
    
   <a href="/fssm/" class="holo-card">
      <h3>FSSM</h3>
      <p>Formation académique, projets et compétences acquises</p>
    </a>
    
   <a href="/tryhackme/" class="holo-card">
      <h3>TRYHACKME</h3>
      <p>Paths complétés, badges et write-ups de challenges</p>
    </a>
    
  <a href="/my-lab/" class="holo-card">
      <h3>MON LAB</h3>
      <p>Environnement de test, machines virtuelles et expériences</p>
   </a>
  </div>

  <div class="welcome-text">
    <div class="welcome-lain-container">
      <img src="/assets/images/li.png" 
           alt="Lain at her Navi" 
           class="welcome-lain-image">
    </div>
    <div class="welcome-text-content">
      <p>Salut — je suis <strong style="color: #3b82f6;">Haname</strong>, étudiante en cybersécurité à la FSSM.<br>
      Bienvenue sur mon site où je partage mon parcours, mes parcours (paths) TryHackMe, la formation FSSM, et mes laboratoires personnels.</p>
    </div>
  </div>

  <!-- BIG SISTER COUNTER ENHANCED -->
  <div class="counter-container">
    <div class="counter-box">
      <div class="lain-image-container">
        <img src="/assets/images/watch.png" 
             alt="Lain watching" 
             class="lain-image">
        <div class="eye-overlay"></div>
      </div>
      
   <div class="counter-content">
        <div class="counter-label">
          <span class="eye-icon">👁️</span>
          <span>Big Sister is watching</span>
        </div>
        <div class="counter-number" id="visitorCount">0</div>
        <div class="counter-subtitle">visitors observed</div>
      </div>
    </div>
  </div>

  <script>
    let visits = parseInt(localStorage.getItem('cyberiaVisits') || '0');
    visits++;
    localStorage.setItem('cyberiaVisits', visits);
    document.getElementById('visitorCount').textContent = visits;
  </script>

  <div class="badge-container">
    <a href="/tryhackme/" class="floating-badge">TRYHACKME</a>
    <a href="https://github.com/ItsHaname" class="floating-badge" target="_blank">GITHUB</a>
    <a href="#" class="floating-badge">TWITTER</a>
    <a href="#" class="floating-badge">LINKEDIN</a>
  </div>

  <div class="cyber-footer">
    © 2025 CYBERIA — HANAME — FSSM — Personal Knowledge Repository
  </div>
</div
