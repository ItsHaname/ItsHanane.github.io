---
layout: default
title: Accueil
nav: home
---

<style>
@keyframes slideIn {
  from { opacity: 0; transform: translateY(-20px); }
  to { opacity: 1; transform: translateY(0); }
}
@keyframes pulse {
  0% { transform: scale(1); }
  50% { transform: scale(1.05); }
  100% { transform: scale(1); }
}
@keyframes gradientBG {
  0% { background-position: 0% 50%; }
  50% { background-position: 100% 50%; }
  100% { background-position: 0% 50%; }
}
@keyframes typewriter {
  from { width: 0; }
  to { width: 100%; }
}
@keyframes blink {
  0%, 100% { border-color: transparent; }
  50% { border-color: #ea4aaa; }
}

.cyber-terminal {
  background: #0d1117;
  border: 2px solid #30363d;
  border-radius: 10px;
  padding: 30px;
  margin: 30px 0;
  position: relative;
  overflow: hidden;
}
.terminal-header {
  display: flex;
  gap: 10px;
  margin-bottom: 20px;
}
.terminal-dot {
  width: 12px;
  height: 12px;
  border-radius: 50%;
}
.red { background: #ff5f56; }
.yellow { background: #ffbd2e; }
.green { background: #27c93f; }
.typing-text {
  font-family: 'Courier New', monospace;
  color: #58a6ff;
  font-size: 1.2em;
  white-space: nowrap;
  overflow: hidden;
  border-right: 2px solid;
  animation: typewriter 3s steps(40) 1s 1 normal both,
             blink 0.75s step-end infinite;
  width: 0;
}
.neon-title {
  font-size: 3em;
  text-align: center;
  color: transparent;
  background: linear-gradient(90deg, #ff6b9d, #8a8dff, #58a6ff);
  background-size: 200% auto;
  -webkit-background-clip: text;
  background-clip: text;
  animation: gradientBG 3s ease infinite;
  margin: 20px 0;
}
.hologram-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 15px;
  margin: 40px 0;
}
.holo-card {
  background: rgba(13, 17, 23, 0.8);
  border: 1px solid rgba(138, 141, 255, 0.3);
  border-radius: 8px;
  padding: 20px;
  text-align: center;
  transition: all 0.3s;
  position: relative;
  overflow: hidden;
}
.holo-card:before {
  content: '';
  position: absolute;
  top: -2px;
  left: -2px;
  right: -2px;
  bottom: -2px;
  background: linear-gradient(45deg, #ff6b9d, #8a8dff, transparent);
  z-index: -1;
  opacity: 0;
  transition: opacity 0.3s;
}
.holo-card:hover:before {
  opacity: 1;
}
.holo-card:hover {
  transform: translateY(-5px);
  border-color: #8a8dff;
  box-shadow: 0 10px 20px rgba(138, 141, 255, 0.2);
}
.holo-card h3 {
  color: #ff6b9d;
  margin: 0 0 10px 0;
  font-size: 1.3em;
}
.glitch-text {
  font-size: 2em;
  font-weight: bold;
  color: #fff;
  position: relative;
  display: inline-block;
  margin: 20px 0;
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
  text-shadow: -1px 0 #ff6b9d;
  animation: glitch-1 2s infinite linear alternate-reverse;
}
.glitch-text:after {
  left: -2px;
  text-shadow: -1px 0 #8a8dff;
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
.scan-line {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 2px;
  background: rgba(138, 141, 255, 0.5);
  animation: scan 2s linear infinite;
  z-index: 1;
}
@keyframes scan {
  0% { top: 0; }
  100% { top: 100%; }
}
.binary-rain {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  overflow: hidden;
  pointer-events: none;
  z-index: 0;
}
.binary-digit {
  position: absolute;
  color: #0af;
  font-family: monospace;
  font-size: 14px;
  opacity: 0.3;
  animation: fall linear infinite;
}
@keyframes fall {
  to { transform: translateY(100vh); }
}
.floating-badge {
  display: inline-block;
  padding: 8px 20px;
  margin: 10px;
  background: #161b22;
  border: 1px solid #30363d;
  border-radius: 20px;
  color: #58a6ff;
  animation: pulse 2s infinite;
  cursor: pointer;
  transition: all 0.3s;
}
.floating-badge:hover {
  background: #8a8dff;
  color: white;
  transform: scale(1.1);
}
</style>

<script>
// Binary rain effect
document.addEventListener('DOMContentLoaded', function() {
  const binaryRain = document.createElement('div');
  binaryRain.className = 'binary-rain';
  document.querySelector('.cyber-terminal').appendChild(binaryRain);
  
  for (let i = 0; i < 50; i++) {
    const digit = document.createElement('div');
    digit.className = 'binary-digit';
    digit.textContent = Math.random() > 0.5 ? '1' : '0';
    digit.style.left = Math.random() * 100 + '%';
    digit.style.animationDuration = (Math.random() * 5 + 3) + 's';
    digit.style.animationDelay = Math.random() * 5 + 's';
    binaryRain.appendChild(digit);
  }
});
</script>

<div class="cyber-terminal">
  <div class="scan-line"></div>
  <div class="terminal-header">
    <div class="terminal-dot red"></div>
    <div class="terminal-dot yellow"></div>
    <div class="terminal-dot green"></div>
  </div>
  <div class="typing-text">$  Bienvenue sur mon site ...</div>
</div>

<div class="neon-title">HANAME</div>
<div class="glitch-text" data-text="CYBERSECURITY STUDENT">CYBERSECURITY STUDENT</div>

<div class="hologram-grid">
  <div class="holo-card">
    <h3>À PROPOS</h3>
    <p style="color: #c9d1d9;">Mon parcours cyber</p>
  </div>
  <div class="holo-card">
    <h3>FSSM</h3>
    <p style="color: #c9d1d9;">Formation académique</p>
  </div>
  <div class="holo-card">
    <h3>TRYHACKME</h3>
    <p style="color: #c9d1d9;">Challenges & badges</p>
  </div>
  <div class="holo-card">
    <h3>MON LAB</h3>
    <p style="color: #c9d1d9;">Environnement de test</p>
  </div>
</div>

<p style="text-align: center; font-size: 1.2em; color: #8b949e; margin: 40px 0; animation: slideIn 1s ease-out;">
  Salut — je suis <strong style="color: #ff6b9d;">Haname</strong>, étudiante en cybersécurité à la FSSM.<br>
  Bienvenue sur mon site où je partage mon parcours, mes parcours (paths) TryHackMe, la formation FSSM, et mes laboratoires personnels.
</p>

<div style="text-align: center; margin: 30px 0;">
  <span class="floating-badge" onclick="window.location='{{ site.baseurl }}/tryhackme'">TRYHACKME</span>
  <span class="floating-badge" onclick="window.open('https://github.com/ItsHaname')">GITHUB</span>
  <span class="floating-badge">TWITTER</span>
  <span class="floating-badge">LINKEDIN</span>
</div>

<div style="text-align: center; margin-top: 50px; color: #586069; font-size: 0.9em;">
  © 2025 HANAME — CYBERSECURITY STUDENT — FSSM
</div>
