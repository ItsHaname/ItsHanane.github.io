---
layout: default
title: TryHackMe
nav: tryhackme
---

<style>
:root {
  --cyber-teal: #00ffff;
  --cyber-purple: #9d00ff;
  --cyber-pink: #ff00ff;
  --dark-bg: #0a0a0a;
  --darker-bg: #050505;
  --card-bg: rgba(15, 15, 25, 0.9);
}

body {
  background-color: var(--dark-bg);
  color: #e0e0e0;
  font-family: 'Segoe UI', system-ui, sans-serif;
  margin: 0;
  padding: 0;
  line-height: 1.6;
}

.container {
  max-width: 900px;
  margin: 0 auto;
  padding: 2rem;
}

/* Header */
.header {
  text-align: center;
  padding: 2rem 0;
  margin-bottom: 3rem;
  border-bottom: 1px solid rgba(0, 255, 255, 0.3);
}

.title {
  font-size: 3rem;
  color: var(--cyber-teal);
  margin-bottom: 0.5rem;
  font-weight: 300;
  letter-spacing: -1px;
}

.subtitle {
  color: var(--cyber-pink);
  font-size: 1.1rem;
  opacity: 0.9;
}

/* Content styling */
.content {
  background: var(--card-bg);
  border-radius: 8px;
  padding: 3rem;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.3);
  border: 1px solid rgba(0, 255, 255, 0.1);
}

h1 {
  color: var(--cyber-teal);
  font-size: 2.5rem;
  margin-top: 3rem;
  margin-bottom: 1rem;
  padding-bottom: 0.5rem;
  border-bottom: 2px solid rgba(157, 0, 255, 0.3);
}

h1:first-of-type {
  margin-top: 0;
}

h2 {
  color: var(--cyber-purple);
  font-size: 1.8rem;
  margin-top: 2.5rem;
  margin-bottom: 1rem;
  font-weight: 500;
}

h3 {
  color: var(--cyber-pink);
  font-size: 1.4rem;
  margin-top: 2rem;
  margin-bottom: 0.8rem;
  font-weight: 500;
  padding-left: 1rem;
  border-left: 3px solid var(--cyber-pink);
}

p {
  margin-bottom: 1.5rem;
  font-size: 1.1rem;
  color: #cccccc;
}

/* Decorative elements */
.decorative-line {
  height: 1px;
  background: linear-gradient(90deg, 
    transparent, 
    var(--cyber-teal), 
    var(--cyber-purple), 
    var(--cyber-pink),
    transparent);
  margin: 2rem 0;
  opacity: 0.5;
}

.badge {
  display: inline-block;
  background: rgba(0, 255, 255, 0.1);
  color: var(--cyber-teal);
  padding: 0.3rem 0.8rem;
  border-radius: 4px;
  font-size: 0.9rem;
  margin: 0 0.3rem 0.5rem 0;
  border: 1px solid rgba(0, 255, 255, 0.3);
}

/* Footer */
.footer {
  text-align: center;
  margin-top: 4rem;
  padding: 2rem;
  color: rgba(255, 255, 255, 0.5);
  font-size: 0.9rem;
  border-top: 1px solid rgba(255, 255, 255, 0.1);
}

/* Responsive */
@media (max-width: 768px) {
  .container {
    padding: 1rem;
  }
  
  .content {
    padding: 1.5rem;
  }
  
  .title {
    font-size: 2.2rem;
  }
  
  h1 {
    font-size: 2rem;
  }
  
  h2 {
    font-size: 1.5rem;
  }
}
</style>

<div class="container">
  
  <div class="header">
    <h1 class="title">TryHackMe Learning Path</h1>
    <div class="subtitle">My Cybersecurity Curriculum & Progress</div>
  </div>
  
  <div class="content">
    
  <h1>Introduction to Cyber Security</h1>
    <p>Understand what is offensive and defensive security, and learn about careers available in cyber.</p>
    
   <div class="decorative-line"></div>
    
   <h2>Introduction to Pentesting</h2>
    <p>Understand what a penetration test involves, including testing techniques and methodologies every pentester should know.</p>
    
   <div class="decorative-line"></div>
    
  <h2>Introduction to Web Hacking</h2>
    <p>Get hands-on, learn about and exploit some of the most popular web application vulnerabilities seen in the industry today.</p>
    
   <h3>Burp Suite</h3>
    <p>Burp Suite is the industry standard tool for web application hacking, and is essential in any web penetration test.</p>
    
   <h3>Network Security</h3>
    <p>Learn the basics of passive and active network reconnaissance. Understand how common protocols work and their attack vectors.</p>
    
  <h3>Vulnerability Research</h3>
    <p>Familiarise yourself with the skills, research methods, and resources used to exploit vulnerable applications and systems.</p>
    
  <h3>Metasploit</h3>
    <p>Metasploit is the most widely used exploitation framework. Learn how to use it and unlock its full potential.</p>
    
  <h3>Privilege Escalation</h3>
    <p>Learn the fundamental techniques that will allow you to elevate account privileges in Linux and windows systems.</p>
    
  </div>
  
  <div class="footer">
    <p>TryHackMe Profile: <span style="color: var(--cyber-teal);">@3165378</span> | Status: <span style="color: var(--cyber-pink);">Active Learning</span></p>
  </div>
  
</div>
