---
layout: default
title: Accueil
nav: home
---

<style>
.hero {
  text-align: center;
  padding: 40px 20px;
  margin-bottom: 40px;
}
.hero h1 {
  color: #000;
  font-size: 2.5em;
  margin-bottom: 10px;
}
.nav-cards {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 20px;
  margin: 40px 0;
}
.card {
  background: #f6f8fa;
  border: 1px solid #e1e4e8;
  border-radius: 6px;
  padding: 25px;
  transition: 0.2s;
  text-decoration: none;
  color: inherit;
  display: block;
}
.card:hover {
  border-color: #0366d6;
  box-shadow: 0 3px 6px rgba(0,0,0,0.1);
}
.card h3 {
  color: #24292e;
  margin-top: 0;
  border-bottom: 2px solid #ea4aaa;
  padding-bottom: 8px;
}
.card p {
  color: #586069;
}
.badges {
  display: flex;
  gap: 10px;
  margin: 30px 0;
  justify-content: center;
  flex-wrap: wrap;
}
.badge {
  background: #f6f8fa;
  color: #0366d6;
  padding: 8px 15px;
  border-radius: 15px;
  border: 1px solid #e1e4e8;
  font-size: 0.9em;
}
.welcome-text {
  text-align: center;
  font-size: 1.1em;
  margin: 30px 0;
  padding: 20px;
  background: #f6f8fa;
  border-radius: 6px;
  border-left: 4px solid #0366d6;
}
@media (max-width: 600px) {
  .nav-cards {
    grid-template-columns: 1fr;
  }
}
</style>

<div class="hero">
  <h1>Haname — Cybersecurity Student</h1>
  <p>Étudiante en Cybersécurité – FSSM</p>
</div>

<div class="nav-cards">
  <a href="{{ site.baseurl }}/about" class="card">
    <h3>À propos</h3>
    <p>Mon parcours, passions et motivation dans la cybersécurité</p>
  </a>
  
  <a href="{{ site.baseurl }}/fssm" class="card">
    <h3>FSSM</h3>
    <p>Formation académique, projets et compétences acquises</p>
  </a>
  
  <a href="{{ site.baseurl }}/tryhackme" class="card">
    <h3>TryHackMe</h3>
    <p>Paths complétés, badges et write-ups de challenges</p>
  </a>
  
  <a href="{{ site.baseurl }}/my-lab" class="card">
    <h3>Mon Lab</h3>
    <p>Environnement de test, machines virtuelles et expériences</p>
  </a>
</div>

<div class="welcome-text">
  <p>Salut — je suis <strong>Haname</strong>, étudiante en cybersécurité à la FSSM.<br>
  Bienvenue sur mon site où je partage mon parcours, mes parcours (paths) TryHackMe, la formation FSSM, et mes laboratoires personnels.</p>
</div>

<div class="badges">
  <span class="badge">TryHackMe</span>
  <span class="badge">GitHub</span>
  <span class="badge">Twitter</span>
  <span class="badge">LinkedIn</span>
</div>

<footer style="text-align: center; margin-top: 50px; color: #586069; font-size: 0.9em;">
  © 2025 Haname — Cybersecurity Student — FSSM
</footer>
