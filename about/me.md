---
layout: default
title: À propos
nav: about
---

<style>
@keyframes floatParticle {
    0% { transform: translateY(-100vh) rotate(0deg); opacity: 0; }
    10% { opacity: 0.6; }
    90% { opacity: 0.6; }
    100% { transform: translateY(100vh) rotate(360deg); opacity: 0; }
}

@keyframes floatUpDown {
    0%, 100% { transform: translateY(0); }
    50% { transform: translateY(-20px); }
}

@keyframes fadeIn {
    from { opacity: 0; transform: translateY(30px); }
    to { opacity: 1; transform: translateY(0); }
}

@keyframes gradientShift {
    0% { background-position: 0% 50%; }
    50% { background-position: 100% 50%; }
    100% { background-position: 0% 50%; }
}

@keyframes pulse {
    0%, 100% { transform: scale(1); }
    50% { transform: scale(1.05); }
}

.about-page-wrapper {
    position: relative;
    min-height: 100vh;
    margin: 0;
    padding: 0;
    background: linear-gradient(135deg, #ffe0ec 0%, #ffd4e5 50%, #ffc9e0 100%);
}

.particle-background {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    pointer-events: none;
    z-index: 0;
    overflow: hidden;
}

.particle {
    position: absolute;
    font-size: 16px;
    opacity: 0;
    animation: floatParticle linear infinite;
    color: rgba(255, 182, 193, 0.25);
}

.particle.floating {
    animation: floatUpDown 5s ease-in-out infinite;
}

.about-container {
    max-width: 1100px;
    margin: 0 auto;
    padding: 60px 20px;
    position: relative;
    z-index: 1;
    color: #4a4a4a;
}

.about-header {
    text-align: center;
    margin-bottom: 60px;
    animation: fadeIn 1s ease-out;
}

.about-header h1 {
    font-size: 3em;
    background: linear-gradient(90deg, #ff69b4, #ff1493, #ff69b4);
    background-size: 200% auto;
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    animation: gradientShift 3s ease infinite;
    margin-bottom: 15px;
    font-weight: 700;
    letter-spacing: 3px;
}

.about-tagline {
    font-size: 1.2em;
    color: #c2588d;
    font-weight: 300;
}

.divider {
    width: 150px;
    height: 2px;
    background: linear-gradient(90deg, transparent, #ff69b4, #ff1493, #ff69b4, transparent);
    margin: 25px auto;
}

.profile-container {
    display: flex;
    gap: 50px;
    margin-bottom: 50px;
    animation: fadeIn 1.2s ease-out;
    align-items: flex-start;
}

.profile-left {
    display: flex;
    flex-direction: row;
    gap: 30px;
    flex: 1;
    align-items: center;
}

.profile-image {
    width: 280px;
    height: 280px;
    border-radius: 50%;
    overflow: hidden;
    border: 6px solid #ff69b4;
    box-shadow: 
        0 10px 40px rgba(255, 105, 180, 0.5),
        0 0 0 12px rgba(255, 182, 193, 0.3);
    background: #ffffff;
    transition: all 0.4s ease;
    flex-shrink: 0;
}

.profile-image:hover {
    transform: scale(1.05);
    box-shadow: 
        0 15px 50px rgba(255, 105, 180, 0.6),
        0 0 0 15px rgba(255, 182, 193, 0.4);
}

.profile-image img {
    width: 100%;
    height: 100%;
    object-fit: cover;
}

.quick-info {
    background: rgba(255, 255, 255, 0.95);
    border: 2px solid rgba(255, 105, 180, 0.4);
    border-radius: 15px;
    padding: 25px;
    flex: 1;
    text-align: left;
    box-shadow: 0 5px 20px rgba(255, 105, 180, 0.2);
    transition: all 0.3s ease;
}

.quick-info:hover {
    box-shadow: 0 8px 30px rgba(255, 105, 180, 0.35);
    border-color: #ff69b4;
}

.quick-info h3 {
    color: #ff1493;
    font-size: 1.3em;
    margin-bottom: 20px;
    font-weight: 600;
    border-bottom: 2px solid #ff69b4;
    padding-bottom: 10px;
}

.quick-info p {
    color: #5a5a5a;
    font-size: 0.95em;
    line-height: 1.8;
    margin-bottom: 10px;
    padding-left: 5px;
}

.quick-info strong {
    color: #ff69b4;
}

.about-section {
    background: rgba(255, 255, 255, 0.9);
    border: 2px solid rgba(255, 105, 180, 0.3);
    border-radius: 20px;
    padding: 45px;
    margin-bottom: 50px;
    box-shadow: 0 8px 30px rgba(255, 105, 180, 0.2);
    animation: fadeIn 1.4s ease-out;
}

.about-section h2 {
    color: #ff1493;
    font-size: 2.2em;
    margin-bottom: 25px;
    font-weight: 700;
    position: relative;
    display: inline-block;
}

.about-section h2:after {
    content: '';
    position: absolute;
    bottom: -8px;
    left: 0;
    width: 60%;
    height: 3px;
    background: linear-gradient(90deg, #ff1493, #ff69b4);
}

.about-section p {
    color: #5a5a5a;
    line-height: 1.9;
    margin-bottom: 18px;
    font-size: 1.05em;
}

.highlight {
    color: #ff69b4;
    font-weight: 600;
}

.section-title {
    color: #ff1493;
    font-size: 2em;
    margin: 60px 0 30px 0;
    font-weight: 700;
    text-align: center;
    letter-spacing: 1px;
}

.focus-areas {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 25px;
    margin-bottom: 50px;
}

.focus-card {
    background: rgba(255, 255, 255, 0.85);
    border: 2px solid rgba(255, 105, 180, 0.3);
    border-radius: 15px;
    padding: 30px;
    transition: all 0.3s ease;
    animation: fadeIn 1.4s ease-out;
}

.focus-card:hover {
    transform: translateY(-5px);
    box-shadow: 0 10px 30px rgba(255, 105, 180, 0.3);
    border-color: #ff69b4;
}

.focus-card h3 {
    color: #ff1493;
    font-size: 1.3em;
    margin-bottom: 15px;
    font-weight: 600;
}

.focus-card ul {
    list-style: none;
    padding: 0;
}

.focus-card li {
    color: #5a5a5a;
    margin-bottom: 10px;
    padding-left: 20px;
    position: relative;
    line-height: 1.6;
}

.focus-card li:before {
    content: "→";
    position: absolute;
    left: 0;
    color: #ff69b4;
    font-weight: bold;
}

.newsletter-section {
    background: linear-gradient(135deg, rgba(255, 182, 193, 0.3), rgba(255, 105, 180, 0.2));
    border: 2px solid rgba(255, 105, 180, 0.4);
    border-radius: 20px;
    padding: 40px;
    margin: 50px 0;
    text-align: center;
    animation: fadeIn 1.6s ease-out;
}

.newsletter-section h3 {
    color: #ff1493;
    font-size: 1.8em;
    margin-bottom: 15px;
    font-weight: 700;
}

.newsletter-section p {
    color: #5a5a5a;
    font-size: 1.1em;
    margin-bottom: 25px;
    line-height: 1.6;
}

.subscribe-form {
    display: flex;
    gap: 15px;
    max-width: 500px;
    margin: 0 auto;
    flex-wrap: wrap;
    justify-content: center;
}

.subscribe-form input {
    flex: 1;
    min-width: 250px;
    padding: 15px 20px;
    border: 2px solid rgba(255, 105, 180, 0.4);
    border-radius: 8px;
    font-size: 1em;
    background: white;
    color: #5a5a5a;
    transition: all 0.3s ease;
}

.subscribe-form input:focus {
    outline: none;
    border-color: #ff69b4;
    box-shadow: 0 0 15px rgba(255, 105, 180, 0.3);
}

.subscribe-form button {
    padding: 15px 35px;
    background: linear-gradient(135deg, #ff1493, #ff69b4);
    color: white;
    border: none;
    border-radius: 8px;
    font-size: 1em;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.3s ease;
}

.subscribe-form button:hover {
    transform: translateY(-2px);
    box-shadow: 0 8px 20px rgba(255, 105, 180, 0.5);
    animation: pulse 1s infinite;
}

.subscribe-message {
    margin-top: 15px;
    padding: 10px;
    border-radius: 8px;
    display: none;
}

.subscribe-message.success {
    background: rgba(76, 175, 80, 0.1);
    border: 1px solid rgba(76, 175, 80, 0.3);
    color: #2e7d32;
}

.subscribe-message.error {
    background: rgba(244, 67, 54, 0.1);
    border: 1px solid rgba(244, 67, 54, 0.3);
    color: #c62828;
}

.social-links {
    display: flex;
    gap: 15px;
    justify-content: center;
    flex-wrap: wrap;
    margin: 50px 0;
}

.social-btn {
    padding: 12px 28px;
    background: rgba(255, 105, 180, 0.15);
    border: 2px solid #ff69b4;
    color: #ff1493;
    text-decoration: none;
    border-radius: 8px;
    font-weight: 600;
    transition: all 0.3s ease;
    display: inline-block;
}

.social-btn:hover {
    background: linear-gradient(135deg, #ff1493, #ff69b4);
    color: white;
    transform: translateY(-2px);
    box-shadow: 0 8px 20px rgba(255, 105, 180, 0.5);
}

.about-footer {
    text-align: center;
    margin-top: 80px;
    padding-top: 30px;
    border-top: 2px solid rgba(255, 105, 180, 0.3);
    color: #c2588d;
    font-size: 0.9em;
}

@media (max-width: 968px) {
    .profile-container {
        flex-direction: column;
    }

    .profile-left {
        flex-direction: column;
        width: 100%;
    }

    .profile-image {
        width: 100%;
        max-width: 300px;
        height: 300px;
    }

    .about-header h1 {
        font-size: 2.2em;
    }

    .focus-areas {
        grid-template-columns: 1fr;
    }

    .subscribe-form {
        flex-direction: column;
    }

    .subscribe-form input {
        min-width: 100%;
    }
}
</style>

<div class="about-page-wrapper">
    <div class="particle-background" id="particleBg"></div>

    <div class="about-container">
        <div class="about-header">
            <h1>HANANE AIT BAH</h1>
            <div class="divider"></div>
            <p class="about-tagline">Network Security Student | Cybersecurity Enthusiast | NSC @ FSSM</p>
        </div>

        <div class="profile-container">
            <div class="profile-left">
                <div class="profile-image">
                    <img src="https://github.com/user-attachments/assets/6c553521-15b0-4d1a-aa6f-798d79f1c896" alt="Hanane AIT BAH">
                </div>
                
                <div class="quick-info">
                    <h3>Contact Information</h3>
                    <p><strong>Location:</strong> Marrakech, Morocco</p>
                    <p><strong>Institution:</strong> FSSM, Cadi Ayyad University</p>
                    <p><strong>Program:</strong> Bachelor's in Networking & Cybersecurity</p>
                    <p><strong>Blog Launch:</strong> January 1, 2026</p>
                </div>
            </div>
        </div>

        <div class="about-section">
            <h2>Welcome to Cyberia</h2>
            <p>Je m'appelle <span class="highlight">Hanane (Haname)</span>, étudiante en cybersécurité à la Faculté des Sciences Semlalia (FSSM), Université Cadi Ayyad. Je suis actuellement en Licence Réseaux et Cybersécurité après avoir complété des études fondamentales en Informatique.</p>
            
            <p>Le 1er janvier 2026, j'ai lancé ce blog pour documenter mon parcours en tant qu'étudiante <span class="highlight">NSC (Network Security)</span>. Mon objectif est de partager mes notes, projets et réflexions liés à la cybersécurité, la défense réseau et mon parcours académique.</p>
            
            <p>Je suis passionnée par la <span class="highlight">sécurité offensive</span>, l'<span class="highlight">analyse de vulnérabilités</span> et le <span class="highlight">reverse engineering</span>. Ce blog sert à la fois de journal d'apprentissage personnel et de ressource pour les autres intéressés par le domaine.</p>
        </div>

        <h2 class="section-title">Ce que vous trouverez ici</h2>
        
        <div class="focus-areas">
            <div class="focus-card">
                <h3>Mon parcours académique à la FSSM</h3>
                <ul>
                    <li>Notes de cours et matériel d'étude</li>
                    <li>Projets académiques</li>
                    <li>Concepts clés en sécurité réseau</li>
                    <li>Expériences d'apprentissage universitaire</li>
                </ul>
            </div>

            <div class="focus-card">
                <h3>Mes parcours TryHackMe</h3>
                <ul>
                    <li>Rooms complétés</li>
                    <li>Write-ups détaillés</li>
                    <li>Badges et achievements</li>
                    <li>Suivi du développement des compétences</li>
                </ul>
            </div>

            <div class="focus-card">
                <h3>Mon laboratoire personnel</h3>
                <ul>
                    <li>Configurations de machines virtuelles</li>
                    <li>Topologies réseau</li>
                    <li>Expérimentations pratiques</li>
                    <li>Documentation technique</li>
                </ul>
            </div>

            <div class="focus-card">
                <h3>Ressources et notes d'apprentissage</h3>
                <ul>
                    <li>Matériel d'étude sélectionné</li>
                    <li>Revues d'outils et logiciels</li>
                    <li>Meilleures pratiques de sécurité</li>
                    <li>Recommandations communautaires</li>
                </ul>
            </div>
        </div>

        <div class="newsletter-section">
            <h3>Restez informé du nouveau contenu</h3>
            <p>Abonnez-vous pour recevoir des notifications chaque fois que je publie de nouveaux articles, write-ups ou projets. Rejoignez la communauté Cyberia !</p>
            
            <form class="subscribe-form" id="subscribeForm">
                <input type="email" id="emailInput" placeholder="Entrez votre adresse email" required>
                <button type="submit">S'abonner</button>
            </form>
            
            <div class="subscribe-message" id="subscribeMessage"></div>
        </div>

        <h2 class="section-title">Connectez-vous avec moi</h2>

        <div class="social-links">
            <a href="https://tryhackme.com/p/hananeaitbah" class="social-btn" target="_blank">TryHackMe</a>
            <a href="https://github.com/ItsHaname" class="social-btn" target="_blank">GitHub</a>
            <a href="https://www.linkedin.com/in/hanane-ait-bah-746ba5357/" class="social-btn" target="_blank">LinkedIn</a>
        </div>

        <div class="about-footer">
            <p>&copy; 2026 Hanane AIT BAH - Network Security Student @ FSSM</p>
            <p>Cyberia: A Personal Cybersecurity Learning Journey</p>
        </div>
    </div>
</div>

<script>
document.addEventListener('DOMContentLoaded', function() {
    const particleBg = document.getElementById('particleBg');
    
    // Particules qui tombent
    const symbols = ['0', '1', '◆', '◇', '●', '○', '■', '□', '▲', '△'];
    
    for (let i = 0; i < 80; i++) {
        const particle = document.createElement('div');
        particle.className = 'particle';
        particle.textContent = symbols[Math.floor(Math.random() * symbols.length)];
        
        particle.style.left = Math.random() * 100 + 'vw';
        particle.style.fontSize = (Math.random() * 12 + 14) + 'px';
        
        const duration = Math.random() * 20 + 15;
        const delay = Math.random() * 10;
        particle.style.animationDuration = duration + 's';
        particle.style.animationDelay = delay + 's';
        
        particleBg.appendChild(particle);
    }
    
    // Particules flottantes
    for (let i = 0; i < 30; i++) {
        const floatParticle = document.createElement('div');
        floatParticle.className = 'particle floating';
        floatParticle.textContent = symbols[Math.floor(Math.random() * symbols.length)];
        
        floatParticle.style.left = Math.random() * 100 + 'vw';
        floatParticle.style.top = Math.random() * 100 + 'vh';
        floatParticle.style.fontSize = (Math.random() * 14 + 12) + 'px';
        floatParticle.style.animationDelay = Math.random() * 5 + 's';
        floatParticle.style.opacity = Math.random() * 0.4 + 0.2;
        
        particleBg.appendChild(floatParticle);
    }

    // Gestion du formulaire d'inscription
    const form = document.getElementById('subscribeForm');
    const emailInput = document.getElementById('emailInput');
    const message = document.getElementById('subscribeMessage');

    form.addEventListener('submit', function(e) {
        e.preventDefault();
        
        const email = emailInput.value.trim();
        
        if (email) {
            let subscribers = JSON.parse(localStorage.getItem('subscribers') || '[]');
            
            if (subscribers.includes(email)) {
                message.textContent = 'Vous êtes déjà abonné !';
                message.className = 'subscribe-message error';
            } else {
                subscribers.push(email);
                localStorage.setItem('subscribers', JSON.stringify(subscribers));
                
                message.textContent = 'Merci de vous être abonné ! Vous recevrez des notifications pour le nouveau contenu.';
                message.className = 'subscribe-message success';
                emailInput.value = '';
            }
            
            message.style.display = 'block';
            
            setTimeout(() => {
                message.style.display = 'none';
            }, 5000);
        }
    });
});
</script>
