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

/* CYBERIA Header */
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
  font-style: italic;
  -webkit-text-stroke: 2px #ff3300;
  paint-order: stroke fill;
}

.cyberia-line {
  width: 100%;
  height: 3px;
  background: linear-gradient(90deg, transparent, #1e4d7b, #3b82f6, #1e4d7b, transparent);
  margin: 20px auto;
  max-width: 500px;
  box-shadow: 0 0 15px #3b82f6;
}

.cyberia-subtitle {
  font-size: 1.8em;
  color: #60a5fa;
  margin-top: 10px;
  text-shadow: 0 0 10px #60a5fa, 0 0 20px #3b82f6;
  letter-spacing: 4px;
  font-style: italic;
}

.cyberia-subtitle::after {
  content: '_';
  animation: blink 1s infinite;
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

/* NEW small container for visitor count */
.visitor-box {
  margin-bottom: 15px;
  padding: 10px 20px;
  display: inline-block;
  background: rgba(15, 23, 42, 0.9);
  border: 1px solid rgba(59, 130, 246, 0.4);
  border-radius: 20px;
  color: #60a5fa;
  font-family: 'Courier New', monospace;
  box-shadow: 0 0 15px rgba(59, 130, 246, 0.3);
}

.cyber-footer {
  text-align: center;
  margin-top: 80px;
  padding-top: 30px;
  border-top: 1px solid rgba(59, 130, 246, 0.3);
  color: #64748b;
  font-size: 0.9em;
}
</style>

<script>
document.addEventListener('DOMContentLoaded', function () {

  // Visitor counter (localStorage)
  let visits = localStorage.getItem('cyberia_visits');
  visits = visits ? parseInt(visits) + 1 : 1;
  localStorage.setItem('cyberia_visits', visits);

  document.getElementById('visitor-count').textContent = visits;
});
</script>

<div class="container">

  <div class="cyberia-header">
    <div class="cyberia-title">CYBERIA</div>
    <div class="cyberia-line"></div>
    <div class="cyberia-subtitle">Cafe & Club</div>
  </div>

  <!-- MODIFIED PART ONLY -->
  <div class="welcome-text">
    <div class="visitor-box">
      Hello visitor <span id="visitor-count">0</span> 👋
    </div>

   <p>
      Hello visitor <strong style="color:#60a5fa;"><span id="visitor-count-inline"></span></strong>,
      je suis <strong style="color: #3b82f6;">Hanane</strong>, étudiante en cybersécurité à la FSSM.<br>
      Bienvenue à <strong>CYBERIA</strong>, mon espace personnel où je partage mes parcours TryHackMe,
      ma formation FSSM et mes laboratoires personnels.
    </p>
  </div>

  <div class="cyber-footer">
    © 2025 CYBERIA — HANAME — FSSM — Personal Knowledge Repository
  </div>

</div>

<script>
  // sync inline visitor number
  document.getElementById('visitor-count-inline').textContent =
    localStorage.getItem('cyberia_visits');
</script>
