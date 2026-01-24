---
layout: default
title: VulHub CVE
nav: vulhub
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

@keyframes slideIn {
  from { opacity: 0; transform: translateY(-20px); }
  to { opacity: 1; transform: translateY(0); }
}

@keyframes gradientBG {
  0% { background-position: 0% 50%; }
  50% { background-position: 100% 50%; }
  100% { background-position: 0% 50%; }
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

.back-link {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  color: #60a5fa;
  text-decoration: none;
  font-weight: 600;
  margin-bottom: 40px;
  padding: 10px 20px;
  background: rgba(15, 23, 42, 0.85);
  border: 1px solid rgba(59, 130, 246, 0.3);
  border-radius: 10px;
  transition: all 0.3s;
}

.back-link:hover {
  border-color: #60a5fa;
  transform: translateX(-5px);
}

.vulhub-header {
  text-align: center;
  margin-bottom: 60px;
  animation: slideIn 0.8s ease-out;
}

.vulhub-logo {
  width: 180px;
  height: auto;
  margin-bottom: 20px;
  filter: drop-shadow(0 0 20px rgba(59, 130, 246, 0.4));
  animation: floatUpDown 3s ease-in-out infinite;
}

.vulhub-title {
  font-size: 3em;
  color: transparent;
  background: linear-gradient(90deg, #3b82f6, #60a5fa, #2563eb);
  background-size: 200% auto;
  -webkit-background-clip: text;
  background-clip: text;
  animation: gradientBG 3s ease infinite;
  margin: 10px 0;
  font-weight: 900;
  letter-spacing: 2px;
}

.vulhub-subtitle {
  font-size: 1.2em;
  color: #94a3b8;
  font-style: italic;
}

.intro-section {
  background: rgba(15, 23, 42, 0.85);
  border: 1px solid rgba(59, 130, 246, 0.3);
  border-radius: 15px;
  padding: 30px;
  margin-bottom: 50px;
  border-left: 4px solid #3b82f6;
}

.intro-section h2 {
  color: #60a5fa;
  margin-bottom: 20px;
  font-size: 1.6em;
}

.intro-section p {
  color: #cbd5e1;
  line-height: 1.8;
  margin-bottom: 15px;
}

.intro-section .highlight {
  color: #fbbf24;
  font-weight: 600;
}

.cve-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
  gap: 30px;
  margin-top: 40px;
}

.cve-card {
  background: rgba(15, 23, 42, 0.85);
  border: 1px solid rgba(71, 85, 105, 0.5);
  border-radius: 15px;
  padding: 30px;
  transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
  position: relative;
  overflow: hidden;
  cursor: pointer;
  text-decoration: none;
  color: inherit;
  display: block;
}

.cve-card::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 3px;
  background: linear-gradient(90deg, #3b82f6, #60a5fa, #2563eb);
  transform: scaleX(0);
  transition: transform 0.3s ease;
}

.cve-card:hover::before {
  transform: scaleX(1);
}

.cve-card:hover {
  border-color: rgba(96, 165, 250, 0.8);
  transform: translateY(-8px);
  box-shadow: 0 20px 40px rgba(59, 130, 246, 0.3);
}

.cve-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
}

.cve-id {
  font-family: 'Courier New', monospace;
  color: #60a5fa;
  background: rgba(59, 130, 246, 0.15);
  padding: 6px 12px;
  border-radius: 6px;
  font-size: 0.9em;
  font-weight: 700;
  border: 1px solid rgba(59, 130, 246, 0.3);
}

.severity {
  padding: 6px 16px;
  border-radius: 20px;
  font-size: 0.75em;
  font-weight: 800;
  text-transform: uppercase;
  letter-spacing: 1px;
}

.severity.critical {
  background: linear-gradient(135deg, #dc2626, #ef4444);
  color: white;
}

.severity.high {
  background: linear-gradient(135deg, #f59e0b, #fbbf24);
  color: #1e293b;
}

.severity.medium {
  background: linear-gradient(135deg, #eab308, #facc15);
  color: #1e293b;
}

.cve-card h3 {
  color: #f1f5f9;
  font-size: 1.4em;
  margin-bottom: 15px;
  font-weight: 700;
}

.cve-description {
  color: #cbd5e1;
  line-height: 1.7;
  margin-bottom: 20px;
}

.cve-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
  margin-bottom: 15px;
}

.tag {
  background: rgba(59, 130, 246, 0.15);
  border: 1px solid rgba(59, 130, 246, 0.4);
  color: #93c5fd;
  padding: 4px 12px;
  border-radius: 12px;
  font-size: 0.85em;
  font-weight: 600;
}

.view-details {
  display: inline-flex;
  align-items: center;
  gap: 6px;
  color: #60a5fa;
  font-size: 0.95em;
  font-weight: 600;
  margin-top: 10px;
  transition: all 0.3s;
}

.cve-card:hover .view-details {
  gap: 10px;
  color: #93c5fd;
}

.coming-soon {
  opacity: 0.7;
  border-style: dashed !important;
  cursor: default;
}

.contact-box {
  background: rgba(15, 23, 42, 0.85);
  border: 1px solid rgba(59, 130, 246, 0.3);
  border-radius: 15px;
  padding: 30px;
  margin-top: 50px;
  text-align: center;
}

.contact-box h3 {
  color: #60a5fa;
  margin-bottom: 15px;
  font-size: 1.4em;
}

.contact-box p {
  color: #cbd5e1;
  margin-bottom: 20px;
  line-height: 1.6;
}

.discord-link {
  display: inline-block;
  background: rgba(59, 130, 246, 0.2);
  border: 2px solid #3b82f6;
  color: #60a5fa;
  padding: 12px 30px;
  border-radius: 10px;
  text-decoration: none;
  font-weight: 600;
  transition: all 0.3s;
}

.discord-link:hover {
  background: rgba(59, 130, 246, 0.4);
  border-color: #60a5fa;
  transform: translateY(-2px);
  box-shadow: 0 10px 20px rgba(59, 130, 246, 0.3);
}

@media (max-width: 768px) {
  .vulhub-title {
    font-size: 2em;
  }
  
  .cve-grid {
    grid-template-columns: 1fr;
  }
  
  .vulhub-logo {
    width: 140px;
  }
}
</style>

<script>
document.addEventListener('DOMContentLoaded', function() {
  const binaryContainer = document.createElement('div');
  binaryContainer.className = 'binary-background';
  document.body.appendChild(binaryContainer);
  
  for (let i = 0; i < 80; i++) {
    const digit = document.createElement('div');
    digit.className = 'binary-digit';
    digit.textContent = Math.random() > 0.5 ? '1' : '0';
    
    digit.style.left = Math.random() * 100 + 'vw';
    const size = Math.random() * 18 + 12;
    digit.style.fontSize = size + 'px';
    const duration = Math.random() * 10 + 5;
    const delay = Math.random() * 5;
    digit.style.animationDuration = duration + 's';
    digit.style.animationDelay = delay + 's';
    digit.style.opacity = Math.random() * 0.2 + 0.05;
    
    const colors = [
      'rgba(59, 130, 246, 0.15)',
      'rgba(96, 165, 250, 0.15)',
      'rgba(37, 99, 235, 0.15)'
    ];
    digit.style.color = colors[Math.floor(Math.random() * colors.length)];
    
    binaryContainer.appendChild(digit);
  }
  
  for (let i = 0; i < 25; i++) {
    const floatDigit = document.createElement('div');
    floatDigit.className = 'binary-digit float';
    floatDigit.textContent = Math.random() > 0.5 ? '1' : '0';
    
    floatDigit.style.left = Math.random() * 100 + 'vw';
    floatDigit.style.top = Math.random() * 100 + 'vh';
    const floatSize = Math.random() * 22 + 14;
    floatDigit.style.fontSize = floatSize + 'px';
    floatDigit.style.animationDelay = Math.random() * 2 + 's';
    floatDigit.style.opacity = Math.random() * 0.3 + 0.1;
    
    const floatColors = [
      'rgba(59, 130, 246, 0.25)',
      'rgba(96, 165, 250, 0.25)',
      'rgba(37, 99, 235, 0.25)'
    ];
    floatDigit.style.color = floatColors[Math.floor(Math.random() * floatColors.length)];
    
    binaryContainer.appendChild(floatDigit);
  }
});
</script>

<div class="container">
  <a href="/my-lab/" class="back-link">
    <span>←</span>
    <span>Back to Lab</span>
  </a>

  <div class="vulhub-header">
    <img src="/assets/images/vulhub.png" alt="VulHub" class="vulhub-logo">
    <h1 class="vulhub-title">CVE Adventures</h1>
    <p class="vulhub-subtitle">breaking things & learning stuff</p>
  </div>

  <div class="intro-section">
    <h2>What's this about?</h2>
    <p>
      I'm diving into CVEs from GitHub and trying my own solutions <span class="highlight">(when they work)</span>. 
      This is my collection of notes and findings from vulnerability research.
    </p>
    <p>
      Each CVE here is something I've actually tested and documented. 
      No fancy writeups, just practical notes on what works, what doesn't, and what I learned.
    </p>
    <p>
      <strong>Note:</strong> These are learning experiments. Only use in authorized lab environments.
    </p>
  </div>

  <div class="cve-grid">
    <!-- NotPetya - Add your Canva link in the href -->
    <a href="YOUR_CANVA_LINK_HERE" target="_blank" class="cve-card">
      <div class="cve-header">
        <span class="cve-id">CVE-2017-7494 </span>
        <span class="severity critical">Critical</span>
      </div>
      <h3>SambaCry</h3>
      <div class="cve-description">
        C'est une vulnérabilité d'exécution de code à distance (RCE) dans Samba (service de partage de fichiers Linux/UNIX). Elle permet à un attaquant de télécharger et exécuter du code arbitraire sur le serveur Samba.
      </div>
      <div class="view-details">
        View Full Analysis →
      </div>
    </a>

    <!-- Coming Soon 1 -->
  <div class="cve-card coming-soon">
      <div class="cve-header">
        <span class="cve-id">CVE-????-????</span>
        <span class="severity high">High</span>
      </div>
      <h3>Next Research Target</h3>
      <div class="cve-description">
        Currently researching new vulnerabilities in the lab. 
        More documentation coming soon with detailed analysis and testing results.
      </div>
      <div class="cve-tags">
        <span class="tag">In Progress</span>
        <span class="tag">Research</span>
        <span class="tag">Testing</span>
      </div>
    </div>

    <!-- Coming Soon 2 -->
  <div class="cve-card coming-soon">
      <div class="cve-header">
        <span class="cve-id">CVE-????-????</span>
        <span class="severity medium">Medium</span>
      </div>
      <h3>Additional Research</h3>
      <div class="cve-description">
        Planning to explore more interesting vulnerabilities. 
        Each addition will include testing methodology and practical findings.
      </div>
      <div class="cve-tags">
        <span class="tag">Planned</span>
        <span class="tag">Queue</span>
      </div>
    </div>
  </div>
</div>
