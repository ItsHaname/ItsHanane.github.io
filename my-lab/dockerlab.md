<style>
  body {
    background: #1a1f2e;
    margin: 0;
    padding: 0;
    /* On centre tout le contenu du body */
    display: flex;
    flex-direction: column;
    align-items: center; 
  }

  .container {
    /* On prend 96% de la largeur pour laisser 2% de vide de chaque côté */
    width: 96%; 
    max-width: 1800px; /* Optionnel: évite que ce soit TROP géant sur les écrans TV */
    margin: 20px auto;
  }

  img {
    display: block;
    width: 100%; /* L'image remplit tout le container de 96% */
    height: auto;
    margin-bottom: 30px; /* Espace entre les images */
    border-radius: 12px; /* Un petit arrondi pour la douceur */
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5); /* Une ombre plus profonde */
    transition: transform 0.3s ease;
  }

  img:hover {
    transform: scale(1.01); /* Un très léger zoom au survol */
    box-shadow: 0 15px 40px rgba(0, 217, 255, 0.3);
  }
</style>

<div class="container">
  <img src="https://github.com/user-attachments/assets/5b6bcc1a-6f76-46fd-88fb-34b43fbaa0e5" />
  <img src="https://github.com/user-attachments/assets/8d54004b-3bcb-4f57-b5a0-310241f73b75" />
  <img src="https://github.com/user-attachments/assets/972ed0ac-d641-4f54-bd52-c4f9b4380774" />
  <img src="https://github.com/user-attachments/assets/39848e20-ce8b-49cb-ab3a-5679691abe8c" />
</div>
