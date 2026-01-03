---
layout: default
title: Parcours FSSM
nav: fssm
---

<style>
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
  0%, 100% { transform: scale(1); box-shadow: 0 0 20px rgba(59, 130, 246, 0.3); }
  50% { transform: scale(1.05); box-shadow: 0 0 40px rgba(59, 130, 246, 0.6); }
}

@keyframes blink {
  0%, 100% { opacity: 1; }
  50% { opacity: 0; }
}

@keyframes float {
  0%, 100% { transform: translateY(0px); }
  50% { transform: translateY(-15px); }
}

@keyframes glow {
  0%, 100% { text-shadow: 0 0 10px #60a5fa, 0 0 20px #3b82f6; }
  50% { text-shadow: 0 0 20px #60a5fa, 0 0 40px #3b82f6, 0 0 60px #2563eb; }
}

@keyframes rotate3d {
  from { transform: rotateY(0deg); }
  to { transform: rotateY(360deg); }
}

.fssm-container {
  position: relative;
  overflow: hidden;
}

/* Particles background */
.particles {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  pointer-events: none;
  z-index: -1;
  opacity: 0.4;
}

.particle {
  position: absolute;
  width: 3px;
  height: 3px;
  background: #3b82f6;
  border-radius: 50%;
  animation: float 4s infinite ease-in-out;
}

.fssm-hero {
  text-align: center;
  margin-bottom: 80px;
  padding: 60px 20px;
  background: linear-gradient(135deg, rgba(0, 20, 40, 0.9), rgba(15, 23, 42, 0.8));
  border-radius: 30px;
  border: 3px solid transparent;
  background-clip: padding-box;
  position: relative;
  overflow: hidden;
}

.fssm-hero::before {
  content: '';
  position: absolute;
  top: -3px;
  left: -3px;
  right: -3px;
  bottom: -3px;
  background: linear-gradient(45deg, #3b82f6, #60a5fa, #2563eb, #1e40af);
  background-size: 300% 300%;
  animation: gradientBG 4s ease infinite;
  border-radius: 30px;
  z-index: -1;
}

.semester-badge {
  display: inline-block;
  padding: 15px 40px;
  background: linear-gradient(135deg, #ff6b4a, #ff3300);
  color: white;
  font-size: 1.8em;
  font-weight: 900;
  border-radius: 50px;
  margin-bottom: 30px;
  box-shadow: 0 10px 30px rgba(255, 107, 74, 0.5);
  animation: pulse 3s infinite;
  letter-spacing: 3px;
}

.fssm-title {
  font-size: 4em;
  color: transparent;
  background: linear-gradient(90deg, #3b82f6, #60a5fa, #2563eb, #60a5fa, #3b82f6);
  background-size: 300% auto;
  -webkit-background-clip: text;
  background-clip: text;
  animation: gradientBG 3s ease infinite, glow 2s ease-in-out infinite;
  margin: 30px 0;
  font-weight: 900;
  letter-spacing: 5px;
  text-transform: uppercase;
}

.fssm-subtitle {
  font-size: 1.5em;
  color: #60a5fa;
  margin: 20px 0;
  font-style: italic;
  letter-spacing: 2px;
}

.fssm-subtitle::after {
  content: '_';
  animation: blink 1s infinite;
  color: #ff6b4a;
}

.university-name {
  font-size: 1.2em;
  color: #94a3b8;
  margin-top: 20px;
  text-transform: uppercase;
  letter-spacing: 2px;
}

.terminal-section {
  background: rgba(10, 14, 26, 0.95);
  border: 2px solid #3b82f6;
  border-radius: 15px;
  padding: 25px;
  margin: 40px 0;
  font-family: 'Courier New', monospace;
  box-shadow: 0 0 30px rgba(59, 130, 246, 0.3);
}

.terminal-header {
  display: flex;
  gap: 8px;
  margin-bottom: 20px;
}

.terminal-dot {
  width: 12px;
  height: 12px;
  border-radius: 50%;
}

.terminal-dot.red { background: #ff5f56; }
.terminal-dot.yellow { background: #ffbd2e; }
.terminal-dot.green { background: #27c93f; }

.terminal-text {
  color: #60a5fa;
  line-height: 2;
}

.terminal-text .prompt {
  color: #ff6b4a;
  font-weight: bold;
}

.terminal-text .command {
  color: #3b82f6;
}

.modules-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
  gap: 30px;
  margin: 60px 0;
  perspective: 1000px;
}

.module-card {
  background: linear-gradient(135deg, rgba(15, 23, 42, 0.9), rgba(30, 41, 59, 0.8));
  border: 2px solid transparent;
  border-radius: 20px;
  padding: 35px;
  transition: all 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
  position: relative;
  text-decoration: none;
  color: inherit;
  display: block;
  animation: slideIn 0.8s ease-out backwards;
  transform-style: preserve-3d;
  overflow: hidden;
}

.module-card::before {
  content: '';
  position: absolute;
  top: -2px;
  left: -2px;
  right: -2px;
  bottom: -2px;
  background: linear-gradient(45deg, #3b82f6, #60a5fa, #2563eb, #1e40af);
  background-size: 300% 300%;
  animation: gradientBG 6s ease infinite;
  border-radius: 20px;
  z-index: -1;
  opacity: 0;
  transition: opacity 0.5s;
}

.module-card:hover::before {
  opacity: 1;
}

.module-card::after {
  content: '';
  position: absolute;
  top: 50%;
  left: 50%;
  width: 0;
  height: 0;
  border-radius: 50%;
  background: rgba(96, 165, 250, 0.3);
  transform: translate(-50%, -50%);
  transition: width 0.6s, height 0.6s;
}

.module-card:hover::after {
  width: 500px;
  height: 500px;
}

.module-card:hover {
  transform: translateY(-15px) rotateX(5deg) rotateY(5deg);
  box-shadow: 0 25px 60px rgba(59, 130, 246, 0.6);
}

.module-card:nth-child(1) { animation-delay: 0.1s; }
.module-card:nth-child(2) { animation-delay: 0.2s; }
.module-card:nth-child(3) { animation-delay: 0.3s; }
.module-card:nth-child(4) { animation-delay: 0.4s; }
.module-card:nth-child(5) { animation-delay: 0.5s; }

.module-icon {
  font-size: 3em;
  margin-bottom: 20px;
  display: inline-block;
  animation: float 3s ease-in-out infinite;
  filter: drop-shadow(0 0 15px currentColor);
}

.module-number {
  position: absolute;
  top: 20px;
  right: 20px;
  background: rgba(59, 130, 246, 0.2);
  color: #60a5fa;
  padding: 10px 18px;
  border-radius: 25px;
  font-size: 0.85em;
  font-weight: 900;
  border: 1px solid #3b82f6;
  box-shadow: 0 0 15px rgba(59, 130, 246, 0.4);
  z-index: 1;
}

.module-card h3 {
  color: #60a5fa;
  margin: 20px 0;
  font-size: 1.8em;
  font-weight: 700;
  position: relative;
  z-index: 1;
  text-shadow: 0 0 10px rgba(96, 165, 250, 0.5);
}

.module-status {
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
  position: relative;
  z-index: 1;
}

.status-dot {
  width: 8px;
  height: 8px;
  background: #3b82f6;
  border-radius: 50%;
  animation: pulse 2s infinite;
}

.coming-soon {
  text-align: center;
  padding: 60px 20px;
  background: linear-gradient(135deg, rgba(255, 107, 74, 0.1), rgba(59, 130, 246, 0.1));
  border-radius: 20px;
  border: 2px dashed #3b82f6;
  margin: 50px 0;
}

.coming-soon h2 {
  color: #ff6b4a;
  font-size: 2.5em;
  margin-bottom: 20px;
  animation: glow 2s ease-in-out infinite;
}

.coming-soon p {
  color: #94a3b8;
  font-size: 1.2em;
}

@media (max-width: 768px) {
  .fssm-title {
    font-size: 2.5em;
  }
  
  .semester-badge {
    font-size: 1.3em;
    padding: 12px 30px;
  }
  
  .modules-grid {
    grid-template-columns: 1fr;
  }
  
  .module-card:hover {
    transform: translateY(-10px);
  }
}
</style>

<div class="fssm-container">

<div class="fssm-hero">
  <div class="semester-badge">S6</div>
  <div class="fssm-title">Formation FSSM</div>
  <div class="fssm-subtitle">Cybersecurity & Network Engineering</div>
  <div class="university-name">Faculté des Sciences Semlalia • Marrakech</div>
</div>

<div class="terminal-section">
  <div class="terminal-header">
    <div class="terminal-dot red"></div>
    <div class="terminal-dot yellow"></div>
    <div class="terminal-dot green"></div>
  </div>
  <div class="terminal-text">
    <span class="prompt">haname@fssm:~$</span> <span class="command">cat semester_info.txt</span><br>
    → Semestre: S6 (Janvier - Juin 2025)<br>
    → Spécialisation: Cybersécurité & Réseaux<br>
    → Modules: 5 modules avancés<br>
    → Status: En cours...<span style="animation: blink 1s infinite;">_</span>
  </div>
</div>

<h2 style="color: #60a5fa; text-align: center; margin: 60px 0 40px 0; font-size: 2.5em; text-shadow: 0 0 20px rgba(96, 165, 250, 0.5);">
  📚 Modules S6
</h2>

<div class="modules-grid">
  
  <a href="/fssm/iot-analyse-connexion" class="module-card">
    <span class="module-number">M1</span>
    <div class="module-icon">🌐</div>
    <h3>IoT Analyse et Connexion</h3>
    <div class="module-status">
      <span class="status-dot"></span>
      En cours
    </div>
  </a>

  <a href="/fssm/parallelisme-programmation-reseaux" class="module-card">
    <span class="module-number">M2</span>
    <div class="module-icon">⚡</div>
    <h3>Parallélisme et Programmation Réseaux</h3>
    <div class="module-status">
      <span class="status-dot"></span>
      En cours
    </div>
  </a>

  <a href="/fssm/droit-digital" class="module-card">
    <span class="module-number">M3</span>
    <div class="module-icon">⚖️</div>
    <h3>Droit Digital</h3>
    <div class="module-status">
      <span class="status-dot"></span>
      En cours
    </div>
  </a>

  <a href="/fssm/gouvernance-securite" class="module-card">
    <span class="module-number">M4</span>
    <div class="module-icon">🛡️</div>
    <h3>Gouvernance de la Sécurité</h3>
    <div class="module-status">
      <span class="status-dot"></span>
      En cours
    </div>
  </a>

  <a href="/fssm/cryptographie-cybersecurite" class="module-card">
    <span class="module-number">M5</span>
    <div class="module-icon">🔐</div>
    <h3>Cryptographie et Cybersécurité</h3>
    <div class="module-status">
      <span class="status-dot"></span>
      En cours
    </div>
  </a>

</div>

<div class="coming-soon">
  <h2>🚀 Notes & Projets</h2>
  <p>Le contenu détaillé de chaque module sera ajouté au fur et à mesure du semestre.</p>
  <p style="margin-top: 15px; color: #60a5fa;">Stay tuned for updates...</p>
</div>

<div style="text-align: center; margin-top: 80px; padding: 40px; background: linear-gradient(135deg, rgba(15, 23, 42, 0.8), rgba(0, 20, 40, 0.9)); border-radius: 20px; border: 2px solid #1e4d7b;">
  <p style="color: #94a3b8; font-size: 1.1em; line-height: 1.8;">
    🎓 Année académique <span style="color: #60a5fa; font-weight: bold;">2024-2025</span><br>
    📍 FSSM - Faculté des Sciences Semlalia, Marrakech<br>
    💼 Spécialité: <span style="color: #3b82f6; font-weight: bold;">Cybersécurité & Ingénierie Réseau</span>
  </p>
</div>

</div>

<script>
// Create animated particles
document.addEventListener('DOMContentLoaded', function() {
  const container = document.querySelector('.fssm-container');
  const particlesDiv = document.createElement('div');
  particlesDiv.className = 'particles';
  container.insertBefore(particlesDiv, container.firstChild);
  
  for (let i = 0; i < 30; i++) {
    const particle = document.createElement('div');
    particle.className = 'particle';
    particle.style.left = Math.random() * 100 + '%';
    particle.style.top = Math.random() * 100 + '%';
    particle.style.animationDelay = Math.random() * 4 + 's';
    particle.style.animationDuration = (Math.random() * 3 + 3) + 's';
    particlesDiv.appendChild(particle);
  }
});
</script>
