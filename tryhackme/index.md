<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>TryHackMe - Junior Penetration Tester Path</title>
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
      50% { text-shadow: 0 0 20px #dc2626, 0 0 40px #dc2626, 0 0 60px #991b1b; }
    }

   * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

   body {
      background: #0a0e1a;
      color: #e2e8f0;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      min-height: 100vh;
      padding: 20px;
    }

  .container {
      max-width: 1400px;
      margin: 0 auto;
      position: relative;
    }

   /* Particles background */
    .particles {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      pointer-events: none;
      z-index: -1;
      opacity: 0.4;
    }

   .particle {
      position: absolute;
      width: 3px;
      height: 3px;
      background: #dc2626;
      border-radius: 50%;
      animation: float 4s infinite ease-in-out;
    }

   /* Hero Section */
    .thm-hero {
      text-align: center;
      margin-bottom: 60px;
      padding: 60px 20px;
      background: linear-gradient(135deg, rgba(20, 0, 0, 0.9), rgba(40, 10, 10, 0.8));
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
      background: linear-gradient(45deg, #dc2626, #ef4444, #991b1b, #7f1d1d);
      background-size: 300% 300%;
      animation: gradientBG 4s ease infinite;
      border-radius: 30px;
      z-index: -1;
    }

  .platform-badge {
      display: inline-block;
      padding: 12px 35px;
      background: linear-gradient(135deg, #dc2626, #991b1b);
      color: white;
      font-size: 1.2em;
      font-weight: 700;
      border-radius: 50px;
      margin-bottom: 25px;
      box-shadow: 0 10px 30px rgba(220, 38, 38, 0.5);
      letter-spacing: 2px;
    }

   .thm-title {
      font-size: 4em;
      color: transparent;
      background: linear-gradient(90deg, #dc2626, #ef4444, #991b1b, #ef4444, #dc2626);
      background-size: 300% auto;
      -webkit-background-clip: text;
      background-clip: text;
      animation: gradientBG 3s ease infinite, glow 2s ease-in-out infinite;
      margin: 20px 0;
      font-weight: 900;
      letter-spacing: 3px;
      text-transform: uppercase;
    }

   .path-name {
      font-size: 1.8em;
      color: #ef4444;
      margin: 20px 0;
      font-style: italic;
      letter-spacing: 2px;
    }

   .path-name::after {
      content: '_';
      animation: blink 1s infinite;
      color: #dc2626;
    }

  /* Profile Section */
    .profile-section {
      margin: 50px 0 30px 0;
    }

  /* Terminal Section */
    .terminal-section {
      background: rgba(10, 14, 26, 0.95);
      border: 2px solid #dc2626;
      border-radius: 15px;
      padding: 25px;
      margin: 40px 0;
      font-family: 'Courier New', monospace;
      box-shadow: 0 0 30px rgba(220, 38, 38, 0.3);
    }

   .terminal-header {
      display: flex;
      gap: 8px;
      margin-bottom: 20px;
    }

   .terminal-dot {
      width: 12px;
      height: 12px;
      border-radius: 50%;
    }

   .terminal-dot.red { background: #ff5f56; }
    .terminal-dot.yellow { background: #ffbd2e; }
    .terminal-dot.green { background: #27c93f; }

  .terminal-text {
      color: #ef4444;
      line-height: 2;
    }

   .terminal-text .prompt {
      color: #dc2626;
      font-weight: bold;
    }

   .terminal-text .command {
      color: #ef4444;
    }

   /* Modules Grid */
    .modules-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
      gap: 30px;
      margin: 60px 0;
      perspective: 1000px;
    }

  .module-card {
      background: linear-gradient(135deg, rgba(15, 23, 42, 0.9), rgba(30, 41, 59, 0.8));
      border: 2px solid transparent;
      border-radius: 20px;
      padding: 35px;
      transition: all 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
      position: relative;
      text-decoration: none;
      color: inherit;
      display: block;
      animation: slideIn 0.8s ease-out backwards;
      transform-style: preserve-3d;
      overflow: hidden;
    }

   .module-card::before {
      content: '';
      position: absolute;
      top: -2px;
      left: -2px;
      right: -2px;
      bottom: -2px;
      background: linear-gradient(45deg, #dc2626, #ef4444, #991b1b, #7f1d1d);
      background-size: 300% 300%;
      animation: gradientBG 6s ease infinite;
      border-radius: 20px;
      z-index: -1;
      opacity: 0;
      transition: opacity 0.5s;
    }

   .module-card:hover::before {
      opacity: 1;
    }

   .module-card::after {
      content: '';
      position: absolute;
      top: 50%;
      left: 50%;
      width: 0;
      height: 0;
      border-radius: 50%;
      background: rgba(220, 38, 38, 0.3);
      transform: translate(-50%, -50%);
      transition: width 0.6s, height 0.6s;
    }

  .module-card:hover::after {
      width: 500px;
      height: 500px;
    }

   .module-card:hover {
      transform: translateY(-15px) rotateX(5deg) rotateY(5deg);
      box-shadow: 0 25px 60px rgba(220, 38, 38, 0.6);
    }

  .module-card:nth-child(1) { animation-delay: 0.1s; }
    .module-card:nth-child(2) { animation-delay: 0.2s; }
    .module-card:nth-child(3) { animation-delay: 0.3s; }
    .module-card:nth-child(4) { animation-delay: 0.4s; }
    .module-card:nth-child(5) { animation-delay: 0.5s; }
    .module-card:nth-child(6) { animation-delay: 0.6s; }
    .module-card:nth-child(7) { animation-delay: 0.7s; }
    .module-card:nth-child(8) { animation-delay: 0.8s; }

   .module-icon {
      font-size: 3em;
      margin-bottom: 20px;
      display: inline-block;
      animation: float 3s ease-in-out infinite;
      filter: drop-shadow(0 0 15px currentColor);
    }

 =   .module-number {
      position: absolute;
      top: 20px;
      right: 20px;
      background: rgba(220, 38, 38, 0.2);
      color: #ef4444;
      padding: 10px 18px;
      border-radius: 25px;
      font-size: 0.85em;
      font-weight: 900;
      border: 1px solid #dc2626;
      box-shadow: 0 0 15px rgba(220, 38, 38, 0.4);
      z-index: 1;
    }

   .module-card h3 {
      color: #ef4444;
      margin: 20px 0;
      font-size: 1.5em;
      font-weight: 700;
      position: relative;
      z-index: 1;
      text-shadow: 0 0 10px rgba(239, 68, 68, 0.5);
    }

 .module-status {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      background: rgba(220, 38, 38, 0.15);
      padding: 8px 16px;
      border-radius: 20px;
      font-size: 0.9em;
      color: #ef4444;
      border: 1px solid rgba(220, 38, 38, 0.3);
      margin-top: 15px;
      position: relative;
      z-index: 1;
    }

   .status-dot {
      width: 8px;
      height: 8px;
      background: #dc2626;
      border-radius: 50%;
      animation: pulse 2s infinite;
    }

  .module-description {
      color: #94a3b8;
      font-size: 0.95em;
      line-height: 1.6;
      margin-top: 15px;
      position: relative;
      z-index: 1;
    }

  .section-title {
      color: #ef4444;
      text-align: center;
      margin: 60px 0 40px 0;
      font-size: 2.5em;
      text-shadow: 0 0 20px rgba(220, 38, 38, 0.5);
    }

  .coming-soon {
      text-align: center;
      padding: 60px 20px;
      background: linear-gradient(135deg, rgba(40, 10, 10, 0.3), rgba(20, 0, 0, 0.2));
      border-radius: 20px;
      border: 2px dashed #dc2626;
      margin: 50px 0;
    }

   .coming-soon h2 {
      color: #ef4444;
      font-size: 2.5em;
      margin-bottom: 20px;
      animation: glow 2s ease-in-out infinite;
    }

   .coming-soon p {
      color: #94a3b8;
      font-size: 1.2em;
    }

  @media (max-width: 768px) {
      .thm-title {
        font-size: 2.5em;
      }
      
.path-name {
        font-size: 1.3em;
      }
      
 .modules-grid {
        grid-template-columns: 1fr;
      }
      
   .module-card:hover {
        transform: translateY(-10px);
      }
    }
  </style>
</head>
<body>
  <div class="particles" id="particles"></div>
  
  <div class="container">
    <!-- Hero Section -->
    <div class="thm-hero">
      <div class="platform-badge">TRYHACKME</div>
      <div class="thm-title">Junior Penetration Tester</div>
      <div class="path-name">Path Progress & Notes</div>
    </div>
 <!-- Profile Section -->
    <div class="profile-section">
      <iframe src="https://tryhackme.com/api/v2/badges/public-profile?userPublicId=3165378" style='border:none;'></iframe>
    </div>

   <!-- Terminal Info -->
  <div class="terminal-section">
      <div class="terminal-header">
        <div class="terminal-dot red"></div>
        <div class="terminal-dot yellow"></div>
        <div class="terminal-dot green"></div>
      </div>
      <div class="terminal-text">
        <span class="prompt">haname@tryhackme:~$</span> <span class="command">cat path_info.txt</span><br>
        → Path: Junior Penetration Tester<br>
        → Modules: 8 sections complètes<br>
        → Focus: Pentesting, Web Hacking, Privilege Escalation<br>
        → Status: En cours...<span style="animation: blink 1s infinite;">_</span>
      </div>
    </div>

    <!-- Modules Section -->
   
<h2 class="section-title">📚 Modules du Path</h2>

 div class="modules-grid">
      
  <div class="module-card">
        <span class="module-number">M1</span>
        <div class="module-icon">🖥️</div>
        <h3>Introduction to Cyber Security</h3>
        <p class="module-description">Understand what is offensive and defensive security, and learn about careers available in cyber.</p>
        <div class="module-status">
          <span class="status-dot"></span>
          Notes à venir
        </div>
      </div>

  <div class="module-card">
        <span class="module-number">M2</span>
        <div class="module-icon">⚔️</div>
        <h3>Introduction to Pentesting</h3>
        <p class="module-description">Understand what a penetration test involves, including testing techniques and methodologies every pentester should know.</p>
        <div class="module-status">
          <span class="status-dot"></span>
          Notes à venir
        </div>
      </div>

   <div class="module-card">
        <span class="module-number">M3</span>
        <div class="module-icon">🌐</div>
        <h3>Introduction to Web Hacking</h3>
        <p class="module-description">Get hands-on, learn about and exploit some of the most popular web application vulnerabilities seen in the industry today.</p>
        <div class="module-status">
          <span class="status-dot"></span>
          Notes à venir
        </div>
      </div>

   <div class="module-card">
        <span class="module-number">M4</span>
        <div class="module-icon">🔶</div>
        <h3>Burp Suite</h3>
        <p class="module-description">Burp Suite is the industry standard tool for web application hacking, and is essential in any web penetration test.</p>
        <div class="module-status">
          <span class="status-dot"></span>
          Notes à venir
        </div>
      </div>

   <div class="module-card">
        <span class="module-number">M5</span>
        <div class="module-icon">🔴</div>
        <h3>Network Security</h3>
        <p class="module-description">Learn the basics of passive and active network reconnaissance. Understand how common protocols work and their attack vectors.</p>
        <div class="module-status">
          <span class="status-dot"></span>
          Notes à venir
        </div>
      </div>

   <div class="module-card">
        <span class="module-number">M6</span>
        <div class="module-icon">💻</div>
        <h3>Vulnerability Research</h3>
        <p class="module-description">Familiarise yourself with the skills, research methods, and resources used to exploit vulnerable applications and systems.</p>
        <div class="module-status">
          <span class="status-dot"></span>
          Notes à venir
        </div>
      </div>

   <div class="module-card">
        <span class="module-number">M7</span>
        <div class="module-icon">Ⓜ️</div>
        <h3>Metasploit</h3>
        <p class="module-description">Metasploit is the most widely used exploitation framework. Learn how to use it and unlock its full potential.</p>
        <div class="module-status">
          <span class="status-dot"></span>
          Notes à venir
        </div>
      </div>
  <div class="module-card">
      <span class="module-number">M8</span>
        <div class="module-icon">🔓</div>
        <h3>Privilege Escalation</h3>
        <p class="module-description">Learn the fundamental techniques that will allow you to elevate account privileges in Linux and Windows systems.</p>
        <div class="module-status">
          <span class="status-dot"></span>
          Notes à venir
        </div>
      </div>

    </div>

  <!-- Coming Soon Section -->
   <div class="coming-soon">
      <h2>📝 Notes & Write-ups</h2>
      <p>Les notes détaillées et write-ups de chaque module seront ajoutés au fur et à mesure de ma progression.</p>
      <p style="margin-top: 15px; color: #ef4444;">Keep hacking, keep learning...</p>
    </div>

    <!-- Footer -->
   <div style="text-align: center; margin-top: 80px; padding: 40px; background: linear-gradient(135deg, rgba(15, 23, 42, 0.8), rgba(10, 14, 26, 0.9)); border-radius: 20px; border: 2px solid #7f1d1d;">
      <p style="color: #94a3b8; font-size: 1.1em; line-height: 1.8;">
        🎯 Path: <span style="color: #ef4444; font-weight: bold;">Junior Penetration Tester</span><br>
        🏆 Platform: <span style="color: #dc2626; font-weight: bold;">TryHackMe</span><br>
        💼 Progression: <span style="color: #ef4444; font-weight: bold;">En cours</span>
      </p>
    </div>

  </div>

  <script>
    // Create animated particles
    document.addEventListener('DOMContentLoaded', function() {
      const particlesDiv = document.getElementById('particles');
      
      for (let i = 0; i < 30; i++) {
        const particle = document.createElement('div');
        particle.className = 'particle';
        particle.style.left = Math.random() * 100 + '%';
        particle.style.top = Math.random() * 100 + '%';
        particle.style.animationDelay = Math.random() * 4 + 's';
        particle.style.animationDuration = (Math.random() * 3 + 3) + 's';
        particlesDiv.appendChild(particle);
      }
    });
  </script>
</body>
</html>
