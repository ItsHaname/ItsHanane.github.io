<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>TryHackMe - Junior Penetration Tester Path</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

   body {
      font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
      background: #0a0e1a;
      color: #e2e8f0;
      line-height: 1.6;
    }

   .container {
      max-width: 900px;
      margin: 0 auto;
      padding: 60px 30px;
    }

    /* Hero Section */
  .hero {
      text-align: center;
      margin-bottom: 60px;
      padding-bottom: 40px;
      border-bottom: 2px solid rgba(220, 38, 38, 0.3);
    }

  .platform-badge {
      display: inline-block;
      padding: 10px 25px;
      background: rgba(220, 38, 38, 0.2);
      color: #ef4444;
      font-size: 1em;
      font-weight: 700;
      border-radius: 20px;
      margin-bottom: 20px;
      border: 1px solid rgba(220, 38, 38, 0.3);
      letter-spacing: 2px;
    }

   .hero h1 {
      font-size: 2.5em;
      color: #fff;
      margin-bottom: 10px;
    }

  .hero .subtitle {
      font-size: 1.3em;
      color: #ef4444;
      margin-bottom: 30px;
    }

    /* Profile Badge */
  .profile-section {
      text-align: center;
      margin: 40px 0;
    }

   .profile-section iframe {
      border: none;
      max-width: 100%;
    }

    /* Terminal Section */
   .terminal {
      background: rgba(15, 23, 42, 0.6);
      border: 1px solid rgba(220, 38, 38, 0.3);
      border-radius: 12px;
      padding: 25px;
      margin: 40px 0;
      font-family: 'Courier New', monospace;
    }

  .terminal-header {
      display: flex;
      gap: 8px;
      margin-bottom: 15px;
    }

  .terminal-dot {
      width: 10px;
      height: 10px;
      border-radius: 50%;
    }

   .terminal-dot.red { background: #ff5f56; }
    .terminal-dot.yellow { background: #ffbd2e; }
    .terminal-dot.green { background: #27c93f; }

   .terminal-text {
      color: #ef4444;
      line-height: 1.8;
      font-size: 0.95em;
    }

   .prompt {
      color: #dc2626;
      font-weight: bold;
    }

    /* Section Title */
   h2 {
      color: #ef4444;
      font-size: 2em;
      margin: 50px 0 30px;
      padding-bottom: 10px;
      border-bottom: 2px solid rgba(220, 38, 38, 0.3);
    }

    /* Modules Grid */
   .modules-grid {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 20px;
      margin: 30px 0;
    }

  .module-card {
      background: rgba(15, 23, 42, 0.6);
      border: 1px solid rgba(220, 38, 38, 0.3);
      border-radius: 12px;
      padding: 25px;
      transition: all 0.3s ease;
      position: relative;
    }

   .module-card:hover {
      border-color: #dc2626;
      transform: translateY(-5px);
      box-shadow: 0 8px 25px rgba(220, 38, 38, 0.3);
    }

   .module-number {
      position: absolute;
      top: 15px;
      right: 15px;
      background: rgba(220, 38, 38, 0.2);
      color: #ef4444;
      padding: 5px 12px;
      border-radius: 15px;
      font-size: 0.85em;
      font-weight: 700;
      border: 1px solid rgba(220, 38, 38, 0.3);
    }

   .module-icon {
      font-size: 2.5em;
      margin-bottom: 15px;
      display: block;
      color: #dc2626;
      font-weight: 700;
    }

   .module-card h3 {
      color: #fff;
      font-size: 1.3em;
      margin-bottom: 10px;
    }

  .module-description {
      color: #cbd5e1;
      font-size: 0.95em;
      line-height: 1.6;
      margin-bottom: 15px;
    }

  .module-status {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      background: rgba(220, 38, 38, 0.15);
      padding: 6px 14px;
      border-radius: 15px;
      font-size: 0.85em;
      color: #ef4444;
      border: 1px solid rgba(220, 38, 38, 0.3);
    }

   .status-dot {
      width: 6px;
      height: 6px;
      background: #dc2626;
      border-radius: 50%;
    }

    /* Coming Soon */
   .coming-soon {
      text-align: center;
      padding: 50px 20px;
      background: rgba(15, 23, 42, 0.6);
      border-radius: 12px;
      border: 2px dashed rgba(220, 38, 38, 0.3);
      margin: 50px 0;
    }

  .coming-soon h2 {
      border: none;
      margin: 0 0 15px 0;
      padding: 0;
    }

   .coming-soon p {
      color: #cbd5e1;
      font-size: 1.1em;
      margin: 10px 0;
    }

  .coming-soon .highlight {
      color: #ef4444;
      font-weight: 600;
    }

    /* Footer */
  .footer {
      text-align: center;
      margin-top: 60px;
      padding: 30px;
      background: rgba(15, 23, 42, 0.6);
      border-radius: 12px;
      border: 1px solid rgba(220, 38, 38, 0.3);
    }

   .footer p {
      color: #cbd5e1;
      line-height: 1.8;
    }

   .footer .highlight {
      color: #ef4444;
      font-weight: 600;
    }

    /* Responsive */
   @media (max-width: 768px) {
      .container {
        padding: 40px 20px;
      }

  .hero h1 {
        font-size: 2em;
      }

  .modules-grid {
        grid-template-columns: 1fr;
      }
    }
  </style>
</head>
<body>
  <div class="container">
    <!-- Hero Section -->
    <div class="hero">
      <div class="platform-badge">TRYHACKME</div>
      <h1>Junior Penetration Tester</h1>
      <p class="subtitle">Path Progress & Notes</p>
    </div>

    <!-- Profile Section -->
   <div class="profile-section">
      <iframe src="https://tryhackme.com/api/v2/badges/public-profile?userPublicId=3165378"></iframe>
    </div>

    <!-- Terminal Info -->
   <div class="terminal">
      <div class="terminal-header">
        <div class="terminal-dot red"></div>
        <div class="terminal-dot yellow"></div>
        <div class="terminal-dot green"></div>
      </div>
      <div class="terminal-text">
        <span class="prompt">haname@tryhackme:~$</span> cat path_info.txt<br>
        → Path: Junior Penetration Tester<br>
        → Modules: 8 sections complètes<br>
        → Focus: Pentesting, Web Hacking, Privilege Escalation<br>
        → Status: En cours...
      </div>
    </div>

    <!-- Modules Section -->
   <h2>Modules du Path</h2>

   <div class="modules-grid">
      <div class="module-card">
        <span class="module-number">M1</span>
        <div class="module-icon">01</div>
        <h3>Introduction to Cyber Security</h3>
        <p class="module-description">Understand what is offensive and defensive security, and learn about careers available in cyber.</p>
        <div class="module-status">
          <span class="status-dot"></span>
          Notes à venir
        </div>
      </div>

  <div class="module-card">
        <span class="module-number">M2</span>
        <div class="module-icon">02</div>
        <h3>Introduction to Pentesting</h3>
        <p class="module-description">Understand what a penetration test involves, including testing techniques and methodologies every pentester should know.</p>
        <div class="module-status">
          <span class="status-dot"></span>
          Notes à venir
        </div>
      </div>

   <div class="module-card">
        <span class="module-number">M3</span>
        <div class="module-icon">03</div>
        <h3>Introduction to Web Hacking</h3>
        <p class="module-description">Get hands-on, learn about and exploit some of the most popular web application vulnerabilities seen in the industry today.</p>
        <div class="module-status">
          <span class="status-dot"></span>
          Notes à venir
        </div>
      </div>

  <div class="module-card">
        <span class="module-number">M4</span>
        <div class="module-icon">04</div>
        <h3>Burp Suite</h3>
        <p class="module-description">Burp Suite is the industry standard tool for web application hacking, and is essential in any web penetration test.</p>
        <div class="module-status">
          <span class="status-dot"></span>
          Notes à venir
        </div>
      </div>

  <div class="module-card">
        <span class="module-number">M5</span>
        <div class="module-icon">05</div>
        <h3>Network Security</h3>
        <p class="module-description">Learn the basics of passive and active network reconnaissance. Understand how common protocols work and their attack vectors.</p>
        <div class="module-status">
          <span class="status-dot"></span>
          Notes à venir
        </div>
      </div>

   <div class="module-card">
        <span class="module-number">M6</span>
        <div class="module-icon">06</div>
        <h3>Vulnerability Research</h3>
        <p class="module-description">Familiarise yourself with the skills, research methods, and resources used to exploit vulnerable applications and systems.</p>
        <div class="module-status">
          <span class="status-dot"></span>
          Notes à venir
        </div>
      </div>

   <div class="module-card">
        <span class="module-number">M7</span>
        <div class="module-icon">07</div>
        <h3>Metasploit</h3>
        <p class="module-description">Metasploit is the most widely used exploitation framework. Learn how to use it and unlock its full potential.</p>
        <div class="module-status">
          <span class="status-dot"></span>
          Notes à venir
        </div>
      </div>

  <div class="module-card">
        <span class="module-number">M8</span>
        <div class="module-icon">08</div>
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
      <h2>Notes & Write-ups</h2>
      <p>Detailed notes and write-ups for each module will be added as I progress through the path.</p>
      <p><span class="highlight">Continuous learning and documentation in progress.</span></p>
    </div>

    <!-- Footer -->
   <div class="footer">
      <p>
        Path: <span class="highlight">Junior Penetration Tester</span><br>
        Platform: <span class="highlight">TryHackMe</span><br>
        Status: <span class="highlight">In Progress</span>
      </p>
    </div>
  </div>
</body>
</html>
