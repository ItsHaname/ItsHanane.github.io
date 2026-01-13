---
layout: default
title: About
nav: about
---

<style>
@keyframes matrixRain {
    0% { transform: translateY(-100vh); }
    100% { transform: translateY(100vh); }
}

@keyframes float {
    0%, 100% { transform: translateY(0px); }
    50% { transform: translateY(-15px); }
}

@keyframes gradientShift {
    0% { background-position: 0% 50%; }
    50% { background-position: 100% 50%; }
    100% { background-position: 0% 50%; }
}

@keyframes blink {
    0%, 100% { opacity: 1; }
    50% { opacity: 0; }
}

@keyframes glowPulse {
    0%, 100% { 
        box-shadow: 0 0 20px rgba(59, 130, 246, 0.4),
                    0 0 40px rgba(59, 130, 246, 0.2),
                    inset 0 0 20px rgba(59, 130, 246, 0.1);
    }
    50% { 
        box-shadow: 0 0 40px rgba(59, 130, 246, 0.6),
                    0 0 80px rgba(59, 130, 246, 0.4),
                    inset 0 0 30px rgba(59, 130, 246, 0.2);
    }
}

@keyframes slideInLeft {
    from { opacity: 0; transform: translateX(-80px); }
    to { opacity: 1; transform: translateX(0); }
}

@keyframes slideInRight {
    from { opacity: 0; transform: translateX(80px); }
    to { opacity: 1; transform: translateX(0); }
}

@keyframes borderRun {
    0% { background-position: 0% 0%; }
    100% { background-position: 200% 0%; }
}

@keyframes scaleIn {
    from { transform: scale(0.8); opacity: 0; }
    to { transform: scale(1); opacity: 1; }
}

@keyframes textGlow {
    0%, 100% { text-shadow: 0 0 10px rgba(59, 130, 246, 0.5); }
    50% { text-shadow: 0 0 20px rgba(59, 130, 246, 0.8), 0 0 30px rgba(96, 165, 250, 0.6); }
}

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    background: #0a0e1a;
    min-height: 100vh;
    margin: 0;
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
    color: #e2e8f0;
    overflow-x: hidden;
    position: relative;
}

body::before {
    content: '';
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: 
        radial-gradient(ellipse at top, rgba(59, 130, 246, 0.1) 0%, transparent 50%),
        radial-gradient(ellipse at bottom, rgba(96, 165, 250, 0.05) 0%, transparent 50%);
    pointer-events: none;
    z-index: 0;
}

.binary-background {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    pointer-events: none;
    z-index: 0;
    overflow: hidden;
}

.binary-digit {
    position: absolute;
    font-family: 'Courier New', monospace;
    font-size: 16px;
    color: rgba(59, 130, 246, 0.15);
    opacity: 0;
    animation: matrixRain linear infinite;
}

.about-container {
    max-width: 1400px;
    margin: 0 auto;
    padding: 80px 30px;
    position: relative;
    z-index: 1;
}

.main-layout {
    display: grid;
    grid-template-columns: 450px 1fr;
    gap: 80px;
    align-items: start;
}

/* Left Column - Profile */
.profile-sidebar {
    position: sticky;
    top: 40px;
    animation: slideInLeft 1.2s cubic-bezier(0.34, 1.56, 0.64, 1);
}

.profile-card {
    background: rgba(15, 23, 42, 0.95);
    border: 2px solid transparent;
    background-image: 
        linear-gradient(rgba(15, 23, 42, 0.95), rgba(15, 23, 42, 0.95)),
        linear-gradient(135deg, #3b82f6, #60a5fa, #3b82f6);
    background-origin: border-box;
    background-clip: padding-box, border-box;
    border-radius: 25px;
    padding: 50px;
    text-align: center;
    position: relative;
    overflow: hidden;
}

.profile-card::before {
    content: '';
    position: absolute;
    top: -2px;
    left: -2px;
    right: -2px;
    bottom: -2px;
    background: linear-gradient(45deg, #3b82f6, #60a5fa, #3b82f6, #60a5fa);
    background-size: 300% 300%;
    border-radius: 25px;
    z-index: -1;
    animation: borderRun 4s linear infinite;
    opacity: 0;
    transition: opacity 0.3s ease;
}

.profile-card:hover::before {
    opacity: 1;
}

.profile-image-wrapper {
    position: relative;
    width: 280px;
    height: 280px;
    margin: 0 auto 35px;
}

.profile-image-wrapper::before {
    content: '';
    position: absolute;
    top: -15px;
    left: -15px;
    right: -15px;
    bottom: -15px;
    border: 2px solid #3b82f6;
    border-radius: 50%;
    opacity: 0.3;
    animation: glowPulse 3s ease-in-out infinite;
}

.profile-image-wrapper::after {
    content: '';
    position: absolute;
    top: -25px;
    left: -25px;
    right: -25px;
    bottom: -25px;
    border: 1px solid #60a5fa;
    border-radius: 50%;
    opacity: 0.2;
    animation: glowPulse 3s ease-in-out infinite 0.5s;
}

.profile-image {
    width: 280px;
    height: 280px;
    border-radius: 50%;
    overflow: hidden;
    border: 4px solid #3b82f6;
    animation: float 6s ease-in-out infinite;
    transition: all 0.5s cubic-bezier(0.34, 1.56, 0.64, 1);
    position: relative;
    z-index: 1;
}

.profile-image:hover {
    transform: scale(1.05) rotate(2deg);
    border-color: #60a5fa;
    box-shadow: 0 15px 40px rgba(59, 130, 246, 0.5);
}

.profile-image img {
    width: 100%;
    height: 100%;
    object-fit: cover;
}

.profile-name {
    font-size: 2.2em;
    font-weight: 700;
    background: linear-gradient(135deg, #60a5fa, #3b82f6, #60a5fa);
    background-size: 200% auto;
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    margin-bottom: 12px;
    animation: gradientShift 4s ease infinite, textGlow 2s ease-in-out infinite;
}

.profile-title {
    color: #94a3b8;
    font-size: 1.05em;
    margin-bottom: 30px;
    line-height: 1.7;
    font-weight: 300;
}

.profile-divider {
    width: 80px;
    height: 3px;
    background: linear-gradient(90deg, transparent, #3b82f6, #60a5fa, #3b82f6, transparent);
    margin: 30px auto;
    border-radius: 2px;
}

.profile-info {
    text-align: left;
    margin-top: 35px;
    background: rgba(30, 41, 59, 0.4);
    border-radius: 15px;
    padding: 25px;
    border: 1px solid rgba(59, 130, 246, 0.2);
}

.info-row {
    display: flex;
    justify-content: space-between;
    padding: 16px 0;
    border-bottom: 1px solid rgba(59, 130, 246, 0.15);
    transition: all 0.3s ease;
}

.info-row:hover {
    padding-left: 10px;
    border-bottom-color: #3b82f6;
}

.info-row:last-child {
    border-bottom: none;
}

.info-label {
    color: #94a3b8;
    font-size: 0.9em;
    font-weight: 500;
}

.info-value {
    color: #60a5fa;
    font-weight: 600;
    font-size: 0.95em;
    text-shadow: 0 0 10px rgba(96, 165, 250, 0.3);
}

/* Right Column - Content */
.content-area {
    animation: slideInRight 1.2s cubic-bezier(0.34, 1.56, 0.64, 1) 0.2s both;
}

.content-header {
    margin-bottom: 50px;
    position: relative;
}

.content-header h1 {
    font-size: 3.5em;
    background: linear-gradient(120deg, #60a5fa 0%, #3b82f6 50%, #2563eb 100%);
    background-size: 200% auto;
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    animation: gradientShift 3s ease infinite;
    font-weight: 800;
    letter-spacing: 3px;
    margin-bottom: 20px;
    line-height: 1.2;
}

.content-tagline {
    font-size: 1.5em;
    color: #94a3b8;
    font-weight: 300;
    letter-spacing: 1px;
}

.content-tagline::after {
    content: '_';
    animation: blink 1s infinite;
    color: #60a5fa;
    font-weight: 700;
}

.content-section {
    background: rgba(15, 23, 42, 0.9);
    border: 1px solid rgba(59, 130, 246, 0.3);
    border-radius: 25px;
    padding: 55px;
    margin-bottom: 35px;
    transition: all 0.4s cubic-bezier(0.34, 1.56, 0.64, 1);
    position: relative;
    overflow: hidden;
    animation: scaleIn 0.6s ease-out;
}

.content-section::before {
    content: '';
    position: absolute;
    top: 0;
    left: -100%;
    width: 100%;
    height: 100%;
    background: linear-gradient(90deg, transparent, rgba(59, 130, 246, 0.1), transparent);
    transition: left 0.5s ease;
}

.content-section:hover::before {
    left: 100%;
}

.content-section:hover {
    border-color: #3b82f6;
    box-shadow: 0 10px 30px rgba(59, 130, 246, 0.3);
    transform: translateY(-3px);
}

.content-section h2 {
    color: #60a5fa;
    font-size: 2em;
    margin-bottom: 30px;
    font-weight: 700;
    display: flex;
    align-items: center;
    gap: 15px;
    text-shadow: 0 0 20px rgba(59, 130, 246, 0.3);
}

.content-section h2::before {
    content: '';
    width: 5px;
    height: 35px;
    background: linear-gradient(180deg, #3b82f6, #60a5fa);
    border-radius: 3px;
    box-shadow: 0 0 10px rgba(59, 130, 246, 0.5);
}

.content-section p {
    color: #cbd5e1;
    line-height: 2;
    font-size: 1.1em;
    margin-bottom: 20px;
}

.highlight {
    color: #60a5fa;
    font-weight: 700;
    text-shadow: 0 0 10px rgba(96, 165, 250, 0.4);
    position: relative;
}

.focus-vertical {
    display: flex;
    flex-direction: column;
    gap: 18px;
    margin-top: 35px;
}

.focus-item {
    background: linear-gradient(135deg, rgba(30, 41, 59, 0.6), rgba(30, 41, 59, 0.4));
    border: 2px solid rgba(59, 130, 246, 0.2);
    border-radius: 15px;
    padding: 30px;
    transition: all 0.4s cubic-bezier(0.34, 1.56, 0.64, 1);
    position: relative;
    overflow: hidden;
}

.focus-item::before {
    content: '';
    position: absolute;
    left: 0;
    top: 0;
    width: 4px;
    height: 0;
    background: linear-gradient(180deg, #3b82f6, #60a5fa);
    transition: height 0.4s ease;
}

.focus-item:hover::before {
    height: 100%;
}

.focus-item:hover {
    background: linear-gradient(135deg, rgba(30, 41, 59, 0.9), rgba(30, 41, 59, 0.7));
    border-color: #3b82f6;
    transform: translateX(8px);
    box-shadow: -5px 0 20px rgba(59, 130, 246, 0.2);
}

.focus-item h3 {
    color: #60a5fa;
    font-size: 1.3em;
    margin-bottom: 12px;
    font-weight: 700;
    display: flex;
    align-items: center;
    gap: 10px;
}

.focus-item h3::before {
    content: '▸';
    color: #3b82f6;
    font-size: 1.2em;
    transition: transform 0.3s ease;
}

.focus-item:hover h3::before {
    transform: translateX(3px);
}

.focus-item p {
    color: #94a3b8;
    font-size: 1em;
    line-height: 1.7;
    margin: 0;
}

/* Responsive */
@media (max-width: 1024px) {
    .main-layout {
        grid-template-columns: 1fr;
        gap: 60px;
    }
    
    .profile-sidebar {
        position: relative;
        top: 0;
    }
    
    .content-header h1 {
        font-size: 2.8em;
    }
}

@media (max-width: 768px) {
    .content-header h1 {
        font-size: 2.2em;
    }
    
    .profile-image-wrapper {
        width: 200px;
        height: 200px;
    }
    
    .profile-image {
        width: 200px;
        height: 200px;
    }
    
    .content-section {
        padding: 35px;
    }
}
</style>

<div class="binary-background" id="binaryBg"></div>

<div class="about-container">
    <div class="main-layout">
        <!-- Left Sidebar - Profile -->
        <aside class="profile-sidebar">
            <div class="profile-card">
                <div class="profile-image-wrapper">
                    <div class="profile-image">
                        <img src="https://github.com/user-attachments/assets/6c553521-15b0-4d1a-aa6f-798d79f1c896" alt="Hanane AIT BAH">
                    </div>
                </div>
                
   <h2 class="profile-name">HANANE</h2>
                <p class="profile-title">Network Security Student<br>Cybersecurity Enthusiast</p>
                
   <div class="profile-divider"></div>
         
 <div class="profile-info">
                    <div class="info-row">
                        <span class="info-label">Location</span>
                        <span class="info-value">Marrakech</span>
                    </div>
                    <div class="info-row">
                        <span class="info-label">University</span>
                        <span class="info-value">FSSM</span>
                    </div>
                    <div class="info-row">
                        <span class="info-label">Program</span>
                        <span class="info-value">NSC</span>
                    </div>
                    <div class="info-row">
                        <span class="info-label">Blog Launch</span>
                        <span class="info-value">Jan 2026</span>
                    </div>
                </div>
            </div>
        </aside>

        <!-- Right Content Area -->
  <main class="content-area">
            <div class="content-header">
                <h1>WELCOME TO CYBERIA</h1>
                <p class="content-tagline">My Personal Cybersecurity Journey</p>
            </div>

  <section class="content-section">
           <h2>About Me</h2>
                <p>
                    I'm <span class="highlight">Hanane</span>, a cybersecurity student at FSSM, Cadi Ayyad University, pursuing a Bachelor's in Networking and Cybersecurity. Passionate about <span class="highlight">offensive security</span>, <span class="highlight">vulnerability analysis</span>, and <span class="highlight">reverse engineering</span>.
                </p>
                <p>
                    This blog documents my journey through the world of cybersecurity—from academic courses to hands-on labs, from TryHackMe challenges to building my own security testing environment.
                </p>
            </section>

 <section class="content-section">
                <h2>What You'll Find Here</h2>
                <div class="focus-vertical">
                    <div class="focus-item">
                        <h3>Academic Notes</h3>
                        <p>Course materials and university projects from NSC</p>
                    </div>
                    
<div class="focus-item">
                        <h3>TryHackMe</h3>
                        <p>Write-ups and walkthroughs from challenges</p>
                    </div>
                    
  <div class="focus-item">
                        <h3>Personal Lab</h3>
                        <p>Home lab setups and experiments</p>
                    </div>
      
  <div class="focus-item">
                        <h3>Learning Journey</h3>
                        <p>Reflections and discoveries</p>
                    </div>
                </div>
            </section>
        </main>
    </div>
</div>

<script>
function createBinaryBackground() {
    const container = document.getElementById('binaryBg');
    const binaryChars = ['0', '1'];
    const numberOfDigits = 50;

    for (let i = 0; i < numberOfDigits; i++) {
        const digit = document.createElement('div');
        digit.className = 'binary-digit';
        digit.textContent = binaryChars[Math.floor(Math.random() * 2)];
        digit.style.left = Math.random() * 100 + '%';
        digit.style.animationDuration = (Math.random() * 10 + 10) + 's';
        digit.style.animationDelay = Math.random() * 5 + 's';
        digit.style.opacity = Math.random() * 0.5 + 0.1;
        container.appendChild(digit);
    }
}

createBinaryBackground();
</script>
