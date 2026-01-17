---
layout: default
title: About
nav: about
---

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
    border-bottom: 2px solid rgba(59, 130, 246, 0.2);
}

.hero img {
    width: 280px;
    height: 280px;
    border-radius: 50%;
    border: 5px solid #3b82f6;
    margin: 0 auto 30px;
    object-fit: cover;
    object-position: center 35%;
    display: block;
    box-shadow: 0 10px 40px rgba(59, 130, 246, 0.4);
    background: #0a0e1a;
    transform: scale(1.15);
}

.hero h1 {
    font-size: 2.5em;
    color: #fff;
    margin-bottom: 10px;
}

.hero .role {
    font-size: 1.3em;
    color: #60a5fa;
    margin-bottom: 20px;
}

.hero .bio {
    font-size: 1.1em;
    color: #cbd5e1;
    max-width: 700px;
    margin: 0 auto 30px;
}

.highlight {
    color: #60a5fa;
    font-weight: 600;
}

.stats {
    display: flex;
    justify-content: center;
    gap: 50px;
    margin-top: 30px;
}

.stat {
    text-align: center;
}

.stat-value {
    font-size: 1.8em;
    color: #60a5fa;
    font-weight: 700;
    display: block;
}

.stat-label {
    color: #94a3b8;
    font-size: 0.95em;
}

/* Section */
section {
    margin-bottom: 50px;
}

section h2 {
    color: #60a5fa;
    font-size: 2em;
    margin-bottom: 25px;
    padding-bottom: 10px;
    border-bottom: 2px solid rgba(59, 130, 246, 0.3);
}

section p {
    color: #cbd5e1;
    margin-bottom: 15px;
    font-size: 1.05em;
}

/* Skills/Focus Areas */
.skills {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    margin-top: 20px;
}

.skill-tag {
    background: rgba(59, 130, 246, 0.15);
    color: #60a5fa;
    padding: 8px 16px;
    border-radius: 8px;
    border: 1px solid rgba(59, 130, 246, 0.3);
    font-size: 0.95em;
}

/* Education Timeline */
.timeline-item {
    margin-bottom: 30px;
    padding-left: 30px;
    border-left: 2px solid rgba(59, 130, 246, 0.3);
    position: relative;
}

.timeline-item::before {
    content: '';
    position: absolute;
    left: -6px;
    top: 5px;
    width: 10px;
    height: 10px;
    background: #3b82f6;
    border-radius: 50%;
}

.timeline-item h3 {
    color: #fff;
    font-size: 1.3em;
    margin-bottom: 5px;
}

.timeline-item .period {
    color: #60a5fa;
    font-size: 0.95em;
    margin-bottom: 10px;
}

/* Cards Grid */
.cards {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 20px;
    margin-top: 25px;
}

.card {
    background: rgba(15, 23, 42, 0.6);
    border: 1px solid rgba(59, 130, 246, 0.3);
    border-radius: 12px;
    padding: 25px;
}

.card h3 {
    color: #fff;
    font-size: 1.3em;
    margin-bottom: 8px;
}

.card .meta {
    color: #60a5fa;
    font-size: 0.9em;
    margin-bottom: 15px;
}

.card ul {
    list-style: none;
}

.card li {
    color: #cbd5e1;
    padding-left: 15px;
    position: relative;
    margin-bottom: 6px;
}

.card li::before {
    content: '▹';
    position: absolute;
    left: 0;
    color: #3b82f6;
}

/* Responsive */
@media (max-width: 768px) {
    .container {
        padding: 40px 20px;
    }

    .hero h1 {
        font-size: 2em;
    }

    .hero img {
        width: 150px;
        height: 150px;
    }

    .stats {
        flex-direction: column;
        gap: 20px;
    }

    .info-grid {
        grid-template-columns: 1fr;
    }

    .cards {
        grid-template-columns: 1fr;
    }
}
</style>

<div class="container">
    <!-- Hero Section -->
    <div class="hero">
        <img src="https://github.com/user-attachments/assets/6c553521-15b0-4d1a-aa6f-798d79f1c896" alt="Hanane AIT BAH">
        <h1>HANANE AIT BAH</h1>
        <p class="role">Network Security Student | Cybersecurity Enthusiast</p>
        <p class="bio">
            Passionate about <span class="highlight">offensive security</span>, <span class="highlight">vulnerability analysis</span>, and <span class="highlight">reverse engineering</span>. Currently pursuing a Bachelor's in Networking and Cybersecurity at FSSM, Cadi Ayyad University.
        </p>
        
 <div class="stats">
            <div class="stat">
                <span class="stat-value">2026</span>
                <span class="stat-label">Blog Launch</span>
            </div>
            <div class="stat">
                <span class="stat-value">NSC</span>
                <span class="stat-label">Program</span>
            </div>
            <div class="stat">
                <span class="stat-value">FSSM</span>
                <span class="stat-label">University</span>
            </div>
        </div>
    </div>

    <!-- Focus Areas -->
 <section>
        <h2>Focus Areas</h2>
        <div class="skills">
            <div class="skill-tag">Penetration Testing</div>
            <div class="skill-tag">Network Defense</div>
            <div class="skill-tag">Vulnerability Analysis</div>
            <div class="skill-tag">CTF Challenges</div>
            <div class="skill-tag">Linux Systems</div>
            <div class="skill-tag">Virtual Labs</div>
            <div class="skill-tag">TryHackMe</div>
            <div class="skill-tag">Security Research</div>
        </div>
    </section>

    <!-- Education -->
 <section>
        <h2>Education</h2>
        <div class="timeline-item">
            <h3>Bachelor's in Networking & Cybersecurity</h3>
            <p class="period">FSSM, Cadi Ayyad University | 2025-2026 - Present</p>
            <p>Specialized program focusing on network defense, penetration testing, and security protocols. Building strong foundations in system administration and threat analysis.</p>
        </div>
        <div class="timeline-item">
            <h3>Computer Science Foundations</h3>
            <p class="period">FSSM | 2023 - 2025</p>
            <p>Core studies in programming, algorithms, databases, and computer architecture. and technical fundamentals.</p>
        </div>
    </section>

    <!-- What You'll Find Here -->
  <section>
        <h2>What You'll Find Here</h2>
        <div class="cards">
            <div class="card">
                <h3>Academic Notes</h3>
                <p class="meta">NSC Program @ FSSM</p>
                <ul>
                    <li>Network security fundamentals</li>
                    <li>Course materials and study guides</li>
                    <li>University projects and labs</li>
                </ul>
            </div>
            
 <div class="card">
                <h3>TryHackMe Journey</h3>
                <p class="meta">Practical Cybersecurity Training</p>
                <ul>
                    <li>Completed challenges and rooms</li>
                    <li>Detailed write-ups and walkthroughs</li>
                    <li>Skills development tracking</li>
                </ul>
            </div>
            
  <div class="card">
                <h3>Personal Lab</h3>
                <p class="meta">Hands-On Learning Environment</p>
                <ul>
                    <li>Virtual machine configurations</li>
                    <li>Network topologies and setups</li>
                    <li>Security experiments and tests</li>
                </ul>
            </div>
            
   <div class="card">
                <h3>Learning Resources</h3>
                <p class="meta">Community & Knowledge Sharing</p>
                <ul>
                    <li>Curated study materials</li>
                    <li>Tools and software reviews</li>
                    <li>Security best practices</li>
                </ul>
            </div>
        </div>
    </section>

    <!-- About This Blog -->
 <section>
        <h2>About This Blog</h2>
        <p>
            On January 1st, 2026, I launched <span class="highlight">Cyberia</span> to document my journey through the world of cybersecurity. This blog serves as both a personal learning journal and a resource for others interested in the field.
        </p>
        <p>
            The content here reflects my academic path at FSSM, hands-on practice through platforms like TryHackMe, and my experiments in building a home lab for security testing. This is a living record of what I learn, the challenges I face, and the progress I make.
        </p>
        <p>
            Whether you're a fellow student, a cybersecurity enthusiast, or just curious about the field, I hope you find something useful here. Welcome to Cyberia.
        </p>
    </section>
</div>
