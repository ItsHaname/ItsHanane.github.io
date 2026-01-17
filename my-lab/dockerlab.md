<style>
  body {
    background: #1a1f2e;
    margin: 0;
    padding: 0;
    display: flex;
    flex-direction: column;
    align-items: center; 
  }

  .container {
    /* On passe à 85% pour laisser plus d'espace sur les côtés */
    width: 85%; 
    /* On limite la largeur maximale pour les très grands écrans */
    max-width: 1400px; 
    margin: 40px auto;
  }

  img {
    display: block;
    width: 100%;
    height: auto;
    margin-bottom: 50px; /* Plus d'espace entre les images pour aérer */
    border-radius: 15px; /* Coins encore plus arrondis pour un look moderne */
    box-shadow: 0 10px 40px rgba(0, 0, 0, 0.6);
    /* Transition pour que le survol soit tout doux */
    transition: all 0.4s ease-in-out; 
  }

  img:hover {
    transform: translateY(-5px); /* L'image monte légèrement au survol */
    box-shadow: 0 20px 50px rgba(0, 217, 255, 0.3);
    filter: brightness(1.05);
  }
</style>

<div class="container">
  <img src="https://github.com/user-attachments/assets/5b6bcc1a-6f76-46fd-88fb-34b43fbaa0e5" />
  <img src="https://github.com/user-attachments/assets/8d54004b-3bcb-4f57-b5a0-310241f73b75" />
  <img src="https://github.com/user-attachments/assets/972ed0ac-d641-4f54-bd52-c4f9b4380774" />
  <img src="https://github.com/user-attachments/assets/39848e20-ce8b-49cb-ab3a-5679691abe8c" />
</div>
