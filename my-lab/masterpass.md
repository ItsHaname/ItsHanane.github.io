---
layout: default
title: Master Password on Arch Linux
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

.container {
  max-width: 1100px;
  margin: 0 auto;
  padding: 40px 20px;
  position: relative;
  z-index: 1;
}

.page-header {
  text-align: center;
  margin-bottom: 50px;
  padding: 40px 20px;
  background: rgba(0, 20, 40, 0.6);
  border-radius: 20px;
  border: 2px solid #1e4d7b;
  box-shadow: 0 0 30px rgba(30, 77, 123, 0.3);
}

.page-title {
  font-size: 3em;
  color: transparent;
  background: linear-gradient(90deg, #3b82f6, #60a5fa, #2563eb);
  background-size: 200% auto;
  -webkit-background-clip: text;
  background-clip: text;
  animation: gradientBG 3s ease infinite;
  margin-bottom: 15px;
  font-weight: 900;
}

.page-subtitle {
  color: #94a3b8;
  font-size: 1.2em;
  font-style: italic;
}

.section-card {
  background: rgba(15, 23, 42, 0.85);
  border: 1px solid rgba(59, 130, 246, 0.3);
  border-radius: 15px;
  padding: 30px;
  margin-bottom: 30px;
  animation: slideIn 0.8s ease-out;
}

.section-card h2 {
  color: #3b82f6;
  font-size: 2em;
  margin: 0 0 20px 0;
  border-bottom: 2px solid rgba(59, 130, 246, 0.3);
  padding-bottom: 10px;
}

.section-card h3 {
  color: #60a5fa;
  font-size: 1.5em;
  margin: 25px 0 15px 0;
}

.section-card p {
  color: #cbd5e1;
  line-height: 1.8;
  margin-bottom: 15px;
}

.section-card ul, .section-card ol {
  color: #cbd5e1;
  margin-left: 30px;
  margin-bottom: 15px;
}

.section-card li {
  margin-bottom: 10px;
  line-height: 1.6;
}

.section-card strong {
  color: #60a5fa;
}

.code-block {
  background: #0f172a;
  border: 1px solid #1e40af;
  border-radius: 8px;
  padding: 20px;
  margin: 20px 0;
  font-family: 'Courier New', monospace;
  color: #60a5fa;
  overflow-x: auto;
  position: relative;
}

.code-block code {
  font-size: 0.95em;
  line-height: 1.6;
}

.command {
  color: #10b981;
  font-weight: bold;
}

.output {
  color: #94a3b8;
}

.highlight-box {
  background: rgba(59, 130, 246, 0.1);
  border-left: 4px solid #3b82f6;
  padding: 20px;
  margin: 20px 0;
  border-radius: 8px;
}

.warning-box {
  background: rgba(255, 107, 74, 0.1);
  border: 2px solid rgba(255, 107, 74, 0.3);
  border-radius: 10px;
  padding: 20px;
  margin: 20px 0;
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

.warning-box ul {
  margin: 10px 0 0 20px;
  color: #cbd5e1;
}

.success-box {
  background: rgba(16, 185, 129, 0.1);
  border: 2px solid rgba(16, 185, 129, 0.3);
  border-radius: 10px;
  padding: 20px;
  margin: 20px 0;
}

.success-box h4 {
  color: #10b981;
  margin: 0 0 10px 0;
  font-size: 1.3em;
}

.success-box p {
  color: #cbd5e1;
  margin: 0;
  line-height: 1.6;
}

.step-number {
  display: inline-block;
  width: 35px;
  height: 35px;
  background: linear-gradient(135deg, #3b82f6, #2563eb);
  color: white;
  font-size: 1.2em;
  font-weight: 900;
  border-radius: 50%;
  text-align: center;
  line-height: 35px;
  margin-right: 10px;
  box-shadow: 0 5px 15px rgba(59, 130, 246, 0.4);
}

.comparison-table {
  width: 100%;
  border-collapse: collapse;
  margin: 20px 0;
  background: rgba(15, 23, 42, 0.5);
}

.comparison-table th {
  background: rgba(59, 130, 246, 0.2);
  color: #60a5fa;
  padding: 15px;
  text-align: left;
  font-weight: 600;
}

.comparison-table td {
  padding: 15px;
  border-bottom: 1px solid rgba(59, 130, 246, 0.2);
  color: #cbd5e1;
}

.footer-nav {
  display: flex;
  justify-content: space-between;
  margin-top: 50px;
  gap: 20px;
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
    font-size: 2em;
  }
  
  .section-card {
    padding: 20px;
  }
  
  .footer-nav {
    flex-direction: column;
  }
}
</style>

<div class="binary-background"></div>

<div class="container">
  <div class="page-header">
    <h1 class="page-title">🔐 Master Password on Arch Linux</h1>
    <p class="page-subtitle">Stateless Password Management</p>
  </div>

  <div class="section-card">
    <h2>Qu'est-ce que Master Password ?</h2>
    
    <div class="highlight-box">
      <p><strong>Master Password</strong> est un gestionnaire de mots de passe <strong>stateless</strong> (sans état). Contrairement à LastPass, 1Password ou Bitwarden, il ne stocke AUCUN mot de passe. Au lieu de cela, il génère vos mots de passe de manière <strong>algorithmique</strong> à partir de :</p>
      <ul>
        <li>Votre nom complet</li>
        <li>Votre mot de passe maître</li>
        <li>Le nom du site</li>
      </ul>
    </div>

    <h3>✅ Avantages</h3>
    <ul>
      <li><strong>Aucun fichier à perdre</strong> - Pas de base de données à sauvegarder</li>
      <li><strong>Aucun cloud</strong> - Pas de synchronisation nécessaire</li>
      <li><strong>Portable</strong> - Fonctionne partout (Linux, Windows, Mac, Android, iOS)</li>
      <li><strong>Sécurisé</strong> - Utilise l'algorithme scrypt pour la dérivation de clés</li>
      <li><strong>Open source</strong> - Code transparent et auditable</li>
    </ul>

    <h3>⚠️ Inconvénients</h3>
    <ul>
      <li>Tu dois te souvenir exactement de ton nom complet et mot de passe maître</li>
      <li>Pas de stockage de notes ou fichiers</li>
      <li>Changement de mot de passe = changer le "counter" du site</li>
    </ul>
  </div>

  <div class="section-card">
    <h2>Installation sur Arch Linux</h2>

    <h3><span class="step-number">1</span>Installer depuis AUR</h3>
    <p>Master Password est disponible dans l'AUR (Arch User Repository).</p>

    <div class="code-block">
<code><span class="command"># Avec yay (AUR helper)</span>
yay -S masterpassword

<span class="command"># Ou avec paru</span>
paru -S masterpassword

<span class="command"># Ou manuellement avec makepkg</span>
git clone https://aur.archlinux.org/masterpassword.git
cd masterpassword
makepkg -si</code>
    </div>

  <h3><span class="step-number">2</span>Vérifier l'installation</h3>
    <div class="code-block">
<code><span class="command">mpw --version</span>
<span class="output">Master Password v2.6</span></code>
    </div>

  <div class="success-box">
      <h4>✓ Installation réussie !</h4>
      <p>Master Password est maintenant installé et prêt à être utilisé.</p>
    </div>
  </div>

  <div class="section-card">
    <h2>Utilisation de Base</h2>

  <h3><span class="step-number">1</span>Générer votre premier mot de passe</h3>
    <div class="code-block">
<code><span class="command">mpw</span>

<span class="output">Your full name: </span>Haname Cyberia
<span class="output">Your master password: </span>************
<span class="output">Site name: </span>github.com

<span class="output">Generated password: </span>Xoja2*HufpDuvu</code>
    </div>

   <div class="warning-box">
      <h4>⚠️ Important</h4>
      <p>Entre <strong>EXACTEMENT</strong> le même nom et mot de passe maître à chaque fois. Une seule lettre différente = mot de passe différent !</p>
    </div>

  <h3><span class="step-number">2</span>Mode interactif vs mode direct</h3>
    
  <p><strong>Mode interactif</strong> (recommandé pour débuter) :</p>
    <div class="code-block">
<code><span class="command">mpw</span>
<span class="comment"># Tu seras guidé étape par étape</span></code>
    </div>

  <p><strong>Mode direct</strong> (plus rapide) :</p>
    <div class="code-block">
<code><span class="command">mpw -u "Haname Cyberia" github.com</span>
<span class="output">Your master password: </span>************
<span class="output">Xoja2*HufpDuvu</span></code>
    </div>

   <h3><span class="step-number">3</span>Copier directement dans le presse-papier</h3>
    <div class="code-block">
<code><span class="command"># Avec xclip</span>
mpw -u "Haname Cyberia" github.com | xclip -selection clipboard

<span class="command"># Avec wl-clipboard (Wayland)</span>
mpw -u "Haname Cyberia" github.com | wl-copy</code>
    </div>
  </div>

  <div class="section-card">
    <h2>Options Avancées</h2>

  <h3>Types de mots de passe</h3>
    <p>Master Password peut générer différents formats :</p>

   <table class="comparison-table">
      <tr>
        <th>Type</th>
        <th>Code</th>
        <th>Format</th>
        <th>Exemple</th>
      </tr>
      <tr>
        <td><strong>Maximum</strong></td>
        <td>-t x</td>
        <td>20 caractères, tous types</td>
        <td>w!3*Jugr1@Foli7%Huha</td>
      </tr>
      <tr>
        <td><strong>Long</strong> (défaut)</td>
        <td>-t l</td>
        <td>CvcvnoCvc</td>
        <td>Xoja2*HufpDuvu</td>
      </tr>
      <tr>
        <td><strong>Medium</strong></td>
        <td>-t m</td>
        <td>CvcnoCvc</td>
        <td>Xoj2*Huf</td>
      </tr>
      <tr>
        <td><strong>Basic</strong></td>
        <td>-t b</td>
        <td>aaanaaan</td>
        <td>xoj2hufp</td>
      </tr>
      <tr>
        <td><strong>Short</strong></td>
        <td>-t s</td>
        <td>Cvcn</td>
        <td>Xoj2</td>
      </tr>
      <tr>
        <td><strong>PIN</strong></td>
        <td>-t i</td>
        <td>nnnn</td>
        <td>7452</td>
      </tr>
    </table>

    <div class="code-block">
<code><span class="command"># Exemple : générer un PIN</span>
mpw -u "Haname Cyberia" -t i phone.unlock

<span class="command"># Exemple : mot de passe court</span>
mpw -u "Haname Cyberia" -t s wifi.password</code>
    </div>

   <h3>Counter (version du mot de passe)</h3>
    <p>Si tu dois changer un mot de passe, utilise le <strong>counter</strong> :</p>

  <div class="code-block">
<code><span class="command"># Première version (défaut)</span>
mpw -u "Haname Cyberia" github.com
<span class="output">Xoja2*HufpDuvu</span>

<span class="command"># Deuxième version (après changement forcé)</span>
mpw -u "Hanane Cyberia" -c 2 github.com
<span class="output">Lipo7+TekfZewo</span></code>
    </div>
  </div>

  <div class="section-card">
    <h2>Fichier de Configuration</h2>

   <p>Pour éviter de retaper ton nom à chaque fois, crée un fichier de config :</p>

  <div class="code-block">
<code><span class="command"># Créer le fichier de config</span>
mkdir -p ~/.config/mpw
nano ~/.config/mpw/mpw.conf</code>
    </div>

   <p>Contenu du fichier :</p>
    <div class="code-block">
<code># ~/.config/mpw/mpw.conf
fullName=Haname Cyberia
defaultType=long</code>
    </div>

  <p>Maintenant tu peux juste taper :</p>
    <div class="code-block">
<code><span class="command">mpw github.com</span>
<span class="output">Your master password: </span>************
<span class="output">Xoja2*HufpDuvu</span></code>
    </div>
  </div>

  <div class="section-card">
    <h2>Créer un Alias Pratique</h2>

   <p>Ajoute dans ton <code>~/.bashrc</code> ou <code>~/.zshrc</code> :</p>

  <div class="code-block">
<code><span class="command"># Alias pour copier directement le mot de passe</span>
alias pw='mpw -u "Haname Cyberia" "$1" | xclip -selection clipboard && echo "Password copied to clipboard!"'

<span class="command"># Utilisation</span>
pw github.com</code>
    </div>
  </div>

  <div class="section-card">
    <h2>Conseils de Sécurité</h2>

   <div class="warning-box">
      <h4> Bonnes Pratiques</h4>
      <ul>
        <li>Choisis un <strong>mot de passe maître fort</strong> (minimum 16 caractères)</li>
        <li>Ne stocke JAMAIS ton mot de passe maître quelque part</li>
        <li>Utilise exactement le même format de nom à chaque fois</li>
        <li>Teste ton mot de passe maître dans un environnement sûr avant de l'utiliser partout</li>
        <li>Note les "counters" si tu dois changer des mots de passe</li>
      </ul>
    </div>

  <div class="success-box">
      <h4>✓ Pourquoi c'est sûr ?</h4>
      <p>Master Password utilise <strong>scrypt</strong>, un algorithme de dérivation de clés résistant aux attaques par force brute. Même si quelqu'un connaît l'algorithme, il ne peut pas deviner tes mots de passe sans ton mot de passe maître.</p>
    </div>
  </div>

  <div class="section-card">
    <h2>Applications Complémentaires</h2>

   <h3>GUI (Interface Graphique)</h3>
    <div class="code-block">
<code><span class="command"># Installer l'interface graphique</span>
yay -S masterpassword-gui</code>
    </div>

   <h3>Extensions Navigateur</h3>
    <ul>
      <li><strong>Firefox</strong> : Master Password for Firefox</li>
      <li><strong>Chrome</strong> : Master Password for Chrome</li>
    </ul>

   <h3>Apps Mobiles</h3>
    <ul>
      <li><strong>Android</strong> : Master Password disponible sur F-Droid</li>
      <li><strong>iOS</strong> : Spectre (version moderne de Master Password)</li>
    </ul>
  </div>

  <div class="footer-nav">
    <a href="{{ site.baseurl }}/my-lab/archlinux" class="nav-button">← Retour Arch Linux</a>
    <a href="https://masterpassword.app/" target="_blank" class="nav-button">Site Officiel 🔐</a>
  </div>
</div>

<script>
document.addEventListener('DOMContentLoaded', function() {
  const binaryContainer = document.querySelector('.binary-background');
  
  for (let i = 0; i < 80; i++) {
    const digit = document.createElement('div');
    digit.className = 'binary-digit';
    digit.textContent = Math.random() > 0.5 ? '1' : '0';
    digit.style.left = Math.random() * 100 + 'vw';
    digit.style.fontSize = (Math.random() * 18 + 12) + 'px';
    digit.style.animationDuration = (Math.random() * 10 + 5) + 's';
    digit.style.animationDelay = Math.random() * 5 + 's';
    digit.style.opacity = Math.random() * 0.2 + 0.05;
    const colors = ['rgba(59, 130, 246, 0.15)', 'rgba(96, 165, 250, 0.15)'];
    digit.style.color = colors[Math.floor(Math.random() * colors.length)];
    binaryContainer.appendChild(digit);
  }
});
</script>
