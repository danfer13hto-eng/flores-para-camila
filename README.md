<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Para Camila 💛</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      font-family: 'Segoe UI', sans-serif;
      background: linear-gradient(to bottom, #fffde7, #fff9c4);
      color: #333;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      min-height: 100vh;
      text-align: center;
      overflow: hidden;
    }

    h1 {
      color: #fdd835;
      font-size: 3em;
      margin-bottom: 0.2em;
    }

    p {
      font-size: 1.5em;
      margin-bottom: 1em;
    }

    button {
      background-color: #fdd835;
      border: none;
      padding: 15px 30px;
      font-size: 1.2em;
      color: #333;
      border-radius: 10px;
      cursor: pointer;
      transition: all 0.3s ease;
    }

    button:hover {
      background-color: #ffee58;
      transform: scale(1.05);
    }

    .message {
      display: none;
      font-size: 1.3em;
      margin-top: 20px;
      color: #4caf50;
      animation: fadeIn 2s ease forwards;
    }

    @keyframes fadeIn {
      from { opacity: 0; }
      to { opacity: 1; }
    }

    .flowers {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      pointer-events: none;
      z-index: -1;
    }

    .flower {
      position: absolute;
      width: 40px;
      height: 40px;
      background-image: url('https://i.ibb.co/3WJmdnC/yellow-flower.png');
      background-size: cover;
      animation: float 10s linear infinite;
    }

    @keyframes float {
      0% {
        transform: translateY(0) rotate(0deg);
        opacity: 1;
      }
      100% {
        transform: translateY(100vh) rotate(360deg);
        opacity: 0;
      }
    }

    iframe {
      display: none;
    }
  </style>
</head>
<body>

  <h1>💛 Para Camila Hernández 💛</h1>
  <p>La flor más hermosa entre todas las flores. Te amo con todo mi corazón.</p>

  <button onclick="mostrarMensaje()">Haz clic si tú también me amas ❤️</button>
  <div class="message" id="mensaje">¡Sabía que sí! 💕 Gracias por estar en mi vida, Camila.</div>

  <div class="flowers" id="flores"></div>

  <!-- Reproductor de YouTube oculto -->
  <iframe 
    id="player" 
    src="https://www.youtube.com/embed/wnJ6LuUFpMo?autoplay=1&loop=1&playlist=wnJ6LuUFpMo&controls=0&mute=0"
    allow="autoplay"
    frameborder="0"
    allowfullscreen
  ></iframe>

  <script>
    function mostrarMensaje() {
      document.getElementById('mensaje').style.display = 'block';
    }

    function crearFlores() {
      const container = document.getElementById('flores');
      for (let i = 0; i < 30; i++) {
        const flower = document.createElement('div');
        flower.classList.add('flower');
        flower.style.left = Math.random() * 100 + 'vw';
        flower.style.animationDuration = (5 + Math.random() * 5) + 's';
        container.appendChild(flower);
      }
    }

    crearFlores();
  </script>
</body>
</html>
