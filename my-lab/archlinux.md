---
layout: default
title: Arch Linux Setup
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
  padding: 40px 20px;
  background: rgba(0, 20, 40, 0.6);
  border-radius: 30px;
  border: 3px solid #1e4d7b;
  box-shadow: 0 0 40px rgba(30, 77, 123, 0.5), inset 0 0 30px rgba(30, 77, 123, 0.2);
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

.intro-box {
  background: rgba(15, 23, 42, 0.85);
  border: 1px solid rgba(59, 130, 246, 0.3);
  border-radius: 15px;
  padding: 30px;
  margin-bottom: 40px;
  border-left: 4px solid #3b82f6;
}

.intro-box p {
  color: #cbd5e1;
  line-height: 1.8;
  font-size: 1.1em;
  margin: 0;
}

.intro-box strong {
  color: #60a5fa;
}

.intro-box a {
  color: #3b82f6;
  text-decoration: none;
  border-bottom: 2px solid rgba(59, 130, 246, 0.3);
  transition: all 0.3s;
}

.intro-box a:hover {
  color: #60a5fa;
  border-bottom-color: #60a5fa;
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

.resources-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
  gap: 25px;
  margin: 40px 0;
}

.resource-card {
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

.resource-card:before {
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

.resource-card:hover:before {
  opacity: 0.5;
}

.resource-card:hover {
  transform: translateY(-10px) scale(1.02);
  border-color: #60a5fa;
  box-shadow: 0 15px 35px rgba(59, 130, 246, 0.3);
}

.resource-number {
  display: inline-block;
  width: 50px;
  height: 50px;
  background: linear-gradient(135deg, #3b82f6, #2563eb);
  color: white;
  font-size: 1.5em;
  font-weight: 900;
  border-radius: 50%;
  text-align: center;
  line-height: 50px;
  margin-bottom: 20px;
  box-shadow: 0 5px 15px rgba(59, 130, 246, 0.4);
}

.resource-card h3 {
  color: #3b82f6;
  font-size: 1.6em;
  margin: 0 0 15px 0;
  font-weight: 600;
}

.resource-card p {
  color: #cbd5e1;
  line-height: 1.6;
  margin: 0 0 15px 0;
}

.resource-link {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  color: #60a5fa;
  text-decoration: none;
  font-weight: 500;
  transition: all 0.3s;
}

.resource-link:hover {
  color: #3b82f6;
  gap: 12px;
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

.status-badge.done {
  background: rgba(16, 185, 129, 0.15);
  border-color: rgba(16, 185, 129, 0.3);
  color: #10b981;
}

.status-dot {
  width: 8px;
  height: 8px;
  background: #3b82f6;
  border-radius: 50%;
  animation: pulse 2s infinite;
}

.status-dot.done {
  background: #10b981;
  animation: none;
}

.tips-section {
  background: rgba(15, 23, 42, 0.85);
  border: 1px solid rgba(59, 130, 246, 0.3);
  border-radius: 15px;
  padding: 30px;
  margin: 40px 0;
}

.tips-section h3 {
  color: #60a5fa;
  font-size: 1.8em;
  margin: 0 0 20px 0;
}

.tips-section ul {
  list-style: none;
  margin: 0;
  padding: 0;
}

.tips-section li {
  color: #cbd5e1;
  padding: 12px 0 12px 30px;
  position: relative;
  line-height: 1.6;
}

.tips-section li:before {
  content: "→";
  color: #3b82f6;
  font-weight: bold;
  position: absolute;
  left: 0;
}

.warning-box {
  background: rgba(255, 107, 74, 0.1);
  border: 2px solid rgba(255, 107, 74, 0.3);
  border-radius: 10px;
  padding: 20px;
  margin: 30px 0;
}

.warning-box h4 {
  color: #ff6b4a;
  margin: 0 0 10px 0;
  font-size: 1.3em;
}

.warning-box p {
  color: #cbd5e1;
  margin: 0;
  line-height: 1.6;
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
  
  .resources-grid {
    grid-template-columns: 1fr;
  }
}
</style>

<div class="binary-background"></div>

<div class="container">
  <div class="page-header">
    <h1 class="page-title">ARCH LINUX</h1>
    <p class="page-subtitle">Learning to be a stable user</p>
  </div>

  <div class="intro-box">
    <p>
      <strong>Hey!</strong> 👋 This is my documentation page where I track everything I learn about <strong>Arch Linux</strong>. 
      My goal? <strong>Not breaking my system</strong> while exploring and experimenting.<br><br>
      I'm currently running <strong>Arch Linux on dual boot</strong>, and I'm documenting every useful thing I discover along the way.
      If you're interested in installing Arch yourself, check out 
      <a href="https://gelules.github.io/linux/arch.html" target="_blank">this installation guide</a> — why not give it a try? 
    </p>
  </div>

  <div class="warning-box">
    <h4>⚠️ Learning & Experimenting</h4>
    <p>This page is my personal lab notebook. Things might break, commands might change, and mistakes will be made — but that's how we learn!</p>
  </div>

  <h2 class="section-title">Useful Resources & Guides</h2>

  <div class="resources-grid">
    <a href="{{ site.baseurl }}/my-lab/masterpass" class="resource-card">
      <div class="resource-number">1</div>
      <h3>Master Password Setup</h3>
      <p>Secure your system with a master password configuration for enhanced security and credential management.</p>
      <div class="status-badge done">
        <span class="status-dot done"></span>
        Done
      </div>
    </a>

  <a href="#" class="resource-card">
      <div class="resource-number">2</div>
      <h3>System Maintenance</h3>
      <p>Essential commands and practices to keep your Arch system healthy and running smoothly without breaking things.</p>
      <div class="status-badge">
        <span class="status-dot"></span>
        Coming soon
      </div>
    </a>

   <a href="#" class="resource-card">
      <div class="resource-number">3</div>
      <h3>Package Management</h3>
      <p>Pacman tips, AUR helpers, and best practices for installing and managing software safely on Arch.</p>
      <div class="status-badge">
        <span class="status-dot"></span>
        Coming soon
      </div>
    </a>

   <a href="#" class="resource-card">
      <div class="resource-number">4</div>
      <h3>Dual Boot Configuration</h3>
      <p>My setup and troubleshooting notes for running Arch alongside Windows without headaches.</p>
      <div class="status-badge">
        <span class="status-dot"></span>
        Coming soon
      </div>
    </a>

   <a href="#" class="resource-card">
      <div class="resource-number">5</div>
      <h3>Dotfiles & Customization</h3>
      <p>My configuration files, themes, and customizations to make Arch look and feel awesome.</p>
      <div class="status-badge">
        <span class="status-dot"></span>
        Coming soon
      </div>
    </a>

   <a href="#" class="resource-card">
      <div class="resource-number">6</div>
      <h3>Troubleshooting Tips</h3>
      <p>Common problems I've encountered and how I fixed them — saved me multiple times already!</p>
      <div class="status-badge">
        <span class="status-dot"></span>
        Coming soon
      </div>
    </a>
  </div>

  <div class="tips-section">
    <h3> Quick Tips I've Learned</h3>
    <ul>
      <li>Always read the Arch Wiki before installing anything</li>
      <li>Create snapshots before major system updates</li>
      <li>Test new configurations in a virtual machine first</li>
      <li>Keep a USB rescue disk handy for emergencies</li>
      <li>Document your custom configurations and changes</li>
      <li>Join the Arch community — they're super helpful!</li>
    </ul>
  </div>

  <div class="footer-nav">
    <a href="{{ site.baseurl }}/my-lab" class="nav-button">← Back to Lab</a>
    <a href="https://wiki.archlinux.org/" target="_blank" class="nav-button">Arch Wiki 📚</a>
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
