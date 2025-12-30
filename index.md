---
layout: default
title: Accueil
nav: home
---

<style>
/* Matrix background */
@keyframes matrixRain {
  0% { background-position: 0% 0%; }
  100% { background-position: 0% 100%; }
}

body {
  background: 
    linear-gradient(rgba(13, 17, 23, 0.95), rgba(13, 17, 23, 0.98)),
    repeating-linear-gradient(0deg, 
      transparent, 
      transparent 2px, 
      rgba(0, 170, 255, 0.03) 2px, 
      rgba(0, 170, 255, 0.03) 4px);
  animation: matrixRain 20s linear infinite;
}

/* Navigation cards */
.nav-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 20px;
  margin: 40px 0;
}

.nav-card {
  background: #161b22;
  border: 1px solid #30363d;
  border-radius: 10px;
  padding: 25px;
  text-align: center;
  text-decoration: none;
  color: inherit;
  display: block;
  transition: all 0.3s;
  position: relative;
  overflow: hidden;
}

.nav-card:hover {
  border-color: #ea4aaa;
  transform: translateY(-5px);
  box-shadow: 0 10px 20px rgba(234, 74, 170, 0.2);
}

.nav-card h3 {
  color: #ea4aaa;
  margin: 0 0 10px 0;
  font-size: 1.3em;
}

.nav-card p {
  color: #8b949e;
  margin: 0;
}

/* Typing effect */
.typing-container {
  background: #0d1117;
  border: 2px solid #30363d;
  border-radius: 10px;
  padding: 20px;
  margin: 30px 0;
  font-family: 'Courier New', monospace;
}

.typing-text {
  color: #58a6ff;
  font-size: 1.1em;
  white-space: nowrap;
  overflow: hidden;
  border-right: 2px solid #58a6ff;
  animation: blink 0.75s step-end infinite;
}

@keyframes blink {
  0%, 100% { border-color: #58a6ff; }
  50% { border-color: transparent; }
}

/* Badges */
.badge-container {
  display: flex;
  gap: 15px;
  justify-content: center;
  margin: 30px 0;
  flex-wrap: wrap;
}

.badge {
  background: #161b22;
  color: #58a6ff;
  padding: 8px 16px;
  border-radius: 20px;
  border: 1px solid #30363d;
  text-decoration: none;
  font-size: 0.9em;
  transition: all 0.3s;
}

.badge:hover {
  background: #58a6ff;
  color: white;
  transform: scale(1.05);
}

/* Responsive */
@media (max-width: 768px) {
  .nav-grid {
    grid-template-columns: 1fr;
  }
}
</style>

<script>
// Simple typing effect
document.addEventListener('DOMContentLoaded', function() {
  const text = "$ Bienvenue sur le terminal de Haname...";
  const typingElement = document.querySelector('.typing-text');
  let i = 0;
  
  function typeWriter() {
    if (i < text.length) {
      typingElement.textContent += text.charAt(i);
      i++;
      setTimeout(typeWriter, 50);
    }
  }
  
  setTimeout(typeWriter, 500);
});
</script>

<div style="text-align: center; margin: 40px 0;">
  <h1 style="color: #ea4aaa; font-size: 2.5em;">Haname</h1>
  <p style="color: #8b949e; font-size: 1.2em;">Cybersecurity Student — FSSM</p>
</div>

<div class="typing-container">
  <div class="typing-text"></div>
</div>

<div class="nav-grid">
  <a href="{{ site.baseurl }}/about" class="nav-card">
    <h3>À propos</h3>
    <p>Mon parcours en cybersécurité</p>
  </a>
  
  <a href="{{ site.baseurl }}/fssm" class="nav-card">
    <h3>FSSM</h3>
    <p>Formation académique et projets</p>
  </a>
  
  <a href="{{ site.baseurl }}/tryhackme" class="nav-card">
    <h3>TryHackMe</h3>
    <p>Challenges et badges obtenus</p>
  </a>
  
  <a href="{{ site.baseurl }}/my-lab" class="nav-card">
    <h3>Mon Lab</h3>
    <p>Environnement de test personnel</p>
  </a>
</div>

<p style="text-align: center; font-size: 1.1em; color: #c9d1d9; margin: 30px 0; padding: 0 20px;">
  Salut — je suis <strong style="color: #ea4aaa;">Haname</strong>, étudiante en cybersécurité à la FSSM.<br>
  Bienvenue sur mon site où je partage mon parcours, mes parcours (paths) TryHackMe, la formation FSSM, et mes laboratoires personnels.
</p>

<div class="badge-container">
  <a href="{{ site.baseurl }}/tryhackme" class="badge">TryHackMe</a>
  <a href="https://github.com/ItsHaname" class="badge" target="_blank">GitHub</a>
  <a href="#" class="badge">Twitter</a>
  <a href="#" class="badge">LinkedIn</a>
</div>

<footer style="text-align: center; margin-top: 50px; color: #8b949e; font-size: 0.9em;">
  © 2025 Haname — Cybersecurity Student — FSSM
</footer>
