---
layout: default
title: Parcours TryHackMe
nav: tryhackme
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
  0%, 100% { transform: scale(1); box-shadow: 0 0 20px rgba(220, 38, 38, 0.3); }
  50% { transform: scale(1.05); box-shadow: 0 0 40px rgba(220, 38, 38, 0.6); }
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
  0%, 100% { text-shadow: 0 0 10px #dc2626, 0 0 20px #dc2626; }
  50% { text-shadow: 0 0 20px #dc2626, 0 0 40px #ef4444, 0 0 60px #f87171; }
}

.thm-container {
  position: relative;
  overflow: hidden;
}

.thm-hero {
  text-align: center;
  margin-bottom: 80px;
  padding: 60px 20px;
  background: linear-gradient(135deg, rgba(15, 23, 42, 0.9), rgba(30, 41, 59, 0.8));
  border-radius: 30px;
  border: 3px solid transparent;
  background-clip: padding-box;
  position: relative;
  overflow: hidden;
}

.thm-hero::before {
  content: '';
  position: absolute;
  top: -3px;
  left: -3px;
  right: -3px;
  bottom: -3px;
  background: linear-gradient(45deg, #dc2626, #ef4444, #f87171, #dc2626);
  background-size: 300% 300%;
  animation: gradientBG 4s ease infinite;
  border-radius: 30px;
  z-index: -1;
}

.thm-logo {
  font-size: 4em;
  margin-bottom: 20px;
  animation: float 3s ease-in-out infinite;
  filter: drop-shadow(0 0 30px #dc2626);
}

.thm-title {
  font-size: 4em;
  color: transparent;
  background: linear-gradient(90deg, #dc2626, #ef4444, #f87171, #ef4444, #dc2626);
  background-size: 300% auto;
  -webkit-background-clip: text;
  background-clip: text;
  animation: gradientBG 3s ease infinite, glow 2s ease-in-out infinite;
  margin: 30px 0;
  font-weight: 900;
  letter-spacing: 5px;
  text-transform: uppercase;
}

.thm-subtitle {
  font-size: 1.5em;
  color: #94a3b8;
  margin: 20px 0;
  font-style: italic;
  letter-spacing: 2px;
}

.thm-subtitle::after {
  content: '_';
  animation: blink 1s infinite;
  color: #dc2626;
}

.badge-section {
  text-align: center;
  margin: 60px 0;
  padding: 40px;
  background: rgba(15, 23, 42, 0.8);
  border-radius: 20px;
  border: 2px solid #dc2626;
  box-shadow: 0 0 30px rgba(220, 38, 38, 0.3);
}

.badge-section h2 {
  color: #ef4444;
  font-size: 2em;
  margin-bottom: 30px;
  text-shadow: 0 0 20px rgba(220, 38, 38, 0.5);
}

.badge-frame {
  display: inline-block;
  padding: 20px;
  background: rgba(0, 0, 0, 0.5);
  border-radius: 15px;
  border: 2px solid #dc2626;
  box-shadow: 0 10px 40px rgba(220, 38, 38, 0.4);
}

.badge-frame iframe {
  border: none;
  border-radius: 10px;
  min-height: 200px;
}

.path-section {
  margin: 80px 0;
}

.path-header {
  text-align: center;
  margin-bottom: 50px;
}

.path-badge {
  display: inline-block;
  padding: 15px 40px;
  background: linear-gradient(135deg, #dc2626, #991b1b);
  color: white;
  font-size: 1.2em;
  font-weight: 900;
  border-radius: 50px;
  margin-bottom: 20px;
  box-shadow: 0 10px 30px rgba(220, 38, 38, 0.5);
  animation: pulse 3s infinite;
  letter-spacing: 2px;
}

.path-title {
  font-size: 3em;
  color: #ef4444;
  font-weight: 900;
  text-shadow: 0 0 20px rgba(220, 38, 38, 0.5);
  margin: 20px 0;
}

.path-description {
  color: #94a3b8;
  font-size: 1.2em;
  max-width: 800px;
  margin: 0 auto;
  line-height: 1.8;
}

.progress-bar-container {
  background: rgba(15, 23, 42, 0.8);
  border-radius: 15px;
  padding: 30px;
  margin: 40px 0;
  border: 2px solid rgba(220, 38, 38, 0.3);
}

.progress-label {
  display: flex;
  justify-content: space-between;
  color: #cbd5e1;
  font-size: 1.1em;
  margin-bottom: 15px;
  font-weight: 600;
}

.progress-bar {
  width: 100%;
  height: 30px;
  background: rgba(30, 41, 59, 0.8);
  border-radius: 15px;
  overflow: hidden;
  position: relative;
  border: 2px solid #374151;
}

.progress-fill {
  height: 100%;
  background: linear-gradient(90deg, #dc2626, #ef4444);
  border-radius: 15px;
  transition: width 2s ease-out;
  box-shadow: 0 0 20px rgba(220, 38, 38, 0.6);
  position: relative;
  overflow: hidden;
}

.progress-fill::after {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.3), transparent);
  animation: shimmer 2s infinite;
}

@keyframes shimmer {
  0% { transform: translateX(-100%); }
  100% { transform: translateX(100%); }
}

.rooms-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 25px;
  margin: 40px 0;
}

.room-card {
  background: linear-gradient(135deg, rgba(15, 23, 42, 0.9), rgba(30, 41, 59, 0.8));
  border: 2px solid transparent;
  border-radius: 20px;
  padding: 30px;
  transition: all 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
  position: relative;
  text-decoration: none;
  color: inherit;
  display: block;
  animation: slideIn 0.8s ease-out backwards;
}

.room-card::before {
  content: '';
  position: absolute;
  top: -2px;
  left: -2px;
  right: -2px;
  bottom: -2px;
  background: linear-gradient(45deg, #dc2626, #ef4444, #f87171, #dc2626);
  background-size: 300% 300%;
  animation: gradientBG 6s ease infinite;
  border-radius: 20px;
  z-index: -1;
  opacity: 0;
  transition: opacity 0.5s;
}

.room-card:hover::before {
  opacity: 1;
}

.room-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 20px 50px rgba(220, 38, 38, 0.5);
}

.room-status {
  position: absolute;
  top: 20px;
  right: 20px;
  padding: 8px 16px;
  border-radius: 20px;
  font-size: 0.85em;
  font-weight: 700;
  border: 1px solid;
}

.status-completed {
  background: rgba(34, 197, 94, 0.2);
  color: #22c55e;
  border-color: #22c55e;
}

.status-progress {
  background: rgba(234, 179, 8, 0.2);
  color: #eab308;
  border-color: #eab308;
}

.status-pending {
  background: rgba(107, 114, 128, 0.2);
  color: #9ca3af;
  border-color: #6b7280;
}

.room-card h3 {
  color: #ef4444;
  margin: 10px 0 15px 0;
  font-size: 1.6em;
  font-weight: 700;
}

.room-card p {
  color: #cbd5e1;
  margin: 15px 0;
  line-height: 1.6;
  font-size: 0.95em;
}

.room-difficulty {
  display: inline-block;
  padding: 6px 14px;
  border-radius: 15px;
  font-size: 0.9em;
  font-weight: 600;
  margin-top: 10px;
}

.difficulty-easy {
  background: rgba(34, 197, 94, 0.2);
  color: #22c55e;
  border: 1px solid #22c55e;
}

.difficulty-medium {
  background: rgba(234, 179, 8, 0.2);
  color: #eab308;
  border: 1px solid #eab308;
}

.difficulty-hard {
  background: rgba(220, 38, 38, 0.2);
  color: #dc2626;
  border: 1px solid #dc2626;
}

.stats-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 20px;
  margin: 50px 0;
}

.stat-box {
  background: rgba(15, 23, 42, 0.8);
  border: 2px solid rgba(220, 38, 38, 0.3);
  border-radius: 15px;
  padding: 30px;
  text-align: center;
  transition: all 0.3s;
}

.stat-box:hover {
  border-color: #ef4444;
  box-shadow: 0 10px 30px rgba(220, 38, 38, 0.4);
  transform: translateY(-5px);
}

.stat-number {
  font-size: 2.5em;
  color: #dc2626;
  font-weight: 900;
  margin-bottom: 10px;
}

.stat-label {
  color: #94a3b8;
  font-size: 0.95em;
  text-transform: uppercase;
  letter-spacing: 1px;
}

@media (max-width: 768px) {
  .thm-title {
    font-size: 2.5em;
  }
  
  .path-title {
    font-size: 2em;
  }
  
  .rooms-grid {
    grid-template-columns: 1fr;
  }
}
</style>

<div class="thm-container">

<div class="thm-hero">
  <div class="thm-logo">🔐</div>
  <div class="thm-title">TryHackMe</div>
  <div class="thm-subtitle">Mon Apprentissage en Cybersécurité</div>
</div>

<div class="badge-section">
  <h2>Mon Profil TryHackMe</h2>
  <div class="badge-frame">
    <iframe src="https://tryhackme.com/api/v2/badges/public-profile?userPublicId=3165378" width="100%" height="280"></iframe>
  </div>
</div>

<div class="path-section">
  <div class="path-header">
    <div class="path-badge">EN COURS</div>
    <h2 class="path-title">Parcours d'Apprentissage</h2>
    <p class="path-description">
      Mon parcours sur TryHackMe pour développer mes compétences en cybersécurité offensive et défensive,
      en suivant les modules recommandés pour devenir un professionnel qualifié.
    </p>
  </div>

  <div class="progress-bar-container">
    <div class="progress-label">
      <span>Progression globale</span>
      <span>Débutant</span>
    </div>
    <div class="progress-bar">
      <div class="progress-fill" style="width: 20%;"></div>
    </div>
  </div>

  <div class="stats-grid">
    <div class="stat-box">
      <div class="stat-number">3</div>
      <div class="stat-label">Modules actifs</div>
    </div>
    <div class="stat-box">
      <div class="stat-number">12+</div>
      <div class="stat-label">Salles visitées</div>
    </div>
    <div class="stat-box">
      <div class="stat-number">5</div>
      <div class="stat-label">Badges obtenus</div>
    </div>
  </div>

  <h3 style="color: #ef4444; font-size: 2em; margin: 60px 0 30px 0; text-align: center;">
    Mes Modules Actuels
  </h3>

  <div class="rooms-grid">
    
   <div class="room-card">
      <span class="room-status status-progress">En cours</span>
      <h3>Introduction to Cyber Security</h3>
      <p>Comprendre la sécurité offensive et défensive, et découvrir les carrières disponibles en cybersécurité.</p>
      <span class="room-difficulty difficulty-easy">Facile</span>
    </div>

   <div class="room-card">
      <span class="room-status status-progress">En cours</span>
      <h3>Introduction to Pentesting</h3>
      <p>Comprendre ce qu'implique un test d'intrusion, y compris les techniques et méthodologies que tout pentester devrait connaître.</p>
      <span class="room-difficulty difficulty-medium">Moyen</span>
    </div>

   <div class="room-card">
      <span class="room-status status-progress">En cours</span>
      <h3>Introduction to Web Hacking</h3>
      <p>Apprendre et exploiter certaines des vulnérabilités d'application web les plus populaires dans l'industrie.</p>
      <span class="room-difficulty difficulty-medium">Moyen</span>
    </div>

  <div class="room-card">
      <span class="room-status status-pending">À venir</span>
      <h3>Burp Suite</h3>
      <p>L'outil standard de l'industrie pour le hacking d'applications web, essentiel pour tout test de pénétration web.</p>
      <span class="room-difficulty difficulty-medium">Moyen</span>
    </div>

  <div class="room-card">
      <span class="room-status status-pending">À venir</span>
      <h3>Network Security</h3>
      <p>Apprendre les bases de la reconnaissance réseau passive et active. Comprendre le fonctionnement des protocoles courants.</p>
      <span class="room-difficulty difficulty-medium">Moyen</span>
    </div>

   <div class="room-card">
      <span class="room-status status-pending">À venir</span>
      <h3>Metasploit</h3>
      <p>Le framework d'exploitation le plus utilisé. Apprendre à l'utiliser et à débloquer son plein potentiel.</p>
      <span class="room-difficulty difficulty-hard">Difficile</span>
    </div>

  <div class="room-card">
      <span class="room-status status-pending">À venir</span>
      <h3>Privilege Escalation</h3>
      <p>Apprendre les techniques fondamentales pour élever les privilèges de compte dans les systèmes Linux et Windows.</p>
      <span class="room-difficulty difficulty-hard">Difficile</span>
    </div>

  <div class="room-card">
      <span class="room-status status-pending">À venir</span>
      <h3>Vulnerability Research</h3>
      <p>Se familiariser avec les compétences, méthodes de recherche et ressources utilisées pour exploiter les applications et systèmes vulnérables.</p>
      <span class="room-difficulty difficulty-hard">Difficile</span>
    </div>

  </div>
</div>

<div style="text-align: center; margin-top: 80px; padding: 40px; background: linear-gradient(135deg, rgba(15, 23, 42, 0.8), rgba(30, 41, 59, 0.9)); border-radius: 20px; border: 2px solid #7f1d1d;">
  <p style="color: #94a3b8; font-size: 1.1em; line-height: 1.8;">
    <span style="color: #ef4444; font-weight: bold;">🎯 Objectif Principal:</span> Devenir un Pentester Junior certifié<br>
    <span style="color: #ef4444; font-weight: bold;">📊 Progression:</span> Débutant → Junior Penetration Tester → Pentester Professionnel<br>
    <span style="color: #ef4444; font-weight: bold;">🔗 Profil TryHackMe:</span> <a href="https://tryhackme.com/p/3165378" target="_blank" style="color: #ef4444; font-weight: bold; text-decoration: none;">@3165378</a><br>
    <span style="color: #ef4444; font-weight: bold;">🏆 Certification visée:</span> Jr. Penetration Tester (PT1)
  </p>
</div>

</div>
