<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>My Lab - CYBERIA</title>
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
@keyframes blink {
  0%, 100% { opacity: 1; }
  50% { opacity: 0; }
}
body {
  background: #0a0e1a;
  min-height: 100vh;
  margin: 0;
  position: relative;
  overflow-x: hidden;
  font-family: 'Courier New', monospace;
  color: #e2e8f0;
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

/* Header */
.page-header {
  text-align: center;
  margin-bottom: 60px;
  padding: 40px 20px;
  background: rgba(0, 20, 40, 0.6);
  border-radius: 30px;
  border: 3px solid #1e4d7b;
  box-shadow: 0 0 40px rgba(30, 77, 123, 0.5);
}
.page-title {
  font-size: 4em;
  color: #60a5fa;
  text-shadow: 
    0 0 10px #60a5fa,
    0 0 20px #3b82f6,
    0 0 30px #2563eb;
  margin: 0;
  font-weight: 900;
  letter-spacing: 8px;
  text-transform: uppercase;
}
.page-subtitle {
  font-size: 1.5em;
  color: #94a3b8;
  margin: 15px 0 0 0;
  font-style: italic;
}
.page-subtitle::after {
  content: '_';
  animation: blink 1s infinite;
  color: #60a5fa;
}

/* Terminal Box */
.terminal-box {
  background: #0f1419;
  border: 2px solid #2d3748;
  border-radius: 10px;
  padding: 20px;
  margin: 40px 0;
  font-family: 'Courier New', monospace;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
}
.terminal-header {
  display: flex;
  gap: 8px;
  margin-bottom: 15px;
}
.terminal-dot {
  width: 12px;
  height: 12px;
  border-radius: 50%;
}
.terminal-dot.red { background: #ff5f56; }
.terminal-dot.yellow { background: #ffbd2e; }
.terminal-dot.green { background: #27c93f; }
.terminal-content {
  color: #00ff00;
  font-size: 0.95em;
  line-height: 1.8;
}
.terminal-prompt {
  color: #60a5fa;
}
.terminal-comment {
  color: #64748b;
}

/* Infrastructure Section */
.section-title {
  text-align: center;
  font-size: 2em;
  color: #60a5fa;
  margin: 60px 0 40px 0;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 15px;
}
.section-title::before,
.section-title::after {
  content: '';
  height: 2px;
  width: 100px;
  background: linear-gradient(90deg, transparent, #3b82f6, transparent);
}

/* Lab Cards Grid */
.lab-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 30px;
  margin: 40px 0;
}
.lab-card {
  background: rgba(15, 23, 42, 0.85);
  border: 1px solid rgba(59, 130, 246, 0.3);
  border-radius: 15px;
  padding: 30px;
  text-align: center;
  text-decoration: none;
  color: inherit;
  display: block;
  transition: all 0.3s ease;
}
.lab-card:hover {
  border-color: #60a5fa;
  box-shadow: 0 10px 30px rgba(59, 130, 246, 0.3);
  transform: translateY(-5px);
}
.lab-icon {
  width: 120px;
  height: 120px;
  margin: 0 auto 20px;
  display: flex;
  align-items: center;
  justify-content: center;
  background: rgba(30, 41, 59, 0.5);
  border-radius: 15px;
  border: 2px solid rgba(59, 130, 246, 0.3);
}
.lab-icon img {
  width: 100px;
  height: 100px;
  object-fit: contain;
}
.lab-card h3 {
  color: #3b82f6;
  margin: 15px 0 10px 0;
  font-size: 1.5em;
  font-weight: 600;
}
.lab-card p {
  color: #cbd5e1;
  margin: 0;
  line-height: 1.6;
  font-size: 0.95em;
}

/* Construction Banner */
.construction-banner {
  background: rgba(30, 41, 59, 0.6);
  border: 2px dashed rgba(59, 130, 246, 0.5);
  border-radius: 15px;
  padding: 30px;
  text-align: center;
  margin: 60px 0;
}
.construction-banner h3 {
  color: #60a5fa;
  font-size: 1.8em;
  margin: 0 0 15px 0;
}
.construction-banner p {
  color: #94a3b8;
  margin: 10px 0;
  line-height: 1.6;
}

/* Footer */
.cyber-footer {
  text-align: center;
  margin-top: 80px;
  padding-top: 30px;
  border-top: 1px solid rgba(59, 130, 246, 0.3);
  color: #64748b;
  font-size: 0.9em;
}

@media (max-width: 768px) {
  .page-title {
    font-size: 2.5em;
    letter-spacing: 4px;
  }
  .page-subtitle {
    font-size: 1.2em;
  }
  .section-title {
    font-size: 1.5em;
  }
  .section-title::before,
  .section-title::after {
    width: 50px;
  }
  .lab-grid {
    grid-template-columns: 1fr;
  }
}
</style>
</head>
<body>

<div class="binary-background" id="binaryBG"></div>

<div class="container">
  <!-- Header -->
  <div class="page-header">
    <h1 class="page-title">HOME LAB SETUP</h1>
    <p class="page-subtitle">Raspberry Pi • Docker • Arch Linux</p>
  </div>

  <!-- Terminal Box -->
  <div class="terminal-box">
    <div class="terminal-header">
      <div class="terminal-dot red"></div>
      <div class="terminal-dot yellow"></div>
      <div class="terminal-dot green"></div>
    </div>
    <div class="terminal-content">
<span class="terminal-prompt">haname@homelab:~$</span> cat lab_overview.txt<br>
<span class="terminal-comment">- Infrastructure: Raspberry Pi 4 + Docker Containers + Arch Linux VMs</span><br>
<span class="terminal-comment">- Objectif: Reconnaissance, Exploitation, Post-Exploitation, Persistence</span><br>
<span class="terminal-comment">- Reseau: 10.10.10.0/24 (Lab Network)</span><br>
<span class="terminal-comment">- Status: Building...</span>
    </div>
  </div>

  <!-- Infrastructure Section -->
  <h2 class="section-title">💻 Infrastructure</h2>

  <div class="lab-grid">
    <!-- Raspberry Pi -->
    <a href="/my-lab/pi" class="lab-card">
      <div class="lab-icon">
        <img src="/assets/images/pi.png" alt="Raspberry Pi">
      </div>
      <h3>Raspberry Pi</h3>
      <p>Serveur principal du lab, héberge les containers Docker et services réseau</p>
    </a>

    <!-- Docker -->
    <a href="/my-lab/dockerlab" class="lab-card">
      <div class="lab-icon">
        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/docker/docker-original.svg" alt="Docker">
      </div>
      <h3>Docker Containers</h3>
      <p>Environnements isolés pour tests et déploiement d'applications vulnérables</p>
    </a>

    <!-- Arch Linux -->
    <a href="/my-lab/archlinux" class="lab-card">
      <div class="lab-icon">
        <img src="/assets/images/arch-mascot.png" alt="Arch Linux">
      </div>
      <h3>Arch Linux</h3>
      <p>Machines virtuelles pour pentesting et développement d'outils</p>
    </a>

    <!-- VulHub -->
    <a href="/my-lab/vulhub_cve" class="lab-card">
      <div class="lab-icon">
        <img src="/assets/images/vulhub.png" alt="VulHub">
      </div>
      <h3>VulHub CVE</h3>
      <p>Environnements Docker pour exploitation de CVE réels</p>
    </a>

    <!-- Other Labs -->
    <a href="/my-lab/other_lab" class="lab-card">
      <div class="lab-icon">
        <img src="/assets/images/otherlab.png" alt="Other Labs">
      </div>
      <h3>Other Labs</h3>
      <p>Projets expérimentaux et environnements de test additionnels</p>
    </a>
  </div>

  <!-- Construction Banner -->
  <div class="construction-banner">
    <h3>Lab en Construction</h3>
    <p>Les machines, challenges et write-ups seront ajoutés progressivement.</p>
    <p>Documentation technique et notes pratiques à venir...</p>
  </div>

  <!-- Footer -->
  <div class="cyber-footer">
    <a href="/" style="color: #60a5fa; text-decoration: none;">← Retour à l'accueil</a><br><br>
    © 2025 CYBERIA — HANAME — Home Lab Setup
  </div>
</div>

<script>
// Create binary rain background
document.addEventListener('DOMContentLoaded', function() {
  const binaryContainer = document.getElementById('binaryBG');

  // Falling binary digits
  for (let i = 0; i < 80; i++) {
    const digit = document.createElement('div');
    digit.className = 'binary-digit';
    digit.textContent = Math.random() > 0.5 ? '1' : '0';
    digit.style.left = Math.random() * 100 + 'vw';
    digit.style.fontSize = (Math.random() * 18 + 12) + 'px';
    digit.style.animationDuration = (Math.random() * 10 + 5) + 's';
    digit.style.animationDelay = (Math.random() * 5) + 's';
    digit.style.opacity = Math.random() * 0.2 + 0.05;
    const colors = ['rgba(59, 130, 246, 0.15)', 'rgba(96, 165, 250, 0.15)', 'rgba(37, 99, 235, 0.15)'];
    digit.style.color = colors[Math.floor(Math.random() * colors.length)];
    binaryContainer.appendChild(digit);
  }

  // Floating binary digits
  for (let i = 0; i < 25; i++) {
    const floatDigit = document.createElement('div');
    floatDigit.className = 'binary-digit float';
    floatDigit.textContent = Math.random() > 0.5 ? '1' : '0';
    floatDigit.style.left = Math.random() * 100 + 'vw';
    floatDigit.style.top = Math.random() * 100 + 'vh';
    floatDigit.style.fontSize = (Math.random() * 22 + 14) + 'px';
    floatDigit.style.animationDelay = (Math.random() * 2) + 's';
    floatDigit.style.opacity = Math.random() * 0.3 + 0.1;
    const floatColors = ['rgba(59, 130, 246, 0.25)', 'rgba(96, 165, 250, 0.25)', 'rgba(37, 99, 235, 0.25)'];
    floatDigit.style.color = floatColors[Math.floor(Math.random() * floatColors.length)];
    binaryContainer.appendChild(floatDigit);
  }
});
</script>

</body>
</html>
