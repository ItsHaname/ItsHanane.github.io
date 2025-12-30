/* CYBERIA Header avec ligne horizontale */
.cyberia-header {
  text-align: center;
  margin-bottom: 60px;
  padding: 40px 20px;
  position: relative;
  background: rgba(0, 20, 40, 0.6);
  border-radius: 30px;
  border: 3px solid #1e4d7b;
  box-shadow: 0 0 40px rgba(30, 77, 123, 0.5), inset 0 0 30px rgba(30, 77, 123, 0.2);
}

.cyberia-title {
  font-size: 5em;
  color: #ff6b4a;
  text-shadow: 
    0 0 10px #ff6b4a,
    0 0 20px #ff6b4a,
    0 0 30px #ff6b4a,
    0 0 40px #ff3300;
  margin: 0;
  font-weight: 900;
  letter-spacing: 10px;
  text-transform: uppercase;
  position: relative;
  font-style: italic;
  -webkit-text-stroke: 2px #ff3300;
  paint-order: stroke fill;
}

/* Ligne horizontale comme dans l'image */
.cyberia-line {
  width: 100%;
  height: 3px;
  background: linear-gradient(90deg, 
    transparent, 
    #1e4d7b, 
    #3b82f6, 
    #1e4d7b, 
    transparent);
  margin: 20px auto;
  max-width: 500px;
  box-shadow: 0 0 15px #3b82f6;
}

.cyberia-subtitle {
  font-size: 1.8em;
  color: #60a5fa;
  margin: 10px 0 0 0;
  text-shadow: 
    0 0 10px #60a5fa,
    0 0 20px #3b82f6,
    0 0 30px #2563eb;
  letter-spacing: 4px;
  font-weight: 300;
  font-style: italic;
}

.cyberia-subtitle::after {
  content: '_';
  animation: blink 1s infinite;
  color: #60a5fa;
}1
