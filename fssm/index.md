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
  0% { transform: scale(1); }
  50% { transform: scale(1.05); }
  100% { transform: scale(1); }
}

@keyframes blink {
  0%, 100% { opacity: 1; }
  50% { opacity: 0; }
}

.fssm-header {
  text-align: center;
  margin-bottom: 60px;
  padding: 40px 20px;
  background: rgba(0, 20, 40, 0.6);
  border-radius: 20px;
  border: 2px solid #1e4d7b;
  box-shadow: 0 0 30px rgba(30, 77, 123, 0.4);
}

.fssm-logo {
  max-width: 600px;
  width: 100%;
  margin-bottom: 30px;
  filter: drop-shadow(0 0 20px rgba(59, 130, 246, 0.3));
}

.fssm-title {
  font-size: 3em;
  color: transparent;
  background: linear-gradient(90deg, #3b82f6, #60a5fa, #2563eb);
  background-size: 200% auto;
  -webkit-background-clip: text;
  background-clip: text;
  animation: gradientBG 3s ease infinite;
  margin: 20px 0;
  font-weight: 900;
  letter-spacing: 3px;
}

.fssm-subtitle {
  font-size: 1.3em;
  color: #94a3b8;
  margin: 10px 0;
  font-style: italic;
}

.fssm-subtitle::after {
  content: '_';
  animation: blink 1s infinite;
  color: #60a5fa;
}

.intro-section {
  background: rgba(15, 23, 42, 0.7);
  padding: 30px;
  border-radius: 15px;
  border-left: 4px solid #3b82f6;
  margin-bottom: 50px;
  color: #cbd5e1;
  line-height: 1.8;
  animation: slideIn 0.8s ease-out;
}

.intro-section strong {
  color: #60a5fa;
}

.modules-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 25px;
  margin: 40px 0;
}

.module-card {
  background: rgba(15, 23, 42, 0.85);
  border: 2px solid rgba(59, 130, 246, 0.3);
  border-radius: 15px;
  padding: 30px;
  transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
  position: relative;
  overflow: hidden;
  text-decoration: none;
  color: inherit;
  display: block;
  animation: slideIn 0.8s ease-out backwards;
}

.module-card:nth-child(1) { animation-delay: 0.1s; }
.module-card:nth-child(2) { animation-delay: 0.2s; }
.module-card:nth-child(3) { animation-delay: 0.3s; }
.module-card:nth-child(4) { animation-delay: 0.4s; }
.module-card:nth-child(5) { animation-delay: 0.5s; }

.module-card:before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: linear-gradient(135deg, rgba(59, 130, 246, 0.1), transparent);
  opacity: 0;
  transition: opacity 0.4s;
}

.module-card:hover:before {
  opacity: 1;
}

.module-card:hover {
  transform: translateY(-8px) scale(1.02);
  border-color: #60a5fa;
  box-shadow: 0 15px 40px rgba(59, 130, 246, 0.4);
}

.module-number {
  display: inline-block;
  background: linear-gradient(135deg, #3b82f6, #2563eb);
  color: white;
  padding: 8px 16px;
  border-radius: 20px;
  font-size: 0.9em;
  font-weight: 700;
  margin-bottom: 15px;
  box-shadow: 0 4px 10px rgba(59, 130, 246, 0.3);
}

.module-card h3 {
  color: #60a5fa;
  margin: 15px 0;
  font-size: 1.5em;
  font-weight: 600;
  display: flex;
  align-items: center;
  gap: 10px;
}

.module-card h3::before {
  content: '▹';
  color: #3b82f6;
  font-size: 1.2em;
}

.module-card p {
  color: #94a3b8;
  margin: 15px 0;
  line-height: 1.7;
}

.module-topics {
  list-style: none;
  padding: 0;
  margin: 20px 0 0 0;
}

.module-topics li {
  color: #cbd5e1;
  padding: 8px 0;
  padding-left: 25px;
  position: relative;
  font-size: 0.95em;
}

.module-topics li::before {
  content: '→';
  position: absolute;
  left: 0;
  color: #3b82f6;
  font-weight: bold;
}

.stats-section {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 20px;
  margin: 50px 0;
}

.stat-box {
  background: rgba(15, 23, 42, 0.8);
  border: 1px solid rgba(59, 130, 246, 0.3);
  border-radius: 12px;
  padding: 25px;
  text-align: center;
  transition: all 0.3s;
}

.stat-box:hover {
  border-color: #60a5fa;
  box-shadow: 0 8px 20px rgba(59, 130, 246, 0.3);
  transform: translateY(-5px);
}

.stat-number {
  font-size: 2.5em;
  color: #3b82f6;
  font-weight: 900;
  margin-bottom: 10px;
}

.stat-label {
  color: #94a3b8;
  font-size: 0.95em;
  text-transform: uppercase;
  letter-spacing: 1px;
}

.note-box {
  background: rgba(37, 99, 235, 0.1);
  border-left: 4px solid #3b82f6;
  padding: 20px;
  border-radius: 8px;
  margin: 30px 0;
  color: #cbd5e1;
}

.note-box strong {
  color: #60a5fa;
}

@media (max-width: 768px) {
  .fssm-title {
    font-size: 2em;
  }
  
  .modules-grid {
    grid-template-columns: 1fr;
  }
  
  .stats-section {
    grid-template-columns: 1fr;
  }
}
</style>

<div class="fssm-header">
  <img src="https://raw.githubusercontent.com/ItsHaname/ItsHaname.github.io/main/assets/images/fssm-logo.png" alt="FSSM Logo" class="fssm-logo" onerror="this.style.display='none'">
  <div class="fssm-title">PARCOURS FSSM</div>
  <div class="fssm-subtitle">Faculté des Sciences Semlalia - Marrakech</div>
</div>

<div class="intro-section">
  <p>
    Bienvenue dans mon parcours académique à la <strong>Faculté des Sciences Semlalia (FSSM)</strong> de Marrakech. 
    Cette section regroupe l'ensemble de mes modules en cybersécurité, réseaux, et technologies de l'information.
  </p>
  <p>
    Chaque module contient mes <strong>notes de cours</strong>, <strong>travaux pratiques</strong>, 
    <strong>projets</strong>, et <strong>ressources</strong> que j'ai accumulés tout au long de ma formation.
  </p>
</div>

<div class="stats-section">
  <div class="stat-box">
    <div class="stat-number">5</div>
    <div class="stat-label">Modules</div>
  </div>
  <div class="stat-box">
    <div class="stat-number">S5</div>
    <div class="stat-label">Semestre</div>
  </div>
  <div class="stat-box">
    <div class="stat-number">100%</div>
    <div class="stat-label">Cybersécurité</div>
  </div>
</div>

<h2 style="color: #60a5fa; text-align: center; margin: 50px 0 30px 0; font-size: 2em;">📚 Modules du Parcours</h2>

<div class="modules-grid">
  
  <a href="/fssm/iot-analyse-connexion" class="module-card">
    <span class="module-number">MODULE 1</span>
    <h3>IoT Analyse et Connexion</h3>
    <p>Exploration des objets connectés, protocoles IoT, et sécurité des réseaux de capteurs.</p>
    <ul class="module-topics">
      <li>Architecture IoT</li>
      <li>Protocoles MQTT, CoAP</li>
      <li>Sécurité des devices</li>
      <li>Projets Arduino/Raspberry Pi</li>
    </ul>
  </a>

  <a href="/fssm/parallelisme-programmation-reseaux" class="module-card">
    <span class="module-number">MODULE 2</span>
    <h3>Parallélisme et Programmation Réseaux</h3>
    <p>Programmation concurrente, sockets, et développement d'applications réseau.</p>
    <ul class="module-topics">
      <li>Threads et processus</li>
      <li>Sockets TCP/UDP</li>
      <li>Client-Serveur</li>
      <li>Synchronisation</li>
    </ul>
  </a>

  <a href="/fssm/droit-digital" class="module-card">
    <span class="module-number">MODULE 3</span>
    <h3>Droit Digital</h3>
    <p>Cadre juridique du numérique, RGPD, propriété intellectuelle et cybercrimes.</p>
    <ul class="module-topics">
      <li>RGPD et protection des données</li>
      <li>Cybercriminalité</li>
      <li>Propriété intellectuelle</li>
      <li>Contrats numériques</li>
    </ul>
  </a>

  <a href="/fssm/gouvernance-securite" class="module-card">
    <span class="module-number">MODULE 4</span>
    <h3>Gouvernance de la Sécurité et Transformation Digitale</h3>
    <p>Gestion des risques, normes ISO, gouvernance IT et stratégie de sécurité.</p>
    <ul class="module-topics">
      <li>ISO 27001/27002</li>
      <li>Gestion des risques</li>
      <li>ITIL et gouvernance IT</li>
      <li>Audit de sécurité</li>
    </ul>
  </a>

  <a href="/fssm/cryptographie-cybersecurite" class="module-card">
    <span class="module-number">MODULE 5</span>
    <h3>Cryptographie et Cybersécurité</h3>
    <p>Algorithmes de chiffrement, cryptanalyse, PKI et applications de sécurité.</p>
    <ul class="module-topics">
      <li>Chiffrement symétrique/asymétrique</li>
      <li>Hash et signature digitale</li>
      <li>PKI et certificats</li>
      <li>Cryptanalyse</li>
    </ul>
  </a>

</div>

<div class="note-box">
  <strong>📝 Note :</strong> Chaque module contient mes notes de cours, TPs, projets et ressources. 
  Clique sur un module pour accéder à son contenu détaillé.
</div>

<div style="text-align: center; margin-top: 60px; padding: 30px; background: rgba(15, 23, 42, 0.5); border-radius: 15px;">
  <p style="color: #94a3b8; font-size: 1.1em;">
    🎓 Année académique 2024-2025 • FSSM Marrakech
  </p>
</div>
